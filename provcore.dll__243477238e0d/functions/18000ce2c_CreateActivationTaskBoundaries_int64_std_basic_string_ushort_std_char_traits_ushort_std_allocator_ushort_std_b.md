# CreateActivationTaskBoundaries(__int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000ce2c`
- end: `0x18000d01c`
- name: `?CreateActivationTaskBoundaries@@YAX_JAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `496`
- prototype: `void __fastcall(__int64 DelayInSeconds, std::wstring *StartBoundary, std::wstring *EndBoundary)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000bfe0`

## callees

- `0x180002790`
- `0x1800033a4`
- `0x18000866c`
- `0x18000ce2c`
- `0x180012400`
- `0x1800127cc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000ce61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000ce61`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000ce77`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000ce77`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000ce9d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000cf64`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000ce9d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000cf64`

## pseudocode

```c

```
