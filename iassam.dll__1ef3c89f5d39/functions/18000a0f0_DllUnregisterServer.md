# DllUnregisterServer

- ea: `0x18000a0f0`
- end: `0x18000a131`
- name: `DllUnregisterServer`
- size: `65`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008a0c`
- `0x18000a0f0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000a11d`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000a11d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  HRESULT result; // eax
  int v3; // edx
  ATL::CComModule *v4; // rcx
  const struct _GUID *v5; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  result = NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
    return ATL::CComModule::UnregisterServer(v4, v3, v5);
  return result;
}

```

## disassembly

```asm
0x18000a0f0  sub     rsp, 28h
0x18000a0f4  mov     rax, cs:aProxyFileList
0x18000a0fb  mov     rcx, [rax+8]
0x18000a0ff  mov     rax, [rcx]
0x18000a102  test    rax, rax
0x18000a105  jz      short loc_18000A10C
0x18000a107  mov     r8, [rax]
0x18000a10a  jmp     short loc_18000A10F
0x18000a10c  xor     r8d, r8d; pclsid
0x18000a10f  mov     rcx, cs:hProxyDll; hDll
0x18000a116  lea     rdx, aProxyFileList; pProxyFileList
0x18000a11d  call    cs:__imp_NdrDllUnregisterProxy
0x18000a123  test    eax, eax
0x18000a125  js      short loc_18000A12C
0x18000a127  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x18000a12c  add     rsp, 28h
0x18000a130  retn
```
