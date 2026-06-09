# CFDRPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x180035c50`
- end: `0x180035fdd`
- name: `?InvokeCallback@CFDRPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `909`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800028b4`
- `0x180003b38`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180034ccc`
- `0x180035168`
- `0x180035224`
- `0x180035c50`
- `0x18003659c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035ef2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035ef2`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180035db0`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180035db0`
- `wer!WerpSetReportFlags` at `0x180035d67`
- `wer!WerpSetReportFlags` at `0x180035d67`
- `wer!WerpGetReportFlags` at `0x180035d13`
- `wer!WerpGetReportFlags` at `0x180035d13`

## pseudocode

```c

```
