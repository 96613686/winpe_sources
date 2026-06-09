# DllUnregisterServer

- ea: `0x180017ae0`
- end: `0x180017b10`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180017ae0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180017b09`

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
0x180017ae0  mov     rax, cs:aProxyFileList
0x180017ae7  mov     rcx, [rax+8]
0x180017aeb  mov     rax, [rcx]
0x180017aee  test    rax, rax
0x180017af1  jz      short loc_180017AF8
0x180017af3  mov     r8, [rax]
0x180017af6  jmp     short loc_180017AFB
0x180017af8  xor     r8d, r8d
0x180017afb  mov     rcx, cs:hProxyDll
0x180017b02  lea     rdx, aProxyFileList
0x180017b09  jmp     cs:__imp_NdrDllUnregisterProxy
```
