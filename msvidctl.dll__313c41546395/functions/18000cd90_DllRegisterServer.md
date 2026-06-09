# DllRegisterServer

- ea: `0x18000cd90`
- end: `0x18000ce95`
- name: `DllRegisterServer`
- size: `261`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180007590`
- `0x18000764c`
- `0x18000c4f8`
- `0x18000cd90`
- `0x180042bb0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000ce12`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000ce61`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000ce12`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000ce61`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  struct ATL::_ATL_MODULE *v0; // rcx
  HRESULT v1; // ebx
  int v2; // edx
  struct ATL::_ATL_MODULE *v3; // rcx
  const struct _GUID *v4; // r8
  int v5; // eax
  HRESULT v6; // eax
  bool v7; // zf
  int v8; // eax
  HRESULT v9; // eax

  v1 = ATL::AtlModuleRegisterTypeLib(v0, L"\\2");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl'::`2'::impl) )
  {
    if ( v1 < 0 && v1 != -2147319780 && v1 != -2147024891 && v1 != -2147352567 )
      return v1;
    v5 = ATL::AtlModuleRegisterServer(v3, v2, v4);
    v1 = v5;
    if ( v5 < 0 && v5 != -2147319780 && v5 != -2147024891 && v5 != -2147352567 )
      return v1;
    v6 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &IID_IDVBTLocator);
    v1 = v6;
    if ( v6 >= 0 || v6 == -2147319780 || v6 == -2147024891 )
      return BDATuningModel::RegisterTuningSpaces(lpSource);
    v7 = v6 == -2147352567;
  }
  else
  {
    if ( v1 < 0 && v1 != -2147319780 && v1 != -2147024891 )
      return v1;
    v8 = ATL::AtlModuleRegisterServer(v3, v2, v4);
    v1 = v8;
    if ( v8 < 0 && v8 != -2147319780 && v8 != -2147024891 )
      return v1;
    v9 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &IID_IDVBTLocator);
    v1 = v9;
    if ( v9 >= 0 || v9 == -2147319780 )
      return BDATuningModel::RegisterTuningSpaces(lpSource);
    v7 = v9 == -2147024891;
  }
  if ( v7 )
    return BDATuningModel::RegisterTuningSpaces(lpSource);
  return v1;
}

```

## disassembly

```asm
0x18000cd90  mov     [rsp+arg_0], rbx
0x18000cd95  mov     [rsp+arg_8], rsi
0x18000cd9a  push    rdi
0x18000cd9b  sub     rsp, 20h
0x18000cd9f  lea     rdx, a2; "\\2"
0x18000cda6  call    ?AtlModuleRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z; ATL::AtlModuleRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)
0x18000cdab  mov     ebx, eax
0x18000cdad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl(void)'::`2'::impl
0x18000cdb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(void)
0x18000cdb9  mov     esi, 8002801Ch
0x18000cdbe  mov     edi, 80070005h
0x18000cdc3  test    al, al
0x18000cdc5  jz      short loc_18000CE2D
0x18000cdc7  test    ebx, ebx
0x18000cdc9  jns     short loc_18000CDDF
0x18000cdcb  cmp     ebx, esi
0x18000cdcd  jz      short loc_18000CDDF
0x18000cdcf  cmp     ebx, edi
0x18000cdd1  jz      short loc_18000CDDF
0x18000cdd3  cmp     ebx, 80020009h
0x18000cdd9  jnz     loc_18000CE83
0x18000cddf  call    ?AtlModuleRegisterServer@ATL@@YAJPEAU_ATL_MODULE@1@HPEBU_GUID@@@Z; ATL::AtlModuleRegisterServer(ATL::_ATL_MODULE *,int,_GUID const *)
0x18000cde4  mov     ebx, eax
0x18000cde6  test    eax, eax
0x18000cde8  jns     short loc_18000CDFD
0x18000cdea  cmp     eax, esi
0x18000cdec  jz      short loc_18000CDFD
0x18000cdee  cmp     eax, edi
0x18000cdf0  jz      short loc_18000CDFD
0x18000cdf2  cmp     eax, 80020009h
0x18000cdf7  jnz     loc_18000CE83
0x18000cdfd  mov     rcx, cs:hProxyDll; hDll
0x18000ce04  lea     r8, IID_IDVBTLocator; pclsid
0x18000ce0b  lea     rdx, aProxyFileList; pProxyFileList
0x18000ce12  call    cs:__imp_NdrDllRegisterProxy
0x18000ce18  mov     ebx, eax
0x18000ce1a  test    eax, eax
0x18000ce1c  jns     short loc_18000CE75
0x18000ce1e  cmp     eax, esi
0x18000ce20  jz      short loc_18000CE75
0x18000ce22  cmp     eax, edi
0x18000ce24  jz      short loc_18000CE75
0x18000ce26  cmp     eax, 80020009h
0x18000ce2b  jmp     short loc_18000CE73
0x18000ce2d  test    ebx, ebx
0x18000ce2f  jns     short loc_18000CE39
0x18000ce31  cmp     ebx, esi
0x18000ce33  jz      short loc_18000CE39
0x18000ce35  cmp     ebx, edi
0x18000ce37  jnz     short loc_18000CE83
0x18000ce39  call    ?AtlModuleRegisterServer@ATL@@YAJPEAU_ATL_MODULE@1@HPEBU_GUID@@@Z; ATL::AtlModuleRegisterServer(ATL::_ATL_MODULE *,int,_GUID const *)
0x18000ce3e  mov     ebx, eax
0x18000ce40  test    eax, eax
0x18000ce42  jns     short loc_18000CE4C
0x18000ce44  cmp     eax, esi
0x18000ce46  jz      short loc_18000CE4C
0x18000ce48  cmp     eax, edi
0x18000ce4a  jnz     short loc_18000CE83
0x18000ce4c  mov     rcx, cs:hProxyDll; hDll
0x18000ce53  lea     r8, IID_IDVBTLocator; pclsid
0x18000ce5a  lea     rdx, aProxyFileList; pProxyFileList
0x18000ce61  call    cs:__imp_NdrDllRegisterProxy
0x18000ce67  mov     ebx, eax
0x18000ce69  test    eax, eax
0x18000ce6b  jns     short loc_18000CE75
0x18000ce6d  cmp     eax, esi
0x18000ce6f  jz      short loc_18000CE75
0x18000ce71  cmp     eax, edi
0x18000ce73  jnz     short loc_18000CE83
0x18000ce75  mov     rcx, cs:lpSource; HINSTANCE
0x18000ce7c  call    ?RegisterTuningSpaces@BDATuningModel@@YAJPEAUHINSTANCE__@@@Z; BDATuningModel::RegisterTuningSpaces(HINSTANCE__ *)
0x18000ce81  mov     ebx, eax
0x18000ce83  mov     rsi, [rsp+28h+arg_8]
0x18000ce88  mov     eax, ebx
0x18000ce8a  mov     rbx, [rsp+28h+arg_0]
0x18000ce8f  add     rsp, 20h
0x18000ce93  pop     rdi
0x18000ce94  retn
```
