# DllRegisterServer

- ea: `0x18000ba40`
- end: `0x18000ba70`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ba40`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000ba69`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x18000ba40  mov     rax, cs:aProxyFileList
0x18000ba47  mov     rcx, [rax+8]
0x18000ba4b  mov     rax, [rcx]
0x18000ba4e  test    rax, rax
0x18000ba51  jz      short loc_18000BA58
0x18000ba53  mov     r8, [rax]
0x18000ba56  jmp     short loc_18000BA5B
0x18000ba58  xor     r8d, r8d
0x18000ba5b  mov     rcx, cs:hProxyDll
0x18000ba62  lea     rdx, aProxyFileList
0x18000ba69  jmp     cs:__imp_NdrDllRegisterProxy
```
