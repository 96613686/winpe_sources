# Tracer::TraceToFiles(ushort const *,ulong)

- ea: `0x18002bc28`
- end: `0x18002c021`
- name: `?TraceToFiles@Tracer@@QEAAKPEBGK@Z`
- size: `1017`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004ac3c`

## callees

- `0x18002bc28`
- `0x18002c028`
- `0x18002c1a4`
- `0x18002c3c4`
- `0x18002c414`
- `0x180046aec`

## import_xrefs

- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x18002bcbe`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x18002bcbe`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002bfa2`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002bfa2`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002be79`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002bf0c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002be79`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18002bf0c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002bdac`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002bdac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bc61`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bc61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bec1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bc51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002beee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bc51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002beee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bff3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bca6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bca6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfd8`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18002be42`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18002be42`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18002bd72`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18002bd72`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18002bdff`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18002bf93`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18002bdff`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18002bf93`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002bfc1`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002bfc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Tracer::TraceToFiles(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  PEVENT_TRACE_PROPERTIES *p_OwningThread; // rsi
  DWORD LastError; // edi
  struct _EVENT_TRACE_PROPERTIES *v8; // rax
  unsigned __int64 v9; // rdx
  DWORD v10; // ecx
  int v11; // eax
  TRACEHANDLE *p_LockCount; // r12
  REGHANDLE *v13; // r13
  ULONG v14; // eax
  unsigned int v15; // eax
  ULONG v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  REGHANDLE DebugInfo; // rcx
  TRACEHANDLE v20; // rcx
  HANDLE *v21; // rsi
  unsigned int TraceInformation; // [rsp+40h] [rbp-48h] BYREF
  PEVENT_TRACE_PROPERTIES *v24; // [rsp+48h] [rbp-40h]
  TRACEHANDLE *v25; // [rsp+50h] [rbp-38h]
  HANDLE *p_DebugInfo; // [rsp+58h] [rbp-30h]

  v4 = this;
  TraceInformation = 0;
  EnterCriticalSection(this);
  EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 0, 0, 0);
  p_DebugInfo = (HANDLE *)&v4[1].DebugInfo;
  v4[1].DebugInfo = EventW;
  p_OwningThread = (PEVENT_TRACE_PROPERTIES *)&v4[1].OwningThread;
  v24 = (PEVENT_TRACE_PROPERTIES *)&v4[1].OwningThread;
  if ( !EventW )
  {
    LastError = GetLastError();
    goto LABEL_36;
  }
  v8 = (struct _EVENT_TRACE_PROPERTIES *)LocalAlloc(0x40u, 0x880u);
  *p_OwningThread = v8;
  if ( !v8 )
  {
    LastError = 14;
    goto LABEL_36;
  }
  v10 = 8 * GetActiveProcessorCount(0xFFFFu);
  if ( v10 >= 0x40 )
  {
    if ( v10 > 0x400 )
      v10 = 1024;
  }
  else
  {
    v10 = 64;
  }
  (*p_OwningThread)->Wnode.BufferSize = 2176;
  (*p_OwningThread)->Wnode.Flags = 0x20000;
  (*p_OwningThread)->Wnode.Guid = (GUID)xmmword_18009D528;
  (*p_OwningThread)->MaximumFileSize = 200;
  (*p_OwningThread)->BufferSize = 64;
  (*p_OwningThread)->MinimumBuffers = 16;
  (*p_OwningThread)->MaximumBuffers = v10;
  (*p_OwningThread)->LogFileMode = 33554433;
  (*p_OwningThread)->LoggerNameOffset = 120;
  (*p_OwningThread)->LogFileNameOffset = (*p_OwningThread)->LoggerNameOffset + 8;
  v11 = StringCbCopyW((unsigned __int16 *)((char *)*p_OwningThread + (*p_OwningThread)->LogFileNameOffset), v9, a2);
  if ( v11 < 0 )
  {
    LastError = (unsigned __int16)v11;
    goto LABEL_36;
  }
  p_LockCount = (TRACEHANDLE *)&v4[1].LockCount;
  v25 = (TRACEHANDLE *)&v4[1].LockCount;
  LastError = StartTraceW((PTRACEHANDLE)&v4[1].LockCount, L"Power Efficiency Diagnostic Logger", *p_OwningThread);
  if ( LastError )
  {
    if ( LastError == 183 )
      LastError = -1073479167;
    *p_LockCount = 0;
    goto LABEL_36;
  }
  v13 = (REGHANDLE *)&v4[2];
  LastError = EventRegister(&ENERGY_ETW_PROVIDER, 0, 0, (PREGHANDLE)&v4[2]);
  if ( LastError )
  {
    *v13 = 0;
    goto LABEL_36;
  }
  v14 = EnableTraceEx2(*p_LockCount, &ENERGY_ETW_PROVIDER, 1u, 0, 0, 0, 0xFFFFFFFF, 0);
  LastError = v14;
  if ( !v14 )
  {
    try
    {
      v15 = Tracer::TraceEnergyDetails((Tracer *)v4, *v13);
    }
    catch ( std::bad_alloc )
    {
      v4 = this;
      LastError = 14;
      p_OwningThread = v24;
      p_LockCount = v25;
      goto LABEL_34;
    }
    catch ( ... )
    {
      v4 = this;
      LastError = 1627;
      p_OwningThread = v24;
      p_LockCount = v25;
      goto LABEL_34;
    }
    LastError = v15;
    if ( v15 )
      goto LABEL_34;
    TraceInformation = Tracer::NtklEnableFlags((Tracer *)v4);
    v16 = TraceSetInformation(*p_LockCount, TraceSystemTraceEnableFlagsInfo, &TraceInformation, 4u);
    LastError = v16;
    if ( v16 )
      goto LABEL_34;
    try
    {
      v17 = Tracer::EnableEtwProviders((Tracer *)v4, *p_LockCount);
    }
    catch ( std::bad_alloc )
    {
      v4 = this;
      LastError = 14;
      p_OwningThread = v24;
      p_LockCount = v25;
      goto LABEL_34;
    }
    catch ( ... )
    {
      v4 = this;
      LastError = 1627;
      p_OwningThread = v24;
      p_LockCount = v25;
      goto LABEL_34;
    }
    LastError = v17;
    if ( v17 )
      goto LABEL_34;
    LastError = EventWrite(*v13, &ENERGY_EVT_TRACE_START, 0, 0);
    if ( !LastError )
    {
      LeaveCriticalSection(v4);
      v18 = 60;
      if ( a3 != -1 )
        v18 = a3;
      if ( !v18 )
        v18 = 1;
      LastError = WaitForSingleObject(*p_DebugInfo, 1000 * v18);
      if ( LastError == 258 )
      {
        EnterCriticalSection(v4);
        if ( *v13 )
          LastError = EventWrite(*v13, &ENERGY_EVT_TRACE_STOP, 0, 0);
      }
      else
      {
        LastError = 1627;
        EnterCriticalSection(v4);
      }
    }
    if ( *p_LockCount )
    {
      Tracer::DisableEtwProviders((Tracer *)v4, *p_LockCount);
LABEL_34:
      if ( *p_LockCount )
        EnableTraceEx2(*p_LockCount, &ENERGY_ETW_PROVIDER, 0, 0, 0, 0, 0xFFFFFFFF, 0);
    }
  }
LABEL_36:
  DebugInfo = (REGHANDLE)v4[2].DebugInfo;
  if ( DebugInfo )
  {
    EventUnregister(DebugInfo);
    v4[2].DebugInfo = 0;
  }
  v20 = *(_QWORD *)&v4[1].LockCount;
  if ( v20 )
  {
    ControlTraceW(v20, 0, *p_OwningThread, 1u);
    *(_QWORD *)&v4[1].LockCount = 0;
  }
  if ( *p_OwningThread )
  {
    LocalFree(*p_OwningThread);
    *p_OwningThread = 0;
  }
  v21 = p_DebugInfo;
  if ( *p_DebugInfo )
  {
    CloseHandle(*p_DebugInfo);
    *v21 = 0;
  }
  LeaveCriticalSection(v4);
  return LastError;
}

```

## disassembly

```asm
0x18002bc28  mov     rax, rsp
0x18002bc2b  mov     [rax+10h], rsi
0x18002bc2f  mov     [rax+18h], r8d
0x18002bc33  mov     [rax+8], rcx
0x18002bc37  push    rdi
0x18002bc38  push    r12
0x18002bc3a  push    r13
0x18002bc3c  push    r14
0x18002bc3e  push    r15
0x18002bc40  sub     rsp, 60h
0x18002bc44  mov     rdi, rdx
0x18002bc47  mov     r14, rcx
0x18002bc4a  mov     dword ptr [rax-48h], 0
0x18002bc51  call    cs:__imp_EnterCriticalSection
0x18002bc57  xor     r9d, r9d; lpName
0x18002bc5a  xor     r8d, r8d; bInitialState
0x18002bc5d  xor     edx, edx; bManualReset
0x18002bc5f  xor     ecx, ecx; lpEventAttributes
0x18002bc61  call    cs:__imp_CreateEventW
0x18002bc67  lea     rsi, [r14+28h]
0x18002bc6b  mov     [rsp+88h+var_30], rsi
0x18002bc70  mov     [rsi], rax
0x18002bc73  lea     rsi, [r14+38h]
0x18002bc77  mov     [rsp+88h+var_40], rsi
0x18002bc7c  test    rax, rax
0x18002bc7f  jnz     short loc_18002BC94
0x18002bc81  call    cs:__imp_GetLastError
0x18002bc87  mov     edi, eax
0x18002bc89  mov     r15d, 1
0x18002bc8f  jmp     loc_18002BF99
0x18002bc94  mov     r12d, 880h
0x18002bc9a  mov     edx, r12d; uBytes
0x18002bc9d  mov     r15d, 40h ; '@'
0x18002bca3  mov     ecx, r15d; uFlags
0x18002bca6  call    cs:__imp_LocalAlloc
0x18002bcac  mov     [rsi], rax
0x18002bcaf  test    rax, rax
0x18002bcb2  jnz     short loc_18002BCB9
0x18002bcb4  lea     edi, [rax+0Eh]
0x18002bcb7  jmp     short loc_18002BC89
0x18002bcb9  mov     ecx, 0FFFFh; GroupNumber
0x18002bcbe  call    cs:__imp_GetActiveProcessorCount
0x18002bcc4  lea     ecx, ds:0[rax*8]
0x18002bccb  cmp     ecx, r15d
0x18002bcce  jnb     short loc_18002BCD5
0x18002bcd0  mov     ecx, r15d
0x18002bcd3  jmp     short loc_18002BCDF
0x18002bcd5  mov     eax, 400h
0x18002bcda  cmp     ecx, eax
0x18002bcdc  cmova   ecx, eax
0x18002bcdf  mov     rax, [rsi]
0x18002bce2  mov     [rax], r12d
0x18002bce5  mov     rax, [rsi]
0x18002bce8  mov     dword ptr [rax+2Ch], 20000h
0x18002bcef  mov     rax, [rsi]
0x18002bcf2  movups  xmm0, cs:xmmword_18009D528
0x18002bcf9  movdqu  xmmword ptr [rax+18h], xmm0
0x18002bcfe  mov     rax, [rsi]
0x18002bd01  mov     dword ptr [rax+3Ch], 0C8h
0x18002bd08  mov     rax, [rsi]
0x18002bd0b  mov     [rax+30h], r15d
0x18002bd0f  mov     rax, [rsi]
0x18002bd12  mov     dword ptr [rax+34h], 10h
0x18002bd19  mov     rax, [rsi]
0x18002bd1c  mov     [rax+38h], ecx
0x18002bd1f  mov     rax, [rsi]
0x18002bd22  mov     dword ptr [rax+40h], 2000001h
0x18002bd29  mov     rax, [rsi]
0x18002bd2c  mov     dword ptr [rax+74h], 78h ; 'x'
0x18002bd33  mov     rcx, [rsi]
0x18002bd36  mov     eax, [rcx+74h]
0x18002bd39  add     eax, 8
0x18002bd3c  mov     [rcx+70h], eax
0x18002bd3f  mov     rax, [rsi]
0x18002bd42  mov     ecx, [rax+70h]
0x18002bd45  add     rcx, rax; unsigned __int16 *
0x18002bd48  mov     r8, rdi; unsigned __int16 *
0x18002bd4b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bd50  test    eax, eax
0x18002bd52  jns     short loc_18002BD5C
0x18002bd54  movzx   edi, ax
0x18002bd57  jmp     loc_18002BC89
0x18002bd5c  lea     r12, [r14+30h]
0x18002bd60  mov     [rsp+88h+var_38], r12
0x18002bd65  mov     r8, [rsi]; Properties
0x18002bd68  lea     rdx, InstanceName; "Power Efficiency Diagnostic Logger"
0x18002bd6f  mov     rcx, r12; TraceHandle
0x18002bd72  call    cs:__imp_StartTraceW
0x18002bd78  mov     edi, eax
0x18002bd7a  test    eax, eax
0x18002bd7c  jz      short loc_18002BD99
0x18002bd7e  mov     eax, 0C0040201h
0x18002bd83  cmp     edi, 0B7h
0x18002bd89  cmovz   edi, eax
0x18002bd8c  mov     qword ptr [r12], 0
0x18002bd94  jmp     loc_18002BC89
0x18002bd99  lea     r13, [r14+50h]
0x18002bd9d  mov     r9, r13; RegHandle
0x18002bda0  xor     r8d, r8d; CallbackContext
0x18002bda3  xor     edx, edx; EnableCallback
0x18002bda5  lea     rcx, ENERGY_ETW_PROVIDER; ProviderId
0x18002bdac  call    cs:__imp_EventRegister
0x18002bdb2  mov     edi, eax
0x18002bdb4  mov     r15d, 1
0x18002bdba  test    eax, eax
0x18002bdbc  jz      short loc_18002BDCB
0x18002bdbe  mov     qword ptr [r13+0], 0
0x18002bdc6  jmp     loc_18002BF99
0x18002bdcb  mov     [rsp+88h+EnableParameters], 0; EnableParameters
0x18002bdd4  mov     [rsp+88h+Timeout], 0FFFFFFFFh; Timeout
0x18002bddc  mov     [rsp+88h+MatchAllKeyword], 0; MatchAllKeyword
0x18002bde5  mov     [rsp+88h+MatchAnyKeyword], 0; MatchAnyKeyword
0x18002bdee  xor     r9d, r9d; Level
0x18002bdf1  mov     r8d, r15d; ControlCode
0x18002bdf4  lea     rdx, ENERGY_ETW_PROVIDER; ProviderId
0x18002bdfb  mov     rcx, [r12]; TraceHandle
0x18002bdff  call    cs:__imp_EnableTraceEx2
0x18002be05  mov     edi, eax
0x18002be07  test    eax, eax
0x18002be09  jnz     loc_18002BF99
0x18002be0f  mov     rdx, [r13+0]; RegHandle
0x18002be13  mov     rcx, r14; this
0x18002be16  call    ?TraceEnergyDetails@Tracer@@AEAAK_K@Z; Tracer::TraceEnergyDetails(unsigned __int64)
0x18002be1b  mov     edi, eax
0x18002be1d  test    eax, eax
0x18002be1f  jnz     loc_18002BF58
0x18002be25  mov     rcx, r14; this
0x18002be28  call    ?NtklEnableFlags@Tracer@@AEAAKXZ; Tracer::NtklEnableFlags(void)
0x18002be2d  mov     [rsp+88h+TraceInformation], eax
0x18002be31  mov     edx, 4; InformationClass
0x18002be36  mov     r9d, edx; InformationLength
0x18002be39  lea     r8, [rsp+88h+TraceInformation]; TraceInformation
0x18002be3e  mov     rcx, [r12]; SessionHandle
0x18002be42  call    cs:__imp_TraceSetInformation
0x18002be48  mov     edi, eax
0x18002be4a  test    eax, eax
0x18002be4c  jnz     loc_18002BF58
0x18002be52  mov     rdx, [r12]; unsigned __int64
0x18002be56  mov     rcx, r14; this
0x18002be59  call    ?EnableEtwProviders@Tracer@@AEAAK_K@Z; Tracer::EnableEtwProviders(unsigned __int64)
0x18002be5e  mov     edi, eax
0x18002be60  test    eax, eax
0x18002be62  jnz     loc_18002BF58
0x18002be68  xor     r9d, r9d; UserData
0x18002be6b  xor     r8d, r8d; UserDataCount
0x18002be6e  lea     rdx, ENERGY_EVT_TRACE_START; EventDescriptor
0x18002be75  mov     rcx, [r13+0]; RegHandle
0x18002be79  call    cs:__imp_EventWrite
0x18002be7f  mov     edi, eax
0x18002be81  mov     [rsp+88h+arg_18], eax
0x18002be88  test    eax, eax
0x18002be8a  jnz     loc_18002BF1B
0x18002be90  mov     rcx, r14; lpCriticalSection
0x18002be93  call    cs:__imp_LeaveCriticalSection
0x18002be99  lea     eax, [rdi+3Ch]
0x18002be9c  cmp     [rsp+88h+arg_10], 0FFFFFFFFh
0x18002bea4  cmovnz  eax, [rsp+88h+arg_10]
0x18002beac  cmp     eax, r15d
0x18002beaf  cmovb   eax, r15d
0x18002beb3  imul    edx, eax, 3E8h; dwMilliseconds
0x18002beb9  mov     rcx, [rsp+88h+var_30]
0x18002bebe  mov     rcx, [rcx]; hHandle
0x18002bec1  call    cs:__imp_WaitForSingleObject
0x18002bec7  mov     edi, eax
0x18002bec9  mov     [rsp+88h+arg_18], eax
0x18002bed0  mov     rcx, r14; lpCriticalSection
0x18002bed3  cmp     eax, 102h
0x18002bed8  jz      short loc_18002BEEE
0x18002beda  mov     edi, 65Bh
0x18002bedf  mov     [rsp+88h+arg_18], edi
0x18002bee6  call    cs:__imp_EnterCriticalSection
0x18002beec  jmp     short loc_18002BF1B
0x18002beee  call    cs:__imp_EnterCriticalSection
0x18002bef4  cmp     qword ptr [r13+0], 0
0x18002bef9  jz      short loc_18002BF1B
0x18002befb  xor     r9d, r9d; UserData
0x18002befe  xor     r8d, r8d; UserDataCount
0x18002bf01  lea     rdx, ENERGY_EVT_TRACE_STOP; EventDescriptor
0x18002bf08  mov     rcx, [r13+0]; RegHandle
0x18002bf0c  call    cs:__imp_EventWrite
0x18002bf12  mov     edi, eax
0x18002bf14  mov     [rsp+88h+arg_18], eax
0x18002bf1b  cmp     qword ptr [r12], 0
0x18002bf20  jz      short loc_18002BF99
0x18002bf22  mov     rdx, [r12]; unsigned __int64
0x18002bf26  mov     rcx, r14; this
0x18002bf29  call    ?DisableEtwProviders@Tracer@@AEAAX_K@Z; Tracer::DisableEtwProviders(unsigned __int64)
0x18002bf2e  nop
0x18002bf2f  jmp     short loc_18002BF58
0x18002bf31  jmp     short loc_18002BF39
0x18002bf33  jmp     short loc_18002BF39
0x18002bf35  jmp     short loc_18002BF39
0x18002bf37  jmp     short $+2
0x18002bf39  mov     r15d, 1
0x18002bf3f  mov     r14, [rsp+88h+arg_0]
0x18002bf47  mov     edi, [rsp+88h+arg_18]
0x18002bf4e  mov     rsi, [rsp+88h+var_40]
0x18002bf53  mov     r12, [rsp+88h+var_38]
0x18002bf58  cmp     qword ptr [r12], 0
0x18002bf5d  jz      short loc_18002BF99
0x18002bf5f  mov     [rsp+88h+EnableParameters], 0; EnableParameters
0x18002bf68  mov     [rsp+88h+Timeout], 0FFFFFFFFh; Timeout
0x18002bf70  mov     [rsp+88h+MatchAllKeyword], 0; MatchAllKeyword
0x18002bf79  mov     [rsp+88h+MatchAnyKeyword], 0; MatchAnyKeyword
0x18002bf82  xor     r9d, r9d; Level
0x18002bf85  xor     r8d, r8d; ControlCode
0x18002bf88  lea     rdx, ENERGY_ETW_PROVIDER; ProviderId
0x18002bf8f  mov     rcx, [r12]; TraceHandle
0x18002bf93  call    cs:__imp_EnableTraceEx2
0x18002bf99  mov     rcx, [r14+50h]; RegHandle
0x18002bf9d  test    rcx, rcx
0x18002bfa0  jz      short loc_18002BFB0
0x18002bfa2  call    cs:__imp_EventUnregister
0x18002bfa8  mov     qword ptr [r14+50h], 0
0x18002bfb0  mov     rcx, [r14+30h]; TraceHandle
0x18002bfb4  test    rcx, rcx
0x18002bfb7  jz      short loc_18002BFCF
0x18002bfb9  mov     r9d, r15d; ControlCode
0x18002bfbc  mov     r8, [rsi]; Properties
0x18002bfbf  xor     edx, edx; InstanceName
0x18002bfc1  call    cs:__imp_ControlTraceW
0x18002bfc7  mov     qword ptr [r14+30h], 0
0x18002bfcf  cmp     qword ptr [rsi], 0
0x18002bfd3  jz      short loc_18002BFE5
0x18002bfd5  mov     rcx, [rsi]; hMem
0x18002bfd8  call    cs:__imp_LocalFree
0x18002bfde  mov     qword ptr [rsi], 0
0x18002bfe5  mov     rsi, [rsp+88h+var_30]
0x18002bfea  cmp     qword ptr [rsi], 0
0x18002bfee  jz      short loc_18002C000
0x18002bff0  mov     rcx, [rsi]; hObject
0x18002bff3  call    cs:__imp_CloseHandle
0x18002bff9  mov     qword ptr [rsi], 0
0x18002c000  mov     rcx, r14; lpCriticalSection
0x18002c003  call    cs:__imp_LeaveCriticalSection
0x18002c009  mov     eax, edi
0x18002c00b  mov     rsi, [rsp+88h+arg_8]
0x18002c013  add     rsp, 60h
0x18002c017  pop     r15
0x18002c019  pop     r14
0x18002c01b  pop     r13
0x18002c01d  pop     r12
0x18002c01f  pop     rdi
0x18002c020  retn
```
