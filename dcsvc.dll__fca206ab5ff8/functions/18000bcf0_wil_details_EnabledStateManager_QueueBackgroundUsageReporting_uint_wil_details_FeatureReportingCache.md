# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000bcf0`
- end: `0x18000bea4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `436`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bf84`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x18000a270`
- `0x18000bcf0`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bd9c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bdc4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bd9c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bdc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bd3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bd3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000be26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000be7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000be26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000be7e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000be34`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000be34`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000be01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000be01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000be3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000be3d`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  size_t v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
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
            v14 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v14);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v15 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v15 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v15, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = 56698136;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)_o__errno(v9, v8, v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v5, v7) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000bcf0  push    rbx
0x18000bcf2  push    rbp
0x18000bcf3  push    rsi
0x18000bcf4  push    rdi
0x18000bcf5  push    r14
0x18000bcf7  push    r15
0x18000bcf9  sub     rsp, 28h
0x18000bcfd  mov     rbp, r8
0x18000bd00  mov     rdi, rcx
0x18000bd03  mov     eax, [rcx]
0x18000bd05  test    eax, eax
0x18000bd07  jz      loc_18000BE97
0x18000bd0d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bd14  jnz     loc_18000BE97
0x18000bd1a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bd21  test    rax, rax
0x18000bd24  jz      short loc_18000BD33
0x18000bd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd2b  test    al, al
0x18000bd2d  jnz     loc_18000BE97
0x18000bd33  lea     rsi, [rdi+8]
0x18000bd37  mov     rcx, rsi; SRWLock
0x18000bd3a  call    cs:__imp_AcquireSRWLockExclusive
0x18000bd40  mov     eax, [rdi]
0x18000bd42  test    eax, eax
0x18000bd44  jz      loc_18000BE88
0x18000bd4a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bd51  jnz     loc_18000BE88
0x18000bd57  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bd5e  test    rax, rax
0x18000bd61  jz      short loc_18000BD70
0x18000bd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd68  test    al, al
0x18000bd6a  jnz     loc_18000BE88
0x18000bd70  mov     edx, 10h; unsigned __int64
0x18000bd75  lea     rcx, [rdi+20h]; this
0x18000bd79  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000bd7e  test    al, al
0x18000bd80  jz      short loc_18000BDDA
0x18000bd82  mov     rcx, [rdi+28h]; void *
0x18000bd86  mov     rax, [rdi+30h]
0x18000bd8a  sub     rax, rcx
0x18000bd8d  cmp     rcx, [rdi+30h]
0x18000bd91  sbb     r8, r8
0x18000bd94  and     r8, rax; Size
0x18000bd97  test    rcx, rcx
0x18000bd9a  jnz     short loc_18000BDAA
0x18000bd9c  call    cs:__imp__o__errno
0x18000bda2  mov     dword ptr [rax], 16h
0x18000bda8  jmp     short loc_18000BDD0
0x18000bdaa  cmp     r8, 10h
0x18000bdae  jb      short loc_18000BDBD
0x18000bdb0  mov     qword ptr [rcx], 3612518h
0x18000bdb7  mov     [rcx+8], rbp
0x18000bdbb  jmp     short loc_18000BDD5
0x18000bdbd  xor     edx, edx; Val
0x18000bdbf  call    memset_0
0x18000bdc4  call    cs:__imp__o__errno
0x18000bdca  mov     dword ptr [rax], 22h ; '"'
0x18000bdd0  call    _invalid_parameter_noinfo
0x18000bdd5  add     qword ptr [rdi+28h], 10h
0x18000bdda  cmp     byte ptr [rdi+18h], 0
0x18000bdde  jnz     loc_18000BE88
0x18000bde4  cmp     qword ptr [rdi+10h], 0
0x18000bde9  jnz     short loc_18000BE58
0x18000bdeb  call    cs:__imp_GetLastError
0x18000bdf1  mov     r14d, eax
0x18000bdf4  xor     r8d, r8d; pcbe
0x18000bdf7  mov     rdx, rdi; pv
0x18000bdfa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000be01  call    cs:__imp_CreateThreadpoolTimer
0x18000be07  mov     r15, rax
0x18000be0a  mov     rbp, [rdi+10h]
0x18000be0e  test    rbp, rbp
0x18000be11  jz      short loc_18000BE4B
0x18000be13  call    cs:__imp_GetLastError
0x18000be19  mov     ebx, eax
0x18000be1b  xor     r9d, r9d; msWindowLength
0x18000be1e  xor     r8d, r8d; msPeriod
0x18000be21  xor     edx, edx; pftDueTime
0x18000be23  mov     rcx, rbp; pti
0x18000be26  call    cs:__imp_SetThreadpoolTimer
0x18000be2c  mov     edx, 1; fCancelPendingCallbacks
0x18000be31  mov     rcx, rbp; pti
0x18000be34  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000be3a  mov     rcx, rbp; pti
0x18000be3d  call    cs:__imp_CloseThreadpoolTimer
0x18000be43  mov     ecx, ebx; dwErrCode
0x18000be45  call    cs:__imp_SetLastError
0x18000be4b  mov     [rdi+10h], r15
0x18000be4f  mov     ecx, r14d; dwErrCode
0x18000be52  call    cs:__imp_SetLastError
0x18000be58  mov     rcx, [rdi+10h]; pti
0x18000be5c  test    rcx, rcx
0x18000be5f  jz      short loc_18000BE88
0x18000be61  mov     rax, 0FFFFFFFF4D2FA200h
0x18000be6b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000be70  mov     r9d, 124F8h; msWindowLength
0x18000be76  xor     r8d, r8d; msPeriod
0x18000be79  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000be7e  call    cs:__imp_SetThreadpoolTimer
0x18000be84  mov     byte ptr [rdi+18h], 1
0x18000be88  test    rsi, rsi
0x18000be8b  jz      short loc_18000BE97
0x18000be8d  mov     rcx, rsi; SRWLock
0x18000be90  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be96  nop
0x18000be97  add     rsp, 28h
0x18000be9b  pop     r15
0x18000be9d  pop     r14
0x18000be9f  pop     rdi
0x18000bea0  pop     rsi
0x18000bea1  pop     rbp
0x18000bea2  pop     rbx
0x18000bea3  retn
```
