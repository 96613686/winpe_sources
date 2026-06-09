# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000629c`
- end: `0x180006424`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007f60`

## callees

- `0x18000629c`
- `0x1800084cc`
- `0x18000bbf0`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000634a`
- `msvcrt!memcpy_s` at `0x18000634a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800063b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800063b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000637b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000637b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800063ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800063ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000638d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063cc`

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
0x18000629c  push    rbx
0x18000629e  push    rbp
0x18000629f  push    rsi
0x1800062a0  push    rdi
0x1800062a1  push    r14
0x1800062a3  push    r15
0x1800062a5  sub     rsp, 48h
0x1800062a9  mov     rax, cs:__security_cookie
0x1800062b0  xor     rax, rsp
0x1800062b3  mov     [rsp+78h+var_40], rax
0x1800062b8  cmp     byte ptr [rcx], 0
0x1800062bb  mov     r14d, r9d
0x1800062be  movzx   ebp, r8w
0x1800062c2  mov     ebx, edx
0x1800062c4  mov     rdi, rcx
0x1800062c7  jz      loc_18000640A
0x1800062cd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800062d4  jnz     loc_18000640A
0x1800062da  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800062e1  test    rax, rax
0x1800062e4  jz      short loc_1800062F3
0x1800062e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062eb  test    al, al
0x1800062ed  jnz     loc_18000640A
0x1800062f3  lea     rsi, [rdi+28h]
0x1800062f7  mov     rcx, rsi; SRWLock
0x1800062fa  call    cs:__imp_AcquireSRWLockExclusive
0x180006300  xor     eax, eax
0x180006302  mov     [rsp+78h+Source], ebx
0x180006306  mov     [rsp+78h+var_4C], bp
0x18000630b  lea     rbx, [rdi+0E8h]
0x180006312  mov     rcx, rbx; this
0x180006315  mov     [rsp+78h+var_4A], ax
0x18000631a  mov     [rsp+78h+var_48], r14d
0x18000631f  lea     ebp, [rax+0Ch]
0x180006322  mov     edx, ebp; unsigned __int64
0x180006324  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006329  test    al, al
0x18000632b  jz      short loc_180006354
0x18000632d  mov     rcx, [rbx+8]; Destination
0x180006331  lea     r8, [rsp+78h+Source]; Source
0x180006336  mov     rax, [rbx+10h]
0x18000633a  mov     r9d, ebp; SourceSize
0x18000633d  sub     rax, rcx
0x180006340  cmp     rcx, [rbx+10h]
0x180006344  sbb     rdx, rdx
0x180006347  and     rdx, rax; DestinationSize
0x18000634a  call    cs:__imp_memcpy_s
0x180006350  add     [rbx+8], rbp
0x180006354  cmp     byte ptr [rdi+40h], 0
0x180006358  jnz     loc_1800063FC
0x18000635e  cmp     qword ptr [rdi+38h], 0
0x180006363  jnz     short loc_1800063D2
0x180006365  call    cs:__imp_GetLastError
0x18000636b  xor     r8d, r8d; pcbe
0x18000636e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006375  mov     rdx, rdi; pv
0x180006378  mov     r14d, eax
0x18000637b  call    cs:__imp_CreateThreadpoolTimer
0x180006381  mov     rbp, [rdi+38h]
0x180006385  mov     r15, rax
0x180006388  test    rbp, rbp
0x18000638b  jz      short loc_1800063C5
0x18000638d  call    cs:__imp_GetLastError
0x180006393  xor     r9d, r9d; msWindowLength
0x180006396  xor     r8d, r8d; msPeriod
0x180006399  xor     edx, edx; pftDueTime
0x18000639b  mov     rcx, rbp; pti
0x18000639e  mov     ebx, eax
0x1800063a0  call    cs:__imp_SetThreadpoolTimer
0x1800063a6  mov     edx, 1; fCancelPendingCallbacks
0x1800063ab  mov     rcx, rbp; pti
0x1800063ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800063b4  mov     rcx, rbp; pti
0x1800063b7  call    cs:__imp_CloseThreadpoolTimer
0x1800063bd  mov     ecx, ebx; dwErrCode
0x1800063bf  call    cs:__imp_SetLastError
0x1800063c5  mov     ecx, r14d; dwErrCode
0x1800063c8  mov     [rdi+38h], r15
0x1800063cc  call    cs:__imp_SetLastError
0x1800063d2  mov     rcx, [rdi+38h]; pti
0x1800063d6  test    rcx, rcx
0x1800063d9  jz      short loc_1800063FC
0x1800063db  mov     r9d, 4E2h; msWindowLength
0x1800063e1  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800063ea  xor     r8d, r8d; msPeriod
0x1800063ed  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800063f2  call    cs:__imp_SetThreadpoolTimer
0x1800063f8  mov     byte ptr [rdi+40h], 1
0x1800063fc  test    rsi, rsi
0x1800063ff  jz      short loc_18000640A
0x180006401  mov     rcx, rsi; SRWLock
0x180006404  call    cs:__imp_ReleaseSRWLockExclusive
0x18000640a  mov     rcx, [rsp+78h+var_40]
0x18000640f  xor     rcx, rsp; StackCookie
0x180006412  call    __security_check_cookie
0x180006417  add     rsp, 48h
0x18000641b  pop     r15
0x18000641d  pop     r14
0x18000641f  pop     rdi
0x180006420  pop     rsi
0x180006421  pop     rbp
0x180006422  pop     rbx
0x180006423  retn
```
