# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000815c`
- end: `0x180008314`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800097a8`

## callees

- `0x180002b62`
- `0x180002be8`
- `0x18000815c`
- `0x18000c80c`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000820d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008235`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000820d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008283`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008300`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008300`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008271`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082a4`

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
0x18000815c  push    rbx
0x18000815e  push    rbp
0x18000815f  push    rsi
0x180008160  push    rdi
0x180008161  push    r14
0x180008163  push    r15
0x180008165  sub     rsp, 28h
0x180008169  mov     rbp, r8
0x18000816c  mov     r14d, edx
0x18000816f  mov     rdi, rcx
0x180008172  mov     eax, [rcx]
0x180008174  test    eax, eax
0x180008176  jz      loc_180008307
0x18000817c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008183  jnz     loc_180008307
0x180008189  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008190  test    rax, rax
0x180008193  jz      short loc_1800081A2
0x180008195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819a  test    al, al
0x18000819c  jnz     loc_180008307
0x1800081a2  lea     rsi, [rdi+8]
0x1800081a6  mov     rcx, rsi; SRWLock
0x1800081a9  call    cs:__imp_AcquireSRWLockExclusive
0x1800081af  mov     eax, [rdi]
0x1800081b1  test    eax, eax
0x1800081b3  jz      loc_1800082F8
0x1800081b9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800081c0  jnz     loc_1800082F8
0x1800081c6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800081cd  test    rax, rax
0x1800081d0  jz      short loc_1800081DF
0x1800081d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d7  test    al, al
0x1800081d9  jnz     loc_1800082F8
0x1800081df  xor     r15d, r15d
0x1800081e2  lea     edx, [r15+10h]; unsigned __int64
0x1800081e6  lea     rcx, [rdi+20h]; this
0x1800081ea  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800081ef  test    al, al
0x1800081f1  jz      short loc_18000824B
0x1800081f3  mov     rcx, [rdi+28h]; void *
0x1800081f7  mov     rax, [rdi+30h]
0x1800081fb  sub     rax, rcx
0x1800081fe  cmp     rcx, [rdi+30h]
0x180008202  sbb     r8, r8
0x180008205  and     r8, rax; Size
0x180008208  test    rcx, rcx
0x18000820b  jnz     short loc_18000821B
0x18000820d  call    cs:__imp__o__errno
0x180008213  mov     dword ptr [rax], 16h
0x180008219  jmp     short loc_180008241
0x18000821b  cmp     r8, 10h
0x18000821f  jb      short loc_18000822E
0x180008221  mov     [rcx], r14d
0x180008224  mov     [rcx+4], r15d
0x180008228  mov     [rcx+8], rbp
0x18000822c  jmp     short loc_180008246
0x18000822e  xor     edx, edx; Val
0x180008230  call    memset_0
0x180008235  call    cs:__imp__o__errno
0x18000823b  mov     dword ptr [rax], 22h ; '"'
0x180008241  call    _invalid_parameter_noinfo
0x180008246  add     qword ptr [rdi+28h], 10h
0x18000824b  cmp     [rdi+18h], r15b
0x18000824f  jnz     loc_1800082F8
0x180008255  cmp     [rdi+10h], r15
0x180008259  jnz     short loc_1800082C8
0x18000825b  call    cs:__imp_GetLastError
0x180008261  mov     r14d, eax
0x180008264  xor     r8d, r8d; pcbe
0x180008267  mov     rdx, rdi; pv
0x18000826a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008271  call    cs:__imp_CreateThreadpoolTimer
0x180008277  mov     r15, rax
0x18000827a  mov     rbp, [rdi+10h]
0x18000827e  test    rbp, rbp
0x180008281  jz      short loc_1800082BB
0x180008283  call    cs:__imp_GetLastError
0x180008289  mov     ebx, eax
0x18000828b  xor     r9d, r9d; msWindowLength
0x18000828e  xor     r8d, r8d; msPeriod
0x180008291  xor     edx, edx; pftDueTime
0x180008293  mov     rcx, rbp; pti
0x180008296  call    cs:__imp_SetThreadpoolTimer
0x18000829c  mov     edx, 1; fCancelPendingCallbacks
0x1800082a1  mov     rcx, rbp; pti
0x1800082a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082aa  mov     rcx, rbp; pti
0x1800082ad  call    cs:__imp_CloseThreadpoolTimer
0x1800082b3  mov     ecx, ebx; dwErrCode
0x1800082b5  call    cs:__imp_SetLastError
0x1800082bb  mov     [rdi+10h], r15
0x1800082bf  mov     ecx, r14d; dwErrCode
0x1800082c2  call    cs:__imp_SetLastError
0x1800082c8  mov     rcx, [rdi+10h]; pti
0x1800082cc  test    rcx, rcx
0x1800082cf  jz      short loc_1800082F8
0x1800082d1  mov     rax, 0FFFFFFFF4D2FA200h
0x1800082db  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800082e0  mov     r9d, 124F8h; msWindowLength
0x1800082e6  xor     r8d, r8d; msPeriod
0x1800082e9  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800082ee  call    cs:__imp_SetThreadpoolTimer
0x1800082f4  mov     byte ptr [rdi+18h], 1
0x1800082f8  test    rsi, rsi
0x1800082fb  jz      short loc_180008307
0x1800082fd  mov     rcx, rsi; SRWLock
0x180008300  call    cs:__imp_ReleaseSRWLockExclusive
0x180008306  nop
0x180008307  add     rsp, 28h
0x18000830b  pop     r15
0x18000830d  pop     r14
0x18000830f  pop     rdi
0x180008310  pop     rsi
0x180008311  pop     rbp
0x180008312  pop     rbx
0x180008313  retn
```
