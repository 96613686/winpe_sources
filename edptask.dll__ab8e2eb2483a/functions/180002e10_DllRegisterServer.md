# DllRegisterServer

- ea: `0x180002e10`
- end: `0x180002e15`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002770`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CEdpNotificationTaskHandler,&_GUID const CLSID_EdpNotificationTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180002e10  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCEdpNotificationTaskHandler@@$1?CLSID_EdpNotificationTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CEdpNotificationTaskHandler,&_GUID const CLSID_EdpNotificationTask>::DllRegisterServer(void)
```
