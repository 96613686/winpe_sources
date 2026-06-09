# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a89c`
- end: `0x18000aa24`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c560`

## callees

- `0x18000a89c`
- `0x18000cacc`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a94a`
- `msvcrt!memcpy_s` at `0x18000a94a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a98d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a9f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a97b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a97b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a9ae`

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
0x18000a89c  push    rbx
0x18000a89e  push    rbp
0x18000a89f  push    rsi
0x18000a8a0  push    rdi
0x18000a8a1  push    r14
0x18000a8a3  push    r15
0x18000a8a5  sub     rsp, 48h
0x18000a8a9  mov     rax, cs:__security_cookie
0x18000a8b0  xor     rax, rsp
0x18000a8b3  mov     [rsp+78h+var_40], rax
0x18000a8b8  cmp     byte ptr [rcx], 0
0x18000a8bb  mov     r14d, r9d
0x18000a8be  movzx   ebp, r8w
0x18000a8c2  mov     ebx, edx
0x18000a8c4  mov     rdi, rcx
0x18000a8c7  jz      loc_18000AA0A
0x18000a8cd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a8d4  jnz     loc_18000AA0A
0x18000a8da  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a8e1  test    rax, rax
0x18000a8e4  jz      short loc_18000A8F3
0x18000a8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8eb  test    al, al
0x18000a8ed  jnz     loc_18000AA0A
0x18000a8f3  lea     rsi, [rdi+28h]
0x18000a8f7  mov     rcx, rsi; SRWLock
0x18000a8fa  call    cs:__imp_AcquireSRWLockExclusive
0x18000a900  xor     eax, eax
0x18000a902  mov     [rsp+78h+Source], ebx
0x18000a906  mov     [rsp+78h+var_4C], bp
0x18000a90b  lea     rbx, [rdi+0E8h]
0x18000a912  mov     rcx, rbx; this
0x18000a915  mov     [rsp+78h+var_4A], ax
0x18000a91a  mov     [rsp+78h+var_48], r14d
0x18000a91f  lea     ebp, [rax+0Ch]
0x18000a922  mov     edx, ebp; unsigned __int64
0x18000a924  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a929  test    al, al
0x18000a92b  jz      short loc_18000A954
0x18000a92d  mov     rcx, [rbx+8]; Destination
0x18000a931  lea     r8, [rsp+78h+Source]; Source
0x18000a936  mov     rax, [rbx+10h]
0x18000a93a  mov     r9d, ebp; SourceSize
0x18000a93d  sub     rax, rcx
0x18000a940  cmp     rcx, [rbx+10h]
0x18000a944  sbb     rdx, rdx
0x18000a947  and     rdx, rax; DestinationSize
0x18000a94a  call    cs:__imp_memcpy_s
0x18000a950  add     [rbx+8], rbp
0x18000a954  cmp     byte ptr [rdi+40h], 0
0x18000a958  jnz     loc_18000A9FC
0x18000a95e  cmp     qword ptr [rdi+38h], 0
0x18000a963  jnz     short loc_18000A9D2
0x18000a965  call    cs:__imp_GetLastError
0x18000a96b  xor     r8d, r8d; pcbe
0x18000a96e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a975  mov     rdx, rdi; pv
0x18000a978  mov     r14d, eax
0x18000a97b  call    cs:__imp_CreateThreadpoolTimer
0x18000a981  mov     rbp, [rdi+38h]
0x18000a985  mov     r15, rax
0x18000a988  test    rbp, rbp
0x18000a98b  jz      short loc_18000A9C5
0x18000a98d  call    cs:__imp_GetLastError
0x18000a993  xor     r9d, r9d; msWindowLength
0x18000a996  xor     r8d, r8d; msPeriod
0x18000a999  xor     edx, edx; pftDueTime
0x18000a99b  mov     rcx, rbp; pti
0x18000a99e  mov     ebx, eax
0x18000a9a0  call    cs:__imp_SetThreadpoolTimer
0x18000a9a6  mov     edx, 1; fCancelPendingCallbacks
0x18000a9ab  mov     rcx, rbp; pti
0x18000a9ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a9b4  mov     rcx, rbp; pti
0x18000a9b7  call    cs:__imp_CloseThreadpoolTimer
0x18000a9bd  mov     ecx, ebx; dwErrCode
0x18000a9bf  call    cs:__imp_SetLastError
0x18000a9c5  mov     ecx, r14d; dwErrCode
0x18000a9c8  mov     [rdi+38h], r15
0x18000a9cc  call    cs:__imp_SetLastError
0x18000a9d2  mov     rcx, [rdi+38h]; pti
0x18000a9d6  test    rcx, rcx
0x18000a9d9  jz      short loc_18000A9FC
0x18000a9db  mov     r9d, 4E2h; msWindowLength
0x18000a9e1  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a9ea  xor     r8d, r8d; msPeriod
0x18000a9ed  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000a9f2  call    cs:__imp_SetThreadpoolTimer
0x18000a9f8  mov     byte ptr [rdi+40h], 1
0x18000a9fc  test    rsi, rsi
0x18000a9ff  jz      short loc_18000AA0A
0x18000aa01  mov     rcx, rsi; SRWLock
0x18000aa04  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aa0a  mov     rcx, [rsp+78h+var_40]
0x18000aa0f  xor     rcx, rsp; StackCookie
0x18000aa12  call    __security_check_cookie
0x18000aa17  add     rsp, 48h
0x18000aa1b  pop     r15
0x18000aa1d  pop     r14
0x18000aa1f  pop     rdi
0x18000aa20  pop     rsi
0x18000aa21  pop     rbp
0x18000aa22  pop     rbx
0x18000aa23  retn
```
