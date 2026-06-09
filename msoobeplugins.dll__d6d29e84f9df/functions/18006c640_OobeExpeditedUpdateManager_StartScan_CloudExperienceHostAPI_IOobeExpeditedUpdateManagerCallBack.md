# OobeExpeditedUpdateManager::StartScan(CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack *)

- ea: `0x18006c640`
- end: `0x18006c9a7`
- name: `?StartScan@OobeExpeditedUpdateManager@@UEAAJPEAUIOobeExpeditedUpdateManagerCallBack@CloudExperienceHostAPI@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180006b18`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x180054a64`
- `0x18005cf54`
- `0x18005cf84`
- `0x18005d2a8`
- `0x18005e20c`
- `0x18005e3cc`
- `0x18005f124`
- `0x18005f23c`
- `0x18005f468`
- `0x18005f558`
- `0x180062d88`
- `0x1800632bc`
- `0x180063c08`
- `0x18006c640`
- `0x180070d98`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c91a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c91a`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18006c672`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18006c672`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18006c97b`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18006c97b`

## string_xrefs

- `0x18006c6a8`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c6eb`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c76b`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c7c5`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c834`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c8cb`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall OobeExpeditedUpdateManager::StartScan(
        RTL_SRWLOCK *this,
        struct CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack *a2)
{
  int v4; // ebx
  int v5; // eax
  char IsEnabled; // al
  RTL_SRWLOCK *v7; // rdi
  PVOID Ptr; // rcx
  int updated; // eax
  int v10; // eax
  void (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  void (__fastcall **v12)(_QWORD, GUID *, __int64 *); // rax
  int v13; // eax
  __int64 v14; // rcx
  void *v15; // rdx
  unsigned int v16; // r8d
  int v17; // r9d
  int v19; // [rsp+20h] [rbp-49h]
  OobeExpeditedUpdateStatusPropertyStore *v20; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v21[2]; // [rsp+38h] [rbp-31h] BYREF
  char v22; // [rsp+48h] [rbp-21h]
  char v23; // [rsp+51h] [rbp-18h]
  RTL_SRWLOCK *v24; // [rsp+58h] [rbp-11h] BYREF
  char v25[8]; // [rsp+60h] [rbp-9h] BYREF
  char v26[8]; // [rsp+68h] [rbp-1h] BYREF
  wil **v27; // [rsp+70h] [rbp+7h]
  char *v28; // [rsp+78h] [rbp+Fh]
  struct CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack *v29; // [rsp+80h] [rbp+17h] BYREF
  char v30; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v31; // [rsp+90h] [rbp+27h] BYREF
  wil *v32; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v29 = a2;
  CoAddRefServerProcess();
  v23 = 1;
  v30 = 1;
  v21[0] = a2;
  v21[1] = &v30;
  v22 = 1;
  if ( IsLowBattery() )
  {
    v4 = -2147467260;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)0x80004004LL,
      v19);
    v22 = 0;
    _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
  }
  else
  {
    v20 = 0;
    v5 = Microsoft::WRL::Details::MakeAndInitialize<OobeExpeditedUpdateStatusPropertyStore,INamedPropertyStore,CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack * &>(
           &v20,
           &v29);
    v4 = v5;
    if ( v5 >= 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupUsoTask>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupUsoTask>::GetImpl'::`2'::impl);
      v7 = this + 11;
      Ptr = this[11].Ptr;
      this[11].Ptr = 0;
      v29 = v20;
      if ( IsEnabled )
      {
        if ( Ptr )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
        updated = Microsoft::WRL::Details::MakeAndInitialize<ExpeditedUpdateUSOTask,CloudExperienceHostAPI::IExpeditedUpdateTask,INamedPropertyStore *>(
                    (ExpeditedUpdateUSOTask **)&this[11],
                    (struct INamedPropertyStore **)&v29);
        v4 = updated;
        if ( updated < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x172,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)updated,
            v19);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
          v22 = 0;
          _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
          goto LABEL_19;
        }
      }
      else
      {
        if ( Ptr )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
        v10 = Microsoft::WRL::Details::MakeAndInitialize<ExpeditedUpdateWUTask,CloudExperienceHostAPI::IExpeditedUpdateTask,INamedPropertyStore *>(
                (ExpeditedUpdateWUTask **)&this[11],
                (struct INamedPropertyStore **)&v29);
        v4 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v10,
            v19);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
          v22 = 0;
          _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
          goto LABEL_19;
        }
      }
      v31 = 0;
      v11 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v7->Ptr;
      v12 = *(void (__fastcall ***)(_QWORD, GUID *, __int64 *))v7->Ptr;
      v31 = 0;
      (*v12)(v11, &GUID_5a1a910b_7401_4918_9be2_e0c6e7be2b86, &v31);
      v32 = 0;
      v13 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              &v32,
              1);
      v4 = v13;
      if ( v13 >= 0 )
      {
        wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(
          &v29,
          this);
        wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(
          v25,
          v29);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
          v26,
          &v31);
        v27 = &v32;
        v28 = &v30;
        v4 = Windows::Internal::ComTaskPool::QueueTask<_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_>(v14, v25);
        _lambda_49cbbb9f3c58f4a46a51cd789624c3b3_::~_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_((_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_ *)v25);
        if ( v4 >= 0 )
        {
          AcquireSRWLockExclusive(this + 8);
          v24 = this + 8;
          wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy>::operator=(&this[9], &v31);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
          wil::handle_wait(v32, v15, v16, v17);
          wil::com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>::~com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>(&v29);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v31);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
          v22 = 0;
          _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
          v4 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x193,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v4,
            v19);
          wil::com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>::~com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>(&v29);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v31);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
          v22 = 0;
          _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v13,
          v19);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v32);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v31);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
        v22 = 0;
        _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v5,
        v19);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
      v22 = 0;
      _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(v21);
    }
  }
LABEL_19:
  CoReleaseServerProcess();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006c640  mov     [rsp-8+arg_10], rbx
0x18006c645  mov     [rsp-8+arg_18], rsi
0x18006c64a  push    rbp
0x18006c64b  push    rdi
0x18006c64c  push    r14
0x18006c64e  lea     rbp, [rsp-47h]
0x18006c653  sub     rsp, 0B0h
0x18006c65a  mov     rax, cs:__security_cookie
0x18006c661  xor     rax, rsp
0x18006c664  mov     [rbp+57h+var_20], rax
0x18006c668  mov     rbx, rdx
0x18006c66b  mov     rsi, rcx
0x18006c66e  mov     [rbp+57h+var_40], rdx
0x18006c672  call    cs:__imp_CoAddRefServerProcess
0x18006c678  mov     [rbp+57h+var_6F], 1
0x18006c67c  mov     [rbp+57h+var_38], 1
0x18006c680  mov     [rbp+57h+var_88], rbx
0x18006c684  lea     rax, [rbp+57h+var_38]
0x18006c688  mov     [rbp+57h+var_80], rax
0x18006c68c  mov     [rbp+57h+var_78], 1
0x18006c690  call    ?IsLowBattery@@YA_NXZ; IsLowBattery(void)
0x18006c695  xor     r14d, r14d
0x18006c698  test    al, al
0x18006c69a  jz      short loc_18006C6CD
0x18006c69c  mov     rcx, [rbp+5Fh]; this
0x18006c6a0  mov     ebx, 80004004h
0x18006c6a5  mov     r9d, ebx; char *
0x18006c6a8  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c6af  mov     edx, 16Bh; void *
0x18006c6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c6b9  nop
0x18006c6ba  mov     [rbp+57h+var_78], r14b
0x18006c6be  lea     rcx, [rbp+57h+var_88]
0x18006c6c2  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c6c7  nop
0x18006c6c8  jmp     loc_18006C97B
0x18006c6cd  mov     [rbp+57h+var_90], r14
0x18006c6d1  lea     rdx, [rbp+57h+var_40]
0x18006c6d5  lea     rcx, [rbp+57h+var_90]
0x18006c6d9  call    ??$MakeAndInitialize@VOobeExpeditedUpdateStatusPropertyStore@@UINamedPropertyStore@@AEAPEAUIOobeExpeditedUpdateManagerCallBack@CloudExperienceHostAPI@@@Details@WRL@Microsoft@@YAJPEAPEAUINamedPropertyStore@@AEAPEAUIOobeExpeditedUpdateManagerCallBack@CloudExperienceHostAPI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OobeExpeditedUpdateStatusPropertyStore,INamedPropertyStore,CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack * &>(INamedPropertyStore * *,CloudExperienceHostAPI::IOobeExpeditedUpdateManagerCallBack * &)
0x18006c6de  mov     ebx, eax
0x18006c6e0  test    eax, eax
0x18006c6e2  jns     short loc_18006C71A
0x18006c6e4  mov     rcx, [rbp+5Fh]; this
0x18006c6e8  mov     r9d, eax; char *
0x18006c6eb  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c6f2  mov     edx, 16Fh; void *
0x18006c6f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c6fc  nop
0x18006c6fd  lea     rcx, [rbp+57h+var_90]
0x18006c701  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c706  nop
0x18006c707  mov     [rbp+57h+var_78], r14b
0x18006c70b  lea     rcx, [rbp+57h+var_88]
0x18006c70f  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c714  nop
0x18006c715  jmp     loc_18006C97B
0x18006c71a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeNdupUsoTask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupUsoTask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupUsoTask> `wil::Feature<__WilFeatureTraits_Feature_OobeNdupUsoTask>::GetImpl(void)'::`2'::impl
0x18006c721  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupUsoTask@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupUsoTask>::__private_IsEnabled(void)
0x18006c726  lea     rdi, [rsi+58h]
0x18006c72a  mov     rcx, [rdi]
0x18006c72d  mov     [rdi], r14
0x18006c730  test    al, al
0x18006c732  mov     rax, [rbp+57h+var_90]
0x18006c736  mov     [rbp+57h+var_40], rax
0x18006c73a  jz      short loc_18006C79A
0x18006c73c  test    rcx, rcx
0x18006c73f  jz      short loc_18006C74E
0x18006c741  mov     rax, [rcx]
0x18006c744  mov     rax, [rax+10h]
0x18006c748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c74d  nop
0x18006c74e  lea     rdx, [rbp+57h+var_40]
0x18006c752  mov     rcx, rdi
0x18006c755  call    ??$MakeAndInitialize@VExpeditedUpdateUSOTask@@UIExpeditedUpdateTask@CloudExperienceHostAPI@@PEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIExpeditedUpdateTask@CloudExperienceHostAPI@@$$QEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ExpeditedUpdateUSOTask,CloudExperienceHostAPI::IExpeditedUpdateTask,INamedPropertyStore *>(CloudExperienceHostAPI::IExpeditedUpdateTask * *,INamedPropertyStore * &&)
0x18006c75a  mov     ebx, eax
0x18006c75c  test    eax, eax
0x18006c75e  jns     loc_18006C7F4
0x18006c764  mov     rcx, [rbp+5Fh]; this
0x18006c768  mov     r9d, eax; char *
0x18006c76b  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c772  mov     edx, 172h; void *
0x18006c777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c77c  nop
0x18006c77d  lea     rcx, [rbp+57h+var_90]
0x18006c781  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c786  nop
0x18006c787  mov     [rbp+57h+var_78], r14b
0x18006c78b  lea     rcx, [rbp+57h+var_88]
0x18006c78f  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c794  nop
0x18006c795  jmp     loc_18006C97B
0x18006c79a  test    rcx, rcx
0x18006c79d  jz      short loc_18006C7AC
0x18006c79f  mov     rax, [rcx]
0x18006c7a2  mov     rax, [rax+10h]
0x18006c7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7ab  nop
0x18006c7ac  lea     rdx, [rbp+57h+var_40]
0x18006c7b0  mov     rcx, rdi
0x18006c7b3  call    ??$MakeAndInitialize@VExpeditedUpdateWUTask@@UIExpeditedUpdateTask@CloudExperienceHostAPI@@PEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIExpeditedUpdateTask@CloudExperienceHostAPI@@$$QEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ExpeditedUpdateWUTask,CloudExperienceHostAPI::IExpeditedUpdateTask,INamedPropertyStore *>(CloudExperienceHostAPI::IExpeditedUpdateTask * *,INamedPropertyStore * &&)
0x18006c7b8  mov     ebx, eax
0x18006c7ba  test    eax, eax
0x18006c7bc  jns     short loc_18006C7F4
0x18006c7be  mov     rcx, [rbp+5Fh]; this
0x18006c7c2  mov     r9d, eax; char *
0x18006c7c5  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c7cc  mov     edx, 176h; void *
0x18006c7d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c7d6  nop
0x18006c7d7  lea     rcx, [rbp+57h+var_90]
0x18006c7db  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c7e0  nop
0x18006c7e1  mov     [rbp+57h+var_78], r14b
0x18006c7e5  lea     rcx, [rbp+57h+var_88]
0x18006c7e9  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c7ee  nop
0x18006c7ef  jmp     loc_18006C97B
0x18006c7f4  mov     [rbp+57h+var_30], r14
0x18006c7f8  mov     rcx, [rdi]
0x18006c7fb  mov     rax, [rcx]
0x18006c7fe  mov     [rbp+57h+var_30], r14
0x18006c802  lea     r8, [rbp+57h+var_30]
0x18006c806  lea     rdx, _GUID_5a1a910b_7401_4918_9be2_e0c6e7be2b86
0x18006c80d  mov     rax, [rax]
0x18006c810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c815  mov     [rbp+57h+var_28], r14
0x18006c819  mov     edx, 1
0x18006c81e  lea     rcx, [rbp+57h+var_28]
0x18006c822  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006c827  mov     ebx, eax
0x18006c829  test    eax, eax
0x18006c82b  jns     short loc_18006C876
0x18006c82d  mov     rcx, [rbp+5Fh]; this
0x18006c831  mov     r9d, eax; char *
0x18006c834  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c83b  mov     edx, 17Eh; void *
0x18006c840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c845  lea     rcx, [rbp+57h+var_28]
0x18006c849  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006c84e  nop
0x18006c84f  lea     rcx, [rbp+57h+var_30]
0x18006c853  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c858  nop
0x18006c859  lea     rcx, [rbp+57h+var_90]
0x18006c85d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c862  nop
0x18006c863  mov     [rbp+57h+var_78], r14b
0x18006c867  lea     rcx, [rbp+57h+var_88]
0x18006c86b  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c870  nop
0x18006c871  jmp     loc_18006C97B
0x18006c876  mov     rdx, rsi
0x18006c879  lea     rcx, [rbp+57h+var_40]
0x18006c87d  call    ??0?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeZdpManager@@@Z; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(OobeZdpManager *)
0x18006c882  mov     rdx, [rbp+57h+var_40]
0x18006c886  lea     rcx, [rbp+57h+var_60]
0x18006c88a  call    ??0?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeZdpManager@@@Z; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(OobeZdpManager *)
0x18006c88f  lea     rdx, [rbp+57h+var_30]
0x18006c893  lea     rcx, [rbp+57h+var_58]
0x18006c897  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x18006c89c  lea     rax, [rbp+57h+var_28]
0x18006c8a0  mov     [rbp+57h+var_50], rax
0x18006c8a4  lea     rax, [rbp+57h+var_38]
0x18006c8a8  mov     [rbp+57h+var_48], rax
0x18006c8ac  lea     rdx, [rbp+57h+var_60]
0x18006c8b0  call    ??$QueueTask@V_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_>(Windows::Internal::TaskApartment,_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_ &&)
0x18006c8b5  mov     ebx, eax
0x18006c8b7  lea     rcx, [rbp+57h+var_60]; this
0x18006c8bb  call    ??1_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_@@QEAA@XZ; _lambda_49cbbb9f3c58f4a46a51cd789624c3b3_::~_lambda_49cbbb9f3c58f4a46a51cd789624c3b3_(void)
0x18006c8c0  test    ebx, ebx
0x18006c8c2  jns     short loc_18006C913
0x18006c8c4  mov     rcx, [rbp+5Fh]; this
0x18006c8c8  mov     r9d, ebx; char *
0x18006c8cb  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c8d2  mov     edx, 193h; void *
0x18006c8d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c8dc  lea     rcx, [rbp+57h+var_40]
0x18006c8e0  call    ??1?$com_ptr_t@VOobeExpeditedUpdateManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>::~com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>(void)
0x18006c8e5  lea     rcx, [rbp+57h+var_28]
0x18006c8e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006c8ee  nop
0x18006c8ef  lea     rcx, [rbp+57h+var_30]
0x18006c8f3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c8f8  nop
0x18006c8f9  lea     rcx, [rbp+57h+var_90]
0x18006c8fd  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c902  nop
0x18006c903  mov     [rbp+57h+var_78], r14b
0x18006c907  lea     rcx, [rbp+57h+var_88]
0x18006c90b  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c910  nop
0x18006c911  jmp     short loc_18006C97B
0x18006c913  lea     rbx, [rsi+40h]
0x18006c917  mov     rcx, rbx; SRWLock
0x18006c91a  call    cs:__imp_AcquireSRWLockExclusive
0x18006c920  mov     [rbp+57h+var_68], rbx
0x18006c924  lea     rcx, [rsi+48h]
0x18006c928  lea     rdx, [rbp+57h+var_30]
0x18006c92c  call    ??4?$com_ptr_t@UIOOBECancellableTask@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy> const &)
0x18006c931  lea     rcx, [rbp+57h+var_68]
0x18006c935  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006c93a  mov     rcx, [rbp+57h+var_28]; this
0x18006c93e  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18006c943  lea     rcx, [rbp+57h+var_40]
0x18006c947  call    ??1?$com_ptr_t@VOobeExpeditedUpdateManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>::~com_ptr_t<OobeExpeditedUpdateManager,wil::err_exception_policy>(void)
0x18006c94c  lea     rcx, [rbp+57h+var_28]
0x18006c950  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006c955  nop
0x18006c956  lea     rcx, [rbp+57h+var_30]
0x18006c95a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c95f  nop
0x18006c960  lea     rcx, [rbp+57h+var_90]
0x18006c964  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c969  nop
0x18006c96a  mov     [rbp+57h+var_78], r14b
0x18006c96e  lea     rcx, [rbp+57h+var_88]
0x18006c972  call    ??R_lambda_7b2acef07bb712895dac199eaffffd7b_@@QEBA@XZ; _lambda_7b2acef07bb712895dac199eaffffd7b_::operator()(void)
0x18006c977  nop
0x18006c978  mov     ebx, r14d
0x18006c97b  call    cs:__imp_CoReleaseServerProcess
0x18006c981  mov     eax, ebx
0x18006c983  mov     rcx, [rbp+57h+var_20]
0x18006c987  xor     rcx, rsp; StackCookie
0x18006c98a  call    __security_check_cookie
0x18006c98f  lea     r11, [rsp+0C0h+var_10]
0x18006c997  mov     rbx, [r11+30h]
0x18006c99b  mov     rsi, [r11+38h]
0x18006c99f  mov     rsp, r11
0x18006c9a2  pop     r14
0x18006c9a4  pop     rdi
0x18006c9a5  pop     rbp
0x18006c9a6  retn
```
