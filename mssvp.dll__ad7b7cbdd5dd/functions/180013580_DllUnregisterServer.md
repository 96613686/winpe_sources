# DllUnregisterServer

- ea: `0x180013580`
- end: `0x1800135bd`
- name: `DllUnregisterServer`
- size: `61`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011f44`
- `0x180013580`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800135b6`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // edx
  ATL::CComModule *v1; // rcx
  const struct _GUID *v2; // r8
  PCInterfaceStubVtblList v3; // rax
  const CLSID *piid; // r8

  ATL::CComModule::UnregisterServer(v1, v0, v2);
  v3 = *aProxyFileList->pStubVtblList;
  if ( v3 )
    piid = v3->header.piid;
  else
    piid = 0;
  return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180013580  sub     rsp, 28h
0x180013584  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x180013589  mov     rax, cs:aProxyFileList
0x180013590  mov     rcx, [rax+8]
0x180013594  mov     rax, [rcx]
0x180013597  test    rax, rax
0x18001359a  jz      short loc_1800135A1
0x18001359c  mov     r8, [rax]
0x18001359f  jmp     short loc_1800135A4
0x1800135a1  xor     r8d, r8d
0x1800135a4  mov     rcx, cs:hProxyDll
0x1800135ab  lea     rdx, aProxyFileList
0x1800135b2  add     rsp, 28h
0x1800135b6  jmp     cs:__imp_NdrDllUnregisterProxy
```
