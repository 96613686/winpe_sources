# DllUnregisterServer

- ea: `0x1800118d0`
- end: `0x180011905`
- name: `DllUnregisterServer`
- size: `53`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800118d0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800118f8`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800118f8`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const CLSID *v0; // r8

  v0 = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( v0 )
    v0 = *(const CLSID **)&v0->Data1;
  NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v0);
  return 0;
}

```

## disassembly

```asm
0x1800118d0  sub     rsp, 28h
0x1800118d4  mov     rax, cs:aProxyFileList
0x1800118db  mov     rcx, [rax+8]
0x1800118df  mov     r8, [rcx]
0x1800118e2  test    r8, r8
0x1800118e5  jz      short loc_1800118EA
0x1800118e7  mov     r8, [r8]; pclsid
0x1800118ea  mov     rcx, cs:hProxyDll; hDll
0x1800118f1  lea     rdx, aProxyFileList; pProxyFileList
0x1800118f8  call    cs:__imp_NdrDllUnregisterProxy
0x1800118fe  xor     eax, eax
0x180011900  add     rsp, 28h
0x180011904  retn
```
