# RealtimeProtection::CRtpDlpEngine::CheckIfShadowFile(wchar_t const *,_MP_KNOWN_PROCESS_TYPE,ulong,ulong,ulong,bool &)

- ea: `0x180194970`
- end: `0x1801952f7`
- name: `?CheckIfShadowFile@CRtpDlpEngine@RealtimeProtection@@AEAAJPEB_WW4_MP_KNOWN_PROCESS_TYPE@@KKKAEA_N@Z`
- size: `2439`
- prototype: `int __high(const wchar_t *, enum _MP_KNOWN_PROCESS_TYPE, unsigned int, unsigned int, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x18018d9f0`

## callees

- `0x180029290`
- `0x180029590`
- `0x18002e728`
- `0x180034420`
- `0x180038450`
- `0x18004e000`
- `0x18006aa2c`
- `0x180080030`
- `0x1800809d0`
- `0x180080fd0`
- `0x180089fa0`
- `0x18009ffb8`
- `0x18010cb40`
- `0x18010d1e0`
- `0x18010d20c`
- `0x18010d310`
- `0x18010d380`
- `0x18016ad74`
- `0x180194970`
- `0x1801a5598`
- `0x1801a5648`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180194d57`
- `MpClient!MpFreeMemory` at `0x180194db9`
- `MpClient!MpFreeMemory` at `0x180194d57`
- `MpClient!MpFreeMemory` at `0x180194db9`
- `KERNEL32!GetFileAttributesW` at `0x180194c3c`
- `KERNEL32!GetFileAttributesW` at `0x180194c3c`
- `KERNEL32!GetLastError` at `0x180194c4e`
- `KERNEL32!GetLastError` at `0x180194c4e`

## string_xrefs

- `0x180194cd0`: `MpDlp_MarkAsShadowFilePath`

## pseudocode

```c

```
