# DllRegisterServer

- ea: `0x180007d40`
- end: `0x180007d97`
- name: `DllRegisterServer`
- size: `87`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cae4`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  __int64 v1; // rcx

  RegisterServer(
    v0,
    &CLSID_DirectMusicLoader,
    (BYTE *)&g_szFriendlyName,
    (BYTE *)&g_szVerIndProgID,
    (BYTE *)&g_szProgID);
  RegisterServer(
    v1,
    &CLSID_DirectMusicContainer,
    (BYTE *)&g_szContFriendlyName,
    (BYTE *)&g_szContVerIndProgID,
    (BYTE *)&g_szContProgID);
  return 0;
}

```

## disassembly

```asm
0x180007d40  sub     rsp, 38h
0x180007d44  lea     rax, ?g_szProgID@@3PADA; "Microsoft.DirectMusicLoader.1"
0x180007d4b  lea     r9, ?g_szVerIndProgID@@3PADA; "Microsoft.DirectMusicLoader"
0x180007d52  mov     [rsp+38h+var_18], rax
0x180007d57  lea     r8, ?g_szFriendlyName@@3PADA; "DirectMusicLoader"
0x180007d5e  lea     rdx, CLSID_DirectMusicLoader
0x180007d65  call    RegisterServer
0x180007d6a  lea     rax, ?g_szContProgID@@3PADA; "Microsoft.DirectMusicContainer.1"
0x180007d71  lea     r9, ?g_szContVerIndProgID@@3PADA; "Microsoft.DirectMusicContainer"
0x180007d78  mov     [rsp+38h+var_18], rax
0x180007d7d  lea     r8, ?g_szContFriendlyName@@3PADA; "DirectMusicContainer"
0x180007d84  lea     rdx, CLSID_DirectMusicContainer
0x180007d8b  call    RegisterServer
0x180007d90  xor     eax, eax
0x180007d92  add     rsp, 38h
0x180007d96  retn
```
