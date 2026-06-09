# CAutoVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x18002c3e0`
- end: `0x18002c6ea`
- name: `?InvokeCallback@CAutoVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `778`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800028b4`
- `0x180003b38`
- `0x180009ed8`
- `0x180009f00`
- `0x18002b4c4`
- `0x18002c3e0`
- `0x18002cc7c`
- `0x180037098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c5b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c5b9`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002c4fc`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002c4fc`
- `wer!WerpSetReportFlags` at `0x18002c4b3`
- `wer!WerpSetReportFlags` at `0x18002c4b3`
- `wer!WerpGetReportFlags` at `0x18002c45f`
- `wer!WerpGetReportFlags` at `0x18002c45f`

## pseudocode

```c

```
