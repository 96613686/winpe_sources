# OobeZdpElevatedManagerCore::Search(IUpdateSession *,IUpdateCollection * *)

- ea: `0x180010640`
- end: `0x180010a04`
- name: `?Search@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSession@@PEAPEAUIUpdateCollection@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateSession *, struct IUpdateCollection **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000abd0`
- `0x18000dfb4`
- `0x18000f3c0`
- `0x18000fa00`
- `0x180010134`
- `0x1800103a0`
- `0x180010640`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800106ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800106ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010724`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800107ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010864`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800108ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010969`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800109da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010724`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800107ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010864`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800108ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010969`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800109da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001094c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001094c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bd`

## string_xrefs

- `0x180010686`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x1800106cf`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18001074f`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18001088f`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x180010912`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OobeZdpElevatedManagerCore::Search(
        OobeZdpElevatedManagerCore *this,
        struct IUpdateSession *a2,
        struct IUpdateCollection **a3)
{
  struct IUpdateSessionVtbl *lpVtbl; // rax
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE EventW; // rax
  int LastError; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  HWND v13; // rcx
  unsigned int v14; // eax
  OobeZdpElevatedManagerCore *v15; // rcx
  int v16; // eax
  int Error; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v22; // eax
  int v23; // [rsp+20h] [rbp-30h]
  int v24; // [rsp+20h] [rbp-30h]
  unsigned int v25; // [rsp+28h] [rbp-28h]
  struct IUpdateSearcher *v26; // [rsp+30h] [rbp-20h] BYREF
  void *v27; // [rsp+38h] [rbp-18h] BYREF
  void **v28; // [rsp+40h] [rbp-10h] BYREF
  void *v29; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v31; // [rsp+88h] [rbp+38h] BYREF
  int v32; // [rsp+90h] [rbp+40h] BYREF
  struct ISearchJob *v33; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUpdateSession *, struct IUpdateSearcher **))lpVtbl->CreateUpdateSearcher)(
         a2,
         &v26);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v6,
      v23);
LABEL_41:
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
      (void *)0x127,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)0x8000FFFFLL,
      v23);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_27;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
LABEL_26:
      v29 = 0;
      goto LABEL_27;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  v33 = 0;
  v10 = OobeZdpElevatedManagerCore::BeginAsyncSearch(this, v26, EventW, &v33);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v10,
      v23);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_41;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
      goto LABEL_40;
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    RaiseException(v11, 1u, 0, 0);
  }
  v12 = 240;
  v31 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
              L"TestZDPScanTimeoutSeconds",
              &v31) >= 0
    && v31 )
  {
    v12 = v31;
  }
  v27 = v29;
  v14 = SHProcessMessagesUntilEventsEx(v13, &v27, 1u, 1000 * v12, v23, v25);
  v32 = 0;
  if ( !v14 || v14 == 258 )
    goto LABEL_34;
  if ( v14 != -1 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( v29 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
      {
        v16 = GetLastError();
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        RaiseException(v16, 1u, 0, 0);
        __debugbreak();
      }
      goto LABEL_26;
    }
LABEL_27:
    v7 = -2147418113;
    goto LABEL_41;
  }
  Error = ResultFromKnownLastError();
  v7 = Error;
  if ( Error >= 0 )
    goto LABEL_43;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x143,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)Error,
    v24);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
  v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !v29 )
    goto LABEL_41;
  if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
  {
LABEL_40:
    v29 = 0;
    goto LABEL_41;
  }
  v18 = GetLastError();
  if ( v18 > 0 )
    v18 = (unsigned __int16)v18 | 0x80070000;
  RaiseException(v18, 1u, 0, 0);
LABEL_34:
  v19 = OobeZdpElevatedManagerCore::OnSearchCompleted(v15, v26, v33, a3);
  v7 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v19,
      v24);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
    v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !v29 )
      goto LABEL_41;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      RaiseException(v20, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_40;
  }
  ((void (__fastcall *)(_QWORD, int *))(*a3)->lpVtbl->get_Count)(*a3, &v32);
LABEL_43:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
  v28 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( v29 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(&v28) )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      RaiseException(v22, 1u, 0, 0);
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
0x180010640  mov     [rsp-28h+arg_0], rbx
0x180010645  push    rbp
0x180010646  push    rsi
0x180010647  push    rdi
0x180010648  push    r14
0x18001064a  push    r15
0x18001064c  mov     rbp, rsp
0x18001064f  sub     rsp, 50h
0x180010653  mov     rdi, r8
0x180010656  mov     r9, rdx
0x180010659  mov     rsi, rcx
0x18001065c  xor     r14d, r14d
0x18001065f  mov     [r8], r14
0x180010662  mov     rax, [rdx]
0x180010665  mov     [rbp+var_20], r14
0x180010669  lea     rdx, [rbp+var_20]
0x18001066d  mov     rcx, r9
0x180010670  mov     rax, [rax+60h]
0x180010674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010679  mov     ebx, eax
0x18001067b  test    eax, eax
0x18001067d  jns     short loc_18001069C
0x18001067f  mov     rcx, [rbp+28h]; this
0x180010683  mov     r9d, eax; char *
0x180010686  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18001068d  mov     edx, 124h; void *
0x180010692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010697  jmp     loc_180010974
0x18001069c  xor     r9d, r9d; lpName
0x18001069f  xor     r8d, r8d; bInitialState
0x1800106a2  lea     r15d, [r9+1]
0x1800106a6  mov     edx, r15d; bManualReset
0x1800106a9  xor     ecx, ecx; lpEventAttributes
0x1800106ab  call    cs:__imp_CreateEventW
0x1800106b1  mov     [rbp+var_8], rax
0x1800106b5  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800106bc  mov     [rbp+var_10], rcx
0x1800106c0  test    rax, rax
0x1800106c3  jnz     short loc_18001072B
0x1800106c5  mov     rcx, [rbp+28h]; this
0x1800106c9  mov     r9d, 8000FFFFh; char *
0x1800106cf  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800106d6  mov     edx, 127h; void *
0x1800106db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106e0  nop
0x1800106e1  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800106e8  mov     [rbp+var_10], rax
0x1800106ec  cmp     [rbp+var_8], r14
0x1800106f0  jz      loc_18001086F
0x1800106f6  lea     rcx, [rbp+var_10]
0x1800106fa  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x1800106ff  test    al, al
0x180010701  jnz     loc_18001086B
0x180010707  call    cs:__imp_GetLastError
0x18001070d  test    eax, eax
0x18001070f  jle     short loc_180010719
0x180010711  movzx   eax, ax
0x180010714  or      eax, 80070000h
0x180010719  xor     r9d, r9d; lpArguments
0x18001071c  xor     r8d, r8d; nNumberOfArguments
0x18001071f  mov     edx, r15d; dwExceptionFlags
0x180010722  mov     ecx, eax; dwExceptionCode
0x180010724  call    cs:__imp_RaiseException
0x18001072a  nop
0x18001072b  mov     [rbp+arg_18], r14
0x18001072f  lea     r9, [rbp+arg_18]; struct ISearchJob **
0x180010733  mov     r8, rax; void *
0x180010736  mov     rdx, [rbp+var_20]; struct IUpdateSearcher *
0x18001073a  mov     rcx, rsi; this
0x18001073d  call    ?BeginAsyncSearch@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSearcher@@PEAXPEAPEAUISearchJob@@@Z; OobeZdpElevatedManagerCore::BeginAsyncSearch(IUpdateSearcher *,void *,ISearchJob * *)
0x180010742  mov     ebx, eax
0x180010744  test    eax, eax
0x180010746  jns     short loc_1800107B5
0x180010748  mov     rcx, [rbp+28h]; this
0x18001074c  mov     r9d, eax; char *
0x18001074f  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010756  mov     edx, 12Ah; void *
0x18001075b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010760  nop
0x180010761  lea     rcx, [rbp+arg_18]
0x180010765  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18001076a  nop
0x18001076b  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180010772  mov     [rbp+var_10], rax
0x180010776  cmp     [rbp+var_8], r14
0x18001077a  jz      loc_180010974
0x180010780  lea     rcx, [rbp+var_10]
0x180010784  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x180010789  test    al, al
0x18001078b  jnz     loc_180010970
0x180010791  call    cs:__imp_GetLastError
0x180010797  test    eax, eax
0x180010799  jle     short loc_1800107A3
0x18001079b  movzx   eax, ax
0x18001079e  or      eax, 80070000h
0x1800107a3  xor     r9d, r9d; lpArguments
0x1800107a6  xor     r8d, r8d; nNumberOfArguments
0x1800107a9  mov     edx, r15d; dwExceptionFlags
0x1800107ac  mov     ecx, eax; dwExceptionCode
0x1800107ae  call    cs:__imp_RaiseException
0x1800107b4  nop
0x1800107b5  mov     ebx, 0F0h
0x1800107ba  mov     [rbp+arg_8], r14d
0x1800107be  lea     r9, [rbp+arg_8]; unsigned int *
0x1800107c2  lea     r8, aTestzdpscantim; "TestZDPScanTimeoutSeconds"
0x1800107c9  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800107d0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800107d7  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800107dc  test    eax, eax
0x1800107de  js      short loc_1800107E8
0x1800107e0  mov     eax, [rbp+arg_8]
0x1800107e3  test    eax, eax
0x1800107e5  cmovnz  ebx, eax
0x1800107e8  mov     rax, [rbp+var_8]
0x1800107ec  mov     [rbp+var_18], rax
0x1800107f0  imul    r9d, ebx, 3E8h; unsigned int
0x1800107f7  mov     r8d, r15d; unsigned int
0x1800107fa  lea     rdx, [rbp+var_18]; void **
0x1800107fe  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180010803  mov     [rbp+arg_10], r14d
0x180010807  test    eax, eax
0x180010809  jz      loc_1800108F5
0x18001080f  cmp     eax, 102h
0x180010814  jz      loc_1800108F5
0x18001081a  cmp     eax, 0FFFFFFFFh
0x18001081d  jz      short loc_180010879
0x18001081f  lea     rcx, [rbp+arg_18]
0x180010823  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180010828  nop
0x180010829  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180010830  mov     [rbp+var_10], rax
0x180010834  cmp     [rbp+var_8], r14
0x180010838  jz      short loc_18001086F
0x18001083a  lea     rcx, [rbp+var_10]
0x18001083e  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x180010843  test    al, al
0x180010845  jnz     short loc_18001086B
0x180010847  call    cs:__imp_GetLastError
0x18001084d  test    eax, eax
0x18001084f  jle     short loc_180010859
0x180010851  movzx   eax, ax
0x180010854  or      eax, 80070000h
0x180010859  xor     r9d, r9d; lpArguments
0x18001085c  xor     r8d, r8d; nNumberOfArguments
0x18001085f  mov     edx, r15d; dwExceptionFlags
0x180010862  mov     ecx, eax; dwExceptionCode
0x180010864  call    cs:__imp_RaiseException
0x18001086a  int     3; Trap to Debugger
0x18001086b  mov     [rbp+var_8], r14
0x18001086f  mov     ebx, 8000FFFFh
0x180010874  jmp     loc_180010974
0x180010879  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001087e  mov     ebx, eax
0x180010880  test    eax, eax
0x180010882  jns     loc_180010995
0x180010888  mov     rcx, [rbp+28h]; this
0x18001088c  mov     r9d, eax; char *
0x18001088f  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010896  mov     edx, 143h; void *
0x18001089b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108a0  nop
0x1800108a1  lea     rcx, [rbp+arg_18]
0x1800108a5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800108aa  nop
0x1800108ab  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800108b2  mov     [rbp+var_10], rax
0x1800108b6  cmp     [rbp+var_8], r14
0x1800108ba  jz      loc_180010974
0x1800108c0  lea     rcx, [rbp+var_10]
0x1800108c4  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x1800108c9  test    al, al
0x1800108cb  jnz     loc_180010970
0x1800108d1  call    cs:__imp_GetLastError
0x1800108d7  test    eax, eax
0x1800108d9  jle     short loc_1800108E3
0x1800108db  movzx   eax, ax
0x1800108de  or      eax, 80070000h
0x1800108e3  xor     r9d, r9d; lpArguments
0x1800108e6  xor     r8d, r8d; nNumberOfArguments
0x1800108e9  mov     edx, r15d; dwExceptionFlags
0x1800108ec  mov     ecx, eax; dwExceptionCode
0x1800108ee  call    cs:__imp_RaiseException
0x1800108f4  nop
0x1800108f5  mov     r9, rdi; struct IUpdateCollection **
0x1800108f8  mov     r8, [rbp+arg_18]; struct ISearchJob *
0x1800108fc  mov     rdx, [rbp+var_20]; struct IUpdateSearcher *
0x180010900  call    ?OnSearchCompleted@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSearcher@@PEAUISearchJob@@PEAPEAUIUpdateCollection@@@Z; OobeZdpElevatedManagerCore::OnSearchCompleted(IUpdateSearcher *,ISearchJob *,IUpdateCollection * *)
0x180010905  mov     ebx, eax
0x180010907  test    eax, eax
0x180010909  jns     short loc_180010981
0x18001090b  mov     rcx, [rbp+28h]; this
0x18001090f  mov     r9d, eax; char *
0x180010912  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x180010919  mov     edx, 13Eh; void *
0x18001091e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010923  nop
0x180010924  lea     rcx, [rbp+arg_18]
0x180010928  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18001092d  nop
0x18001092e  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180010935  mov     [rbp+var_10], rax
0x180010939  cmp     [rbp+var_8], r14
0x18001093d  jz      short loc_180010974
0x18001093f  lea     rcx, [rbp+var_10]
0x180010943  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x180010948  test    al, al
0x18001094a  jnz     short loc_180010970
0x18001094c  call    cs:__imp_GetLastError
0x180010952  test    eax, eax
0x180010954  jle     short loc_18001095E
0x180010956  movzx   eax, ax
0x180010959  or      eax, 80070000h
0x18001095e  xor     r9d, r9d; lpArguments
0x180010961  xor     r8d, r8d; nNumberOfArguments
0x180010964  mov     edx, r15d; dwExceptionFlags
0x180010967  mov     ecx, eax; dwExceptionCode
0x180010969  call    cs:__imp_RaiseException
0x18001096f  int     3; Trap to Debugger
0x180010970  mov     [rbp+var_8], r14
0x180010974  lea     rcx, [rbp+var_20]
0x180010978  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18001097d  mov     eax, ebx
0x18001097f  jmp     short loc_1800109F0
0x180010981  mov     rcx, [rdi]
0x180010984  mov     rax, [rcx]
0x180010987  lea     rdx, [rbp+arg_10]
0x18001098b  mov     rax, [rax+50h]
0x18001098f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010994  nop
0x180010995  lea     rcx, [rbp+arg_18]
0x180010999  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18001099e  nop
0x18001099f  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800109a6  mov     [rbp+var_10], rax
0x1800109aa  cmp     [rbp+var_8], r14
0x1800109ae  jz      short loc_1800109E5
0x1800109b0  lea     rcx, [rbp+var_10]
0x1800109b4  call    ?InternalClose@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::InternalClose(void)
0x1800109b9  test    al, al
0x1800109bb  jnz     short loc_1800109E1
0x1800109bd  call    cs:__imp_GetLastError
0x1800109c3  test    eax, eax
0x1800109c5  jle     short loc_1800109CF
0x1800109c7  movzx   eax, ax
0x1800109ca  or      eax, 80070000h
0x1800109cf  xor     r9d, r9d; lpArguments
0x1800109d2  xor     r8d, r8d; nNumberOfArguments
0x1800109d5  mov     edx, r15d; dwExceptionFlags
0x1800109d8  mov     ecx, eax; dwExceptionCode
0x1800109da  call    cs:__imp_RaiseException
0x1800109e0  int     3; Trap to Debugger
0x1800109e1  mov     [rbp+var_8], r14
0x1800109e5  lea     rcx, [rbp+var_20]
0x1800109e9  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800109ee  xor     eax, eax
0x1800109f0  mov     rbx, [rsp+50h+arg_0]
0x1800109f8  add     rsp, 50h
0x1800109fc  pop     r15
0x1800109fe  pop     r14
0x180010a00  pop     rdi
0x180010a01  pop     rsi
0x180010a02  pop     rbp
0x180010a03  retn
```
