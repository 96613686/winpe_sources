# DllUnregisterServer

- ea: `0x180002190`
- end: `0x1800021c0`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002190`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800021b9`

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
0x180002190  mov     rax, cs:aProxyFileList
0x180002197  mov     rcx, [rax+8]
0x18000219b  mov     rax, [rcx]
0x18000219e  test    rax, rax
0x1800021a1  jz      short loc_1800021A8
0x1800021a3  mov     r8, [rax]
0x1800021a6  jmp     short loc_1800021AB
0x1800021a8  xor     r8d, r8d
0x1800021ab  mov     rcx, cs:hProxyDll
0x1800021b2  lea     rdx, aProxyFileList
0x1800021b9  jmp     cs:__imp_NdrDllUnregisterProxy
```
