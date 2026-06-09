# FeedbackHubEscalateIfNeeded(_GUID,int)

- ea: `0x18002b418`
- end: `0x18002b8b0`
- name: `?FeedbackHubEscalateIfNeeded@@YAJU_GUID@@H@Z`
- size: `1176`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b3f0`

## callees

- `0x180002ddc`
- `0x18002701c`
- `0x18002772c`
- `0x180027b28`
- `0x18002b418`
- `0x18002c34c`
- `0x18007fca8`
- `0x1800801a4`
- `0x180099590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b891`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b891`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002b529`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002b529`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b574`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b574`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b551`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b551`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b87e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b87e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002b724`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002b724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b6f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b7d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b6f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b7d9`

## string_xrefs

- `0x18002b5b9`: `Escalation already running for another connection, quitting`
- `0x18002b7a6`: `Repromode running, let's make sure it doesn't get deleted`

## pseudocode

```c
__int64 __fastcall FeedbackHubEscalateIfNeeded(struct _GUID *Buf2, unsigned int a2, int a3, int a4)
{
  int v5; // ebx
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  HANDLE MutexW; // rax
  const unsigned __int16 *v12; // rdx
  Microsoft::Diagnostics::UtcApiWrapper *v13; // rcx
  const unsigned __int16 *v14; // r8
  int v15; // r9d
  int *v16; // rdx
  struct _GUID *v17; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int dwCreationFlags; // [rsp+20h] [rbp-39h]
  int lpThreadId; // [rsp+28h] [rbp-31h]
  int v24[2]; // [rsp+40h] [rbp-19h] BYREF
  __int128 *v25; // [rsp+48h] [rbp-11h] BYREF
  int v26[4]; // [rsp+50h] [rbp-9h] BYREF
  struct _GUID v27; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v28[8]; // [rsp+70h] [rbp+17h] BYREF

  v5 = *(_WORD *)&Buf2->Data4[6] & 0x8000;
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    LODWORD(v25) = a2;
    *(_QWORD *)v24 = "Is the ActivityID bit set?";
    v28[0] = Buf2;
    v26[0] = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (_DWORD)Buf2,
      (unsigned int)&byte_1800CC60F,
      a3,
      a4,
      (__int64)v24,
      (__int64)v26,
      (__int64)v28,
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
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          *(_QWORD *)v24 = "Failed to initialize UtcApiWrapper, feedback hub won't work";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            dword_1800DF020,
            (unsigned int)byte_1800CC5CD,
            v9,
            v10,
            (__int64)v24);
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
    if ( g_EscalationStatus == 1 && a2 == 1 && memcmp_0(&xmmword_1800DFDC0, Buf2, 0x10u) )
    {
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        *(_QWORD *)v24 = "Escalation already running for another connection, quitting";
        v16 = &dword_1800CC5AC;
        v17 = (struct _GUID *)v24;
LABEL_21:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v13,
          (_DWORD)v16,
          (_DWORD)v14,
          v15,
          (__int64)v17);
      }
    }
    else
    {
      if ( !g_PreloadedFeedback )
      {
        v18 = Microsoft::Diagnostics::UtcApiWrapper::DownloadLatestSettingsForNamespace2(
                v13,
                v12,
                v14,
                v15,
                dwCreationFlags,
                lpThreadId,
                0x2710u);
        if ( v18 >= 0 )
        {
          if ( (unsigned int)dword_1800DF020 > 5 )
          {
            *(_QWORD *)v24 = "Downloaded settings successfully.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (_DWORD)v13,
              (unsigned int)&byte_1800CC557,
              (_DWORD)v14,
              v15,
              (__int64)v24);
          }
          g_PreloadedFeedback = 1;
        }
        else
        {
          LODWORD(v13) = dword_1800DF020;
          if ( (unsigned int)dword_1800DF020 > 3 )
          {
            v26[0] = v18;
            *(_QWORD *)v24 = "Failed to download latest settings quickly in monitor loop. Using what's present on the machine.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_1800DF020,
              (unsigned int)qword_1800CC578,
              (_DWORD)v14,
              v15,
              (__int64)v24,
              (__int64)v26);
          }
        }
      }
      if ( !a2 )
      {
        if ( g_EscalationStatus )
        {
          if ( (unsigned int)dword_1800DF020 > 5 )
          {
            LODWORD(v25) = 0;
            *(_QWORD *)v24 = "Repromode running, let's queue for deletion";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v13,
              (unsigned int)byte_1800CC503,
              (_DWORD)v14,
              v15,
              (__int64)v24,
              (__int64)&v25);
          }
          g_EscalationStatus = 0;
          qword_1800DFDB0 = GetTickCount64();
          CreateThread(0, 0, FeedbackHubMonitorThread, 0, 0, 0);
        }
        else if ( (unsigned int)dword_1800DF020 > 5 )
        {
          LODWORD(v25) = 0;
          *(_QWORD *)v24 = "Repro mode wasn't running, exiting";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)v13,
            (unsigned int)byte_1800CC52D,
            (_DWORD)v14,
            v15,
            (__int64)v24,
            (__int64)&v25);
        }
        goto LABEL_48;
      }
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        LODWORD(v28[0]) = g_EscalationStatus;
        *(_QWORD *)&v27.Data1 = "we maybe need to start...";
        *(_QWORD *)v24 = Buf2;
        v25 = &xmmword_1800DFDC0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          (_DWORD)v13,
          (unsigned int)word_1800CC49A,
          (_DWORD)v14,
          v15,
          (__int64)&v27,
          (__int64)&v25,
          (__int64)v28,
          (__int64)v24);
      }
      if ( !memcmp_0(&xmmword_1800DFDC0, Buf2, 0x10u) )
      {
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          LODWORD(v25) = a2;
          *(_QWORD *)&v27.Data1 = "Repromode running, let's make sure it doesn't get deleted";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)qword_1800CC470,
            v20,
            v21,
            (__int64)&v27,
            (__int64)&v25);
        }
        g_EscalationStatus = 1;
        qword_1800DFDB8 = GetTickCount64();
        goto LABEL_48;
      }
      if ( !memcmp_0(&xmmword_1800DFDC0, qword_1800BA8F8, 0x10u) )
      {
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          LODWORD(v25) = a2;
          *(_QWORD *)&v27.Data1 = "We need to start the escalation";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)v13,
            (unsigned int)byte_1800CC425,
            (_DWORD)v14,
            v15,
            (__int64)&v27,
            (__int64)&v25);
        }
        v27 = *Buf2;
        v8 = FeedbackHubEscalateInternal(&v27, 1);
        goto LABEL_48;
      }
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        *(_QWORD *)&v27.Data1 = "There is a pending deletion, ignoring new activityID";
        v16 = (int *)&byte_1800CC44F;
        v17 = &v27;
        goto LABEL_21;
      }
    }
LABEL_48:
    SetEvent(g_FeedbackEvent);
    ReleaseMutex(g_FeedbackLock);
    return (unsigned int)v8;
  }
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    *(_QWORD *)v24 = "Exiting early, nothing to do";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)Buf2,
      (unsigned int)&word_1800CC5EE,
      a3,
      a4,
      (__int64)v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b418  push    rbp
0x18002b41a  push    rbx
0x18002b41b  push    rsi
0x18002b41c  push    rdi
0x18002b41d  push    r12
0x18002b41f  push    r13
0x18002b421  lea     rbp, [rsp-2Fh]
0x18002b426  sub     rsp, 88h
0x18002b42d  movzx   ebx, word ptr [rcx+0Eh]
0x18002b431  mov     edi, edx
0x18002b433  mov     eax, cs:dword_1800DF020
0x18002b439  and     ebx, 8000h
0x18002b43f  mov     rsi, rcx
0x18002b442  cmp     eax, 5
0x18002b445  jbe     short loc_18002B48C
0x18002b447  lea     rax, aIsTheActivityi; "Is the ActivityID bit set?"
0x18002b44e  mov     dword ptr [rbp+57h+var_68], edx
0x18002b451  mov     qword ptr [rbp+57h+var_70], rax
0x18002b455  lea     rdx, byte_1800CC60F
0x18002b45c  lea     rax, [rbp+57h+var_68]
0x18002b460  mov     [rbp+57h+var_40], rcx
0x18002b464  mov     [rsp+0B0h+var_78], rax
0x18002b469  lea     rax, [rbp+57h+var_40]
0x18002b46d  mov     qword ptr [rsp+0B0h+var_80], rax
0x18002b472  lea     rax, [rbp+57h+var_60]
0x18002b476  mov     [rsp+0B0h+lpThreadId], rax; int
0x18002b47b  lea     rax, [rbp+57h+var_70]
0x18002b47f  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax; int
0x18002b484  mov     [rbp+57h+var_60], ebx
0x18002b487  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002b48c  test    ebx, ebx
0x18002b48e  jnz     short loc_18002B4C2
0x18002b490  mov     eax, cs:dword_1800DF020
0x18002b496  cmp     eax, 5
0x18002b499  jbe     short loc_18002B4BB
0x18002b49b  lea     rax, aExitingEarlyNo; "Exiting early, nothing to do"
0x18002b4a2  mov     qword ptr [rbp+57h+var_70], rax
0x18002b4a6  lea     rdx, word_1800CC5EE
0x18002b4ad  lea     rax, [rbp+57h+var_70]
0x18002b4b1  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b4b6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002b4bb  xor     eax, eax
0x18002b4bd  jmp     loc_18002B89F
0x18002b4c2  xor     ebx, ebx
0x18002b4c4  cmp     cs:?g_InitWrapper@@3HA, ebx; int g_InitWrapper
0x18002b4ca  lea     r12d, [rbx+1]
0x18002b4ce  jnz     short loc_18002B516
0x18002b4d0  call    ?Initialize@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJK@Z; Microsoft::Diagnostics::UtcApiWrapper::Initialize(ulong)
0x18002b4d5  mov     ebx, eax
0x18002b4d7  test    eax, eax
0x18002b4d9  jns     short loc_18002B50F
0x18002b4db  mov     ecx, cs:dword_1800DF020
0x18002b4e1  cmp     ecx, 2
0x18002b4e4  jbe     loc_18002B89D
0x18002b4ea  lea     rax, aFailedToInitia_0; "Failed to initialize UtcApiWrapper, fee"...
0x18002b4f1  mov     qword ptr [rbp+57h+var_70], rax
0x18002b4f5  lea     rdx, byte_1800CC5CD
0x18002b4fc  lea     rax, [rbp+57h+var_70]
0x18002b500  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b505  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002b50a  jmp     loc_18002B89D
0x18002b50f  mov     cs:?g_InitWrapper@@3HA, r12d; int g_InitWrapper
0x18002b516  mov     rax, cs:?g_FeedbackLock@@3PEAXEA; void * g_FeedbackLock
0x18002b51d  test    rax, rax
0x18002b520  jnz     short loc_18002B53C
0x18002b522  xor     r8d, r8d; lpName
0x18002b525  xor     edx, edx; bInitialOwner
0x18002b527  xor     ecx, ecx; lpMutexAttributes
0x18002b529  call    cs:__imp_CreateMutexW
0x18002b530  nop     dword ptr [rax+rax+00h]
0x18002b535  mov     cs:?g_FeedbackLock@@3PEAXEA, rax; void * g_FeedbackLock
0x18002b53c  cmp     cs:?g_FeedbackEvent@@3PEAXEA, 0; void * g_FeedbackEvent
0x18002b544  jnz     short loc_18002B56B
0x18002b546  xor     r9d, r9d; lpName
0x18002b549  xor     r8d, r8d; bInitialState
0x18002b54c  mov     edx, r12d; bManualReset
0x18002b54f  xor     ecx, ecx; lpEventAttributes
0x18002b551  call    cs:__imp_CreateEventW
0x18002b558  nop     dword ptr [rax+rax+00h]
0x18002b55d  mov     cs:?g_FeedbackEvent@@3PEAXEA, rax; void * g_FeedbackEvent
0x18002b564  mov     rax, cs:?g_FeedbackLock@@3PEAXEA; void * g_FeedbackLock
0x18002b56b  xor     r8d, r8d; bAlertable
0x18002b56e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b571  mov     rcx, rax; hHandle
0x18002b574  call    cs:__imp_WaitForSingleObjectEx
0x18002b57b  nop     dword ptr [rax+rax+00h]
0x18002b580  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, r12d; ESCALATION_STATUS g_EscalationStatus
0x18002b587  lea     r13, xmmword_1800DFDC0
0x18002b58e  jnz     short loc_18002B5DE
0x18002b590  cmp     edi, r12d
0x18002b593  jnz     short loc_18002B5DE
0x18002b595  mov     r8d, 10h; Size
0x18002b59b  mov     rdx, rsi; Buf2
0x18002b59e  mov     rcx, r13; Buf1
0x18002b5a1  call    memcmp_0
0x18002b5a6  test    eax, eax
0x18002b5a8  jz      short loc_18002B5DE
0x18002b5aa  mov     eax, cs:dword_1800DF020
0x18002b5b0  cmp     eax, 5
0x18002b5b3  jbe     loc_18002B877
0x18002b5b9  lea     rax, aEscalationAlre; "Escalation already running for another "...
0x18002b5c0  mov     qword ptr [rbp+57h+var_70], rax
0x18002b5c4  lea     rdx, dword_1800CC5AC
0x18002b5cb  lea     rax, [rbp+57h+var_70]
0x18002b5cf  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b5d4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002b5d9  jmp     loc_18002B877
0x18002b5de  cmp     cs:?g_PreloadedFeedback@@3HA, 0; int g_PreloadedFeedback
0x18002b5e5  jnz     short loc_18002B663
0x18002b5e7  mov     [rsp+0B0h+var_80], 2710h; unsigned int
0x18002b5ef  call    ?DownloadLatestSettingsForNamespace2@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHHI@Z; Microsoft::Diagnostics::UtcApiWrapper::DownloadLatestSettingsForNamespace2(ushort const *,ushort const *,int,int,int,uint)
0x18002b5f4  test    eax, eax
0x18002b5f6  jns     short loc_18002B631
0x18002b5f8  mov     ecx, cs:dword_1800DF020
0x18002b5fe  cmp     ecx, 3
0x18002b601  jbe     short loc_18002B663
0x18002b603  mov     [rbp+57h+var_60], eax
0x18002b606  lea     rdx, qword_1800CC578
0x18002b60d  lea     rax, aFailedToDownlo_0; "Failed to download latest settings quic"...
0x18002b614  mov     qword ptr [rbp+57h+var_70], rax
0x18002b618  lea     rax, [rbp+57h+var_60]
0x18002b61c  mov     [rsp+0B0h+lpThreadId], rax
0x18002b621  lea     rax, [rbp+57h+var_70]
0x18002b625  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b62a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b62f  jmp     short loc_18002B663
0x18002b631  mov     eax, cs:dword_1800DF020
0x18002b637  cmp     eax, 5
0x18002b63a  jbe     short loc_18002B65C
0x18002b63c  lea     rax, aDownloadedSett; "Downloaded settings successfully."
0x18002b643  mov     qword ptr [rbp+57h+var_70], rax
0x18002b647  lea     rdx, byte_1800CC557
0x18002b64e  lea     rax, [rbp+57h+var_70]
0x18002b652  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b657  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002b65c  mov     cs:?g_PreloadedFeedback@@3HA, r12d; int g_PreloadedFeedback
0x18002b663  mov     eax, cs:dword_1800DF020
0x18002b669  test    edi, edi
0x18002b66b  jnz     loc_18002B735
0x18002b671  cmp     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, edi; ESCALATION_STATUS g_EscalationStatus
0x18002b677  jnz     short loc_18002B6B3
0x18002b679  cmp     eax, 5
0x18002b67c  jbe     loc_18002B877
0x18002b682  lea     rax, aReproModeWasnT; "Repro mode wasn't running, exiting"
0x18002b689  mov     dword ptr [rbp+57h+var_68], edi
0x18002b68c  mov     qword ptr [rbp+57h+var_70], rax
0x18002b690  lea     rdx, byte_1800CC52D
0x18002b697  lea     rax, [rbp+57h+var_68]
0x18002b69b  mov     [rsp+0B0h+lpThreadId], rax
0x18002b6a0  lea     rax, [rbp+57h+var_70]
0x18002b6a4  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b6a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b6ae  jmp     loc_18002B877
0x18002b6b3  cmp     eax, 5
0x18002b6b6  jbe     short loc_18002B6E8
0x18002b6b8  lea     rax, aRepromodeRunni_0; "Repromode running, let's queue for dele"...
0x18002b6bf  mov     dword ptr [rbp+57h+var_68], 0
0x18002b6c6  mov     qword ptr [rbp+57h+var_70], rax
0x18002b6ca  lea     rdx, byte_1800CC503
0x18002b6d1  lea     rax, [rbp+57h+var_68]
0x18002b6d5  mov     [rsp+0B0h+lpThreadId], rax
0x18002b6da  lea     rax, [rbp+57h+var_70]
0x18002b6de  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b6e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b6e8  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, 0; ESCALATION_STATUS g_EscalationStatus
0x18002b6f2  call    cs:__imp_GetTickCount64
0x18002b6f9  nop     dword ptr [rax+rax+00h]
0x18002b6fe  xor     r9d, r9d; lpParameter
0x18002b701  mov     [rsp+0B0h+lpThreadId], 0; lpThreadId
0x18002b70a  lea     r8, ?FeedbackHubMonitorThread@@YAKPEAX@Z; lpStartAddress
0x18002b711  mov     cs:qword_1800DFDB0, rax
0x18002b718  xor     edx, edx; dwStackSize
0x18002b71a  mov     [rsp+0B0h+dwCreationFlags], 0; dwCreationFlags
0x18002b722  xor     ecx, ecx; lpThreadAttributes
0x18002b724  call    cs:__imp_CreateThread
0x18002b72b  nop     dword ptr [rax+rax+00h]
0x18002b730  jmp     loc_18002B877
0x18002b735  cmp     eax, 5
0x18002b738  jbe     short loc_18002B786
0x18002b73a  mov     eax, cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A; ESCALATION_STATUS g_EscalationStatus
0x18002b740  lea     rdx, word_1800CC49A
0x18002b747  mov     dword ptr [rbp+57h+var_40], eax
0x18002b74a  lea     rax, aWeMaybeNeedToS; "we maybe need to start..."
0x18002b751  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002b755  lea     rax, [rbp+57h+var_70]
0x18002b759  mov     [rsp+0B0h+var_78], rax
0x18002b75e  lea     rax, [rbp+57h+var_40]
0x18002b762  mov     qword ptr [rsp+0B0h+var_80], rax
0x18002b767  lea     rax, [rbp+57h+var_68]
0x18002b76b  mov     [rsp+0B0h+lpThreadId], rax
0x18002b770  lea     rax, [rbp+57h+var_50]
0x18002b774  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b779  mov     qword ptr [rbp+57h+var_70], rsi
0x18002b77d  mov     [rbp+57h+var_68], r13
0x18002b781  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18002b786  mov     r8d, 10h; Size
0x18002b78c  mov     rdx, rsi; Buf2
0x18002b78f  mov     rcx, r13; Buf1
0x18002b792  call    memcmp_0
0x18002b797  test    eax, eax
0x18002b799  jnz     short loc_18002B7F1
0x18002b79b  mov     eax, cs:dword_1800DF020
0x18002b7a1  cmp     eax, 5
0x18002b7a4  jbe     short loc_18002B7D2
0x18002b7a6  lea     rax, aRepromodeRunni; "Repromode running, let's make sure it d"...
0x18002b7ad  mov     dword ptr [rbp+57h+var_68], edi
0x18002b7b0  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002b7b4  lea     rdx, qword_1800CC470
0x18002b7bb  lea     rax, [rbp+57h+var_68]
0x18002b7bf  mov     [rsp+0B0h+lpThreadId], rax
0x18002b7c4  lea     rax, [rbp+57h+var_50]
0x18002b7c8  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b7cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b7d2  mov     cs:?g_EscalationStatus@@3UESCALATION_STATUS@@A, r12d; ESCALATION_STATUS g_EscalationStatus
0x18002b7d9  call    cs:__imp_GetTickCount64
0x18002b7e0  nop     dword ptr [rax+rax+00h]
0x18002b7e5  mov     cs:qword_1800DFDB8, rax
0x18002b7ec  jmp     loc_18002B877
0x18002b7f1  mov     r8d, 10h; Size
0x18002b7f7  lea     rdx, qword_1800BA8F8; Buf2
0x18002b7fe  mov     rcx, r13; Buf1
0x18002b801  call    memcmp_0
0x18002b806  test    eax, eax
0x18002b808  mov     eax, cs:dword_1800DF020
0x18002b80e  jz      short loc_18002B830
0x18002b810  cmp     eax, 5
0x18002b813  jbe     short loc_18002B877
0x18002b815  lea     rax, aThereIsAPendin; "There is a pending deletion, ignoring n"...
0x18002b81c  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002b820  lea     rdx, byte_1800CC44F
0x18002b827  lea     rax, [rbp+57h+var_50]
0x18002b82b  jmp     loc_18002B5CF
0x18002b830  cmp     eax, 5
0x18002b833  jbe     short loc_18002B861
0x18002b835  lea     rax, aWeNeedToStartT; "We need to start the escalation"
0x18002b83c  mov     dword ptr [rbp+57h+var_68], edi
0x18002b83f  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18002b843  lea     rdx, byte_1800CC425
0x18002b84a  lea     rax, [rbp+57h+var_68]
0x18002b84e  mov     [rsp+0B0h+lpThreadId], rax
0x18002b853  lea     rax, [rbp+57h+var_50]
0x18002b857  mov     qword ptr [rsp+0B0h+dwCreationFlags], rax
0x18002b85c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b861  movups  xmm0, xmmword ptr [rsi]
0x18002b864  mov     edx, r12d; int
0x18002b867  lea     rcx, [rbp+57h+var_50]; struct _GUID
0x18002b86b  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18002b870  call    ?FeedbackHubEscalateInternal@@YAJU_GUID@@H@Z; FeedbackHubEscalateInternal(_GUID,int)
0x18002b875  mov     ebx, eax
0x18002b877  mov     rcx, cs:?g_FeedbackEvent@@3PEAXEA; hEvent
0x18002b87e  call    cs:__imp_SetEvent
0x18002b885  nop     dword ptr [rax+rax+00h]
0x18002b88a  mov     rcx, cs:?g_FeedbackLock@@3PEAXEA; hMutex
0x18002b891  call    cs:__imp_ReleaseMutex
0x18002b898  nop     dword ptr [rax+rax+00h]
0x18002b89d  mov     eax, ebx
0x18002b89f  add     rsp, 88h
0x18002b8a6  pop     r13
0x18002b8a8  pop     r12
0x18002b8aa  pop     rdi
0x18002b8ab  pop     rsi
0x18002b8ac  pop     rbx
0x18002b8ad  pop     rbp
0x18002b8ae  retn
```
