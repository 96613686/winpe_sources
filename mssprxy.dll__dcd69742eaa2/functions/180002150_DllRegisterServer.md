# DllRegisterServer

- ea: `0x180002150`
- end: `0x180002180`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002150`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180002179`

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
0x180002150  mov     rax, cs:aProxyFileList
0x180002157  mov     rcx, [rax+8]
0x18000215b  mov     rax, [rcx]
0x18000215e  test    rax, rax
0x180002161  jz      short loc_180002168
0x180002163  mov     r8, [rax]
0x180002166  jmp     short loc_18000216B
0x180002168  xor     r8d, r8d
0x18000216b  mov     rcx, cs:hProxyDll
0x180002172  lea     rdx, aProxyFileList
0x180002179  jmp     cs:__imp_NdrDllRegisterProxy
```
