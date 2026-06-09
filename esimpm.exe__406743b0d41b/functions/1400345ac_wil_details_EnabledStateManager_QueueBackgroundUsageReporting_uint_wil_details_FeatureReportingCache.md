# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1400345ac`
- end: `0x140034760`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `436`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140034840`

## callees

- `0x140003a6e`
- `0x140003b28`
- `0x140013f7c`
- `0x1400345ac`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140034658`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140034680`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140034658`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140034680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003474c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003474c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400345f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400345f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140034701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003470e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140034701`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003470e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400346bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400346bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400346f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400346f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400346f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400346f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400346e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003473a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400346e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003473a`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  size_t v7; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v11 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v11);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v12 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v12 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v12, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = 43378192;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v5, v7) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1400345ac  push    rbx
0x1400345ae  push    rbp
0x1400345af  push    rsi
0x1400345b0  push    rdi
0x1400345b1  push    r14
0x1400345b3  push    r15
0x1400345b5  sub     rsp, 28h
0x1400345b9  mov     rbp, r8
0x1400345bc  mov     rdi, rcx
0x1400345bf  mov     eax, [rcx]
0x1400345c1  test    eax, eax
0x1400345c3  jz      loc_140034753
0x1400345c9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400345d0  jnz     loc_140034753
0x1400345d6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400345dd  test    rax, rax
0x1400345e0  jz      short loc_1400345EF
0x1400345e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400345e7  test    al, al
0x1400345e9  jnz     loc_140034753
0x1400345ef  lea     rsi, [rdi+8]
0x1400345f3  mov     rcx, rsi; SRWLock
0x1400345f6  call    cs:__imp_AcquireSRWLockExclusive
0x1400345fc  mov     eax, [rdi]
0x1400345fe  test    eax, eax
0x140034600  jz      loc_140034744
0x140034606  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14003460d  jnz     loc_140034744
0x140034613  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14003461a  test    rax, rax
0x14003461d  jz      short loc_14003462C
0x14003461f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034624  test    al, al
0x140034626  jnz     loc_140034744
0x14003462c  mov     edx, 10h; unsigned __int64
0x140034631  lea     rcx, [rdi+20h]; this
0x140034635  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14003463a  test    al, al
0x14003463c  jz      short loc_140034696
0x14003463e  mov     rcx, [rdi+28h]; void *
0x140034642  mov     rax, [rdi+30h]
0x140034646  sub     rax, rcx
0x140034649  cmp     rcx, [rdi+30h]
0x14003464d  sbb     r8, r8
0x140034650  and     r8, rax; Size
0x140034653  test    rcx, rcx
0x140034656  jnz     short loc_140034666
0x140034658  call    cs:__imp__o__errno
0x14003465e  mov     dword ptr [rax], 16h
0x140034664  jmp     short loc_14003468C
0x140034666  cmp     r8, 10h
0x14003466a  jb      short loc_140034679
0x14003466c  mov     qword ptr [rcx], 295E610h
0x140034673  mov     [rcx+8], rbp
0x140034677  jmp     short loc_140034691
0x140034679  xor     edx, edx; Val
0x14003467b  call    memset_0
0x140034680  call    cs:__imp__o__errno
0x140034686  mov     dword ptr [rax], 22h ; '"'
0x14003468c  call    _invalid_parameter_noinfo
0x140034691  add     qword ptr [rdi+28h], 10h
0x140034696  cmp     byte ptr [rdi+18h], 0
0x14003469a  jnz     loc_140034744
0x1400346a0  cmp     qword ptr [rdi+10h], 0
0x1400346a5  jnz     short loc_140034714
0x1400346a7  call    cs:__imp_GetLastError
0x1400346ad  mov     r14d, eax
0x1400346b0  xor     r8d, r8d; pcbe
0x1400346b3  mov     rdx, rdi; pv
0x1400346b6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400346bd  call    cs:__imp_CreateThreadpoolTimer
0x1400346c3  mov     r15, rax
0x1400346c6  mov     rbp, [rdi+10h]
0x1400346ca  test    rbp, rbp
0x1400346cd  jz      short loc_140034707
0x1400346cf  call    cs:__imp_GetLastError
0x1400346d5  mov     ebx, eax
0x1400346d7  xor     r9d, r9d; msWindowLength
0x1400346da  xor     r8d, r8d; msPeriod
0x1400346dd  xor     edx, edx; pftDueTime
0x1400346df  mov     rcx, rbp; pti
0x1400346e2  call    cs:__imp_SetThreadpoolTimer
0x1400346e8  mov     edx, 1; fCancelPendingCallbacks
0x1400346ed  mov     rcx, rbp; pti
0x1400346f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400346f6  mov     rcx, rbp; pti
0x1400346f9  call    cs:__imp_CloseThreadpoolTimer
0x1400346ff  mov     ecx, ebx; dwErrCode
0x140034701  call    cs:__imp_SetLastError
0x140034707  mov     [rdi+10h], r15
0x14003470b  mov     ecx, r14d; dwErrCode
0x14003470e  call    cs:__imp_SetLastError
0x140034714  mov     rcx, [rdi+10h]; pti
0x140034718  test    rcx, rcx
0x14003471b  jz      short loc_140034744
0x14003471d  mov     rax, 0FFFFFFFF4D2FA200h
0x140034727  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x14003472c  mov     r9d, 124F8h; msWindowLength
0x140034732  xor     r8d, r8d; msPeriod
0x140034735  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x14003473a  call    cs:__imp_SetThreadpoolTimer
0x140034740  mov     byte ptr [rdi+18h], 1
0x140034744  test    rsi, rsi
0x140034747  jz      short loc_140034753
0x140034749  mov     rcx, rsi; SRWLock
0x14003474c  call    cs:__imp_ReleaseSRWLockExclusive
0x140034752  nop
0x140034753  add     rsp, 28h
0x140034757  pop     r15
0x140034759  pop     r14
0x14003475b  pop     rdi
0x14003475c  pop     rsi
0x14003475d  pop     rbp
0x14003475e  pop     rbx
0x14003475f  retn
```
