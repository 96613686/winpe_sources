# UtilGetProcessPathFromHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180016e94`
- end: `0x180016f77`
- name: `?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016c20`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009e04`
- `0x180016e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f02`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180016ef8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180016ef8`

## pseudocode

```c

```
