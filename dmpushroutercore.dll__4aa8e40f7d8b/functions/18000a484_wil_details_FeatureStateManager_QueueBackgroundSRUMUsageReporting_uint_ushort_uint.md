# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a484`
- end: `0x18000a61f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ce50`

## callees

- `0x180004346`
- `0x1800043a8`
- `0x18000a484`
- `0x18000d58c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a51b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a545`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a51b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a545`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a594`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a60b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a60b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a4d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a4d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a582`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a582`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5f9`

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
0x18000a484  push    rbx
0x18000a486  push    rbp
0x18000a487  push    rsi
0x18000a488  push    rdi
0x18000a489  push    r14
0x18000a48b  push    r15
0x18000a48d  sub     rsp, 38h
0x18000a491  mov     ebp, r9d
0x18000a494  movzx   ebx, r8w
0x18000a498  mov     r14d, edx
0x18000a49b  mov     rdi, rcx
0x18000a49e  cmp     byte ptr [rcx], 0
0x18000a4a1  jz      loc_18000A612
0x18000a4a7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a4ae  jnz     loc_18000A612
0x18000a4b4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a4bb  test    rax, rax
0x18000a4be  jz      short loc_18000A4CD
0x18000a4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c5  test    al, al
0x18000a4c7  jnz     loc_18000A612
0x18000a4cd  lea     rsi, [rdi+28h]
0x18000a4d1  mov     rcx, rsi; SRWLock
0x18000a4d4  call    cs:__imp_AcquireSRWLockExclusive
0x18000a4da  xor     eax, eax
0x18000a4dc  mov     word ptr [rsp+68h+var_48+6], ax
0x18000a4e1  mov     dword ptr [rsp+68h+var_48], r14d
0x18000a4e6  mov     word ptr [rsp+68h+var_48+4], bx
0x18000a4eb  lea     rbx, [rdi+0E8h]
0x18000a4f2  lea     edx, [rax+0Ch]; unsigned __int64
0x18000a4f5  mov     rcx, rbx; this
0x18000a4f8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a4fd  test    al, al
0x18000a4ff  jz      short loc_18000A55B
0x18000a501  mov     rcx, [rbx+8]; void *
0x18000a505  mov     rax, [rbx+10h]
0x18000a509  sub     rax, rcx
0x18000a50c  cmp     rcx, [rbx+10h]
0x18000a510  sbb     r8, r8
0x18000a513  and     r8, rax; Size
0x18000a516  test    rcx, rcx
0x18000a519  jnz     short loc_18000A529
0x18000a51b  call    cs:__imp__o__errno
0x18000a521  mov     dword ptr [rax], 16h
0x18000a527  jmp     short loc_18000A551
0x18000a529  cmp     r8, 0Ch
0x18000a52d  jb      short loc_18000A53E
0x18000a52f  movsd   xmm0, [rsp+68h+var_48]
0x18000a535  movsd   qword ptr [rcx], xmm0
0x18000a539  mov     [rcx+8], ebp
0x18000a53c  jmp     short loc_18000A556
0x18000a53e  xor     edx, edx; Val
0x18000a540  call    memset_0
0x18000a545  call    cs:__imp__o__errno
0x18000a54b  mov     dword ptr [rax], 22h ; '"'
0x18000a551  call    _invalid_parameter_noinfo
0x18000a556  add     qword ptr [rbx+8], 0Ch
0x18000a55b  cmp     byte ptr [rdi+40h], 0
0x18000a55f  jnz     loc_18000A603
0x18000a565  cmp     qword ptr [rdi+38h], 0
0x18000a56a  jnz     short loc_18000A5D9
0x18000a56c  call    cs:__imp_GetLastError
0x18000a572  mov     r14d, eax
0x18000a575  xor     r8d, r8d; pcbe
0x18000a578  mov     rdx, rdi; pv
0x18000a57b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a582  call    cs:__imp_CreateThreadpoolTimer
0x18000a588  mov     r15, rax
0x18000a58b  mov     rbp, [rdi+38h]
0x18000a58f  test    rbp, rbp
0x18000a592  jz      short loc_18000A5CC
0x18000a594  call    cs:__imp_GetLastError
0x18000a59a  mov     ebx, eax
0x18000a59c  xor     r9d, r9d; msWindowLength
0x18000a59f  xor     r8d, r8d; msPeriod
0x18000a5a2  xor     edx, edx; pftDueTime
0x18000a5a4  mov     rcx, rbp; pti
0x18000a5a7  call    cs:__imp_SetThreadpoolTimer
0x18000a5ad  mov     edx, 1; fCancelPendingCallbacks
0x18000a5b2  mov     rcx, rbp; pti
0x18000a5b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a5bb  mov     rcx, rbp; pti
0x18000a5be  call    cs:__imp_CloseThreadpoolTimer
0x18000a5c4  mov     ecx, ebx; dwErrCode
0x18000a5c6  call    cs:__imp_SetLastError
0x18000a5cc  mov     [rdi+38h], r15
0x18000a5d0  mov     ecx, r14d; dwErrCode
0x18000a5d3  call    cs:__imp_SetLastError
0x18000a5d9  mov     rcx, [rdi+38h]; pti
0x18000a5dd  test    rcx, rcx
0x18000a5e0  jz      short loc_18000A603
0x18000a5e2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a5eb  mov     r9d, 4E2h; msWindowLength
0x18000a5f1  xor     r8d, r8d; msPeriod
0x18000a5f4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000a5f9  call    cs:__imp_SetThreadpoolTimer
0x18000a5ff  mov     byte ptr [rdi+40h], 1
0x18000a603  test    rsi, rsi
0x18000a606  jz      short loc_18000A612
0x18000a608  mov     rcx, rsi; SRWLock
0x18000a60b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a611  nop
0x18000a612  add     rsp, 38h
0x18000a616  pop     r15
0x18000a618  pop     r14
0x18000a61a  pop     rdi
0x18000a61b  pop     rsi
0x18000a61c  pop     rbp
0x18000a61d  pop     rbx
0x18000a61e  retn
```
