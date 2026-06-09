# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140014a8c`
- end: `0x140014c15`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400167d0`

## callees

- `0x140014a8c`
- `0x140016bbc`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140014b3a`
- `msvcrt!memcpy_s` at `0x140014b3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014aea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014bf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014baf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014baf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014bbc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014b9e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014b9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014b90`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014be2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014b90`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014be2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014ba7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014ba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014b6b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014b6b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x140014a8c  push    rbx
0x140014a8e  push    rbp
0x140014a8f  push    rsi
0x140014a90  push    rdi
0x140014a91  push    r14
0x140014a93  push    r15
0x140014a95  sub     rsp, 48h
0x140014a99  mov     rax, cs:__security_cookie
0x140014aa0  xor     rax, rsp
0x140014aa3  mov     [rsp+78h+var_40], rax
0x140014aa8  mov     r14d, r9d
0x140014aab  movzx   ebp, r8w
0x140014aaf  mov     ebx, edx
0x140014ab1  mov     rdi, rcx
0x140014ab4  cmp     byte ptr [rcx], 0
0x140014ab7  jz      loc_140014BFB
0x140014abd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014ac4  jnz     loc_140014BFB
0x140014aca  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014ad1  test    rax, rax
0x140014ad4  jz      short loc_140014AE3
0x140014ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014adb  test    al, al
0x140014add  jnz     loc_140014BFB
0x140014ae3  lea     rsi, [rdi+28h]
0x140014ae7  mov     rcx, rsi; SRWLock
0x140014aea  call    cs:__imp_AcquireSRWLockExclusive
0x140014af0  xor     eax, eax
0x140014af2  mov     [rsp+78h+var_4A], ax
0x140014af7  mov     [rsp+78h+Source], ebx
0x140014afb  mov     [rsp+78h+var_4C], bp
0x140014b00  mov     [rsp+78h+var_48], r14d
0x140014b05  lea     rbx, [rdi+0E8h]
0x140014b0c  lea     ebp, [rax+0Ch]
0x140014b0f  mov     edx, ebp; unsigned __int64
0x140014b11  mov     rcx, rbx; this
0x140014b14  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014b19  test    al, al
0x140014b1b  jz      short loc_140014B44
0x140014b1d  mov     rcx, [rbx+8]; Destination
0x140014b21  mov     rax, [rbx+10h]
0x140014b25  sub     rax, rcx
0x140014b28  cmp     rcx, [rbx+10h]
0x140014b2c  sbb     rdx, rdx
0x140014b2f  and     rdx, rax; DestinationSize
0x140014b32  mov     r9d, ebp; SourceSize
0x140014b35  lea     r8, [rsp+78h+Source]; Source
0x140014b3a  call    cs:__imp_memcpy_s
0x140014b40  add     [rbx+8], rbp
0x140014b44  cmp     byte ptr [rdi+40h], 0
0x140014b48  jnz     loc_140014BEC
0x140014b4e  cmp     qword ptr [rdi+38h], 0
0x140014b53  jnz     short loc_140014BC2
0x140014b55  call    cs:__imp_GetLastError
0x140014b5b  mov     r14d, eax
0x140014b5e  xor     r8d, r8d; pcbe
0x140014b61  mov     rdx, rdi; pv
0x140014b64  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140014b6b  call    cs:__imp_CreateThreadpoolTimer
0x140014b71  mov     r15, rax
0x140014b74  mov     rbp, [rdi+38h]
0x140014b78  test    rbp, rbp
0x140014b7b  jz      short loc_140014BB5
0x140014b7d  call    cs:__imp_GetLastError
0x140014b83  mov     ebx, eax
0x140014b85  xor     r9d, r9d; msWindowLength
0x140014b88  xor     r8d, r8d; msPeriod
0x140014b8b  xor     edx, edx; pftDueTime
0x140014b8d  mov     rcx, rbp; pti
0x140014b90  call    cs:__imp_SetThreadpoolTimer
0x140014b96  mov     edx, 1; fCancelPendingCallbacks
0x140014b9b  mov     rcx, rbp; pti
0x140014b9e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140014ba4  mov     rcx, rbp; pti
0x140014ba7  call    cs:__imp_CloseThreadpoolTimer
0x140014bad  mov     ecx, ebx; dwErrCode
0x140014baf  call    cs:__imp_SetLastError
0x140014bb5  mov     [rdi+38h], r15
0x140014bb9  mov     ecx, r14d; dwErrCode
0x140014bbc  call    cs:__imp_SetLastError
0x140014bc2  mov     rcx, [rdi+38h]; pti
0x140014bc6  test    rcx, rcx
0x140014bc9  jz      short loc_140014BEC
0x140014bcb  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140014bd4  mov     r9d, 4E2h; msWindowLength
0x140014bda  xor     r8d, r8d; msPeriod
0x140014bdd  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x140014be2  call    cs:__imp_SetThreadpoolTimer
0x140014be8  mov     byte ptr [rdi+40h], 1
0x140014bec  test    rsi, rsi
0x140014bef  jz      short loc_140014BFB
0x140014bf1  mov     rcx, rsi; SRWLock
0x140014bf4  call    cs:__imp_ReleaseSRWLockExclusive
0x140014bfa  nop
0x140014bfb  mov     rcx, [rsp+78h+var_40]
0x140014c00  xor     rcx, rsp; StackCookie
0x140014c03  call    __security_check_cookie
0x140014c08  add     rsp, 48h
0x140014c0c  pop     r15
0x140014c0e  pop     r14
0x140014c10  pop     rdi
0x140014c11  pop     rsi
0x140014c12  pop     rbp
0x140014c13  pop     rbx
0x140014c14  retn
```
