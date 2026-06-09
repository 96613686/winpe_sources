# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006980`
- end: `0x180006b1b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009510`

## callees

- `0x18000288a`
- `0x1800028dc`
- `0x180006980`
- `0x180009ba0`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a17`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a17`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800069d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800069d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ac2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006acf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ac2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a90`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006aa3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006af5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006aa3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006af5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006aba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006aba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ab1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ab1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006a7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006a7e`

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
0x180006980  push    rbx
0x180006982  push    rbp
0x180006983  push    rsi
0x180006984  push    rdi
0x180006985  push    r14
0x180006987  push    r15
0x180006989  sub     rsp, 38h
0x18000698d  mov     ebp, r9d
0x180006990  movzx   ebx, r8w
0x180006994  mov     r14d, edx
0x180006997  mov     rdi, rcx
0x18000699a  cmp     byte ptr [rcx], 0
0x18000699d  jz      loc_180006B0E
0x1800069a3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800069aa  jnz     loc_180006B0E
0x1800069b0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800069b7  test    rax, rax
0x1800069ba  jz      short loc_1800069C9
0x1800069bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c1  test    al, al
0x1800069c3  jnz     loc_180006B0E
0x1800069c9  lea     rsi, [rdi+28h]
0x1800069cd  mov     rcx, rsi; SRWLock
0x1800069d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800069d6  xor     eax, eax
0x1800069d8  mov     word ptr [rsp+68h+var_48+6], ax
0x1800069dd  mov     dword ptr [rsp+68h+var_48], r14d
0x1800069e2  mov     word ptr [rsp+68h+var_48+4], bx
0x1800069e7  lea     rbx, [rdi+0E8h]
0x1800069ee  lea     edx, [rax+0Ch]; unsigned __int64
0x1800069f1  mov     rcx, rbx; this
0x1800069f4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800069f9  test    al, al
0x1800069fb  jz      short loc_180006A57
0x1800069fd  mov     rcx, [rbx+8]; void *
0x180006a01  mov     rax, [rbx+10h]
0x180006a05  sub     rax, rcx
0x180006a08  cmp     rcx, [rbx+10h]
0x180006a0c  sbb     r8, r8
0x180006a0f  and     r8, rax; Size
0x180006a12  test    rcx, rcx
0x180006a15  jnz     short loc_180006A25
0x180006a17  call    cs:__imp__o__errno
0x180006a1d  mov     dword ptr [rax], 16h
0x180006a23  jmp     short loc_180006A4D
0x180006a25  cmp     r8, 0Ch
0x180006a29  jb      short loc_180006A3A
0x180006a2b  movsd   xmm0, [rsp+68h+var_48]
0x180006a31  movsd   qword ptr [rcx], xmm0
0x180006a35  mov     [rcx+8], ebp
0x180006a38  jmp     short loc_180006A52
0x180006a3a  xor     edx, edx; Val
0x180006a3c  call    memset_0
0x180006a41  call    cs:__imp__o__errno
0x180006a47  mov     dword ptr [rax], 22h ; '"'
0x180006a4d  call    _invalid_parameter_noinfo
0x180006a52  add     qword ptr [rbx+8], 0Ch
0x180006a57  cmp     byte ptr [rdi+40h], 0
0x180006a5b  jnz     loc_180006AFF
0x180006a61  cmp     qword ptr [rdi+38h], 0
0x180006a66  jnz     short loc_180006AD5
0x180006a68  call    cs:__imp_GetLastError
0x180006a6e  mov     r14d, eax
0x180006a71  xor     r8d, r8d; pcbe
0x180006a74  mov     rdx, rdi; pv
0x180006a77  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006a7e  call    cs:__imp_CreateThreadpoolTimer
0x180006a84  mov     r15, rax
0x180006a87  mov     rbp, [rdi+38h]
0x180006a8b  test    rbp, rbp
0x180006a8e  jz      short loc_180006AC8
0x180006a90  call    cs:__imp_GetLastError
0x180006a96  mov     ebx, eax
0x180006a98  xor     r9d, r9d; msWindowLength
0x180006a9b  xor     r8d, r8d; msPeriod
0x180006a9e  xor     edx, edx; pftDueTime
0x180006aa0  mov     rcx, rbp; pti
0x180006aa3  call    cs:__imp_SetThreadpoolTimer
0x180006aa9  mov     edx, 1; fCancelPendingCallbacks
0x180006aae  mov     rcx, rbp; pti
0x180006ab1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006ab7  mov     rcx, rbp; pti
0x180006aba  call    cs:__imp_CloseThreadpoolTimer
0x180006ac0  mov     ecx, ebx; dwErrCode
0x180006ac2  call    cs:__imp_SetLastError
0x180006ac8  mov     [rdi+38h], r15
0x180006acc  mov     ecx, r14d; dwErrCode
0x180006acf  call    cs:__imp_SetLastError
0x180006ad5  mov     rcx, [rdi+38h]; pti
0x180006ad9  test    rcx, rcx
0x180006adc  jz      short loc_180006AFF
0x180006ade  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006ae7  mov     r9d, 4E2h; msWindowLength
0x180006aed  xor     r8d, r8d; msPeriod
0x180006af0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180006af5  call    cs:__imp_SetThreadpoolTimer
0x180006afb  mov     byte ptr [rdi+40h], 1
0x180006aff  test    rsi, rsi
0x180006b02  jz      short loc_180006B0E
0x180006b04  mov     rcx, rsi; SRWLock
0x180006b07  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b0d  nop
0x180006b0e  add     rsp, 38h
0x180006b12  pop     r15
0x180006b14  pop     r14
0x180006b16  pop     rdi
0x180006b17  pop     rsi
0x180006b18  pop     rbp
0x180006b19  pop     rbx
0x180006b1a  retn
```
