# DllRegisterServer

- ea: `0x180001ec0`
- end: `0x180001ef0`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ec0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180001ee9`

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
0x180001ec0  mov     rax, cs:aProxyFileList
0x180001ec7  mov     rcx, [rax+8]
0x180001ecb  mov     rax, [rcx]
0x180001ece  test    rax, rax
0x180001ed1  jz      short loc_180001ED8
0x180001ed3  mov     r8, [rax]
0x180001ed6  jmp     short loc_180001EDB
0x180001ed8  xor     r8d, r8d
0x180001edb  mov     rcx, cs:hProxyDll
0x180001ee2  lea     rdx, aProxyFileList
0x180001ee9  jmp     cs:__imp_NdrDllRegisterProxy
```
