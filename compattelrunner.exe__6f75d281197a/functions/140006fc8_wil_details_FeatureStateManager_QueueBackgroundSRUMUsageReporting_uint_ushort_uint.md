# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140006fc8`
- end: `0x140007163`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140009be0`

## callees

- `0x1400025ba`
- `0x1400026c0`
- `0x140006fc8`
- `0x14000a3ac`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000705f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007089`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000705f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007089`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007018`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000714f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000714f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000710a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000710a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400070f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400070f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400070c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400070c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007102`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007102`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400070eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000713d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400070eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000713d`

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
0x140006fc8  push    rbx
0x140006fca  push    rbp
0x140006fcb  push    rsi
0x140006fcc  push    rdi
0x140006fcd  push    r14
0x140006fcf  push    r15
0x140006fd1  sub     rsp, 38h
0x140006fd5  mov     ebp, r9d
0x140006fd8  movzx   ebx, r8w
0x140006fdc  mov     r14d, edx
0x140006fdf  mov     rdi, rcx
0x140006fe2  cmp     byte ptr [rcx], 0
0x140006fe5  jz      loc_140007156
0x140006feb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006ff2  jnz     loc_140007156
0x140006ff8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006fff  test    rax, rax
0x140007002  jz      short loc_140007011
0x140007004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007009  test    al, al
0x14000700b  jnz     loc_140007156
0x140007011  lea     rsi, [rdi+28h]
0x140007015  mov     rcx, rsi; SRWLock
0x140007018  call    cs:__imp_AcquireSRWLockExclusive
0x14000701e  xor     eax, eax
0x140007020  mov     word ptr [rsp+68h+var_48+6], ax
0x140007025  mov     dword ptr [rsp+68h+var_48], r14d
0x14000702a  mov     word ptr [rsp+68h+var_48+4], bx
0x14000702f  lea     rbx, [rdi+0E8h]
0x140007036  lea     edx, [rax+0Ch]; unsigned __int64
0x140007039  mov     rcx, rbx; this
0x14000703c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007041  test    al, al
0x140007043  jz      short loc_14000709F
0x140007045  mov     rcx, [rbx+8]; void *
0x140007049  mov     rax, [rbx+10h]
0x14000704d  sub     rax, rcx
0x140007050  cmp     rcx, [rbx+10h]
0x140007054  sbb     r8, r8
0x140007057  and     r8, rax; Size
0x14000705a  test    rcx, rcx
0x14000705d  jnz     short loc_14000706D
0x14000705f  call    cs:__imp__o__errno
0x140007065  mov     dword ptr [rax], 16h
0x14000706b  jmp     short loc_140007095
0x14000706d  cmp     r8, 0Ch
0x140007071  jb      short loc_140007082
0x140007073  movsd   xmm0, [rsp+68h+var_48]
0x140007079  movsd   qword ptr [rcx], xmm0
0x14000707d  mov     [rcx+8], ebp
0x140007080  jmp     short loc_14000709A
0x140007082  xor     edx, edx; Val
0x140007084  call    memset_0
0x140007089  call    cs:__imp__o__errno
0x14000708f  mov     dword ptr [rax], 22h ; '"'
0x140007095  call    _invalid_parameter_noinfo
0x14000709a  add     qword ptr [rbx+8], 0Ch
0x14000709f  cmp     byte ptr [rdi+40h], 0
0x1400070a3  jnz     loc_140007147
0x1400070a9  cmp     qword ptr [rdi+38h], 0
0x1400070ae  jnz     short loc_14000711D
0x1400070b0  call    cs:__imp_GetLastError
0x1400070b6  mov     r14d, eax
0x1400070b9  xor     r8d, r8d; pcbe
0x1400070bc  mov     rdx, rdi; pv
0x1400070bf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400070c6  call    cs:__imp_CreateThreadpoolTimer
0x1400070cc  mov     r15, rax
0x1400070cf  mov     rbp, [rdi+38h]
0x1400070d3  test    rbp, rbp
0x1400070d6  jz      short loc_140007110
0x1400070d8  call    cs:__imp_GetLastError
0x1400070de  mov     ebx, eax
0x1400070e0  xor     r9d, r9d; msWindowLength
0x1400070e3  xor     r8d, r8d; msPeriod
0x1400070e6  xor     edx, edx; pftDueTime
0x1400070e8  mov     rcx, rbp; pti
0x1400070eb  call    cs:__imp_SetThreadpoolTimer
0x1400070f1  mov     edx, 1; fCancelPendingCallbacks
0x1400070f6  mov     rcx, rbp; pti
0x1400070f9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400070ff  mov     rcx, rbp; pti
0x140007102  call    cs:__imp_CloseThreadpoolTimer
0x140007108  mov     ecx, ebx; dwErrCode
0x14000710a  call    cs:__imp_SetLastError
0x140007110  mov     [rdi+38h], r15
0x140007114  mov     ecx, r14d; dwErrCode
0x140007117  call    cs:__imp_SetLastError
0x14000711d  mov     rcx, [rdi+38h]; pti
0x140007121  test    rcx, rcx
0x140007124  jz      short loc_140007147
0x140007126  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000712f  mov     r9d, 4E2h; msWindowLength
0x140007135  xor     r8d, r8d; msPeriod
0x140007138  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000713d  call    cs:__imp_SetThreadpoolTimer
0x140007143  mov     byte ptr [rdi+40h], 1
0x140007147  test    rsi, rsi
0x14000714a  jz      short loc_140007156
0x14000714c  mov     rcx, rsi; SRWLock
0x14000714f  call    cs:__imp_ReleaseSRWLockExclusive
0x140007155  nop
0x140007156  add     rsp, 38h
0x14000715a  pop     r15
0x14000715c  pop     r14
0x14000715e  pop     rdi
0x14000715f  pop     rsi
0x140007160  pop     rbp
0x140007161  pop     rbx
0x140007162  retn
```
