# ModifyPrivilege(wchar_t const *,int)

- ea: `0x14000c080`
- end: `0x14000c30f`
- name: `?ModifyPrivilege@@YAJPEB_WH@Z`
- size: `655`
- prototype: `int __fastcall(const wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ca60`

## callees

- `0x140002360`
- `0x1400067bc`
- `0x140006c50`
- `0x14000952c`
- `0x14000c080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000c0c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000c0c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000c0d3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000c0d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2ea`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000c182`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000c182`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000c266`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000c266`

## string_xrefs

- `0x14000c0f5`: `Failed opening the process token`
- `0x14000c1a4`: `Failed looking up the privilege`
- `0x14000c284`: `Failed adjusting token privilege`
- `0x14000c179`: `SeShutdownPrivilege`

## pseudocode

```c
int __fastcall ModifyPrivilege(const wchar_t *a1, int a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  __int64 v5; // rdx
  unsigned int v6; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-60h]
  unsigned int v16; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v17[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-40h]
  void **p_TokenHandle; // [rsp+48h] [rbp-38h]
  char v20; // [rsp+50h] [rbp-30h]
  void *TokenHandle; // [rsp+58h] [rbp-28h] BYREF
  _LUID Luid; // [rsp+60h] [rbp-20h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v18 = -2;
  NewState = 0;
  Luid = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed opening the process token");
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      else
        v6 = LastError;
      v16 = v6;
      *(_QWORD *)v17 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {0}",
        (__int64)v17);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x59,
               (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
               (const char *)(unsigned int)LastError,
               PreviousState);
    return 0;
  }
  p_TokenHandle = &TokenHandle;
  v20 = 1;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = Luid;
    NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      v8 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adjusting token privilege");
        if ( v8 > 0 )
          v14 = (unsigned __int16)v8 | 0x80070000;
        else
          v14 = v8;
        v16 = v14;
        *(_QWORD *)v17 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v13,
          3,
          (__int64)": {0}",
          (__int64)v17);
      }
      if ( v8 )
      {
        v11 = 112;
        goto LABEL_17;
      }
    }
LABEL_28:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return 0;
  }
  v8 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed looking up the privilege");
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    else
      v10 = v8;
    v16 = v10;
    *(_QWORD *)v17 = &v16;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v9,
      3,
      (__int64)": {0}",
      (__int64)v17);
  }
  if ( !v8 )
    goto LABEL_28;
  v11 = 97;
LABEL_17:
  v12 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
          (const char *)(unsigned int)v8,
          PreviousState);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v12;
}

```

## disassembly

```asm
0x14000c080  mov     rax, rsp
0x14000c083  push    rbp
0x14000c084  mov     rbp, rsp
0x14000c087  sub     rsp, 80h
0x14000c08e  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x14000c096  mov     [rax+8], rbx
0x14000c09a  mov     rax, cs:__security_cookie
0x14000c0a1  xor     rax, rsp
0x14000c0a4  mov     [rbp+var_8], rax
0x14000c0a8  mov     ebx, edx
0x14000c0aa  xorps   xmm0, xmm0
0x14000c0ad  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x14000c0b1  mov     qword ptr [rbp+Luid.LowPart], 0
0x14000c0b9  mov     [rbp+TokenHandle], 0
0x14000c0c1  call    cs:__imp_GetCurrentProcess
0x14000c0c7  mov     rcx, rax; ProcessHandle
0x14000c0ca  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000c0ce  mov     edx, 28h ; '('; DesiredAccess
0x14000c0d3  call    cs:__imp_OpenProcessToken
0x14000c0d9  test    eax, eax
0x14000c0db  jnz     loc_14000C169
0x14000c0e1  call    cs:__imp_GetLastError
0x14000c0e7  mov     ebx, eax
0x14000c0e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c0f0  test    rcx, rcx
0x14000c0f3  jz      short loc_14000C144
0x14000c0f5  lea     r9, aFailedOpeningT; "Failed opening the process token"
0x14000c0fc  xor     edx, edx
0x14000c0fe  lea     r8d, [rdx+3]
0x14000c102  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c107  test    ebx, ebx
0x14000c109  jg      short loc_14000C10F
0x14000c10b  mov     eax, ebx
0x14000c10d  jmp     short loc_14000C117
0x14000c10f  movzx   eax, bx
0x14000c112  or      eax, 80070000h
0x14000c117  mov     [rbp+var_50], eax
0x14000c11a  lea     rax, [rbp+var_50]
0x14000c11e  mov     qword ptr [rbp+var_48], rax
0x14000c122  lea     rax, [rbp+var_48]
0x14000c126  mov     [rsp+80h+PreviousState], rax; unsigned int
0x14000c12b  lea     r9, a0; ": {0}"
0x14000c132  mov     r8d, 3
0x14000c138  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c13f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c144  test    ebx, ebx
0x14000c146  jz      loc_14000C2F0
0x14000c14c  mov     rcx, [rbp+8]; this
0x14000c150  mov     r9d, ebx; char *
0x14000c153  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000c15a  mov     edx, 59h ; 'Y'; void *
0x14000c15f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000c164  jmp     loc_14000C2F2
0x14000c169  lea     rax, [rbp+TokenHandle]
0x14000c16d  mov     [rbp+var_38], rax
0x14000c171  mov     [rbp+var_30], 1
0x14000c175  lea     r8, [rbp+Luid]; lpLuid
0x14000c179  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x14000c180  xor     ecx, ecx; lpSystemName
0x14000c182  call    cs:__imp_LookupPrivilegeValueW
0x14000c188  test    eax, eax
0x14000c18a  jnz     loc_14000C22B
0x14000c190  call    cs:__imp_GetLastError
0x14000c196  mov     ebx, eax
0x14000c198  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c19f  test    rcx, rcx
0x14000c1a2  jz      short loc_14000C1F3
0x14000c1a4  lea     r9, aFailedLookingU; "Failed looking up the privilege"
0x14000c1ab  xor     edx, edx
0x14000c1ad  lea     r8d, [rdx+3]
0x14000c1b1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c1b6  test    ebx, ebx
0x14000c1b8  jg      short loc_14000C1BE
0x14000c1ba  mov     eax, ebx
0x14000c1bc  jmp     short loc_14000C1C6
0x14000c1be  movzx   eax, bx
0x14000c1c1  or      eax, 80070000h
0x14000c1c6  mov     [rbp+var_50], eax
0x14000c1c9  lea     rax, [rbp+var_50]
0x14000c1cd  mov     qword ptr [rbp+var_48], rax
0x14000c1d1  lea     rax, [rbp+var_48]
0x14000c1d5  mov     [rsp+80h+PreviousState], rax; unsigned int
0x14000c1da  lea     r9, a0; ": {0}"
0x14000c1e1  mov     r8d, 3
0x14000c1e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c1ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c1f3  test    ebx, ebx
0x14000c1f5  jz      loc_14000C2E1
0x14000c1fb  mov     edx, 61h ; 'a'; void *
0x14000c200  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000c207  mov     r9d, ebx; char *
0x14000c20a  mov     rcx, [rbp+8]; this
0x14000c20e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000c213  mov     ebx, eax
0x14000c215  mov     rcx, [rbp+TokenHandle]; hObject
0x14000c219  test    rcx, rcx
0x14000c21c  jz      short loc_14000C224
0x14000c21e  call    cs:__imp_CloseHandle
0x14000c224  mov     eax, ebx
0x14000c226  jmp     loc_14000C2F2
0x14000c22b  mov     [rbp+NewState.PrivilegeCount], 1
0x14000c232  mov     rax, qword ptr [rbp+Luid.LowPart]
0x14000c236  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x14000c23a  neg     ebx
0x14000c23c  sbb     eax, eax
0x14000c23e  and     eax, 2
0x14000c241  mov     [rbp+NewState.Privileges.Attributes], eax
0x14000c244  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x14000c24d  mov     [rsp+80h+PreviousState], 0; PreviousState
0x14000c256  mov     r9d, 10h; BufferLength
0x14000c25c  lea     r8, [rbp+NewState]; NewState
0x14000c260  xor     edx, edx; DisableAllPrivileges
0x14000c262  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000c266  call    cs:__imp_AdjustTokenPrivileges
0x14000c26c  test    eax, eax
0x14000c26e  jnz     short loc_14000C2E1
0x14000c270  call    cs:__imp_GetLastError
0x14000c276  mov     ebx, eax
0x14000c278  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c27f  test    rcx, rcx
0x14000c282  jz      short loc_14000C2D3
0x14000c284  lea     r9, aFailedAdjustin; "Failed adjusting token privilege"
0x14000c28b  xor     edx, edx
0x14000c28d  lea     r8d, [rdx+3]
0x14000c291  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c296  test    ebx, ebx
0x14000c298  jg      short loc_14000C29E
0x14000c29a  mov     eax, ebx
0x14000c29c  jmp     short loc_14000C2A6
0x14000c29e  movzx   eax, bx
0x14000c2a1  or      eax, 80070000h
0x14000c2a6  mov     [rbp+var_50], eax
0x14000c2a9  lea     rax, [rbp+var_50]
0x14000c2ad  mov     qword ptr [rbp+var_48], rax
0x14000c2b1  lea     rax, [rbp+var_48]
0x14000c2b5  mov     [rsp+80h+PreviousState], rax
0x14000c2ba  lea     r9, a0; ": {0}"
0x14000c2c1  mov     r8d, 3
0x14000c2c7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c2ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c2d3  test    ebx, ebx
0x14000c2d5  jz      short loc_14000C2E1
0x14000c2d7  mov     edx, 70h ; 'p'
0x14000c2dc  jmp     loc_14000C200
0x14000c2e1  mov     rcx, [rbp+TokenHandle]; hObject
0x14000c2e5  test    rcx, rcx
0x14000c2e8  jz      short loc_14000C2F0
0x14000c2ea  call    cs:__imp_CloseHandle
0x14000c2f0  xor     eax, eax
0x14000c2f2  mov     rcx, [rbp+var_8]
0x14000c2f6  xor     rcx, rsp; StackCookie
0x14000c2f9  call    __security_check_cookie
0x14000c2fe  mov     rbx, [rsp+80h+arg_0]
0x14000c306  add     rsp, 80h
0x14000c30d  pop     rbp
0x14000c30e  retn
```
