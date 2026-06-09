# DllRegisterServer

- ea: `0x180002970`
- end: `0x180002975`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001cac`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CsvtaskHandler,&_GUID const CLSID_pstask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180002970  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCsvtaskHandler@@$1?CLSID_pstask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CsvtaskHandler,&_GUID const CLSID_pstask>::DllRegisterServer(void)
```
