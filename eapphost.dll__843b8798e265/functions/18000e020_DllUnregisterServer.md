# DllUnregisterServer

- ea: `0x18000e020`
- end: `0x18000e062`
- name: `DllUnregisterServer`
- size: `66`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e020`
- `0x18000f8a4`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000e04d`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000e04d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  return ComOutOfProcUnregisterServer();
}

```

## disassembly

```asm
0x18000e020  sub     rsp, 28h
0x18000e024  mov     rax, cs:aProxyFileList
0x18000e02b  mov     rcx, [rax+8]
0x18000e02f  mov     rax, [rcx]
0x18000e032  test    rax, rax
0x18000e035  jz      short loc_18000E03C
0x18000e037  mov     r8, [rax]
0x18000e03a  jmp     short loc_18000E03F
0x18000e03c  xor     r8d, r8d; pclsid
0x18000e03f  mov     rcx, cs:hProxyDll; hDll
0x18000e046  lea     rdx, aProxyFileList; pProxyFileList
0x18000e04d  call    cs:__imp_NdrDllUnregisterProxy
0x18000e054  nop     dword ptr [rax+rax+00h]
0x18000e059  add     rsp, 28h
0x18000e05d  jmp     ?ComOutOfProcUnregisterServer@@YAJXZ; ComOutOfProcUnregisterServer(void)
```
