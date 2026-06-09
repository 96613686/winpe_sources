# DllRegisterServer

- ea: `0x18000a080`
- end: `0x18000a0dc`
- name: `DllRegisterServer`
- size: `92`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007da4`
- `0x1800095f0`
- `0x18000a080`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000a0d1`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000a0d1`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // edx
  ATL::CComModule *v1; // rcx
  const struct _GUID *v2; // r8
  HRESULT result; // eax
  PCInterfaceStubVtblList v4; // rax
  const CLSID *piid; // r8

  result = ATL::CComModule::RegisterServer(v1, v0, v2);
  if ( result >= 0 )
  {
    result = ATL::CComModule::UpdateRegistryFromResourceS((ATL::CComModule *)&_Module, 2u, 1, 0);
    if ( result >= 0 )
    {
      v4 = *aProxyFileList->pStubVtblList;
      if ( v4 )
        piid = v4->header.piid;
      else
        piid = 0;
      return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a080  sub     rsp, 28h
0x18000a084  call    ?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::RegisterServer(int,_GUID const *)
0x18000a089  test    eax, eax
0x18000a08b  js      short loc_18000A0D7
0x18000a08d  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000a090  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000a097  lea     edx, [r9+2]; unsigned int
0x18000a09b  lea     r8d, [r9+1]; int
0x18000a09f  call    ?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000a0a4  test    eax, eax
0x18000a0a6  js      short loc_18000A0D7
0x18000a0a8  mov     rax, cs:aProxyFileList
0x18000a0af  mov     rcx, [rax+8]
0x18000a0b3  mov     rax, [rcx]
0x18000a0b6  test    rax, rax
0x18000a0b9  jz      short loc_18000A0C0
0x18000a0bb  mov     r8, [rax]
0x18000a0be  jmp     short loc_18000A0C3
0x18000a0c0  xor     r8d, r8d; pclsid
0x18000a0c3  mov     rcx, cs:hProxyDll; hDll
0x18000a0ca  lea     rdx, aProxyFileList; pProxyFileList
0x18000a0d1  call    cs:__imp_NdrDllRegisterProxy
0x18000a0d7  add     rsp, 28h
0x18000a0db  retn
```
