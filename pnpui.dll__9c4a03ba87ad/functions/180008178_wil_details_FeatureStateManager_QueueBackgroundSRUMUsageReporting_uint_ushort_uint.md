# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008178`
- end: `0x180008300`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a030`

## callees

- `0x180008178`
- `0x18000a5e4`
- `0x18000cd10`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008226`
- `msvcrt!memcpy_s` at `0x180008226`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000829b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000829b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000827c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000827c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008293`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008293`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008257`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008257`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000828a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000828a`

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
0x180008178  push    rbx
0x18000817a  push    rbp
0x18000817b  push    rsi
0x18000817c  push    rdi
0x18000817d  push    r14
0x18000817f  push    r15
0x180008181  sub     rsp, 48h
0x180008185  mov     rax, cs:__security_cookie
0x18000818c  xor     rax, rsp
0x18000818f  mov     [rsp+78h+var_40], rax
0x180008194  cmp     byte ptr [rcx], 0
0x180008197  mov     r14d, r9d
0x18000819a  movzx   ebp, r8w
0x18000819e  mov     ebx, edx
0x1800081a0  mov     rdi, rcx
0x1800081a3  jz      loc_1800082E6
0x1800081a9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800081b0  jnz     loc_1800082E6
0x1800081b6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800081bd  test    rax, rax
0x1800081c0  jz      short loc_1800081CF
0x1800081c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c7  test    al, al
0x1800081c9  jnz     loc_1800082E6
0x1800081cf  lea     rsi, [rdi+28h]
0x1800081d3  mov     rcx, rsi; SRWLock
0x1800081d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800081dc  xor     eax, eax
0x1800081de  mov     [rsp+78h+Source], ebx
0x1800081e2  mov     [rsp+78h+var_4C], bp
0x1800081e7  lea     rbx, [rdi+0E8h]
0x1800081ee  mov     rcx, rbx; this
0x1800081f1  mov     [rsp+78h+var_4A], ax
0x1800081f6  mov     [rsp+78h+var_48], r14d
0x1800081fb  lea     ebp, [rax+0Ch]
0x1800081fe  mov     edx, ebp; unsigned __int64
0x180008200  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008205  test    al, al
0x180008207  jz      short loc_180008230
0x180008209  mov     rcx, [rbx+8]; Destination
0x18000820d  lea     r8, [rsp+78h+Source]; Source
0x180008212  mov     rax, [rbx+10h]
0x180008216  mov     r9d, ebp; SourceSize
0x180008219  sub     rax, rcx
0x18000821c  cmp     rcx, [rbx+10h]
0x180008220  sbb     rdx, rdx
0x180008223  and     rdx, rax; DestinationSize
0x180008226  call    cs:__imp_memcpy_s
0x18000822c  add     [rbx+8], rbp
0x180008230  cmp     byte ptr [rdi+40h], 0
0x180008234  jnz     loc_1800082D8
0x18000823a  cmp     qword ptr [rdi+38h], 0
0x18000823f  jnz     short loc_1800082AE
0x180008241  call    cs:__imp_GetLastError
0x180008247  xor     r8d, r8d; pcbe
0x18000824a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008251  mov     rdx, rdi; pv
0x180008254  mov     r14d, eax
0x180008257  call    cs:__imp_CreateThreadpoolTimer
0x18000825d  mov     rbp, [rdi+38h]
0x180008261  mov     r15, rax
0x180008264  test    rbp, rbp
0x180008267  jz      short loc_1800082A1
0x180008269  call    cs:__imp_GetLastError
0x18000826f  xor     r9d, r9d; msWindowLength
0x180008272  xor     r8d, r8d; msPeriod
0x180008275  xor     edx, edx; pftDueTime
0x180008277  mov     rcx, rbp; pti
0x18000827a  mov     ebx, eax
0x18000827c  call    cs:__imp_SetThreadpoolTimer
0x180008282  mov     edx, 1; fCancelPendingCallbacks
0x180008287  mov     rcx, rbp; pti
0x18000828a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008290  mov     rcx, rbp; pti
0x180008293  call    cs:__imp_CloseThreadpoolTimer
0x180008299  mov     ecx, ebx; dwErrCode
0x18000829b  call    cs:__imp_SetLastError
0x1800082a1  mov     ecx, r14d; dwErrCode
0x1800082a4  mov     [rdi+38h], r15
0x1800082a8  call    cs:__imp_SetLastError
0x1800082ae  mov     rcx, [rdi+38h]; pti
0x1800082b2  test    rcx, rcx
0x1800082b5  jz      short loc_1800082D8
0x1800082b7  mov     r9d, 4E2h; msWindowLength
0x1800082bd  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800082c6  xor     r8d, r8d; msPeriod
0x1800082c9  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800082ce  call    cs:__imp_SetThreadpoolTimer
0x1800082d4  mov     byte ptr [rdi+40h], 1
0x1800082d8  test    rsi, rsi
0x1800082db  jz      short loc_1800082E6
0x1800082dd  mov     rcx, rsi; SRWLock
0x1800082e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800082e6  mov     rcx, [rsp+78h+var_40]
0x1800082eb  xor     rcx, rsp; StackCookie
0x1800082ee  call    __security_check_cookie
0x1800082f3  add     rsp, 48h
0x1800082f7  pop     r15
0x1800082f9  pop     r14
0x1800082fb  pop     rdi
0x1800082fc  pop     rsi
0x1800082fd  pop     rbp
0x1800082fe  pop     rbx
0x1800082ff  retn
```
