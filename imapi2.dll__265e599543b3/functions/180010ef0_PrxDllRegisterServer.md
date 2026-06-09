# PrxDllRegisterServer

- ea: `0x180010ef0`
- end: `0x180010f20`
- name: `PrxDllRegisterServer`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800421c0`
- `0x180042260`

## callees

- `0x180010ef0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180010f19`

## pseudocode

```c
HRESULT PrxDllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180010ef0  mov     rax, cs:aProxyFileList
0x180010ef7  mov     rcx, [rax+8]
0x180010efb  mov     rax, [rcx]
0x180010efe  test    rax, rax
0x180010f01  jz      short loc_180010F08
0x180010f03  mov     r8, [rax]
0x180010f06  jmp     short loc_180010F0B
0x180010f08  xor     r8d, r8d
0x180010f0b  mov     rcx, cs:hProxyDll
0x180010f12  lea     rdx, aProxyFileList
0x180010f19  jmp     cs:__imp_NdrDllRegisterProxy
```
