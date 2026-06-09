# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a618`
- end: `0x18000a7b3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c0f0`

## callees

- `0x180002b1a`
- `0x180002b78`
- `0x18000a618`
- `0x18000c544`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a6af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a6d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a6af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a6d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a79f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a79f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a668`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a668`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a728`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a716`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a716`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a752`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a752`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a73b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a78d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a73b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a78d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a749`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a749`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)_o__errno(v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000a618  push    rbx
0x18000a61a  push    rbp
0x18000a61b  push    rsi
0x18000a61c  push    rdi
0x18000a61d  push    r14
0x18000a61f  push    r15
0x18000a621  sub     rsp, 38h
0x18000a625  mov     ebp, r9d
0x18000a628  movzx   ebx, r8w
0x18000a62c  mov     r14d, edx
0x18000a62f  mov     rdi, rcx
0x18000a632  cmp     byte ptr [rcx], 0
0x18000a635  jz      loc_18000A7A6
0x18000a63b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a642  jnz     loc_18000A7A6
0x18000a648  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a64f  test    rax, rax
0x18000a652  jz      short loc_18000A661
0x18000a654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a659  test    al, al
0x18000a65b  jnz     loc_18000A7A6
0x18000a661  lea     rsi, [rdi+28h]
0x18000a665  mov     rcx, rsi; SRWLock
0x18000a668  call    cs:__imp_AcquireSRWLockExclusive
0x18000a66e  xor     eax, eax
0x18000a670  mov     word ptr [rsp+68h+var_48+6], ax
0x18000a675  mov     dword ptr [rsp+68h+var_48], r14d
0x18000a67a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000a67f  lea     rbx, [rdi+0E8h]
0x18000a686  lea     edx, [rax+0Ch]; unsigned __int64
0x18000a689  mov     rcx, rbx; this
0x18000a68c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a691  test    al, al
0x18000a693  jz      short loc_18000A6EF
0x18000a695  mov     rcx, [rbx+8]; void *
0x18000a699  mov     rax, [rbx+10h]
0x18000a69d  sub     rax, rcx
0x18000a6a0  cmp     rcx, [rbx+10h]
0x18000a6a4  sbb     r8, r8
0x18000a6a7  and     r8, rax; Size
0x18000a6aa  test    rcx, rcx
0x18000a6ad  jnz     short loc_18000A6BD
0x18000a6af  call    cs:__imp__o__errno
0x18000a6b5  mov     dword ptr [rax], 16h
0x18000a6bb  jmp     short loc_18000A6E5
0x18000a6bd  cmp     r8, 0Ch
0x18000a6c1  jb      short loc_18000A6D2
0x18000a6c3  movsd   xmm0, [rsp+68h+var_48]
0x18000a6c9  movsd   qword ptr [rcx], xmm0
0x18000a6cd  mov     [rcx+8], ebp
0x18000a6d0  jmp     short loc_18000A6EA
0x18000a6d2  xor     edx, edx; Val
0x18000a6d4  call    memset_0
0x18000a6d9  call    cs:__imp__o__errno
0x18000a6df  mov     dword ptr [rax], 22h ; '"'
0x18000a6e5  call    _invalid_parameter_noinfo
0x18000a6ea  add     qword ptr [rbx+8], 0Ch
0x18000a6ef  cmp     byte ptr [rdi+40h], 0
0x18000a6f3  jnz     loc_18000A797
0x18000a6f9  cmp     qword ptr [rdi+38h], 0
0x18000a6fe  jnz     short loc_18000A76D
0x18000a700  call    cs:__imp_GetLastError
0x18000a706  mov     r14d, eax
0x18000a709  xor     r8d, r8d; pcbe
0x18000a70c  mov     rdx, rdi; pv
0x18000a70f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a716  call    cs:__imp_CreateThreadpoolTimer
0x18000a71c  mov     r15, rax
0x18000a71f  mov     rbp, [rdi+38h]
0x18000a723  test    rbp, rbp
0x18000a726  jz      short loc_18000A760
0x18000a728  call    cs:__imp_GetLastError
0x18000a72e  mov     ebx, eax
0x18000a730  xor     r9d, r9d; msWindowLength
0x18000a733  xor     r8d, r8d; msPeriod
0x18000a736  xor     edx, edx; pftDueTime
0x18000a738  mov     rcx, rbp; pti
0x18000a73b  call    cs:__imp_SetThreadpoolTimer
0x18000a741  mov     edx, 1; fCancelPendingCallbacks
0x18000a746  mov     rcx, rbp; pti
0x18000a749  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a74f  mov     rcx, rbp; pti
0x18000a752  call    cs:__imp_CloseThreadpoolTimer
0x18000a758  mov     ecx, ebx; dwErrCode
0x18000a75a  call    cs:__imp_SetLastError
0x18000a760  mov     [rdi+38h], r15
0x18000a764  mov     ecx, r14d; dwErrCode
0x18000a767  call    cs:__imp_SetLastError
0x18000a76d  mov     rcx, [rdi+38h]; pti
0x18000a771  test    rcx, rcx
0x18000a774  jz      short loc_18000A797
0x18000a776  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a77f  mov     r9d, 4E2h; msWindowLength
0x18000a785  xor     r8d, r8d; msPeriod
0x18000a788  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000a78d  call    cs:__imp_SetThreadpoolTimer
0x18000a793  mov     byte ptr [rdi+40h], 1
0x18000a797  test    rsi, rsi
0x18000a79a  jz      short loc_18000A7A6
0x18000a79c  mov     rcx, rsi; SRWLock
0x18000a79f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a7a5  nop
0x18000a7a6  add     rsp, 38h
0x18000a7aa  pop     r15
0x18000a7ac  pop     r14
0x18000a7ae  pop     rdi
0x18000a7af  pop     rsi
0x18000a7b0  pop     rbp
0x18000a7b1  pop     rbx
0x18000a7b2  retn
```
