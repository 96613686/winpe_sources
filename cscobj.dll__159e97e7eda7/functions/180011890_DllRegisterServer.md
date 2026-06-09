# DllRegisterServer

- ea: `0x180011890`
- end: `0x1800118c5`
- name: `DllRegisterServer`
- size: `53`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011890`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800118b8`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800118b8`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const CLSID *v0; // r8

  v0 = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( v0 )
    v0 = *(const CLSID **)&v0->Data1;
  NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v0);
  return 0;
}

```

## disassembly

```asm
0x180011890  sub     rsp, 28h
0x180011894  mov     rax, cs:aProxyFileList
0x18001189b  mov     rcx, [rax+8]
0x18001189f  mov     r8, [rcx]
0x1800118a2  test    r8, r8
0x1800118a5  jz      short loc_1800118AA
0x1800118a7  mov     r8, [r8]; pclsid
0x1800118aa  mov     rcx, cs:hProxyDll; hDll
0x1800118b1  lea     rdx, aProxyFileList; pProxyFileList
0x1800118b8  call    cs:__imp_NdrDllRegisterProxy
0x1800118be  xor     eax, eax
0x1800118c0  add     rsp, 28h
0x1800118c4  retn
```
