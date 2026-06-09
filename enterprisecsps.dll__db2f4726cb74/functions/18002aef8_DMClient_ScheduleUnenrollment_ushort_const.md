# DMClient::ScheduleUnenrollment(ushort const *)

- ea: `0x18002aef8`
- end: `0x18002b309`
- name: `?ScheduleUnenrollment@DMClient@@YAJPEBG@Z`
- size: `1041`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035000`
- `0x180035100`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000a3ec`
- `0x18000a540`
- `0x18000b5d8`
- `0x18000da10`
- `0x18000db08`
- `0x180023874`
- `0x180024d8c`
- `0x1800256ac`
- `0x180025b70`
- `0x180025cec`
- `0x18002aef8`
- `0x18002c6d0`
- `0x18002c9f0`
- `0x18002d3ec`
- `0x18002df7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002b1a1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002b1a1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b08f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b08f`
- `RPCRT4!UuidFromStringW` at `0x18002afd7`
- `RPCRT4!UuidFromStringW` at `0x18002aff2`
- `RPCRT4!UuidFromStringW` at `0x18002afd7`
- `RPCRT4!UuidFromStringW` at `0x18002aff2`
- `dmEnrollEngine!GetEnrollmentType` at `0x18002b035`
- `dmEnrollEngine!GetEnrollmentType` at `0x18002b035`

## string_xrefs

- `0x18002b088`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DMClient::ScheduleUnenrollment(DMClient *this, const unsigned __int16 *a2)
{
  signed int v3; // eax
  int EnrollmentType; // eax
  const char *v5; // r9
  int v6; // eax
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  struct _PROCESS_INFORMATION *v10; // rdx
  wil *v11; // rcx
  __int64 result; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  int bInheritHandles; // [rsp+20h] [rbp-698h]
  const char *dwCreationFlags; // [rsp+28h] [rbp-690h]
  unsigned int v18; // [rsp+50h] [rbp-668h] BYREF
  DMClient *v19; // [rsp+58h] [rbp-660h]
  DMClient *v20; // [rsp+60h] [rbp-658h] BYREF
  __int128 v21; // [rsp+68h] [rbp-650h]
  WCHAR *v22; // [rsp+78h] [rbp-640h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-638h] BYREF
  UUID v24; // [rsp+A0h] [rbp-618h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-608h] BYREF
  UUID Uuid; // [rsp+120h] [rbp-598h] BYREF
  _QWORD v27[42]; // [rsp+130h] [rbp-588h] BYREF
  WCHAR CommandLine[264]; // [rsp+280h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+490h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+0h]

  v19 = this;
  v21 = 0;
  v22 = 0;
  v20 = this;
  wil::ActivityBase<DmClientLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DmClientLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v27);
  v27[0] = &DmClientLogging::ScheduleUnenrollmentActivity::`vftable';
  try
  {
    DmClientLogging::ScheduleUnenrollmentActivity::StartActivity(
      (DmClientLogging::ScheduleUnenrollmentActivity *)v27,
      (const struct DmClientLogging::UnenrollmentData *)&v20);
    memset_0(Dst, 0, 0x208u);
    memset_0(CommandLine, 0, 0x208u);
    Uuid = 0;
    v18 = 63;
    *((_QWORD *)&v21 + 1) = Dst;
    v22 = CommandLine;
    if ( !this )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x474,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)0x80070057LL,
        bInheritHandles);
    if ( UuidFromStringW((RPC_WSTR)this, &Uuid) )
      v3 = UuidFromStringW((RPC_WSTR)this, &Uuid) | 0x80010000;
    else
      v3 = 0;
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x476,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)(unsigned int)v3,
        bInheritHandles);
    v24 = Uuid;
    EnrollmentType = GetEnrollmentType(&v24, &v18);
    if ( EnrollmentType < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x478,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)(unsigned int)EnrollmentType,
        bInheritHandles);
    LODWORD(v21) = v18;
    if ( v18 == 6
      && ((unsigned __int8)IsConvertLocalAccountToAADAccountPresent(retaddr)
       || (unsigned __int8)IsCreateAndSignInAADUserPresent()) )
    {
      v13 = wil::verify_hresult<long>(2147500033LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x47F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)v13,
        (int)"Not supported by windows phone.",
        dwCreationFlags);
    }
    if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x489,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        v5);
    v6 = StringCchCopyW(CommandLine, 0x104u, L"/C /n /d \"");
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)(unsigned int)v6,
        bInheritHandles);
    v7 = StringCchCatW(CommandLine, 0x104u, (const unsigned __int16 *)this);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)(unsigned int)v7,
        bInheritHandles);
    v8 = StringCchCatW(CommandLine, 0x104u, L"\"");
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)(unsigned int)v8,
        bInheritHandles);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( !CreateProcessW(Dst, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x49C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        v9);
    DmClientLogging::ScheduleUnenrollmentActivity::Stop(
      (DmClientLogging::ScheduleUnenrollmentActivity *)v27,
      (const struct DmClientLogging::UnenrollmentData *)&v20);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsDMClientUnenrollStartSucceeded,
        this);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v10);
    DmClientLogging::ScheduleUnenrollmentActivity::~ScheduleUnenrollmentActivity((DmClientLogging::ScheduleUnenrollmentActivity *)v27);
    result = 0;
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v11);
    v18 = v14;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(v15, EnterpriseDiagnosticsDMClientUnenrollStartFailed, v19, v14);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x18002aef8  mov     [rsp+arg_8], rbx
0x18002aefd  push    rdi
0x18002aefe  sub     rsp, 6B0h
0x18002af05  mov     rax, cs:__security_cookie
0x18002af0c  xor     rax, rsp
0x18002af0f  mov     [rsp+6B8h+var_18], rax
0x18002af17  mov     rbx, rcx
0x18002af1a  mov     [rsp+6B8h+var_660], rcx
0x18002af1f  xorps   xmm0, xmm0
0x18002af22  movdqu  [rsp+6B8h+var_650], xmm0
0x18002af28  mov     [rsp+6B8h+var_640], 0
0x18002af31  mov     [rsp+6B8h+var_658], rcx
0x18002af36  lea     rcx, [rsp+6B8h+var_588]; struct wil::details::IFailureCallback *
0x18002af3e  call    ??0?$ActivityBase@VDmClientLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DmClientLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DmClientLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002af43  lea     rax, ??_7ScheduleUnenrollmentActivity@DmClientLogging@@6B@; const DmClientLogging::ScheduleUnenrollmentActivity::`vftable'
0x18002af4a  mov     [rsp+6B8h+var_588], rax
0x18002af52  lea     rdx, [rsp+6B8h+var_658]; struct DmClientLogging::UnenrollmentData *
0x18002af57  lea     rcx, [rsp+6B8h+var_588]; this
0x18002af5f  call    ?StartActivity@ScheduleUnenrollmentActivity@DmClientLogging@@QEAAXAEBUUnenrollmentData@2@@Z; DmClientLogging::ScheduleUnenrollmentActivity::StartActivity(DmClientLogging::UnenrollmentData const &)
0x18002af64  nop
0x18002af65  mov     edi, 208h
0x18002af6a  mov     r8d, edi; Size
0x18002af6d  xor     edx, edx; Val
0x18002af6f  lea     rcx, [rsp+6B8h+Dst]; void *
0x18002af77  call    memset_0
0x18002af7c  mov     r8d, edi; Size
0x18002af7f  xor     edx, edx; Val
0x18002af81  lea     rcx, [rsp+6B8h+CommandLine]; void *
0x18002af89  call    memset_0
0x18002af8e  xorps   xmm0, xmm0
0x18002af91  movups  xmmword ptr [rsp+6B8h+Uuid.Data1], xmm0
0x18002af99  mov     [rsp+6B8h+var_668], 3Fh ; '?'
0x18002afa1  lea     rax, [rsp+6B8h+Dst]
0x18002afa9  mov     qword ptr [rsp+6B8h+var_650+8], rax
0x18002afae  lea     rax, [rsp+6B8h+CommandLine]
0x18002afb6  mov     [rsp+6B8h+var_640], rax
0x18002afbb  mov     rcx, [rsp+6B8h]; this
0x18002afc3  test    rbx, rbx
0x18002afc6  jz      loc_18002B22C
0x18002afcc  lea     rdx, [rsp+6B8h+Uuid]; Uuid
0x18002afd4  mov     rcx, rbx; StringUuid
0x18002afd7  call    cs:__imp_UuidFromStringW
0x18002afde  nop     dword ptr [rax+rax+00h]
0x18002afe3  test    eax, eax
0x18002afe5  jz      short loc_18002B005
0x18002afe7  lea     rdx, [rsp+6B8h+Uuid]; Uuid
0x18002afef  mov     rcx, rbx; StringUuid
0x18002aff2  call    cs:__imp_UuidFromStringW
0x18002aff9  nop     dword ptr [rax+rax+00h]
0x18002affe  or      eax, 80010000h
0x18002b003  jmp     short loc_18002B007
0x18002b005  xor     eax, eax
0x18002b007  mov     rcx, [rsp+6B8h]; this
0x18002b00f  test    eax, eax
0x18002b011  js      loc_18002B243
0x18002b017  movaps  xmm0, xmmword ptr [rsp+6B8h+Uuid.Data1]
0x18002b01f  movdqa  [rsp+6B8h+var_618], xmm0
0x18002b028  lea     rdx, [rsp+6B8h+var_668]
0x18002b02d  lea     rcx, [rsp+6B8h+var_618]
0x18002b035  call    cs:__imp_GetEnrollmentType
0x18002b03c  nop     dword ptr [rax+rax+00h]
0x18002b041  mov     rcx, [rsp+6B8h]; this
0x18002b049  test    eax, eax
0x18002b04b  js      loc_18002B257
0x18002b051  mov     eax, [rsp+6B8h+var_668]
0x18002b055  mov     dword ptr [rsp+6B8h+var_650], eax
0x18002b059  cmp     eax, 6
0x18002b05c  jnz     short loc_18002B078
0x18002b05e  call    IsConvertLocalAccountToAADAccountPresent
0x18002b063  test    al, al
0x18002b065  jnz     loc_18002B26B
0x18002b06b  call    IsCreateAndSignInAADUserPresent
0x18002b070  test    al, al
0x18002b072  jnz     loc_18002B26B
0x18002b078  mov     edi, 104h
0x18002b07d  mov     r8d, edi; nSize
0x18002b080  lea     rdx, [rsp+6B8h+Dst]; lpDst
0x18002b088  lea     rcx, Src; "%windir%\\system32\\deviceenroller.exe"
0x18002b08f  call    cs:__imp_ExpandEnvironmentStringsW
0x18002b096  nop     dword ptr [rax+rax+00h]
0x18002b09b  test    eax, eax
0x18002b09d  jz      loc_18002B29D
0x18002b0a3  lea     r8, aCND; "/C /n /d \""
0x18002b0aa  mov     rdx, rdi; unsigned __int64
0x18002b0ad  lea     rcx, [rsp+6B8h+CommandLine]; unsigned __int16 *
0x18002b0b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b0ba  mov     rcx, [rsp+6B8h]; this
0x18002b0c2  test    eax, eax
0x18002b0c4  js      loc_18002B2B6
0x18002b0ca  mov     r8, rbx; unsigned __int16 *
0x18002b0cd  mov     rdx, rdi; unsigned __int64
0x18002b0d0  lea     rcx, [rsp+6B8h+CommandLine]; unsigned __int16 *
0x18002b0d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b0dd  mov     rcx, [rsp+6B8h]; this
0x18002b0e5  test    eax, eax
0x18002b0e7  js      loc_18002B2CA
0x18002b0ed  lea     r8, asc_18011E928; "\""
0x18002b0f4  mov     rdx, rdi; unsigned __int64
0x18002b0f7  lea     rcx, [rsp+6B8h+CommandLine]; unsigned __int16 *
0x18002b0ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b104  mov     rcx, [rsp+6B8h]; this
0x18002b10c  test    eax, eax
0x18002b10e  js      loc_18002B2DE
0x18002b114  xorps   xmm0, xmm0
0x18002b117  xor     eax, eax
0x18002b119  movups  xmmword ptr [rsp+6B8h+ProcessInformation.hProcess], xmm0
0x18002b121  mov     qword ptr [rsp+6B8h+ProcessInformation.dwProcessId], rax
0x18002b129  xor     edx, edx; Val
0x18002b12b  lea     r8d, [rax+64h]; Size
0x18002b12f  lea     rcx, [rsp+6B8h+StartupInfo+4]; void *
0x18002b137  call    memset_0
0x18002b13c  mov     [rsp+6B8h+StartupInfo.cb], 68h ; 'h'
0x18002b147  mov     rdi, [rsp+6B8h]
0x18002b14f  lea     rax, [rsp+6B8h+ProcessInformation]
0x18002b157  mov     [rsp+6B8h+lpProcessInformation], rax; lpProcessInformation
0x18002b15c  lea     rax, [rsp+6B8h+StartupInfo]
0x18002b164  mov     [rsp+6B8h+lpStartupInfo], rax; lpStartupInfo
0x18002b169  mov     [rsp+6B8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002b172  mov     [rsp+6B8h+lpEnvironment], 0; lpEnvironment
0x18002b17b  mov     dword ptr [rsp+6B8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002b183  mov     [rsp+6B8h+bInheritHandles], 0; bInheritHandles
0x18002b18b  xor     r9d, r9d; lpThreadAttributes
0x18002b18e  xor     r8d, r8d; lpProcessAttributes
0x18002b191  lea     rdx, [rsp+6B8h+CommandLine]; lpCommandLine
0x18002b199  lea     rcx, [rsp+6B8h+Dst]; lpApplicationName
0x18002b1a1  call    cs:__imp_CreateProcessW
0x18002b1a8  nop     dword ptr [rax+rax+00h]
0x18002b1ad  test    eax, eax
0x18002b1af  jz      loc_18002B2F3
0x18002b1b5  lea     rdx, [rsp+6B8h+var_658]; struct DmClientLogging::UnenrollmentData *
0x18002b1ba  lea     rcx, [rsp+6B8h+var_588]; this
0x18002b1c2  call    ?Stop@ScheduleUnenrollmentActivity@DmClientLogging@@QEAAXAEBUUnenrollmentData@2@@Z; DmClientLogging::ScheduleUnenrollmentActivity::Stop(DmClientLogging::UnenrollmentData const &)
0x18002b1c7  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x18002b1ce  jz      short loc_18002B1E7
0x18002b1d0  mov     r8, rbx
0x18002b1d3  lea     rdx, EnterpriseDiagnosticsDMClientUnenrollStartSucceeded
0x18002b1da  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18002b1e1  call    McTemplateU0z_EventWriteTransfer
0x18002b1e6  nop
0x18002b1e7  lea     rcx, [rsp+6B8h+ProcessInformation]; this
0x18002b1ef  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18002b1f4  nop
0x18002b1f5  lea     rcx, [rsp+6B8h+var_588]; this
0x18002b1fd  call    ??1ScheduleUnenrollmentActivity@DmClientLogging@@QEAA@XZ; DmClientLogging::ScheduleUnenrollmentActivity::~ScheduleUnenrollmentActivity(void)
0x18002b202  xor     eax, eax
0x18002b204  jmp     short loc_18002B20A
0x18002b206  mov     eax, [rsp+6B8h+var_668]
0x18002b20a  mov     rcx, [rsp+6B8h+var_18]
0x18002b212  xor     rcx, rsp; StackCookie
0x18002b215  call    __security_check_cookie
0x18002b21a  mov     rbx, [rsp+6B8h+arg_8]
0x18002b222  add     rsp, 6B0h
0x18002b229  pop     rdi
0x18002b22a  retn
0x18002b22c  mov     r9d, 80070057h; char *
0x18002b232  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b239  mov     edx, 474h; void *
0x18002b23e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b243  mov     r9d, eax; char *
0x18002b246  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b24d  mov     edx, 476h; void *
0x18002b252  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b257  mov     r9d, eax; char *
0x18002b25a  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b261  mov     edx, 478h; void *
0x18002b266  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b26b  mov     ecx, 80004001h
0x18002b270  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b275  mov     r9d, eax; char *
0x18002b278  mov     rcx, [rsp+6B8h]; this
0x18002b280  lea     rax, aNotSupportedBy; "Not supported by windows phone."
0x18002b287  mov     qword ptr [rsp+6B8h+bInheritHandles], rax; int
0x18002b28c  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b293  mov     edx, 47Fh; void *
0x18002b298  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002b29d  mov     rcx, [rsp+6B8h]; this
0x18002b2a5  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b2ac  mov     edx, 489h; void *
0x18002b2b1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002b2b6  mov     r9d, eax; char *
0x18002b2b9  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b2c0  mov     edx, 48Ch; void *
0x18002b2c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b2ca  mov     r9d, eax; char *
0x18002b2cd  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b2d4  mov     edx, 48Dh; void *
0x18002b2d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b2de  mov     r9d, eax; char *
0x18002b2e1  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b2e8  mov     edx, 48Eh; void *
0x18002b2ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b2f3  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b2fa  mov     edx, 49Ch; void *
0x18002b2ff  mov     rcx, rdi; this
0x18002b302  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
