# DllRegisterServer

- ea: `0x18000d620`
- end: `0x18000d677`
- name: `DllRegisterServer`
- size: `87`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015474`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  __int64 v1; // rcx

  RegisterServer(v0, &CLSID_DirectMusic, (BYTE *)&g_szFriendlyName, (BYTE *)&g_szVerIndProgID, (BYTE *)&g_szProgID);
  RegisterServer(
    v1,
    &CLSID_DirectMusicCollection,
    (BYTE *)&g_szCollFriendlyName,
    (BYTE *)&g_szCollVerIndProgID,
    (BYTE *)&g_szCollProgID);
  return 0;
}

```

## disassembly

```asm
0x18000d620  sub     rsp, 38h
0x18000d624  lea     rax, ?g_szProgID@@3PADA; "Microsoft.DirectMusic.1"
0x18000d62b  lea     r9, ?g_szVerIndProgID@@3PADA; "Microsoft.DirectMusic"
0x18000d632  mov     [rsp+38h+var_18], rax
0x18000d637  lea     r8, ?g_szFriendlyName@@3PADA; "DirectMusic"
0x18000d63e  lea     rdx, CLSID_DirectMusic
0x18000d645  call    RegisterServer
0x18000d64a  lea     rax, ?g_szCollProgID@@3PADA; "Microsoft.DirectMusicCollection.1"
0x18000d651  lea     r9, ?g_szCollVerIndProgID@@3PADA; "Microsoft.DirectMusicCollection"
0x18000d658  mov     [rsp+38h+var_18], rax
0x18000d65d  lea     r8, ?g_szCollFriendlyName@@3PADA; "DirectMusicCollection"
0x18000d664  lea     rdx, CLSID_DirectMusicCollection
0x18000d66b  call    RegisterServer
0x18000d670  xor     eax, eax
0x18000d672  add     rsp, 38h
0x18000d676  retn
```
