# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180017b94`
- end: `0x180017d2e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c9a0`

## callees

- `0x180002c36`
- `0x180002cbc`
- `0x180017b94`
- `0x18001cf8c`
- `0x180020010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c2b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c2b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017be4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017be4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017d1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ce3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017cd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017ce3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017cc5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017cc5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017cce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017cce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017c92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017c92`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017cb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017d09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017cb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017d09`

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
0x180017b94  push    rbx
0x180017b96  push    rbp
0x180017b97  push    rsi
0x180017b98  push    rdi
0x180017b99  push    r14
0x180017b9b  push    r15
0x180017b9d  sub     rsp, 38h
0x180017ba1  mov     ebp, r9d
0x180017ba4  movzx   ebx, r8w
0x180017ba8  mov     r14d, edx
0x180017bab  mov     rdi, rcx
0x180017bae  cmp     byte ptr [rcx], 0
0x180017bb1  jz      loc_180017D21
0x180017bb7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180017bbe  jnz     loc_180017D21
0x180017bc4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180017bcb  test    rax, rax
0x180017bce  jz      short loc_180017BDD
0x180017bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bd5  test    al, al
0x180017bd7  jnz     loc_180017D21
0x180017bdd  lea     rsi, [rdi+28h]
0x180017be1  mov     rcx, rsi; SRWLock
0x180017be4  call    cs:__imp_AcquireSRWLockExclusive
0x180017bea  xor     eax, eax
0x180017bec  mov     word ptr [rsp+68h+var_48+6], ax
0x180017bf1  mov     dword ptr [rsp+68h+var_48], r14d
0x180017bf6  mov     word ptr [rsp+68h+var_48+4], bx
0x180017bfb  lea     rbx, [rdi+0E8h]
0x180017c02  lea     edx, [rax+0Ch]; unsigned __int64
0x180017c05  mov     rcx, rbx; this
0x180017c08  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180017c0d  test    al, al
0x180017c0f  jz      short loc_180017C6B
0x180017c11  mov     rcx, [rbx+8]; void *
0x180017c15  mov     rax, [rbx+10h]
0x180017c19  sub     rax, rcx
0x180017c1c  cmp     rcx, [rbx+10h]
0x180017c20  sbb     r8, r8
0x180017c23  and     r8, rax; Size
0x180017c26  test    rcx, rcx
0x180017c29  jnz     short loc_180017C39
0x180017c2b  call    cs:__imp__o__errno
0x180017c31  mov     dword ptr [rax], 16h
0x180017c37  jmp     short loc_180017C61
0x180017c39  cmp     r8, 0Ch
0x180017c3d  jb      short loc_180017C4E
0x180017c3f  movsd   xmm0, [rsp+68h+var_48]
0x180017c45  movsd   qword ptr [rcx], xmm0
0x180017c49  mov     [rcx+8], ebp
0x180017c4c  jmp     short loc_180017C66
0x180017c4e  xor     edx, edx; Val
0x180017c50  call    memset_0
0x180017c55  call    cs:__imp__o__errno
0x180017c5b  mov     dword ptr [rax], 22h ; '"'
0x180017c61  call    _invalid_parameter_noinfo
0x180017c66  add     qword ptr [rbx+8], 0Ch
0x180017c6b  cmp     byte ptr [rdi+40h], 0
0x180017c6f  jnz     loc_180017D13
0x180017c75  cmp     qword ptr [rdi+38h], 0
0x180017c7a  jnz     short loc_180017CE9
0x180017c7c  call    cs:__imp_GetLastError
0x180017c82  mov     r14d, eax
0x180017c85  xor     r8d, r8d; pcbe
0x180017c88  mov     rdx, rdi; pv
0x180017c8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017c92  call    cs:__imp_CreateThreadpoolTimer
0x180017c98  mov     r15, rax
0x180017c9b  mov     rbp, [rdi+38h]
0x180017c9f  test    rbp, rbp
0x180017ca2  jz      short loc_180017CDC
0x180017ca4  call    cs:__imp_GetLastError
0x180017caa  mov     ebx, eax
0x180017cac  xor     r9d, r9d; msWindowLength
0x180017caf  xor     r8d, r8d; msPeriod
0x180017cb2  xor     edx, edx; pftDueTime
0x180017cb4  mov     rcx, rbp; pti
0x180017cb7  call    cs:__imp_SetThreadpoolTimer
0x180017cbd  mov     edx, 1; fCancelPendingCallbacks
0x180017cc2  mov     rcx, rbp; pti
0x180017cc5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017ccb  mov     rcx, rbp; pti
0x180017cce  call    cs:__imp_CloseThreadpoolTimer
0x180017cd4  mov     ecx, ebx; dwErrCode
0x180017cd6  call    cs:__imp_SetLastError
0x180017cdc  mov     [rdi+38h], r15
0x180017ce0  mov     ecx, r14d; dwErrCode
0x180017ce3  call    cs:__imp_SetLastError
0x180017ce9  mov     rcx, [rdi+38h]; pti
0x180017ced  test    rcx, rcx
0x180017cf0  jz      short loc_180017D13
0x180017cf2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180017cfb  mov     r9d, 4E2h; msWindowLength
0x180017d01  xor     r8d, r8d; msPeriod
0x180017d04  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180017d09  call    cs:__imp_SetThreadpoolTimer
0x180017d0f  mov     byte ptr [rdi+40h], 1
0x180017d13  test    rsi, rsi
0x180017d16  jz      short loc_180017D21
0x180017d18  mov     rcx, rsi; SRWLock
0x180017d1b  call    cs:__imp_ReleaseSRWLockExclusive
0x180017d21  add     rsp, 38h
0x180017d25  pop     r15
0x180017d27  pop     r14
0x180017d29  pop     rdi
0x180017d2a  pop     rsi
0x180017d2b  pop     rbp
0x180017d2c  pop     rbx
0x180017d2d  retn
```
