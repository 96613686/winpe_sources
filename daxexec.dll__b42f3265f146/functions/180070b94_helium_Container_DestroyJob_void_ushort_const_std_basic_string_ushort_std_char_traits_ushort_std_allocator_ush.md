# helium::Container::DestroyJob(void *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,helium::ReasonDestroyed,std::optional<long>,DesktopAppXProvider::TryGetViableRunningHeliumContainer *)

- ea: `0x180070b94`
- end: `0x180070ec9`
- name: `?DestroyJob@Container@helium@@SAXPEAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ReasonDestroyed@2@V?$optional@J@4@PEAVTryGetViableRunningHeliumContainer@DesktopAppXProvider@@@Z`
- size: `821`
- prototype: `__int64 __usercall@<rax>(struct _GUID *retstr@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056a70`
- `0x18005b74c`
- `0x1800705d4`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x18002109c`
- `0x18004abc0`
- `0x1800545a0`
- `0x18006dd94`
- `0x18006df94`
- `0x18006e168`
- `0x180070b94`
- `0x1800731f4`
- `0x180097fb8`
- `0x1800983ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070dad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180070dad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180070e73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180070e73`
- `ntdll!RtlNtStatusToDosError` at `0x180070d44`
- `ntdll!RtlNtStatusToDosError` at `0x180070d44`
- `ntdll!NtMakeTemporaryObject` at `0x180070cf4`
- `ntdll!NtMakeTemporaryObject` at `0x180070cf4`
- `container!WcCleanupContainer` at `0x180070cbb`
- `container!WcCleanupContainer` at `0x180070cbb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180070c34`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180070c34`

## string_xrefs

- `0x180070e9e`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c

```
