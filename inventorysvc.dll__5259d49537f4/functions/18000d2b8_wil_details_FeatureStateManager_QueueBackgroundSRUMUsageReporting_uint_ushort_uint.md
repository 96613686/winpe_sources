# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000d2b8`
- end: `0x18000d453`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800102c0`

## callees

- `0x1800037d2`
- `0x1800038b8`
- `0x18000d2b8`
- `0x18001125c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d34f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d379`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d34f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d379`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d308`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d308`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d43f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d43f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d42d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d3db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d42d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d3b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d3b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d3f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d3e9`

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
0x18000d2b8  push    rbx
0x18000d2ba  push    rbp
0x18000d2bb  push    rsi
0x18000d2bc  push    rdi
0x18000d2bd  push    r14
0x18000d2bf  push    r15
0x18000d2c1  sub     rsp, 38h
0x18000d2c5  mov     ebp, r9d
0x18000d2c8  movzx   ebx, r8w
0x18000d2cc  mov     r14d, edx
0x18000d2cf  mov     rdi, rcx
0x18000d2d2  cmp     byte ptr [rcx], 0
0x18000d2d5  jz      loc_18000D446
0x18000d2db  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d2e2  jnz     loc_18000D446
0x18000d2e8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d2ef  test    rax, rax
0x18000d2f2  jz      short loc_18000D301
0x18000d2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f9  test    al, al
0x18000d2fb  jnz     loc_18000D446
0x18000d301  lea     rsi, [rdi+28h]
0x18000d305  mov     rcx, rsi; SRWLock
0x18000d308  call    cs:__imp_AcquireSRWLockExclusive
0x18000d30e  xor     eax, eax
0x18000d310  mov     word ptr [rsp+68h+var_48+6], ax
0x18000d315  mov     dword ptr [rsp+68h+var_48], r14d
0x18000d31a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000d31f  lea     rbx, [rdi+0E8h]
0x18000d326  lea     edx, [rax+0Ch]; unsigned __int64
0x18000d329  mov     rcx, rbx; this
0x18000d32c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d331  test    al, al
0x18000d333  jz      short loc_18000D38F
0x18000d335  mov     rcx, [rbx+8]; void *
0x18000d339  mov     rax, [rbx+10h]
0x18000d33d  sub     rax, rcx
0x18000d340  cmp     rcx, [rbx+10h]
0x18000d344  sbb     r8, r8
0x18000d347  and     r8, rax; Size
0x18000d34a  test    rcx, rcx
0x18000d34d  jnz     short loc_18000D35D
0x18000d34f  call    cs:__imp__o__errno
0x18000d355  mov     dword ptr [rax], 16h
0x18000d35b  jmp     short loc_18000D385
0x18000d35d  cmp     r8, 0Ch
0x18000d361  jb      short loc_18000D372
0x18000d363  movsd   xmm0, [rsp+68h+var_48]
0x18000d369  movsd   qword ptr [rcx], xmm0
0x18000d36d  mov     [rcx+8], ebp
0x18000d370  jmp     short loc_18000D38A
0x18000d372  xor     edx, edx; Val
0x18000d374  call    memset_0
0x18000d379  call    cs:__imp__o__errno
0x18000d37f  mov     dword ptr [rax], 22h ; '"'
0x18000d385  call    _invalid_parameter_noinfo
0x18000d38a  add     qword ptr [rbx+8], 0Ch
0x18000d38f  cmp     byte ptr [rdi+40h], 0
0x18000d393  jnz     loc_18000D437
0x18000d399  cmp     qword ptr [rdi+38h], 0
0x18000d39e  jnz     short loc_18000D40D
0x18000d3a0  call    cs:__imp_GetLastError
0x18000d3a6  mov     r14d, eax
0x18000d3a9  xor     r8d, r8d; pcbe
0x18000d3ac  mov     rdx, rdi; pv
0x18000d3af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d3b6  call    cs:__imp_CreateThreadpoolTimer
0x18000d3bc  mov     r15, rax
0x18000d3bf  mov     rbp, [rdi+38h]
0x18000d3c3  test    rbp, rbp
0x18000d3c6  jz      short loc_18000D400
0x18000d3c8  call    cs:__imp_GetLastError
0x18000d3ce  mov     ebx, eax
0x18000d3d0  xor     r9d, r9d; msWindowLength
0x18000d3d3  xor     r8d, r8d; msPeriod
0x18000d3d6  xor     edx, edx; pftDueTime
0x18000d3d8  mov     rcx, rbp; pti
0x18000d3db  call    cs:__imp_SetThreadpoolTimer
0x18000d3e1  mov     edx, 1; fCancelPendingCallbacks
0x18000d3e6  mov     rcx, rbp; pti
0x18000d3e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d3ef  mov     rcx, rbp; pti
0x18000d3f2  call    cs:__imp_CloseThreadpoolTimer
0x18000d3f8  mov     ecx, ebx; dwErrCode
0x18000d3fa  call    cs:__imp_SetLastError
0x18000d400  mov     [rdi+38h], r15
0x18000d404  mov     ecx, r14d; dwErrCode
0x18000d407  call    cs:__imp_SetLastError
0x18000d40d  mov     rcx, [rdi+38h]; pti
0x18000d411  test    rcx, rcx
0x18000d414  jz      short loc_18000D437
0x18000d416  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000d41f  mov     r9d, 4E2h; msWindowLength
0x18000d425  xor     r8d, r8d; msPeriod
0x18000d428  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000d42d  call    cs:__imp_SetThreadpoolTimer
0x18000d433  mov     byte ptr [rdi+40h], 1
0x18000d437  test    rsi, rsi
0x18000d43a  jz      short loc_18000D446
0x18000d43c  mov     rcx, rsi; SRWLock
0x18000d43f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d445  nop
0x18000d446  add     rsp, 38h
0x18000d44a  pop     r15
0x18000d44c  pop     r14
0x18000d44e  pop     rdi
0x18000d44f  pop     rsi
0x18000d450  pop     rbp
0x18000d451  pop     rbx
0x18000d452  retn
```
