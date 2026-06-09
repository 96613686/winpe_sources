# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18005d360`
- end: `0x18005d6be`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `862`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x18002c984`
- `0x18002ca8c`
- `0x18002cbb0`
- `0x18002cdd0`
- `0x18002dccc`
- `0x180052624`
- `0x18005d360`
- `0x18006f520`
- `0x18006ff06`
- `0x18006ffc8`
- `0x180078508`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005d553`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005d582`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005d553`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005d582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d4ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d52a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d618`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d627`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d4ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d52a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d618`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d627`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d438`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d438`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d664`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d664`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d4f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d4f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d505`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d505`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005d607`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005d607`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005d610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005d610`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d5f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d650`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d5f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d650`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d5d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d5d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, unsigned int a2, DWORD a3)
{
  DWORD v4; // esi
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned __int64 v7; // r10
  unsigned __int64 v8; // rdx
  struct _FILETIME *v9; // r9
  unsigned __int64 v10; // rbx
  DWORD LastError; // esi
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r8
  char *v14; // rax
  char *v15; // rbx
  signed __int64 v16; // r14
  void *v17; // rbp
  HANDLE ProcessHeap; // rax
  size_t v19; // r8
  struct _TP_TIMER *v20; // rcx
  DWORD v21; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v23; // rdi
  DWORD v24; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF

  v4 = (unsigned int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( !(_DWORD)this && !a3 && !v5 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180132108[25], qword_180132108);
      wil::details_abi::FeatureStateData::RecordUsage(qword_180132108);
    }
    return;
  }
  if ( (a2 & 0x40000000) == 0 )
  {
    if ( a3 || v5 == 254 )
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v5,
        a3);
    else
      wil_RtlStagingConfig_RecordFeatureUsage(this, v5, a2 >> 31);
    return;
  }
  if ( !wil::details::g_featureStateManager
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(&stru_180132118);
  pftDueTime.dwLowDateTime = v4;
  pftDueTime.dwHighDateTime = (unsigned __int16)v5;
  v7 = (unsigned __int64)*(&xmmword_1801321E0 + 1);
  v8 = (_BYTE *)*(&xmmword_1801321E0 + 1) - (_BYTE *)Source;
  v9 = (struct _FILETIME *)xmmword_1801321E0;
  if ( (_BYTE *)xmmword_1801321E0 - (_BYTE *)Source + 12 >= (unsigned __int64)((_BYTE *)*(&xmmword_1801321E0 + 1)
                                                                             - (_BYTE *)Source) )
  {
    v10 = 12;
    if ( 2 * v8 > 0xC )
      v10 = 2 * v8;
    if ( v8 < v10 )
    {
      LastError = GetLastError();
      v12 = (v10 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v14 = (char *)wil::details::ProcessHeapAlloc(0, v12, v13);
      v15 = v14;
      if ( !v14 )
      {
        SetLastError(LastError);
        goto LABEL_32;
      }
      v16 = (_BYTE *)xmmword_1801321E0 - (_BYTE *)Source;
      memcpy_s(v14, v12, Source, (_BYTE *)xmmword_1801321E0 - (_BYTE *)Source);
      v17 = lpMem;
      lpMem = v15;
      if ( v17 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
      Source = v15;
      xmmword_1801321E0 = &v15[v16];
      *(&xmmword_1801321E0 + 1) = &v15[v12];
      SetLastError(LastError);
      v7 = (unsigned __int64)*(&xmmword_1801321E0 + 1);
      v9 = (struct _FILETIME *)xmmword_1801321E0;
    }
  }
  v19 = 0;
  if ( (unsigned __int64)v9 < v7 )
    v19 = v7 - (_QWORD)v9;
  if ( !v9 )
  {
    *(_DWORD *)_o__errno(v6, v8, v19) = 22;
LABEL_30:
    invalid_parameter_noinfo();
    goto LABEL_31;
  }
  if ( v19 < 0xC )
  {
    memset_0(v9, 0, v19);
    *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    goto LABEL_30;
  }
  *v9 = pftDueTime;
  v9[1].dwLowDateTime = a3;
LABEL_31:
  xmmword_1801321E0 = (char *)xmmword_1801321E0 + 12;
LABEL_32:
  if ( !(_BYTE)word_180132130 )
  {
    v20 = qword_180132128;
    if ( qword_180132128 )
      goto LABEL_37;
    v21 = GetLastError();
    ThreadpoolTimer = CreateThreadpoolTimer(
                        _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                        &wil::details::g_featureStateManager,
                        0);
    v23 = qword_180132128;
    if ( qword_180132128 )
    {
      v24 = GetLastError();
      SetThreadpoolTimer(v23, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v23, 1);
      CloseThreadpoolTimer(v23);
      SetLastError(v24);
    }
    qword_180132128 = ThreadpoolTimer;
    SetLastError(v21);
    v20 = qword_180132128;
    if ( qword_180132128 )
    {
LABEL_37:
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v20, &pftDueTime, 0, 0x4E2u);
      LOBYTE(word_180132130) = 1;
    }
  }
  ReleaseSRWLockExclusive(&stru_180132118);
}

```

## disassembly

```asm
0x18005d360  mov     [rsp+arg_18], rbx
0x18005d365  push    rbp
0x18005d366  push    rsi
0x18005d367  push    rdi
0x18005d368  push    r14
0x18005d36a  push    r15
0x18005d36c  sub     rsp, 40h
0x18005d370  mov     rax, cs:__security_cookie
0x18005d377  xor     rax, rsp
0x18005d37a  mov     [rsp+68h+var_38], rax
0x18005d37f  mov     edi, r8d
0x18005d382  mov     esi, ecx
0x18005d384  mov     ebx, edx
0x18005d386  btr     ebx, 1Fh
0x18005d38a  test    ecx, ecx
0x18005d38c  jnz     short loc_18005D3F4
0x18005d38e  test    r8d, r8d
0x18005d391  jnz     short loc_18005D3F4
0x18005d393  test    ebx, ebx
0x18005d395  jnz     short loc_18005D3F4
0x18005d397  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x18005d39d  jnz     loc_18005D66B
0x18005d3a3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18005d3aa  test    rax, rax
0x18005d3ad  jz      short loc_18005D3BC
0x18005d3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3b4  test    al, al
0x18005d3b6  jnz     loc_18005D66B
0x18005d3bc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18005d3c3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18005d3c8  test    al, al
0x18005d3ca  jz      loc_18005D66B
0x18005d3d0  mov     rdx, cs:qword_180132108; SRWLock
0x18005d3d7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18005d3de  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18005d3e3  mov     rcx, cs:qword_180132108; SRWLock
0x18005d3ea  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18005d3ef  jmp     loc_18005D66B
0x18005d3f4  bt      ebx, 1Eh
0x18005d3f8  jnb     loc_18005D66D
0x18005d3fe  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18005d405  jz      loc_18005D66B
0x18005d40b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18005d412  jnz     loc_18005D66B
0x18005d418  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18005d41f  test    rax, rax
0x18005d422  jz      short loc_18005D431
0x18005d424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d429  test    al, al
0x18005d42b  jnz     loc_18005D66B
0x18005d431  lea     rcx, stru_180132118; SRWLock
0x18005d438  call    cs:__imp_AcquireSRWLockExclusive
0x18005d43e  xor     eax, eax
0x18005d440  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime+2], ax
0x18005d445  mov     [rsp+68h+pftDueTime.dwLowDateTime], esi
0x18005d449  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime], bx
0x18005d44e  mov     r10, qword ptr cs:xmmword_1801321E0+8
0x18005d455  mov     rdx, r10
0x18005d458  sub     rdx, cs:Source
0x18005d45f  mov     r9, qword ptr cs:xmmword_1801321E0
0x18005d466  mov     rax, r9
0x18005d469  sub     rax, cs:Source
0x18005d470  add     rax, 0Ch
0x18005d474  cmp     rax, rdx
0x18005d477  jb      loc_18005D53E
0x18005d47d  lea     rax, [rdx+rdx]
0x18005d481  mov     ebx, 0Ch
0x18005d486  cmp     rax, rbx
0x18005d489  cmova   rbx, rax
0x18005d48d  cmp     rdx, rbx
0x18005d490  jnb     loc_18005D53E
0x18005d496  call    cs:__imp_GetLastError
0x18005d49c  mov     esi, eax
0x18005d49e  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18005d4a2  lea     r15, [rbx+40h]
0x18005d4a6  mov     rdx, r15; dwBytes
0x18005d4a9  xor     ecx, ecx; dwFlags
0x18005d4ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18005d4b0  mov     rbx, rax
0x18005d4b3  test    rax, rax
0x18005d4b6  jnz     short loc_18005D4C5
0x18005d4b8  mov     ecx, esi; dwErrCode
0x18005d4ba  call    cs:__imp_SetLastError
0x18005d4c0  jmp     loc_18005D59B
0x18005d4c5  mov     r8, cs:Source; Source
0x18005d4cc  mov     r14, qword ptr cs:xmmword_1801321E0
0x18005d4d3  sub     r14, r8
0x18005d4d6  mov     r9, r14; SourceSize
0x18005d4d9  mov     rdx, r15; DestinationSize
0x18005d4dc  mov     rcx, rbx; Destination
0x18005d4df  call    memcpy_s
0x18005d4e4  mov     rbp, cs:lpMem
0x18005d4eb  mov     cs:lpMem, rbx
0x18005d4f2  test    rbp, rbp
0x18005d4f5  jz      short loc_18005D50B
0x18005d4f7  call    cs:__imp_GetProcessHeap
0x18005d4fd  mov     rcx, rax; hHeap
0x18005d500  mov     r8, rbp; lpMem
0x18005d503  xor     edx, edx; dwFlags
0x18005d505  call    cs:__imp_HeapFree
0x18005d50b  mov     cs:Source, rbx
0x18005d512  lea     rax, [r14+rbx]
0x18005d516  mov     qword ptr cs:xmmword_1801321E0, rax
0x18005d51d  lea     rax, [r15+rbx]
0x18005d521  mov     qword ptr cs:xmmword_1801321E0+8, rax
0x18005d528  mov     ecx, esi; dwErrCode
0x18005d52a  call    cs:__imp_SetLastError
0x18005d530  mov     r10, qword ptr cs:xmmword_1801321E0+8
0x18005d537  mov     r9, qword ptr cs:xmmword_1801321E0
0x18005d53e  mov     rax, r10
0x18005d541  sub     rax, r9
0x18005d544  xor     r8d, r8d
0x18005d547  cmp     r9, r10
0x18005d54a  cmovb   r8, rax; Size
0x18005d54e  test    r9, r9
0x18005d551  jnz     short loc_18005D561
0x18005d553  call    cs:__imp__o__errno
0x18005d559  mov     dword ptr [rax], 16h
0x18005d55f  jmp     short loc_18005D58E
0x18005d561  cmp     r8, 0Ch
0x18005d565  jb      short loc_18005D578
0x18005d567  movsd   xmm0, qword ptr [rsp+68h+pftDueTime.dwLowDateTime]
0x18005d56d  movsd   qword ptr [r9], xmm0
0x18005d572  mov     [r9+8], edi
0x18005d576  jmp     short loc_18005D593
0x18005d578  xor     edx, edx; Val
0x18005d57a  mov     rcx, r9; void *
0x18005d57d  call    memset_0
0x18005d582  call    cs:__imp__o__errno
0x18005d588  mov     dword ptr [rax], 22h ; '"'
0x18005d58e  call    _invalid_parameter_noinfo
0x18005d593  add     qword ptr cs:xmmword_1801321E0, 0Ch
0x18005d59b  cmp     byte ptr cs:word_180132130, 0
0x18005d5a2  jnz     loc_18005D65D
0x18005d5a8  mov     rcx, cs:qword_180132128
0x18005d5af  test    rcx, rcx
0x18005d5b2  jnz     loc_18005D639
0x18005d5b8  call    cs:__imp_GetLastError
0x18005d5be  mov     esi, eax
0x18005d5c0  xor     r8d, r8d; pcbe
0x18005d5c3  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18005d5ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005d5d1  call    cs:__imp_CreateThreadpoolTimer
0x18005d5d7  mov     rbp, rax
0x18005d5da  mov     rdi, cs:qword_180132128
0x18005d5e1  test    rdi, rdi
0x18005d5e4  jz      short loc_18005D61E
0x18005d5e6  call    cs:__imp_GetLastError
0x18005d5ec  mov     ebx, eax
0x18005d5ee  xor     r9d, r9d; msWindowLength
0x18005d5f1  xor     r8d, r8d; msPeriod
0x18005d5f4  xor     edx, edx; pftDueTime
0x18005d5f6  mov     rcx, rdi; pti
0x18005d5f9  call    cs:__imp_SetThreadpoolTimer
0x18005d5ff  mov     edx, 1; fCancelPendingCallbacks
0x18005d604  mov     rcx, rdi; pti
0x18005d607  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005d60d  mov     rcx, rdi; pti
0x18005d610  call    cs:__imp_CloseThreadpoolTimer
0x18005d616  mov     ecx, ebx; dwErrCode
0x18005d618  call    cs:__imp_SetLastError
0x18005d61e  mov     cs:qword_180132128, rbp
0x18005d625  mov     ecx, esi; dwErrCode
0x18005d627  call    cs:__imp_SetLastError
0x18005d62d  mov     rcx, cs:qword_180132128; pti
0x18005d634  test    rcx, rcx
0x18005d637  jz      short loc_18005D65D
0x18005d639  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18005d642  mov     r9d, 4E2h; msWindowLength
0x18005d648  xor     r8d, r8d; msPeriod
0x18005d64b  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18005d650  call    cs:__imp_SetThreadpoolTimer
0x18005d656  mov     byte ptr cs:word_180132130, 1
0x18005d65d  lea     rcx, stru_180132118; SRWLock
0x18005d664  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d66a  nop
0x18005d66b  jmp     short loc_18005D69D
0x18005d66d  test    r8d, r8d
0x18005d670  jnz     short loc_18005D689
0x18005d672  cmp     ebx, 0FEh
0x18005d678  jz      short loc_18005D689
0x18005d67a  shr     edx, 1Fh
0x18005d67d  mov     r8d, edx
0x18005d680  mov     edx, ebx
0x18005d682  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18005d687  jmp     short loc_18005D69D
0x18005d689  mov     r9, rdi
0x18005d68c  mov     r8d, ebx
0x18005d68f  mov     edx, esi
0x18005d691  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18005d698  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18005d69d  mov     rcx, [rsp+68h+var_38]
0x18005d6a2  xor     rcx, rsp; StackCookie
0x18005d6a5  call    __security_check_cookie
0x18005d6aa  mov     rbx, [rsp+68h+arg_18]
0x18005d6b2  add     rsp, 40h
0x18005d6b6  pop     r15
0x18005d6b8  pop     r14
0x18005d6ba  pop     rdi
0x18005d6bb  pop     rsi
0x18005d6bc  pop     rbp
0x18005d6bd  retn
```
