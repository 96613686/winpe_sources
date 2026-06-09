# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002289c`
- end: `0x180022a25`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024470`

## callees

- `0x18002289c`
- `0x180024b74`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002294a`
- `msvcrt!memcpy_s` at `0x18002294a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002298d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002298d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002297b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002297b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800229f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800229ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800229ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800229b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800229b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
0x18002289c  push    rbx
0x18002289e  push    rbp
0x18002289f  push    rsi
0x1800228a0  push    rdi
0x1800228a1  push    r14
0x1800228a3  push    r15
0x1800228a5  sub     rsp, 48h
0x1800228a9  mov     rax, cs:__security_cookie
0x1800228b0  xor     rax, rsp
0x1800228b3  mov     [rsp+78h+var_40], rax
0x1800228b8  mov     r14d, r9d
0x1800228bb  movzx   ebp, r8w
0x1800228bf  mov     ebx, edx
0x1800228c1  mov     rdi, rcx
0x1800228c4  cmp     byte ptr [rcx], 0
0x1800228c7  jz      loc_180022A0B
0x1800228cd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800228d4  jnz     loc_180022A0B
0x1800228da  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800228e1  test    rax, rax
0x1800228e4  jz      short loc_1800228F3
0x1800228e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228eb  test    al, al
0x1800228ed  jnz     loc_180022A0B
0x1800228f3  lea     rsi, [rdi+28h]
0x1800228f7  mov     rcx, rsi; SRWLock
0x1800228fa  call    cs:__imp_AcquireSRWLockExclusive
0x180022900  xor     eax, eax
0x180022902  mov     [rsp+78h+var_4A], ax
0x180022907  mov     [rsp+78h+Source], ebx
0x18002290b  mov     [rsp+78h+var_4C], bp
0x180022910  mov     [rsp+78h+var_48], r14d
0x180022915  lea     rbx, [rdi+0E8h]
0x18002291c  lea     ebp, [rax+0Ch]
0x18002291f  mov     edx, ebp; unsigned __int64
0x180022921  mov     rcx, rbx; this
0x180022924  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180022929  test    al, al
0x18002292b  jz      short loc_180022954
0x18002292d  mov     rcx, [rbx+8]; Destination
0x180022931  mov     rax, [rbx+10h]
0x180022935  sub     rax, rcx
0x180022938  cmp     rcx, [rbx+10h]
0x18002293c  sbb     rdx, rdx
0x18002293f  and     rdx, rax; DestinationSize
0x180022942  mov     r9d, ebp; SourceSize
0x180022945  lea     r8, [rsp+78h+Source]; Source
0x18002294a  call    cs:__imp_memcpy_s
0x180022950  add     [rbx+8], rbp
0x180022954  cmp     byte ptr [rdi+40h], 0
0x180022958  jnz     loc_1800229FC
0x18002295e  cmp     qword ptr [rdi+38h], 0
0x180022963  jnz     short loc_1800229D2
0x180022965  call    cs:__imp_GetLastError
0x18002296b  mov     r14d, eax
0x18002296e  xor     r8d, r8d; pcbe
0x180022971  mov     rdx, rdi; pv
0x180022974  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002297b  call    cs:__imp_CreateThreadpoolTimer
0x180022981  mov     r15, rax
0x180022984  mov     rbp, [rdi+38h]
0x180022988  test    rbp, rbp
0x18002298b  jz      short loc_1800229C5
0x18002298d  call    cs:__imp_GetLastError
0x180022993  mov     ebx, eax
0x180022995  xor     r9d, r9d; msWindowLength
0x180022998  xor     r8d, r8d; msPeriod
0x18002299b  xor     edx, edx; pftDueTime
0x18002299d  mov     rcx, rbp; pti
0x1800229a0  call    cs:__imp_SetThreadpoolTimer
0x1800229a6  mov     edx, 1; fCancelPendingCallbacks
0x1800229ab  mov     rcx, rbp; pti
0x1800229ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800229b4  mov     rcx, rbp; pti
0x1800229b7  call    cs:__imp_CloseThreadpoolTimer
0x1800229bd  mov     ecx, ebx; dwErrCode
0x1800229bf  call    cs:__imp_SetLastError
0x1800229c5  mov     [rdi+38h], r15
0x1800229c9  mov     ecx, r14d; dwErrCode
0x1800229cc  call    cs:__imp_SetLastError
0x1800229d2  mov     rcx, [rdi+38h]; pti
0x1800229d6  test    rcx, rcx
0x1800229d9  jz      short loc_1800229FC
0x1800229db  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800229e4  mov     r9d, 4E2h; msWindowLength
0x1800229ea  xor     r8d, r8d; msPeriod
0x1800229ed  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800229f2  call    cs:__imp_SetThreadpoolTimer
0x1800229f8  mov     byte ptr [rdi+40h], 1
0x1800229fc  test    rsi, rsi
0x1800229ff  jz      short loc_180022A0B
0x180022a01  mov     rcx, rsi; SRWLock
0x180022a04  call    cs:__imp_ReleaseSRWLockExclusive
0x180022a0a  nop
0x180022a0b  mov     rcx, [rsp+78h+var_40]
0x180022a10  xor     rcx, rsp; StackCookie
0x180022a13  call    __security_check_cookie
0x180022a18  add     rsp, 48h
0x180022a1c  pop     r15
0x180022a1e  pop     r14
0x180022a20  pop     rdi
0x180022a21  pop     rsi
0x180022a22  pop     rbp
0x180022a23  pop     rbx
0x180022a24  retn
```
