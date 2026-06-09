# OobeZdpElevatedManagerCore::Install(IUpdateSession *,IUpdateCollection *)

- ea: `0x18000f044`
- end: `0x18000f3b5`
- name: `?Install@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateSession *, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000ddf4`
- `0x18000f044`
- `0x18000f3c0`
- `0x18000f880`
- `0x180010134`
- `0x1800103a0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f0ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f0ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f125`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f1b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f229`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f2b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f32e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f38b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f125`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f1b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f229`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f2b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f32e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f38b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f20c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f20c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f36e`

## string_xrefs

- `0x18000f087`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000f0d0`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000f158`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000f254`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000f2d7`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OobeZdpElevatedManagerCore::Install(
        OobeZdpElevatedManagerCore *this,
        struct IUpdateSession *a2,
        struct IUpdateCollection *a3)
{
  struct IUpdateSessionVtbl *lpVtbl; // rax
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE EventW; // rax
  int v9; // eax
  HWND v10; // rcx
  int LastError; // eax
  unsigned int v12; // eax
  int v13; // eax
  int Error; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v19; // eax
  int v20; // [rsp+20h] [rbp-30h]
  unsigned int v21; // [rsp+20h] [rbp-30h]
  int v22; // [rsp+20h] [rbp-30h]
  unsigned int v23; // [rsp+28h] [rbp-28h]
  void *v24; // [rsp+30h] [rbp-20h] BYREF
  void **v25; // [rsp+38h] [rbp-18h] BYREF
  void *v26; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct IInstallationJob *v28; // [rsp+88h] [rbp+38h] BYREF
  struct IUpdateInstaller *v29; // [rsp+98h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v29 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUpdateSession *, struct IUpdateInstaller **))lpVtbl->CreateUpdateInstaller)(
         a2,
         &v29);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_33:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v29);
    return v7;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v26 = EventW;
  v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !EventW )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)0x8000FFFFLL,
      v20);
    v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
LABEL_19:
    v7 = -2147418113;
    goto LABEL_33;
  }
  v28 = 0;
  v9 = OobeZdpElevatedManagerCore::BeginAsyncInstall(this, v29, a3, EventW, &v28);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v9,
      v21);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
    v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v26 )
      goto LABEL_33;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v25) )
      goto LABEL_32;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  v24 = v26;
  v12 = SHProcessMessagesUntilEventsEx(v10, &v24, 1u, 0xFFFFFFFF, v21, v23);
  if ( !v12 )
    goto LABEL_26;
  if ( v12 != -1 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
    v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( v26 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v25) )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        RaiseException(v13, 1u, 0, 0);
        __debugbreak();
      }
      v26 = 0;
    }
    goto LABEL_19;
  }
  Error = ResultFromKnownLastError();
  v7 = Error;
  if ( Error >= 0 )
    goto LABEL_34;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1DB,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)Error,
    v22);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
  v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !v26 )
    goto LABEL_33;
  if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v25) )
  {
LABEL_32:
    v26 = 0;
    goto LABEL_33;
  }
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  RaiseException(v15, 1u, 0, 0);
LABEL_26:
  v16 = OobeZdpElevatedManagerCore::OnInstallCompleted(this, v29, v28);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v16,
      v22);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
    v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v26 )
      goto LABEL_33;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v25) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      RaiseException(v17, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_32;
  }
LABEL_34:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v28);
  v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( v26 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v25) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      RaiseException(v19, 1u, 0, 0);
      __debugbreak();
    }
    v26 = 0;
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v29);
  return 0;
}

```

## disassembly

```asm
0x18000f044  mov     [rsp-28h+arg_0], rbx
0x18000f049  push    rbp
0x18000f04a  push    rsi
0x18000f04b  push    rdi
0x18000f04c  push    r14
0x18000f04e  push    r15
0x18000f050  mov     rbp, rsp
0x18000f053  sub     rsp, 50h
0x18000f057  mov     rsi, r8
0x18000f05a  mov     r9, rdx
0x18000f05d  mov     rdi, rcx
0x18000f060  mov     rax, [rdx]
0x18000f063  xor     r14d, r14d
0x18000f066  mov     [rbp+arg_18], r14
0x18000f06a  lea     rdx, [rbp+arg_18]
0x18000f06e  mov     rcx, r9
0x18000f071  mov     rax, [rax+70h]
0x18000f075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07a  mov     ebx, eax
0x18000f07c  test    eax, eax
0x18000f07e  jns     short loc_18000F09D
0x18000f080  mov     rcx, [rbp+28h]; this
0x18000f084  mov     r9d, eax; char *
0x18000f087  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f08e  mov     edx, 1CAh; void *
0x18000f093  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f098  jmp     loc_18000F339
0x18000f09d  xor     r9d, r9d; lpName
0x18000f0a0  xor     r8d, r8d; bInitialState
0x18000f0a3  lea     r15d, [r9+1]
0x18000f0a7  mov     edx, r15d; bManualReset
0x18000f0aa  xor     ecx, ecx; lpEventAttributes
0x18000f0ac  call    cs:__imp_CreateEventW
0x18000f0b2  mov     [rbp+var_10], rax
0x18000f0b6  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f0bd  mov     [rbp+var_18], rcx
0x18000f0c1  test    rax, rax
0x18000f0c4  jnz     short loc_18000F12C
0x18000f0c6  mov     rcx, [rbp+28h]; this
0x18000f0ca  mov     r9d, 8000FFFFh; char *
0x18000f0d0  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f0d7  mov     edx, 1CDh; void *
0x18000f0dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f0e1  nop
0x18000f0e2  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f0e9  mov     [rbp+var_18], rax
0x18000f0ed  cmp     [rbp+var_10], r14
0x18000f0f1  jz      loc_18000F234
0x18000f0f7  lea     rcx, [rbp+var_18]
0x18000f0fb  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f100  test    al, al
0x18000f102  jnz     loc_18000F230
0x18000f108  call    cs:__imp_GetLastError
0x18000f10e  test    eax, eax
0x18000f110  jle     short loc_18000F11A
0x18000f112  movzx   eax, ax
0x18000f115  or      eax, 80070000h
0x18000f11a  xor     r9d, r9d; lpArguments
0x18000f11d  xor     r8d, r8d; nNumberOfArguments
0x18000f120  mov     edx, r15d; dwExceptionFlags
0x18000f123  mov     ecx, eax; dwExceptionCode
0x18000f125  call    cs:__imp_RaiseException
0x18000f12b  nop
0x18000f12c  mov     [rbp+arg_8], r14
0x18000f130  lea     rcx, [rbp+arg_8]
0x18000f134  mov     [rsp+50h+var_30], rcx; int
0x18000f139  mov     r9, rax; void *
0x18000f13c  mov     r8, rsi; struct IUpdateCollection *
0x18000f13f  mov     rdx, [rbp+arg_18]; struct IUpdateInstaller *
0x18000f143  mov     rcx, rdi; this
0x18000f146  call    ?BeginAsyncInstall@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateInstaller@@PEAUIUpdateCollection@@PEAXPEAPEAUIInstallationJob@@@Z; OobeZdpElevatedManagerCore::BeginAsyncInstall(IUpdateInstaller *,IUpdateCollection *,void *,IInstallationJob * *)
0x18000f14b  mov     ebx, eax
0x18000f14d  test    eax, eax
0x18000f14f  jns     short loc_18000F1BE
0x18000f151  mov     rcx, [rbp+28h]; this
0x18000f155  mov     r9d, eax; char *
0x18000f158  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f15f  mov     edx, 1D0h; void *
0x18000f164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f169  nop
0x18000f16a  lea     rcx, [rbp+arg_8]
0x18000f16e  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f173  nop
0x18000f174  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f17b  mov     [rbp+var_18], rax
0x18000f17f  cmp     [rbp+var_10], r14
0x18000f183  jz      loc_18000F339
0x18000f189  lea     rcx, [rbp+var_18]
0x18000f18d  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f192  test    al, al
0x18000f194  jnz     loc_18000F335
0x18000f19a  call    cs:__imp_GetLastError
0x18000f1a0  test    eax, eax
0x18000f1a2  jle     short loc_18000F1AC
0x18000f1a4  movzx   eax, ax
0x18000f1a7  or      eax, 80070000h
0x18000f1ac  xor     r9d, r9d; lpArguments
0x18000f1af  xor     r8d, r8d; nNumberOfArguments
0x18000f1b2  mov     edx, r15d; dwExceptionFlags
0x18000f1b5  mov     ecx, eax; dwExceptionCode
0x18000f1b7  call    cs:__imp_RaiseException
0x18000f1bd  nop
0x18000f1be  mov     rax, [rbp+var_10]
0x18000f1c2  mov     [rbp+var_20], rax
0x18000f1c6  or      ebx, 0FFFFFFFFh
0x18000f1c9  mov     r9d, ebx; unsigned int
0x18000f1cc  mov     r8d, r15d; unsigned int
0x18000f1cf  lea     rdx, [rbp+var_20]; void **
0x18000f1d3  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18000f1d8  test    eax, eax
0x18000f1da  jz      loc_18000F2BA
0x18000f1e0  cmp     eax, ebx
0x18000f1e2  jz      short loc_18000F23E
0x18000f1e4  lea     rcx, [rbp+arg_8]
0x18000f1e8  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f1ed  nop
0x18000f1ee  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f1f5  mov     [rbp+var_18], rax
0x18000f1f9  cmp     [rbp+var_10], r14
0x18000f1fd  jz      short loc_18000F234
0x18000f1ff  lea     rcx, [rbp+var_18]
0x18000f203  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f208  test    al, al
0x18000f20a  jnz     short loc_18000F230
0x18000f20c  call    cs:__imp_GetLastError
0x18000f212  test    eax, eax
0x18000f214  jle     short loc_18000F21E
0x18000f216  movzx   eax, ax
0x18000f219  or      eax, 80070000h
0x18000f21e  xor     r9d, r9d; lpArguments
0x18000f221  xor     r8d, r8d; nNumberOfArguments
0x18000f224  mov     edx, r15d; dwExceptionFlags
0x18000f227  mov     ecx, eax; dwExceptionCode
0x18000f229  call    cs:__imp_RaiseException
0x18000f22f  int     3; Trap to Debugger
0x18000f230  mov     [rbp+var_10], r14
0x18000f234  mov     ebx, 8000FFFFh
0x18000f239  jmp     loc_18000F339
0x18000f23e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f243  mov     ebx, eax
0x18000f245  test    eax, eax
0x18000f247  jns     loc_18000F346
0x18000f24d  mov     rcx, [rbp+28h]; this
0x18000f251  mov     r9d, eax; char *
0x18000f254  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f25b  mov     edx, 1DBh; void *
0x18000f260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f265  nop
0x18000f266  lea     rcx, [rbp+arg_8]
0x18000f26a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f26f  nop
0x18000f270  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f277  mov     [rbp+var_18], rax
0x18000f27b  cmp     [rbp+var_10], r14
0x18000f27f  jz      loc_18000F339
0x18000f285  lea     rcx, [rbp+var_18]
0x18000f289  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f28e  test    al, al
0x18000f290  jnz     loc_18000F335
0x18000f296  call    cs:__imp_GetLastError
0x18000f29c  test    eax, eax
0x18000f29e  jle     short loc_18000F2A8
0x18000f2a0  movzx   eax, ax
0x18000f2a3  or      eax, 80070000h
0x18000f2a8  xor     r9d, r9d; lpArguments
0x18000f2ab  xor     r8d, r8d; nNumberOfArguments
0x18000f2ae  mov     edx, r15d; dwExceptionFlags
0x18000f2b1  mov     ecx, eax; dwExceptionCode
0x18000f2b3  call    cs:__imp_RaiseException
0x18000f2b9  nop
0x18000f2ba  mov     r8, [rbp+arg_8]; struct IInstallationJob *
0x18000f2be  mov     rdx, [rbp+arg_18]; struct IUpdateInstaller *
0x18000f2c2  mov     rcx, rdi; this
0x18000f2c5  call    ?OnInstallCompleted@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateInstaller@@PEAUIInstallationJob@@@Z; OobeZdpElevatedManagerCore::OnInstallCompleted(IUpdateInstaller *,IInstallationJob *)
0x18000f2ca  mov     ebx, eax
0x18000f2cc  test    eax, eax
0x18000f2ce  jns     short loc_18000F346
0x18000f2d0  mov     rcx, [rbp+28h]; this
0x18000f2d4  mov     r9d, eax; char *
0x18000f2d7  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f2de  mov     edx, 1D7h; void *
0x18000f2e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2e8  nop
0x18000f2e9  lea     rcx, [rbp+arg_8]
0x18000f2ed  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f2f2  nop
0x18000f2f3  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f2fa  mov     [rbp+var_18], rax
0x18000f2fe  cmp     [rbp+var_10], r14
0x18000f302  jz      short loc_18000F339
0x18000f304  lea     rcx, [rbp+var_18]
0x18000f308  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f30d  test    al, al
0x18000f30f  jnz     short loc_18000F335
0x18000f311  call    cs:__imp_GetLastError
0x18000f317  test    eax, eax
0x18000f319  jle     short loc_18000F323
0x18000f31b  movzx   eax, ax
0x18000f31e  or      eax, 80070000h
0x18000f323  xor     r9d, r9d; lpArguments
0x18000f326  xor     r8d, r8d; nNumberOfArguments
0x18000f329  mov     edx, r15d; dwExceptionFlags
0x18000f32c  mov     ecx, eax; dwExceptionCode
0x18000f32e  call    cs:__imp_RaiseException
0x18000f334  int     3; Trap to Debugger
0x18000f335  mov     [rbp+var_10], r14
0x18000f339  lea     rcx, [rbp+arg_18]
0x18000f33d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f342  mov     eax, ebx
0x18000f344  jmp     short loc_18000F3A1
0x18000f346  lea     rcx, [rbp+arg_8]
0x18000f34a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f34f  nop
0x18000f350  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000f357  mov     [rbp+var_18], rax
0x18000f35b  cmp     [rbp+var_10], r14
0x18000f35f  jz      short loc_18000F396
0x18000f361  lea     rcx, [rbp+var_18]
0x18000f365  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x18000f36a  test    al, al
0x18000f36c  jnz     short loc_18000F392
0x18000f36e  call    cs:__imp_GetLastError
0x18000f374  test    eax, eax
0x18000f376  jle     short loc_18000F380
0x18000f378  movzx   eax, ax
0x18000f37b  or      eax, 80070000h
0x18000f380  xor     r9d, r9d; lpArguments
0x18000f383  xor     r8d, r8d; nNumberOfArguments
0x18000f386  mov     edx, r15d; dwExceptionFlags
0x18000f389  mov     ecx, eax; dwExceptionCode
0x18000f38b  call    cs:__imp_RaiseException
0x18000f391  int     3; Trap to Debugger
0x18000f392  mov     [rbp+var_10], r14
0x18000f396  lea     rcx, [rbp+arg_18]
0x18000f39a  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f39f  xor     eax, eax
0x18000f3a1  mov     rbx, [rsp+50h+arg_0]
0x18000f3a9  add     rsp, 50h
0x18000f3ad  pop     r15
0x18000f3af  pop     r14
0x18000f3b1  pop     rdi
0x18000f3b2  pop     rsi
0x18000f3b3  pop     rbp
0x18000f3b4  retn
```
