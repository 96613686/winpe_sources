# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001b478`
- end: `0x18001b601`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180020770`

## callees

- `0x18001b478`
- `0x180022284`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b526`
- `msvcrt!memcpy_s` at `0x18001b526`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b4d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b4d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b59b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b5a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b59b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b569`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b57c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b5ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b57c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b5ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b593`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b593`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b557`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b557`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b58a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b58a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
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
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x18001b478  push    rbx
0x18001b47a  push    rbp
0x18001b47b  push    rsi
0x18001b47c  push    rdi
0x18001b47d  push    r14
0x18001b47f  push    r15
0x18001b481  sub     rsp, 48h
0x18001b485  mov     rax, cs:__security_cookie
0x18001b48c  xor     rax, rsp
0x18001b48f  mov     [rsp+78h+var_40], rax
0x18001b494  mov     r14d, r9d
0x18001b497  movzx   ebp, r8w
0x18001b49b  mov     ebx, edx
0x18001b49d  mov     rdi, rcx
0x18001b4a0  cmp     byte ptr [rcx], 0
0x18001b4a3  jz      loc_18001B5E7
0x18001b4a9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001b4b0  jnz     loc_18001B5E7
0x18001b4b6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b4bd  test    rax, rax
0x18001b4c0  jz      short loc_18001B4CF
0x18001b4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c7  test    al, al
0x18001b4c9  jnz     loc_18001B5E7
0x18001b4cf  lea     rsi, [rdi+28h]
0x18001b4d3  mov     rcx, rsi; SRWLock
0x18001b4d6  call    cs:__imp_AcquireSRWLockExclusive
0x18001b4dc  xor     eax, eax
0x18001b4de  mov     [rsp+78h+var_4A], ax
0x18001b4e3  mov     [rsp+78h+Source], ebx
0x18001b4e7  mov     [rsp+78h+var_4C], bp
0x18001b4ec  mov     [rsp+78h+var_48], r14d
0x18001b4f1  lea     rbx, [rdi+0E8h]
0x18001b4f8  lea     ebp, [rax+0Ch]
0x18001b4fb  mov     edx, ebp; unsigned __int64
0x18001b4fd  mov     rcx, rbx; this
0x18001b500  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b505  test    al, al
0x18001b507  jz      short loc_18001B530
0x18001b509  mov     rcx, [rbx+8]; Destination
0x18001b50d  mov     rax, [rbx+10h]
0x18001b511  sub     rax, rcx
0x18001b514  cmp     rcx, [rbx+10h]
0x18001b518  sbb     rdx, rdx
0x18001b51b  and     rdx, rax; DestinationSize
0x18001b51e  mov     r9d, ebp; SourceSize
0x18001b521  lea     r8, [rsp+78h+Source]; Source
0x18001b526  call    cs:__imp_memcpy_s
0x18001b52c  add     [rbx+8], rbp
0x18001b530  cmp     byte ptr [rdi+40h], 0
0x18001b534  jnz     loc_18001B5D8
0x18001b53a  cmp     qword ptr [rdi+38h], 0
0x18001b53f  jnz     short loc_18001B5AE
0x18001b541  call    cs:__imp_GetLastError
0x18001b547  mov     r14d, eax
0x18001b54a  xor     r8d, r8d; pcbe
0x18001b54d  mov     rdx, rdi; pv
0x18001b550  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b557  call    cs:__imp_CreateThreadpoolTimer
0x18001b55d  mov     r15, rax
0x18001b560  mov     rbp, [rdi+38h]
0x18001b564  test    rbp, rbp
0x18001b567  jz      short loc_18001B5A1
0x18001b569  call    cs:__imp_GetLastError
0x18001b56f  mov     ebx, eax
0x18001b571  xor     r9d, r9d; msWindowLength
0x18001b574  xor     r8d, r8d; msPeriod
0x18001b577  xor     edx, edx; pftDueTime
0x18001b579  mov     rcx, rbp; pti
0x18001b57c  call    cs:__imp_SetThreadpoolTimer
0x18001b582  mov     edx, 1; fCancelPendingCallbacks
0x18001b587  mov     rcx, rbp; pti
0x18001b58a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b590  mov     rcx, rbp; pti
0x18001b593  call    cs:__imp_CloseThreadpoolTimer
0x18001b599  mov     ecx, ebx; dwErrCode
0x18001b59b  call    cs:__imp_SetLastError
0x18001b5a1  mov     [rdi+38h], r15
0x18001b5a5  mov     ecx, r14d; dwErrCode
0x18001b5a8  call    cs:__imp_SetLastError
0x18001b5ae  mov     rcx, [rdi+38h]; pti
0x18001b5b2  test    rcx, rcx
0x18001b5b5  jz      short loc_18001B5D8
0x18001b5b7  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001b5c0  mov     r9d, 4E2h; msWindowLength
0x18001b5c6  xor     r8d, r8d; msPeriod
0x18001b5c9  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18001b5ce  call    cs:__imp_SetThreadpoolTimer
0x18001b5d4  mov     byte ptr [rdi+40h], 1
0x18001b5d8  test    rsi, rsi
0x18001b5db  jz      short loc_18001B5E7
0x18001b5dd  mov     rcx, rsi; SRWLock
0x18001b5e0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b5e6  nop
0x18001b5e7  mov     rcx, [rsp+78h+var_40]
0x18001b5ec  xor     rcx, rsp; StackCookie
0x18001b5ef  call    __security_check_cookie
0x18001b5f4  add     rsp, 48h
0x18001b5f8  pop     r15
0x18001b5fa  pop     r14
0x18001b5fc  pop     rdi
0x18001b5fd  pop     rsi
0x18001b5fe  pop     rbp
0x18001b5ff  pop     rbx
0x18001b600  retn
```
