# OobeZdpElevatedManagerCore::Download(IUpdateSession *,IUpdateCollection *)

- ea: `0x18000e4e4`
- end: `0x18000e869`
- name: `?Download@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z`
- size: `901`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateSession *, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000dbb0`
- `0x18000e4e4`
- `0x18000f3c0`
- `0x18000f794`
- `0x180010134`
- `0x1800103a0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e54c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e54c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e5c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e657`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e6e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e76a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e83f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e5c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e657`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e6e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e76a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e822`

## string_xrefs

- `0x18000e527`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e570`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e5f8`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e70b`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e78b`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OobeZdpElevatedManagerCore::Download(
        OobeZdpElevatedManagerCore *this,
        struct IUpdateSession *a2,
        struct IUpdateCollection *a3)
{
  struct IUpdateSessionVtbl *lpVtbl; // rax
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE EventW; // rax
  int LastError; // eax
  int v10; // eax
  int v11; // eax
  HWND v12; // rcx
  unsigned int v13; // eax
  OobeZdpElevatedManagerCore *v14; // rcx
  int v15; // eax
  int Error; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v21; // eax
  int v22; // [rsp+20h] [rbp-30h]
  unsigned int v23; // [rsp+20h] [rbp-30h]
  int v24; // [rsp+20h] [rbp-30h]
  unsigned int v25; // [rsp+28h] [rbp-28h]
  struct IUpdateDownloader *v26; // [rsp+30h] [rbp-20h] BYREF
  void *v27; // [rsp+38h] [rbp-18h] BYREF
  void **v28; // [rsp+40h] [rbp-10h] BYREF
  void *v29; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v31; // [rsp+88h] [rbp+38h] BYREF
  struct IDownloadJob *v32; // [rsp+98h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUpdateSession *, struct IUpdateDownloader **))lpVtbl->CreateUpdateDownloader)(
         a2,
         &v26);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v6,
      v22);
LABEL_37:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
    return v7;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v29 = EventW;
  v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !EventW )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)0x8000FFFFLL,
      v22);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_23;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
LABEL_22:
      v29 = 0;
      goto LABEL_23;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  v32 = 0;
  v10 = OobeZdpElevatedManagerCore::BeginAsyncDownload(this, v26, a3, EventW, &v32);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v10,
      v23);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_37;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
      goto LABEL_36;
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    RaiseException(v11, 1u, 0, 0);
  }
  v31 = 0;
  ((void (__fastcall *)(struct IUpdateCollection *, int *))a3->lpVtbl->get_Count)(a3, &v31);
  v27 = v29;
  v13 = SHProcessMessagesUntilEventsEx(v12, &v27, 1u, 0xFFFFFFFF, v23, v25);
  if ( !v13 )
    goto LABEL_30;
  if ( v13 != -1 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( v29 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        RaiseException(v15, 1u, 0, 0);
        __debugbreak();
      }
      goto LABEL_22;
    }
LABEL_23:
    v7 = -2147418113;
    goto LABEL_37;
  }
  Error = ResultFromKnownLastError();
  v7 = Error;
  if ( Error >= 0 )
    goto LABEL_38;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD7,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)Error,
    v24);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
  v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !v29 )
    goto LABEL_37;
  if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
  {
LABEL_36:
    v29 = 0;
    goto LABEL_37;
  }
  v17 = GetLastError();
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  RaiseException(v17, 1u, 0, 0);
LABEL_30:
  v18 = OobeZdpElevatedManagerCore::OnDownloadCompleted(v14, v26, v32);
  v7 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v18,
      v24);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_37;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      RaiseException(v19, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_36;
  }
LABEL_38:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v32);
  v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( v29 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      RaiseException(v21, 1u, 0, 0);
      __debugbreak();
    }
    v29 = 0;
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v26);
  return 0;
}

```

## disassembly

```asm
0x18000e4e4  mov     [rsp-28h+arg_0], rbx
0x18000e4e9  push    rbp
0x18000e4ea  push    rsi
0x18000e4eb  push    rdi
0x18000e4ec  push    r14
0x18000e4ee  push    r15
0x18000e4f0  mov     rbp, rsp
0x18000e4f3  sub     rsp, 50h
0x18000e4f7  mov     rdi, r8
0x18000e4fa  mov     r9, rdx
0x18000e4fd  mov     rsi, rcx
0x18000e500  mov     rax, [rdx]
0x18000e503  xor     r14d, r14d
0x18000e506  mov     [rbp+var_20], r14
0x18000e50a  lea     rdx, [rbp+var_20]
0x18000e50e  mov     rcx, r9
0x18000e511  mov     rax, [rax+68h]
0x18000e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51a  mov     ebx, eax
0x18000e51c  test    eax, eax
0x18000e51e  jns     short loc_18000E53D
0x18000e520  mov     rcx, [rbp+28h]; this
0x18000e524  mov     r9d, eax; char *
0x18000e527  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e52e  mov     edx, 0C7h; void *
0x18000e533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e538  jmp     loc_18000E7ED
0x18000e53d  xor     r9d, r9d; lpName
0x18000e540  xor     r8d, r8d; bInitialState
0x18000e543  lea     r15d, [r9+1]
0x18000e547  mov     edx, r15d; bManualReset
0x18000e54a  xor     ecx, ecx; lpEventAttributes
0x18000e54c  call    cs:__imp_CreateEventW
0x18000e552  mov     [rbp+var_8], rax
0x18000e556  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e55d  mov     [rbp+var_10], rcx
0x18000e561  test    rax, rax
0x18000e564  jnz     short loc_18000E5CC
0x18000e566  mov     rcx, [rbp+28h]; this
0x18000e56a  mov     r9d, 8000FFFFh; char *
0x18000e570  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e577  mov     edx, 0CAh; void *
0x18000e57c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e581  nop
0x18000e582  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e589  mov     [rbp+var_10], rax
0x18000e58d  cmp     [rbp+var_8], r14
0x18000e591  jz      loc_18000E6EB
0x18000e597  lea     rcx, [rbp+var_10]
0x18000e59b  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e5a0  test    al, al
0x18000e5a2  jnz     loc_18000E6E7
0x18000e5a8  call    cs:__imp_GetLastError
0x18000e5ae  test    eax, eax
0x18000e5b0  jle     short loc_18000E5BA
0x18000e5b2  movzx   eax, ax
0x18000e5b5  or      eax, 80070000h
0x18000e5ba  xor     r9d, r9d; lpArguments
0x18000e5bd  xor     r8d, r8d; nNumberOfArguments
0x18000e5c0  mov     edx, r15d; dwExceptionFlags
0x18000e5c3  mov     ecx, eax; dwExceptionCode
0x18000e5c5  call    cs:__imp_RaiseException
0x18000e5cb  nop
0x18000e5cc  mov     [rbp+arg_18], r14
0x18000e5d0  lea     rcx, [rbp+arg_18]
0x18000e5d4  mov     [rsp+50h+var_30], rcx; int
0x18000e5d9  mov     r9, rax; void *
0x18000e5dc  mov     r8, rdi; struct IUpdateCollection *
0x18000e5df  mov     rdx, [rbp+var_20]; struct IUpdateDownloader *
0x18000e5e3  mov     rcx, rsi; this
0x18000e5e6  call    ?BeginAsyncDownload@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateDownloader@@PEAUIUpdateCollection@@PEAXPEAPEAUIDownloadJob@@@Z; OobeZdpElevatedManagerCore::BeginAsyncDownload(IUpdateDownloader *,IUpdateCollection *,void *,IDownloadJob * *)
0x18000e5eb  mov     ebx, eax
0x18000e5ed  test    eax, eax
0x18000e5ef  jns     short loc_18000E65E
0x18000e5f1  mov     rcx, [rbp+28h]; this
0x18000e5f5  mov     r9d, eax; char *
0x18000e5f8  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e5ff  mov     edx, 0CDh; void *
0x18000e604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e609  nop
0x18000e60a  lea     rcx, [rbp+arg_18]
0x18000e60e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e613  nop
0x18000e614  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e61b  mov     [rbp+var_10], rax
0x18000e61f  cmp     [rbp+var_8], r14
0x18000e623  jz      loc_18000E7ED
0x18000e629  lea     rcx, [rbp+var_10]
0x18000e62d  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e632  test    al, al
0x18000e634  jnz     loc_18000E7E9
0x18000e63a  call    cs:__imp_GetLastError
0x18000e640  test    eax, eax
0x18000e642  jle     short loc_18000E64C
0x18000e644  movzx   eax, ax
0x18000e647  or      eax, 80070000h
0x18000e64c  xor     r9d, r9d; lpArguments
0x18000e64f  xor     r8d, r8d; nNumberOfArguments
0x18000e652  mov     edx, r15d; dwExceptionFlags
0x18000e655  mov     ecx, eax; dwExceptionCode
0x18000e657  call    cs:__imp_RaiseException
0x18000e65d  nop
0x18000e65e  mov     [rbp+arg_8], r14d
0x18000e662  mov     rax, [rdi]
0x18000e665  lea     rdx, [rbp+arg_8]
0x18000e669  mov     rcx, rdi
0x18000e66c  mov     rax, [rax+50h]
0x18000e670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e675  mov     rax, [rbp+var_8]
0x18000e679  mov     [rbp+var_18], rax
0x18000e67d  or      ebx, 0FFFFFFFFh
0x18000e680  mov     r9d, ebx; unsigned int
0x18000e683  mov     r8d, r15d; unsigned int
0x18000e686  lea     rdx, [rbp+var_18]; void **
0x18000e68a  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18000e68f  test    eax, eax
0x18000e691  jz      loc_18000E771
0x18000e697  cmp     eax, ebx
0x18000e699  jz      short loc_18000E6F5
0x18000e69b  lea     rcx, [rbp+arg_18]
0x18000e69f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e6a4  nop
0x18000e6a5  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e6ac  mov     [rbp+var_10], rax
0x18000e6b0  cmp     [rbp+var_8], r14
0x18000e6b4  jz      short loc_18000E6EB
0x18000e6b6  lea     rcx, [rbp+var_10]
0x18000e6ba  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e6bf  test    al, al
0x18000e6c1  jnz     short loc_18000E6E7
0x18000e6c3  call    cs:__imp_GetLastError
0x18000e6c9  test    eax, eax
0x18000e6cb  jle     short loc_18000E6D5
0x18000e6cd  movzx   eax, ax
0x18000e6d0  or      eax, 80070000h
0x18000e6d5  xor     r9d, r9d; lpArguments
0x18000e6d8  xor     r8d, r8d; nNumberOfArguments
0x18000e6db  mov     edx, r15d; dwExceptionFlags
0x18000e6de  mov     ecx, eax; dwExceptionCode
0x18000e6e0  call    cs:__imp_RaiseException
0x18000e6e6  int     3; Trap to Debugger
0x18000e6e7  mov     [rbp+var_8], r14
0x18000e6eb  mov     ebx, 8000FFFFh
0x18000e6f0  jmp     loc_18000E7ED
0x18000e6f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000e6fa  mov     ebx, eax
0x18000e6fc  test    eax, eax
0x18000e6fe  jns     loc_18000E7FA
0x18000e704  mov     rcx, [rbp+28h]; this
0x18000e708  mov     r9d, eax; char *
0x18000e70b  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e712  mov     edx, 0D7h; void *
0x18000e717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e71c  nop
0x18000e71d  lea     rcx, [rbp+arg_18]
0x18000e721  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e726  nop
0x18000e727  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e72e  mov     [rbp+var_10], rax
0x18000e732  cmp     [rbp+var_8], r14
0x18000e736  jz      loc_18000E7ED
0x18000e73c  lea     rcx, [rbp+var_10]
0x18000e740  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e745  test    al, al
0x18000e747  jnz     loc_18000E7E9
0x18000e74d  call    cs:__imp_GetLastError
0x18000e753  test    eax, eax
0x18000e755  jle     short loc_18000E75F
0x18000e757  movzx   eax, ax
0x18000e75a  or      eax, 80070000h
0x18000e75f  xor     r9d, r9d; lpArguments
0x18000e762  xor     r8d, r8d; nNumberOfArguments
0x18000e765  mov     edx, r15d; dwExceptionFlags
0x18000e768  mov     ecx, eax; dwExceptionCode
0x18000e76a  call    cs:__imp_RaiseException
0x18000e770  nop
0x18000e771  mov     r8, [rbp+arg_18]; struct IDownloadJob *
0x18000e775  mov     rdx, [rbp+var_20]; struct IUpdateDownloader *
0x18000e779  call    ?OnDownloadCompleted@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateDownloader@@PEAUIDownloadJob@@@Z; OobeZdpElevatedManagerCore::OnDownloadCompleted(IUpdateDownloader *,IDownloadJob *)
0x18000e77e  mov     ebx, eax
0x18000e780  test    eax, eax
0x18000e782  jns     short loc_18000E7FA
0x18000e784  mov     rcx, [rbp+28h]; this
0x18000e788  mov     r9d, eax; char *
0x18000e78b  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e792  mov     edx, 0DBh; void *
0x18000e797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e79c  nop
0x18000e79d  lea     rcx, [rbp+arg_18]
0x18000e7a1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e7a6  nop
0x18000e7a7  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e7ae  mov     [rbp+var_10], rax
0x18000e7b2  cmp     [rbp+var_8], r14
0x18000e7b6  jz      short loc_18000E7ED
0x18000e7b8  lea     rcx, [rbp+var_10]
0x18000e7bc  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e7c1  test    al, al
0x18000e7c3  jnz     short loc_18000E7E9
0x18000e7c5  call    cs:__imp_GetLastError
0x18000e7cb  test    eax, eax
0x18000e7cd  jle     short loc_18000E7D7
0x18000e7cf  movzx   eax, ax
0x18000e7d2  or      eax, 80070000h
0x18000e7d7  xor     r9d, r9d; lpArguments
0x18000e7da  xor     r8d, r8d; nNumberOfArguments
0x18000e7dd  mov     edx, r15d; dwExceptionFlags
0x18000e7e0  mov     ecx, eax; dwExceptionCode
0x18000e7e2  call    cs:__imp_RaiseException
0x18000e7e8  int     3; Trap to Debugger
0x18000e7e9  mov     [rbp+var_8], r14
0x18000e7ed  lea     rcx, [rbp+var_20]
0x18000e7f1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e7f6  mov     eax, ebx
0x18000e7f8  jmp     short loc_18000E855
0x18000e7fa  lea     rcx, [rbp+arg_18]
0x18000e7fe  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e803  nop
0x18000e804  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000e80b  mov     [rbp+var_10], rax
0x18000e80f  cmp     [rbp+var_8], r14
0x18000e813  jz      short loc_18000E84A
0x18000e815  lea     rcx, [rbp+var_10]
0x18000e819  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000e81e  test    al, al
0x18000e820  jnz     short loc_18000E846
0x18000e822  call    cs:__imp_GetLastError
0x18000e828  test    eax, eax
0x18000e82a  jle     short loc_18000E834
0x18000e82c  movzx   eax, ax
0x18000e82f  or      eax, 80070000h
0x18000e834  xor     r9d, r9d; lpArguments
0x18000e837  xor     r8d, r8d; nNumberOfArguments
0x18000e83a  mov     edx, r15d; dwExceptionFlags
0x18000e83d  mov     ecx, eax; dwExceptionCode
0x18000e83f  call    cs:__imp_RaiseException
0x18000e845  int     3; Trap to Debugger
0x18000e846  mov     [rbp+var_8], r14
0x18000e84a  lea     rcx, [rbp+var_20]
0x18000e84e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e853  xor     eax, eax
0x18000e855  mov     rbx, [rsp+50h+arg_0]
0x18000e85d  add     rsp, 50h
0x18000e861  pop     r15
0x18000e863  pop     r14
0x18000e865  pop     rdi
0x18000e866  pop     rsi
0x18000e867  pop     rbp
0x18000e868  retn
```
