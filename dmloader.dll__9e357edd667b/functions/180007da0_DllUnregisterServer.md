# DllUnregisterServer

- ea: `0x180007da0`
- end: `0x180007ddf`
- name: `DllUnregisterServer`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cca0`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // rdx

  UnregisterServer(&CLSID_DirectMusicLoader, v0, (const CHAR *)&g_szVerIndProgID, (const CHAR *)&g_szProgID);
  UnregisterServer(&CLSID_DirectMusicContainer, v1, (const CHAR *)&g_szContVerIndProgID, (const CHAR *)&g_szContProgID);
  return 0;
}

```

## disassembly

```asm
0x180007da0  sub     rsp, 28h
0x180007da4  lea     r9, ?g_szProgID@@3PADA; "Microsoft.DirectMusicLoader.1"
0x180007dab  lea     r8, ?g_szVerIndProgID@@3PADA; "Microsoft.DirectMusicLoader"
0x180007db2  lea     rcx, CLSID_DirectMusicLoader
0x180007db9  call    UnregisterServer
0x180007dbe  lea     r9, ?g_szContProgID@@3PADA; "Microsoft.DirectMusicContainer.1"
0x180007dc5  lea     r8, ?g_szContVerIndProgID@@3PADA; "Microsoft.DirectMusicContainer"
0x180007dcc  lea     rcx, CLSID_DirectMusicContainer
0x180007dd3  call    UnregisterServer
0x180007dd8  xor     eax, eax
0x180007dda  add     rsp, 28h
0x180007dde  retn
```
