# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180073204`
- end: `0x18007339f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180076450`

## callees

- `0x18005ff2a`
- `0x18005ffc4`
- `0x180073204`
- `0x180077a8c`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007329b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800732c5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007329b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800732c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007338b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007338b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073254`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073353`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073314`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007333e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007333e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180073335`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180073335`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073327`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073379`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073327`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073379`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073302`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073302`

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
0x180073204  push    rbx
0x180073206  push    rbp
0x180073207  push    rsi
0x180073208  push    rdi
0x180073209  push    r14
0x18007320b  push    r15
0x18007320d  sub     rsp, 38h
0x180073211  mov     ebp, r9d
0x180073214  movzx   ebx, r8w
0x180073218  mov     r14d, edx
0x18007321b  mov     rdi, rcx
0x18007321e  cmp     byte ptr [rcx], 0
0x180073221  jz      loc_180073392
0x180073227  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007322e  jnz     loc_180073392
0x180073234  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007323b  test    rax, rax
0x18007323e  jz      short loc_18007324D
0x180073240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073245  test    al, al
0x180073247  jnz     loc_180073392
0x18007324d  lea     rsi, [rdi+28h]
0x180073251  mov     rcx, rsi; SRWLock
0x180073254  call    cs:__imp_AcquireSRWLockExclusive
0x18007325a  xor     eax, eax
0x18007325c  mov     word ptr [rsp+68h+var_48+6], ax
0x180073261  mov     dword ptr [rsp+68h+var_48], r14d
0x180073266  mov     word ptr [rsp+68h+var_48+4], bx
0x18007326b  lea     rbx, [rdi+0E8h]
0x180073272  lea     edx, [rax+0Ch]; unsigned __int64
0x180073275  mov     rcx, rbx; this
0x180073278  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18007327d  test    al, al
0x18007327f  jz      short loc_1800732DB
0x180073281  mov     rcx, [rbx+8]; void *
0x180073285  mov     rax, [rbx+10h]
0x180073289  sub     rax, rcx
0x18007328c  cmp     rcx, [rbx+10h]
0x180073290  sbb     r8, r8
0x180073293  and     r8, rax; Size
0x180073296  test    rcx, rcx
0x180073299  jnz     short loc_1800732A9
0x18007329b  call    cs:__imp__o__errno
0x1800732a1  mov     dword ptr [rax], 16h
0x1800732a7  jmp     short loc_1800732D1
0x1800732a9  cmp     r8, 0Ch
0x1800732ad  jb      short loc_1800732BE
0x1800732af  movsd   xmm0, [rsp+68h+var_48]
0x1800732b5  movsd   qword ptr [rcx], xmm0
0x1800732b9  mov     [rcx+8], ebp
0x1800732bc  jmp     short loc_1800732D6
0x1800732be  xor     edx, edx; Val
0x1800732c0  call    memset_0
0x1800732c5  call    cs:__imp__o__errno
0x1800732cb  mov     dword ptr [rax], 22h ; '"'
0x1800732d1  call    _invalid_parameter_noinfo
0x1800732d6  add     qword ptr [rbx+8], 0Ch
0x1800732db  cmp     byte ptr [rdi+40h], 0
0x1800732df  jnz     loc_180073383
0x1800732e5  cmp     qword ptr [rdi+38h], 0
0x1800732ea  jnz     short loc_180073359
0x1800732ec  call    cs:__imp_GetLastError
0x1800732f2  mov     r14d, eax
0x1800732f5  xor     r8d, r8d; pcbe
0x1800732f8  mov     rdx, rdi; pv
0x1800732fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180073302  call    cs:__imp_CreateThreadpoolTimer
0x180073308  mov     r15, rax
0x18007330b  mov     rbp, [rdi+38h]
0x18007330f  test    rbp, rbp
0x180073312  jz      short loc_18007334C
0x180073314  call    cs:__imp_GetLastError
0x18007331a  mov     ebx, eax
0x18007331c  xor     r9d, r9d; msWindowLength
0x18007331f  xor     r8d, r8d; msPeriod
0x180073322  xor     edx, edx; pftDueTime
0x180073324  mov     rcx, rbp; pti
0x180073327  call    cs:__imp_SetThreadpoolTimer
0x18007332d  mov     edx, 1; fCancelPendingCallbacks
0x180073332  mov     rcx, rbp; pti
0x180073335  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007333b  mov     rcx, rbp; pti
0x18007333e  call    cs:__imp_CloseThreadpoolTimer
0x180073344  mov     ecx, ebx; dwErrCode
0x180073346  call    cs:__imp_SetLastError
0x18007334c  mov     [rdi+38h], r15
0x180073350  mov     ecx, r14d; dwErrCode
0x180073353  call    cs:__imp_SetLastError
0x180073359  mov     rcx, [rdi+38h]; pti
0x18007335d  test    rcx, rcx
0x180073360  jz      short loc_180073383
0x180073362  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18007336b  mov     r9d, 4E2h; msWindowLength
0x180073371  xor     r8d, r8d; msPeriod
0x180073374  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180073379  call    cs:__imp_SetThreadpoolTimer
0x18007337f  mov     byte ptr [rdi+40h], 1
0x180073383  test    rsi, rsi
0x180073386  jz      short loc_180073392
0x180073388  mov     rcx, rsi; SRWLock
0x18007338b  call    cs:__imp_ReleaseSRWLockExclusive
0x180073391  nop
0x180073392  add     rsp, 38h
0x180073396  pop     r15
0x180073398  pop     r14
0x18007339a  pop     rdi
0x18007339b  pop     rsi
0x18007339c  pop     rbp
0x18007339d  pop     rbx
0x18007339e  retn
```
