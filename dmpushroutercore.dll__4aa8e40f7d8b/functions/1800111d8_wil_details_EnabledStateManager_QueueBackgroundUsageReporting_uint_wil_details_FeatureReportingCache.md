# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800111d8`
- end: `0x180011390`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800114c0`

## callees

- `0x180004346`
- `0x1800043a8`
- `0x18000d58c`
- `0x1800111d8`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011289`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800112b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011289`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800112b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001133e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001133e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001137c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001137c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011225`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011225`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011329`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011329`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800112ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800112ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011320`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011320`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011312`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001136a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011312`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001136a`

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
0x1800111d8  push    rbx
0x1800111da  push    rbp
0x1800111db  push    rsi
0x1800111dc  push    rdi
0x1800111dd  push    r14
0x1800111df  push    r15
0x1800111e1  sub     rsp, 28h
0x1800111e5  mov     rbp, r8
0x1800111e8  mov     r14d, edx
0x1800111eb  mov     rdi, rcx
0x1800111ee  mov     eax, [rcx]
0x1800111f0  test    eax, eax
0x1800111f2  jz      loc_180011383
0x1800111f8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800111ff  jnz     loc_180011383
0x180011205  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001120c  test    rax, rax
0x18001120f  jz      short loc_18001121E
0x180011211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011216  test    al, al
0x180011218  jnz     loc_180011383
0x18001121e  lea     rsi, [rdi+8]
0x180011222  mov     rcx, rsi; SRWLock
0x180011225  call    cs:__imp_AcquireSRWLockExclusive
0x18001122b  mov     eax, [rdi]
0x18001122d  test    eax, eax
0x18001122f  jz      loc_180011374
0x180011235  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001123c  jnz     loc_180011374
0x180011242  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011249  test    rax, rax
0x18001124c  jz      short loc_18001125B
0x18001124e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011253  test    al, al
0x180011255  jnz     loc_180011374
0x18001125b  xor     r15d, r15d
0x18001125e  lea     edx, [r15+10h]; unsigned __int64
0x180011262  lea     rcx, [rdi+20h]; this
0x180011266  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001126b  test    al, al
0x18001126d  jz      short loc_1800112C7
0x18001126f  mov     rcx, [rdi+28h]; void *
0x180011273  mov     rax, [rdi+30h]
0x180011277  sub     rax, rcx
0x18001127a  cmp     rcx, [rdi+30h]
0x18001127e  sbb     r8, r8
0x180011281  and     r8, rax; Size
0x180011284  test    rcx, rcx
0x180011287  jnz     short loc_180011297
0x180011289  call    cs:__imp__o__errno
0x18001128f  mov     dword ptr [rax], 16h
0x180011295  jmp     short loc_1800112BD
0x180011297  cmp     r8, 10h
0x18001129b  jb      short loc_1800112AA
0x18001129d  mov     [rcx], r14d
0x1800112a0  mov     [rcx+4], r15d
0x1800112a4  mov     [rcx+8], rbp
0x1800112a8  jmp     short loc_1800112C2
0x1800112aa  xor     edx, edx; Val
0x1800112ac  call    memset_0
0x1800112b1  call    cs:__imp__o__errno
0x1800112b7  mov     dword ptr [rax], 22h ; '"'
0x1800112bd  call    _invalid_parameter_noinfo
0x1800112c2  add     qword ptr [rdi+28h], 10h
0x1800112c7  cmp     [rdi+18h], r15b
0x1800112cb  jnz     loc_180011374
0x1800112d1  cmp     [rdi+10h], r15
0x1800112d5  jnz     short loc_180011344
0x1800112d7  call    cs:__imp_GetLastError
0x1800112dd  mov     r14d, eax
0x1800112e0  xor     r8d, r8d; pcbe
0x1800112e3  mov     rdx, rdi; pv
0x1800112e6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800112ed  call    cs:__imp_CreateThreadpoolTimer
0x1800112f3  mov     r15, rax
0x1800112f6  mov     rbp, [rdi+10h]
0x1800112fa  test    rbp, rbp
0x1800112fd  jz      short loc_180011337
0x1800112ff  call    cs:__imp_GetLastError
0x180011305  mov     ebx, eax
0x180011307  xor     r9d, r9d; msWindowLength
0x18001130a  xor     r8d, r8d; msPeriod
0x18001130d  xor     edx, edx; pftDueTime
0x18001130f  mov     rcx, rbp; pti
0x180011312  call    cs:__imp_SetThreadpoolTimer
0x180011318  mov     edx, 1; fCancelPendingCallbacks
0x18001131d  mov     rcx, rbp; pti
0x180011320  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011326  mov     rcx, rbp; pti
0x180011329  call    cs:__imp_CloseThreadpoolTimer
0x18001132f  mov     ecx, ebx; dwErrCode
0x180011331  call    cs:__imp_SetLastError
0x180011337  mov     [rdi+10h], r15
0x18001133b  mov     ecx, r14d; dwErrCode
0x18001133e  call    cs:__imp_SetLastError
0x180011344  mov     rcx, [rdi+10h]; pti
0x180011348  test    rcx, rcx
0x18001134b  jz      short loc_180011374
0x18001134d  mov     rax, 0FFFFFFFF4D2FA200h
0x180011357  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001135c  mov     r9d, 124F8h; msWindowLength
0x180011362  xor     r8d, r8d; msPeriod
0x180011365  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001136a  call    cs:__imp_SetThreadpoolTimer
0x180011370  mov     byte ptr [rdi+18h], 1
0x180011374  test    rsi, rsi
0x180011377  jz      short loc_180011383
0x180011379  mov     rcx, rsi; SRWLock
0x18001137c  call    cs:__imp_ReleaseSRWLockExclusive
0x180011382  nop
0x180011383  add     rsp, 28h
0x180011387  pop     r15
0x180011389  pop     r14
0x18001138b  pop     rdi
0x18001138c  pop     rsi
0x18001138d  pop     rbp
0x18001138e  pop     rbx
0x18001138f  retn
```
