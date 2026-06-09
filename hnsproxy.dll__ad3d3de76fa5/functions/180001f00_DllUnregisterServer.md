# DllUnregisterServer

- ea: `0x180001f00`
- end: `0x180001f30`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001f00`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180001f29`

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
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180001f00  mov     rax, cs:aProxyFileList
0x180001f07  mov     rcx, [rax+8]
0x180001f0b  mov     rax, [rcx]
0x180001f0e  test    rax, rax
0x180001f11  jz      short loc_180001F18
0x180001f13  mov     r8, [rax]
0x180001f16  jmp     short loc_180001F1B
0x180001f18  xor     r8d, r8d
0x180001f1b  mov     rcx, cs:hProxyDll
0x180001f22  lea     rdx, aProxyFileList
0x180001f29  jmp     cs:__imp_NdrDllUnregisterProxy
```
