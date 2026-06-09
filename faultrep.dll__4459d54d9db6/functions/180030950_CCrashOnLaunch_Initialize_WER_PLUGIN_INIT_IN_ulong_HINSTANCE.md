# CCrashOnLaunch::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x180030950`
- end: `0x180030aa3`
- name: `?Initialize@CCrashOnLaunch@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(CCrashOnLaunch *this, struct WER_PLUGIN_INIT_IN *, __int64, HINSTANCE)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180030950`
- `0x180030aac`
- `0x18003e5a8`
- `0x1800492d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180030a16`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180030a16`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030a24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030a24`
- `ntdll!DbgPrint` at `0x180030a85`
- `ntdll!DbgPrint` at `0x180030a85`

## pseudocode

```c

```
