# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000ab34`
- end: `0x14000accf`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000f6f0`

## callees

- `0x140002ca2`
- `0x140002d4c`
- `0x14000ab34`
- `0x140010580`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000abcb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000abf5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000abcb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000abf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000acbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000acbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ac83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ac32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ac32`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ac65`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ac65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ac6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ac6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ac57`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000aca9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ac57`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000aca9`

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
0x14000ab34  push    rbx
0x14000ab36  push    rbp
0x14000ab37  push    rsi
0x14000ab38  push    rdi
0x14000ab39  push    r14
0x14000ab3b  push    r15
0x14000ab3d  sub     rsp, 38h
0x14000ab41  mov     ebp, r9d
0x14000ab44  movzx   ebx, r8w
0x14000ab48  mov     r14d, edx
0x14000ab4b  mov     rdi, rcx
0x14000ab4e  cmp     byte ptr [rcx], 0
0x14000ab51  jz      loc_14000ACC2
0x14000ab57  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000ab5e  jnz     loc_14000ACC2
0x14000ab64  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000ab6b  test    rax, rax
0x14000ab6e  jz      short loc_14000AB7D
0x14000ab70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab75  test    al, al
0x14000ab77  jnz     loc_14000ACC2
0x14000ab7d  lea     rsi, [rdi+28h]
0x14000ab81  mov     rcx, rsi; SRWLock
0x14000ab84  call    cs:__imp_AcquireSRWLockExclusive
0x14000ab8a  xor     eax, eax
0x14000ab8c  mov     word ptr [rsp+68h+var_48+6], ax
0x14000ab91  mov     dword ptr [rsp+68h+var_48], r14d
0x14000ab96  mov     word ptr [rsp+68h+var_48+4], bx
0x14000ab9b  lea     rbx, [rdi+0E8h]
0x14000aba2  lea     edx, [rax+0Ch]; unsigned __int64
0x14000aba5  mov     rcx, rbx; this
0x14000aba8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000abad  test    al, al
0x14000abaf  jz      short loc_14000AC0B
0x14000abb1  mov     rcx, [rbx+8]; void *
0x14000abb5  mov     rax, [rbx+10h]
0x14000abb9  sub     rax, rcx
0x14000abbc  cmp     rcx, [rbx+10h]
0x14000abc0  sbb     r8, r8
0x14000abc3  and     r8, rax; Size
0x14000abc6  test    rcx, rcx
0x14000abc9  jnz     short loc_14000ABD9
0x14000abcb  call    cs:__imp__o__errno
0x14000abd1  mov     dword ptr [rax], 16h
0x14000abd7  jmp     short loc_14000AC01
0x14000abd9  cmp     r8, 0Ch
0x14000abdd  jb      short loc_14000ABEE
0x14000abdf  movsd   xmm0, [rsp+68h+var_48]
0x14000abe5  movsd   qword ptr [rcx], xmm0
0x14000abe9  mov     [rcx+8], ebp
0x14000abec  jmp     short loc_14000AC06
0x14000abee  xor     edx, edx; Val
0x14000abf0  call    memset_0
0x14000abf5  call    cs:__imp__o__errno
0x14000abfb  mov     dword ptr [rax], 22h ; '"'
0x14000ac01  call    _invalid_parameter_noinfo
0x14000ac06  add     qword ptr [rbx+8], 0Ch
0x14000ac0b  cmp     byte ptr [rdi+40h], 0
0x14000ac0f  jnz     loc_14000ACB3
0x14000ac15  cmp     qword ptr [rdi+38h], 0
0x14000ac1a  jnz     short loc_14000AC89
0x14000ac1c  call    cs:__imp_GetLastError
0x14000ac22  mov     r14d, eax
0x14000ac25  xor     r8d, r8d; pcbe
0x14000ac28  mov     rdx, rdi; pv
0x14000ac2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ac32  call    cs:__imp_CreateThreadpoolTimer
0x14000ac38  mov     r15, rax
0x14000ac3b  mov     rbp, [rdi+38h]
0x14000ac3f  test    rbp, rbp
0x14000ac42  jz      short loc_14000AC7C
0x14000ac44  call    cs:__imp_GetLastError
0x14000ac4a  mov     ebx, eax
0x14000ac4c  xor     r9d, r9d; msWindowLength
0x14000ac4f  xor     r8d, r8d; msPeriod
0x14000ac52  xor     edx, edx; pftDueTime
0x14000ac54  mov     rcx, rbp; pti
0x14000ac57  call    cs:__imp_SetThreadpoolTimer
0x14000ac5d  mov     edx, 1; fCancelPendingCallbacks
0x14000ac62  mov     rcx, rbp; pti
0x14000ac65  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000ac6b  mov     rcx, rbp; pti
0x14000ac6e  call    cs:__imp_CloseThreadpoolTimer
0x14000ac74  mov     ecx, ebx; dwErrCode
0x14000ac76  call    cs:__imp_SetLastError
0x14000ac7c  mov     [rdi+38h], r15
0x14000ac80  mov     ecx, r14d; dwErrCode
0x14000ac83  call    cs:__imp_SetLastError
0x14000ac89  mov     rcx, [rdi+38h]; pti
0x14000ac8d  test    rcx, rcx
0x14000ac90  jz      short loc_14000ACB3
0x14000ac92  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000ac9b  mov     r9d, 4E2h; msWindowLength
0x14000aca1  xor     r8d, r8d; msPeriod
0x14000aca4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000aca9  call    cs:__imp_SetThreadpoolTimer
0x14000acaf  mov     byte ptr [rdi+40h], 1
0x14000acb3  test    rsi, rsi
0x14000acb6  jz      short loc_14000ACC2
0x14000acb8  mov     rcx, rsi; SRWLock
0x14000acbb  call    cs:__imp_ReleaseSRWLockExclusive
0x14000acc1  nop
0x14000acc2  add     rsp, 38h
0x14000acc6  pop     r15
0x14000acc8  pop     r14
0x14000acca  pop     rdi
0x14000accb  pop     rsi
0x14000accc  pop     rbp
0x14000accd  pop     rbx
0x14000acce  retn
```
