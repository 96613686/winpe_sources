# ApiTelemetryLogger::FireEvent(ApiTelemetryLogger::EventRequestType)

- ea: `0x180144e80`
- end: `0x1801453a8`
- name: `?FireEvent@ApiTelemetryLogger@@YAJW4EventRequestType@1@@Z`
- size: `1320`
- prototype: `HRESULT __fastcall(ApiTelemetryLogger::EventRequestType eventRequestType)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017120`
- `0x18011fbd8`
- `0x180144d60`

## callees

- `0x18003a8bc`
- `0x18007487c`
- `0x1800865f4`
- `0x18011ec10`
- `0x180144e80`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180144f54`
- `ntdll!RtlNtStatusToDosError` at `0x180144f54`
- `ntdll!RtlQueryPackageIdentity` at `0x180144ef1`
- `ntdll!RtlQueryPackageIdentity` at `0x180144ef1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180144f73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180144f73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014501a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014505b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014501a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18014505b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014536b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801452f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18014536b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180145140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801451fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180145140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801451fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180145303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180145398`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180145303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180145398`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180144fc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180144fc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180144fd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180145125`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801451e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180145265`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180144fd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180145125`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801451e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180145265`

## string_xrefs

- `0x180144f44`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180144f33`: `DoesTokenHaveApplicationIdAttribute`
- `0x180145348`: `onecore\com\combase\winrtapilogger\winrtapilogger.cpp`
- `0x18014537a`: `onecore\com\combase\winrtapilogger\winrtapilogger.cpp`

## pseudocode

```c
__int64 __fastcall ApiTelemetryLogger::FireEvent(ApiTelemetryLogger::EventRequestType eventRequestType)
{
  ULONGLONG v2; // rbx
  unsigned int v3; // edi
  HRESULT PackageIdentity; // eax
  NTSTATUS v5; // edi
  ProcessToken *v6; // rcx
  BOOL v7; // r12d
  bool CanProcessBeSuspendedByAnyLifecycleManager; // al
  unsigned __int64 m_nSize_low; // rsi
  SIZE_T v10; // r14
  void *v11; // rax
  void *v12; // rbx
  SIZE_T v13; // r13
  _DWORD *v14; // rax
  _DWORD *v15; // r14
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned __int8 *v19; // rdx
  unsigned int v20; // eax
  unsigned int CurrentProcessId; // eax
  const _tlgProvider_t *v22; // rcx
  const _GUID *v23; // r8
  const _GUID *v24; // r9
  unsigned __int8 *p_tlgChannel; // rdx
  _tlgWrapperArray<8> *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  wchar_t *format; // [rsp+28h] [rbp-D8h]
  const _tlgWrapperByVal<4> *v32; // [rsp+30h] [rbp-D0h]
  const _tlgWrapperByVal<4> *v33; // [rsp+50h] [rbp-B0h]
  _tlgWrapperByVal<1> v34; // [rsp+60h] [rbp-A0h] BYREF
  _tlgWrapperByVal<4> v35; // [rsp+64h] [rbp-9Ch] BYREF
  _tlgWrapperByVal<4> hProvider; // [rsp+68h] [rbp-98h] BYREF
  _tlgWrapperByVal<4> v37[2]; // [rsp+70h] [rbp-90h] BYREF
  _tlgWrapperByVal<8> pEventMetadata; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v39; // [rsp+80h] [rbp-80h] BYREF
  __int16 v40; // [rsp+88h] [rbp-78h]
  _tlgWrapperArray<8> v41; // [rsp+90h] [rbp-70h] BYREF
  char v42[256]; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+1D8h] [rbp+D8h]

  v2 = 0;
  if ( g_processToken._sysAppIdState )
  {
    v3 = g_processToken._sysAppIdState == SysAppIdPresent;
  }
  else
  {
    *(_QWORD *)&v37[0].Value = 256;
    PackageIdentity = RtlQueryPackageIdentity(-4, v42, v37);
    v5 = PackageIdentity;
    if ( PackageIdentity >= 0 )
    {
      v3 = 1;
      g_processToken._sysAppIdState = SysAppIdPresent;
    }
    else
    {
      if ( PackageIdentity != -1073741275 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
          || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
        {
          ComTraceMessage(
            PackageIdentity,
            "onecore\\com\\combase\\processtoken\\processtoken.cxx",
            "DoesTokenHaveApplicationIdAttribute",
            131,
            ERRORS,
            L"RtlQueryPackageIdentity failed: %!STATUS!",
            PackageIdentity);
        }
        RtlNtStatusToDosError(v5);
      }
      g_processToken._sysAppIdState = SysAppIdAbsent;
      v3 = 0;
    }
  }
  v7 = IsDebuggerPresent();
  if ( eventRequestType != ApcDispatched )
  {
    CanProcessBeSuspendedByAnyLifecycleManager = ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager(v6);
    if ( v7 )
    {
      v2 = ApiTelemetryLogger::gDebuggerExponentialBackoffTimer;
    }
    else if ( CanProcessBeSuspendedByAnyLifecycleManager )
    {
      v2 = 2000;
      if ( eventRequestType != Timeout )
        v2 = 1200000;
    }
    else
    {
      v2 = ApiTelemetryLogger::gExponentialBackoffTimer;
    }
  }
  AcquireSRWLockExclusive(&ApiTelemetryLogger::gApiListLock.SRWLock_);
  m_nSize_low = LOWORD(ApiTelemetryLogger::gApiList.m_nSize);
  if ( GetTickCount64() - ApiTelemetryLogger::gLastEventTickCount <= v2 || !(_WORD)m_nSize_low )
    goto LABEL_51;
  v10 = 8 * m_nSize_low;
  if ( !is_mul_ok(m_nSize_low, 8u) )
    v10 = -1;
  v11 = HeapAlloc(g_hHeap, 0, v10);
  v12 = v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xEDu,
      "onecore\\com\\combase\\winrtapilogger\\winrtapilogger.cpp",
      -2147024882);
    goto LABEL_55;
  }
  memset_0(v11, 0, v10);
  v13 = 4LL * (unsigned int)m_nSize_low;
  if ( !is_mul_ok((unsigned int)m_nSize_low, 4u) )
    v13 = -1;
  v14 = HeapAlloc(g_hHeap, 0, v13);
  v15 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xEFu,
      "onecore\\com\\combase\\winrtapilogger\\winrtapilogger.cpp",
      -2147024882);
    HeapFree(g_hHeap, 0, v12);
LABEL_55:
    ReleaseSRWLockExclusive(&ApiTelemetryLogger::gApiListLock.SRWLock_);
    return 2147942414LL;
  }
  memset_0(v14, 0, v13);
  v16 = 0;
  do
  {
    v17 = v16;
    v18 = ApiTelemetryLogger::gApiList.m_cbValue * v16++;
    v19 = &ApiTelemetryLogger::gApiList.m_pData[v18];
    v15[v17] = *((_DWORD *)v19 + 2);
    *((_QWORD *)v12 + v17) = *(_QWORD *)v19;
  }
  while ( v16 < (unsigned int)m_nSize_low );
  if ( eventRequestType == MutexAbandoned )
    v20 = ApiTelemetryLogger::gNumConsecutiveTimerEvents + 1;
  else
    v20 = 0;
  ApiTelemetryLogger::gNumConsecutiveTimerEvents = v20;
  if ( v7 )
  {
    if ( Tlgg_hClassActivationProviderProv.LevelPlus1 <= 5
      || (Tlgg_hClassActivationProviderProv.KeywordAny & 0x800000000000LL) == 0
      || (Tlgg_hClassActivationProviderProv.KeywordAll & 0x800000000000LL) != Tlgg_hClassActivationProviderProv.KeywordAll )
    {
      goto LABEL_43;
    }
    v35.Value = ApiTelemetryLogger::gNumConsecutiveTimerEvents;
    pEventMetadata.Value = GetTickCount64() - ApiTelemetryLogger::gLastEventTickCount;
    hProvider.Value = v3;
    v34.Value = 1;
    CurrentProcessId = GetCurrentProcessId();
    v39 = v15;
    p_tlgChannel = &tlgEvent_35._tlgChannel;
    v37[0].Value = CurrentProcessId;
    v33 = &v35;
    v32 = v37;
    format = (wchar_t *)&v39;
    v26 = &v41;
    v41.Ptr = v12;
  }
  else
  {
    if ( Tlgg_hClassActivationProviderProv.LevelPlus1 <= 5
      || (Tlgg_hClassActivationProviderProv.KeywordAny & 0x400000000000LL) == 0
      || (Tlgg_hClassActivationProviderProv.KeywordAll & 0x400000000000LL) != Tlgg_hClassActivationProviderProv.KeywordAll )
    {
      goto LABEL_43;
    }
    v37[0].Value = ApiTelemetryLogger::gNumConsecutiveTimerEvents;
    pEventMetadata.Value = GetTickCount64() - ApiTelemetryLogger::gLastEventTickCount;
    hProvider.Value = v3;
    v34.Value = 1;
    v27 = GetCurrentProcessId();
    v41.Ptr = v15;
    p_tlgChannel = &tlgEvent_33._tlgChannel;
    v35.Value = v27;
    v33 = v37;
    v32 = &v35;
    format = (wchar_t *)&v41;
    v26 = (_tlgWrapperArray<8> *)&v39;
    v39 = v12;
  }
  v41.Length = m_nSize_low;
  v40 = m_nSize_low;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<8>,_tlgWrapperArray<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
    v22,
    p_tlgChannel,
    v23,
    v24,
    v26,
    (const _tlgWrapperArray<4> *)format,
    v32,
    &v34,
    &hProvider,
    &pEventMetadata,
    v33);
LABEL_43:
  ApiTelemetryLogger::gLastEventTickCount = GetTickCount64();
  v28 = ApiTelemetryLogger::gExponentialBackoffTimer;
  if ( ApiTelemetryLogger::gExponentialBackoffTimer < 0x124F80 )
  {
    ApiTelemetryLogger::gExponentialBackoffTimer *= 2;
    if ( 2 * v28 > 0x124F80 )
      ApiTelemetryLogger::gExponentialBackoffTimer = 1200000;
  }
  if ( v7 )
  {
    v29 = ApiTelemetryLogger::gDebuggerExponentialBackoffTimer;
    if ( ApiTelemetryLogger::gDebuggerExponentialBackoffTimer < 0x124F80 )
    {
      ApiTelemetryLogger::gDebuggerExponentialBackoffTimer *= 2;
      if ( 2 * v29 > 0x124F80 )
        ApiTelemetryLogger::gDebuggerExponentialBackoffTimer = 1200000;
    }
  }
  HeapFree(g_hHeap, 0, ApiTelemetryLogger::gApiList.m_pData);
  ApiTelemetryLogger::gApiList.m_pData = 0;
  *(_QWORD *)&ApiTelemetryLogger::gApiList.m_nSize = 0;
  HeapFree(g_hHeap, 0, v15);
  HeapFree(g_hHeap, 0, v12);
LABEL_51:
  ReleaseSRWLockExclusive(&ApiTelemetryLogger::gApiListLock.SRWLock_);
  return 0;
}

```

## disassembly

```asm
0x180144e80  mov     [rsp-8+arg_10], rbx
0x180144e85  push    rbp
0x180144e86  push    rsi
0x180144e87  push    rdi
0x180144e88  push    r12
0x180144e8a  push    r15
0x180144e8c  lea     rbp, [rsp-0B0h]
0x180144e94  sub     rsp, 1B0h
0x180144e9b  mov     rax, cs:__security_cookie
0x180144ea2  xor     rax, rsp
0x180144ea5  mov     [rbp+0D0h+var_30], rax
0x180144eac  mov     eax, cs:?g_processToken@@3VProcessToken@@A._sysAppIdState; ProcessToken g_processToken ...
0x180144eb2  xor     esi, esi
0x180144eb4  mov     r15d, eventRequestType
0x180144eb7  mov     ebx, esi
0x180144eb9  test    eax, eax
0x180144ebb  jz      short loc_180144ECB
0x180144ebd  cmp     eax, 1
0x180144ec0  mov     edi, esi
0x180144ec2  setz    dil
0x180144ec6  jmp     loc_180144F73
0x180144ecb  mov     [rsp+1D0h+format], rsi
0x180144ed0  lea     r8, [rsp+1D0h+var_160]
0x180144ed5  xor     r9d, r9d
0x180144ed8  mov     qword ptr [rsp+1D0h+level], rsi
0x180144edd  lea     rdx, [rbp+0D0h+var_130]
0x180144ee1  mov     qword ptr [rsp+1D0h+var_160.Value], 100h
0x180144eea  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x180144ef1  call    cs:__imp_RtlQueryPackageIdentity
0x180144ef7  mov     edi, eax
0x180144ef9  test    eax, eax
0x180144efb  jns     short loc_180144F68
0x180144efd  cmp     eax, 0C0000225h
0x180144f02  jz      short loc_180144F5A
0x180144f04  mov     eventRequestType, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180144f0a  test    eventRequestType, eventRequestType
0x180144f0c  jnz     short loc_180144F23
0x180144f0e  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180144f14  jz      short loc_180144F52
0x180144f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180144f1d  test    byte ptr [rcx+1Ch], 1
0x180144f21  jz      short loc_180144F52
0x180144f23  lea     rax, aRtlquerypackag; "RtlQueryPackageIdentity failed: %!STATU"...
0x180144f2a  mov     dword ptr [rsp+1D0h+var_1A0], edi
0x180144f2e  mov     [rsp+1D0h+format], rax; format
0x180144f33  lea     r8, aDoestokenhavea; "DoesTokenHaveApplicationIdAttribute"
0x180144f3a  mov     r9d, 83h; line
0x180144f40  mov     [rsp+1D0h+level], esi; level
0x180144f44  lea     rdx, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x180144f4b  mov     eventRequestType, edi; hr
0x180144f4d  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180144f52  mov     eventRequestType, edi; Status
0x180144f54  call    cs:__imp_RtlNtStatusToDosError
0x180144f5a  mov     cs:?g_processToken@@3VProcessToken@@A._sysAppIdState, 2; ProcessToken g_processToken ...
0x180144f64  mov     edi, esi
0x180144f66  jmp     short loc_180144F73
0x180144f68  mov     edi, 1
0x180144f6d  mov     cs:?g_processToken@@3VProcessToken@@A._sysAppIdState, edi; ProcessToken g_processToken ...
0x180144f73  call    cs:__imp_IsDebuggerPresent
0x180144f79  mov     esi, 124F80h
0x180144f7e  mov     r12d, eax
0x180144f81  cmp     r15d, 2
0x180144f85  jz      short loc_180144FB2
0x180144f87  call    ?CanProcessBeSuspendedByAnyLifecycleManager@ProcessToken@@QEAA_NXZ; ProcessToken::CanProcessBeSuspendedByAnyLifecycleManager(void)
0x180144f8c  test    r12d, r12d
0x180144f8f  jz      short loc_180144F99
0x180144f91  mov     ebx, cs:?gDebuggerExponentialBackoffTimer@ApiTelemetryLogger@@3IA; uint ApiTelemetryLogger::gDebuggerExponentialBackoffTimer
0x180144f97  jmp     short loc_180144FB2
0x180144f99  test    al, al
0x180144f9b  jz      short loc_180144FAC
0x180144f9d  cmp     r15d, 3
0x180144fa1  mov     ebx, 7D0h
0x180144fa6  cmovnz  rbx, rsi
0x180144faa  jmp     short loc_180144FB2
0x180144fac  mov     ebx, cs:?gExponentialBackoffTimer@ApiTelemetryLogger@@3IA; uint ApiTelemetryLogger::gExponentialBackoffTimer
0x180144fb2  mov     [rsp+1D0h+arg_0], r13
0x180144fba  lea     rcx, ?gApiListLock@ApiTelemetryLogger@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180144fc1  mov     [rsp+1D0h+arg_8], r14
0x180144fc9  call    cs:__imp_AcquireSRWLockExclusive
0x180144fcf  movzx   esi, word ptr cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_nSize; CArrayFValue ApiTelemetryLogger::gApiList ...
0x180144fd6  call    cs:__imp_GetTickCount64
0x180144fdc  sub     rax, cs:?gLastEventTickCount@ApiTelemetryLogger@@3_KA; unsigned __int64 ApiTelemetryLogger::gLastEventTickCount
0x180144fe3  cmp     rax, rbx
0x180144fe6  jbe     loc_1801452FC
0x180144fec  test    si, si
0x180144fef  jz      loc_1801452FC
0x180144ff5  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180144ffc  mov     eax, 8
0x180145001  mul     rsi
0x180145004  mov     r13d, esi
0x180145007  mov     r14, rax
0x18014500a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180145011  cmovb   r14, rax
0x180145015  xor     edx, edx; dwFlags
0x180145017  mov     r8, r14; dwBytes
0x18014501a  call    cs:__imp_HeapAlloc
0x180145020  mov     rbx, rax
0x180145023  test    rax, rax
0x180145026  jz      loc_180145373
0x18014502c  mov     r8, r14; Size
0x18014502f  xor     edx, edx; Val
0x180145031  mov     rcx, rax; void *
0x180145034  call    memset_0
0x180145039  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180145040  mov     eax, 4
0x180145045  mul     r13
0x180145048  mov     r13, rax
0x18014504b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180145052  cmovb   r13, rax
0x180145056  xor     edx, edx; dwFlags
0x180145058  mov     r8, r13; dwBytes
0x18014505b  call    cs:__imp_HeapAlloc
0x180145061  mov     r14, rax
0x180145064  test    rax, rax
0x180145067  jz      loc_180145341
0x18014506d  mov     r8, r13; Size
0x180145070  xor     edx, edx; Val
0x180145072  mov     rcx, rax; void *
0x180145075  call    memset_0
0x18014507a  xor     r13d, r13d
0x18014507d  mov     r8d, r13d
0x180145080  test    esi, esi
0x180145082  jz      short loc_1801450BA
0x180145084  nop     dword ptr [rax+00h]
0x180145088  nop     dword ptr [rax+rax+00000000h]
0x180145090  mov     edx, r8d
0x180145093  mov     eventRequestType, r8d
0x180145096  imul    edx, cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_cbValue; CArrayFValue ApiTelemetryLogger::gApiList ...
0x18014509d  inc     r8d
0x1801450a0  add     rdx, cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_pData; CArrayFValue ApiTelemetryLogger::gApiList ...
0x1801450a7  mov     eax, [rdx+8]
0x1801450aa  mov     [r14+rcx*4], eax
0x1801450ae  mov     rax, [rdx]
0x1801450b1  mov     [rbx+rcx*8], rax
0x1801450b5  cmp     r8d, esi
0x1801450b8  jb      short loc_180145090
0x1801450ba  cmp     r15d, 1
0x1801450be  jnz     short loc_1801450CA
0x1801450c0  mov     eax, cs:?gNumConsecutiveTimerEvents@ApiTelemetryLogger@@3IA; uint ApiTelemetryLogger::gNumConsecutiveTimerEvents
0x1801450c6  inc     eax
0x1801450c8  jmp     short loc_1801450CD
0x1801450ca  mov     eax, r13d
0x1801450cd  mov     cs:?gNumConsecutiveTimerEvents@ApiTelemetryLogger@@3IA, eax; uint ApiTelemetryLogger::gNumConsecutiveTimerEvents
0x1801450d3  mov     eax, cs:_Tlgg_hClassActivationProviderProv.LevelPlus1
0x1801450d9  test    r12d, r12d
0x1801450dc  jz      loc_18014519D
0x1801450e2  cmp     eax, 5
0x1801450e5  jbe     loc_180145265
0x1801450eb  mov     rcx, cs:_Tlgg_hClassActivationProviderProv.KeywordAll
0x1801450f2  mov     rdx, 800000000000h
0x1801450fc  mov     rax, cs:_Tlgg_hClassActivationProviderProv.KeywordAny
0x180145103  test    rdx, rax
0x180145106  jz      loc_180145265
0x18014510c  mov     rax, rcx
0x18014510f  and     rax, rdx
0x180145112  cmp     rax, rcx
0x180145115  jnz     loc_180145265
0x18014511b  mov     eax, cs:?gNumConsecutiveTimerEvents@ApiTelemetryLogger@@3IA; __annotation("_TlgWrite:|272|g_hClassActivationProvider|"WinRtClassActivationInfoDebuggerPresent"=WinRT classes this debugged process has activated.|"ApiHashArray"=|"CallCounts"=|"PID"=|"UTCReplace_AppSessionGuid"=|"IsWinRTApp"=|"RuntimeMs"=|"NumConsequtiveTimerEvents"=")
0x180145121  mov     [rsp+1D0h+var_16C.Value], eax
0x180145125  call    cs:__imp_GetTickCount64
0x18014512b  sub     rax, cs:?gLastEventTickCount@ApiTelemetryLogger@@3_KA; unsigned __int64 ApiTelemetryLogger::gLastEventTickCount
0x180145132  mov     [rsp+1D0h+var_158.Value], rax
0x180145137  mov     [rsp+1D0h+var_168.Value], edi
0x18014513b  mov     [rsp+1D0h+var_170.Value], 1
0x180145140  call    cs:__imp_GetCurrentProcessId
0x180145146  mov     [rbp+0D0h+var_150], r14
0x18014514a  lea     rdx, _tlgEvent_35._tlgChannel
0x180145151  mov     [rsp+1D0h+var_160.Value], eax
0x180145155  lea     rax, [rsp+1D0h+var_16C]
0x18014515a  mov     [rsp+1D0h+var_180], rax
0x18014515f  lea     rax, [rsp+1D0h+var_158]
0x180145164  mov     [rsp+1D0h+pEventMetadata], rax
0x180145169  lea     rax, [rsp+1D0h+var_168]
0x18014516e  mov     [rsp+1D0h+hProvider], rax
0x180145173  lea     rax, [rsp+1D0h+var_170]
0x180145178  mov     [rsp+1D0h+var_198], rax
0x18014517d  lea     rax, [rsp+1D0h+var_160]
0x180145182  mov     [rsp+1D0h+var_1A0], rax
0x180145187  lea     rax, [rbp+0D0h+var_150]
0x18014518b  mov     [rsp+1D0h+format], rax
0x180145190  lea     rax, [rbp+0D0h+var_140]
0x180145194  mov     [rbp+0D0h+var_140.Ptr], rbx
0x180145198  jmp     loc_180145253
0x18014519d  cmp     eax, 5
0x1801451a0  jbe     loc_180145265
0x1801451a6  mov     rcx, cs:_Tlgg_hClassActivationProviderProv.KeywordAll
0x1801451ad  mov     rdx, 400000000000h
0x1801451b7  mov     rax, cs:_Tlgg_hClassActivationProviderProv.KeywordAny
0x1801451be  test    rdx, rax
0x1801451c1  jz      loc_180145265
0x1801451c7  mov     rax, rcx
0x1801451ca  and     rax, rdx
0x1801451cd  cmp     rax, rcx
0x1801451d0  jnz     loc_180145265
0x1801451d6  mov     eax, cs:?gNumConsecutiveTimerEvents@ApiTelemetryLogger@@3IA; __annotation("_TlgWrite:|287|g_hClassActivationProvider|"WinRtClassActivationInfo"=WinRT classes this process has activated.|"ApiHashArray"=|"CallCounts"=|"PID"=|"UTCReplace_AppSessionGuid"=|"IsWinRTApp"=|"RuntimeMs"=|"NumConsequtiveTimerEvents"=")
0x1801451dc  mov     [rsp+1D0h+var_160.Value], eax
0x1801451e0  call    cs:__imp_GetTickCount64
0x1801451e6  sub     rax, cs:?gLastEventTickCount@ApiTelemetryLogger@@3_KA; unsigned __int64 ApiTelemetryLogger::gLastEventTickCount
0x1801451ed  mov     [rsp+1D0h+var_158.Value], rax
0x1801451f2  mov     [rsp+1D0h+var_168.Value], edi
0x1801451f6  mov     [rsp+1D0h+var_170.Value], 1
0x1801451fb  call    cs:__imp_GetCurrentProcessId
0x180145201  mov     [rbp+0D0h+var_140.Ptr], r14
0x180145205  lea     rdx, _tlgEvent_33._tlgChannel; <wrappedArgs_0>
0x18014520c  mov     [rsp+1D0h+var_16C.Value], eax
0x180145210  lea     rax, [rsp+1D0h+var_160]
0x180145215  mov     [rsp+1D0h+var_180], rax; <writerArgs_0>
0x18014521a  lea     rax, [rsp+1D0h+var_158]
0x18014521f  mov     [rsp+1D0h+pEventMetadata], rax; pEventMetadata
0x180145224  lea     rax, [rsp+1D0h+var_168]
0x180145229  mov     [rsp+1D0h+hProvider], rax; hProvider
0x18014522e  lea     rax, [rsp+1D0h+var_170]
0x180145233  mov     [rsp+1D0h+var_198], rax; <wrappedArgs_6>
0x180145238  lea     rax, [rsp+1D0h+var_16C]
0x18014523d  mov     [rsp+1D0h+var_1A0], rax; <wrappedArgs_5>
0x180145242  lea     rax, [rbp+0D0h+var_140]
0x180145246  mov     [rsp+1D0h+format], rax; <wrappedArgs_4>
0x18014524b  lea     rax, [rbp+0D0h+var_150]
0x18014524f  mov     [rbp+0D0h+var_150], rbx
0x180145253  mov     qword ptr [rsp+1D0h+level], rax; <wrappedArgs_3>
0x180145258  mov     [rbp+0D0h+var_140.Length], si
0x18014525c  mov     [rbp+0D0h+var_148], si
0x180145260  call    ??$Write@U?$_tlgWrapperArray@$07@@U?$_tlgWrapperArray@$03@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U3@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapperArray@$03@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@5AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<8>,_tlgWrapperArray<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<8> const &,_tlgWrapperArray<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180145265  call    cs:__imp_GetTickCount64
0x18014526b  mov     cs:?gLastEventTickCount@ApiTelemetryLogger@@3_KA, rax; unsigned __int64 ApiTelemetryLogger::gLastEventTickCount
0x180145272  mov     eventRequestType, 124F80h
0x180145277  mov     eax, cs:?gExponentialBackoffTimer@ApiTelemetryLogger@@3IA; uint ApiTelemetryLogger::gExponentialBackoffTimer
0x18014527d  cmp     eax, eventRequestType
0x18014527f  jnb     short loc_180145293
0x180145281  add     eax, eax
0x180145283  mov     cs:?gExponentialBackoffTimer@ApiTelemetryLogger@@3IA, eax; uint ApiTelemetryLogger::gExponentialBackoffTimer
0x180145289  cmp     eax, eventRequestType
0x18014528b  jbe     short loc_180145293
0x18014528d  mov     cs:?gExponentialBackoffTimer@ApiTelemetryLogger@@3IA, eventRequestType; uint ApiTelemetryLogger::gExponentialBackoffTimer
0x180145293  test    r12d, r12d
0x180145296  jz      short loc_1801452B4
0x180145298  mov     eax, cs:?gDebuggerExponentialBackoffTimer@ApiTelemetryLogger@@3IA; uint ApiTelemetryLogger::gDebuggerExponentialBackoffTimer
0x18014529e  cmp     eax, eventRequestType
0x1801452a0  jnb     short loc_1801452B4
0x1801452a2  add     eax, eax
0x1801452a4  mov     cs:?gDebuggerExponentialBackoffTimer@ApiTelemetryLogger@@3IA, eax; uint ApiTelemetryLogger::gDebuggerExponentialBackoffTimer
0x1801452aa  cmp     eax, eventRequestType
0x1801452ac  jbe     short loc_1801452B4
0x1801452ae  mov     cs:?gDebuggerExponentialBackoffTimer@ApiTelemetryLogger@@3IA, eventRequestType; uint ApiTelemetryLogger::gDebuggerExponentialBackoffTimer
0x1801452b4  mov     r8, cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_pData; lpMem
0x1801452bb  xor     edx, edx; dwFlags
0x1801452bd  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801452c4  call    cs:__imp_HeapFree
0x1801452ca  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801452d1  mov     r8, r14; lpMem
0x1801452d4  xor     edx, edx; dwFlags
0x1801452d6  mov     cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_pData, r13; CArrayFValue ApiTelemetryLogger::gApiList ...
0x1801452dd  mov     qword ptr cs:?gApiList@ApiTelemetryLogger@@3VCArrayFValue@@A.m_nSize, r13; CArrayFValue ApiTelemetryLogger::gApiList ...
0x1801452e4  call    cs:__imp_HeapFree
0x1801452ea  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801452f1  mov     r8, rbx; lpMem
0x1801452f4  xor     edx, edx; dwFlags
0x1801452f6  call    cs:__imp_HeapFree
0x1801452fc  lea     rcx, ?gApiListLock@ApiTelemetryLogger@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180145303  call    cs:__imp_ReleaseSRWLockExclusive
0x180145309  xor     eax, eax
0x18014530b  mov     r14, [rsp+1D0h+arg_8]
0x180145313  mov     r13, [rsp+1D0h+arg_0]
0x18014531b  mov     rcx, [rbp+0D0h+var_30]
0x180145322  xor     rcx, rsp; StackCookie
0x180145325  call    __security_check_cookie
0x18014532a  mov     rbx, [rsp+1D0h+arg_10]
0x180145332  add     rsp, 1B0h
0x180145339  pop     r15
0x18014533b  pop     r12
0x18014533d  pop     rdi
0x18014533e  pop     rsi
0x18014533f  pop     rbp
0x180145340  retn
0x180145341  mov     rcx, [rbp+0D8h]; callerReturnAddress
0x180145348  lea     r8, aOnecoreComComb_52; "onecore\\com\\combase\\winrtapilogger\\"...
0x18014534f  mov     r9d, 8007000Eh; hr
0x180145355  mov     edx, 0EFh; lineNumber
0x18014535a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014535f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180145366  mov     r8, rbx; lpMem
0x180145369  xor     edx, edx; dwFlags
0x18014536b  call    cs:__imp_HeapFree
0x180145371  jmp     short loc_180145391
0x180145373  mov     rcx, [rbp+0D8h]; callerReturnAddress
0x18014537a  lea     r8, aOnecoreComComb_52; "onecore\\com\\combase\\winrtapilogger\\"...
0x180145381  mov     r9d, 8007000Eh; hr
0x180145387  mov     edx, 0EDh; lineNumber
0x18014538c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145391  lea     rcx, ?gApiListLock@ApiTelemetryLogger@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180145398  call    cs:__imp_ReleaseSRWLockExclusive
0x18014539e  mov     eax, 8007000Eh
0x1801453a3  jmp     loc_18014530B
```
