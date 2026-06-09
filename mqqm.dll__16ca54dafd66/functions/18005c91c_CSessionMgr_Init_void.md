# CSessionMgr::Init(void)

- ea: `0x18005c91c`
- end: `0x18005cda0`
- name: `?Init@CSessionMgr@@QEAAJXZ`
- size: `1156`
- prototype: `__int64 __fastcall(CSessionMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cd84`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18002c6c8`
- `0x18005bc38`
- `0x18005c91c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18005c9ba`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18005c9ba`
- `KERNEL32!GetLastError` at `0x18005c96a`
- `KERNEL32!GetLastError` at `0x18005c98d`
- `KERNEL32!GetLastError` at `0x18005c96a`
- `KERNEL32!GetLastError` at `0x18005c98d`
- `KERNEL32!CreateEventW` at `0x18005c93a`
- `KERNEL32!CreateEventW` at `0x18005c93a`
- `mqsec!GetFalconKeyValue` at `0x18005ca02`
- `mqsec!GetFalconKeyValue` at `0x18005ca3a`
- `mqsec!GetFalconKeyValue` at `0x18005ca97`
- `mqsec!GetFalconKeyValue` at `0x18005cad7`
- `mqsec!GetFalconKeyValue` at `0x18005cb0c`
- `mqsec!GetFalconKeyValue` at `0x18005cb4d`
- `mqsec!GetFalconKeyValue` at `0x18005cb82`
- `mqsec!GetFalconKeyValue` at `0x18005cbb3`
- `mqsec!GetFalconKeyValue` at `0x18005cbe8`
- `mqsec!GetFalconKeyValue` at `0x18005cc0f`
- `mqsec!GetFalconKeyValue` at `0x18005cc40`
- `mqsec!GetFalconKeyValue` at `0x18005cc7a`
- `mqsec!GetFalconKeyValue` at `0x18005cced`
- `mqsec!GetFalconKeyValue` at `0x18005cd28`
- `mqsec!GetFalconKeyValue` at `0x18005cd85`
- `mqsec!GetFalconKeyValue` at `0x18005ca02`
- `mqsec!GetFalconKeyValue` at `0x18005ca3a`
- `mqsec!GetFalconKeyValue` at `0x18005ca97`
- `mqsec!GetFalconKeyValue` at `0x18005cad7`
- `mqsec!GetFalconKeyValue` at `0x18005cb0c`
- `mqsec!GetFalconKeyValue` at `0x18005cb4d`
- `mqsec!GetFalconKeyValue` at `0x18005cb82`
- `mqsec!GetFalconKeyValue` at `0x18005cbb3`
- `mqsec!GetFalconKeyValue` at `0x18005cbe8`
- `mqsec!GetFalconKeyValue` at `0x18005cc0f`
- `mqsec!GetFalconKeyValue` at `0x18005cc40`
- `mqsec!GetFalconKeyValue` at `0x18005cc7a`
- `mqsec!GetFalconKeyValue` at `0x18005cced`
- `mqsec!GetFalconKeyValue` at `0x18005cd28`
- `mqsec!GetFalconKeyValue` at `0x18005cd85`

## string_xrefs

- `0x18005cca9`: `GUID=http://www.microsoft.com/App=MSMQ/VER=2.000/SAPP=Express`
- `0x18005cd7e`: `DeferFirstConnectAttempt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSessionMgr::Init(CSessionMgr *this)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  DWORD v3; // eax
  bool v4; // zf
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int16 v7; // ax
  int v8; // eax
  bool v9; // al
  int v11; // [rsp+30h] [rbp-38h] BYREF
  int v12; // [rsp+34h] [rbp-34h] BYREF
  int v13; // [rsp+38h] [rbp-30h] BYREF
  int v14; // [rsp+3Ch] [rbp-2Ch] BYREF
  int v15; // [rsp+40h] [rbp-28h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+48h] [rbp-20h] BYREF
  CSessionMgr *v17; // [rsp+90h] [rbp+28h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+30h] BYREF
  int v19; // [rsp+A0h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+40h] BYREF

  v17 = this;
  v1 = 1;
  CSessionMgr::m_hAcceptAllowed = CreateEventW(0, 1, 1, 0);
  if ( !CSessionMgr::m_hAcceptAllowed )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_2f346da78fab34b0e9706cf8a54ed686_Traceguids, LastError);
    }
    v3 = GetLastError();
    if ( v3 )
      LogMsgNTStatus(v3, (wchar_t *)L"sessmgr", 0x5DDu);
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  LODWORD(v17) = 4;
  v18 = 4;
  v19 = 0;
  if ( !GetFalconKeyValue(L"RoundTripDelay", &v18, &v19, (unsigned int *)&v17, 0) )
    CSessionMgr::m_dwRoundTripDelayMS = 1000 * v19;
  LODWORD(v17) = 4;
  v18 = 4;
  v20 = 0;
  v4 = GetFalconKeyValue(L"TryConnectInterval", &v18, &v20, (unsigned int *)&v17, 0) == 0;
  v5 = v20;
  if ( !v4 )
    v5 = CSessionMgr::m_dwTryConnectIntervalMS;
  CSessionMgr::m_dwTryConnectIntervalMS = CSessionMgr::m_dwRoundTripDelayMS + v5;
  LODWORD(v17) = 4;
  v18 = 4;
  v11 = CQueueMgr::m_bMQSRouting ? 120000 : 300000;
  v4 = GetFalconKeyValue(
         L"CleanupInterval",
         &v18,
         &CSessionMgr::m_dwSessionCleanTimeout,
         (unsigned int *)&v17,
         (const wchar_t *)&v11) == 0;
  v6 = v11;
  if ( v4 )
    v6 = CSessionMgr::m_dwSessionCleanTimeout;
  CSessionMgr::m_dwSessionCleanTimeout = CSessionMgr::m_dwRoundTripDelayMS + v6;
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(
         L"QosCleanupIntervalMultiplier",
         &v18,
         &CSessionMgr::m_dwQoSSessionCleanTimeoutMultiplier,
         (unsigned int *)&v17,
         0) )
  {
    CSessionMgr::m_dwQoSSessionCleanTimeoutMultiplier = 2;
  }
  LODWORD(v17) = 4;
  v18 = 4;
  v12 = 0;
  v4 = GetFalconKeyValue(L"MaxUnackedPacket", &v18, &v12, (unsigned int *)&v17, 0) == 0;
  v7 = 64;
  if ( v4 )
    v7 = v12;
  HIWORD(dword_18013A508) = v7;
  LOWORD(dword_18013A508) = v7;
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(L"AckTimeout", &v18, &CSessionMgr::m_dwSessionAckTimeout, (unsigned int *)&v17, 0) )
    CSessionMgr::m_dwSessionAckTimeout = -1;
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(
         L"RecvAckTimeoutMult",
         &v18,
         &CSessionMgr::m_dwSessionAckTimeoutMultiplier,
         (unsigned int *)&v17,
         0) )
  {
    CSessionMgr::m_dwSessionAckTimeoutMultiplier = 1;
  }
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(L"StoreAckTimeout", &v18, &CSessionMgr::m_dwSessionStoreAckTimeout, (unsigned int *)&v17, 0) )
    CSessionMgr::m_dwSessionStoreAckTimeout = -1;
  LODWORD(v17) = 4;
  v18 = 4;
  GetFalconKeyValue(L"IdleAckDelay", &v18, CSessionMgr::m_dwIdleAckDelay, (unsigned int *)&v17, 0);
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(L"WaitTime", &v18, &dword_18013A50C, (unsigned int *)&v17, 0) )
    dword_18013A50C = 0;
  LODWORD(v17) = 4;
  v18 = 4;
  v13 = 0;
  if ( GetFalconKeyValue(L"TCPNoDelay", &v18, &v13, (unsigned int *)&v17, 0) || (v8 = 1, !v13) )
    v8 = 0;
  *(_DWORD *)g_fTcpNoDelay = v8;
  LODWORD(v17) = 4;
  v18 = 4;
  v14 = 0;
  if ( GetFalconKeyValue(L"UseQoS", &v18, &v14, (unsigned int *)&v17, 0) || !v14 )
  {
    CSessionMgr::m_fUseQoS = 0;
  }
  else
  {
    CSessionMgr::m_fUseQoS = 1;
    CSessionMgr::GetAndAllocateCharKeyValue(
      L"QosSessAppName",
      &CSessionMgr::m_pszMsmqAppName,
      "Microsoft Message Queuing");
    CSessionMgr::GetAndAllocateCharKeyValue(
      L"QosSessPolicyLoc",
      &CSessionMgr::m_pszMsmqPolicyLocator,
      "GUID=http://www.microsoft.com/App=MSMQ/VER=2.000/SAPP=Express");
  }
  LODWORD(v17) = 4;
  v18 = 4;
  v15 = 0;
  if ( GetFalconKeyValue(L"AllocateMore", &v18, &v15, (unsigned int *)&v17, 0) || (v9 = 1, !v15) )
    v9 = 0;
  CSessionMgr::m_fAllocateMore = v9;
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(
         L"DeliveryRetryTimeOutScale",
         &v18,
         &CSessionMgr::m_DeliveryRetryTimeOutScale,
         (unsigned int *)&v17,
         0) )
  {
    CSessionMgr::m_DeliveryRetryTimeOutScale = 1;
  }
  else
  {
    v1 = CSessionMgr::m_DeliveryRetryTimeOutScale;
  }
  if ( v1 >= 0xA )
    CSessionMgr::m_DeliveryRetryTimeOutScale = 10;
  CSessionMgr::m_dwEstablishConnectionTimeout += 2 * CSessionMgr::m_dwRoundTripDelayMS;
  LODWORD(v17) = 4;
  v18 = 4;
  if ( GetFalconKeyValue(
         L"DeferFirstConnectAttempt",
         &v18,
         &CSessionMgr::m_fDeferFirstConnectAttempt,
         (unsigned int *)&v17,
         0) )
  {
    CSessionMgr::m_fDeferFirstConnectAttempt = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18005c91c  mov     [rsp-20h+arg_0], rcx
0x18005c921  push    rbp
0x18005c922  push    rbx
0x18005c923  push    rsi
0x18005c924  push    rdi
0x18005c925  mov     rbp, rsp
0x18005c928  sub     rsp, 68h
0x18005c92c  xor     r9d, r9d; lpName
0x18005c92f  lea     ebx, [r9+1]
0x18005c933  mov     r8d, ebx; bInitialState
0x18005c936  mov     edx, ebx; bManualReset
0x18005c938  xor     ecx, ecx; lpEventAttributes
0x18005c93a  call    cs:__imp_CreateEventW
0x18005c940  mov     cs:?m_hAcceptAllowed@CSessionMgr@@2PEAXEA, rax; void * CSessionMgr::m_hAcceptAllowed
0x18005c947  xor     edi, edi
0x18005c949  test    rax, rax
0x18005c94c  jnz     loc_18005C9DC
0x18005c952  lea     rcx, WPP_GLOBAL_Control
0x18005c959  mov     rax, cs:WPP_GLOBAL_Control
0x18005c960  cmp     rax, rcx
0x18005c963  jz      short loc_18005C98D
0x18005c965  test    [rax+6Ch], bl
0x18005c968  jz      short loc_18005C98D
0x18005c96a  call    cs:__imp_GetLastError
0x18005c970  lea     edx, [rbx+0Dh]
0x18005c973  mov     r9d, eax
0x18005c976  lea     r8, WPP_2f346da78fab34b0e9706cf8a54ed686_Traceguids
0x18005c97d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c984  mov     rcx, [rcx+60h]
0x18005c988  call    WPP_SF_d
0x18005c98d  call    cs:__imp_GetLastError
0x18005c993  test    eax, eax
0x18005c995  jz      short loc_18005C9AC
0x18005c997  mov     r8d, 5DDh; unsigned __int16
0x18005c99d  lea     rdx, aSessmgr; "sessmgr"
0x18005c9a4  mov     ecx, eax; int
0x18005c9a6  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18005c9ab  nop
0x18005c9ac  mov     r8d, ebx
0x18005c9af  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18005c9b6  lea     rcx, [rbp+pExceptionObject]
0x18005c9ba  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18005c9c0  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18005c9c7  mov     [rbp+pExceptionObject], rax
0x18005c9cb  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18005c9d2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005c9d6  call    _CxxThrowException_0
0x18005c9dc  mov     esi, 4
0x18005c9e1  mov     dword ptr [rbp+arg_0], esi
0x18005c9e4  mov     [rbp+arg_8], esi
0x18005c9e7  mov     [rbp+arg_10], edi
0x18005c9ea  mov     [rsp+68h+var_48], rdi
0x18005c9ef  lea     r9, [rbp+arg_0]
0x18005c9f3  lea     r8, [rbp+arg_10]
0x18005c9f7  lea     rdx, [rbp+arg_8]
0x18005c9fb  lea     rcx, aRoundtripdelay; "RoundTripDelay"
0x18005ca02  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005ca08  test    eax, eax
0x18005ca0a  jnz     short loc_18005CA19
0x18005ca0c  imul    eax, [rbp+arg_10], 3E8h
0x18005ca13  mov     cs:?m_dwRoundTripDelayMS@CSessionMgr@@2KA, eax; ulong CSessionMgr::m_dwRoundTripDelayMS
0x18005ca19  mov     dword ptr [rbp+arg_0], esi
0x18005ca1c  mov     [rbp+arg_8], esi
0x18005ca1f  mov     [rbp+arg_18], edi
0x18005ca22  mov     [rsp+68h+var_48], rdi
0x18005ca27  lea     r9, [rbp+arg_0]
0x18005ca2b  lea     r8, [rbp+arg_18]
0x18005ca2f  lea     rdx, [rbp+arg_8]
0x18005ca33  lea     rcx, aTryconnectinte; "TryConnectInterval"
0x18005ca3a  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005ca40  test    eax, eax
0x18005ca42  mov     eax, [rbp+arg_18]
0x18005ca45  jz      short loc_18005CA4D
0x18005ca47  mov     eax, cs:?m_dwTryConnectIntervalMS@CSessionMgr@@2KA; ulong CSessionMgr::m_dwTryConnectIntervalMS
0x18005ca4d  add     eax, cs:?m_dwRoundTripDelayMS@CSessionMgr@@2KA; ulong CSessionMgr::m_dwRoundTripDelayMS
0x18005ca53  mov     cs:?m_dwTryConnectIntervalMS@CSessionMgr@@2KA, eax; ulong CSessionMgr::m_dwTryConnectIntervalMS
0x18005ca59  mov     dword ptr [rbp+arg_0], esi
0x18005ca5c  mov     [rbp+arg_8], esi
0x18005ca5f  mov     al, cs:?m_bMQSRouting@CQueueMgr@@0_NA; bool CQueueMgr::m_bMQSRouting
0x18005ca65  neg     al
0x18005ca67  sbb     ecx, ecx
0x18005ca69  and     ecx, 0FFFD40E0h
0x18005ca6f  add     ecx, 493E0h
0x18005ca75  mov     [rbp+var_38], ecx
0x18005ca78  lea     rax, [rbp+var_38]
0x18005ca7c  mov     [rsp+68h+var_48], rax
0x18005ca81  lea     r9, [rbp+arg_0]
0x18005ca85  lea     r8, ?m_dwSessionCleanTimeout@CSessionMgr@@0KA; ulong CSessionMgr::m_dwSessionCleanTimeout
0x18005ca8c  lea     rdx, [rbp+arg_8]
0x18005ca90  lea     rcx, aCleanupinterva; "CleanupInterval"
0x18005ca97  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005ca9d  test    eax, eax
0x18005ca9f  mov     eax, [rbp+var_38]
0x18005caa2  jnz     short loc_18005CAAA
0x18005caa4  mov     eax, cs:?m_dwSessionCleanTimeout@CSessionMgr@@0KA; ulong CSessionMgr::m_dwSessionCleanTimeout
0x18005caaa  add     eax, cs:?m_dwRoundTripDelayMS@CSessionMgr@@2KA; ulong CSessionMgr::m_dwRoundTripDelayMS
0x18005cab0  mov     cs:?m_dwSessionCleanTimeout@CSessionMgr@@0KA, eax; ulong CSessionMgr::m_dwSessionCleanTimeout
0x18005cab6  mov     dword ptr [rbp+arg_0], esi
0x18005cab9  mov     [rbp+arg_8], esi
0x18005cabc  mov     [rsp+68h+var_48], rdi
0x18005cac1  lea     r9, [rbp+arg_0]
0x18005cac5  lea     r8, ?m_dwQoSSessionCleanTimeoutMultiplier@CSessionMgr@@0KA; ulong CSessionMgr::m_dwQoSSessionCleanTimeoutMultiplier
0x18005cacc  lea     rdx, [rbp+arg_8]
0x18005cad0  lea     rcx, aQoscleanupinte; "QosCleanupIntervalMultiplier"
0x18005cad7  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cadd  test    eax, eax
0x18005cadf  jz      short loc_18005CAEB
0x18005cae1  mov     cs:?m_dwQoSSessionCleanTimeoutMultiplier@CSessionMgr@@0KA, 2; ulong CSessionMgr::m_dwQoSSessionCleanTimeoutMultiplier
0x18005caeb  mov     dword ptr [rbp+arg_0], esi
0x18005caee  mov     [rbp+arg_8], esi
0x18005caf1  mov     [rbp+var_34], edi
0x18005caf4  mov     [rsp+68h+var_48], rdi
0x18005caf9  lea     r9, [rbp+arg_0]
0x18005cafd  lea     r8, [rbp+var_34]
0x18005cb01  lea     rdx, [rbp+arg_8]
0x18005cb05  lea     rcx, aMaxunackedpack; "MaxUnackedPacket"
0x18005cb0c  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cb12  test    eax, eax
0x18005cb14  mov     eax, 40h ; '@'
0x18005cb19  jnz     short loc_18005CB1E
0x18005cb1b  mov     eax, [rbp+var_34]
0x18005cb1e  mov     word ptr cs:dword_18013A508+2, ax
0x18005cb25  mov     word ptr cs:dword_18013A508, ax
0x18005cb2c  mov     dword ptr [rbp+arg_0], esi
0x18005cb2f  mov     [rbp+arg_8], esi
0x18005cb32  mov     [rsp+68h+var_48], rdi
0x18005cb37  lea     r9, [rbp+arg_0]
0x18005cb3b  lea     r8, ?m_dwSessionAckTimeout@CSessionMgr@@2KA; ulong CSessionMgr::m_dwSessionAckTimeout
0x18005cb42  lea     rdx, [rbp+arg_8]
0x18005cb46  lea     rcx, aAcktimeout; "AckTimeout"
0x18005cb4d  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cb53  test    eax, eax
0x18005cb55  jz      short loc_18005CB61
0x18005cb57  mov     cs:?m_dwSessionAckTimeout@CSessionMgr@@2KA, 0FFFFFFFFh; ulong CSessionMgr::m_dwSessionAckTimeout
0x18005cb61  mov     dword ptr [rbp+arg_0], esi
0x18005cb64  mov     [rbp+arg_8], esi
0x18005cb67  mov     [rsp+68h+var_48], rdi
0x18005cb6c  lea     r9, [rbp+arg_0]
0x18005cb70  lea     r8, ?m_dwSessionAckTimeoutMultiplier@CSessionMgr@@2KA; ulong CSessionMgr::m_dwSessionAckTimeoutMultiplier
0x18005cb77  lea     rdx, [rbp+arg_8]
0x18005cb7b  lea     rcx, aRecvacktimeout; "RecvAckTimeoutMult"
0x18005cb82  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cb88  test    eax, eax
0x18005cb8a  jz      short loc_18005CB92
0x18005cb8c  mov     cs:?m_dwSessionAckTimeoutMultiplier@CSessionMgr@@2KA, ebx; ulong CSessionMgr::m_dwSessionAckTimeoutMultiplier
0x18005cb92  mov     dword ptr [rbp+arg_0], esi
0x18005cb95  mov     [rbp+arg_8], esi
0x18005cb98  mov     [rsp+68h+var_48], rdi
0x18005cb9d  lea     r9, [rbp+arg_0]
0x18005cba1  lea     r8, ?m_dwSessionStoreAckTimeout@CSessionMgr@@2KA; ulong CSessionMgr::m_dwSessionStoreAckTimeout
0x18005cba8  lea     rdx, [rbp+arg_8]
0x18005cbac  lea     rcx, aStoreacktimeou; "StoreAckTimeout"
0x18005cbb3  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cbb9  test    eax, eax
0x18005cbbb  jz      short loc_18005CBC7
0x18005cbbd  mov     cs:?m_dwSessionStoreAckTimeout@CSessionMgr@@2KA, 0FFFFFFFFh; ulong CSessionMgr::m_dwSessionStoreAckTimeout
0x18005cbc7  mov     dword ptr [rbp+arg_0], esi
0x18005cbca  mov     [rbp+arg_8], esi
0x18005cbcd  mov     [rsp+68h+var_48], rdi
0x18005cbd2  lea     r9, [rbp+arg_0]
0x18005cbd6  lea     r8, ?m_dwIdleAckDelay@CSessionMgr@@2KA; ulong CSessionMgr::m_dwIdleAckDelay
0x18005cbdd  lea     rdx, [rbp+arg_8]
0x18005cbe1  lea     rcx, aIdleackdelay; "IdleAckDelay"
0x18005cbe8  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cbee  mov     dword ptr [rbp+arg_0], esi
0x18005cbf1  mov     [rbp+arg_8], esi
0x18005cbf4  mov     [rsp+68h+var_48], rdi
0x18005cbf9  lea     r9, [rbp+arg_0]
0x18005cbfd  lea     r8, dword_18013A50C
0x18005cc04  lea     rdx, [rbp+arg_8]
0x18005cc08  lea     rcx, aWaittime; "WaitTime"
0x18005cc0f  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cc15  test    eax, eax
0x18005cc17  jz      short loc_18005CC1F
0x18005cc19  mov     cs:dword_18013A50C, edi
0x18005cc1f  mov     dword ptr [rbp+arg_0], esi
0x18005cc22  mov     [rbp+arg_8], esi
0x18005cc25  mov     [rbp+var_30], edi
0x18005cc28  mov     [rsp+68h+var_48], rdi
0x18005cc2d  lea     r9, [rbp+arg_0]
0x18005cc31  lea     r8, [rbp+var_30]
0x18005cc35  lea     rdx, [rbp+arg_8]
0x18005cc39  lea     rcx, aTcpnodelay; "TCPNoDelay"
0x18005cc40  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cc46  test    eax, eax
0x18005cc48  jnz     short loc_18005CC51
0x18005cc4a  cmp     [rbp+var_30], edi
0x18005cc4d  mov     eax, ebx
0x18005cc4f  jnz     short loc_18005CC53
0x18005cc51  mov     eax, edi
0x18005cc53  mov     cs:?g_fTcpNoDelay@@3HA, eax; int g_fTcpNoDelay
0x18005cc59  mov     dword ptr [rbp+arg_0], esi
0x18005cc5c  mov     [rbp+arg_8], esi
0x18005cc5f  mov     [rbp+var_2C], edi
0x18005cc62  mov     [rsp+68h+var_48], rdi
0x18005cc67  lea     r9, [rbp+arg_0]
0x18005cc6b  lea     r8, [rbp+var_2C]
0x18005cc6f  lea     rdx, [rbp+arg_8]
0x18005cc73  lea     rcx, aUseqos; "UseQoS"
0x18005cc7a  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cc80  test    eax, eax
0x18005cc82  jnz     short loc_18005CCC5
0x18005cc84  cmp     [rbp+var_2C], edi
0x18005cc87  jz      short loc_18005CCC5
0x18005cc89  mov     cs:?m_fUseQoS@CSessionMgr@@2_NA, bl; bool CSessionMgr::m_fUseQoS
0x18005cc8f  lea     r8, aMicrosoftMessa; "Microsoft Message Queuing"
0x18005cc96  lea     rdx, ?m_pszMsmqAppName@CSessionMgr@@2V?$AP@D@@A; char **
0x18005cc9d  lea     rcx, aQossessappname; "QosSessAppName"
0x18005cca4  call    ?GetAndAllocateCharKeyValue@CSessionMgr@@CAXPEB_WPEAPEADPEBD@Z; CSessionMgr::GetAndAllocateCharKeyValue(wchar_t const *,char * *,char const *)
0x18005cca9  lea     r8, aGuidHttpWwwMic; "GUID=http://www.microsoft.com/App=MSMQ/"...
0x18005ccb0  lea     rdx, ?m_pszMsmqPolicyLocator@CSessionMgr@@2V?$AP@D@@A; char **
0x18005ccb7  lea     rcx, aQossesspolicyl; "QosSessPolicyLoc"
0x18005ccbe  call    ?GetAndAllocateCharKeyValue@CSessionMgr@@CAXPEB_WPEAPEADPEBD@Z; CSessionMgr::GetAndAllocateCharKeyValue(wchar_t const *,char * *,char const *)
0x18005ccc3  jmp     short loc_18005CCCC
0x18005ccc5  mov     cs:?m_fUseQoS@CSessionMgr@@2_NA, dil; bool CSessionMgr::m_fUseQoS
0x18005cccc  mov     dword ptr [rbp+arg_0], esi
0x18005cccf  mov     [rbp+arg_8], esi
0x18005ccd2  mov     [rbp+var_28], edi
0x18005ccd5  mov     [rsp+68h+var_48], rdi
0x18005ccda  lea     r9, [rbp+arg_0]
0x18005ccde  lea     r8, [rbp+var_28]
0x18005cce2  lea     rdx, [rbp+arg_8]
0x18005cce6  lea     rcx, aAllocatemore; "AllocateMore"
0x18005cced  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005ccf3  test    eax, eax
0x18005ccf5  jnz     short loc_18005CCFE
0x18005ccf7  cmp     [rbp+var_28], edi
0x18005ccfa  mov     al, bl
0x18005ccfc  jnz     short loc_18005CD01
0x18005ccfe  mov     al, dil
0x18005cd01  mov     cs:?m_fAllocateMore@CSessionMgr@@2_NA, al; bool CSessionMgr::m_fAllocateMore
0x18005cd07  mov     dword ptr [rbp+arg_0], esi
0x18005cd0a  mov     [rbp+arg_8], esi
0x18005cd0d  mov     [rsp+68h+var_48], rdi
0x18005cd12  lea     r9, [rbp+arg_0]
0x18005cd16  lea     r8, ?m_DeliveryRetryTimeOutScale@CSessionMgr@@2KA; ulong CSessionMgr::m_DeliveryRetryTimeOutScale
0x18005cd1d  lea     rdx, [rbp+arg_8]
0x18005cd21  lea     rcx, aDeliveryretryt; "DeliveryRetryTimeOutScale"
0x18005cd28  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cd2e  test    eax, eax
0x18005cd30  jz      short loc_18005CD3A
0x18005cd32  mov     cs:?m_DeliveryRetryTimeOutScale@CSessionMgr@@2KA, ebx; ulong CSessionMgr::m_DeliveryRetryTimeOutScale
0x18005cd38  jmp     short loc_18005CD40
0x18005cd3a  mov     ebx, cs:?m_DeliveryRetryTimeOutScale@CSessionMgr@@2KA; ulong CSessionMgr::m_DeliveryRetryTimeOutScale
0x18005cd40  cmp     ebx, 0Ah
0x18005cd43  jb      short loc_18005CD4F
0x18005cd45  mov     cs:?m_DeliveryRetryTimeOutScale@CSessionMgr@@2KA, 0Ah; ulong CSessionMgr::m_DeliveryRetryTimeOutScale
0x18005cd4f  mov     ecx, cs:?m_dwEstablishConnectionTimeout@CSessionMgr@@2KA; ulong CSessionMgr::m_dwEstablishConnectionTimeout
0x18005cd55  mov     eax, cs:?m_dwRoundTripDelayMS@CSessionMgr@@2KA; ulong CSessionMgr::m_dwRoundTripDelayMS
0x18005cd5b  lea     ecx, [rcx+rax*2]
0x18005cd5e  mov     cs:?m_dwEstablishConnectionTimeout@CSessionMgr@@2KA, ecx; ulong CSessionMgr::m_dwEstablishConnectionTimeout
0x18005cd64  mov     dword ptr [rbp+arg_0], esi
0x18005cd67  mov     [rbp+arg_8], esi
0x18005cd6a  mov     [rsp+68h+var_48], rdi
0x18005cd6f  lea     r9, [rbp+arg_0]
0x18005cd73  lea     r8, ?m_fDeferFirstConnectAttempt@CSessionMgr@@2KA; ulong CSessionMgr::m_fDeferFirstConnectAttempt
0x18005cd7a  lea     rdx, [rbp+arg_8]
0x18005cd7e  lea     rcx, aDeferfirstconn; "DeferFirstConnectAttempt"
0x18005cd85  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18005cd8b  test    eax, eax
0x18005cd8d  jz      short loc_18005CD95
0x18005cd8f  mov     cs:?m_fDeferFirstConnectAttempt@CSessionMgr@@2KA, edi; ulong CSessionMgr::m_fDeferFirstConnectAttempt
0x18005cd95  xor     eax, eax
0x18005cd97  add     rsp, 68h
0x18005cd9b  pop     rdi
0x18005cd9c  pop     rsi
0x18005cd9d  pop     rbx
0x18005cd9e  pop     rbp
0x18005cd9f  retn
```
