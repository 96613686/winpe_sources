# CModernShareCommand::TryShareRemoteItems(IShellItemArray *,IBindCtx *)

- ea: `0x18004fa00`
- end: `0x18004fcd7`
- name: `?TryShareRemoteItems@CModernShareCommand@@QEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(CModernShareCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f758`

## callees

- `0x180008900`
- `0x18001bfd8`
- `0x18001d18c`
- `0x180020c64`
- `0x180020f6c`
- `0x180020fb8`
- `0x1800214cc`
- `0x1800222cc`
- `0x1800254e0`
- `0x180031020`
- `0x18003a290`
- `0x18003a650`
- `0x18003d22c`
- `0x180044690`
- `0x180048f44`
- `0x18004cf4c`
- `0x18004f1c4`
- `0x18004fa00`
- `0x1800513b8`
- `0x180053120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fb3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fb3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fbee`

## string_xrefs

- `0x18004fa81`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004fb15`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004fb78`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004fc28`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CModernShareCommand::TryShareRemoteItems(
        CModernShareCommand *this,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  __int64 v6; // rdx
  int RemotePropertyStoreFromShellItemArray; // eax
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  _QWORD *v16; // rax
  int MRUIdentifiers; // eax
  __int64 v18; // rdx
  __int64 v20; // [rsp+20h] [rbp-59h] BYREF
  struct IPropertyStore *v21; // [rsp+28h] [rbp-51h] BYREF
  __int64 v22; // [rsp+30h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v24[56]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1h]
  HSTRING string[2]; // [rsp+80h] [rbp+7h] BYREF
  int v27; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v21 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>::start_and_watch_errors(
    &v21,
    v24);
  wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>,wil::err_returncode_policy>(&v21);
  if ( !IsRemoteFileFromShellItemArray(a2, 0) )
  {
    tip2::details::shared_data<0,0,0>::complete_without_lock(v25 + 8);
    v8 = -2147024809;
    goto LABEL_31;
  }
  ShareVerbTelemetry::ShareVerb_InvokeMRUShareWindow();
  v21 = 0;
  RemotePropertyStoreFromShellItemArray = TryGetRemotePropertyStoreFromShellItemArray(a2, v6, &v21);
  v8 = RemotePropertyStoreFromShellItemArray;
  if ( RemotePropertyStoreFromShellItemArray >= 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
    {
      v20 = 0;
      v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[29])v9);
      MRUIdentifiers = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                         *v16,
                         &v20);
      v8 = MRUIdentifiers;
      if ( MRUIdentifiers >= 0 )
      {
        MRUIdentifiers = CModernShareCommand::GetMRUIdentifiers((__int64)this, &v21, &v20);
        v8 = MRUIdentifiers;
        if ( MRUIdentifiers >= 0 )
        {
          MRUIdentifiers = CModernShareCommand::OneDriveInvoke(this, L"launchsharedialog", &v20);
          v8 = MRUIdentifiers;
          if ( MRUIdentifiers >= 0 )
          {
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
LABEL_28:
            tip2::details::shared_data<0,0,0>::complete_without_lock(v25 + 8);
            v8 = 0;
            goto LABEL_29;
          }
          v18 = 1905;
        }
        else
        {
          v18 = 1903;
        }
      }
      else
      {
        v18 = 1902;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)MRUIdentifiers,
        v20);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
      goto LABEL_29;
    }
    pv = 0;
    wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v20, v21);
    v10 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    *(_OWORD *)string = PKEY_StorageProviderFullyQualifiedId;
    v27 = 119;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v20, string, v10) >= 0 )
    {
      v12 = CModernShareCommand::CreateAndInvokeCloudProviderShareHandlerFromId(
              this,
              (const unsigned __int16 *)pv,
              a2,
              a3);
      v8 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x760,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v12,
          v20);
        goto LABEL_8;
      }
      goto LABEL_18;
    }
    v22 = 0;
    v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[29])v11);
    v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v13, &v22);
    v8 = v14;
    if ( v14 >= 0 )
    {
      v14 = CModernShareCommand::GetMRUIdentifiers((__int64)this, &v21, &v22);
      v8 = v14;
      if ( v14 >= 0 )
      {
        v14 = CModernShareCommand::OneDriveInvoke(this, L"launchsharedialog", &v22);
        v8 = v14;
        if ( v14 >= 0 )
        {
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
LABEL_18:
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
          if ( pv )
            CoTaskMemFree(pv);
          goto LABEL_28;
        }
        v15 = 1896;
      }
      else
      {
        v15 = 1894;
      }
    }
    else
    {
      v15 = 1893;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v14,
      v20);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
LABEL_8:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x755,
    (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
    (const char *)(unsigned int)RemotePropertyStoreFromShellItemArray,
    v20);
LABEL_29:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
LABEL_31:
  tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>(v24);
  return v8;
}

```

## disassembly

```asm
0x18004fa00  push    rbp
0x18004fa02  push    rbx
0x18004fa03  push    rsi
0x18004fa04  push    rdi
0x18004fa05  push    r14
0x18004fa07  lea     rbp, [rsp-37h]
0x18004fa0c  sub     rsp, 0B0h
0x18004fa13  mov     rax, cs:__security_cookie
0x18004fa1a  xor     rax, rsp
0x18004fa1d  mov     [rbp+57h+var_30], rax
0x18004fa21  mov     r14, r8
0x18004fa24  mov     rsi, rdx
0x18004fa27  mov     rdi, rcx
0x18004fa2a  mov     [rbp+57h+var_A8], 0
0x18004fa32  lea     rdx, [rbp+57h+var_90]
0x18004fa36  lea     rcx, [rbp+57h+var_A8]
0x18004fa3a  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_FileExplorerContextMenuOneDriveShare@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_FileExplorerContextMenuOneDriveShare@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>::start_and_watch_errors(void)
0x18004fa3f  lea     rcx, [rbp+57h+var_A8]
0x18004fa43  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FileExplorerContextMenuOneDriveShare@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>,wil::err_returncode_policy>(void)
0x18004fa48  nop
0x18004fa49  xor     edx, edx; unsigned int
0x18004fa4b  mov     rcx, rsi; struct IShellItemArray *
0x18004fa4e  call    ?IsRemoteFileFromShellItemArray@@YA_NPEAUIShellItemArray@@K@Z; IsRemoteFileFromShellItemArray(IShellItemArray *,ulong)
0x18004fa53  test    al, al
0x18004fa55  jz      loc_18004FCA0
0x18004fa5b  call    ?ShareVerb_InvokeMRUShareWindow@ShareVerbTelemetry@@SAXXZ; ShareVerbTelemetry::ShareVerb_InvokeMRUShareWindow(void)
0x18004fa60  mov     [rbp+57h+var_A8], 0
0x18004fa68  lea     r8, [rbp+57h+var_A8]
0x18004fa6c  mov     rcx, rsi
0x18004fa6f  call    ?TryGetRemotePropertyStoreFromShellItemArray@@YAJPEAUIShellItemArray@@KAEAV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@Z; TryGetRemotePropertyStoreFromShellItemArray(IShellItemArray *,ulong,Microsoft::WRL::ComPtr<IPropertyStore> &)
0x18004fa74  mov     ebx, eax
0x18004fa76  test    eax, eax
0x18004fa78  jns     short loc_18004FA97
0x18004fa7a  mov     rcx, [rbp+5Fh]; this
0x18004fa7e  mov     r9d, eax; char *
0x18004fa81  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004fa88  mov     edx, 755h; void *
0x18004fa8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fa92  jmp     loc_18004FC95
0x18004fa97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56314744@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744> `wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl(void)'::`2'::impl
0x18004fa9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(wil::ReportingKind)
0x18004faa3  test    al, al
0x18004faa5  jz      loc_18004FBF9
0x18004faab  mov     [rbp+57h+pv], 0
0x18004fab3  mov     rdx, [rbp+57h+var_A8]; struct IPropertyStore *
0x18004fab7  lea     rcx, [rbp+57h+var_B0]; this
0x18004fabb  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x18004fac0  nop
0x18004fac1  lea     rcx, [rbp+57h+pv]
0x18004fac5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004faca  movups  xmm0, cs:PKEY_StorageProviderFullyQualifiedId
0x18004fad1  movaps  xmmword ptr [rbp+57h+string], xmm0
0x18004fad5  mov     edx, cs:dword_180082CC8
0x18004fadb  mov     [rbp+57h+var_40], edx
0x18004fade  mov     r8, rax
0x18004fae1  lea     rdx, [rbp+57h+string]
0x18004fae5  lea     rcx, [rbp+57h+var_B0]
0x18004fae9  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18004faee  test    eax, eax
0x18004faf0  js      short loc_18004FB49
0x18004faf2  mov     r9, r14; struct IBindCtx *
0x18004faf5  mov     r8, rsi; struct IShellItemArray *
0x18004faf8  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18004fafc  mov     rcx, rdi; this
0x18004faff  call    ?CreateAndInvokeCloudProviderShareHandlerFromId@CModernShareCommand@@AEAAJPEBGPEAUIShellItemArray@@PEAUIBindCtx@@@Z; CModernShareCommand::CreateAndInvokeCloudProviderShareHandlerFromId(ushort const *,IShellItemArray *,IBindCtx *)
0x18004fb04  mov     ebx, eax
0x18004fb06  test    eax, eax
0x18004fb08  jns     loc_18004FBD7
0x18004fb0e  mov     rcx, [rbp+5Fh]; this
0x18004fb12  mov     r9d, eax; char *
0x18004fb15  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004fb1c  mov     edx, 760h; void *
0x18004fb21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb26  nop
0x18004fb27  lea     rcx, [rbp+57h+var_B0]
0x18004fb2b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fb30  nop
0x18004fb31  mov     rcx, [rbp+57h+pv]; pv
0x18004fb35  test    rcx, rcx
0x18004fb38  jz      loc_18004FC95
0x18004fb3e  call    cs:__imp_CoTaskMemFree
0x18004fb44  jmp     loc_18004FC95
0x18004fb49  mov     [rbp+57h+var_A0], 0
0x18004fb51  lea     rcx, [rbp+57h+string]; string
0x18004fb55  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x18004fb5a  lea     rdx, [rbp+57h+var_A0]
0x18004fb5e  mov     rcx, [rax]
0x18004fb61  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18004fb66  mov     ebx, eax
0x18004fb68  test    eax, eax
0x18004fb6a  jns     short loc_18004FB90
0x18004fb6c  mov     edx, 765h; void *
0x18004fb71  mov     rcx, [rbp+5Fh]; this
0x18004fb75  mov     r9d, eax; char *
0x18004fb78  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004fb7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb84  nop
0x18004fb85  lea     rcx, [rbp+57h+var_A0]
0x18004fb89  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fb8e  jmp     short loc_18004FB27
0x18004fb90  lea     r8, [rbp+57h+var_A0]
0x18004fb94  lea     rdx, [rbp+57h+var_A8]
0x18004fb98  mov     rcx, rdi
0x18004fb9b  call    ?GetMRUIdentifiers@CModernShareCommand@@QEAAJAEBV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@34@@Z; CModernShareCommand::GetMRUIdentifiers(Microsoft::WRL::ComPtr<IPropertyStore> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18004fba0  mov     ebx, eax
0x18004fba2  test    eax, eax
0x18004fba4  jns     short loc_18004FBAD
0x18004fba6  mov     edx, 766h
0x18004fbab  jmp     short loc_18004FB71
0x18004fbad  lea     r8, [rbp+57h+var_A0]
0x18004fbb1  lea     rdx, aLaunchsharedia; "launchsharedialog"
0x18004fbb8  mov     rcx, rdi
0x18004fbbb  call    ?OneDriveInvoke@CModernShareCommand@@QEAAJPEBGAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; CModernShareCommand::OneDriveInvoke(ushort const *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)
0x18004fbc0  mov     ebx, eax
0x18004fbc2  test    eax, eax
0x18004fbc4  jns     short loc_18004FBCD
0x18004fbc6  mov     edx, 768h
0x18004fbcb  jmp     short loc_18004FB71
0x18004fbcd  lea     rcx, [rbp+57h+var_A0]
0x18004fbd1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fbd6  nop
0x18004fbd7  lea     rcx, [rbp+57h+var_B0]
0x18004fbdb  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fbe0  nop
0x18004fbe1  mov     rcx, [rbp+57h+pv]; pv
0x18004fbe5  test    rcx, rcx
0x18004fbe8  jz      loc_18004FC86
0x18004fbee  call    cs:__imp_CoTaskMemFree
0x18004fbf4  jmp     loc_18004FC86
0x18004fbf9  mov     [rbp+57h+var_B0], 0
0x18004fc01  lea     rcx, [rbp+57h+string]; string
0x18004fc05  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x18004fc0a  lea     rdx, [rbp+57h+var_B0]
0x18004fc0e  mov     rcx, [rax]
0x18004fc11  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18004fc16  mov     ebx, eax
0x18004fc18  test    eax, eax
0x18004fc1a  jns     short loc_18004FC40
0x18004fc1c  mov     edx, 76Eh; void *
0x18004fc21  mov     rcx, [rbp+5Fh]; this
0x18004fc25  mov     r9d, eax; char *
0x18004fc28  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004fc2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc34  nop
0x18004fc35  lea     rcx, [rbp+57h+var_B0]
0x18004fc39  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fc3e  jmp     short loc_18004FC95
0x18004fc40  lea     r8, [rbp+57h+var_B0]
0x18004fc44  lea     rdx, [rbp+57h+var_A8]
0x18004fc48  mov     rcx, rdi
0x18004fc4b  call    ?GetMRUIdentifiers@CModernShareCommand@@QEAAJAEBV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@34@@Z; CModernShareCommand::GetMRUIdentifiers(Microsoft::WRL::ComPtr<IPropertyStore> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18004fc50  mov     ebx, eax
0x18004fc52  test    eax, eax
0x18004fc54  jns     short loc_18004FC5D
0x18004fc56  mov     edx, 76Fh
0x18004fc5b  jmp     short loc_18004FC21
0x18004fc5d  lea     r8, [rbp+57h+var_B0]
0x18004fc61  lea     rdx, aLaunchsharedia; "launchsharedialog"
0x18004fc68  mov     rcx, rdi
0x18004fc6b  call    ?OneDriveInvoke@CModernShareCommand@@QEAAJPEBGAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; CModernShareCommand::OneDriveInvoke(ushort const *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)
0x18004fc70  mov     ebx, eax
0x18004fc72  test    eax, eax
0x18004fc74  jns     short loc_18004FC7D
0x18004fc76  mov     edx, 771h
0x18004fc7b  jmp     short loc_18004FC21
0x18004fc7d  lea     rcx, [rbp+57h+var_B0]
0x18004fc81  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fc86  mov     rcx, [rbp+57h+var_58]
0x18004fc8a  add     rcx, 8
0x18004fc8e  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18004fc93  xor     ebx, ebx
0x18004fc95  lea     rcx, [rbp+57h+var_A8]
0x18004fc99  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004fc9e  jmp     short loc_18004FCB2
0x18004fca0  mov     rcx, [rbp+57h+var_58]
0x18004fca4  add     rcx, 8
0x18004fca8  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18004fcad  mov     ebx, 80070057h
0x18004fcb2  lea     rcx, [rbp+57h+var_90]
0x18004fcb6  call    ??1?$test_watcher@V?$merged_data@U_tip_FileExplorerContextMenuOneDriveShare@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerContextMenuOneDriveShare,_tip_FileExplorerContextMenuOneDriveShare>>(void)
0x18004fcbb  mov     eax, ebx
0x18004fcbd  mov     rcx, [rbp+57h+var_30]
0x18004fcc1  xor     rcx, rsp; StackCookie
0x18004fcc4  call    __security_check_cookie
0x18004fcc9  add     rsp, 0B0h
0x18004fcd0  pop     r14
0x18004fcd2  pop     rdi
0x18004fcd3  pop     rsi
0x18004fcd4  pop     rbx
0x18004fcd5  pop     rbp
0x18004fcd6  retn
```
