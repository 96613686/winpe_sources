# OobeZdpManager::StartUpdate(CloudExperienceHostAPI::IOobeZdpManagerCallBack *)

- ea: `0x18005ddb0`
- end: `0x18005e1a3`
- name: `?StartUpdate@OobeZdpManager@@UEAAJPEAUIOobeZdpManagerCallBack@CloudExperienceHostAPI@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(OobeZdpManager *__hidden this, struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006b18`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x1800230b0`
- `0x180054a64`
- `0x180055b48`
- `0x180059030`
- `0x18005cb38`
- `0x18005cda0`
- `0x18005cf54`
- `0x18005cf84`
- `0x18005d0d0`
- `0x18005d1b8`
- `0x18005d2a8`
- `0x18005ddb0`
- `0x18005e20c`
- `0x18005e3cc`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e0fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e0fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e037`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18005ddd3`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18005ddd3`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18005e184`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18005e184`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005e052`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005e052`

## string_xrefs

- `0x18005de0c`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005de42`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005de77`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005deb7`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005def4`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005df3d`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005df73`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005dfc5`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005e083`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005e0de`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`
- `0x18005e16f`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OobeZdpManager::StartUpdate(
        RTL_SRWLOCK *this,
        struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rax
  __int64 v13; // rsi
  DWORD CurrentThreadId; // eax
  int v15; // eax
  void *v16; // rdx
  unsigned int v17; // r8d
  int v18; // r9d
  int v19; // eax
  int v21; // [rsp+20h] [rbp-39h]
  int v22; // [rsp+20h] [rbp-39h]
  int v23; // [rsp+20h] [rbp-39h]
  int v24; // [rsp+20h] [rbp-39h]
  int v25; // [rsp+20h] [rbp-39h]
  int v26; // [rsp+20h] [rbp-39h]
  __int64 v27; // [rsp+30h] [rbp-29h] BYREF
  __int64 v28; // [rsp+38h] [rbp-21h] BYREF
  wil *v29; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v30[3]; // [rsp+48h] [rbp-11h] BYREF
  char v31; // [rsp+60h] [rbp+7h]
  __int64 v32; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE v33[8]; // [rsp+70h] [rbp+17h] BYREF
  wil **v34; // [rsp+78h] [rbp+1Fh]
  char *v35; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *v37; // [rsp+C8h] [rbp+6Fh] BYREF
  char v38; // [rsp+D0h] [rbp+77h] BYREF
  char v39; // [rsp+D9h] [rbp+80h]

  v37 = a2;
  CoAddRefServerProcess();
  v39 = 1;
  v38 = 1;
  v30[1] = a2;
  v30[2] = &v38;
  v31 = 1;
  if ( IsLowBattery() )
  {
    v4 = -2147467260;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
      (const char *)0x80004004LL,
      v21);
    if ( v38 )
    {
      v5 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
             a2,
             4);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
          (const char *)(unsigned int)v5,
          v22);
    }
  }
  else
  {
    v28 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<OobeZdpStatusPropertyStore,INamedPropertyStore,CloudExperienceHostAPI::IOobeZdpManagerCallBack * &>(
           &v28,
           &v37);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v27 = 0;
      v37 = (struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *)v28;
      v8 = Microsoft::WRL::Details::MakeAndInitialize<CZDPTask,IOOBECancellableTask,INamedPropertyStore * &>(
             &v27,
             (__int64 *)&v37);
      v4 = v8;
      if ( v8 >= 0 )
      {
        v29 = 0;
        v10 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                &v29,
                1);
        v4 = v10;
        if ( v10 >= 0 )
        {
          wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(
            &v37,
            this);
          wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(
            &v32,
            v37);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
            v33,
            &v27);
          v34 = &v29;
          v35 = &v38;
          v12 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_>,_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_>(
                  v30,
                  &v32);
          v13 = *v12;
          *v12 = 0;
          if ( v30[0] )
          {
            v30[0] = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConciergeSettingProvider>::Release();
          }
          CurrentThreadId = GetCurrentThreadId();
          v4 = SHTaskPoolQueueTask(1, 0, CurrentThreadId, 0);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          _lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_::~_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_((_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_ *)&v32);
          if ( v4 >= 0 )
          {
            AcquireSRWLockExclusive(this + 8);
            v30[0] = this + 8;
            wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy>::operator=(&this[9], &v27);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v30);
            wil::handle_wait(v29, v16, v17, v18);
            wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(&v37);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
            if ( v38 )
            {
              v19 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
                      a2,
                      4);
              if ( v19 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8D,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
                  (const char *)(unsigned int)v19,
                  v13);
            }
            v4 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB3,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
              (const char *)(unsigned int)v4,
              v13);
            wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(&v37);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
            wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
            if ( v38 )
            {
              v15 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
                      a2,
                      4);
              if ( v15 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8D,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
                  (const char *)(unsigned int)v15,
                  v26);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9E,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
            (const char *)(unsigned int)v10,
            v21);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
          if ( v38 )
          {
            v11 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
                    a2,
                    4);
            if ( v11 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x8D,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
                (const char *)(unsigned int)v11,
                v25);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
          (const char *)(unsigned int)v8,
          v21);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v27);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
        if ( v38 )
        {
          v9 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
                 a2,
                 4);
          if ( v9 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8D,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
              (const char *)(unsigned int)v9,
              v24);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
        (const char *)(unsigned int)v6,
        v21);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
      if ( v38 )
      {
        v7 = (*(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeZdpManagerCallBack *, __int64))(*(_QWORD *)a2 + 48LL))(
               a2,
               4);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
            (const char *)(unsigned int)v7,
            v23);
      }
    }
  }
  CoReleaseServerProcess();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005ddb0  mov     [rsp-8+arg_0], rbx
0x18005ddb5  mov     [rsp-8+arg_8], rdx
0x18005ddba  push    rbp
0x18005ddbb  push    rsi
0x18005ddbc  push    rdi
0x18005ddbd  push    r14
0x18005ddbf  push    r15
0x18005ddc1  lea     rbp, [rsp-37h]
0x18005ddc6  sub     rsp, 90h
0x18005ddcd  mov     rdi, rdx
0x18005ddd0  mov     r14, rcx
0x18005ddd3  call    cs:__imp_CoAddRefServerProcess
0x18005ddd9  mov     [rbp+57h+arg_19], 1
0x18005dde0  mov     [rbp+57h+arg_10], 1
0x18005dde4  mov     [rbp+57h+var_60], rdi
0x18005dde8  lea     rax, [rbp+57h+arg_10]
0x18005ddec  mov     [rbp+57h+var_58], rax
0x18005ddf0  mov     [rbp+57h+var_50], 1
0x18005ddf4  call    ?IsLowBattery@@YA_NXZ; IsLowBattery(void)
0x18005ddf9  xor     r15d, r15d
0x18005ddfc  test    al, al
0x18005ddfe  jz      short loc_18005DE59
0x18005de00  mov     rcx, [rbp+5Fh]; this
0x18005de04  mov     ebx, 80004004h
0x18005de09  mov     r9d, ebx; char *
0x18005de0c  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005de13  mov     edx, 94h; void *
0x18005de18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005de1d  nop
0x18005de1e  cmp     [rbp+57h+arg_10], r15b
0x18005de22  jz      short loc_18005DE54
0x18005de24  mov     rax, [rdi]
0x18005de27  lea     edx, [r15+4]
0x18005de2b  mov     rcx, rdi
0x18005de2e  mov     rax, [rax+30h]
0x18005de32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de37  mov     rcx, [rbp+5Fh]; this
0x18005de3b  test    eax, eax
0x18005de3d  jns     short loc_18005DE54
0x18005de3f  mov     r9d, eax; char *
0x18005de42  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005de49  mov     edx, 8Dh; void *
0x18005de4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005de53  nop
0x18005de54  jmp     loc_18005E184
0x18005de59  mov     [rbp+57h+var_78], r15
0x18005de5d  lea     rdx, [rbp+57h+arg_8]
0x18005de61  lea     rcx, [rbp+57h+var_78]
0x18005de65  call    ??$MakeAndInitialize@VOobeZdpStatusPropertyStore@@UINamedPropertyStore@@AEAPEAUIOobeZdpManagerCallBack@CloudExperienceHostAPI@@@Details@WRL@Microsoft@@YAJPEAPEAUINamedPropertyStore@@AEAPEAUIOobeZdpManagerCallBack@CloudExperienceHostAPI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OobeZdpStatusPropertyStore,INamedPropertyStore,CloudExperienceHostAPI::IOobeZdpManagerCallBack * &>(INamedPropertyStore * *,CloudExperienceHostAPI::IOobeZdpManagerCallBack * &)
0x18005de6a  mov     ebx, eax
0x18005de6c  test    eax, eax
0x18005de6e  jns     short loc_18005DECE
0x18005de70  mov     rcx, [rbp+5Fh]; this
0x18005de74  mov     r9d, eax; char *
0x18005de77  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005de7e  mov     edx, 98h; void *
0x18005de83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005de88  lea     rcx, [rbp+57h+var_78]
0x18005de8c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005de91  nop
0x18005de92  cmp     [rbp+57h+arg_10], r15b
0x18005de96  jz      short loc_18005DEC9
0x18005de98  mov     rax, [rdi]
0x18005de9b  mov     edx, 4
0x18005dea0  mov     rcx, rdi
0x18005dea3  mov     rax, [rax+30h]
0x18005dea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005deac  mov     rcx, [rbp+5Fh]; this
0x18005deb0  test    eax, eax
0x18005deb2  jns     short loc_18005DEC9
0x18005deb4  mov     r9d, eax; char *
0x18005deb7  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005debe  mov     edx, 8Dh; void *
0x18005dec3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005dec8  nop
0x18005dec9  jmp     loc_18005E184
0x18005dece  mov     [rbp+57h+var_80], r15
0x18005ded2  mov     rax, [rbp+57h+var_78]
0x18005ded6  mov     [rbp+57h+arg_8], rax
0x18005deda  lea     rdx, [rbp+57h+arg_8]
0x18005dede  lea     rcx, [rbp+57h+var_80]
0x18005dee2  call    ??$MakeAndInitialize@VCZDPTask@@UIOOBECancellableTask@@AEAPEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIOOBECancellableTask@@AEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CZDPTask,IOOBECancellableTask,INamedPropertyStore * &>(IOOBECancellableTask * *,INamedPropertyStore * &)
0x18005dee7  mov     ebx, eax
0x18005dee9  test    eax, eax
0x18005deeb  jns     short loc_18005DF54
0x18005deed  mov     rcx, [rbp+5Fh]; this
0x18005def1  mov     r9d, eax; char *
0x18005def4  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005defb  mov     edx, 9Ah; void *
0x18005df00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df05  lea     rcx, [rbp+57h+var_80]
0x18005df09  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005df0e  lea     rcx, [rbp+57h+var_78]
0x18005df12  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005df17  nop
0x18005df18  cmp     [rbp+57h+arg_10], r15b
0x18005df1c  jz      short loc_18005DF4F
0x18005df1e  mov     rax, [rdi]
0x18005df21  mov     edx, 4
0x18005df26  mov     rcx, rdi
0x18005df29  mov     rax, [rax+30h]
0x18005df2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df32  mov     rcx, [rbp+5Fh]; this
0x18005df36  test    eax, eax
0x18005df38  jns     short loc_18005DF4F
0x18005df3a  mov     r9d, eax; char *
0x18005df3d  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005df44  mov     edx, 8Dh; void *
0x18005df49  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005df4e  nop
0x18005df4f  jmp     loc_18005E184
0x18005df54  mov     [rbp+57h+var_70], r15
0x18005df58  mov     edx, 1
0x18005df5d  lea     rcx, [rbp+57h+var_70]
0x18005df61  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005df66  mov     ebx, eax
0x18005df68  test    eax, eax
0x18005df6a  jns     short loc_18005DFDC
0x18005df6c  mov     rcx, [rbp+5Fh]; this
0x18005df70  mov     r9d, eax; char *
0x18005df73  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005df7a  mov     edx, 9Eh; void *
0x18005df7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005df84  lea     rcx, [rbp+57h+var_70]
0x18005df88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005df8d  lea     rcx, [rbp+57h+var_80]
0x18005df91  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005df96  lea     rcx, [rbp+57h+var_78]
0x18005df9a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005df9f  nop
0x18005dfa0  cmp     [rbp+57h+arg_10], r15b
0x18005dfa4  jz      short loc_18005DFD7
0x18005dfa6  mov     rax, [rdi]
0x18005dfa9  mov     edx, 4
0x18005dfae  mov     rcx, rdi
0x18005dfb1  mov     rax, [rax+30h]
0x18005dfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfba  mov     rcx, [rbp+5Fh]; this
0x18005dfbe  test    eax, eax
0x18005dfc0  jns     short loc_18005DFD7
0x18005dfc2  mov     r9d, eax; char *
0x18005dfc5  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005dfcc  mov     edx, 8Dh; void *
0x18005dfd1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005dfd6  nop
0x18005dfd7  jmp     loc_18005E184
0x18005dfdc  mov     rdx, r14
0x18005dfdf  lea     rcx, [rbp+57h+arg_8]
0x18005dfe3  call    ??0?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeZdpManager@@@Z; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(OobeZdpManager *)
0x18005dfe8  mov     rdx, [rbp+57h+arg_8]
0x18005dfec  lea     rcx, [rbp+57h+var_48]
0x18005dff0  call    ??0?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeZdpManager@@@Z; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::com_ptr_t<OobeZdpManager,wil::err_exception_policy>(OobeZdpManager *)
0x18005dff5  lea     rdx, [rbp+57h+var_80]
0x18005dff9  lea     rcx, [rbp+57h+var_40]
0x18005dffd  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x18005e002  lea     rax, [rbp+57h+var_70]
0x18005e006  mov     [rbp+57h+var_38], rax
0x18005e00a  lea     rax, [rbp+57h+arg_10]
0x18005e00e  mov     [rbp+57h+var_30], rax
0x18005e012  lea     rdx, [rbp+57h+var_48]
0x18005e016  lea     rcx, [rbp+57h+var_68]
0x18005e01a  call    ??$Make@V?$CTaskWrapper@V_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_@@@ComTaskPool@Internal@Windows@@V_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_>,_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_>(_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_ &&)
0x18005e01f  mov     rsi, [rax]
0x18005e022  mov     [rax], r15
0x18005e025  mov     rcx, [rbp+57h+var_68]
0x18005e029  test    rcx, rcx
0x18005e02c  jz      short loc_18005E037
0x18005e02e  mov     [rbp+57h+var_68], r15
0x18005e032  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIConciergeSettingProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConciergeSettingProvider>::Release(void)
0x18005e037  call    cs:__imp_GetCurrentThreadId
0x18005e03d  mov     [rsp+0B0h+var_88], r15
0x18005e042  mov     qword ptr [rsp+0B0h+var_90], rsi; int
0x18005e047  xor     r9d, r9d
0x18005e04a  mov     r8d, eax
0x18005e04d  xor     edx, edx
0x18005e04f  lea     ecx, [rdx+1]
0x18005e052  call    cs:__imp_SHTaskPoolQueueTask
0x18005e058  mov     ebx, eax
0x18005e05a  test    rsi, rsi
0x18005e05d  jz      short loc_18005E06F
0x18005e05f  mov     rax, [rsi]
0x18005e062  mov     rcx, rsi
0x18005e065  mov     rax, [rax+10h]
0x18005e069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e06e  nop
0x18005e06f  lea     rcx, [rbp+57h+var_48]; this
0x18005e073  call    ??1_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_@@QEAA@XZ; _lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_::~_lambda_7fb3e2fc0a8ed1930a2d72c0630714f6_(void)
0x18005e078  test    ebx, ebx
0x18005e07a  jns     short loc_18005E0F5
0x18005e07c  mov     rcx, [rbp+5Fh]; this
0x18005e080  mov     r9d, ebx; char *
0x18005e083  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005e08a  mov     edx, 0B3h; void *
0x18005e08f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e094  lea     rcx, [rbp+57h+arg_8]
0x18005e098  call    ??1?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(void)
0x18005e09d  lea     rcx, [rbp+57h+var_70]
0x18005e0a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e0a6  lea     rcx, [rbp+57h+var_80]
0x18005e0aa  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005e0af  lea     rcx, [rbp+57h+var_78]
0x18005e0b3  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005e0b8  nop
0x18005e0b9  cmp     [rbp+57h+arg_10], r15b
0x18005e0bd  jz      short loc_18005E0F0
0x18005e0bf  mov     rax, [rdi]
0x18005e0c2  mov     edx, 4
0x18005e0c7  mov     rcx, rdi
0x18005e0ca  mov     rax, [rax+30h]
0x18005e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0d3  mov     rcx, [rbp+5Fh]; this
0x18005e0d7  test    eax, eax
0x18005e0d9  jns     short loc_18005E0F0
0x18005e0db  mov     r9d, eax; char *
0x18005e0de  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005e0e5  mov     edx, 8Dh; void *
0x18005e0ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e0ef  nop
0x18005e0f0  jmp     loc_18005E184
0x18005e0f5  lea     rbx, [r14+40h]
0x18005e0f9  mov     rcx, rbx; SRWLock
0x18005e0fc  call    cs:__imp_AcquireSRWLockExclusive
0x18005e102  mov     [rbp+57h+var_68], rbx
0x18005e106  lea     rcx, [r14+48h]
0x18005e10a  lea     rdx, [rbp+57h+var_80]
0x18005e10e  call    ??4?$com_ptr_t@UIOOBECancellableTask@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOOBECancellableTask,wil::err_exception_policy> const &)
0x18005e113  lea     rcx, [rbp+57h+var_68]
0x18005e117  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005e11c  mov     rcx, [rbp+57h+var_70]; this
0x18005e120  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18005e125  lea     rcx, [rbp+57h+arg_8]
0x18005e129  call    ??1?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(void)
0x18005e12e  lea     rcx, [rbp+57h+var_70]
0x18005e132  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e137  lea     rcx, [rbp+57h+var_80]
0x18005e13b  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005e140  lea     rcx, [rbp+57h+var_78]
0x18005e144  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18005e149  nop
0x18005e14a  cmp     [rbp+57h+arg_10], r15b
0x18005e14e  jz      short loc_18005E181
0x18005e150  mov     rax, [rdi]
0x18005e153  mov     edx, 4
0x18005e158  mov     rcx, rdi
0x18005e15b  mov     rax, [rax+30h]
0x18005e15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e164  mov     rcx, [rbp+5Fh]; this
0x18005e168  test    eax, eax
0x18005e16a  jns     short loc_18005E181
0x18005e16c  mov     r9d, eax; char *
0x18005e16f  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005e176  mov     edx, 8Dh; void *
0x18005e17b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e180  nop
0x18005e181  mov     ebx, r15d
0x18005e184  call    cs:__imp_CoReleaseServerProcess
0x18005e18a  mov     eax, ebx
0x18005e18c  mov     rbx, [rsp+0B0h+arg_0]
0x18005e194  add     rsp, 90h
0x18005e19b  pop     r15
0x18005e19d  pop     r14
0x18005e19f  pop     rdi
0x18005e1a0  pop     rsi
0x18005e1a1  pop     rbp
0x18005e1a2  retn
```
