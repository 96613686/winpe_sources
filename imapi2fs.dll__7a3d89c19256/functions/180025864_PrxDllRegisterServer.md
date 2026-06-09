# PrxDllRegisterServer

- ea: `0x180025864`
- end: `0x180025894`
- name: `PrxDllRegisterServer`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800283d0`
- `0x180028470`

## callees

- `0x180025864`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18002588d`

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
0x180025864  mov     rax, cs:aProxyFileList
0x18002586b  mov     rcx, [rax+8]
0x18002586f  mov     rax, [rcx]
0x180025872  test    rax, rax
0x180025875  jz      short loc_18002587C
0x180025877  mov     r8, [rax]
0x18002587a  jmp     short loc_18002587F
0x18002587c  xor     r8d, r8d
0x18002587f  mov     rcx, cs:hProxyDll
0x180025886  lea     rdx, aProxyFileList
0x18002588d  jmp     cs:__imp_NdrDllRegisterProxy
```
