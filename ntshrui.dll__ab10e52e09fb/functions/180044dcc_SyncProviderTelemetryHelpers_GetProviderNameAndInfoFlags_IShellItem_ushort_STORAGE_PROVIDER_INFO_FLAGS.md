# SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(IShellItem *,ushort * *,STORAGE_PROVIDER_INFO_FLAGS *)

- ea: `0x180044dcc`
- end: `0x18004512d`
- name: `?GetProviderNameAndInfoFlags@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAGPEAW4STORAGE_PROVIDER_INFO_FLAGS@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **, enum STORAGE_PROVIDER_INFO_FLAGS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049dcc`

## callees

- `0x180008900`
- `0x180015ad0`
- `0x1800161bc`
- `0x180019670`
- `0x18001d18c`
- `0x1800214cc`
- `0x180021660`
- `0x1800222cc`
- `0x18002cdd0`
- `0x180044dcc`
- `0x180045e80`
- `0x1800513b8`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180044f0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180044f0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004508d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004509d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004508d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004509d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450b3`

## string_xrefs

- `0x180044e7a`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180044fef`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180045073`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x1800450f4`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
        struct IShellItem *a1,
        unsigned __int16 **a2,
        enum STORAGE_PROVIDER_INFO_FLAGS *a3)
{
  int StorageProviderInfo; // ebx
  struct IStorageProviderInfo *v8; // rdi
  int (__fastcall *v9)(struct IStorageProviderInfo *, __int64); // rbx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rbx
  _WORD *v15; // rdi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64); // rbx
  __int64 v18; // rax
  int v19; // eax
  void *v20; // rcx
  const wchar_t *v21; // rdx
  int v22; // eax
  int v23; // edi
  int v24; // eax
  __int64 v25; // rdx
  LPVOID v26; // [rsp+20h] [rbp-40h] BYREF
  void *v27; // [rsp+28h] [rbp-38h] BYREF
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v29; // [rsp+38h] [rbp-28h] BYREF
  PROPERTYKEY v30; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF
  struct IStorageProviderInfo *v33; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+58h] BYREF

  *a2 = 0;
  *(_DWORD *)a3 = 0;
  if ( !Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered((Windows::Internal::SyncRootHelpers *)a1) )
    return 2147943568LL;
  v33 = 0;
  StorageProviderInfo = SyncProviderTelemetryHelpers::GetStorageProviderInfo(a1, &v33);
  if ( StorageProviderInfo >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
    {
      pv = 0;
      v8 = v33;
      v9 = *(int (__fastcall **)(struct IStorageProviderInfo *, __int64))(*(_QWORD *)v33 + 40LL);
      v10 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
      if ( v9(v8, v10) < 0 )
      {
        v34 = 0;
        v11 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v34, a1);
        StorageProviderInfo = v11;
        if ( v11 < 0 )
        {
          v12 = 297;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
            (const char *)(unsigned int)v11,
            (int)v26);
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
LABEL_9:
          if ( pv )
            CoTaskMemFree(pv);
          goto LABEL_44;
        }
        v13 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
        v30 = PKEY_StorageProviderId;
        v11 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v34, &v30, v13);
        StorageProviderInfo = v11;
        if ( v11 < 0 )
        {
          v12 = 298;
          goto LABEL_8;
        }
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
      }
      v14 = 0;
      v27 = 0;
      if ( pv )
      {
        if ( (unsigned int)_o__wcsicmp(pv, L"OneDrive") )
        {
          if ( pv )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v27,
              &pv);
            v14 = v27;
          }
        }
        else
        {
          v15 = 0;
          v29 = 0;
          v28 = 0;
          if ( (**(int (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v33)(
                 v33,
                 &GUID_4905f136_1f36_4b43_bbcb_fb93964639cd,
                 &v28) < 0 )
            goto LABEL_24;
          v26 = 0;
          v16 = v28;
          v17 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 40LL);
          v18 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v26);
          v19 = v17(v16, v18);
          v20 = v26;
          if ( v19 >= 0 && v26 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v29,
              &v26);
            v15 = v29;
            v20 = v26;
          }
          if ( v20 )
            CoTaskMemFree(v20);
          if ( !v15 || (v21 = L"OneDrive Business", !*v15) )
LABEL_24:
            v21 = L"OneDrive Consumer";
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v29,
            v21,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v27,
            &v29);
          if ( v29 )
            CoTaskMemFree(v29);
          v14 = v27;
          if ( !v27 )
          {
            StorageProviderInfo = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x147,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
              (const char *)0x8007000ELL,
              (int)v26);
            wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v28);
            if ( v15 )
              CoTaskMemFree(v15);
            goto LABEL_9;
          }
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v28);
          if ( v15 )
            CoTaskMemFree(v15);
        }
      }
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, enum STORAGE_PROVIDER_INFO_FLAGS *))(*(_QWORD *)v33 + 168LL))(
              v33,
              a3);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v22,
          (int)v26);
        if ( v14 )
          CoTaskMemFree(v14);
        if ( pv )
          CoTaskMemFree(pv);
        StorageProviderInfo = v23;
        goto LABEL_44;
      }
      *a2 = (unsigned __int16 *)v14;
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_43;
    }
    v24 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, unsigned __int16 **))(*(_QWORD *)v33 + 40LL))(
            v33,
            a2);
    StorageProviderInfo = v24;
    if ( v24 >= 0 )
    {
      v24 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, enum STORAGE_PROVIDER_INFO_FLAGS *))(*(_QWORD *)v33 + 168LL))(
              v33,
              a3);
      StorageProviderInfo = v24;
      if ( v24 >= 0 )
      {
LABEL_43:
        StorageProviderInfo = 0;
        goto LABEL_44;
      }
      v25 = 343;
    }
    else
    {
      v25 = 341;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)v24,
      (int)v26);
  }
LABEL_44:
  wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v33);
  return (unsigned int)StorageProviderInfo;
}

```

## disassembly

```asm
0x180044dcc  push    rbp
0x180044dce  push    rbx
0x180044dcf  push    rsi
0x180044dd0  push    rdi
0x180044dd1  push    r12
0x180044dd3  push    r14
0x180044dd5  push    r15
0x180044dd7  mov     rbp, rsp
0x180044dda  sub     rsp, 60h
0x180044dde  mov     r15, r8
0x180044de1  mov     r14, rdx
0x180044de4  mov     rsi, rcx
0x180044de7  xor     r12d, r12d
0x180044dea  mov     [rdx], r12
0x180044ded  mov     [r8], r12d
0x180044df0  call    ?AreAnyStorageProvidersRegistered@SyncRootHelpers@Internal@Windows@@YA_NXZ; Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(void)
0x180044df5  test    al, al
0x180044df7  jnz     short loc_180044E03
0x180044df9  mov     eax, 80070490h
0x180044dfe  jmp     loc_1800450C7
0x180044e03  mov     [rbp+arg_10], r12
0x180044e07  lea     rdx, [rbp+arg_10]; struct IStorageProviderInfo **
0x180044e0b  mov     rcx, rsi; struct IShellItem *
0x180044e0e  call    ?GetStorageProviderInfo@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAUIStorageProviderInfo@@@Z; SyncProviderTelemetryHelpers::GetStorageProviderInfo(IShellItem *,IStorageProviderInfo * *)
0x180044e13  mov     ebx, eax
0x180044e15  test    eax, eax
0x180044e17  js      loc_1800450BC
0x180044e1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56314744@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744> `wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl(void)'::`2'::impl
0x180044e24  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(wil::ReportingKind)
0x180044e29  test    al, al
0x180044e2b  jz      loc_1800450D6
0x180044e31  mov     [rbp+pv], r12
0x180044e35  mov     rdi, [rbp+arg_10]
0x180044e39  mov     rax, [rdi]
0x180044e3c  mov     rbx, [rax+28h]
0x180044e40  lea     rcx, [rbp+pv]
0x180044e44  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180044e49  mov     rdx, rax
0x180044e4c  mov     rcx, rdi
0x180044e4f  mov     rax, rbx
0x180044e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e57  test    eax, eax
0x180044e59  jns     loc_180044EF3
0x180044e5f  mov     [rbp+arg_18], r12
0x180044e63  mov     rdx, rsi
0x180044e66  lea     rcx, [rbp+arg_18]
0x180044e6a  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180044e6f  mov     ebx, eax
0x180044e71  test    eax, eax
0x180044e73  jns     short loc_180044EB0
0x180044e75  mov     edx, 129h; void *
0x180044e7a  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180044e81  mov     r9d, eax; char *
0x180044e84  mov     rcx, [rbp+38h]; this
0x180044e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e8d  nop
0x180044e8e  lea     rcx, [rbp+arg_18]
0x180044e92  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044e97  nop
0x180044e98  mov     rcx, [rbp+pv]; pv
0x180044e9c  test    rcx, rcx
0x180044e9f  jz      loc_1800450BC
0x180044ea5  call    cs:__imp_CoTaskMemFree
0x180044eab  jmp     loc_1800450BC
0x180044eb0  lea     rcx, [rbp+pv]
0x180044eb4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180044eb9  movups  xmm0, xmmword ptr cs:PKEY_StorageProviderId.fmtid.Data1
0x180044ec0  movaps  [rbp+var_20], xmm0
0x180044ec4  mov     ecx, cs:PKEY_StorageProviderId.pid
0x180044eca  mov     [rbp+var_10], ecx
0x180044ecd  mov     r8, rax
0x180044ed0  lea     rdx, [rbp+var_20]
0x180044ed4  lea     rcx, [rbp+arg_18]
0x180044ed8  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180044edd  mov     ebx, eax
0x180044edf  test    eax, eax
0x180044ee1  jns     short loc_180044EEA
0x180044ee3  mov     edx, 12Ah
0x180044ee8  jmp     short loc_180044E7A
0x180044eea  lea     rcx, [rbp+arg_18]
0x180044eee  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044ef3  mov     rbx, r12
0x180044ef6  mov     [rbp+var_38], rbx
0x180044efa  mov     rcx, [rbp+pv]
0x180044efe  test    rcx, rcx
0x180044f01  jz      loc_180045050
0x180044f07  lea     rdx, aOnedrive_1; "OneDrive"
0x180044f0e  call    cs:__imp__o__wcsicmp
0x180044f14  test    eax, eax
0x180044f16  jnz     loc_180045039
0x180044f1c  mov     rdi, r12
0x180044f1f  mov     [rbp+var_28], r12
0x180044f23  mov     [rbp+var_30], r12
0x180044f27  mov     rcx, [rbp+arg_10]
0x180044f2b  mov     rax, [rcx]
0x180044f2e  lea     r8, [rbp+var_30]
0x180044f32  lea     rdx, _GUID_4905f136_1f36_4b43_bbcb_fb93964639cd
0x180044f39  mov     rax, [rax]
0x180044f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f41  test    eax, eax
0x180044f43  js      short loc_180044FAA
0x180044f45  mov     [rbp+var_40], r12
0x180044f49  mov     rsi, [rbp+var_30]
0x180044f4d  mov     rax, [rsi]
0x180044f50  mov     rbx, [rax+28h]
0x180044f54  lea     rcx, [rbp+var_40]
0x180044f58  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180044f5d  mov     rdx, rax
0x180044f60  mov     rcx, rsi
0x180044f63  mov     rax, rbx
0x180044f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f6b  mov     rcx, [rbp+var_40]
0x180044f6f  test    eax, eax
0x180044f71  js      short loc_180044F8D
0x180044f73  test    rcx, rcx
0x180044f76  jz      short loc_180044F8D
0x180044f78  lea     rdx, [rbp+var_40]
0x180044f7c  lea     rcx, [rbp+var_28]
0x180044f80  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180044f85  mov     rdi, [rbp+var_28]
0x180044f89  mov     rcx, [rbp+var_40]; pv
0x180044f8d  test    rcx, rcx
0x180044f90  jz      short loc_180044F98
0x180044f92  call    cs:__imp_CoTaskMemFree
0x180044f98  test    rdi, rdi
0x180044f9b  jz      short loc_180044FAA
0x180044f9d  cmp     [rdi], r12w
0x180044fa1  lea     rdx, aOnedriveBusine; "OneDrive Business"
0x180044fa8  jnz     short loc_180044FB1
0x180044faa  lea     rdx, aOnedriveConsum; "OneDrive Consumer"
0x180044fb1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044fb5  lea     rcx, [rbp+var_28]
0x180044fb9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180044fbe  lea     rdx, [rbp+var_28]
0x180044fc2  lea     rcx, [rbp+var_38]
0x180044fc6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180044fcb  mov     rcx, [rbp+var_28]; pv
0x180044fcf  test    rcx, rcx
0x180044fd2  jz      short loc_180044FDA
0x180044fd4  call    cs:__imp_CoTaskMemFree
0x180044fda  mov     rbx, [rbp+var_38]
0x180044fde  test    rbx, rbx
0x180044fe1  jnz     short loc_18004501F
0x180044fe3  mov     rcx, [rbp+38h]; this
0x180044fe7  mov     ebx, 8007000Eh
0x180044fec  mov     r9d, ebx; char *
0x180044fef  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180044ff6  mov     edx, 147h; void *
0x180044ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045000  nop
0x180045001  lea     rcx, [rbp+var_30]
0x180045005  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004500a  nop
0x18004500b  test    rdi, rdi
0x18004500e  jz      short loc_18004501A
0x180045010  mov     rcx, rdi; pv
0x180045013  call    cs:__imp_CoTaskMemFree
0x180045019  nop
0x18004501a  jmp     loc_180044E98
0x18004501f  lea     rcx, [rbp+var_30]
0x180045023  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180045028  nop
0x180045029  test    rdi, rdi
0x18004502c  jz      short loc_180045050
0x18004502e  mov     rcx, rdi; pv
0x180045031  call    cs:__imp_CoTaskMemFree
0x180045037  jmp     short loc_180045050
0x180045039  cmp     [rbp+pv], r12
0x18004503d  jz      short loc_180045050
0x18004503f  lea     rdx, [rbp+pv]
0x180045043  lea     rcx, [rbp+var_38]
0x180045047  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004504c  mov     rbx, [rbp+var_38]
0x180045050  mov     rcx, [rbp+arg_10]
0x180045054  mov     rax, [rcx]
0x180045057  mov     rdx, r15
0x18004505a  mov     rax, [rax+0A8h]
0x180045061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045066  mov     edi, eax
0x180045068  test    eax, eax
0x18004506a  jns     short loc_1800450A7
0x18004506c  mov     rcx, [rbp+38h]; this
0x180045070  mov     r9d, eax; char *
0x180045073  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18004507a  mov     edx, 14Eh; void *
0x18004507f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045084  nop
0x180045085  test    rbx, rbx
0x180045088  jz      short loc_180045094
0x18004508a  mov     rcx, rbx; pv
0x18004508d  call    cs:__imp_CoTaskMemFree
0x180045093  nop
0x180045094  mov     rcx, [rbp+pv]; pv
0x180045098  test    rcx, rcx
0x18004509b  jz      short loc_1800450A3
0x18004509d  call    cs:__imp_CoTaskMemFree
0x1800450a3  mov     ebx, edi
0x1800450a5  jmp     short loc_1800450BC
0x1800450a7  mov     [r14], rbx
0x1800450aa  mov     rcx, [rbp+pv]; pv
0x1800450ae  test    rcx, rcx
0x1800450b1  jz      short loc_1800450B9
0x1800450b3  call    cs:__imp_CoTaskMemFree
0x1800450b9  mov     ebx, r12d
0x1800450bc  lea     rcx, [rbp+arg_10]
0x1800450c0  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x1800450c5  mov     eax, ebx
0x1800450c7  add     rsp, 60h
0x1800450cb  pop     r15
0x1800450cd  pop     r14
0x1800450cf  pop     r12
0x1800450d1  pop     rdi
0x1800450d2  pop     rsi
0x1800450d3  pop     rbx
0x1800450d4  pop     rbp
0x1800450d5  retn
0x1800450d6  mov     rcx, [rbp+arg_10]
0x1800450da  mov     rax, [rcx]
0x1800450dd  mov     rdx, r14
0x1800450e0  mov     rax, [rax+28h]
0x1800450e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450e9  mov     ebx, eax
0x1800450eb  test    eax, eax
0x1800450ed  jns     short loc_180045109
0x1800450ef  mov     edx, 155h; void *
0x1800450f4  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800450fb  mov     r9d, eax; char *
0x1800450fe  mov     rcx, [rbp+38h]; this
0x180045102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045107  jmp     short loc_1800450BC
0x180045109  mov     rcx, [rbp+arg_10]
0x18004510d  mov     rax, [rcx]
0x180045110  mov     rdx, r15
0x180045113  mov     rax, [rax+0A8h]
0x18004511a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004511f  mov     ebx, eax
0x180045121  test    eax, eax
0x180045123  jns     short loc_1800450B9
0x180045125  mov     edx, 157h
0x18004512a  jmp     short loc_1800450F4
```
