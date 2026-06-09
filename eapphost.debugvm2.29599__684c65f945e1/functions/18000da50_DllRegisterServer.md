# DllRegisterServer

- ea: `0x18000da50`
- end: `0x18000da91`
- name: `DllRegisterServer`
- size: `65`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000da50`
- `0x18000f200`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000da7d`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000da7d`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  HRESULT result; // eax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
    return ComOutOfProcRegisterServer();
  return result;
}

```

## disassembly

```asm
0x18000da50  sub     rsp, 28h
0x18000da54  mov     rax, cs:aProxyFileList
0x18000da5b  mov     rcx, [rax+8]
0x18000da5f  mov     rax, [rcx]
0x18000da62  test    rax, rax
0x18000da65  jz      short loc_18000DA6C
0x18000da67  mov     r8, [rax]
0x18000da6a  jmp     short loc_18000DA6F
0x18000da6c  xor     r8d, r8d; pclsid
0x18000da6f  mov     rcx, cs:hProxyDll; hDll
0x18000da76  lea     rdx, aProxyFileList; pProxyFileList
0x18000da7d  call    cs:__imp_NdrDllRegisterProxy
0x18000da83  test    eax, eax
0x18000da85  js      short loc_18000DA8C
0x18000da87  call    ?ComOutOfProcRegisterServer@@YAJXZ; ComOutOfProcRegisterServer(void)
0x18000da8c  add     rsp, 28h
0x18000da90  retn
```
