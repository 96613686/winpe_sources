# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800103bc`
- end: `0x180010574`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800119b4`

## callees

- `0x180009e16`
- `0x180009f14`
- `0x1800103bc`
- `0x18001398c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001046d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010495`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001046d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010495`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010560`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010560`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010409`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010515`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010515`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800104f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001054e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800104f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001054e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001050d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001050d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800104d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800104d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010504`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010504`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
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
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x1800103bc  push    rbx
0x1800103be  push    rbp
0x1800103bf  push    rsi
0x1800103c0  push    rdi
0x1800103c1  push    r14
0x1800103c3  push    r15
0x1800103c5  sub     rsp, 28h
0x1800103c9  mov     rbp, r8
0x1800103cc  mov     r14d, edx
0x1800103cf  mov     rdi, rcx
0x1800103d2  mov     eax, [rcx]
0x1800103d4  test    eax, eax
0x1800103d6  jz      loc_180010567
0x1800103dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800103e3  jnz     loc_180010567
0x1800103e9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800103f0  test    rax, rax
0x1800103f3  jz      short loc_180010402
0x1800103f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103fa  test    al, al
0x1800103fc  jnz     loc_180010567
0x180010402  lea     rsi, [rdi+8]
0x180010406  mov     rcx, rsi; SRWLock
0x180010409  call    cs:__imp_AcquireSRWLockExclusive
0x18001040f  mov     eax, [rdi]
0x180010411  test    eax, eax
0x180010413  jz      loc_180010558
0x180010419  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010420  jnz     loc_180010558
0x180010426  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001042d  test    rax, rax
0x180010430  jz      short loc_18001043F
0x180010432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010437  test    al, al
0x180010439  jnz     loc_180010558
0x18001043f  xor     r15d, r15d
0x180010442  lea     edx, [r15+10h]; unsigned __int64
0x180010446  lea     rcx, [rdi+20h]; this
0x18001044a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001044f  test    al, al
0x180010451  jz      short loc_1800104AB
0x180010453  mov     rcx, [rdi+28h]; void *
0x180010457  mov     rax, [rdi+30h]
0x18001045b  sub     rax, rcx
0x18001045e  cmp     rcx, [rdi+30h]
0x180010462  sbb     r8, r8
0x180010465  and     r8, rax; Size
0x180010468  test    rcx, rcx
0x18001046b  jnz     short loc_18001047B
0x18001046d  call    cs:__imp__o__errno
0x180010473  mov     dword ptr [rax], 16h
0x180010479  jmp     short loc_1800104A1
0x18001047b  cmp     r8, 10h
0x18001047f  jb      short loc_18001048E
0x180010481  mov     [rcx], r14d
0x180010484  mov     [rcx+4], r15d
0x180010488  mov     [rcx+8], rbp
0x18001048c  jmp     short loc_1800104A6
0x18001048e  xor     edx, edx; Val
0x180010490  call    memset_0
0x180010495  call    cs:__imp__o__errno
0x18001049b  mov     dword ptr [rax], 22h ; '"'
0x1800104a1  call    _invalid_parameter_noinfo
0x1800104a6  add     qword ptr [rdi+28h], 10h
0x1800104ab  cmp     [rdi+18h], r15b
0x1800104af  jnz     loc_180010558
0x1800104b5  cmp     [rdi+10h], r15
0x1800104b9  jnz     short loc_180010528
0x1800104bb  call    cs:__imp_GetLastError
0x1800104c1  mov     r14d, eax
0x1800104c4  xor     r8d, r8d; pcbe
0x1800104c7  mov     rdx, rdi; pv
0x1800104ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800104d1  call    cs:__imp_CreateThreadpoolTimer
0x1800104d7  mov     r15, rax
0x1800104da  mov     rbp, [rdi+10h]
0x1800104de  test    rbp, rbp
0x1800104e1  jz      short loc_18001051B
0x1800104e3  call    cs:__imp_GetLastError
0x1800104e9  mov     ebx, eax
0x1800104eb  xor     r9d, r9d; msWindowLength
0x1800104ee  xor     r8d, r8d; msPeriod
0x1800104f1  xor     edx, edx; pftDueTime
0x1800104f3  mov     rcx, rbp; pti
0x1800104f6  call    cs:__imp_SetThreadpoolTimer
0x1800104fc  mov     edx, 1; fCancelPendingCallbacks
0x180010501  mov     rcx, rbp; pti
0x180010504  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001050a  mov     rcx, rbp; pti
0x18001050d  call    cs:__imp_CloseThreadpoolTimer
0x180010513  mov     ecx, ebx; dwErrCode
0x180010515  call    cs:__imp_SetLastError
0x18001051b  mov     [rdi+10h], r15
0x18001051f  mov     ecx, r14d; dwErrCode
0x180010522  call    cs:__imp_SetLastError
0x180010528  mov     rcx, [rdi+10h]; pti
0x18001052c  test    rcx, rcx
0x18001052f  jz      short loc_180010558
0x180010531  mov     rax, 0FFFFFFFF4D2FA200h
0x18001053b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180010540  mov     r9d, 124F8h; msWindowLength
0x180010546  xor     r8d, r8d; msPeriod
0x180010549  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001054e  call    cs:__imp_SetThreadpoolTimer
0x180010554  mov     byte ptr [rdi+18h], 1
0x180010558  test    rsi, rsi
0x18001055b  jz      short loc_180010567
0x18001055d  mov     rcx, rsi; SRWLock
0x180010560  call    cs:__imp_ReleaseSRWLockExclusive
0x180010566  nop
0x180010567  add     rsp, 28h
0x18001056b  pop     r15
0x18001056d  pop     r14
0x18001056f  pop     rdi
0x180010570  pop     rsi
0x180010571  pop     rbp
0x180010572  pop     rbx
0x180010573  retn
```
