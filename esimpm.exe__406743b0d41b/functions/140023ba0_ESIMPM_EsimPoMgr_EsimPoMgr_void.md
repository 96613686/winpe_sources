# ESIMPM::EsimPoMgr::~EsimPoMgr(void)

- ea: `0x140023ba0`
- end: `0x140023ffd`
- name: `??1EsimPoMgr@ESIMPM@@QEAA@XZ`
- size: `1117`
- prototype: `void __fastcall(ESIMPM::EsimPoMgr *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034cf8`
- `0x14003dc10`

## callees

- `0x140001278`
- `0x140001308`
- `0x140003244`
- `0x140013df8`
- `0x140014f64`
- `0x140020620`
- `0x14002327c`
- `0x140023ae0`
- `0x140023ba0`
- `0x140024004`
- `0x14002fb4c`
- `0x1400350e4`
- `0x14003518c`
- `0x140035420`
- `0x1400354f8`
- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`
- `0x140035994`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140023d15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140023d15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140023d07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140023d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ec3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140023d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140023d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140023d27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140023d27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023fa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023fa4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x140023bf5`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x140023bf5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140023cc0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140023cc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x140023eb9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x140023eb9`
- `wwapi!WwanCloseHandle` at `0x140023c11`
- `wwapi!WwanCloseHandle` at `0x140023c11`
- `ext-ms-win-ntuser-powermanagement-l1-1-0!UnregisterSuspendResumeNotification` at `0x140023c65`
- `ext-ms-win-ntuser-powermanagement-l1-1-0!UnregisterSuspendResumeNotification` at `0x140023c65`

## string_xrefs

- `0x140023dbb`: `ESIMPM::TimerWrapper::DeleteTimer`
- `0x140023df2`: ` Timer Stop Completed`
- `0x140023e14`: ` Timer Deinitialization Completed`
- `0x140023f51`: `Timer Library Deinitialization Completed`
- `0x140023ccd`: `RtlUnsubscribeWnfNotificationWaitForCompletion failed (ntStatus: %08x)`

## pseudocode

```c
void __fastcall ESIMPM::EsimPoMgr::~EsimPoMgr(ESIMPM::EsimPoMgr *this, __int64 a2, __int64 a3, __int64 a4)
{
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  BOOL v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // eax
  char *v15; // rsi
  volatile signed __int32 *v16; // rbx
  void *v17; // rdx
  HANDLE v18; // rsi
  _BYTE *v19; // rcx
  unsigned int v20; // ebx
  DWORD LastError; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  void *v25; // rcx
  void *v26; // rbx
  const char *v27; // [rsp+60h] [rbp+8h] BYREF
  const char *v28; // [rsp+68h] [rbp+10h] BYREF

  *(_QWORD *)this = &ESIMPM::EsimPoMgr::`vftable';
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v27 = "ESIMPM::EsimPoMgr::~EsimPoMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)byte_14006AE43,
      a3,
      a4,
      (const unsigned __int16 **)&v27);
  }
  v5 = (void *)*((_QWORD *)this + 121);
  if ( v5 )
  {
    PowerSettingUnregisterNotification(v5);
    *((_QWORD *)this + 121) = 0;
  }
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    WwanCloseHandle(v6, 0);
    *((_QWORD *)this + 1) = 0;
  }
  ESIMPM::LpaHelper::DeInitialize((ESIMPM::EsimPoMgr *)((char *)this + 128));
  if ( *((_QWORD *)this + 122) )
  {
    if ( (unsigned int)dword_140075078 > 4 )
    {
      v27 = "ESIMPM::EsimPoMgr::~EsimPoMgr";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (__int64)word_14006AE0A,
        v8,
        v9,
        (const unsigned __int16 **)&v27);
    }
    v10 = UnregisterSuspendResumeNotification(*((HPOWERNOTIFY *)this + 122));
    *((_QWORD *)this + 122) = 0;
    if ( !v10 && (unsigned int)dword_140075078 > 2 )
    {
      v28 = "ESIMPM::EsimPoMgr::~EsimPoMgr";
      LODWORD(v27) = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (__int64)byte_14006ADC1,
        v12,
        v13,
        (__int64)&v27,
        (const unsigned __int16 **)&v28);
    }
  }
  if ( *((_QWORD *)this + 124) )
  {
    v14 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v14 < 0 )
      ESIMPM::Log::Error(
        "ESIMPM::EsimPoMgr::DeinitializePolicyHandler",
        0,
        L"RtlUnsubscribeWnfNotificationWaitForCompletion failed (ntStatus: %08x)",
        (unsigned int)v14);
  }
  *((_QWORD *)this + 124) = 0;
  v15 = (char *)ESIMPM::MessageDispatcher::s_Dispatcher;
  if ( ESIMPM::MessageDispatcher::s_Dispatcher )
  {
    if ( *((_BYTE *)ESIMPM::MessageDispatcher::s_Dispatcher + 56) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)ESIMPM::MessageDispatcher::s_Dispatcher + 16));
      v15[56] = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 16));
      CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v15 + 17), 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v15 + 17));
      *((_QWORD *)v15 + 17) = 0;
    }
    ESIMPM::MessageDispatcher::s_Dispatcher = 0;
    v16 = (volatile signed __int32 *)qword_140075D08;
    qword_140075D08 = 0;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 124, 0, 1) )
  {
    AcquireWriteLock(*((_QWORD *)this + 61), (char *)this + 384, "ESIMPM::TimerWrapper::DeleteTimer", 48);
    StopTimer(*((_QWORD *)this + 61), "ESIMPM::TimerWrapper::DeleteTimer");
    ReleaseWriteLock(*((_QWORD *)this + 61), (char *)this + 384, "ESIMPM::TimerWrapper::DeleteTimer", 50);
    ESIMPM::Log::Info("ESIMPM::TimerWrapper::DeleteTimer", 0, L" Timer Stop Completed");
    ESIMPM::WwanTimerDeleteTimer(*((ESIMPM **)this + 61), v17);
    DeleteReadWriteLock((char *)this + 384);
    ESIMPM::Log::Info("ESIMPM::TimerWrapper::DeleteTimer", 0, L" Timer Deinitialization Completed");
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  ESIMPM::Log::Info("ESIMPM::CoreFSM::DeInitialize", (const struct _GUID *)((char *)this + 552), L" DeInitialized");
  v18 = g_hTimerContext;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v19 = WPP_GLOBAL_Control;
  }
  if ( !v18 )
  {
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control )
      goto LABEL_46;
    v20 = 87;
    if ( (v19[28] & 4) == 0 )
      goto LABEL_43;
    WPP_SF_(*((_QWORD *)v19 + 2), 16, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    goto LABEL_42;
  }
  if ( DeleteTimerQueueEx(v18, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    v20 = 0;
  }
  else
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( LastError )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_43;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, LastError);
      goto LABEL_42;
    }
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_46;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v18);
LABEL_42:
    v19 = WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( v19 != (_BYTE *)&WPP_GLOBAL_Control && (v19[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v19 + 2), 19, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v20);
LABEL_46:
  ESIMPM::Log::Info("ESIMPM::WwanTimerDeinit", 0, L"Timer Library Deinitialization Completed");
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v27 = "ESIMPM::EsimPoMgr::~EsimPoMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v22,
      (__int64)&byte_14006ADA7,
      v23,
      v24,
      (const unsigned __int16 **)&v27);
  }
  v25 = (void *)*((_QWORD *)this + 125);
  if ( (unsigned __int64)v25 + 1 > 1 )
    CloseHandle(v25);
  v26 = (void *)*((_QWORD *)this + 120);
  if ( v26 )
  {
    std::wstring::_Tidy_deallocate(*((_QWORD *)this + 120));
    operator delete(v26);
  }
  ESIMPM::CoreFSM::~CoreFSM((ESIMPM::EsimPoMgr *)((char *)this + 368));
  ESIMPM::LpaHelper::~LpaHelper((ESIMPM::EsimPoMgr *)((char *)this + 128));
  std::wstring::_Tidy_deallocate((char *)this + 96);
  std::wstring::_Tidy_deallocate((char *)this + 64);
}

```

## disassembly

```asm
0x140023ba0  mov     r11, rsp
0x140023ba3  mov     [r11+18h], rbx
0x140023ba7  push    rbp
0x140023ba8  push    rsi
0x140023ba9  push    rdi
0x140023baa  push    r13
0x140023bac  push    r14
0x140023bae  sub     rsp, 30h
0x140023bb2  mov     rdi, rcx
0x140023bb5  lea     rax, ??_7EsimPoMgr@ESIMPM@@6B@; const ESIMPM::EsimPoMgr::`vftable'
0x140023bbc  mov     [rcx], rax
0x140023bbf  mov     eax, cs:dword_140075078
0x140023bc5  lea     rbx, aEsimpmEsimpomg_15; "ESIMPM::EsimPoMgr::~EsimPoMgr"
0x140023bcc  cmp     eax, 5
0x140023bcf  jbe     short loc_140023BE9
0x140023bd1  mov     [r11+8], rbx
0x140023bd5  lea     rax, [r11+8]
0x140023bd9  mov     [r11-38h], rax
0x140023bdd  lea     rdx, byte_14006AE43
0x140023be4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140023be9  mov     rcx, [rdi+3C8h]; RegistrationHandle
0x140023bf0  test    rcx, rcx
0x140023bf3  jz      short loc_140023C06
0x140023bf5  call    cs:__imp_PowerSettingUnregisterNotification
0x140023bfb  mov     qword ptr [rdi+3C8h], 0
0x140023c06  mov     rcx, [rdi+8]
0x140023c0a  test    rcx, rcx
0x140023c0d  jz      short loc_140023C1F
0x140023c0f  xor     edx, edx
0x140023c11  call    cs:__imp_WwanCloseHandle
0x140023c17  mov     qword ptr [rdi+8], 0
0x140023c1f  lea     r14, [rdi+80h]
0x140023c26  mov     rcx, r14; this
0x140023c29  call    ?DeInitialize@LpaHelper@ESIMPM@@QEAAXXZ; ESIMPM::LpaHelper::DeInitialize(void)
0x140023c2e  cmp     qword ptr [rdi+3D0h], 0
0x140023c36  jz      short loc_140023CB4
0x140023c38  mov     eax, cs:dword_140075078
0x140023c3e  cmp     eax, 4
0x140023c41  jbe     short loc_140023C5E
0x140023c43  mov     [rsp+58h+arg_0], rbx
0x140023c48  lea     rax, [rsp+58h+arg_0]
0x140023c4d  mov     [rsp+58h+var_38], rax
0x140023c52  lea     rdx, word_14006AE0A
0x140023c59  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140023c5e  mov     rcx, [rdi+3D0h]; Handle
0x140023c65  call    cs:__imp_UnregisterSuspendResumeNotification
0x140023c6b  mov     qword ptr [rdi+3D0h], 0
0x140023c76  test    eax, eax
0x140023c78  jnz     short loc_140023CB4
0x140023c7a  mov     eax, cs:dword_140075078
0x140023c80  cmp     eax, 2
0x140023c83  jbe     short loc_140023CB4
0x140023c85  mov     [rsp+58h+arg_8], rbx
0x140023c8a  call    cs:__imp_GetLastError
0x140023c90  mov     dword ptr [rsp+58h+arg_0], eax
0x140023c94  lea     rax, [rsp+58h+arg_8]
0x140023c99  mov     [rsp+58h+var_30], rax
0x140023c9e  lea     rax, [rsp+58h+arg_0]
0x140023ca3  mov     [rsp+58h+var_38], rax
0x140023ca8  lea     rdx, byte_14006ADC1
0x140023caf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140023cb4  mov     rcx, [rdi+3E0h]
0x140023cbb  test    rcx, rcx
0x140023cbe  jz      short loc_140023CE2
0x140023cc0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x140023cc6  test    eax, eax
0x140023cc8  jns     short loc_140023CE2
0x140023cca  mov     r9d, eax
0x140023ccd  lea     r8, aRtlunsubscribe; "RtlUnsubscribeWnfNotificationWaitForCom"...
0x140023cd4  xor     edx, edx; struct _GUID *
0x140023cd6  lea     rcx, aEsimpmEsimpomg; "ESIMPM::EsimPoMgr::DeinitializePolicyHa"...
0x140023cdd  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140023ce2  mov     qword ptr [rdi+3E0h], 0
0x140023ced  mov     rsi, cs:?s_Dispatcher@MessageDispatcher@ESIMPM@@0V?$shared_ptr@VMessageDispatcher@ESIMPM@@@std@@A; std::shared_ptr<ESIMPM::MessageDispatcher> ESIMPM::MessageDispatcher::s_Dispatcher
0x140023cf4  test    rsi, rsi
0x140023cf7  jz      loc_140023D9E
0x140023cfd  cmp     byte ptr [rsi+38h], 0
0x140023d01  jz      short loc_140023D45
0x140023d03  lea     rcx, [rsi+10h]; lpCriticalSection
0x140023d07  call    cs:__imp_EnterCriticalSection
0x140023d0d  mov     byte ptr [rsi+38h], 0
0x140023d11  lea     rcx, [rsi+10h]; lpCriticalSection
0x140023d15  call    cs:__imp_LeaveCriticalSection
0x140023d1b  xor     r8d, r8d; pvCleanupContext
0x140023d1e  xor     edx, edx; fCancelPendingCallbacks
0x140023d20  mov     rcx, [rsi+88h]; ptpcg
0x140023d27  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x140023d2d  mov     rcx, [rsi+88h]; ptpcg
0x140023d34  call    cs:__imp_CloseThreadpoolCleanupGroup
0x140023d3a  mov     qword ptr [rsi+88h], 0
0x140023d45  mov     cs:?s_Dispatcher@MessageDispatcher@ESIMPM@@0V?$shared_ptr@VMessageDispatcher@ESIMPM@@@std@@A, 0; std::shared_ptr<ESIMPM::MessageDispatcher> ESIMPM::MessageDispatcher::s_Dispatcher
0x140023d50  mov     rbx, cs:qword_140075D08
0x140023d57  mov     cs:qword_140075D08, 0
0x140023d62  test    rbx, rbx
0x140023d65  jz      short loc_140023D9E
0x140023d67  or      eax, 0FFFFFFFFh
0x140023d6a  lock xadd [rbx+8], eax
0x140023d6f  cmp     eax, 1
0x140023d72  jnz     short loc_140023D9E
0x140023d74  mov     rax, [rbx]
0x140023d77  mov     rcx, rbx
0x140023d7a  mov     rax, [rax]
0x140023d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023d82  or      eax, 0FFFFFFFFh
0x140023d85  lock xadd [rbx+0Ch], eax
0x140023d8a  cmp     eax, 1
0x140023d8d  jnz     short loc_140023D9E
0x140023d8f  mov     rax, [rbx]
0x140023d92  mov     rcx, rbx
0x140023d95  mov     rax, [rax+8]
0x140023d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023d9e  lea     rbp, [rdi+170h]
0x140023da5  lea     rbx, [rbp+10h]
0x140023da9  xor     ecx, ecx
0x140023dab  lea     eax, [rcx+1]
0x140023dae  lock cmpxchg [rbx+70h], ecx
0x140023db3  test    eax, eax
0x140023db5  jz      short loc_140023E27
0x140023db7  lea     r9d, [rcx+30h]
0x140023dbb  lea     rsi, aEsimpmTimerwra_2; "ESIMPM::TimerWrapper::DeleteTimer"
0x140023dc2  mov     r8, rsi
0x140023dc5  mov     rdx, rbx
0x140023dc8  mov     rcx, [rbx+68h]
0x140023dcc  call    AcquireWriteLock
0x140023dd1  mov     rdx, rsi
0x140023dd4  mov     rcx, [rbx+68h]
0x140023dd8  call    StopTimer
0x140023ddd  mov     r9d, 32h ; '2'
0x140023de3  mov     r8, rsi
0x140023de6  mov     rdx, rbx
0x140023de9  mov     rcx, [rbx+68h]
0x140023ded  call    ReleaseWriteLock
0x140023df2  lea     r8, aTimerStopCompl; " Timer Stop Completed"
0x140023df9  xor     edx, edx; struct _GUID *
0x140023dfb  mov     rcx, rsi; char *
0x140023dfe  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140023e03  mov     rcx, [rbx+68h]; this
0x140023e07  call    ?WwanTimerDeleteTimer@ESIMPM@@YAXPEAX@Z; ESIMPM::WwanTimerDeleteTimer(void *)
0x140023e0c  mov     rcx, rbx
0x140023e0f  call    DeleteReadWriteLock
0x140023e14  lea     r8, aTimerDeinitial; " Timer Deinitialization Completed"
0x140023e1b  xor     edx, edx; struct _GUID *
0x140023e1d  mov     rcx, rsi; char *
0x140023e20  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140023e25  jmp     short loc_140023E2C
0x140023e27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140023e2c  lea     rdx, [rbp+0B8h]; struct _GUID *
0x140023e33  lea     r8, aDeinitialized; " DeInitialized"
0x140023e3a  lea     rcx, aEsimpmCorefsmD; "ESIMPM::CoreFSM::DeInitialize"
0x140023e41  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140023e46  mov     rsi, cs:?g_hTimerContext@@3PEAXEA; void * g_hTimerContext
0x140023e4d  lea     r13, WPP_GLOBAL_Control
0x140023e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e5b  cmp     rcx, r13
0x140023e5e  jz      short loc_140023E82
0x140023e60  test    byte ptr [rcx+1Ch], 8
0x140023e64  jz      short loc_140023E82
0x140023e66  mov     edx, 0Fh
0x140023e6b  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023e72  mov     rcx, [rcx+10h]
0x140023e76  call    WPP_SF_
0x140023e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e82  test    rsi, rsi
0x140023e85  jnz     short loc_140023EB2
0x140023e87  cmp     rcx, r13
0x140023e8a  jz      loc_140023F51
0x140023e90  lea     ebx, [rsi+57h]
0x140023e93  test    byte ptr [rcx+1Ch], 4
0x140023e97  jz      loc_140023F2E
0x140023e9d  lea     edx, [rsi+10h]
0x140023ea0  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023ea7  mov     rcx, [rcx+10h]
0x140023eab  call    WPP_SF_
0x140023eb0  jmp     short loc_140023F27
0x140023eb2  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140023eb6  mov     rcx, rsi; TimerQueue
0x140023eb9  call    cs:__imp_DeleteTimerQueueEx
0x140023ebf  test    eax, eax
0x140023ec1  jnz     short loc_140023EFB
0x140023ec3  call    cs:__imp_GetLastError
0x140023ec9  mov     ebx, eax
0x140023ecb  test    eax, eax
0x140023ecd  jz      short loc_140023EFD
0x140023ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ed6  cmp     rcx, r13
0x140023ed9  jz      short loc_140023F51
0x140023edb  test    byte ptr [rcx+1Ch], 4
0x140023edf  jz      short loc_140023F2E
0x140023ee1  mov     edx, 11h
0x140023ee6  mov     r9d, eax
0x140023ee9  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023ef0  mov     rcx, [rcx+10h]
0x140023ef4  call    WPP_SF_d
0x140023ef9  jmp     short loc_140023F27
0x140023efb  xor     ebx, ebx
0x140023efd  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f04  cmp     rcx, r13
0x140023f07  jz      short loc_140023F51
0x140023f09  test    byte ptr [rcx+1Ch], 2
0x140023f0d  jz      short loc_140023F2E
0x140023f0f  mov     edx, 12h
0x140023f14  mov     r9, rsi
0x140023f17  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023f1e  mov     rcx, [rcx+10h]
0x140023f22  call    WPP_SF_q
0x140023f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f2e  cmp     rcx, r13
0x140023f31  jz      short loc_140023F51
0x140023f33  test    byte ptr [rcx+1Ch], 8
0x140023f37  jz      short loc_140023F51
0x140023f39  mov     edx, 13h
0x140023f3e  mov     r9d, ebx
0x140023f41  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023f48  mov     rcx, [rcx+10h]
0x140023f4c  call    WPP_SF_d
0x140023f51  lea     r8, aTimerLibraryDe; "Timer Library Deinitialization Complete"...
0x140023f58  xor     edx, edx; struct _GUID *
0x140023f5a  lea     rcx, aEsimpmWwantime; "ESIMPM::WwanTimerDeinit"
0x140023f61  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140023f66  mov     eax, cs:dword_140075078
0x140023f6c  cmp     eax, 5
0x140023f6f  jbe     short loc_140023F93
0x140023f71  lea     rax, aEsimpmEsimpomg_15; "ESIMPM::EsimPoMgr::~EsimPoMgr"
0x140023f78  mov     [rsp+58h+arg_0], rax
0x140023f7d  lea     rax, [rsp+58h+arg_0]
0x140023f82  mov     [rsp+58h+var_38], rax
0x140023f87  lea     rdx, byte_14006ADA7
0x140023f8e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140023f93  mov     rcx, [rdi+3E8h]; hObject
0x140023f9a  lea     rax, [rcx+1]
0x140023f9e  cmp     rax, 1
0x140023fa2  jbe     short loc_140023FAA
0x140023fa4  call    cs:__imp_CloseHandle
0x140023faa  mov     rbx, [rdi+3C0h]
0x140023fb1  test    rbx, rbx
0x140023fb4  jz      short loc_140023FCB
0x140023fb6  mov     rcx, rbx
0x140023fb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023fbe  mov     edx, 20h ; ' '
0x140023fc3  mov     rcx, rbx; Block
0x140023fc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140023fcb  mov     rcx, rbp; this
0x140023fce  call    ??1CoreFSM@ESIMPM@@QEAA@XZ; ESIMPM::CoreFSM::~CoreFSM(void)
0x140023fd3  mov     rcx, r14; this
0x140023fd6  call    ??1LpaHelper@ESIMPM@@QEAA@XZ; ESIMPM::LpaHelper::~LpaHelper(void)
0x140023fdb  lea     rcx, [rdi+60h]
0x140023fdf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023fe4  lea     rcx, [rdi+40h]
0x140023fe8  mov     rbx, [rsp+58h+arg_10]
0x140023fed  add     rsp, 30h
0x140023ff1  pop     r14
0x140023ff3  pop     r13
0x140023ff5  pop     rdi
0x140023ff6  pop     rsi
0x140023ff7  pop     rbp
0x140023ff8  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
