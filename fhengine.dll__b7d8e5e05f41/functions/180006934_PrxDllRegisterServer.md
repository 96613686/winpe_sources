# PrxDllRegisterServer

- ea: `0x180006934`
- end: `0x180006964`
- name: `PrxDllRegisterServer`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007570`
- `0x1800075f0`

## callees

- `0x180006934`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000695d`

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
0x180006934  mov     rax, cs:aProxyFileList
0x18000693b  mov     rcx, [rax+8]
0x18000693f  mov     rax, [rcx]
0x180006942  test    rax, rax
0x180006945  jz      short loc_18000694C
0x180006947  mov     r8, [rax]
0x18000694a  jmp     short loc_18000694F
0x18000694c  xor     r8d, r8d
0x18000694f  mov     rcx, cs:hProxyDll
0x180006956  lea     rdx, aProxyFileList
0x18000695d  jmp     cs:__imp_NdrDllRegisterProxy
```
