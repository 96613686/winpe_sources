# DllUnregisterServer

- ea: `0x18000d680`
- end: `0x18000d6bf`
- name: `DllUnregisterServer`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015630`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // rdx

  UnregisterServer(&CLSID_DirectMusic, v0, (const CHAR *)&g_szVerIndProgID, (const CHAR *)&g_szProgID);
  UnregisterServer(&CLSID_DirectMusicCollection, v1, (const CHAR *)&g_szCollVerIndProgID, (const CHAR *)&g_szCollProgID);
  return 0;
}

```

## disassembly

```asm
0x18000d680  sub     rsp, 28h
0x18000d684  lea     r9, ?g_szProgID@@3PADA; "Microsoft.DirectMusic.1"
0x18000d68b  lea     r8, ?g_szVerIndProgID@@3PADA; "Microsoft.DirectMusic"
0x18000d692  lea     rcx, CLSID_DirectMusic
0x18000d699  call    UnregisterServer
0x18000d69e  lea     r9, ?g_szCollProgID@@3PADA; "Microsoft.DirectMusicCollection.1"
0x18000d6a5  lea     r8, ?g_szCollVerIndProgID@@3PADA; "Microsoft.DirectMusicCollection"
0x18000d6ac  lea     rcx, CLSID_DirectMusicCollection
0x18000d6b3  call    UnregisterServer
0x18000d6b8  xor     eax, eax
0x18000d6ba  add     rsp, 28h
0x18000d6be  retn
```
