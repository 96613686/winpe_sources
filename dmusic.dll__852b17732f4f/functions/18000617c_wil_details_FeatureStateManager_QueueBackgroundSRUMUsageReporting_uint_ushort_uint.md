# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000617c`
- end: `0x180006317`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008980`

## callees

- `0x18000214a`
- `0x1800021a8`
- `0x18000617c`
- `0x18000900c`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006213`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000623d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006213`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000623d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000628c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000628c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000629f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000629f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000627a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000627a`

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
0x18000617c  push    rbx
0x18000617e  push    rbp
0x18000617f  push    rsi
0x180006180  push    rdi
0x180006181  push    r14
0x180006183  push    r15
0x180006185  sub     rsp, 38h
0x180006189  mov     ebp, r9d
0x18000618c  movzx   ebx, r8w
0x180006190  mov     r14d, edx
0x180006193  mov     rdi, rcx
0x180006196  cmp     byte ptr [rcx], 0
0x180006199  jz      loc_18000630A
0x18000619f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800061a6  jnz     loc_18000630A
0x1800061ac  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800061b3  test    rax, rax
0x1800061b6  jz      short loc_1800061C5
0x1800061b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061bd  test    al, al
0x1800061bf  jnz     loc_18000630A
0x1800061c5  lea     rsi, [rdi+28h]
0x1800061c9  mov     rcx, rsi; SRWLock
0x1800061cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800061d2  xor     eax, eax
0x1800061d4  mov     word ptr [rsp+68h+var_48+6], ax
0x1800061d9  mov     dword ptr [rsp+68h+var_48], r14d
0x1800061de  mov     word ptr [rsp+68h+var_48+4], bx
0x1800061e3  lea     rbx, [rdi+0E8h]
0x1800061ea  lea     edx, [rax+0Ch]; unsigned __int64
0x1800061ed  mov     rcx, rbx; this
0x1800061f0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800061f5  test    al, al
0x1800061f7  jz      short loc_180006253
0x1800061f9  mov     rcx, [rbx+8]; void *
0x1800061fd  mov     rax, [rbx+10h]
0x180006201  sub     rax, rcx
0x180006204  cmp     rcx, [rbx+10h]
0x180006208  sbb     r8, r8
0x18000620b  and     r8, rax; Size
0x18000620e  test    rcx, rcx
0x180006211  jnz     short loc_180006221
0x180006213  call    cs:__imp__o__errno
0x180006219  mov     dword ptr [rax], 16h
0x18000621f  jmp     short loc_180006249
0x180006221  cmp     r8, 0Ch
0x180006225  jb      short loc_180006236
0x180006227  movsd   xmm0, [rsp+68h+var_48]
0x18000622d  movsd   qword ptr [rcx], xmm0
0x180006231  mov     [rcx+8], ebp
0x180006234  jmp     short loc_18000624E
0x180006236  xor     edx, edx; Val
0x180006238  call    memset_0
0x18000623d  call    cs:__imp__o__errno
0x180006243  mov     dword ptr [rax], 22h ; '"'
0x180006249  call    _invalid_parameter_noinfo
0x18000624e  add     qword ptr [rbx+8], 0Ch
0x180006253  cmp     byte ptr [rdi+40h], 0
0x180006257  jnz     loc_1800062FB
0x18000625d  cmp     qword ptr [rdi+38h], 0
0x180006262  jnz     short loc_1800062D1
0x180006264  call    cs:__imp_GetLastError
0x18000626a  mov     r14d, eax
0x18000626d  xor     r8d, r8d; pcbe
0x180006270  mov     rdx, rdi; pv
0x180006273  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000627a  call    cs:__imp_CreateThreadpoolTimer
0x180006280  mov     r15, rax
0x180006283  mov     rbp, [rdi+38h]
0x180006287  test    rbp, rbp
0x18000628a  jz      short loc_1800062C4
0x18000628c  call    cs:__imp_GetLastError
0x180006292  mov     ebx, eax
0x180006294  xor     r9d, r9d; msWindowLength
0x180006297  xor     r8d, r8d; msPeriod
0x18000629a  xor     edx, edx; pftDueTime
0x18000629c  mov     rcx, rbp; pti
0x18000629f  call    cs:__imp_SetThreadpoolTimer
0x1800062a5  mov     edx, 1; fCancelPendingCallbacks
0x1800062aa  mov     rcx, rbp; pti
0x1800062ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800062b3  mov     rcx, rbp; pti
0x1800062b6  call    cs:__imp_CloseThreadpoolTimer
0x1800062bc  mov     ecx, ebx; dwErrCode
0x1800062be  call    cs:__imp_SetLastError
0x1800062c4  mov     [rdi+38h], r15
0x1800062c8  mov     ecx, r14d; dwErrCode
0x1800062cb  call    cs:__imp_SetLastError
0x1800062d1  mov     rcx, [rdi+38h]; pti
0x1800062d5  test    rcx, rcx
0x1800062d8  jz      short loc_1800062FB
0x1800062da  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800062e3  mov     r9d, 4E2h; msWindowLength
0x1800062e9  xor     r8d, r8d; msPeriod
0x1800062ec  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800062f1  call    cs:__imp_SetThreadpoolTimer
0x1800062f7  mov     byte ptr [rdi+40h], 1
0x1800062fb  test    rsi, rsi
0x1800062fe  jz      short loc_18000630A
0x180006300  mov     rcx, rsi; SRWLock
0x180006303  call    cs:__imp_ReleaseSRWLockExclusive
0x180006309  nop
0x18000630a  add     rsp, 38h
0x18000630e  pop     r15
0x180006310  pop     r14
0x180006312  pop     rdi
0x180006313  pop     rsi
0x180006314  pop     rbp
0x180006315  pop     rbx
0x180006316  retn
```
