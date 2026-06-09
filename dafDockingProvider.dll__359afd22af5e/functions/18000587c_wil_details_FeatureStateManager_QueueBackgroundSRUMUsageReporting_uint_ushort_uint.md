# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000587c`
- end: `0x180005a05`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007a10`

## callees

- `0x18000587c`
- `0x18000802c`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000592a`
- `msvcrt!memcpy_s` at `0x18000592a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800059e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800059e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000596d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000599f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000599f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000598e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000598e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005980`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800059d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005980`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800059d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000595b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000595b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005997`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005997`

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
0x18000587c  push    rbx
0x18000587e  push    rbp
0x18000587f  push    rsi
0x180005880  push    rdi
0x180005881  push    r14
0x180005883  push    r15
0x180005885  sub     rsp, 48h
0x180005889  mov     rax, cs:__security_cookie
0x180005890  xor     rax, rsp
0x180005893  mov     [rsp+78h+var_40], rax
0x180005898  mov     r14d, r9d
0x18000589b  movzx   ebp, r8w
0x18000589f  mov     ebx, edx
0x1800058a1  mov     rdi, rcx
0x1800058a4  cmp     byte ptr [rcx], 0
0x1800058a7  jz      loc_1800059EB
0x1800058ad  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800058b4  jnz     loc_1800059EB
0x1800058ba  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800058c1  test    rax, rax
0x1800058c4  jz      short loc_1800058D3
0x1800058c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058cb  test    al, al
0x1800058cd  jnz     loc_1800059EB
0x1800058d3  lea     rsi, [rdi+28h]
0x1800058d7  mov     rcx, rsi; SRWLock
0x1800058da  call    cs:__imp_AcquireSRWLockExclusive
0x1800058e0  xor     eax, eax
0x1800058e2  mov     [rsp+78h+var_4A], ax
0x1800058e7  mov     [rsp+78h+Source], ebx
0x1800058eb  mov     [rsp+78h+var_4C], bp
0x1800058f0  mov     [rsp+78h+var_48], r14d
0x1800058f5  lea     rbx, [rdi+0E8h]
0x1800058fc  lea     ebp, [rax+0Ch]
0x1800058ff  mov     edx, ebp; unsigned __int64
0x180005901  mov     rcx, rbx; this
0x180005904  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005909  test    al, al
0x18000590b  jz      short loc_180005934
0x18000590d  mov     rcx, [rbx+8]; Destination
0x180005911  mov     rax, [rbx+10h]
0x180005915  sub     rax, rcx
0x180005918  cmp     rcx, [rbx+10h]
0x18000591c  sbb     rdx, rdx
0x18000591f  and     rdx, rax; DestinationSize
0x180005922  mov     r9d, ebp; SourceSize
0x180005925  lea     r8, [rsp+78h+Source]; Source
0x18000592a  call    cs:__imp_memcpy_s
0x180005930  add     [rbx+8], rbp
0x180005934  cmp     byte ptr [rdi+40h], 0
0x180005938  jnz     loc_1800059DC
0x18000593e  cmp     qword ptr [rdi+38h], 0
0x180005943  jnz     short loc_1800059B2
0x180005945  call    cs:__imp_GetLastError
0x18000594b  mov     r14d, eax
0x18000594e  xor     r8d, r8d; pcbe
0x180005951  mov     rdx, rdi; pv
0x180005954  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000595b  call    cs:__imp_CreateThreadpoolTimer
0x180005961  mov     r15, rax
0x180005964  mov     rbp, [rdi+38h]
0x180005968  test    rbp, rbp
0x18000596b  jz      short loc_1800059A5
0x18000596d  call    cs:__imp_GetLastError
0x180005973  mov     ebx, eax
0x180005975  xor     r9d, r9d; msWindowLength
0x180005978  xor     r8d, r8d; msPeriod
0x18000597b  xor     edx, edx; pftDueTime
0x18000597d  mov     rcx, rbp; pti
0x180005980  call    cs:__imp_SetThreadpoolTimer
0x180005986  mov     edx, 1; fCancelPendingCallbacks
0x18000598b  mov     rcx, rbp; pti
0x18000598e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005994  mov     rcx, rbp; pti
0x180005997  call    cs:__imp_CloseThreadpoolTimer
0x18000599d  mov     ecx, ebx; dwErrCode
0x18000599f  call    cs:__imp_SetLastError
0x1800059a5  mov     [rdi+38h], r15
0x1800059a9  mov     ecx, r14d; dwErrCode
0x1800059ac  call    cs:__imp_SetLastError
0x1800059b2  mov     rcx, [rdi+38h]; pti
0x1800059b6  test    rcx, rcx
0x1800059b9  jz      short loc_1800059DC
0x1800059bb  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800059c4  mov     r9d, 4E2h; msWindowLength
0x1800059ca  xor     r8d, r8d; msPeriod
0x1800059cd  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800059d2  call    cs:__imp_SetThreadpoolTimer
0x1800059d8  mov     byte ptr [rdi+40h], 1
0x1800059dc  test    rsi, rsi
0x1800059df  jz      short loc_1800059EB
0x1800059e1  mov     rcx, rsi; SRWLock
0x1800059e4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800059ea  nop
0x1800059eb  mov     rcx, [rsp+78h+var_40]
0x1800059f0  xor     rcx, rsp; StackCookie
0x1800059f3  call    __security_check_cookie
0x1800059f8  add     rsp, 48h
0x1800059fc  pop     r15
0x1800059fe  pop     r14
0x180005a00  pop     rdi
0x180005a01  pop     rsi
0x180005a02  pop     rbp
0x180005a03  pop     rbx
0x180005a04  retn
```
