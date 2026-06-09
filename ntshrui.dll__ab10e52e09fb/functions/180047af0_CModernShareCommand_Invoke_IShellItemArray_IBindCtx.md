# CModernShareCommand::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x180047af0`
- end: `0x1800482d4`
- name: `?Invoke@CModernShareCommand@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `2020`
- prototype: `__int64 __fastcall(CModernShareCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `3`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ec30`
- `0x18002ec40`
- `0x1800482e0`

## callees

- `0x180008900`
- `0x180015f30`
- `0x18001d18c`
- `0x1800214cc`
- `0x1800254e0`
- `0x18002cdd0`
- `0x18002e7b0`
- `0x1800341c4`
- `0x180035248`
- `0x180035f78`
- `0x18003828c`
- `0x18003a124`
- `0x18003ae20`
- `0x18003b1a4`
- `0x18003d2b8`
- `0x18003ee00`
- `0x180045b7c`
- `0x180047af0`
- `0x18004901c`
- `0x180049228`
- `0x18004ce34`
- `0x18004cfd4`
- `0x18004d4a8`
- `0x18004f394`
- `0x18004f758`
- `0x1800516c4`
- `0x180051740`
- `0x180051780`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047f36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047f36`
- `USER32!GetAncestor` at `0x180048146`
- `USER32!GetAncestor` at `0x180048146`

## string_xrefs

- `0x180047b5c`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047c2e`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047caf`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047d26`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047db5`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047e92`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180047fbc`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004819b`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x1800481e5`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180048256`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
__int64 __fastcall CModernShareCommand::Invoke(IUnknown **this, struct IShellItemArray *a2, struct IBindCtx *a3)
{
  __int64 v7; // rdx
  int v8; // eax
  CModernShareCommand *v9; // rcx
  unsigned int v10; // ebx
  CModernShareCommand *v11; // rcx
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v13; // eax
  unsigned int v14; // ebx
  unsigned __int16 **v15; // rax
  int StorageProviderEnterpriseId; // eax
  int WindowsShareSheet; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // r8
  HWND Ancestor; // r12
  IUnknown *v23; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // [rsp+20h] [rbp-1C8h]
  struct IShellItemArray *v32; // [rsp+30h] [rbp-1B8h] BYREF
  int v33; // [rsp+38h] [rbp-1B0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-1A8h] BYREF
  struct IShellItem *v35; // [rsp+48h] [rbp-1A0h] BYREF
  HWND hwnd; // [rsp+50h] [rbp-198h] BYREF
  int v37; // [rsp+58h] [rbp-190h] BYREF
  _QWORD v38[42]; // [rsp+60h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v38);
  v38[0] = &SharingWizardTelemetry::ModernShareInvoke::`vftable';
  SharingWizardTelemetry::ModernShareInvoke::StartActivity((SharingWizardTelemetry::ModernShareInvoke *)v38);
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)0x80070057LL,
      v31);
    SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
    return 2147942487LL;
  }
  v32 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl)
    || (unsigned __int8)winrt::impl::call_factory_cast<bool (*)(winrt::WindowsUdk::System::Profile::IIntegratedServicesGeographicRegionPoliciesStatics const &),winrt::WindowsUdk::System::Profile::IntegratedServicesGeographicRegionPolicies,winrt::WindowsUdk::System::Profile::IIntegratedServicesGeographicRegionPoliciesStatics,_lambda_1fb92ff044e7e9d3adc100b9821092ba_>()
    || (v37 = 0, ((int (__fastcall *)(struct IShellItemArray *, int *))a2->lpVtbl->GetCount)(a2, &v37) < 0)
    || v37 != 1
    || !(unsigned __int8)IsAnyItemCloudPlaceholder(a2) )
  {
LABEL_45:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl) )
    {
      if ( (int)CModernShareCommand::TryInvokeShareForCloudProvider((CModernShareCommand *)this, a2, a3, v32) >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
LABEL_48:
          ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<unsigned short const (&)[6]>(L"cloud");
LABEL_49:
        wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v38, 0);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
        SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
        return 0;
      }
    }
    else if ( (int)CModernShareCommand::TryInvokeShareForCloudProvider((CModernShareCommand *)this, a2, a3, 0) >= 0 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
        goto LABEL_49;
      goto LABEL_48;
    }
    Fire_ExplorerTelemetryFromSiteWithShellItemArray(this[5], 40995, v21, a2);
    hwnd = 0;
    GetWindowFromSite(this[5], &hwnd);
    Ancestor = GetAncestor(hwnd, 2u);
    if ( !this[21] )
    {
      v23 = this[22];
      QueryInterface = v23->lpVtbl[1].QueryInterface;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(this + 21);
      v25 = ((__int64 (__fastcall *)(IUnknown *, HWND, GUID *, IUnknown **))QueryInterface)(
              v23,
              Ancestor,
              &GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c,
              this + 21);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x838,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v25,
          v31);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
        SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
        return v26;
      }
    }
    v27 = CModernShareCommand::SetupDataTransferManager((CModernShareCommand *)this, a2);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83B,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v27,
        v31);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
      SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
      return v28;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
      ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<unsigned short const (&)[6]>(L"local");
    v29 = ((__int64 (__fastcall *)(IUnknown *, HWND))this[22]->lpVtbl[1].AddRef)(this[22], Ancestor);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x840,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v29,
        v31);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
      SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
      return v30;
    }
    goto LABEL_49;
  }
  ShareVerbTelemetry::ShareVerb_InvokeWindowsShareForCloudFiles();
  v32 = 0;
  LOBYTE(v7) = 1;
  v8 = CreateIdentityShellItemArray(a2, v7, &v32);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E4,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v8,
      v31);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
    SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
    return v10;
  }
  if ( CModernShareCommand::IsStorageProviderOnedrive(v9, v32) )
  {
    v33 = 0;
    pv = 0;
    lpVtbl = a2->lpVtbl;
    v35 = 0;
    v13 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))lpVtbl->GetItemAt)(
            a2,
            0,
            &v35);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7EA,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v13,
        v31);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
      if ( pv )
        goto LABEL_31;
      goto LABEL_32;
    }
    v15 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    StorageProviderEnterpriseId = GetStorageProviderEnterpriseId(v35, (enum StorageProviderProtectionMode *)&v33, v15);
    v14 = StorageProviderEnterpriseId;
    if ( StorageProviderEnterpriseId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7EB,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)StorageProviderEnterpriseId,
        v31);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
      if ( pv )
        goto LABEL_31;
      goto LABEL_32;
    }
    if ( v33 == 2 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
        ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<unsigned short const (&)[6]>(L"cloud");
      WindowsShareSheet = CModernShareCommand::LoadWindowsShareSheet((CModernShareCommand *)this, v32);
      v14 = WindowsShareSheet;
      if ( WindowsShareSheet < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F3,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)WindowsShareSheet,
          v31);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
        if ( pv )
          goto LABEL_31;
        goto LABEL_32;
      }
      wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v38, 0);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
      if ( pv )
LABEL_24:
        CoTaskMemFree(pv);
LABEL_25:
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
      SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFFATest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFFATest>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
        ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<unsigned short const (&)[6]>(L"cloud");
      v18 = CModernShareCommand::LoadWindowsShareSheet((CModernShareCommand *)this, v32);
      v14 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7FE,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v18,
          v31);
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
        if ( pv )
LABEL_31:
          CoTaskMemFree(pv);
LABEL_32:
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
        SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
        return v14;
      }
      wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v38, 0);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
      if ( pv )
        goto LABEL_24;
      goto LABEL_25;
    }
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v35);
    v11 = (CModernShareCommand *)pv;
    if ( pv )
      CoTaskMemFree(pv);
  }
  hwnd = 0;
  if ( CModernShareCommand::TryGetStorageProviderShareLinkSource(
         v11,
         v32,
         1,
         (struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *)&hwnd) < 0
    || (pv = 0, (unsigned __int8)winrt::Windows::Foundation::operator==(&hwnd, &pv)) )
  {
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&hwnd);
    goto LABEL_45;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl'::`2'::impl) )
    ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<unsigned short const (&)[6]>(L"cloud");
  v19 = CModernShareCommand::LoadWindowsShareSheet((CModernShareCommand *)this, v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v38, 0);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&hwnd);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
    SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80E,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v19,
      v31);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&hwnd);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v32);
    SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke((SharingWizardTelemetry::ModernShareInvoke *)v38);
    return v20;
  }
}

```

## disassembly

```asm
0x180047af0  mov     [rsp+arg_18], rbx
0x180047af5  push    rsi
0x180047af6  push    rdi
0x180047af7  push    r12
0x180047af9  push    r14
0x180047afb  push    r15
0x180047afd  sub     rsp, 1C0h
0x180047b04  mov     rax, cs:__security_cookie
0x180047b0b  xor     rax, rsp
0x180047b0e  mov     [rsp+1E8h+var_38], rax
0x180047b16  mov     rdi, r8
0x180047b19  mov     r14, rdx
0x180047b1c  mov     rsi, rcx
0x180047b1f  lea     rdx, aModernshareinv; "ModernShareInvoke"
0x180047b26  lea     rcx, [rsp+1E8h+var_188]; struct wil::details::IFailureCallback *
0x180047b2b  call    ??0?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180047b30  lea     rax, ??_7ModernShareInvoke@SharingWizardTelemetry@@6B@; const SharingWizardTelemetry::ModernShareInvoke::`vftable'
0x180047b37  mov     [rsp+1E8h+var_188], rax
0x180047b3c  lea     rcx, [rsp+1E8h+var_188]; this
0x180047b41  call    ?StartActivity@ModernShareInvoke@SharingWizardTelemetry@@QEAAXXZ; SharingWizardTelemetry::ModernShareInvoke::StartActivity(void)
0x180047b46  nop
0x180047b47  test    r14, r14
0x180047b4a  jnz     short loc_180047B7F
0x180047b4c  mov     rcx, [rsp+1E8h]; this
0x180047b54  mov     ebx, 80070057h
0x180047b59  mov     r9d, ebx; char *
0x180047b5c  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047b63  mov     edx, 7D1h; void *
0x180047b68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047b6d  nop
0x180047b6e  lea     rcx, [rsp+1E8h+var_188]; this
0x180047b73  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047b78  mov     eax, ebx
0x180047b7a  jmp     loc_1800482AB
0x180047b7f  mov     [rsp+1E8h+var_1B8], 0
0x180047b88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest> `wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl(void)'::`2'::impl
0x180047b8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(void)
0x180047b94  test    al, al
0x180047b96  jz      loc_180048053
0x180047b9c  call    ??$call_factory_cast@P6A_NAEBUIIntegratedServicesGeographicRegionPoliciesStatics@Profile@System@WindowsUdk@winrt@@@ZUIntegratedServicesGeographicRegionPolicies@2345@U12345@V_lambda_1fb92ff044e7e9d3adc100b9821092ba_@@@impl@winrt@@YA?A_P$$QEAV_lambda_1fb92ff044e7e9d3adc100b9821092ba_@@@Z
0x180047ba1  test    al, al
0x180047ba3  jnz     loc_180048053
0x180047ba9  mov     [rsp+1E8h+var_190], 0
0x180047bb1  mov     rax, [r14]
0x180047bb4  lea     rdx, [rsp+1E8h+var_190]
0x180047bb9  mov     rcx, r14
0x180047bbc  mov     rax, [rax+38h]
0x180047bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047bc5  test    eax, eax
0x180047bc7  js      loc_180048033
0x180047bcd  cmp     [rsp+1E8h+var_190], 1
0x180047bd2  jnz     loc_180048033
0x180047bd8  mov     rcx, r14
0x180047bdb  call    _IsAnyItemCloudPlaceholder
0x180047be0  test    al, al
0x180047be2  jz      loc_180048033
0x180047be8  call    ?ShareVerb_InvokeWindowsShareForCloudFiles@ShareVerbTelemetry@@SAXXZ; ShareVerbTelemetry::ShareVerb_InvokeWindowsShareForCloudFiles(void)
0x180047bed  nop
0x180047bee  mov     rcx, [rsp+1E8h+var_1B8]
0x180047bf3  mov     [rsp+1E8h+var_1B8], 0
0x180047bfc  test    rcx, rcx
0x180047bff  jz      short loc_180047C0E
0x180047c01  mov     rax, [rcx]
0x180047c04  mov     rax, [rax+10h]
0x180047c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c0d  nop
0x180047c0e  lea     r8, [rsp+1E8h+var_1B8]
0x180047c13  mov     dl, 1
0x180047c15  mov     rcx, r14
0x180047c18  call    CreateIdentityShellItemArray
0x180047c1d  mov     ebx, eax
0x180047c1f  test    eax, eax
0x180047c21  jns     short loc_180047C5C
0x180047c23  mov     rcx, [rsp+1E8h]; this
0x180047c2b  mov     r9d, eax; char *
0x180047c2e  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047c35  mov     edx, 7E4h; void *
0x180047c3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c3f  nop
0x180047c40  lea     rcx, [rsp+1E8h+var_1B8]
0x180047c45  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047c4a  nop
0x180047c4b  lea     rcx, [rsp+1E8h+var_188]; this
0x180047c50  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047c55  mov     eax, ebx
0x180047c57  jmp     loc_1800482AB
0x180047c5c  mov     rdx, [rsp+1E8h+var_1B8]; struct IShellItemArray *
0x180047c61  call    ?IsStorageProviderOnedrive@CModernShareCommand@@AEAA_NPEAUIShellItemArray@@@Z; CModernShareCommand::IsStorageProviderOnedrive(IShellItemArray *)
0x180047c66  test    al, al
0x180047c68  jz      loc_180047F3C
0x180047c6e  mov     [rsp+1E8h+var_1B0], 0
0x180047c76  mov     [rsp+1E8h+pv], 0
0x180047c7f  mov     rax, [r14]
0x180047c82  mov     [rsp+1E8h+var_1A0], 0
0x180047c8b  lea     r8, [rsp+1E8h+var_1A0]
0x180047c90  xor     edx, edx
0x180047c92  mov     rcx, r14
0x180047c95  mov     rax, [rax+40h]
0x180047c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c9e  mov     ebx, eax
0x180047ca0  test    eax, eax
0x180047ca2  jns     short loc_180047CF9
0x180047ca4  mov     rcx, [rsp+1E8h]; this
0x180047cac  mov     r9d, eax; char *
0x180047caf  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047cb6  mov     edx, 7EAh; void *
0x180047cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047cc0  nop
0x180047cc1  lea     rcx, [rsp+1E8h+var_1A0]
0x180047cc6  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047ccb  nop
0x180047ccc  mov     rcx, [rsp+1E8h+pv]; pv
0x180047cd1  test    rcx, rcx
0x180047cd4  jz      short loc_180047CDD
0x180047cd6  call    cs:__imp_CoTaskMemFree
0x180047cdc  nop
0x180047cdd  lea     rcx, [rsp+1E8h+var_1B8]
0x180047ce2  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047ce7  nop
0x180047ce8  lea     rcx, [rsp+1E8h+var_188]; this
0x180047ced  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047cf2  mov     eax, ebx
0x180047cf4  jmp     loc_1800482AB
0x180047cf9  lea     rcx, [rsp+1E8h+pv]
0x180047cfe  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180047d03  mov     r8, rax; unsigned __int16 **
0x180047d06  lea     rdx, [rsp+1E8h+var_1B0]; enum StorageProviderProtectionMode *
0x180047d0b  mov     rcx, [rsp+1E8h+var_1A0]; struct IShellItem *
0x180047d10  call    ?GetStorageProviderEnterpriseId@@YAJPEAUIShellItem@@PEAW4StorageProviderProtectionMode@@PEAPEAG@Z; GetStorageProviderEnterpriseId(IShellItem *,StorageProviderProtectionMode *,ushort * *)
0x180047d15  mov     ebx, eax
0x180047d17  test    eax, eax
0x180047d19  jns     short loc_180047D70
0x180047d1b  mov     rcx, [rsp+1E8h]; this
0x180047d23  mov     r9d, eax; char *
0x180047d26  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047d2d  mov     edx, 7EBh; void *
0x180047d32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047d37  nop
0x180047d38  lea     rcx, [rsp+1E8h+var_1A0]
0x180047d3d  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047d42  nop
0x180047d43  mov     rcx, [rsp+1E8h+pv]; pv
0x180047d48  test    rcx, rcx
0x180047d4b  jz      short loc_180047D54
0x180047d4d  call    cs:__imp_CoTaskMemFree
0x180047d53  nop
0x180047d54  lea     rcx, [rsp+1E8h+var_1B8]
0x180047d59  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047d5e  nop
0x180047d5f  lea     rcx, [rsp+1E8h+var_188]; this
0x180047d64  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047d69  mov     eax, ebx
0x180047d6b  jmp     loc_1800482AB
0x180047d70  cmp     [rsp+1E8h+var_1B0], 2
0x180047d75  jnz     loc_180047E44
0x180047d7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShareExperiment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment> `wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl(void)'::`2'::impl
0x180047d82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(void)
0x180047d87  test    al, al
0x180047d89  jz      short loc_180047D97
0x180047d8b  lea     rcx, aCloud; "cloud"
0x180047d92  call    ??$BusinessTelemetry_SharesheetInvocationSource_Exp@AEAY05$$CBG@ShareVerbTelemetry@@SAXAEAY05$$CBG@Z; ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<ushort const (&)[6]>(ushort const (&)[6])
0x180047d97  mov     rdx, [rsp+1E8h+var_1B8]; struct IShellItemArray *
0x180047d9c  mov     rcx, rsi; this
0x180047d9f  call    ?LoadWindowsShareSheet@CModernShareCommand@@AEAAJPEAUIShellItemArray@@@Z; CModernShareCommand::LoadWindowsShareSheet(IShellItemArray *)
0x180047da4  mov     ebx, eax
0x180047da6  test    eax, eax
0x180047da8  jns     short loc_180047DFF
0x180047daa  mov     rcx, [rsp+1E8h]; this
0x180047db2  mov     r9d, eax; char *
0x180047db5  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047dbc  mov     edx, 7F3h; void *
0x180047dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047dc6  nop
0x180047dc7  lea     rcx, [rsp+1E8h+var_1A0]
0x180047dcc  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047dd1  nop
0x180047dd2  mov     rcx, [rsp+1E8h+pv]; pv
0x180047dd7  test    rcx, rcx
0x180047dda  jz      short loc_180047DE3
0x180047ddc  call    cs:__imp_CoTaskMemFree
0x180047de2  nop
0x180047de3  lea     rcx, [rsp+1E8h+var_1B8]
0x180047de8  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047ded  nop
0x180047dee  lea     rcx, [rsp+1E8h+var_188]; this
0x180047df3  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047df8  mov     eax, ebx
0x180047dfa  jmp     loc_1800482AB
0x180047dff  xor     edx, edx
0x180047e01  lea     rcx, [rsp+1E8h+var_188]
0x180047e06  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180047e0b  nop
0x180047e0c  lea     rcx, [rsp+1E8h+var_1A0]
0x180047e11  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047e16  nop
0x180047e17  mov     rcx, [rsp+1E8h+pv]; pv
0x180047e1c  test    rcx, rcx
0x180047e1f  jz      short loc_180047E28
0x180047e21  call    cs:__imp_CoTaskMemFree
0x180047e27  nop
0x180047e28  lea     rcx, [rsp+1E8h+var_1B8]
0x180047e2d  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047e32  nop
0x180047e33  lea     rcx, [rsp+1E8h+var_188]; this
0x180047e38  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047e3d  xor     eax, eax
0x180047e3f  jmp     loc_1800482AB
0x180047e44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCFFATest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCFFATest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFFATest> `wil::Feature<__WilFeatureTraits_Feature_SCFFATest>::GetImpl(void)'::`2'::impl
0x180047e4b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCFFATest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFFATest>::__private_IsEnabled(void)
0x180047e50  test    al, al
0x180047e52  jz      loc_180047F21
0x180047e58  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShareExperiment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment> `wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl(void)'::`2'::impl
0x180047e5f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(void)
0x180047e64  test    al, al
0x180047e66  jz      short loc_180047E74
0x180047e68  lea     rcx, aCloud; "cloud"
0x180047e6f  call    ??$BusinessTelemetry_SharesheetInvocationSource_Exp@AEAY05$$CBG@ShareVerbTelemetry@@SAXAEAY05$$CBG@Z; ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<ushort const (&)[6]>(ushort const (&)[6])
0x180047e74  mov     rdx, [rsp+1E8h+var_1B8]; struct IShellItemArray *
0x180047e79  mov     rcx, rsi; this
0x180047e7c  call    ?LoadWindowsShareSheet@CModernShareCommand@@AEAAJPEAUIShellItemArray@@@Z; CModernShareCommand::LoadWindowsShareSheet(IShellItemArray *)
0x180047e81  mov     ebx, eax
0x180047e83  test    eax, eax
0x180047e85  jns     short loc_180047EDC
0x180047e87  mov     rcx, [rsp+1E8h]; this
0x180047e8f  mov     r9d, eax; char *
0x180047e92  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047e99  mov     edx, 7FEh; void *
0x180047e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ea3  nop
0x180047ea4  lea     rcx, [rsp+1E8h+var_1A0]
0x180047ea9  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047eae  nop
0x180047eaf  mov     rcx, [rsp+1E8h+pv]; pv
0x180047eb4  test    rcx, rcx
0x180047eb7  jz      short loc_180047EC0
0x180047eb9  call    cs:__imp_CoTaskMemFree
0x180047ebf  nop
0x180047ec0  lea     rcx, [rsp+1E8h+var_1B8]
0x180047ec5  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047eca  nop
0x180047ecb  lea     rcx, [rsp+1E8h+var_188]; this
0x180047ed0  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047ed5  mov     eax, ebx
0x180047ed7  jmp     loc_1800482AB
0x180047edc  xor     edx, edx
0x180047ede  lea     rcx, [rsp+1E8h+var_188]
0x180047ee3  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180047ee8  nop
0x180047ee9  lea     rcx, [rsp+1E8h+var_1A0]
0x180047eee  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047ef3  nop
0x180047ef4  mov     rcx, [rsp+1E8h+pv]; pv
0x180047ef9  test    rcx, rcx
0x180047efc  jz      short loc_180047F05
0x180047efe  call    cs:__imp_CoTaskMemFree
0x180047f04  nop
0x180047f05  lea     rcx, [rsp+1E8h+var_1B8]
0x180047f0a  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047f0f  nop
0x180047f10  lea     rcx, [rsp+1E8h+var_188]; this
0x180047f15  call    ??1ModernShareInvoke@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ModernShareInvoke::~ModernShareInvoke(void)
0x180047f1a  xor     eax, eax
0x180047f1c  jmp     loc_1800482AB
0x180047f21  lea     rcx, [rsp+1E8h+var_1A0]
0x180047f26  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180047f2b  nop
0x180047f2c  mov     rcx, [rsp+1E8h+pv]; pv
0x180047f31  test    rcx, rcx
0x180047f34  jz      short loc_180047F3C
0x180047f36  call    cs:__imp_CoTaskMemFree
0x180047f3c  mov     [rsp+1E8h+hwnd], 0
0x180047f45  lea     r9, [rsp+1E8h+hwnd]; struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *
0x180047f4a  mov     r8d, 1; int
0x180047f50  mov     rdx, [rsp+1E8h+var_1B8]; struct IShellItemArray *
0x180047f55  call    ?TryGetStorageProviderShareLinkSource@CModernShareCommand@@AEAAJPEAUIShellItemArray@@HAEAUIStorageProviderShareLinkSource@Provider@Storage@Windows@winrt@@@Z; CModernShareCommand::TryGetStorageProviderShareLinkSource(IShellItemArray *,int,winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource &)
0x180047f5a  test    eax, eax
0x180047f5c  js      loc_180048029
0x180047f62  mov     [rsp+1E8h+pv], 0
0x180047f6b  lea     rdx, [rsp+1E8h+pv]
0x180047f70  lea     rcx, [rsp+1E8h+hwnd]
0x180047f75  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180047f7a  test    al, al
0x180047f7c  jnz     loc_180048029
0x180047f82  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShareExperiment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment> `wil::Feature<__WilFeatureTraits_Feature_ShareExperiment>::GetImpl(void)'::`2'::impl
0x180047f89  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShareExperiment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareExperiment>::__private_IsEnabled(void)
0x180047f8e  test    al, al
0x180047f90  jz      short loc_180047F9E
0x180047f92  lea     rcx, aCloud; "cloud"
0x180047f99  call    ??$BusinessTelemetry_SharesheetInvocationSource_Exp@AEAY05$$CBG@ShareVerbTelemetry@@SAXAEAY05$$CBG@Z; ShareVerbTelemetry::BusinessTelemetry_SharesheetInvocationSource_Exp<ushort const (&)[6]>(ushort const (&)[6])
0x180047f9e  mov     rdx, [rsp+1E8h+var_1B8]; struct IShellItemArray *
0x180047fa3  mov     rcx, rsi; this
0x180047fa6  call    ?LoadWindowsShareSheet@CModernShareCommand@@AEAAJPEAUIShellItemArray@@@Z; CModernShareCommand::LoadWindowsShareSheet(IShellItemArray *)
0x180047fab  mov     ebx, eax
0x180047fad  test    eax, eax
0x180047faf  jns     short loc_180047FF5
0x180047fb1  mov     rcx, [rsp+1E8h]; this
0x180047fb9  mov     r9d, eax; char *
0x180047fbc  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180047fc3  mov     edx, 80Eh; void *
0x180047fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
