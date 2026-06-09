# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800b5404`
- end: `0x1800b558c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800b7a70`

## callees

- `0x1800b5404`
- `0x1800b829c`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800b54b2`
- `msvcrt!memcpy_s` at `0x1800b54b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5527`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5534`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5527`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b556c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b556c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5462`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5462`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b5516`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b5516`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b551f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b551f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b54e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b54e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b5508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b555a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b5508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b555a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x1800b5404  push    rbx
0x1800b5406  push    rbp
0x1800b5407  push    rsi
0x1800b5408  push    rdi
0x1800b5409  push    r14
0x1800b540b  push    r15
0x1800b540d  sub     rsp, 48h
0x1800b5411  mov     rax, cs:__security_cookie
0x1800b5418  xor     rax, rsp
0x1800b541b  mov     [rsp+78h+var_40], rax
0x1800b5420  cmp     byte ptr [rcx], 0
0x1800b5423  mov     r14d, r9d
0x1800b5426  movzx   ebp, r8w
0x1800b542a  mov     ebx, edx
0x1800b542c  mov     rdi, rcx
0x1800b542f  jz      loc_1800B5572
0x1800b5435  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800b543c  jnz     loc_1800B5572
0x1800b5442  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800b5449  test    rax, rax
0x1800b544c  jz      short loc_1800B545B
0x1800b544e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5453  test    al, al
0x1800b5455  jnz     loc_1800B5572
0x1800b545b  lea     rsi, [rdi+28h]
0x1800b545f  mov     rcx, rsi; SRWLock
0x1800b5462  call    cs:__imp_AcquireSRWLockExclusive
0x1800b5468  xor     eax, eax
0x1800b546a  mov     [rsp+78h+Source], ebx
0x1800b546e  mov     [rsp+78h+var_4C], bp
0x1800b5473  lea     rbx, [rdi+0E8h]
0x1800b547a  mov     rcx, rbx; this
0x1800b547d  mov     [rsp+78h+var_4A], ax
0x1800b5482  mov     [rsp+78h+var_48], r14d
0x1800b5487  lea     ebp, [rax+0Ch]
0x1800b548a  mov     edx, ebp; unsigned __int64
0x1800b548c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800b5491  test    al, al
0x1800b5493  jz      short loc_1800B54BC
0x1800b5495  mov     rcx, [rbx+8]; Destination
0x1800b5499  lea     r8, [rsp+78h+Source]; Source
0x1800b549e  mov     rax, [rbx+10h]
0x1800b54a2  mov     r9d, ebp; SourceSize
0x1800b54a5  sub     rax, rcx
0x1800b54a8  cmp     rcx, [rbx+10h]
0x1800b54ac  sbb     rdx, rdx
0x1800b54af  and     rdx, rax; DestinationSize
0x1800b54b2  call    cs:__imp_memcpy_s
0x1800b54b8  add     [rbx+8], rbp
0x1800b54bc  cmp     byte ptr [rdi+40h], 0
0x1800b54c0  jnz     loc_1800B5564
0x1800b54c6  cmp     qword ptr [rdi+38h], 0
0x1800b54cb  jnz     short loc_1800B553A
0x1800b54cd  call    cs:__imp_GetLastError
0x1800b54d3  xor     r8d, r8d; pcbe
0x1800b54d6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b54dd  mov     rdx, rdi; pv
0x1800b54e0  mov     r14d, eax
0x1800b54e3  call    cs:__imp_CreateThreadpoolTimer
0x1800b54e9  mov     rbp, [rdi+38h]
0x1800b54ed  mov     r15, rax
0x1800b54f0  test    rbp, rbp
0x1800b54f3  jz      short loc_1800B552D
0x1800b54f5  call    cs:__imp_GetLastError
0x1800b54fb  xor     r9d, r9d; msWindowLength
0x1800b54fe  xor     r8d, r8d; msPeriod
0x1800b5501  xor     edx, edx; pftDueTime
0x1800b5503  mov     rcx, rbp; pti
0x1800b5506  mov     ebx, eax
0x1800b5508  call    cs:__imp_SetThreadpoolTimer
0x1800b550e  mov     edx, 1; fCancelPendingCallbacks
0x1800b5513  mov     rcx, rbp; pti
0x1800b5516  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b551c  mov     rcx, rbp; pti
0x1800b551f  call    cs:__imp_CloseThreadpoolTimer
0x1800b5525  mov     ecx, ebx; dwErrCode
0x1800b5527  call    cs:__imp_SetLastError
0x1800b552d  mov     ecx, r14d; dwErrCode
0x1800b5530  mov     [rdi+38h], r15
0x1800b5534  call    cs:__imp_SetLastError
0x1800b553a  mov     rcx, [rdi+38h]; pti
0x1800b553e  test    rcx, rcx
0x1800b5541  jz      short loc_1800B5564
0x1800b5543  mov     r9d, 4E2h; msWindowLength
0x1800b5549  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800b5552  xor     r8d, r8d; msPeriod
0x1800b5555  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800b555a  call    cs:__imp_SetThreadpoolTimer
0x1800b5560  mov     byte ptr [rdi+40h], 1
0x1800b5564  test    rsi, rsi
0x1800b5567  jz      short loc_1800B5572
0x1800b5569  mov     rcx, rsi; SRWLock
0x1800b556c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b5572  mov     rcx, [rsp+78h+var_40]
0x1800b5577  xor     rcx, rsp; StackCookie
0x1800b557a  call    __security_check_cookie
0x1800b557f  add     rsp, 48h
0x1800b5583  pop     r15
0x1800b5585  pop     r14
0x1800b5587  pop     rdi
0x1800b5588  pop     rsi
0x1800b5589  pop     rbp
0x1800b558a  pop     rbx
0x1800b558b  retn
```
