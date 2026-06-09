# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000b6ec`
- end: `0x18000b8a4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b9e4`

## callees

- `0x18000288a`
- `0x1800028dc`
- `0x180009ba0`
- `0x18000b6ec`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b79d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b7c5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b79d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b7c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b739`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b739`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b890`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b845`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b845`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b813`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b826`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b87e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b826`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b87e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b83d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b83d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b834`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b834`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b801`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b801`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v15 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v15);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v16 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v16 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000b6ec  push    rbx
0x18000b6ee  push    rbp
0x18000b6ef  push    rsi
0x18000b6f0  push    rdi
0x18000b6f1  push    r14
0x18000b6f3  push    r15
0x18000b6f5  sub     rsp, 28h
0x18000b6f9  mov     rbp, r8
0x18000b6fc  mov     r14d, edx
0x18000b6ff  mov     rdi, rcx
0x18000b702  mov     eax, [rcx]
0x18000b704  test    eax, eax
0x18000b706  jz      loc_18000B897
0x18000b70c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b713  jnz     loc_18000B897
0x18000b719  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b720  test    rax, rax
0x18000b723  jz      short loc_18000B732
0x18000b725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b72a  test    al, al
0x18000b72c  jnz     loc_18000B897
0x18000b732  lea     rsi, [rdi+8]
0x18000b736  mov     rcx, rsi; SRWLock
0x18000b739  call    cs:__imp_AcquireSRWLockExclusive
0x18000b73f  mov     eax, [rdi]
0x18000b741  test    eax, eax
0x18000b743  jz      loc_18000B888
0x18000b749  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b750  jnz     loc_18000B888
0x18000b756  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b75d  test    rax, rax
0x18000b760  jz      short loc_18000B76F
0x18000b762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b767  test    al, al
0x18000b769  jnz     loc_18000B888
0x18000b76f  xor     r15d, r15d
0x18000b772  lea     edx, [r15+10h]; unsigned __int64
0x18000b776  lea     rcx, [rdi+20h]; this
0x18000b77a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b77f  test    al, al
0x18000b781  jz      short loc_18000B7DB
0x18000b783  mov     rcx, [rdi+28h]; void *
0x18000b787  mov     rax, [rdi+30h]
0x18000b78b  sub     rax, rcx
0x18000b78e  cmp     rcx, [rdi+30h]
0x18000b792  sbb     r8, r8
0x18000b795  and     r8, rax; Size
0x18000b798  test    rcx, rcx
0x18000b79b  jnz     short loc_18000B7AB
0x18000b79d  call    cs:__imp__o__errno
0x18000b7a3  mov     dword ptr [rax], 16h
0x18000b7a9  jmp     short loc_18000B7D1
0x18000b7ab  cmp     r8, 10h
0x18000b7af  jb      short loc_18000B7BE
0x18000b7b1  mov     [rcx], r14d
0x18000b7b4  mov     [rcx+4], r15d
0x18000b7b8  mov     [rcx+8], rbp
0x18000b7bc  jmp     short loc_18000B7D6
0x18000b7be  xor     edx, edx; Val
0x18000b7c0  call    memset_0
0x18000b7c5  call    cs:__imp__o__errno
0x18000b7cb  mov     dword ptr [rax], 22h ; '"'
0x18000b7d1  call    _invalid_parameter_noinfo
0x18000b7d6  add     qword ptr [rdi+28h], 10h
0x18000b7db  cmp     [rdi+18h], r15b
0x18000b7df  jnz     loc_18000B888
0x18000b7e5  cmp     [rdi+10h], r15
0x18000b7e9  jnz     short loc_18000B858
0x18000b7eb  call    cs:__imp_GetLastError
0x18000b7f1  mov     r14d, eax
0x18000b7f4  xor     r8d, r8d; pcbe
0x18000b7f7  mov     rdx, rdi; pv
0x18000b7fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b801  call    cs:__imp_CreateThreadpoolTimer
0x18000b807  mov     r15, rax
0x18000b80a  mov     rbp, [rdi+10h]
0x18000b80e  test    rbp, rbp
0x18000b811  jz      short loc_18000B84B
0x18000b813  call    cs:__imp_GetLastError
0x18000b819  mov     ebx, eax
0x18000b81b  xor     r9d, r9d; msWindowLength
0x18000b81e  xor     r8d, r8d; msPeriod
0x18000b821  xor     edx, edx; pftDueTime
0x18000b823  mov     rcx, rbp; pti
0x18000b826  call    cs:__imp_SetThreadpoolTimer
0x18000b82c  mov     edx, 1; fCancelPendingCallbacks
0x18000b831  mov     rcx, rbp; pti
0x18000b834  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b83a  mov     rcx, rbp; pti
0x18000b83d  call    cs:__imp_CloseThreadpoolTimer
0x18000b843  mov     ecx, ebx; dwErrCode
0x18000b845  call    cs:__imp_SetLastError
0x18000b84b  mov     [rdi+10h], r15
0x18000b84f  mov     ecx, r14d; dwErrCode
0x18000b852  call    cs:__imp_SetLastError
0x18000b858  mov     rcx, [rdi+10h]; pti
0x18000b85c  test    rcx, rcx
0x18000b85f  jz      short loc_18000B888
0x18000b861  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b86b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000b870  mov     r9d, 124F8h; msWindowLength
0x18000b876  xor     r8d, r8d; msPeriod
0x18000b879  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000b87e  call    cs:__imp_SetThreadpoolTimer
0x18000b884  mov     byte ptr [rdi+18h], 1
0x18000b888  test    rsi, rsi
0x18000b88b  jz      short loc_18000B897
0x18000b88d  mov     rcx, rsi; SRWLock
0x18000b890  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b896  nop
0x18000b897  add     rsp, 28h
0x18000b89b  pop     r15
0x18000b89d  pop     r14
0x18000b89f  pop     rdi
0x18000b8a0  pop     rsi
0x18000b8a1  pop     rbp
0x18000b8a2  pop     rbx
0x18000b8a3  retn
```
