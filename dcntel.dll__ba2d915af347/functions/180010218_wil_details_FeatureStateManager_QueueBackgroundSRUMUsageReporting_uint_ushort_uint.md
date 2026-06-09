# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180010218`
- end: `0x1800103b3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013110`

## callees

- `0x180009e16`
- `0x180009f14`
- `0x180010218`
- `0x18001398c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800102af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800102d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800102af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800102d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001039f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001039f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010268`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010268`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001035a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001035a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010328`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001033b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001038d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001033b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001038d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010352`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010352`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010316`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010316`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010349`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010349`

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
0x180010218  push    rbx
0x18001021a  push    rbp
0x18001021b  push    rsi
0x18001021c  push    rdi
0x18001021d  push    r14
0x18001021f  push    r15
0x180010221  sub     rsp, 38h
0x180010225  mov     ebp, r9d
0x180010228  movzx   ebx, r8w
0x18001022c  mov     r14d, edx
0x18001022f  mov     rdi, rcx
0x180010232  cmp     byte ptr [rcx], 0
0x180010235  jz      loc_1800103A6
0x18001023b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010242  jnz     loc_1800103A6
0x180010248  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001024f  test    rax, rax
0x180010252  jz      short loc_180010261
0x180010254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010259  test    al, al
0x18001025b  jnz     loc_1800103A6
0x180010261  lea     rsi, [rdi+28h]
0x180010265  mov     rcx, rsi; SRWLock
0x180010268  call    cs:__imp_AcquireSRWLockExclusive
0x18001026e  xor     eax, eax
0x180010270  mov     word ptr [rsp+68h+var_48+6], ax
0x180010275  mov     dword ptr [rsp+68h+var_48], r14d
0x18001027a  mov     word ptr [rsp+68h+var_48+4], bx
0x18001027f  lea     rbx, [rdi+0E8h]
0x180010286  lea     edx, [rax+0Ch]; unsigned __int64
0x180010289  mov     rcx, rbx; this
0x18001028c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180010291  test    al, al
0x180010293  jz      short loc_1800102EF
0x180010295  mov     rcx, [rbx+8]; void *
0x180010299  mov     rax, [rbx+10h]
0x18001029d  sub     rax, rcx
0x1800102a0  cmp     rcx, [rbx+10h]
0x1800102a4  sbb     r8, r8
0x1800102a7  and     r8, rax; Size
0x1800102aa  test    rcx, rcx
0x1800102ad  jnz     short loc_1800102BD
0x1800102af  call    cs:__imp__o__errno
0x1800102b5  mov     dword ptr [rax], 16h
0x1800102bb  jmp     short loc_1800102E5
0x1800102bd  cmp     r8, 0Ch
0x1800102c1  jb      short loc_1800102D2
0x1800102c3  movsd   xmm0, [rsp+68h+var_48]
0x1800102c9  movsd   qword ptr [rcx], xmm0
0x1800102cd  mov     [rcx+8], ebp
0x1800102d0  jmp     short loc_1800102EA
0x1800102d2  xor     edx, edx; Val
0x1800102d4  call    memset_0
0x1800102d9  call    cs:__imp__o__errno
0x1800102df  mov     dword ptr [rax], 22h ; '"'
0x1800102e5  call    _invalid_parameter_noinfo
0x1800102ea  add     qword ptr [rbx+8], 0Ch
0x1800102ef  cmp     byte ptr [rdi+40h], 0
0x1800102f3  jnz     loc_180010397
0x1800102f9  cmp     qword ptr [rdi+38h], 0
0x1800102fe  jnz     short loc_18001036D
0x180010300  call    cs:__imp_GetLastError
0x180010306  mov     r14d, eax
0x180010309  xor     r8d, r8d; pcbe
0x18001030c  mov     rdx, rdi; pv
0x18001030f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010316  call    cs:__imp_CreateThreadpoolTimer
0x18001031c  mov     r15, rax
0x18001031f  mov     rbp, [rdi+38h]
0x180010323  test    rbp, rbp
0x180010326  jz      short loc_180010360
0x180010328  call    cs:__imp_GetLastError
0x18001032e  mov     ebx, eax
0x180010330  xor     r9d, r9d; msWindowLength
0x180010333  xor     r8d, r8d; msPeriod
0x180010336  xor     edx, edx; pftDueTime
0x180010338  mov     rcx, rbp; pti
0x18001033b  call    cs:__imp_SetThreadpoolTimer
0x180010341  mov     edx, 1; fCancelPendingCallbacks
0x180010346  mov     rcx, rbp; pti
0x180010349  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001034f  mov     rcx, rbp; pti
0x180010352  call    cs:__imp_CloseThreadpoolTimer
0x180010358  mov     ecx, ebx; dwErrCode
0x18001035a  call    cs:__imp_SetLastError
0x180010360  mov     [rdi+38h], r15
0x180010364  mov     ecx, r14d; dwErrCode
0x180010367  call    cs:__imp_SetLastError
0x18001036d  mov     rcx, [rdi+38h]; pti
0x180010371  test    rcx, rcx
0x180010374  jz      short loc_180010397
0x180010376  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001037f  mov     r9d, 4E2h; msWindowLength
0x180010385  xor     r8d, r8d; msPeriod
0x180010388  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001038d  call    cs:__imp_SetThreadpoolTimer
0x180010393  mov     byte ptr [rdi+40h], 1
0x180010397  test    rsi, rsi
0x18001039a  jz      short loc_1800103A6
0x18001039c  mov     rcx, rsi; SRWLock
0x18001039f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800103a5  nop
0x1800103a6  add     rsp, 38h
0x1800103aa  pop     r15
0x1800103ac  pop     r14
0x1800103ae  pop     rdi
0x1800103af  pop     rsi
0x1800103b0  pop     rbp
0x1800103b1  pop     rbx
0x1800103b2  retn
```
