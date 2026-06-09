# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180012ae0`
- end: `0x180012c93`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `435`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012d74`

## callees

- `0x180001f56`
- `0x180001fb8`
- `0x180008d0c`
- `0x180012ae0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012b8c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012bb4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012b8c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012bb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012bf1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012bf1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012c2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012c2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012c16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012c6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012c16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012c6e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012c24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012c24`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
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
          v11 = ThreadpoolTimer;
          if ( Ptr )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = v11;
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
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = 23065335;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x180012ae0  push    rbx
0x180012ae2  push    rbp
0x180012ae3  push    rsi
0x180012ae4  push    rdi
0x180012ae5  push    r14
0x180012ae7  push    r15
0x180012ae9  sub     rsp, 28h
0x180012aed  mov     eax, [rcx]
0x180012aef  mov     rbp, r8
0x180012af2  mov     rdi, rcx
0x180012af5  test    eax, eax
0x180012af7  jz      loc_180012C86
0x180012afd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012b04  jnz     loc_180012C86
0x180012b0a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012b11  test    rax, rax
0x180012b14  jz      short loc_180012B23
0x180012b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1b  test    al, al
0x180012b1d  jnz     loc_180012C86
0x180012b23  lea     rsi, [rdi+8]
0x180012b27  mov     rcx, rsi; SRWLock
0x180012b2a  call    cs:__imp_AcquireSRWLockExclusive
0x180012b30  mov     eax, [rdi]
0x180012b32  test    eax, eax
0x180012b34  jz      loc_180012C78
0x180012b3a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012b41  jnz     loc_180012C78
0x180012b47  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012b4e  test    rax, rax
0x180012b51  jz      short loc_180012B60
0x180012b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b58  test    al, al
0x180012b5a  jnz     loc_180012C78
0x180012b60  mov     edx, 10h; unsigned __int64
0x180012b65  lea     rcx, [rdi+20h]; this
0x180012b69  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180012b6e  test    al, al
0x180012b70  jz      short loc_180012BCA
0x180012b72  mov     rcx, [rdi+28h]; void *
0x180012b76  mov     rax, [rdi+30h]
0x180012b7a  sub     rax, rcx
0x180012b7d  cmp     rcx, [rdi+30h]
0x180012b81  sbb     r8, r8
0x180012b84  and     r8, rax; Size
0x180012b87  test    rcx, rcx
0x180012b8a  jnz     short loc_180012B9A
0x180012b8c  call    cs:__imp__o__errno
0x180012b92  mov     dword ptr [rax], 16h
0x180012b98  jmp     short loc_180012BC0
0x180012b9a  cmp     r8, 10h
0x180012b9e  jb      short loc_180012BAD
0x180012ba0  mov     qword ptr [rcx], 15FF2F7h
0x180012ba7  mov     [rcx+8], rbp
0x180012bab  jmp     short loc_180012BC5
0x180012bad  xor     edx, edx; Val
0x180012baf  call    memset_0
0x180012bb4  call    cs:__imp__o__errno
0x180012bba  mov     dword ptr [rax], 22h ; '"'
0x180012bc0  call    _invalid_parameter_noinfo
0x180012bc5  add     qword ptr [rdi+28h], 10h
0x180012bca  cmp     byte ptr [rdi+18h], 0
0x180012bce  jnz     loc_180012C78
0x180012bd4  cmp     qword ptr [rdi+10h], 0
0x180012bd9  jnz     short loc_180012C48
0x180012bdb  call    cs:__imp_GetLastError
0x180012be1  xor     r8d, r8d; pcbe
0x180012be4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012beb  mov     rdx, rdi; pv
0x180012bee  mov     r14d, eax
0x180012bf1  call    cs:__imp_CreateThreadpoolTimer
0x180012bf7  mov     rbp, [rdi+10h]
0x180012bfb  mov     r15, rax
0x180012bfe  test    rbp, rbp
0x180012c01  jz      short loc_180012C3B
0x180012c03  call    cs:__imp_GetLastError
0x180012c09  xor     r9d, r9d; msWindowLength
0x180012c0c  xor     r8d, r8d; msPeriod
0x180012c0f  xor     edx, edx; pftDueTime
0x180012c11  mov     rcx, rbp; pti
0x180012c14  mov     ebx, eax
0x180012c16  call    cs:__imp_SetThreadpoolTimer
0x180012c1c  mov     edx, 1; fCancelPendingCallbacks
0x180012c21  mov     rcx, rbp; pti
0x180012c24  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012c2a  mov     rcx, rbp; pti
0x180012c2d  call    cs:__imp_CloseThreadpoolTimer
0x180012c33  mov     ecx, ebx; dwErrCode
0x180012c35  call    cs:__imp_SetLastError
0x180012c3b  mov     ecx, r14d; dwErrCode
0x180012c3e  mov     [rdi+10h], r15
0x180012c42  call    cs:__imp_SetLastError
0x180012c48  mov     rcx, [rdi+10h]; pti
0x180012c4c  test    rcx, rcx
0x180012c4f  jz      short loc_180012C78
0x180012c51  mov     rax, 0FFFFFFFF4D2FA200h
0x180012c5b  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180012c60  mov     r9d, 124F8h; msWindowLength
0x180012c66  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180012c6b  xor     r8d, r8d; msPeriod
0x180012c6e  call    cs:__imp_SetThreadpoolTimer
0x180012c74  mov     byte ptr [rdi+18h], 1
0x180012c78  test    rsi, rsi
0x180012c7b  jz      short loc_180012C86
0x180012c7d  mov     rcx, rsi; SRWLock
0x180012c80  call    cs:__imp_ReleaseSRWLockExclusive
0x180012c86  add     rsp, 28h
0x180012c8a  pop     r15
0x180012c8c  pop     r14
0x180012c8e  pop     rdi
0x180012c8f  pop     rsi
0x180012c90  pop     rbp
0x180012c91  pop     rbx
0x180012c92  retn
```
