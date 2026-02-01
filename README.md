# mod-bg-queue-announcer

## Description

This module announces Battleground queue status to players or the world when players join the queue.

This is a modular implementation of the BG Queue Announcer functionality that was previously part of the core. See [Issue #23411](https://github.com/azerothcore/azerothcore-wotlk/issues/23411).

## Features

- Announce BG queue status when players join
- Option to announce only to the player who joins
- Option to use timed announcements instead of immediate
- Spam protection to prevent announcement flooding
- Optional announcement when Battlegrounds start
- Configurable minimum player limits for announcements

## Installation

1. Clone this module into your `modules` folder
2. Re-run cmake and compile
3. Copy `mod_bg_queue_announcer.conf.dist` to your server's config directory as `mod_bg_queue_announcer.conf`
4. Edit the config file to enable and configure the module

## Configuration

| Option | Default | Description |
|--------|---------|-------------|
| BgQueueAnnouncer.Enable | 0 | Enable/disable the module |
| BgQueueAnnouncer.PlayerOnly | 0 | Announce only to the joining player |
| BgQueueAnnouncer.Timed | 0 | Use timed announcements |
| BgQueueAnnouncer.Timer | 30000 | Timer interval in milliseconds |
| BgQueueAnnouncer.SpamProtection.Delay | 30 | Delay between announcements (seconds) |
| BgQueueAnnouncer.Limit.MinLevel | 0 | Min level to apply player limit filter |
| BgQueueAnnouncer.Limit.MinPlayers | 3 | Min players before announcing |
| BgQueueAnnouncer.OnStart.Enable | 1 | Announce when BG starts |

## Requirements

- AzerothCore with the `CanSendMessageBGQueue` hook available

## Note

This module requires that the core BG Queue Announcer code is disabled or removed. If both are enabled, announcements may be duplicated.

## Credits

- AzerothCore Team
- Based on original core implementation
