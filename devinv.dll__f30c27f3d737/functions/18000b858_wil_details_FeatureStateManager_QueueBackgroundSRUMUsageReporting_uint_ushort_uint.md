# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000b858`
- end: `0x18000b9f3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e570`

## callees

- `0x180006dce`
- `0x180006ec4`
- `0x18000b858`
- `0x18000ed3c`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b919`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b919`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b99a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b99a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b968`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b989`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b989`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b956`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b956`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b97b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b9cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b97b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b9cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b992`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b992`

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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
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
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000b858  push    rbx
0x18000b85a  push    rbp
0x18000b85b  push    rsi
0x18000b85c  push    rdi
0x18000b85d  push    r14
0x18000b85f  push    r15
0x18000b861  sub     rsp, 38h
0x18000b865  mov     ebp, r9d
0x18000b868  movzx   ebx, r8w
0x18000b86c  mov     r14d, edx
0x18000b86f  mov     rdi, rcx
0x18000b872  cmp     byte ptr [rcx], 0
0x18000b875  jz      loc_18000B9E6
0x18000b87b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b882  jnz     loc_18000B9E6
0x18000b888  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b88f  test    rax, rax
0x18000b892  jz      short loc_18000B8A1
0x18000b894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b899  test    al, al
0x18000b89b  jnz     loc_18000B9E6
0x18000b8a1  lea     rsi, [rdi+28h]
0x18000b8a5  mov     rcx, rsi; SRWLock
0x18000b8a8  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8ae  xor     eax, eax
0x18000b8b0  mov     word ptr [rsp+68h+var_48+6], ax
0x18000b8b5  mov     dword ptr [rsp+68h+var_48], r14d
0x18000b8ba  mov     word ptr [rsp+68h+var_48+4], bx
0x18000b8bf  lea     rbx, [rdi+0E8h]
0x18000b8c6  lea     edx, [rax+0Ch]; unsigned __int64
0x18000b8c9  mov     rcx, rbx; this
0x18000b8cc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b8d1  test    al, al
0x18000b8d3  jz      short loc_18000B92F
0x18000b8d5  mov     rcx, [rbx+8]; void *
0x18000b8d9  mov     rax, [rbx+10h]
0x18000b8dd  sub     rax, rcx
0x18000b8e0  cmp     rcx, [rbx+10h]
0x18000b8e4  sbb     r8, r8
0x18000b8e7  and     r8, rax; Size
0x18000b8ea  test    rcx, rcx
0x18000b8ed  jnz     short loc_18000B8FD
0x18000b8ef  call    cs:__imp__o__errno
0x18000b8f5  mov     dword ptr [rax], 16h
0x18000b8fb  jmp     short loc_18000B925
0x18000b8fd  cmp     r8, 0Ch
0x18000b901  jb      short loc_18000B912
0x18000b903  movsd   xmm0, [rsp+68h+var_48]
0x18000b909  movsd   qword ptr [rcx], xmm0
0x18000b90d  mov     [rcx+8], ebp
0x18000b910  jmp     short loc_18000B92A
0x18000b912  xor     edx, edx; Val
0x18000b914  call    memset_0
0x18000b919  call    cs:__imp__o__errno
0x18000b91f  mov     dword ptr [rax], 22h ; '"'
0x18000b925  call    _invalid_parameter_noinfo
0x18000b92a  add     qword ptr [rbx+8], 0Ch
0x18000b92f  cmp     byte ptr [rdi+40h], 0
0x18000b933  jnz     loc_18000B9D7
0x18000b939  cmp     qword ptr [rdi+38h], 0
0x18000b93e  jnz     short loc_18000B9AD
0x18000b940  call    cs:__imp_GetLastError
0x18000b946  mov     r14d, eax
0x18000b949  xor     r8d, r8d; pcbe
0x18000b94c  mov     rdx, rdi; pv
0x18000b94f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b956  call    cs:__imp_CreateThreadpoolTimer
0x18000b95c  mov     r15, rax
0x18000b95f  mov     rbp, [rdi+38h]
0x18000b963  test    rbp, rbp
0x18000b966  jz      short loc_18000B9A0
0x18000b968  call    cs:__imp_GetLastError
0x18000b96e  mov     ebx, eax
0x18000b970  xor     r9d, r9d; msWindowLength
0x18000b973  xor     r8d, r8d; msPeriod
0x18000b976  xor     edx, edx; pftDueTime
0x18000b978  mov     rcx, rbp; pti
0x18000b97b  call    cs:__imp_SetThreadpoolTimer
0x18000b981  mov     edx, 1; fCancelPendingCallbacks
0x18000b986  mov     rcx, rbp; pti
0x18000b989  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b98f  mov     rcx, rbp; pti
0x18000b992  call    cs:__imp_CloseThreadpoolTimer
0x18000b998  mov     ecx, ebx; dwErrCode
0x18000b99a  call    cs:__imp_SetLastError
0x18000b9a0  mov     [rdi+38h], r15
0x18000b9a4  mov     ecx, r14d; dwErrCode
0x18000b9a7  call    cs:__imp_SetLastError
0x18000b9ad  mov     rcx, [rdi+38h]; pti
0x18000b9b1  test    rcx, rcx
0x18000b9b4  jz      short loc_18000B9D7
0x18000b9b6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b9bf  mov     r9d, 4E2h; msWindowLength
0x18000b9c5  xor     r8d, r8d; msPeriod
0x18000b9c8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000b9cd  call    cs:__imp_SetThreadpoolTimer
0x18000b9d3  mov     byte ptr [rdi+40h], 1
0x18000b9d7  test    rsi, rsi
0x18000b9da  jz      short loc_18000B9E6
0x18000b9dc  mov     rcx, rsi; SRWLock
0x18000b9df  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b9e5  nop
0x18000b9e6  add     rsp, 38h
0x18000b9ea  pop     r15
0x18000b9ec  pop     r14
0x18000b9ee  pop     rdi
0x18000b9ef  pop     rsi
0x18000b9f0  pop     rbp
0x18000b9f1  pop     rbx
0x18000b9f2  retn
```
