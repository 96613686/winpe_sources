# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000b9fc`
- end: `0x18000bbb4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000cfa8`

## callees

- `0x180006dce`
- `0x180006ec4`
- `0x18000b9fc`
- `0x18000ed3c`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000baad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bad5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000baad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bad5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bba0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bba0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb23`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bb44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bb44`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bb11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bb11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bb4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bb4d`

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
0x18000b9fc  push    rbx
0x18000b9fe  push    rbp
0x18000b9ff  push    rsi
0x18000ba00  push    rdi
0x18000ba01  push    r14
0x18000ba03  push    r15
0x18000ba05  sub     rsp, 28h
0x18000ba09  mov     rbp, r8
0x18000ba0c  mov     r14d, edx
0x18000ba0f  mov     rdi, rcx
0x18000ba12  mov     eax, [rcx]
0x18000ba14  test    eax, eax
0x18000ba16  jz      loc_18000BBA7
0x18000ba1c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ba23  jnz     loc_18000BBA7
0x18000ba29  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ba30  test    rax, rax
0x18000ba33  jz      short loc_18000BA42
0x18000ba35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3a  test    al, al
0x18000ba3c  jnz     loc_18000BBA7
0x18000ba42  lea     rsi, [rdi+8]
0x18000ba46  mov     rcx, rsi; SRWLock
0x18000ba49  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba4f  mov     eax, [rdi]
0x18000ba51  test    eax, eax
0x18000ba53  jz      loc_18000BB98
0x18000ba59  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ba60  jnz     loc_18000BB98
0x18000ba66  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ba6d  test    rax, rax
0x18000ba70  jz      short loc_18000BA7F
0x18000ba72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba77  test    al, al
0x18000ba79  jnz     loc_18000BB98
0x18000ba7f  xor     r15d, r15d
0x18000ba82  lea     edx, [r15+10h]; unsigned __int64
0x18000ba86  lea     rcx, [rdi+20h]; this
0x18000ba8a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ba8f  test    al, al
0x18000ba91  jz      short loc_18000BAEB
0x18000ba93  mov     rcx, [rdi+28h]; void *
0x18000ba97  mov     rax, [rdi+30h]
0x18000ba9b  sub     rax, rcx
0x18000ba9e  cmp     rcx, [rdi+30h]
0x18000baa2  sbb     r8, r8
0x18000baa5  and     r8, rax; Size
0x18000baa8  test    rcx, rcx
0x18000baab  jnz     short loc_18000BABB
0x18000baad  call    cs:__imp__o__errno
0x18000bab3  mov     dword ptr [rax], 16h
0x18000bab9  jmp     short loc_18000BAE1
0x18000babb  cmp     r8, 10h
0x18000babf  jb      short loc_18000BACE
0x18000bac1  mov     [rcx], r14d
0x18000bac4  mov     [rcx+4], r15d
0x18000bac8  mov     [rcx+8], rbp
0x18000bacc  jmp     short loc_18000BAE6
0x18000bace  xor     edx, edx; Val
0x18000bad0  call    memset_0
0x18000bad5  call    cs:__imp__o__errno
0x18000badb  mov     dword ptr [rax], 22h ; '"'
0x18000bae1  call    _invalid_parameter_noinfo
0x18000bae6  add     qword ptr [rdi+28h], 10h
0x18000baeb  cmp     [rdi+18h], r15b
0x18000baef  jnz     loc_18000BB98
0x18000baf5  cmp     [rdi+10h], r15
0x18000baf9  jnz     short loc_18000BB68
0x18000bafb  call    cs:__imp_GetLastError
0x18000bb01  mov     r14d, eax
0x18000bb04  xor     r8d, r8d; pcbe
0x18000bb07  mov     rdx, rdi; pv
0x18000bb0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bb11  call    cs:__imp_CreateThreadpoolTimer
0x18000bb17  mov     r15, rax
0x18000bb1a  mov     rbp, [rdi+10h]
0x18000bb1e  test    rbp, rbp
0x18000bb21  jz      short loc_18000BB5B
0x18000bb23  call    cs:__imp_GetLastError
0x18000bb29  mov     ebx, eax
0x18000bb2b  xor     r9d, r9d; msWindowLength
0x18000bb2e  xor     r8d, r8d; msPeriod
0x18000bb31  xor     edx, edx; pftDueTime
0x18000bb33  mov     rcx, rbp; pti
0x18000bb36  call    cs:__imp_SetThreadpoolTimer
0x18000bb3c  mov     edx, 1; fCancelPendingCallbacks
0x18000bb41  mov     rcx, rbp; pti
0x18000bb44  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bb4a  mov     rcx, rbp; pti
0x18000bb4d  call    cs:__imp_CloseThreadpoolTimer
0x18000bb53  mov     ecx, ebx; dwErrCode
0x18000bb55  call    cs:__imp_SetLastError
0x18000bb5b  mov     [rdi+10h], r15
0x18000bb5f  mov     ecx, r14d; dwErrCode
0x18000bb62  call    cs:__imp_SetLastError
0x18000bb68  mov     rcx, [rdi+10h]; pti
0x18000bb6c  test    rcx, rcx
0x18000bb6f  jz      short loc_18000BB98
0x18000bb71  mov     rax, 0FFFFFFFF4D2FA200h
0x18000bb7b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000bb80  mov     r9d, 124F8h; msWindowLength
0x18000bb86  xor     r8d, r8d; msPeriod
0x18000bb89  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000bb8e  call    cs:__imp_SetThreadpoolTimer
0x18000bb94  mov     byte ptr [rdi+18h], 1
0x18000bb98  test    rsi, rsi
0x18000bb9b  jz      short loc_18000BBA7
0x18000bb9d  mov     rcx, rsi; SRWLock
0x18000bba0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bba6  nop
0x18000bba7  add     rsp, 28h
0x18000bbab  pop     r15
0x18000bbad  pop     r14
0x18000bbaf  pop     rdi
0x18000bbb0  pop     rsi
0x18000bbb1  pop     rbp
0x18000bbb2  pop     rbx
0x18000bbb3  retn
```
