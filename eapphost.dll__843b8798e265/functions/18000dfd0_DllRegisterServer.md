# DllRegisterServer

- ea: `0x18000dfd0`
- end: `0x18000e018`
- name: `DllRegisterServer`
- size: `72`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000dfd0`
- `0x18000f804`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000dffd`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000dffd`

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
0x18000dfd0  sub     rsp, 28h
0x18000dfd4  mov     rax, cs:aProxyFileList
0x18000dfdb  mov     rcx, [rax+8]
0x18000dfdf  mov     rax, [rcx]
0x18000dfe2  test    rax, rax
0x18000dfe5  jz      short loc_18000DFEC
0x18000dfe7  mov     r8, [rax]
0x18000dfea  jmp     short loc_18000DFEF
0x18000dfec  xor     r8d, r8d; pclsid
0x18000dfef  mov     rcx, cs:hProxyDll; hDll
0x18000dff6  lea     rdx, aProxyFileList; pProxyFileList
0x18000dffd  call    cs:__imp_NdrDllRegisterProxy
0x18000e004  nop     dword ptr [rax+rax+00h]
0x18000e009  test    eax, eax
0x18000e00b  js      short loc_18000E012
0x18000e00d  call    ?ComOutOfProcRegisterServer@@YAJXZ; ComOutOfProcRegisterServer(void)
0x18000e012  add     rsp, 28h
0x18000e016  retn
```
