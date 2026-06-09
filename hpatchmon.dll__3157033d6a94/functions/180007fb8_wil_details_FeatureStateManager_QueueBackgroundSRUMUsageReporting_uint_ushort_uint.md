# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007fb8`
- end: `0x180008153`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c040`

## callees

- `0x180002b62`
- `0x180002be8`
- `0x180007fb8`
- `0x18000c80c`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000804f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008079`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000804f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008008`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008008`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000813f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000813f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800080b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800080b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800080db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000812d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800080db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000812d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800080f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800080f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800080e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800080e9`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
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
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
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
0x180007fb8  push    rbx
0x180007fba  push    rbp
0x180007fbb  push    rsi
0x180007fbc  push    rdi
0x180007fbd  push    r14
0x180007fbf  push    r15
0x180007fc1  sub     rsp, 38h
0x180007fc5  mov     ebp, r9d
0x180007fc8  movzx   ebx, r8w
0x180007fcc  mov     r14d, edx
0x180007fcf  mov     rdi, rcx
0x180007fd2  cmp     byte ptr [rcx], 0
0x180007fd5  jz      loc_180008146
0x180007fdb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007fe2  jnz     loc_180008146
0x180007fe8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007fef  test    rax, rax
0x180007ff2  jz      short loc_180008001
0x180007ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff9  test    al, al
0x180007ffb  jnz     loc_180008146
0x180008001  lea     rsi, [rdi+28h]
0x180008005  mov     rcx, rsi; SRWLock
0x180008008  call    cs:__imp_AcquireSRWLockExclusive
0x18000800e  xor     eax, eax
0x180008010  mov     word ptr [rsp+68h+var_48+6], ax
0x180008015  mov     dword ptr [rsp+68h+var_48], r14d
0x18000801a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000801f  lea     rbx, [rdi+0E8h]
0x180008026  lea     edx, [rax+0Ch]; unsigned __int64
0x180008029  mov     rcx, rbx; this
0x18000802c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008031  test    al, al
0x180008033  jz      short loc_18000808F
0x180008035  mov     rcx, [rbx+8]; void *
0x180008039  mov     rax, [rbx+10h]
0x18000803d  sub     rax, rcx
0x180008040  cmp     rcx, [rbx+10h]
0x180008044  sbb     r8, r8
0x180008047  and     r8, rax; Size
0x18000804a  test    rcx, rcx
0x18000804d  jnz     short loc_18000805D
0x18000804f  call    cs:__imp__o__errno
0x180008055  mov     dword ptr [rax], 16h
0x18000805b  jmp     short loc_180008085
0x18000805d  cmp     r8, 0Ch
0x180008061  jb      short loc_180008072
0x180008063  movsd   xmm0, [rsp+68h+var_48]
0x180008069  movsd   qword ptr [rcx], xmm0
0x18000806d  mov     [rcx+8], ebp
0x180008070  jmp     short loc_18000808A
0x180008072  xor     edx, edx; Val
0x180008074  call    memset_0
0x180008079  call    cs:__imp__o__errno
0x18000807f  mov     dword ptr [rax], 22h ; '"'
0x180008085  call    _invalid_parameter_noinfo
0x18000808a  add     qword ptr [rbx+8], 0Ch
0x18000808f  cmp     byte ptr [rdi+40h], 0
0x180008093  jnz     loc_180008137
0x180008099  cmp     qword ptr [rdi+38h], 0
0x18000809e  jnz     short loc_18000810D
0x1800080a0  call    cs:__imp_GetLastError
0x1800080a6  mov     r14d, eax
0x1800080a9  xor     r8d, r8d; pcbe
0x1800080ac  mov     rdx, rdi; pv
0x1800080af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800080b6  call    cs:__imp_CreateThreadpoolTimer
0x1800080bc  mov     r15, rax
0x1800080bf  mov     rbp, [rdi+38h]
0x1800080c3  test    rbp, rbp
0x1800080c6  jz      short loc_180008100
0x1800080c8  call    cs:__imp_GetLastError
0x1800080ce  mov     ebx, eax
0x1800080d0  xor     r9d, r9d; msWindowLength
0x1800080d3  xor     r8d, r8d; msPeriod
0x1800080d6  xor     edx, edx; pftDueTime
0x1800080d8  mov     rcx, rbp; pti
0x1800080db  call    cs:__imp_SetThreadpoolTimer
0x1800080e1  mov     edx, 1; fCancelPendingCallbacks
0x1800080e6  mov     rcx, rbp; pti
0x1800080e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800080ef  mov     rcx, rbp; pti
0x1800080f2  call    cs:__imp_CloseThreadpoolTimer
0x1800080f8  mov     ecx, ebx; dwErrCode
0x1800080fa  call    cs:__imp_SetLastError
0x180008100  mov     [rdi+38h], r15
0x180008104  mov     ecx, r14d; dwErrCode
0x180008107  call    cs:__imp_SetLastError
0x18000810d  mov     rcx, [rdi+38h]; pti
0x180008111  test    rcx, rcx
0x180008114  jz      short loc_180008137
0x180008116  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000811f  mov     r9d, 4E2h; msWindowLength
0x180008125  xor     r8d, r8d; msPeriod
0x180008128  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000812d  call    cs:__imp_SetThreadpoolTimer
0x180008133  mov     byte ptr [rdi+40h], 1
0x180008137  test    rsi, rsi
0x18000813a  jz      short loc_180008146
0x18000813c  mov     rcx, rsi; SRWLock
0x18000813f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008145  nop
0x180008146  add     rsp, 38h
0x18000814a  pop     r15
0x18000814c  pop     r14
0x18000814e  pop     rdi
0x18000814f  pop     rsi
0x180008150  pop     rbp
0x180008151  pop     rbx
0x180008152  retn
```
