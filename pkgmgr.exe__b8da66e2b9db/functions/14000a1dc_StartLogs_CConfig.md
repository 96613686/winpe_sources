# StartLogs(CConfig *)

- ea: `0x14000a1dc`
- end: `0x14000a6ca`
- name: `?StartLogs@@YAJPEAVCConfig@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(struct CConfig *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000aca8`

## callees

- `0x140001fcc`
- `0x140002360`
- `0x140002d98`
- `0x140005684`
- `0x1400056ac`
- `0x140005c7c`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000726c`
- `0x1400095ac`
- `0x1400097d4`
- `0x1400098b8`
- `0x14000a1bc`
- `0x14000a1dc`
- `0x140011100`
- `0x140011884`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14000a5d9`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14000a5d9`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000a548`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000a5ef`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000a548`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000a5ef`

## string_xrefs

- `0x14000a258`: `No config specified`
- `0x14000a2c8`: `Config does not define filename`
- `0x14000a464`: `Failed adding log file name extension: {}`
- `0x14000a541`: `COMPONENT_BASED_SERVICING_LOGFILE`

## pseudocode

```c
__int64 __fastcall StartLogs(struct CConfig *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  const wchar_t *OfflineWinDirPath; // r14
  __int64 v8; // rdi
  int v9; // edx
  int v10; // r8d
  unsigned __int64 v11; // rsi
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  const char *v21; // r9
  int LastError; // eax
  int v23; // edx
  int v24; // r8d
  __int64 v25; // rdx
  __int64 v27; // rdx
  int v28[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v29[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v32; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR Value[512]; // [rsp+68h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A0h] [rbp+398h]

  v29[1] = -2;
  v32 = 0;
  memset_0(Value, 0, sizeof(Value));
  v29[0] = 0;
  if ( this )
  {
    v30 = *((_QWORD *)this + 30);
    if ( v30 )
    {
      OfflineWinDirPath = CConfig::GetOfflineWinDirPath(this);
      v8 = *((_DWORD *)this + 62) != 0;
      while ( 1 )
      {
        v2 = SczAllocFromSz(&v32, v6);
        if ( v2 < 0 )
        {
          LODWORD(v31) = v2;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed allocating log file name: {}",
              (__int64)&v30);
            *(_QWORD *)v28 = &v31;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v27,
              3,
              (__int64)": {}",
              (__int64)v28);
          }
          v4 = 215;
          goto LABEL_41;
        }
        if ( OfflineWinDirPath )
        {
          v2 = SczAllocConcatSz(&v32, L".bootstrap");
          if ( v2 < 0 )
          {
            LODWORD(v31) = v2;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t [11]>(
                (_DWORD)LogAdapter::g_Logger,
                v9,
                v10,
                (unsigned int)"Failed adding bootstrap log file name marker: {}",
                (__int64)L".bootstrap");
              *(_QWORD *)v28 = &v31;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v17,
                3,
                (__int64)": {}",
                (__int64)v28);
            }
            v4 = 219;
            goto LABEL_41;
          }
        }
        v11 = 48 * v8;
        v12 = (__int64)*(&vrgTraceLoggers + 6 * v8 + 2);
        if ( v12 )
        {
          v2 = SczAllocConcatSz(&v32, v12);
          if ( v2 < 0 )
          {
            LODWORD(v31) = v2;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed adding log file name extension: {}",
                (__int64)&(&off_140050060)[v11 / 8]);
              *(_QWORD *)v28 = &v31;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v18,
                3,
                (__int64)": {}",
                (__int64)v28);
            }
            v4 = 224;
            goto LABEL_41;
          }
        }
        v13 = BeginTracing(
                v32,
                *(const wchar_t **)((char *)&vrgTraceLoggers + v11),
                (const struct _GUID *)&qword_140050068[v11 / 8],
                *(_DWORD *)((char *)&vrgTraceLoggers + v11 + 40),
                (unsigned __int64 *)&algn_140050058[v11]);
        if ( v13 < 0 )
          LogAdapter::TraceAtLevelHr<long,AutoScz>(v14, (unsigned int)v13, v15, &v32);
        v16 = v32;
        v32 = 0;
        operator delete(v16 - 4);
        if ( (unsigned __int64)++v8 >= 2 )
          break;
        v6 = v30;
      }
      if ( OfflineWinDirPath )
      {
        v19 = StringCchPrintfW(Value, 0x200u, L"%s.txt", v30);
        v2 = v19;
        if ( v19 < 0 )
        {
          LODWORD(v31) = v19;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed creating the offline CBS text log file name: {}.txt",
              (__int64)&v30);
            *(_QWORD *)v28 = &v31;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v20,
              3,
              (__int64)": {}",
              (__int64)v28);
          }
          v4 = 239;
          goto LABEL_41;
        }
        if ( !SetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGFILE", Value) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x13D,
                        (int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
                        v21);
          v2 = LastError;
          if ( LastError < 0 )
          {
            LODWORD(v31) = LastError;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t [11]>(
                (_DWORD)LogAdapter::g_Logger,
                v23,
                v24,
                (unsigned int)"Failed setting offline CBS text log file name: {}",
                (__int64)Value);
              *(_QWORD *)v28 = &v31;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v25,
                3,
                (__int64)": {}",
                (__int64)v28);
            }
            v4 = 241;
            goto LABEL_41;
          }
        }
        if ( !GetEnvironmentVariableW(L"WINDOWS_TRACING_LOGFILE", 0, 0) )
          SetEnvironmentVariableW(L"WINDOWS_TRACING_LOGFILE", Value);
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
      return 0;
    }
    v2 = -2147024809;
    LODWORD(v31) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Config does not define filename");
      *(_QWORD *)v28 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    v4 = 206;
  }
  else
  {
    v2 = -2147024809;
    LODWORD(v31) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No config specified");
      *(_QWORD *)v28 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v28);
    }
    v4 = 203;
  }
LABEL_41:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
    (const char *)(unsigned int)v2);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v32);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000a1dc  mov     rax, rsp
0x14000a1df  push    rbp
0x14000a1e0  push    rdi
0x14000a1e1  push    r12
0x14000a1e3  push    r13
0x14000a1e5  push    r14
0x14000a1e7  lea     rbp, [rax-398h]
0x14000a1ee  sub     rsp, 470h
0x14000a1f5  mov     [rsp+490h+var_450], 0FFFFFFFFFFFFFFFEh
0x14000a1fe  mov     [rax+10h], rbx
0x14000a202  mov     [rax+18h], rsi
0x14000a206  mov     rax, cs:__security_cookie
0x14000a20d  xor     rax, rsp
0x14000a210  mov     [rbp+390h+var_30], rax
0x14000a217  mov     rbx, rcx
0x14000a21a  mov     [rsp+490h+var_438], 0
0x14000a223  xor     edx, edx; Val
0x14000a225  mov     r8d, 400h; Size
0x14000a22b  lea     rcx, [rsp+490h+Value]; void *
0x14000a230  call    memset_0
0x14000a235  mov     [rsp+490h+var_458], 0
0x14000a23e  test    rbx, rbx
0x14000a241  jnz     short loc_14000A2A2
0x14000a243  mov     ebx, 80070057h
0x14000a248  mov     dword ptr [rsp+490h+var_440], ebx
0x14000a24c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a253  test    rcx, rcx
0x14000a256  jz      short loc_14000A298
0x14000a258  lea     r9, aNoConfigSpecif; "No config specified"
0x14000a25f  mov     edi, 3
0x14000a264  mov     r8d, edi
0x14000a267  xor     edx, edx
0x14000a269  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000a26e  lea     rax, [rsp+490h+var_440]
0x14000a273  mov     qword ptr [rsp+490h+var_460], rax
0x14000a278  lea     rax, [rsp+490h+var_460]
0x14000a27d  mov     [rsp+490h+var_470], rax
0x14000a282  lea     r9, asc_14002D4FC; ": {}"
0x14000a289  mov     r8d, edi
0x14000a28c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a293  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a298  mov     edx, 0CBh
0x14000a29d  jmp     loc_14000A671
0x14000a2a2  mov     rdx, [rbx+0F0h]
0x14000a2a9  mov     [rsp+490h+var_448], rdx
0x14000a2ae  test    rdx, rdx
0x14000a2b1  jnz     short loc_14000A30E
0x14000a2b3  mov     ebx, 80070057h
0x14000a2b8  mov     dword ptr [rsp+490h+var_440], ebx
0x14000a2bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a2c3  test    rcx, rcx
0x14000a2c6  jz      short loc_14000A304
0x14000a2c8  lea     r9, aConfigDoesNotD; "Config does not define filename"
0x14000a2cf  lea     edi, [rdx+3]
0x14000a2d2  mov     r8d, edi
0x14000a2d5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000a2da  lea     rax, [rsp+490h+var_440]
0x14000a2df  mov     qword ptr [rsp+490h+var_460], rax
0x14000a2e4  lea     rax, [rsp+490h+var_460]
0x14000a2e9  mov     [rsp+490h+var_470], rax
0x14000a2ee  lea     r9, asc_14002D4FC; ": {}"
0x14000a2f5  mov     r8d, edi
0x14000a2f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a2ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a304  mov     edx, 0CEh
0x14000a309  jmp     loc_14000A671
0x14000a30e  mov     rcx, rbx; this
0x14000a311  call    ?GetOfflineWinDirPath@CConfig@@QEAAPEB_WXZ; CConfig::GetOfflineWinDirPath(void)
0x14000a316  mov     r14, rax
0x14000a319  xor     edi, edi
0x14000a31b  cmp     [rbx+0F8h], edi
0x14000a321  setnz   dil
0x14000a325  lea     r13, aBootstrap; ".bootstrap"
0x14000a32c  lea     r12, ?vrgTraceLoggers@@3PAUTRACE_LOGGER@@A; TRACE_LOGGER near * vrgTraceLoggers
0x14000a333  lea     rcx, [rsp+490h+var_438]
0x14000a338  call    SczAllocFromSz
0x14000a33d  mov     ebx, eax
0x14000a33f  test    eax, eax
0x14000a341  js      loc_14000A612
0x14000a347  test    r14, r14
0x14000a34a  jz      short loc_14000A363
0x14000a34c  mov     rdx, r13
0x14000a34f  lea     rcx, [rsp+490h+var_438]
0x14000a354  call    SczAllocConcatSz
0x14000a359  mov     ebx, eax
0x14000a35b  test    eax, eax
0x14000a35d  js      loc_14000A3EF
0x14000a363  lea     rsi, [rdi+rdi*2]
0x14000a367  shl     rsi, 4
0x14000a36b  mov     rdx, [rsi+r12+10h]
0x14000a370  test    rdx, rdx
0x14000a373  jz      short loc_14000A389
0x14000a375  lea     rcx, [rsp+490h+var_438]
0x14000a37a  call    SczAllocConcatSz
0x14000a37f  mov     ebx, eax
0x14000a381  test    eax, eax
0x14000a383  js      loc_14000A447
0x14000a389  lea     rax, [r12+8]
0x14000a38e  add     rax, rsi
0x14000a391  lea     r8, [r12+18h]
0x14000a396  add     r8, rsi; struct _GUID *
0x14000a399  mov     [rsp+490h+var_470], rax; unsigned __int64 *
0x14000a39e  mov     r9d, [rsi+r12+28h]; unsigned int
0x14000a3a3  mov     rdx, [rsi+r12]; wchar_t *
0x14000a3a7  mov     rcx, [rsp+490h+var_438]; wchar_t *
0x14000a3ac  call    ?BeginTracing@@YAJPEB_W0PEBU_GUID@@KPEA_K@Z; BeginTracing(wchar_t const *,wchar_t const *,_GUID const *,ulong,unsigned __int64 *)
0x14000a3b1  test    eax, eax
0x14000a3b3  jns     short loc_14000A3C1
0x14000a3b5  lea     r9, [rsp+490h+var_438]
0x14000a3ba  mov     edx, eax
0x14000a3bc  call    ??$TraceAtLevelHr@JVAutoScz@@@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBVAutoScz@@@Z; LogAdapter::TraceAtLevelHr<long,AutoScz>(LogAdapter::LogLevel,long,char const * const,AutoScz const &)
0x14000a3c1  mov     rcx, [rsp+490h+var_438]
0x14000a3c6  mov     [rsp+490h+var_438], 0
0x14000a3cf  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x14000a3d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a3d8  inc     rdi
0x14000a3db  cmp     rdi, 2
0x14000a3df  jnb     loc_14000A4AE
0x14000a3e5  mov     rdx, [rsp+490h+var_448]
0x14000a3ea  jmp     loc_14000A333
0x14000a3ef  mov     dword ptr [rsp+490h+var_440], ebx
0x14000a3f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a3fa  test    rcx, rcx
0x14000a3fd  jz      short loc_14000A43D
0x14000a3ff  mov     [rsp+490h+var_470], r13
0x14000a404  lea     r9, aFailedAddingBo; "Failed adding bootstrap log file name m"...
0x14000a40b  call    ??$LogNumObjects@$$BY0L@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0L@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [11]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[11])
0x14000a410  lea     rax, [rsp+490h+var_440]
0x14000a415  mov     qword ptr [rsp+490h+var_460], rax
0x14000a41a  lea     rax, [rsp+490h+var_460]
0x14000a41f  mov     [rsp+490h+var_470], rax
0x14000a424  lea     r9, asc_14002D4FC; ": {}"
0x14000a42b  mov     r8d, 3
0x14000a431  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a438  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a43d  mov     edx, 0DBh
0x14000a442  jmp     loc_14000A671
0x14000a447  mov     dword ptr [rsp+490h+var_440], ebx
0x14000a44b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a452  test    rcx, rcx
0x14000a455  jz      short loc_14000A4A4
0x14000a457  lea     rax, [r12+10h]
0x14000a45c  add     rax, rsi
0x14000a45f  mov     [rsp+490h+var_470], rax
0x14000a464  lea     r9, aFailedAddingLo; "Failed adding log file name extension: "...
0x14000a46b  mov     edi, 3
0x14000a470  mov     r8d, edi
0x14000a473  xor     edx, edx
0x14000a475  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000a47a  lea     rax, [rsp+490h+var_440]
0x14000a47f  mov     qword ptr [rsp+490h+var_460], rax
0x14000a484  lea     rax, [rsp+490h+var_460]
0x14000a489  mov     [rsp+490h+var_470], rax
0x14000a48e  lea     r9, asc_14002D4FC; ": {}"
0x14000a495  mov     r8d, edi
0x14000a498  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a49f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a4a4  mov     edx, 0E0h
0x14000a4a9  jmp     loc_14000A671
0x14000a4ae  test    r14, r14
0x14000a4b1  jz      loc_14000A5F6
0x14000a4b7  mov     r9, [rsp+490h+var_448]
0x14000a4bc  lea     r8, aSTxt; "%s.txt"
0x14000a4c3  mov     edx, 200h; unsigned __int64
0x14000a4c8  lea     rcx, [rsp+490h+Value]; wchar_t *
0x14000a4cd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000a4d2  mov     ebx, eax
0x14000a4d4  test    eax, eax
0x14000a4d6  jns     short loc_14000A53C
0x14000a4d8  mov     dword ptr [rsp+490h+var_440], eax
0x14000a4dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a4e3  test    rcx, rcx
0x14000a4e6  jz      short loc_14000A532
0x14000a4e8  lea     rax, [rsp+490h+var_448]
0x14000a4ed  mov     [rsp+490h+var_470], rax
0x14000a4f2  lea     r9, aFailedCreating; "Failed creating the offline CBS text lo"...
0x14000a4f9  mov     edi, 3
0x14000a4fe  mov     r8d, edi
0x14000a501  xor     edx, edx
0x14000a503  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000a508  lea     rax, [rsp+490h+var_440]
0x14000a50d  mov     qword ptr [rsp+490h+var_460], rax
0x14000a512  lea     rax, [rsp+490h+var_460]
0x14000a517  mov     [rsp+490h+var_470], rax
0x14000a51c  lea     r9, asc_14002D4FC; ": {}"
0x14000a523  mov     r8d, edi
0x14000a526  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a52d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a532  mov     edx, 0EFh
0x14000a537  jmp     loc_14000A671
0x14000a53c  lea     rdx, [rsp+490h+Value]; lpValue
0x14000a541  lea     rcx, Name; "COMPONENT_BASED_SERVICING_LOGFILE"
0x14000a548  call    cs:__imp_SetEnvironmentVariableW
0x14000a54e  test    eax, eax
0x14000a550  jnz     short loc_14000A5CD
0x14000a552  mov     rcx, [rbp+398h]; this
0x14000a559  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x14000a560  mov     edx, 13Dh; void *
0x14000a565  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a56a  mov     ebx, eax
0x14000a56c  test    eax, eax
0x14000a56e  jns     short loc_14000A5CD
0x14000a570  mov     dword ptr [rsp+490h+var_440], eax
0x14000a574  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a57b  test    rcx, rcx
0x14000a57e  jz      short loc_14000A5C3
0x14000a580  lea     rax, [rsp+490h+Value]
0x14000a585  mov     [rsp+490h+var_470], rax
0x14000a58a  lea     r9, aFailedSettingO; "Failed setting offline CBS text log fil"...
0x14000a591  call    ??$LogNumObjects@$$BY0L@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0L@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [11]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[11])
0x14000a596  lea     rax, [rsp+490h+var_440]
0x14000a59b  mov     qword ptr [rsp+490h+var_460], rax
0x14000a5a0  lea     rax, [rsp+490h+var_460]
0x14000a5a5  mov     [rsp+490h+var_470], rax
0x14000a5aa  lea     r9, asc_14002D4FC; ": {}"
0x14000a5b1  mov     r8d, 3
0x14000a5b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a5be  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a5c3  mov     edx, 0F1h
0x14000a5c8  jmp     loc_14000A671
0x14000a5cd  xor     r8d, r8d; nSize
0x14000a5d0  xor     edx, edx; lpBuffer
0x14000a5d2  lea     rcx, aWindowsTracing; "WINDOWS_TRACING_LOGFILE"
0x14000a5d9  call    cs:__imp_GetEnvironmentVariableW
0x14000a5df  test    eax, eax
0x14000a5e1  jnz     short loc_14000A5F6
0x14000a5e3  lea     rdx, [rsp+490h+Value]; lpValue
0x14000a5e8  lea     rcx, aWindowsTracing; "WINDOWS_TRACING_LOGFILE"
0x14000a5ef  call    cs:__imp_SetEnvironmentVariableW
0x14000a5f5  nop
0x14000a5f6  lea     rcx, [rsp+490h+var_458]
0x14000a5fb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000a600  nop
0x14000a601  lea     rcx, [rsp+490h+var_438]
0x14000a606  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000a60b  xor     eax, eax
0x14000a60d  jmp     loc_14000A69F
0x14000a612  mov     dword ptr [rsp+490h+var_440], ebx
0x14000a616  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a61d  test    rcx, rcx
0x14000a620  jz      short loc_14000A66C
0x14000a622  lea     rax, [rsp+490h+var_448]
0x14000a627  mov     [rsp+490h+var_470], rax
0x14000a62c  lea     r9, aFailedAllocati_0; "Failed allocating log file name: {}"
0x14000a633  mov     edi, 3
0x14000a638  mov     r8d, edi
0x14000a63b  xor     edx, edx
0x14000a63d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000a642  lea     rax, [rsp+490h+var_440]
0x14000a647  mov     qword ptr [rsp+490h+var_460], rax
0x14000a64c  lea     rax, [rsp+490h+var_460]
0x14000a651  mov     [rsp+490h+var_470], rax; int
0x14000a656  lea     r9, asc_14002D4FC; ": {}"
0x14000a65d  mov     r8d, edi
0x14000a660  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000a667  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000a66c  mov     edx, 0D7h; void *
0x14000a671  mov     r9d, ebx; char *
0x14000a674  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pkgmgrshim\\logger."...
0x14000a67b  mov     rcx, [rbp+398h]; this
0x14000a682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a687  nop
0x14000a688  lea     rcx, [rsp+490h+var_458]
0x14000a68d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000a692  nop
0x14000a693  lea     rcx, [rsp+490h+var_438]
0x14000a698  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000a69d  mov     eax, ebx
0x14000a69f  mov     rcx, [rbp+390h+var_30]
0x14000a6a6  xor     rcx, rsp; StackCookie
0x14000a6a9  call    __security_check_cookie
0x14000a6ae  lea     r11, [rsp+490h+var_20]
0x14000a6b6  mov     rbx, [r11+38h]
0x14000a6ba  mov     rsi, [r11+40h]
0x14000a6be  mov     rsp, r11
0x14000a6c1  pop     r14
0x14000a6c3  pop     r13
0x14000a6c5  pop     r12
0x14000a6c7  pop     rdi
0x14000a6c8  pop     rbp
0x14000a6c9  retn
```
