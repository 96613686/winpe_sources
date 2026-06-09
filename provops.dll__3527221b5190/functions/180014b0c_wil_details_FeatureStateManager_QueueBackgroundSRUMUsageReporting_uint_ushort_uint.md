# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180014b0c`
- end: `0x180014c95`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001b830`

## callees

- `0x180014b0c`
- `0x180021370`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014bba`
- `msvcrt!memcpy_s` at `0x180014bba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014b6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014b6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014c74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c3c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014beb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014beb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014c10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014c62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014c10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014c62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014c27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014c27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014c1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014c1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
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
0x180014b0c  push    rbx
0x180014b0e  push    rbp
0x180014b0f  push    rsi
0x180014b10  push    rdi
0x180014b11  push    r14
0x180014b13  push    r15
0x180014b15  sub     rsp, 48h
0x180014b19  mov     rax, cs:__security_cookie
0x180014b20  xor     rax, rsp
0x180014b23  mov     [rsp+78h+var_40], rax
0x180014b28  mov     r14d, r9d
0x180014b2b  movzx   ebp, r8w
0x180014b2f  mov     ebx, edx
0x180014b31  mov     rdi, rcx
0x180014b34  cmp     byte ptr [rcx], 0
0x180014b37  jz      loc_180014C7B
0x180014b3d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014b44  jnz     loc_180014C7B
0x180014b4a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014b51  test    rax, rax
0x180014b54  jz      short loc_180014B63
0x180014b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b5b  test    al, al
0x180014b5d  jnz     loc_180014C7B
0x180014b63  lea     rsi, [rdi+28h]
0x180014b67  mov     rcx, rsi; SRWLock
0x180014b6a  call    cs:__imp_AcquireSRWLockExclusive
0x180014b70  xor     eax, eax
0x180014b72  mov     [rsp+78h+var_4A], ax
0x180014b77  mov     [rsp+78h+Source], ebx
0x180014b7b  mov     [rsp+78h+var_4C], bp
0x180014b80  mov     [rsp+78h+var_48], r14d
0x180014b85  lea     rbx, [rdi+0E8h]
0x180014b8c  lea     ebp, [rax+0Ch]
0x180014b8f  mov     edx, ebp; unsigned __int64
0x180014b91  mov     rcx, rbx; this
0x180014b94  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014b99  test    al, al
0x180014b9b  jz      short loc_180014BC4
0x180014b9d  mov     rcx, [rbx+8]; Destination
0x180014ba1  mov     rax, [rbx+10h]
0x180014ba5  sub     rax, rcx
0x180014ba8  cmp     rcx, [rbx+10h]
0x180014bac  sbb     rdx, rdx
0x180014baf  and     rdx, rax; DestinationSize
0x180014bb2  mov     r9d, ebp; SourceSize
0x180014bb5  lea     r8, [rsp+78h+Source]; Source
0x180014bba  call    cs:__imp_memcpy_s
0x180014bc0  add     [rbx+8], rbp
0x180014bc4  cmp     byte ptr [rdi+40h], 0
0x180014bc8  jnz     loc_180014C6C
0x180014bce  cmp     qword ptr [rdi+38h], 0
0x180014bd3  jnz     short loc_180014C42
0x180014bd5  call    cs:__imp_GetLastError
0x180014bdb  mov     r14d, eax
0x180014bde  xor     r8d, r8d; pcbe
0x180014be1  mov     rdx, rdi; pv
0x180014be4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014beb  call    cs:__imp_CreateThreadpoolTimer
0x180014bf1  mov     r15, rax
0x180014bf4  mov     rbp, [rdi+38h]
0x180014bf8  test    rbp, rbp
0x180014bfb  jz      short loc_180014C35
0x180014bfd  call    cs:__imp_GetLastError
0x180014c03  mov     ebx, eax
0x180014c05  xor     r9d, r9d; msWindowLength
0x180014c08  xor     r8d, r8d; msPeriod
0x180014c0b  xor     edx, edx; pftDueTime
0x180014c0d  mov     rcx, rbp; pti
0x180014c10  call    cs:__imp_SetThreadpoolTimer
0x180014c16  mov     edx, 1; fCancelPendingCallbacks
0x180014c1b  mov     rcx, rbp; pti
0x180014c1e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014c24  mov     rcx, rbp; pti
0x180014c27  call    cs:__imp_CloseThreadpoolTimer
0x180014c2d  mov     ecx, ebx; dwErrCode
0x180014c2f  call    cs:__imp_SetLastError
0x180014c35  mov     [rdi+38h], r15
0x180014c39  mov     ecx, r14d; dwErrCode
0x180014c3c  call    cs:__imp_SetLastError
0x180014c42  mov     rcx, [rdi+38h]; pti
0x180014c46  test    rcx, rcx
0x180014c49  jz      short loc_180014C6C
0x180014c4b  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180014c54  mov     r9d, 4E2h; msWindowLength
0x180014c5a  xor     r8d, r8d; msPeriod
0x180014c5d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180014c62  call    cs:__imp_SetThreadpoolTimer
0x180014c68  mov     byte ptr [rdi+40h], 1
0x180014c6c  test    rsi, rsi
0x180014c6f  jz      short loc_180014C7B
0x180014c71  mov     rcx, rsi; SRWLock
0x180014c74  call    cs:__imp_ReleaseSRWLockExclusive
0x180014c7a  nop
0x180014c7b  mov     rcx, [rsp+78h+var_40]
0x180014c80  xor     rcx, rsp; StackCookie
0x180014c83  call    __security_check_cookie
0x180014c88  add     rsp, 48h
0x180014c8c  pop     r15
0x180014c8e  pop     r14
0x180014c90  pop     rdi
0x180014c91  pop     rsi
0x180014c92  pop     rbp
0x180014c93  pop     rbx
0x180014c94  retn
```
