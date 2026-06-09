# OobeZdpElevatedManagerCore::BeginAsyncInstall(IUpdateInstaller *,IUpdateCollection *,void *,IInstallationJob * *)

- ea: `0x18000ddf4`
- end: `0x18000dfab`
- name: `?BeginAsyncInstall@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateInstaller@@PEAUIUpdateCollection@@PEAXPEAPEAUIInstallationJob@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateInstaller *, struct IUpdateCollection *, void *, struct IInstallationJob **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f044`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000b098`
- `0x18000c46c`
- `0x18000c6ec`
- `0x18000d684`
- `0x18000ddf4`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ded4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ded4`
- `OLEAUT32!__imp_VariantInit` at `0x18000df2a`
- `OLEAUT32!__imp_VariantInit` at `0x18000df2a`
- `OLEAUT32!__imp_VariantClear` at `0x18000df79`
- `OLEAUT32!__imp_VariantClear` at `0x18000df79`

## string_xrefs

- `0x18000de41`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000de79`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000deab`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000defe`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OobeZdpElevatedManagerCore::BeginAsyncInstall(
        RTL_SRWLOCK *this,
        struct IUpdateInstaller *a2,
        struct IUpdateCollection *a3,
        void *a4,
        struct IInstallationJob **a5)
{
  int v7; // r14d
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-50h]
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF
  void *v21; // [rsp+A8h] [rbp+38h] BYREF

  v21 = a4;
  v7 = (int)a5;
  *a5 = 0;
  v8 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IUpdateCollection *))a2->lpVtbl->put_Updates)(a2, a3);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v20 = 0;
    v10 = Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,IInstallationCompletedCallback,void * &>(
            &v20,
            &v21);
    v9 = v10;
    if ( v10 >= 0 )
    {
      a5 = 0;
      v11 = Microsoft::WRL::Details::MakeAndInitialize<OOBEWUProgressCallback,IInstallationProgressChangedCallback,>(&a5);
      v9 = v11;
      if ( v11 >= 0 )
      {
        AcquireSRWLockShared(this + 4);
        v16 = this + 4;
        v13 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 48LL))(this[5].Ptr, 3);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17B,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
            (const char *)(unsigned int)v13,
            v15);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v18 = pvarg;
        v15 = v7;
        v11 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IInstallationJob **, __int64, VARIANTARG *))a2->lpVtbl->BeginInstall)(
                a2,
                a5,
                v20,
                &v18);
        v9 = v11;
        if ( v11 >= 0 )
        {
          VariantClear(&pvarg);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&a5);
          v9 = 0;
          goto LABEL_13;
        }
        v12 = 384;
      }
      else
      {
        v12 = 375;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v11,
        v15);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&a5);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v10,
        v15);
    }
LABEL_13:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v20);
    return v9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x172,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)v8,
    v15);
  return v9;
}

```

## disassembly

```asm
0x18000ddf4  mov     [rsp-18h+arg_0], rbx
0x18000ddf9  mov     [rsp-18h+arg_10], rsi
0x18000ddfe  mov     [rsp-18h+arg_18], r9
0x18000de03  push    rbp
0x18000de04  push    rdi
0x18000de05  push    r14
0x18000de07  mov     rbp, rsp
0x18000de0a  sub     rsp, 70h
0x18000de0e  mov     rdi, rdx
0x18000de11  mov     rsi, rcx
0x18000de14  mov     r14, [rbp+arg_20]
0x18000de18  mov     qword ptr [r14], 0
0x18000de1f  mov     rax, [rdx]
0x18000de22  mov     rdx, r8
0x18000de25  mov     rcx, rdi
0x18000de28  mov     rax, [rax+80h]
0x18000de2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de34  mov     ebx, eax
0x18000de36  test    eax, eax
0x18000de38  jns     short loc_18000DE57
0x18000de3a  mov     rcx, [rbp+18h]; this
0x18000de3e  mov     r9d, eax; char *
0x18000de41  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000de48  mov     edx, 172h; void *
0x18000de4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de52  jmp     loc_18000DF94
0x18000de57  mov     [rbp+arg_8], 0
0x18000de5f  lea     rdx, [rbp+arg_18]
0x18000de63  lea     rcx, [rbp+arg_8]
0x18000de67  call    ??$MakeAndInitialize@VCOOBEWUCompletionCallback@@UIInstallationCompletedCallback@@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIInstallationCompletedCallback@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,IInstallationCompletedCallback,void * &>(IInstallationCompletedCallback * *,void * &)
0x18000de6c  mov     ebx, eax
0x18000de6e  test    eax, eax
0x18000de70  jns     short loc_18000DE8F
0x18000de72  mov     rcx, [rbp+18h]; this
0x18000de76  mov     r9d, eax; char *
0x18000de79  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000de80  mov     edx, 174h; void *
0x18000de85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de8a  jmp     loc_18000DF8B
0x18000de8f  mov     [rbp+arg_20], 0
0x18000de97  lea     rcx, [rbp+arg_20]
0x18000de9b  call    ??$MakeAndInitialize@VOOBEWUProgressCallback@@UIInstallationProgressChangedCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIInstallationProgressChangedCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OOBEWUProgressCallback,IInstallationProgressChangedCallback,>(IInstallationProgressChangedCallback * *)
0x18000dea0  mov     ebx, eax
0x18000dea2  test    eax, eax
0x18000dea4  jns     short loc_18000DECD
0x18000dea6  mov     edx, 177h; void *
0x18000deab  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000deb2  mov     r9d, eax; char *
0x18000deb5  mov     rcx, [rbp+18h]; this
0x18000deb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000debe  nop
0x18000debf  lea     rcx, [rbp+arg_20]
0x18000dec3  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000dec8  jmp     loc_18000DF8B
0x18000decd  lea     rbx, [rsi+20h]
0x18000ded1  mov     rcx, rbx; SRWLock
0x18000ded4  call    cs:__imp_AcquireSRWLockShared
0x18000deda  mov     [rbp+var_40], rbx
0x18000dede  mov     rcx, [rsi+28h]
0x18000dee2  mov     rax, [rcx]
0x18000dee5  mov     edx, 3
0x18000deea  mov     rax, [rax+30h]
0x18000deee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def3  mov     rcx, [rbp+18h]; this
0x18000def7  test    eax, eax
0x18000def9  jns     short loc_18000DF10
0x18000defb  mov     r9d, eax; char *
0x18000defe  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000df05  mov     edx, 17Bh; void *
0x18000df0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000df0f  nop
0x18000df10  lea     rcx, [rbp+var_40]
0x18000df14  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000df19  xorps   xmm0, xmm0
0x18000df1c  xor     eax, eax
0x18000df1e  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000df22  mov     qword ptr [rbp+pvarg+10h], rax
0x18000df26  lea     rcx, [rbp+pvarg]; pvarg
0x18000df2a  call    cs:__imp_VariantInit
0x18000df30  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000df34  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000df39  movaps  [rbp+var_20], xmm0
0x18000df3d  movsd   [rbp+var_10], xmm1
0x18000df42  mov     rax, [rdi]
0x18000df45  mov     qword ptr [rsp+70h+var_50], r14
0x18000df4a  lea     r9, [rbp+var_20]
0x18000df4e  mov     r8, [rbp+arg_8]
0x18000df52  mov     rdx, [rbp+arg_20]
0x18000df56  mov     rcx, rdi
0x18000df59  mov     rax, [rax+88h]
0x18000df60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df65  mov     ebx, eax
0x18000df67  test    eax, eax
0x18000df69  jns     short loc_18000DF75
0x18000df6b  mov     edx, 180h
0x18000df70  jmp     loc_18000DEAB
0x18000df75  lea     rcx, [rbp+pvarg]; pvarg
0x18000df79  call    cs:__imp_VariantClear
0x18000df7f  nop
0x18000df80  lea     rcx, [rbp+arg_20]
0x18000df84  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000df89  xor     ebx, ebx
0x18000df8b  lea     rcx, [rbp+arg_8]
0x18000df8f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000df94  mov     eax, ebx
0x18000df96  lea     r11, [rsp+70h+var_s0]
0x18000df9b  mov     rbx, [r11+20h]
0x18000df9f  mov     rsi, [r11+30h]
0x18000dfa3  mov     rsp, r11
0x18000dfa6  pop     r14
0x18000dfa8  pop     rdi
0x18000dfa9  pop     rbp
0x18000dfaa  retn
```
