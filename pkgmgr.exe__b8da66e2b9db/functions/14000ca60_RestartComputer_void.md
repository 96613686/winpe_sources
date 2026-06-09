# RestartComputer(void)

- ea: `0x14000ca60`
- end: `0x14000cb72`
- name: `?RestartComputer@@YAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bdbc`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000ab58`
- `0x14000c080`
- `0x14000ca60`
- `0x1400127d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb15`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000cb0b`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x14000cb0b`

## string_xrefs

- `0x14000ca97`: `Failed enabling shutdown privilege`
- `0x14000cb2a`: `Failed restart attempt.`
- `0x14000cb4a`: `Failed disabling shutdown privilege`

## pseudocode

```c
__int64 __fastcall RestartComputer(const wchar_t *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  const wchar_t *v4; // rcx
  signed int LastError; // eax
  unsigned int v6; // eax
  int bRebootAfterShutdown; // [rsp+20h] [rbp-38h]
  int v9[2]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = ModifyPrivilege(a1, 1);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v2 = 0;
    if ( !InitiateSystemShutdownExW(0, 0, 0, 0, 1, 0x80020003) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      CBSWdsLog(0x4000000, v2, 1, "Failed restart attempt.");
    }
    v6 = ModifyPrivilege(v4, 0);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v6, "Failed disabling shutdown privilege");
  }
  else
  {
    v10 = v1;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed enabling shutdown privilege");
      *(_QWORD *)v9 = &v10;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v9);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)v2,
      bRebootAfterShutdown);
  }
  return v2;
}

```

## disassembly

```asm
0x14000ca60  push    rbx
0x14000ca62  sub     rsp, 50h
0x14000ca66  mov     rax, cs:__security_cookie
0x14000ca6d  xor     rax, rsp
0x14000ca70  mov     [rsp+58h+var_18], rax
0x14000ca75  mov     edx, 1; int
0x14000ca7a  call    ?ModifyPrivilege@@YAJPEB_WH@Z; ModifyPrivilege(wchar_t const *,int)
0x14000ca7f  mov     ebx, eax
0x14000ca81  test    eax, eax
0x14000ca83  jns     short loc_14000CAEF
0x14000ca85  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ca8c  mov     [rsp+58h+var_20], eax
0x14000ca90  test    rcx, rcx
0x14000ca93  jz      short loc_14000CAD4
0x14000ca95  xor     edx, edx
0x14000ca97  lea     r9, aFailedEnabling; "Failed enabling shutdown privilege"
0x14000ca9e  lea     r8d, [rdx+3]
0x14000caa2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000caa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000caae  lea     rax, [rsp+58h+var_20]
0x14000cab3  mov     qword ptr [rsp+58h+var_28], rax
0x14000cab8  lea     r9, asc_14002D4FC; ": {}"
0x14000cabf  lea     rax, [rsp+58h+var_28]
0x14000cac4  mov     r8d, 3
0x14000caca  mov     qword ptr [rsp+58h+bRebootAfterShutdown], rax; int
0x14000cacf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000cad4  mov     rcx, [rsp+58h]; this
0x14000cad9  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000cae0  mov     r9d, ebx; char *
0x14000cae3  mov     edx, 83h; void *
0x14000cae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000caed  jmp     short loc_14000CB5D
0x14000caef  mov     [rsp+58h+dwReason], 80020003h; dwReason
0x14000caf7  xor     r9d, r9d; bForceAppsClosed
0x14000cafa  xor     r8d, r8d; dwTimeout
0x14000cafd  mov     [rsp+58h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x14000cb05  xor     edx, edx; lpMessage
0x14000cb07  xor     ecx, ecx; lpMachineName
0x14000cb09  xor     ebx, ebx
0x14000cb0b  call    cs:__imp_InitiateSystemShutdownExW
0x14000cb11  test    eax, eax
0x14000cb13  jnz     short loc_14000CB43
0x14000cb15  call    cs:__imp_GetLastError
0x14000cb1b  mov     ebx, eax
0x14000cb1d  test    eax, eax
0x14000cb1f  jle     short loc_14000CB2A
0x14000cb21  movzx   ebx, ax
0x14000cb24  or      ebx, 80070000h
0x14000cb2a  lea     r9, aFailedRestartA; "Failed restart attempt."
0x14000cb31  mov     r8d, 1
0x14000cb37  mov     edx, ebx
0x14000cb39  mov     ecx, 4000000h
0x14000cb3e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cb43  xor     edx, edx; int
0x14000cb45  call    ?ModifyPrivilege@@YAJPEB_WH@Z; ModifyPrivilege(wchar_t const *,int)
0x14000cb4a  lea     r8, aFailedDisablin; "Failed disabling shutdown privilege"
0x14000cb51  mov     edx, eax
0x14000cb53  mov     ecx, 3
0x14000cb58  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x14000cb5d  mov     eax, ebx
0x14000cb5f  mov     rcx, [rsp+58h+var_18]
0x14000cb64  xor     rcx, rsp; StackCookie
0x14000cb67  call    __security_check_cookie
0x14000cb6c  add     rsp, 50h
0x14000cb70  pop     rbx
0x14000cb71  retn
```
