# DllRegisterServer

- ea: `0x180004b50`
- end: `0x180004b80`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004b50`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180004b79`

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
0x180004b50  mov     rax, cs:aProxyFileList
0x180004b57  mov     rcx, [rax+8]
0x180004b5b  mov     rax, [rcx]
0x180004b5e  test    rax, rax
0x180004b61  jz      short loc_180004B68
0x180004b63  mov     r8, [rax]
0x180004b66  jmp     short loc_180004B6B
0x180004b68  xor     r8d, r8d
0x180004b6b  mov     rcx, cs:hProxyDll
0x180004b72  lea     rdx, aProxyFileList
0x180004b79  jmp     cs:__imp_NdrDllRegisterProxy
```
