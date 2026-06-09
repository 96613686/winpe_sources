# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ef24`
- end: `0x18000f0ad`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011810`

## callees

- `0x18000ef24`
- `0x1800124ac`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000efd2`
- `msvcrt!memcpy_s` at `0x18000efd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f08c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f08c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f047`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f054`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f047`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f015`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f03f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f03f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f003`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f003`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f036`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f036`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f028`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f07a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f028`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f07a`

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
0x18000ef24  push    rbx
0x18000ef26  push    rbp
0x18000ef27  push    rsi
0x18000ef28  push    rdi
0x18000ef29  push    r14
0x18000ef2b  push    r15
0x18000ef2d  sub     rsp, 48h
0x18000ef31  mov     rax, cs:__security_cookie
0x18000ef38  xor     rax, rsp
0x18000ef3b  mov     [rsp+78h+var_40], rax
0x18000ef40  mov     r14d, r9d
0x18000ef43  movzx   ebp, r8w
0x18000ef47  mov     ebx, edx
0x18000ef49  mov     rdi, rcx
0x18000ef4c  cmp     byte ptr [rcx], 0
0x18000ef4f  jz      loc_18000F093
0x18000ef55  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ef5c  jnz     loc_18000F093
0x18000ef62  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ef69  test    rax, rax
0x18000ef6c  jz      short loc_18000EF7B
0x18000ef6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef73  test    al, al
0x18000ef75  jnz     loc_18000F093
0x18000ef7b  lea     rsi, [rdi+28h]
0x18000ef7f  mov     rcx, rsi; SRWLock
0x18000ef82  call    cs:__imp_AcquireSRWLockExclusive
0x18000ef88  xor     eax, eax
0x18000ef8a  mov     [rsp+78h+var_4A], ax
0x18000ef8f  mov     [rsp+78h+Source], ebx
0x18000ef93  mov     [rsp+78h+var_4C], bp
0x18000ef98  mov     [rsp+78h+var_48], r14d
0x18000ef9d  lea     rbx, [rdi+0E8h]
0x18000efa4  lea     ebp, [rax+0Ch]
0x18000efa7  mov     edx, ebp; unsigned __int64
0x18000efa9  mov     rcx, rbx; this
0x18000efac  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000efb1  test    al, al
0x18000efb3  jz      short loc_18000EFDC
0x18000efb5  mov     rcx, [rbx+8]; Destination
0x18000efb9  mov     rax, [rbx+10h]
0x18000efbd  sub     rax, rcx
0x18000efc0  cmp     rcx, [rbx+10h]
0x18000efc4  sbb     rdx, rdx
0x18000efc7  and     rdx, rax; DestinationSize
0x18000efca  mov     r9d, ebp; SourceSize
0x18000efcd  lea     r8, [rsp+78h+Source]; Source
0x18000efd2  call    cs:__imp_memcpy_s
0x18000efd8  add     [rbx+8], rbp
0x18000efdc  cmp     byte ptr [rdi+40h], 0
0x18000efe0  jnz     loc_18000F084
0x18000efe6  cmp     qword ptr [rdi+38h], 0
0x18000efeb  jnz     short loc_18000F05A
0x18000efed  call    cs:__imp_GetLastError
0x18000eff3  mov     r14d, eax
0x18000eff6  xor     r8d, r8d; pcbe
0x18000eff9  mov     rdx, rdi; pv
0x18000effc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f003  call    cs:__imp_CreateThreadpoolTimer
0x18000f009  mov     r15, rax
0x18000f00c  mov     rbp, [rdi+38h]
0x18000f010  test    rbp, rbp
0x18000f013  jz      short loc_18000F04D
0x18000f015  call    cs:__imp_GetLastError
0x18000f01b  mov     ebx, eax
0x18000f01d  xor     r9d, r9d; msWindowLength
0x18000f020  xor     r8d, r8d; msPeriod
0x18000f023  xor     edx, edx; pftDueTime
0x18000f025  mov     rcx, rbp; pti
0x18000f028  call    cs:__imp_SetThreadpoolTimer
0x18000f02e  mov     edx, 1; fCancelPendingCallbacks
0x18000f033  mov     rcx, rbp; pti
0x18000f036  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f03c  mov     rcx, rbp; pti
0x18000f03f  call    cs:__imp_CloseThreadpoolTimer
0x18000f045  mov     ecx, ebx; dwErrCode
0x18000f047  call    cs:__imp_SetLastError
0x18000f04d  mov     [rdi+38h], r15
0x18000f051  mov     ecx, r14d; dwErrCode
0x18000f054  call    cs:__imp_SetLastError
0x18000f05a  mov     rcx, [rdi+38h]; pti
0x18000f05e  test    rcx, rcx
0x18000f061  jz      short loc_18000F084
0x18000f063  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000f06c  mov     r9d, 4E2h; msWindowLength
0x18000f072  xor     r8d, r8d; msPeriod
0x18000f075  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000f07a  call    cs:__imp_SetThreadpoolTimer
0x18000f080  mov     byte ptr [rdi+40h], 1
0x18000f084  test    rsi, rsi
0x18000f087  jz      short loc_18000F093
0x18000f089  mov     rcx, rsi; SRWLock
0x18000f08c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f092  nop
0x18000f093  mov     rcx, [rsp+78h+var_40]
0x18000f098  xor     rcx, rsp; StackCookie
0x18000f09b  call    __security_check_cookie
0x18000f0a0  add     rsp, 48h
0x18000f0a4  pop     r15
0x18000f0a6  pop     r14
0x18000f0a8  pop     rdi
0x18000f0a9  pop     rsi
0x18000f0aa  pop     rbp
0x18000f0ab  pop     rbx
0x18000f0ac  retn
```
