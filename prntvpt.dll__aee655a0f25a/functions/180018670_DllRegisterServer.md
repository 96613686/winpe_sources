# DllRegisterServer

- ea: `0x180018670`
- end: `0x1800186d6`
- name: `DllRegisterServer`
- size: `102`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800184b0`
- `0x180018544`
- `0x180018588`
- `0x180018670`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800186cb`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800186cb`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  PCInterfaceStubVtblList v1; // rax
  const CLSID *piid; // r8

  result = CMyDllModule::UpdateRegistryAppId(1);
  if ( result >= 0 )
  {
    result = ATL::CAtlModuleT<CMyDllModuleAC>::RegisterServer();
    if ( result >= 0 )
    {
      result = CMyDllModuleAC::UpdateRegistryAppId(1);
      if ( result >= 0 )
      {
        result = ATL::CAtlModuleT<CMyDllModuleAC>::RegisterServer();
        if ( result >= 0 )
        {
          v1 = *aProxyFileList->pStubVtblList;
          if ( v1 )
            piid = v1->header.piid;
          else
            piid = 0;
          return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018670  sub     rsp, 28h
0x180018674  mov     ecx, 1; int
0x180018679  call    ?UpdateRegistryAppId@CMyDllModule@@SAJH@Z; CMyDllModule::UpdateRegistryAppId(int)
0x18001867e  test    eax, eax
0x180018680  js      short loc_1800186D1
0x180018682  call    ?RegisterServer@?$CAtlModuleT@VCMyDllModuleAC@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CMyDllModuleAC>::RegisterServer(int,_GUID const *)
0x180018687  test    eax, eax
0x180018689  js      short loc_1800186D1
0x18001868b  mov     ecx, 1; int
0x180018690  call    ?UpdateRegistryAppId@CMyDllModuleAC@@SAJH@Z; CMyDllModuleAC::UpdateRegistryAppId(int)
0x180018695  test    eax, eax
0x180018697  js      short loc_1800186D1
0x180018699  call    ?RegisterServer@?$CAtlModuleT@VCMyDllModuleAC@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CMyDllModuleAC>::RegisterServer(int,_GUID const *)
0x18001869e  test    eax, eax
0x1800186a0  js      short loc_1800186D1
0x1800186a2  mov     rax, cs:aProxyFileList
0x1800186a9  mov     rcx, [rax+8]
0x1800186ad  mov     rax, [rcx]
0x1800186b0  test    rax, rax
0x1800186b3  jz      short loc_1800186BA
0x1800186b5  mov     r8, [rax]
0x1800186b8  jmp     short loc_1800186BD
0x1800186ba  xor     r8d, r8d; pclsid
0x1800186bd  mov     rcx, cs:hProxyDll; hDll
0x1800186c4  lea     rdx, aProxyFileList; pProxyFileList
0x1800186cb  call    cs:__imp_NdrDllRegisterProxy
0x1800186d1  add     rsp, 28h
0x1800186d5  retn
```
