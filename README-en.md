### Bilibili Activity Monitor

Bilibili Activity Monitor is a bot for monitoring Bilibili users' activities and live statuses. It sends notifications to specific groups when there are new activities or changes in live status.

#### Features:
- Supports multiple groups, each with its own watchlist.
- Persistent data storage to retain watch status across restarts.

#### Example Usage:
```bash
poetry add nonebot-plugin-bam
```
```python
import nonebot
from nonebot.adapters.onebot.v11 import Adapter

nonebot.init(_env_file=".env")
driver = nonebot.get_driver()
driver.register_adapter(Adapter)
nonebot.load_builtin_plugins()
nonebot.load_plugin("nonebot_plugin_apscheduler")
nonebot.load_plugin("nonebot_plugin_bam")
nonebot.run()
```

`.env` configuration options:
```env
COMMAND_START=["/"]
COMMAND_SEP=["/"]
BAM_DB_FILE=":memory:"
BAM_ON_STARTUP_CLEAN_LIVE_STATUS=false
BAM_MONITOR_TASK_INTERVAL=5
BAM_ACTIVITY_MONITOR_TASK_INTERVAL=0
BAM_LIVE_MONITOR_TASK_INTERVAL=0
BAM_LIVE_API=2
BAM_ACTIVITY_CONTENT_MAX_LENGTH=0
```

#### Command List:

- **Group Commands:**
  - **Add Group:** `@bot /bam/group/add [superuser_qq]`
  - **Remove Group:** `@bot /bam/group/remove`
  - **List Groups:** `/bam/group/list`

- **Follow Commands:**
  - **Add Follow:** `[@bot] /bam/follower/add [qq_group_id] bilibili_uid`
  - **Remove Follow:** `[@bot] /bam/follower/remove [qq_group_id] bilibili_uid`
  - **List Follows:** `[@bot] /bam/follower/list [qq_group_id]`

- **Bilibili Commands:**
  - **Fetch User Data:** `[@bot] /bam/user/fetch bilibili_uid`
  - **Get Activity Info:** `[@bot] /bam/act bilibili_activity_id`

#### License:
MIT

#### Screenshots:
- [Live Notification](https://rikka.7sdre.am/files/af1c9c5a-5f8c-40df-b199-e97525368ec9.png)
- [Activity Notification - Normal](https://rikka.7sdre.am/files/5350ce1c-63f6-4f43-abcc-004e9c722063.png)
- [Activity Notification - Repost](https://rikka.7sdre.am/files/9c43a32b-2df7-4b93-be53-22c50a981c63.png)

For the original source, click [here](https://raw.githubusercontent.com/7sDream/nonebot-plugin-bam/main/README.md).
