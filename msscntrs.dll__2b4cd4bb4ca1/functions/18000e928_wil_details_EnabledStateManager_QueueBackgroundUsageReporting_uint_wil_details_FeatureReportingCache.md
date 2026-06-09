# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000e928`
- end: `0x18000eae0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000fb64`

## callees

- `0x1800032b2`
- `0x180003320`
- `0x18000a54c`
- `0x18000e928`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e9d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea01`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e9d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ea01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e975`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e975`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eacc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eacc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eaba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eaba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ea79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ea79`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea70`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ea3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ea3d`

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
0x18000e928  push    rbx
0x18000e92a  push    rbp
0x18000e92b  push    rsi
0x18000e92c  push    rdi
0x18000e92d  push    r14
0x18000e92f  push    r15
0x18000e931  sub     rsp, 28h
0x18000e935  mov     rbp, r8
0x18000e938  mov     r14d, edx
0x18000e93b  mov     rdi, rcx
0x18000e93e  mov     eax, [rcx]
0x18000e940  test    eax, eax
0x18000e942  jz      loc_18000EAD3
0x18000e948  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e94f  jnz     loc_18000EAD3
0x18000e955  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e95c  test    rax, rax
0x18000e95f  jz      short loc_18000E96E
0x18000e961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e966  test    al, al
0x18000e968  jnz     loc_18000EAD3
0x18000e96e  lea     rsi, [rdi+8]
0x18000e972  mov     rcx, rsi; SRWLock
0x18000e975  call    cs:__imp_AcquireSRWLockExclusive
0x18000e97b  mov     eax, [rdi]
0x18000e97d  test    eax, eax
0x18000e97f  jz      loc_18000EAC4
0x18000e985  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e98c  jnz     loc_18000EAC4
0x18000e992  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e999  test    rax, rax
0x18000e99c  jz      short loc_18000E9AB
0x18000e99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a3  test    al, al
0x18000e9a5  jnz     loc_18000EAC4
0x18000e9ab  xor     r15d, r15d
0x18000e9ae  lea     edx, [r15+10h]; unsigned __int64
0x18000e9b2  lea     rcx, [rdi+20h]; this
0x18000e9b6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000e9bb  test    al, al
0x18000e9bd  jz      short loc_18000EA17
0x18000e9bf  mov     rcx, [rdi+28h]; void *
0x18000e9c3  mov     rax, [rdi+30h]
0x18000e9c7  sub     rax, rcx
0x18000e9ca  cmp     rcx, [rdi+30h]
0x18000e9ce  sbb     r8, r8
0x18000e9d1  and     r8, rax; Size
0x18000e9d4  test    rcx, rcx
0x18000e9d7  jnz     short loc_18000E9E7
0x18000e9d9  call    cs:__imp__o__errno
0x18000e9df  mov     dword ptr [rax], 16h
0x18000e9e5  jmp     short loc_18000EA0D
0x18000e9e7  cmp     r8, 10h
0x18000e9eb  jb      short loc_18000E9FA
0x18000e9ed  mov     [rcx], r14d
0x18000e9f0  mov     [rcx+4], r15d
0x18000e9f4  mov     [rcx+8], rbp
0x18000e9f8  jmp     short loc_18000EA12
0x18000e9fa  xor     edx, edx; Val
0x18000e9fc  call    memset_0
0x18000ea01  call    cs:__imp__o__errno
0x18000ea07  mov     dword ptr [rax], 22h ; '"'
0x18000ea0d  call    _invalid_parameter_noinfo
0x18000ea12  add     qword ptr [rdi+28h], 10h
0x18000ea17  cmp     [rdi+18h], r15b
0x18000ea1b  jnz     loc_18000EAC4
0x18000ea21  cmp     [rdi+10h], r15
0x18000ea25  jnz     short loc_18000EA94
0x18000ea27  call    cs:__imp_GetLastError
0x18000ea2d  mov     r14d, eax
0x18000ea30  xor     r8d, r8d; pcbe
0x18000ea33  mov     rdx, rdi; pv
0x18000ea36  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ea3d  call    cs:__imp_CreateThreadpoolTimer
0x18000ea43  mov     r15, rax
0x18000ea46  mov     rbp, [rdi+10h]
0x18000ea4a  test    rbp, rbp
0x18000ea4d  jz      short loc_18000EA87
0x18000ea4f  call    cs:__imp_GetLastError
0x18000ea55  mov     ebx, eax
0x18000ea57  xor     r9d, r9d; msWindowLength
0x18000ea5a  xor     r8d, r8d; msPeriod
0x18000ea5d  xor     edx, edx; pftDueTime
0x18000ea5f  mov     rcx, rbp; pti
0x18000ea62  call    cs:__imp_SetThreadpoolTimer
0x18000ea68  mov     edx, 1; fCancelPendingCallbacks
0x18000ea6d  mov     rcx, rbp; pti
0x18000ea70  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ea76  mov     rcx, rbp; pti
0x18000ea79  call    cs:__imp_CloseThreadpoolTimer
0x18000ea7f  mov     ecx, ebx; dwErrCode
0x18000ea81  call    cs:__imp_SetLastError
0x18000ea87  mov     [rdi+10h], r15
0x18000ea8b  mov     ecx, r14d; dwErrCode
0x18000ea8e  call    cs:__imp_SetLastError
0x18000ea94  mov     rcx, [rdi+10h]; pti
0x18000ea98  test    rcx, rcx
0x18000ea9b  jz      short loc_18000EAC4
0x18000ea9d  mov     rax, 0FFFFFFFF4D2FA200h
0x18000eaa7  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000eaac  mov     r9d, 124F8h; msWindowLength
0x18000eab2  xor     r8d, r8d; msPeriod
0x18000eab5  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000eaba  call    cs:__imp_SetThreadpoolTimer
0x18000eac0  mov     byte ptr [rdi+18h], 1
0x18000eac4  test    rsi, rsi
0x18000eac7  jz      short loc_18000EAD3
0x18000eac9  mov     rcx, rsi; SRWLock
0x18000eacc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ead2  nop
0x18000ead3  add     rsp, 28h
0x18000ead7  pop     r15
0x18000ead9  pop     r14
0x18000eadb  pop     rdi
0x18000eadc  pop     rsi
0x18000eadd  pop     rbp
0x18000eade  pop     rbx
0x18000eadf  retn
```
