# OobeZdpElevatedManagerCore::BeginAsyncDownload(IUpdateDownloader *,IUpdateCollection *,void *,IDownloadJob * *)

- ea: `0x18000dbb0`
- end: `0x18000dded`
- name: `?BeginAsyncDownload@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateDownloader@@PEAUIUpdateCollection@@PEAXPEAPEAUIDownloadJob@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateDownloader *, struct IUpdateCollection *, void *, struct IDownloadJob **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e4e4`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000b098`
- `0x18000c384`
- `0x18000c63c`
- `0x18000d684`
- `0x18000dbb0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dd18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dd18`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd6e`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd6e`
- `OLEAUT32!__imp_VariantClear` at `0x18000ddba`
- `OLEAUT32!__imp_VariantClear` at `0x18000ddba`

## string_xrefs

- `0x18000dbf9`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000dc80`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000dcbd`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000dcef`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000dd42`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OobeZdpElevatedManagerCore::BeginAsyncDownload(
        RTL_SRWLOCK *this,
        struct IUpdateDownloader *a2,
        struct IUpdateCollection *a3,
        void *a4,
        struct IDownloadJob **a5)
{
  int v7; // r15d
  int v8; // ebx
  __int64 v9; // rdx
  struct IUpdateDownloaderVtbl *lpVtbl; // rax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-50h]
  __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v21; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  RTL_SRWLOCK *v23; // [rsp+98h] [rbp+28h] BYREF
  void *v24; // [rsp+A8h] [rbp+38h] BYREF

  v24 = a4;
  v7 = (int)a5;
  *a5 = 0;
  v8 = ((__int64 (__fastcall *)(struct IUpdateDownloader *, struct IUpdateCollection *))a2->lpVtbl->put_Updates)(a2, a3);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IUpdateDownloader *, __int64))a2->lpVtbl->put_Priority)(a2, 3);
    if ( v8 < 0 )
    {
      v9 = 245;
      goto LABEL_3;
    }
    lpVtbl = a2->lpVtbl;
    v23 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUpdateDownloader *, GUID *, RTL_SRWLOCK **))lpVtbl->QueryInterface)(
            a2,
            &GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d,
            &v23);
    if ( v11 >= 0 )
    {
      v11 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64))v23->Ptr + 18))(v23, 0xFFFFFFFFLL);
      if ( v11 >= 0 )
        goto LABEL_11;
      v12 = 236;
    }
    else
    {
      v12 = 233;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v11,
      v18);
LABEL_11:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v23);
    v19 = 0;
    v13 = Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,IDownloadCompletedCallback,void * &>(
            &v19,
            &v24);
    v8 = v13;
    if ( v13 >= 0 )
    {
      a5 = 0;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<OOBEWUProgressCallback,IDownloadProgressChangedCallback,>(&a5);
      v8 = v14;
      if ( v14 >= 0 )
      {
        AcquireSRWLockShared(this + 4);
        v23 = this + 4;
        v16 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 48LL))(this[5].Ptr, 2);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x101,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
            (const char *)(unsigned int)v16,
            v18);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v21 = pvarg;
        v18 = v7;
        v14 = ((__int64 (__fastcall *)(struct IUpdateDownloader *, struct IDownloadJob **, __int64, VARIANTARG *))a2->lpVtbl->BeginDownload)(
                a2,
                a5,
                v19,
                &v21);
        v8 = v14;
        if ( v14 >= 0 )
        {
          VariantClear(&pvarg);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&a5);
          v8 = 0;
          goto LABEL_21;
        }
        v15 = 262;
      }
      else
      {
        v15 = 253;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v14,
        v18);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&a5);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v13,
        v18);
    }
LABEL_21:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v19);
    return (unsigned int)v8;
  }
  v9 = 244;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)v8,
    v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000dbb0  mov     [rsp-18h+arg_0], rbx
0x18000dbb5  mov     [rsp-18h+arg_10], rsi
0x18000dbba  mov     [rsp-18h+arg_18], r9
0x18000dbbf  push    rbp
0x18000dbc0  push    r14
0x18000dbc2  push    r15
0x18000dbc4  mov     rbp, rsp
0x18000dbc7  sub     rsp, 70h
0x18000dbcb  mov     rsi, rdx
0x18000dbce  mov     r14, rcx
0x18000dbd1  mov     r15, [rbp+arg_20]
0x18000dbd5  mov     qword ptr [r15], 0
0x18000dbdc  mov     rax, [rdx]
0x18000dbdf  mov     rdx, r8
0x18000dbe2  mov     rcx, rsi
0x18000dbe5  mov     rax, [rax+70h]
0x18000dbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbee  mov     ebx, eax
0x18000dbf0  test    eax, eax
0x18000dbf2  jns     short loc_18000DC11
0x18000dbf4  mov     edx, 0F4h; void *
0x18000dbf9  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000dc00  mov     r9d, ebx; char *
0x18000dc03  mov     rcx, [rbp+18h]; this
0x18000dc07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc0c  jmp     loc_18000DDD5
0x18000dc11  mov     rax, [rsi]
0x18000dc14  mov     edx, 3
0x18000dc19  mov     rcx, rsi
0x18000dc1c  mov     rax, [rax+60h]
0x18000dc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc25  mov     ebx, eax
0x18000dc27  test    eax, eax
0x18000dc29  jns     short loc_18000DC32
0x18000dc2b  mov     edx, 0F5h
0x18000dc30  jmp     short loc_18000DBF9
0x18000dc32  mov     rax, [rsi]
0x18000dc35  mov     [rbp+arg_8], 0
0x18000dc3d  lea     r8, [rbp+arg_8]
0x18000dc41  lea     rdx, _GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d
0x18000dc48  mov     rcx, rsi
0x18000dc4b  mov     rax, [rax]
0x18000dc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc53  test    eax, eax
0x18000dc55  jns     short loc_18000DC5E
0x18000dc57  mov     edx, 0E9h
0x18000dc5c  jmp     short loc_18000DC7D
0x18000dc5e  mov     rcx, [rbp+arg_8]
0x18000dc62  mov     rax, [rcx]
0x18000dc65  or      edx, 0FFFFFFFFh
0x18000dc68  mov     rax, [rax+90h]
0x18000dc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc74  test    eax, eax
0x18000dc76  jns     short loc_18000DC91
0x18000dc78  mov     edx, 0ECh; void *
0x18000dc7d  mov     r9d, eax; char *
0x18000dc80  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000dc87  mov     rcx, [rbp+18h]; this
0x18000dc8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc90  nop
0x18000dc91  lea     rcx, [rbp+arg_8]
0x18000dc95  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000dc9a  nop
0x18000dc9b  mov     [rbp+var_40], 0
0x18000dca3  lea     rdx, [rbp+arg_18]
0x18000dca7  lea     rcx, [rbp+var_40]
0x18000dcab  call    ??$MakeAndInitialize@VCOOBEWUCompletionCallback@@UIDownloadCompletedCallback@@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIDownloadCompletedCallback@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,IDownloadCompletedCallback,void * &>(IDownloadCompletedCallback * *,void * &)
0x18000dcb0  mov     ebx, eax
0x18000dcb2  test    eax, eax
0x18000dcb4  jns     short loc_18000DCD3
0x18000dcb6  mov     rcx, [rbp+18h]; this
0x18000dcba  mov     r9d, eax; char *
0x18000dcbd  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000dcc4  mov     edx, 0FAh; void *
0x18000dcc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcce  jmp     loc_18000DDCC
0x18000dcd3  mov     [rbp+arg_20], 0
0x18000dcdb  lea     rcx, [rbp+arg_20]
0x18000dcdf  call    ??$MakeAndInitialize@VOOBEWUProgressCallback@@UIDownloadProgressChangedCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIDownloadProgressChangedCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OOBEWUProgressCallback,IDownloadProgressChangedCallback,>(IDownloadProgressChangedCallback * *)
0x18000dce4  mov     ebx, eax
0x18000dce6  test    eax, eax
0x18000dce8  jns     short loc_18000DD11
0x18000dcea  mov     edx, 0FDh; void *
0x18000dcef  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000dcf6  mov     r9d, eax; char *
0x18000dcf9  mov     rcx, [rbp+18h]; this
0x18000dcfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd02  nop
0x18000dd03  lea     rcx, [rbp+arg_20]
0x18000dd07  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000dd0c  jmp     loc_18000DDCC
0x18000dd11  lea     rbx, [r14+20h]
0x18000dd15  mov     rcx, rbx; SRWLock
0x18000dd18  call    cs:__imp_AcquireSRWLockShared
0x18000dd1e  mov     [rbp+arg_8], rbx
0x18000dd22  mov     rcx, [r14+28h]
0x18000dd26  mov     rax, [rcx]
0x18000dd29  mov     edx, 2
0x18000dd2e  mov     rax, [rax+30h]
0x18000dd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd37  mov     rcx, [rbp+18h]; this
0x18000dd3b  test    eax, eax
0x18000dd3d  jns     short loc_18000DD54
0x18000dd3f  mov     r9d, eax; char *
0x18000dd42  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000dd49  mov     edx, 101h; void *
0x18000dd4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd53  nop
0x18000dd54  lea     rcx, [rbp+arg_8]
0x18000dd58  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000dd5d  xorps   xmm0, xmm0
0x18000dd60  xor     eax, eax
0x18000dd62  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000dd66  mov     qword ptr [rbp+pvarg+10h], rax
0x18000dd6a  lea     rcx, [rbp+pvarg]; pvarg
0x18000dd6e  call    cs:__imp_VariantInit
0x18000dd74  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000dd78  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000dd7d  movaps  [rbp+var_20], xmm0
0x18000dd81  movsd   [rbp+var_10], xmm1
0x18000dd86  mov     rax, [rsi]
0x18000dd89  mov     qword ptr [rsp+70h+var_50], r15
0x18000dd8e  lea     r9, [rbp+var_20]
0x18000dd92  mov     r8, [rbp+var_40]
0x18000dd96  mov     rdx, [rbp+arg_20]
0x18000dd9a  mov     rcx, rsi
0x18000dd9d  mov     rax, [rax+78h]
0x18000dda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda6  mov     ebx, eax
0x18000dda8  test    eax, eax
0x18000ddaa  jns     short loc_18000DDB6
0x18000ddac  mov     edx, 106h
0x18000ddb1  jmp     loc_18000DCEF
0x18000ddb6  lea     rcx, [rbp+pvarg]; pvarg
0x18000ddba  call    cs:__imp_VariantClear
0x18000ddc0  nop
0x18000ddc1  lea     rcx, [rbp+arg_20]
0x18000ddc5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000ddca  xor     ebx, ebx
0x18000ddcc  lea     rcx, [rbp+var_40]
0x18000ddd0  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000ddd5  mov     eax, ebx
0x18000ddd7  lea     r11, [rsp+70h+var_s0]
0x18000dddc  mov     rbx, [r11+20h]
0x18000dde0  mov     rsi, [r11+30h]
0x18000dde4  mov     rsp, r11
0x18000dde7  pop     r15
0x18000dde9  pop     r14
0x18000ddeb  pop     rbp
0x18000ddec  retn
```
