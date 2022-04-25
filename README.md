# icinga2-telegram-notification
Push Icinga2 notificaitons into Telegram groups or channel as bot

This is an modified version of https://github.com/seffparker/icinga2-rich-slack-notification made compatible with Telegram Bot API.

# Preview
![Sample Notification Preview](https://github.com/seffparker/icinga2-telegram-notification/blob/main/preview.png?raw=true "Sample Notification Preview")

# Features
1. Custom emoji for states like OK, Warning, Critical etc.
1. Includes raw plugin outputs.
1. Shows alert state-duration in human readable format.
1. Shows comment with owner for Acknowledgement and Custom notifications.
1. Can send notifications to multiple Telegram Channels or Groups
1. The default re-notification interval can be changed.
1. The re-notification interval can be customized per host or service.
1. When the notification for a host is enabled, it will be inherited to all of its services checks, unless disabled for the specific service(s).

# Installation and Basic Configuration
1. Copy the two `telegram-notification-*` confs to `/etc/icinga2/conf.d/` directory and configure the existing host or service configuration like the provided one in `sample.conf`
1. Modify the `vars.telegram_notifications_icinga2_base_url` in `telegram-notifications-configuration.conf` with your IcingaWeb2 Base URL. This is to jump to Alert Dashboard right from Telegram channel.
1. Modify the `vars.telegram_notifications_icinga2_base_url` in `telegram-notifications-configuration.conf` with the AUTH_TOKEN of Telegram Bot
1. Get the `chat_id` of the bot instance and add in to the `object User` section of required notification user(s). [Read more here](https://sean-bradley.medium.com/get-telegram-chat-id-80b575520659)
1. Validate the Icinga2 configuration and restart the service.

# Advanced Configuration
1. The notification emoji can be changed in the array variable `vars.telegram_notifications_emoji` array.
1. Notifications for Scheduled DOWNTIME alerts are disabled by default. It can be enabled in the variable `types`
