# BeginTracing(wchar_t const *,wchar_t const *,_GUID const *,ulong,unsigned __int64 *)

- ea: `0x1400098b8`
- end: `0x140009f01`
- name: `?BeginTracing@@YAJPEB_W0PEBU_GUID@@KPEA_K@Z`
- size: `1609`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const struct _GUID *, ULONG, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000a1dc`

## callees

- `0x140001fcc`
- `0x140001fd8`
- `0x140002360`
- `0x140002d98`
- `0x1400056ac`
- `0x140005c44`
- `0x140005c7c`
- `0x1400067bc`
- `0x140006c50`
- `0x14000952c`
- `0x14000955c`
- `0x1400098b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009a5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009a5e`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140009ea2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x140009ea2`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140009d2a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x140009d2a`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140009eac`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x140009eac`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x140009e06`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x140009e06`

## pseudocode

```c
__int64 __fastcall BeginTracing(
        const wchar_t *a1,
        const wchar_t *a2,
        const struct _GUID *a3,
        ULONG a4,
        unsigned __int64 *a5)
{
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  unsigned __int64 v22; // r14
  unsigned int v23; // r15d
  unsigned __int64 v24; // rbx
  struct _EVENT_TRACE_PROPERTIES *v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  ULONG started; // eax
  int v30; // edi
  __int64 v31; // rdx
  unsigned int v32; // eax
  signed int v33; // edi
  __int64 v34; // rdx
  unsigned int v35; // eax
  DWORD CurrentProcessId; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+20h] [rbp-E0h]
  ULONG EnableLevel[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v39[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h]
  PEVENT_TRACE_PROPERTIES *p_Properties; // [rsp+48h] [rbp-B8h]
  char v42; // [rsp+50h] [rbp-B0h]
  WCHAR *v43; // [rsp+58h] [rbp-A8h]
  PEVENT_TRACE_PROPERTIES *v44; // [rsp+60h] [rbp-A0h]
  ULONG64 *p_TraceHandle; // [rsp+68h] [rbp-98h]
  char v46; // [rsp+70h] [rbp-90h]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v48[2]; // [rsp+80h] [rbp-80h] BYREF
  ULONG64 TraceHandle; // [rsp+88h] [rbp-78h] BYREF
  WCHAR InstanceName[512]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v40 = -2;
  EnableLevel[0] = a4;
  TraceHandle = 0;
  memset_0(InstanceName, 0, sizeof(InstanceName));
  v48[0] = 0;
  v39[0] = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v48[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No log file specified");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 78;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
      (const char *)v8,
      CurrentProcessId);
    return v8;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    v48[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session name specified");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 79;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    v48[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No provider guid specified");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v13,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 80;
    goto LABEL_5;
  }
  CurrentProcessId = GetCurrentProcessId();
  v14 = StringCchPrintfW(InstanceName, 0x200u, L"%s%ld", a2);
  v8 = v14;
  if ( v14 < 0 )
  {
    v48[0] = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed creating the tracing session name");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v15,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 82;
    goto LABEL_5;
  }
  v16 = -1;
  do
    ++v16;
  while ( InstanceName[v16] );
  v17 = ULongLongToULong(v16 + 1, v48);
  v8 = v17;
  if ( v17 < 0 )
  {
    v48[0] = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert from size_t to ULONG");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v19,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 84;
    goto LABEL_5;
  }
  do
    ++v18;
  while ( a1[v18] );
  v20 = ULongLongToULong(v18 + 1, v39);
  v8 = v20;
  if ( v20 < 0 )
  {
    v48[0] = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert from size_t to ULONG");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v21,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    v10 = 86;
    goto LABEL_5;
  }
  v22 = v39[0];
  v23 = v48[0];
  v24 = 2 * (v39[0] + (unsigned __int64)v48[0]) + 120;
  v25 = (struct _EVENT_TRACE_PROPERTIES *)operator new[](v24);
  Properties = v25;
  if ( !v25 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
      (const char *)0x8007000ELL,
      CurrentProcessId);
    return 2147942414LL;
  }
  p_Properties = &Properties;
  v42 = 1;
  memset_0(v25, 0, v24);
  v26 = ULongLongToULong(v24, &Properties->Wnode.BufferSize);
  v8 = v26;
  if ( v26 < 0 )
  {
    v48[0] = v26;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert BufferSize to ULONG");
      *(_QWORD *)EnableLevel = v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v27,
        3,
        (__int64)": {}",
        (__int64)EnableLevel);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
      (const char *)v8,
      CurrentProcessId);
LABEL_52:
    operator delete(Properties);
    return v8;
  }
  Properties->Wnode.Flags = 0x20000;
  Properties->Wnode.ClientContext = 1;
  Properties->Wnode.Guid = *a3;
  Properties->LogFileMode = 16777220;
  Properties->LoggerNameOffset = 120;
  v28 = 2 * v23 + 120;
  Properties->LogFileNameOffset = v28;
  StringCchCopyW((wchar_t *)((char *)Properties + v28), v22, a1);
  started = StartTraceW(&TraceHandle, InstanceName, Properties);
  v30 = started;
  if ( started == 183 || started == 32 )
  {
    *a5 = 0;
  }
  else
  {
    if ( started )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Start trace failed");
        if ( v30 > 0 )
          v32 = (unsigned __int16)v30 | 0x80070000;
        else
          v32 = v30;
        v48[0] = v32;
        *(_QWORD *)EnableLevel = v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v31,
          3,
          (__int64)": {0}",
          (__int64)EnableLevel);
      }
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x76,
             (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
             (const char *)(unsigned int)v30,
             CurrentProcessId);
      goto LABEL_52;
    }
    v43 = InstanceName;
    v44 = &Properties;
    p_TraceHandle = &TraceHandle;
    v46 = 1;
    v33 = EnableTrace(1u, 0x1Fu, EnableLevel[0], a3, TraceHandle);
    if ( v33 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Enable cbs trace failed");
        if ( v33 > 0 )
          v35 = (unsigned __int16)v33 | 0x80070000;
        else
          v35 = v33;
        EnableLevel[0] = v35;
        *(_QWORD *)v48 = EnableLevel;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v34,
          3,
          (__int64)": {0}",
          (__int64)v48);
      }
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7E,
             (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\logger.cpp",
             (const char *)(unsigned int)v33,
             v37);
      ControlTraceW(0, InstanceName, Properties, 1u);
      CloseTrace(TraceHandle);
      goto LABEL_52;
    }
    *a5 = TraceHandle;
  }
  operator delete(Properties);
  return 0;
}

```

## disassembly

```asm
0x1400098b8  push    rbp
0x1400098ba  push    rbx
0x1400098bb  push    rsi
0x1400098bc  push    rdi
0x1400098bd  push    r12
0x1400098bf  push    r13
0x1400098c1  push    r14
0x1400098c3  push    r15
0x1400098c5  lea     rbp, [rsp-3A8h]
0x1400098cd  sub     rsp, 4A8h
0x1400098d4  mov     [rsp+4E0h+var_4A0], 0FFFFFFFFFFFFFFFEh
0x1400098dd  mov     rax, cs:__security_cookie
0x1400098e4  xor     rax, rsp
0x1400098e7  mov     [rbp+3E0h+var_50], rax
0x1400098ee  mov     [rsp+4E0h+EnableLevel], r9d
0x1400098f3  mov     r12, r8
0x1400098f6  mov     rbx, rdx
0x1400098f9  mov     r13, rcx
0x1400098fc  mov     rsi, [rbp+3E0h+arg_20]
0x140009903  xor     r14d, r14d
0x140009906  mov     [rbp+3E0h+TraceHandle], r14
0x14000990a  xor     edx, edx; Val
0x14000990c  mov     r8d, 400h; Size
0x140009912  lea     rcx, [rbp+3E0h+InstanceName]; void *
0x140009916  call    memset_0
0x14000991b  mov     [rbp+3E0h+var_460], r14d
0x14000991f  mov     [rsp+4E0h+var_4A8], r14d
0x140009924  test    r13, r13
0x140009927  jnz     short loc_14000999D
0x140009929  mov     edi, 80070057h
0x14000992e  mov     [rbp+3E0h+var_460], edi
0x140009931  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009938  test    rcx, rcx
0x14000993b  jz      short loc_14000997B
0x14000993d  lea     r9, aNoLogFileSpeci; "No log file specified"
0x140009944  lea     ebx, [r14+3]
0x140009948  mov     r8d, ebx
0x14000994b  xor     edx, edx
0x14000994d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009952  lea     rax, [rbp+3E0h+var_460]
0x140009956  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x14000995b  lea     rax, [rsp+4E0h+EnableLevel]
0x140009960  mov     qword ptr [rsp+4E0h+var_4C0], rax; int
0x140009965  lea     r9, asc_14002D4FC; ": {}"
0x14000996c  mov     r8d, ebx
0x14000996f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009976  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000997b  mov     edx, 4Eh ; 'N'; void *
0x140009980  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pkgmgrshim\\logger."...
0x140009987  mov     r9d, edi; char *
0x14000998a  mov     rcx, [rbp+3E8h]; this
0x140009991  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009996  mov     eax, edi
0x140009998  jmp     loc_140009EDE
0x14000999d  test    rbx, rbx
0x1400099a0  jnz     short loc_1400099FC
0x1400099a2  mov     edi, 80070057h
0x1400099a7  mov     [rbp+3E0h+var_460], edi
0x1400099aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400099b1  test    rcx, rcx
0x1400099b4  jz      short loc_1400099F5
0x1400099b6  lea     r9, aNoSessionNameS; "No session name specified"
0x1400099bd  mov     ebx, 3
0x1400099c2  mov     r8d, ebx
0x1400099c5  xor     edx, edx
0x1400099c7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400099cc  lea     rax, [rbp+3E0h+var_460]
0x1400099d0  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x1400099d5  lea     rax, [rsp+4E0h+EnableLevel]
0x1400099da  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x1400099df  lea     r9, asc_14002D4FC; ": {}"
0x1400099e6  mov     r8d, ebx
0x1400099e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400099f0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400099f5  mov     edx, 4Fh ; 'O'
0x1400099fa  jmp     short loc_140009980
0x1400099fc  test    r12, r12
0x1400099ff  jnz     short loc_140009A5E
0x140009a01  mov     edi, 80070057h
0x140009a06  mov     [rbp+3E0h+var_460], edi
0x140009a09  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009a10  test    rcx, rcx
0x140009a13  jz      short loc_140009A54
0x140009a15  lea     r9, aNoProviderGuid; "No provider guid specified"
0x140009a1c  lea     ebx, [r12+3]
0x140009a21  mov     r8d, ebx
0x140009a24  xor     edx, edx
0x140009a26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009a2b  lea     rax, [rbp+3E0h+var_460]
0x140009a2f  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009a34  lea     rax, [rsp+4E0h+EnableLevel]
0x140009a39  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x140009a3e  lea     r9, asc_14002D4FC; ": {}"
0x140009a45  mov     r8d, ebx
0x140009a48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009a4f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009a54  mov     edx, 50h ; 'P'
0x140009a59  jmp     loc_140009980
0x140009a5e  call    cs:__imp_GetCurrentProcessId
0x140009a64  mov     [rsp+4E0h+var_4C0], eax; int
0x140009a68  mov     r9, rbx
0x140009a6b  lea     r8, aSLd; "%s%ld"
0x140009a72  mov     edx, 200h; unsigned __int64
0x140009a77  lea     rcx, [rbp+3E0h+InstanceName]; wchar_t *
0x140009a7b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140009a80  mov     edi, eax
0x140009a82  test    eax, eax
0x140009a84  jns     short loc_140009ADE
0x140009a86  mov     [rbp+3E0h+var_460], eax
0x140009a89  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009a90  test    rcx, rcx
0x140009a93  jz      short loc_140009AD4
0x140009a95  lea     r9, aFailedCreating_0; "Failed creating the tracing session nam"...
0x140009a9c  mov     ebx, 3
0x140009aa1  mov     r8d, ebx
0x140009aa4  xor     edx, edx
0x140009aa6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009aab  lea     rax, [rbp+3E0h+var_460]
0x140009aaf  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009ab4  lea     rax, [rsp+4E0h+EnableLevel]
0x140009ab9  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x140009abe  lea     r9, asc_14002D4FC; ": {}"
0x140009ac5  mov     r8d, ebx
0x140009ac8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009acf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009ad4  mov     edx, 52h ; 'R'
0x140009ad9  jmp     loc_140009980
0x140009ade  lea     rax, [rbp+3E0h+InstanceName]
0x140009ae2  or      r9, 0FFFFFFFFFFFFFFFFh
0x140009ae6  mov     rcx, r9
0x140009ae9  inc     rcx
0x140009aec  cmp     [rax+rcx*2], r14w
0x140009af1  jnz     short loc_140009AE9
0x140009af3  inc     rcx; unsigned __int64
0x140009af6  lea     rdx, [rbp+3E0h+var_460]; unsigned int *
0x140009afa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140009aff  mov     edi, eax
0x140009b01  test    eax, eax
0x140009b03  jns     short loc_140009B5D
0x140009b05  mov     [rbp+3E0h+var_460], eax
0x140009b08  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009b0f  test    rcx, rcx
0x140009b12  jz      short loc_140009B53
0x140009b14  lea     r9, aFailedToConver_0; "Failed to convert from size_t to ULONG"
0x140009b1b  mov     ebx, 3
0x140009b20  mov     r8d, ebx
0x140009b23  xor     edx, edx
0x140009b25  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009b2a  lea     rax, [rbp+3E0h+var_460]
0x140009b2e  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009b33  lea     rax, [rsp+4E0h+EnableLevel]
0x140009b38  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x140009b3d  lea     r9, asc_14002D4FC; ": {}"
0x140009b44  mov     r8d, ebx
0x140009b47  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009b4e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009b53  mov     edx, 54h ; 'T'
0x140009b58  jmp     loc_140009980
0x140009b5d  inc     r9
0x140009b60  cmp     [r13+r9*2+0], r14w
0x140009b66  jnz     short loc_140009B5D
0x140009b68  lea     rcx, [r9+1]; unsigned __int64
0x140009b6c  lea     rdx, [rsp+4E0h+var_4A8]; unsigned int *
0x140009b71  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140009b76  mov     edi, eax
0x140009b78  test    eax, eax
0x140009b7a  jns     short loc_140009BD4
0x140009b7c  mov     [rbp+3E0h+var_460], eax
0x140009b7f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009b86  test    rcx, rcx
0x140009b89  jz      short loc_140009BCA
0x140009b8b  lea     r9, aFailedToConver_0; "Failed to convert from size_t to ULONG"
0x140009b92  mov     ebx, 3
0x140009b97  mov     r8d, ebx
0x140009b9a  xor     edx, edx
0x140009b9c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009ba1  lea     rax, [rbp+3E0h+var_460]
0x140009ba5  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009baa  lea     rax, [rsp+4E0h+EnableLevel]
0x140009baf  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x140009bb4  lea     r9, asc_14002D4FC; ": {}"
0x140009bbb  mov     r8d, ebx
0x140009bbe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009bc5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009bca  mov     edx, 56h ; 'V'
0x140009bcf  jmp     loc_140009980
0x140009bd4  mov     r14d, [rsp+4E0h+var_4A8]
0x140009bd9  mov     r15d, [rbp+3E0h+var_460]
0x140009bdd  lea     rax, [r14+r15]
0x140009be1  lea     rbx, ds:78h[rax*2]
0x140009be9  mov     rcx, rbx; unsigned __int64
0x140009bec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140009bf1  mov     [rsp+4E0h+Properties], rax
0x140009bf6  test    rax, rax
0x140009bf9  jnz     short loc_140009C20
0x140009bfb  mov     rcx, [rbp+3E8h]; this
0x140009c02  mov     ebx, 8007000Eh
0x140009c07  mov     r9d, ebx; char *
0x140009c0a  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pkgmgrshim\\logger."...
0x140009c11  lea     edx, [rax+5Dh]; void *
0x140009c14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009c19  mov     eax, ebx
0x140009c1b  jmp     loc_140009EDE
0x140009c20  lea     rcx, [rsp+4E0h+Properties]
0x140009c25  mov     [rsp+4E0h+var_498], rcx
0x140009c2a  mov     [rsp+4E0h+var_490], 1
0x140009c2f  mov     r8, rbx; Size
0x140009c32  xor     edx, edx; Val
0x140009c34  mov     rcx, rax; void *
0x140009c37  call    memset_0
0x140009c3c  mov     rdx, [rsp+4E0h+Properties]; unsigned int *
0x140009c41  mov     rcx, rbx; unsigned __int64
0x140009c44  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140009c49  mov     edi, eax
0x140009c4b  test    eax, eax
0x140009c4d  jns     short loc_140009CBD
0x140009c4f  mov     [rbp+3E0h+var_460], eax
0x140009c52  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009c59  test    rcx, rcx
0x140009c5c  jz      short loc_140009C9D
0x140009c5e  lea     r9, aFailedToConver; "Failed to convert BufferSize to ULONG"
0x140009c65  mov     ebx, 3
0x140009c6a  mov     r8d, ebx
0x140009c6d  xor     edx, edx
0x140009c6f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009c74  lea     rax, [rbp+3E0h+var_460]
0x140009c78  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009c7d  lea     rax, [rsp+4E0h+EnableLevel]
0x140009c82  mov     qword ptr [rsp+4E0h+var_4C0], rax; int
0x140009c87  lea     r9, asc_14002D4FC; ": {}"
0x140009c8e  mov     r8d, ebx
0x140009c91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009c98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009c9d  mov     rcx, [rbp+3E8h]; this
0x140009ca4  mov     r9d, edi; char *
0x140009ca7  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pkgmgrshim\\logger."...
0x140009cae  mov     edx, 62h ; 'b'; void *
0x140009cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009cb8  jmp     loc_140009EB3
0x140009cbd  mov     rax, [rsp+4E0h+Properties]
0x140009cc2  mov     dword ptr [rax+2Ch], 20000h
0x140009cc9  mov     rax, [rsp+4E0h+Properties]
0x140009cce  mov     ebx, 1
0x140009cd3  mov     [rax+28h], ebx
0x140009cd6  movups  xmm0, xmmword ptr [r12]
0x140009cdb  mov     rax, [rsp+4E0h+Properties]
0x140009ce0  movdqu  xmmword ptr [rax+18h], xmm0
0x140009ce5  mov     rax, [rsp+4E0h+Properties]
0x140009cea  mov     dword ptr [rax+40h], 1000004h
0x140009cf1  mov     rax, [rsp+4E0h+Properties]
0x140009cf6  mov     dword ptr [rax+74h], 78h ; 'x'
0x140009cfd  lea     ecx, ds:78h[r15*2]
0x140009d05  mov     rax, [rsp+4E0h+Properties]
0x140009d0a  mov     [rax+70h], ecx
0x140009d0d  add     rcx, [rsp+4E0h+Properties]; wchar_t *
0x140009d12  mov     r8, r13; wchar_t *
0x140009d15  mov     rdx, r14; unsigned __int64
0x140009d18  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140009d1d  mov     r8, [rsp+4E0h+Properties]; Properties
0x140009d22  lea     rdx, [rbp+3E0h+InstanceName]; InstanceName
0x140009d26  lea     rcx, [rbp+3E0h+TraceHandle]; TraceHandle
0x140009d2a  call    cs:__imp_StartTraceW
0x140009d30  mov     edi, eax
0x140009d32  cmp     eax, 0B7h
0x140009d37  jz      loc_140009ECB
0x140009d3d  cmp     eax, 20h ; ' '
0x140009d40  jz      loc_140009ECB
0x140009d46  test    eax, eax
0x140009d48  jz      loc_140009DCE
0x140009d4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009d55  test    rcx, rcx
0x140009d58  jz      short loc_140009DAC
0x140009d5a  lea     r9, aStartTraceFail; "Start trace failed"
0x140009d61  mov     ebx, 3
0x140009d66  mov     r8d, ebx
0x140009d69  xor     edx, edx
0x140009d6b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009d70  test    edi, edi
0x140009d72  jg      short loc_140009D78
0x140009d74  mov     eax, edi
0x140009d76  jmp     short loc_140009D80
0x140009d78  movzx   eax, di
0x140009d7b  or      eax, 80070000h
0x140009d80  mov     [rbp+3E0h+var_460], eax
0x140009d83  lea     rax, [rbp+3E0h+var_460]
0x140009d87  mov     qword ptr [rsp+4E0h+EnableLevel], rax
0x140009d8c  lea     rax, [rsp+4E0h+EnableLevel]
0x140009d91  mov     qword ptr [rsp+4E0h+var_4C0], rax; unsigned int
0x140009d96  lea     r9, a0; ": {0}"
0x140009d9d  mov     r8d, ebx
0x140009da0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009da7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009dac  mov     rcx, [rbp+3E8h]; this
0x140009db3  mov     r9d, edi; char *
0x140009db6  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pkgmgrshim\\logger."...
0x140009dbd  mov     edx, 76h ; 'v'; void *
0x140009dc2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140009dc7  mov     edi, eax
0x140009dc9  jmp     loc_140009EB3
0x140009dce  lea     rax, [rbp+3E0h+InstanceName]
  ... truncated ...
```
