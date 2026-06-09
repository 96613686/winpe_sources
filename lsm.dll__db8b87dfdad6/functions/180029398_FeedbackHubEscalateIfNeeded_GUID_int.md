# FeedbackHubEscalateIfNeeded(_GUID,int)

- ea: `0x180029398`
- end: `0x1800297ff`
- name: `?FeedbackHubEscalateIfNeeded@@YAJU_GUID@@H@Z`
- size: `1127`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029370`

## callees

- `0x180002dc4`
- `0x180025070`
- `0x180025890`
- `0x180025b08`
- `0x180029398`
- `0x18002a348`
- `0x18007b454`
- `0x18007b920`
- `0x180094040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800297e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800297e7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800294a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800294a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800294e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800294e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800294cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800294cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800297da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800297da`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002968c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002968c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029660`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002973b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029660`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002973b`

## string_xrefs

- `0x180029527`: `Escalation already running for another connection, quitting`
- `0x180029708`: `Repromode running, let's make sure it doesn't get deleted`

## pseudocode

```c
__int64 __fastcall FeedbackHubEscalateIfNeeded(struct _GUID *Buf2, unsigned int a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  HANDLE MutexW; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rcx
  const unsigned __int16 *v14; // r8
  __int64 v15; // r9
  unsigned __int8 *v16; // rdx
  struct _GUID *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  int dwCreationFlags; // [rsp+20h] [rbp-39h]
  int lpThreadId; // [rsp+28h] [rbp-31h]
  int v24[2]; // [rsp+40h] [rbp-19h] BYREF
  __int128 *v25; // [rsp+48h] [rbp-11h] BYREF
  int v26[4]; // [rsp+50h] [rbp-9h] BYREF
  struct _GUID v27; // [rsp+60h] [rbp+7h] BYREF
  __int64 v28[8]; // [rsp+70h] [rbp+17h] BYREF

  v5 = *(_WORD *)&Buf2->Data4[6] & 0x8000;
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    LODWORD(v25) = a2;
    *(_QWORD *)v24 = "Is the ActivityID bit set?";
    v28[0] = (__int64)Buf2;
    v26[0] = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (__int64)Buf2,
      (unsigned __int8 *)qword_1800C74A8,
      a3,
      a4,
      (const unsigned __int16 **)v24,
      (__int64)v26,
      v28,
      (__int64)&v25);
  }
  if ( v5 )
  {
    v8 = 0;
    if ( !g_InitWrapper )
    {
      v8 = Microsoft::Diagnostics::UtcApiWrapper::Initialize((Microsoft::Diagnostics::UtcApiWrapper *)Buf2, a2);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          *(_QWORD *)v24 = "Failed to initialize UtcApiWrapper, feedback hub won't work";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)dword_1800DA020,
            (unsigned __int8 *)&word_1800C7466,
            v9,
            v10,
            (const unsigned __int16 **)v24);
        }
        return (unsigned int)v8;
      }
      g_InitWrapper = 1;
    }
    MutexW = g_FeedbackLock;
    if ( !g_FeedbackLock )
    {
      MutexW = CreateMutexW(0, 0, 0);
      g_FeedbackLock = MutexW;
    }
    if ( !g_FeedbackEvent )
    {
      g_FeedbackEvent = CreateEventW(0, 1, 0, 0);
      MutexW = g_FeedbackLock;
    }
    WaitForSingleObjectEx(MutexW, 0xFFFFFFFF, 0);
    if ( g_EscalationStatus == 1 && a2 == 1 && memcmp_0(&xmmword_1800DADB0, Buf2, 0x10u) )
    {
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        *(_QWORD *)v24 = "Escalation already running for another connection, quitting";
        v16 = (unsigned __int8 *)&dword_1800C7424;
        v17 = (struct _GUID *)v24;
LABEL_21:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v13,
          v16,
          (__int64)v14,
          v15,
          (const unsigned __int16 **)v17);
      }
    }
    else
    {
      if ( !g_PreloadedFeedback )
      {
        v18 = Microsoft::Diagnostics::UtcApiWrapper::DownloadLatestSettingsForNamespace2(
                (Microsoft::Diagnostics::UtcApiWrapper *)v13,
                v12,
                v14,
                v15,
                dwCreationFlags,
                lpThreadId,
                0x2710u);
        if ( v18 >= 0 )
        {
          if ( (unsigned int)dword_1800DA020 > 5 )
          {
            *(_QWORD *)v24 = "Downloaded settings successfully.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v13,
              (unsigned __int8 *)byte_1800C7403,
              (__int64)v14,
              v15,
              (const unsigned __int16 **)v24);
          }
          g_PreloadedFeedback = 1;
        }
        else
        {
          v13 = (unsigned int)dword_1800DA020;
          if ( (unsigned int)dword_1800DA020 > 3 )
          {
            v26[0] = v18;
            *(_QWORD *)v24 = "Failed to download latest settings quickly in monitor loop. Using what's present on the machine.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)dword_1800DA020,
              (unsigned __int8 *)&byte_1800C73CF,
              (__int64)v14,
              v15,
              (const unsigned __int16 **)v24,
              (__int64)v26);
          }
        }
      }
      if ( !a2 )
      {
        if ( g_EscalationStatus )
        {
          if ( (unsigned int)dword_1800DA020 > 5 )
          {
            LODWORD(v25) = 0;
            *(_QWORD *)v24 = "Repromode running, let's queue for deletion";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v13,
              (unsigned __int8 *)byte_1800C73A5,
              (__int64)v14,
              v15,
              (const unsigned __int16 **)v24,
              (__int64)&v25);
          }
          g_EscalationStatus = 0;
          qword_1800DADA0 = GetTickCount64();
          CreateThread(0, 0, FeedbackHubMonitorThread, 0, 0, 0);
        }
        else if ( (unsigned int)dword_1800DA020 > 5 )
        {
          LODWORD(v25) = 0;
          *(_QWORD *)v24 = "Repro mode wasn't running, exiting";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned __int8 *)byte_1800C737B,
            (__int64)v14,
            v15,
            (const unsigned __int16 **)v24,
            (__int64)&v25);
        }
        goto LABEL_48;
      }
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        LODWORD(v28[0]) = g_EscalationStatus;
        *(_QWORD *)&v27.Data1 = "we maybe need to start...";
        *(_QWORD *)v24 = Buf2;
        v25 = &xmmword_1800DADB0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v13,
          (int)word_1800C7312,
          (__int64)v14,
          v15,
          (const unsigned __int16 **)&v27,
          (__int64 *)&v25,
          (__int64)v28,
          (__int64 *)v24);
      }
      if ( !memcmp_0(&xmmword_1800DADB0, Buf2, 0x10u) )
      {
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          LODWORD(v25) = a2;
          *(_QWORD *)&v27.Data1 = "Repromode running, let's make sure it doesn't get deleted";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned __int8 *)&byte_1800C72C7,
            v20,
            v21,
            (const unsigned __int16 **)&v27,
            (__int64)&v25);
        }
        g_EscalationStatus = 1;
        qword_1800DADA8 = GetTickCount64();
        goto LABEL_48;
      }
      if ( !memcmp_0(&xmmword_1800DADB0, qword_1800B5760, 0x10u) )
      {
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          LODWORD(v25) = a2;
          *(_QWORD *)&v27.Data1 = "We need to start the escalation";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned __int8 *)&dword_1800C727C,
            (__int64)v14,
            v15,
            (const unsigned __int16 **)&v27,
            (__int64)&v25);
        }
        v27 = *Buf2;
        v8 = FeedbackHubEscalateInternal(&v27, 1);
        goto LABEL_48;
      }
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        *(_QWORD *)&v27.Data1 = "There is a pending deletion, ignoring new activityID";
        v16 = (unsigned __int8 *)byte_1800C72F1;
        v17 = &v27;
        goto LABEL_21;
      }
    }
LABEL_48:
    SetEvent(g_FeedbackEvent);
    ReleaseMutex(g_FeedbackLock);
    return (unsigned int)v8;
  }
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    *(_QWORD *)v24 = "Exiting early, nothing to do";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)Buf2,
      (unsigned __int8 *)byte_1800C7445,
      a3,
      a4,
      (const unsigned __int16 **)v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180029398  push    rbp
0x18002939a  push    rbx
0x18002939b  push    rsi
0x18002939c  push    rdi
0x18002939d  push    r12
0x18002939f  push    r13
0x1800293a1  lea     rbp, [rsp-2Fh]
0x1800293a6  sub     rsp, 88h
0x1800293ad  movzx   ebx, word ptr [rcx+0Eh]
0x1800293b1  mov     edi, edx
0x1800293b3  mov     eax, cs:dword_1800DA020
0x1800293b9  and     ebx, 8000h
0x1800293bf  mov     rsi, rcx
0x1800293c2  cmp     eax, 5
0x1800293c5  jbe     short loc_18002940C
0x1800293c7  lea     rax, aIsTheActivityi; "Is the ActivityID bit set?"
0x1800293ce  mov     dword ptr [rbp+57h+var_68], edx
0x1800293d1  mov     qword ptr [rbp+57h+var_70], rax
0x1800293d5  lea     rdx, qword_1800C74A8
0x1800293dc  lea     rax, [rbp+57h+var_68]
0x1800293e0  mov     [rbp+57h+var_40], rcx
0x1800293e4  mov     [rsp+0B0h+var_78], rax
0x1800293e9  lea     rax, [rbp+57h+var_40]
0x1800293ed  mov     qword ptr [rsp+0B0h+var_80], rax
0x1800293f2  lea     rax, [rbp+57h+var_60]
0x1800293f6  mov     [rsp+0B0h+lpThreadId], rax; int
0x1800293fb  lea     rax, [rbp+57h+var_70]
0x1800293ff  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax; int
0x180029404  mov     [rbp+57h+var_60], ebx
0x180029407  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002940c  test    ebx, ebx
0x18002940e  jnz     short loc_180029442
0x180029410  mov     eax, cs:dword_1800DA020
0x180029416  cmp     eax, 5
0x180029419  jbe     short loc_18002943B
0x18002941b  lea     rax, aExitingEarlyNo; "Exiting early, nothing to do"
0x180029422  mov     qword ptr [rbp+57h+var_70], rax
0x180029426  lea     rdx, byte_1800C7445
0x18002942d  lea     rax, [rbp+57h+var_70]
0x180029431  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029436  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002943b  xor     eax, eax
0x18002943d  jmp     loc_1800297EF
0x180029442  xor     ebx, ebx
0x180029444  cmp     cs:?g_InitWrapper@@3HA, ebx; int g_InitWrapper
0x18002944a  lea     r12d, [rbx+1]
0x18002944e  jnz     short loc_180029496
0x180029450  call    ?Initialize@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJK@Z; Microsoft::Diagnostics::UtcApiWrapper::Initialize(ulong)
0x180029455  mov     ebx, eax
0x180029457  test    eax, eax
0x180029459  jns     short loc_18002948F
0x18002945b  mov     ecx, cs:dword_1800DA020
0x180029461  cmp     ecx, 2
0x180029464  jbe     loc_1800297ED
0x18002946a  lea     rax, aFailedToInitia_0; "Failed to initialize UtcApiWrapper, fee"...
0x180029471  mov     qword ptr [rbp+57h+var_70], rax
0x180029475  lea     rdx, word_1800C7466
0x18002947c  lea     rax, [rbp+57h+var_70]
0x180029480  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029485  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002948a  jmp     loc_1800297ED
0x18002948f  mov     cs:?g_InitWrapper@@3HA, r12d; int g_InitWrapper
0x180029496  mov     rax, cs:?g_FeedbackLock@@3PEAXEA; void * g_FeedbackLock
0x18002949d  test    rax, rax
0x1800294a0  jnz     short loc_1800294B6
0x1800294a2  xor     r8d, r8d; lpName
0x1800294a5  xor     edx, edx; bInitialOwner
0x1800294a7  xor     ecx, ecx; lpMutexAttributes
0x1800294a9  call    cs:__imp_CreateMutexW
0x1800294af  mov     cs:?g_FeedbackLock@@3PEAXEA, rax; void * g_FeedbackLock
0x1800294b6  cmp     cs:?g_FeedbackEvent@@3PEAXEA, 0; void * g_FeedbackEvent
0x1800294be  jnz     short loc_1800294DF
0x1800294c0  xor     r9d, r9d; lpName
0x1800294c3  xor     r8d, r8d; bInitialState
0x1800294c6  mov     edx, r12d; bManualReset
0x1800294c9  xor     ecx, ecx; lpEventAttributes
0x1800294cb  call    cs:__imp_CreateEventW
0x1800294d1  mov     cs:?g_FeedbackEvent@@3PEAXEA, rax; void * g_FeedbackEvent
0x1800294d8  mov     rax, cs:?g_FeedbackLock@@3PEAXEA; void * g_FeedbackLock
0x1800294df  xor     r8d, r8d; bAlertable
0x1800294e2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800294e5  mov     rcx, rax; hHandle
0x1800294e8  call    cs:__imp_WaitForSingleObjectEx
0x1800294ee  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, r12d; ESCALATION_STATUS g_EscalationStatus
0x1800294f5  lea     r13, xmmword_1800DADB0
0x1800294fc  jnz     short loc_18002954C
0x1800294fe  cmp     edi, r12d
0x180029501  jnz     short loc_18002954C
0x180029503  mov     r8d, 10h; Size
0x180029509  mov     rdx, rsi; Buf2
0x18002950c  mov     rcx, r13; Buf1
0x18002950f  call    memcmp_0
0x180029514  test    eax, eax
0x180029516  jz      short loc_18002954C
0x180029518  mov     eax, cs:dword_1800DA020
0x18002951e  cmp     eax, 5
0x180029521  jbe     loc_1800297D3
0x180029527  lea     rax, aEscalationAlre; "Escalation already running for another "...
0x18002952e  mov     qword ptr [rbp+57h+var_70], rax
0x180029532  lea     rdx, dword_1800C7424
0x180029539  lea     rax, [rbp+57h+var_70]
0x18002953d  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029542  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180029547  jmp     loc_1800297D3
0x18002954c  cmp     cs:?g_PreloadedFeedback@@3HA, 0; int g_PreloadedFeedback
0x180029553  jnz     short loc_1800295D1
0x180029555  mov     [rsp+0B0h+var_80], 2710h; unsigned int
0x18002955d  call    ?DownloadLatestSettingsForNamespace2@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHHI@Z; Microsoft::Diagnostics::UtcApiWrapper::DownloadLatestSettingsForNamespace2(ushort const *,ushort const *,int,int,int,uint)
0x180029562  test    eax, eax
0x180029564  jns     short loc_18002959F
0x180029566  mov     ecx, cs:dword_1800DA020
0x18002956c  cmp     ecx, 3
0x18002956f  jbe     short loc_1800295D1
0x180029571  mov     [rbp+57h+var_60], eax
0x180029574  lea     rdx, byte_1800C73CF
0x18002957b  lea     rax, aFailedToDownlo_0; "Failed to download latest settings quic"...
0x180029582  mov     qword ptr [rbp+57h+var_70], rax
0x180029586  lea     rax, [rbp+57h+var_60]
0x18002958a  mov     [rsp+0B0h+lpThreadId], rax
0x18002958f  lea     rax, [rbp+57h+var_70]
0x180029593  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029598  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002959d  jmp     short loc_1800295D1
0x18002959f  mov     eax, cs:dword_1800DA020
0x1800295a5  cmp     eax, 5
0x1800295a8  jbe     short loc_1800295CA
0x1800295aa  lea     rax, aDownloadedSett; "Downloaded settings successfully."
0x1800295b1  mov     qword ptr [rbp+57h+var_70], rax
0x1800295b5  lea     rdx, byte_1800C7403
0x1800295bc  lea     rax, [rbp+57h+var_70]
0x1800295c0  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x1800295c5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800295ca  mov     cs:?g_PreloadedFeedback@@3HA, r12d; int g_PreloadedFeedback
0x1800295d1  mov     eax, cs:dword_1800DA020
0x1800295d7  test    edi, edi
0x1800295d9  jnz     loc_180029697
0x1800295df  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, edi; ESCALATION_STATUS g_EscalationStatus
0x1800295e5  jnz     short loc_180029621
0x1800295e7  cmp     eax, 5
0x1800295ea  jbe     loc_1800297D3
0x1800295f0  lea     rax, aReproModeWasnT; "Repro mode wasn't running, exiting"
0x1800295f7  mov     dword ptr [rbp+57h+var_68], edi
0x1800295fa  mov     qword ptr [rbp+57h+var_70], rax
0x1800295fe  lea     rdx, byte_1800C737B
0x180029605  lea     rax, [rbp+57h+var_68]
0x180029609  mov     [rsp+0B0h+lpThreadId], rax
0x18002960e  lea     rax, [rbp+57h+var_70]
0x180029612  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029617  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002961c  jmp     loc_1800297D3
0x180029621  cmp     eax, 5
0x180029624  jbe     short loc_180029656
0x180029626  lea     rax, aRepromodeRunni_0; "Repromode running, let's queue for dele"...
0x18002962d  mov     dword ptr [rbp+57h+var_68], 0
0x180029634  mov     qword ptr [rbp+57h+var_70], rax
0x180029638  lea     rdx, byte_1800C73A5
0x18002963f  lea     rax, [rbp+57h+var_68]
0x180029643  mov     [rsp+0B0h+lpThreadId], rax
0x180029648  lea     rax, [rbp+57h+var_70]
0x18002964c  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x180029651  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029656  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, 0; ESCALATION_STATUS g_EscalationStatus
0x180029660  call    cs:__imp_GetTickCount64
0x180029666  xor     r9d, r9d; lpParameter
0x180029669  mov     [rsp+0B0h+lpThreadId], 0; lpThreadId
0x180029672  lea     r8, ?FeedbackHubMonitorThread@@YAKPEAX@Z; lpStartAddress
0x180029679  mov     cs:qword_1800DADA0, rax
0x180029680  xor     edx, edx; dwStackSize
0x180029682  mov     [rsp+0B0h+dwCreationFlags], 0; dwCreationFlags
0x18002968a  xor     ecx, ecx; lpThreadAttributes
0x18002968c  call    cs:__imp_CreateThread
0x180029692  jmp     loc_1800297D3
0x180029697  cmp     eax, 5
0x18002969a  jbe     short loc_1800296E8
0x18002969c  mov     eax, cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A; ESCALATION_STATUS g_EscalationStatus
0x1800296a2  lea     rdx, word_1800C7312
0x1800296a9  mov     dword ptr [rbp+57h+var_40], eax
0x1800296ac  lea     rax, aWeMaybeNeedToS; "we maybe need to start..."
0x1800296b3  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x1800296b7  lea     rax, [rbp+57h+var_70]
0x1800296bb  mov     [rsp+0B0h+var_78], rax
0x1800296c0  lea     rax, [rbp+57h+var_40]
0x1800296c4  mov     qword ptr [rsp+0B0h+var_80], rax
0x1800296c9  lea     rax, [rbp+57h+var_68]
0x1800296cd  mov     [rsp+0B0h+lpThreadId], rax
0x1800296d2  lea     rax, [rbp+57h+var_50]
0x1800296d6  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x1800296db  mov     qword ptr [rbp+57h+var_70], rsi
0x1800296df  mov     [rbp+57h+var_68], r13
0x1800296e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800296e8  mov     r8d, 10h; Size
0x1800296ee  mov     rdx, rsi; Buf2
0x1800296f1  mov     rcx, r13; Buf1
0x1800296f4  call    memcmp_0
0x1800296f9  test    eax, eax
0x1800296fb  jnz     short loc_18002974D
0x1800296fd  mov     eax, cs:dword_1800DA020
0x180029703  cmp     eax, 5
0x180029706  jbe     short loc_180029734
0x180029708  lea     rax, aRepromodeRunni; "Repromode running, let's make sure it d"...
0x18002970f  mov     dword ptr [rbp+57h+var_68], edi
0x180029712  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x180029716  lea     rdx, byte_1800C72C7
0x18002971d  lea     rax, [rbp+57h+var_68]
0x180029721  mov     [rsp+0B0h+lpThreadId], rax
0x180029726  lea     rax, [rbp+57h+var_50]
0x18002972a  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002972f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029734  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, r12d; ESCALATION_STATUS g_EscalationStatus
0x18002973b  call    cs:__imp_GetTickCount64
0x180029741  mov     cs:qword_1800DADA8, rax
0x180029748  jmp     loc_1800297D3
0x18002974d  mov     r8d, 10h; Size
0x180029753  lea     rdx, qword_1800B5760; Buf2
0x18002975a  mov     rcx, r13; Buf1
0x18002975d  call    memcmp_0
0x180029762  test    eax, eax
0x180029764  mov     eax, cs:dword_1800DA020
0x18002976a  jz      short loc_18002978C
0x18002976c  cmp     eax, 5
0x18002976f  jbe     short loc_1800297D3
0x180029771  lea     rax, aThereIsAPendin; "There is a pending deletion, ignoring n"...
0x180029778  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002977c  lea     rdx, byte_1800C72F1
0x180029783  lea     rax, [rbp+57h+var_50]
0x180029787  jmp     loc_18002953D
0x18002978c  cmp     eax, 5
0x18002978f  jbe     short loc_1800297BD
0x180029791  lea     rax, aWeNeedToStartT; "We need to start the escalation"
0x180029798  mov     dword ptr [rbp+57h+var_68], edi
0x18002979b  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002979f  lea     rdx, dword_1800C727C
0x1800297a6  lea     rax, [rbp+57h+var_68]
0x1800297aa  mov     [rsp+0B0h+lpThreadId], rax
0x1800297af  lea     rax, [rbp+57h+var_50]
0x1800297b3  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x1800297b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800297bd  movups  xmm0, xmmword ptr [rsi]
0x1800297c0  mov     edx, r12d; int
0x1800297c3  lea     rcx, [rbp+57h+var_50]; struct _GUID
0x1800297c7  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1800297cc  call    ?FeedbackHubEscalateInternal@@YAJU_GUID@@H@Z; FeedbackHubEscalateInternal(_GUID,int)
0x1800297d1  mov     ebx, eax
0x1800297d3  mov     rcx, cs:?g_FeedbackEvent@@3PEAXEA; hEvent
0x1800297da  call    cs:__imp_SetEvent
0x1800297e0  mov     rcx, cs:?g_FeedbackLock@@3PEAXEA; hMutex
0x1800297e7  call    cs:__imp_ReleaseMutex
0x1800297ed  mov     eax, ebx
0x1800297ef  add     rsp, 88h
0x1800297f6  pop     r13
0x1800297f8  pop     r12
0x1800297fa  pop     rdi
0x1800297fb  pop     rsi
0x1800297fc  pop     rbx
0x1800297fd  pop     rbp
0x1800297fe  retn
```
