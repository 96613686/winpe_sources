# DllRegisterServer

- ea: `0x180017aa0`
- end: `0x180017ad0`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180017aa0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180017ac9`

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
0x180017aa0  mov     rax, cs:aProxyFileList
0x180017aa7  mov     rcx, [rax+8]
0x180017aab  mov     rax, [rcx]
0x180017aae  test    rax, rax
0x180017ab1  jz      short loc_180017AB8
0x180017ab3  mov     r8, [rax]
0x180017ab6  jmp     short loc_180017ABB
0x180017ab8  xor     r8d, r8d
0x180017abb  mov     rcx, cs:hProxyDll
0x180017ac2  lea     rdx, aProxyFileList
0x180017ac9  jmp     cs:__imp_NdrDllRegisterProxy
```
