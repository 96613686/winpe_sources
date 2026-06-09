# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007508`
- end: `0x1800076a3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009e80`

## callees

- `0x1800032b2`
- `0x180003320`
- `0x180007508`
- `0x18000a54c`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000759f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000759f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007558`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007558`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000768f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000768f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007618`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000762b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000767d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000762b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000767d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007642`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007642`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007639`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007639`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007606`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007606`

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
0x180007508  push    rbx
0x18000750a  push    rbp
0x18000750b  push    rsi
0x18000750c  push    rdi
0x18000750d  push    r14
0x18000750f  push    r15
0x180007511  sub     rsp, 38h
0x180007515  mov     ebp, r9d
0x180007518  movzx   ebx, r8w
0x18000751c  mov     r14d, edx
0x18000751f  mov     rdi, rcx
0x180007522  cmp     byte ptr [rcx], 0
0x180007525  jz      loc_180007696
0x18000752b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007532  jnz     loc_180007696
0x180007538  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000753f  test    rax, rax
0x180007542  jz      short loc_180007551
0x180007544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007549  test    al, al
0x18000754b  jnz     loc_180007696
0x180007551  lea     rsi, [rdi+28h]
0x180007555  mov     rcx, rsi; SRWLock
0x180007558  call    cs:__imp_AcquireSRWLockExclusive
0x18000755e  xor     eax, eax
0x180007560  mov     word ptr [rsp+68h+var_48+6], ax
0x180007565  mov     dword ptr [rsp+68h+var_48], r14d
0x18000756a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000756f  lea     rbx, [rdi+0E8h]
0x180007576  lea     edx, [rax+0Ch]; unsigned __int64
0x180007579  mov     rcx, rbx; this
0x18000757c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007581  test    al, al
0x180007583  jz      short loc_1800075DF
0x180007585  mov     rcx, [rbx+8]; void *
0x180007589  mov     rax, [rbx+10h]
0x18000758d  sub     rax, rcx
0x180007590  cmp     rcx, [rbx+10h]
0x180007594  sbb     r8, r8
0x180007597  and     r8, rax; Size
0x18000759a  test    rcx, rcx
0x18000759d  jnz     short loc_1800075AD
0x18000759f  call    cs:__imp__o__errno
0x1800075a5  mov     dword ptr [rax], 16h
0x1800075ab  jmp     short loc_1800075D5
0x1800075ad  cmp     r8, 0Ch
0x1800075b1  jb      short loc_1800075C2
0x1800075b3  movsd   xmm0, [rsp+68h+var_48]
0x1800075b9  movsd   qword ptr [rcx], xmm0
0x1800075bd  mov     [rcx+8], ebp
0x1800075c0  jmp     short loc_1800075DA
0x1800075c2  xor     edx, edx; Val
0x1800075c4  call    memset_0
0x1800075c9  call    cs:__imp__o__errno
0x1800075cf  mov     dword ptr [rax], 22h ; '"'
0x1800075d5  call    _invalid_parameter_noinfo
0x1800075da  add     qword ptr [rbx+8], 0Ch
0x1800075df  cmp     byte ptr [rdi+40h], 0
0x1800075e3  jnz     loc_180007687
0x1800075e9  cmp     qword ptr [rdi+38h], 0
0x1800075ee  jnz     short loc_18000765D
0x1800075f0  call    cs:__imp_GetLastError
0x1800075f6  mov     r14d, eax
0x1800075f9  xor     r8d, r8d; pcbe
0x1800075fc  mov     rdx, rdi; pv
0x1800075ff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007606  call    cs:__imp_CreateThreadpoolTimer
0x18000760c  mov     r15, rax
0x18000760f  mov     rbp, [rdi+38h]
0x180007613  test    rbp, rbp
0x180007616  jz      short loc_180007650
0x180007618  call    cs:__imp_GetLastError
0x18000761e  mov     ebx, eax
0x180007620  xor     r9d, r9d; msWindowLength
0x180007623  xor     r8d, r8d; msPeriod
0x180007626  xor     edx, edx; pftDueTime
0x180007628  mov     rcx, rbp; pti
0x18000762b  call    cs:__imp_SetThreadpoolTimer
0x180007631  mov     edx, 1; fCancelPendingCallbacks
0x180007636  mov     rcx, rbp; pti
0x180007639  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000763f  mov     rcx, rbp; pti
0x180007642  call    cs:__imp_CloseThreadpoolTimer
0x180007648  mov     ecx, ebx; dwErrCode
0x18000764a  call    cs:__imp_SetLastError
0x180007650  mov     [rdi+38h], r15
0x180007654  mov     ecx, r14d; dwErrCode
0x180007657  call    cs:__imp_SetLastError
0x18000765d  mov     rcx, [rdi+38h]; pti
0x180007661  test    rcx, rcx
0x180007664  jz      short loc_180007687
0x180007666  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000766f  mov     r9d, 4E2h; msWindowLength
0x180007675  xor     r8d, r8d; msPeriod
0x180007678  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000767d  call    cs:__imp_SetThreadpoolTimer
0x180007683  mov     byte ptr [rdi+40h], 1
0x180007687  test    rsi, rsi
0x18000768a  jz      short loc_180007696
0x18000768c  mov     rcx, rsi; SRWLock
0x18000768f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007695  nop
0x180007696  add     rsp, 38h
0x18000769a  pop     r15
0x18000769c  pop     r14
0x18000769e  pop     rdi
0x18000769f  pop     rsi
0x1800076a0  pop     rbp
0x1800076a1  pop     rbx
0x1800076a2  retn
```
