# CDriverVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x180033de0`
- end: `0x18003401d`
- name: `?InvokeCallback@CDriverVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `573`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003b38`
- `0x180009ed8`
- `0x180009f00`
- `0x180033a1c`
- `0x180033aec`
- `0x180033de0`
- `0x180034024`
- `0x180034848`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033eed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180033eed`
- `ntdll!NtQuerySystemInformation` at `0x180033f2d`
- `ntdll!NtQuerySystemInformation` at `0x180033f2d`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180033ea5`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180033ea5`

## pseudocode

```c

```
