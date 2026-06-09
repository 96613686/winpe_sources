# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001d510`
- end: `0x18001d6c8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001de4c`

## callees

- `0x180002b1a`
- `0x180002b78`
- `0x18000c544`
- `0x18001d510`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d6b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d6b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d55d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d55d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d669`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d669`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d637`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d625`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d625`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d661`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d661`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d64a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d6a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d64a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d6a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d658`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d658`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  _DWORD *v6; // rcx
  size_t v7; // r8
  __int64 v8; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
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
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
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
        *v6 = a2;
        v6[1] = 0;
        *((_QWORD *)v6 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)_o__errno(v8) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18001d510  push    rbx
0x18001d512  push    rbp
0x18001d513  push    rsi
0x18001d514  push    rdi
0x18001d515  push    r14
0x18001d517  push    r15
0x18001d519  sub     rsp, 28h
0x18001d51d  mov     rbp, r8
0x18001d520  mov     r14d, edx
0x18001d523  mov     rdi, rcx
0x18001d526  mov     eax, [rcx]
0x18001d528  test    eax, eax
0x18001d52a  jz      loc_18001D6BB
0x18001d530  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d537  jnz     loc_18001D6BB
0x18001d53d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d544  test    rax, rax
0x18001d547  jz      short loc_18001D556
0x18001d549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d54e  test    al, al
0x18001d550  jnz     loc_18001D6BB
0x18001d556  lea     rsi, [rdi+8]
0x18001d55a  mov     rcx, rsi; SRWLock
0x18001d55d  call    cs:__imp_AcquireSRWLockExclusive
0x18001d563  mov     eax, [rdi]
0x18001d565  test    eax, eax
0x18001d567  jz      loc_18001D6AC
0x18001d56d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d574  jnz     loc_18001D6AC
0x18001d57a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d581  test    rax, rax
0x18001d584  jz      short loc_18001D593
0x18001d586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d58b  test    al, al
0x18001d58d  jnz     loc_18001D6AC
0x18001d593  xor     r15d, r15d
0x18001d596  lea     edx, [r15+10h]; unsigned __int64
0x18001d59a  lea     rcx, [rdi+20h]; this
0x18001d59e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d5a3  test    al, al
0x18001d5a5  jz      short loc_18001D5FF
0x18001d5a7  mov     rcx, [rdi+28h]; void *
0x18001d5ab  mov     rax, [rdi+30h]
0x18001d5af  sub     rax, rcx
0x18001d5b2  cmp     rcx, [rdi+30h]
0x18001d5b6  sbb     r8, r8
0x18001d5b9  and     r8, rax; Size
0x18001d5bc  test    rcx, rcx
0x18001d5bf  jnz     short loc_18001D5CF
0x18001d5c1  call    cs:__imp__o__errno
0x18001d5c7  mov     dword ptr [rax], 16h
0x18001d5cd  jmp     short loc_18001D5F5
0x18001d5cf  cmp     r8, 10h
0x18001d5d3  jb      short loc_18001D5E2
0x18001d5d5  mov     [rcx], r14d
0x18001d5d8  mov     [rcx+4], r15d
0x18001d5dc  mov     [rcx+8], rbp
0x18001d5e0  jmp     short loc_18001D5FA
0x18001d5e2  xor     edx, edx; Val
0x18001d5e4  call    memset_0
0x18001d5e9  call    cs:__imp__o__errno
0x18001d5ef  mov     dword ptr [rax], 22h ; '"'
0x18001d5f5  call    _invalid_parameter_noinfo
0x18001d5fa  add     qword ptr [rdi+28h], 10h
0x18001d5ff  cmp     [rdi+18h], r15b
0x18001d603  jnz     loc_18001D6AC
0x18001d609  cmp     [rdi+10h], r15
0x18001d60d  jnz     short loc_18001D67C
0x18001d60f  call    cs:__imp_GetLastError
0x18001d615  mov     r14d, eax
0x18001d618  xor     r8d, r8d; pcbe
0x18001d61b  mov     rdx, rdi; pv
0x18001d61e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d625  call    cs:__imp_CreateThreadpoolTimer
0x18001d62b  mov     r15, rax
0x18001d62e  mov     rbp, [rdi+10h]
0x18001d632  test    rbp, rbp
0x18001d635  jz      short loc_18001D66F
0x18001d637  call    cs:__imp_GetLastError
0x18001d63d  mov     ebx, eax
0x18001d63f  xor     r9d, r9d; msWindowLength
0x18001d642  xor     r8d, r8d; msPeriod
0x18001d645  xor     edx, edx; pftDueTime
0x18001d647  mov     rcx, rbp; pti
0x18001d64a  call    cs:__imp_SetThreadpoolTimer
0x18001d650  mov     edx, 1; fCancelPendingCallbacks
0x18001d655  mov     rcx, rbp; pti
0x18001d658  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d65e  mov     rcx, rbp; pti
0x18001d661  call    cs:__imp_CloseThreadpoolTimer
0x18001d667  mov     ecx, ebx; dwErrCode
0x18001d669  call    cs:__imp_SetLastError
0x18001d66f  mov     [rdi+10h], r15
0x18001d673  mov     ecx, r14d; dwErrCode
0x18001d676  call    cs:__imp_SetLastError
0x18001d67c  mov     rcx, [rdi+10h]; pti
0x18001d680  test    rcx, rcx
0x18001d683  jz      short loc_18001D6AC
0x18001d685  mov     rax, 0FFFFFFFF4D2FA200h
0x18001d68f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001d694  mov     r9d, 124F8h; msWindowLength
0x18001d69a  xor     r8d, r8d; msPeriod
0x18001d69d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001d6a2  call    cs:__imp_SetThreadpoolTimer
0x18001d6a8  mov     byte ptr [rdi+18h], 1
0x18001d6ac  test    rsi, rsi
0x18001d6af  jz      short loc_18001D6BB
0x18001d6b1  mov     rcx, rsi; SRWLock
0x18001d6b4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d6ba  nop
0x18001d6bb  add     rsp, 28h
0x18001d6bf  pop     r15
0x18001d6c1  pop     r14
0x18001d6c3  pop     rdi
0x18001d6c4  pop     rsi
0x18001d6c5  pop     rbp
0x18001d6c6  pop     rbx
0x18001d6c7  retn
```
