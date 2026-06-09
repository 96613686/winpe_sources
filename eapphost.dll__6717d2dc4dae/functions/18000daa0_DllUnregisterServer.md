# DllUnregisterServer

- ea: `0x18000daa0`
- end: `0x18000dadc`
- name: `DllUnregisterServer`
- size: `60`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000daa0`
- `0x18000f29c`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000dacd`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000dacd`

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
0x18000daa0  sub     rsp, 28h
0x18000daa4  mov     rax, cs:aProxyFileList
0x18000daab  mov     rcx, [rax+8]
0x18000daaf  mov     rax, [rcx]
0x18000dab2  test    rax, rax
0x18000dab5  jz      short loc_18000DABC
0x18000dab7  mov     r8, [rax]
0x18000daba  jmp     short loc_18000DABF
0x18000dabc  xor     r8d, r8d; pclsid
0x18000dabf  mov     rcx, cs:hProxyDll; hDll
0x18000dac6  lea     rdx, aProxyFileList; pProxyFileList
0x18000dacd  call    cs:__imp_NdrDllUnregisterProxy
0x18000dad3  add     rsp, 28h
0x18000dad7  jmp     ?ComOutOfProcUnregisterServer@@YAJXZ; ComOutOfProcUnregisterServer(void)
```
