# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000e5c8`
- end: `0x18000e780`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000eb2c`

## callees

- `0x180003b36`
- `0x180003bc8`
- `0x18000bf4c`
- `0x18000e5c8`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e679`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e6a1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e679`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e6a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e76c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e76c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e615`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e615`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e72e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e702`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e75a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e702`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e75a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e6dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e6dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e719`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e719`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e710`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e710`

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
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x18000e5c8  push    rbx
0x18000e5ca  push    rbp
0x18000e5cb  push    rsi
0x18000e5cc  push    rdi
0x18000e5cd  push    r14
0x18000e5cf  push    r15
0x18000e5d1  sub     rsp, 28h
0x18000e5d5  mov     rbp, r8
0x18000e5d8  mov     r14d, edx
0x18000e5db  mov     rdi, rcx
0x18000e5de  mov     eax, [rcx]
0x18000e5e0  test    eax, eax
0x18000e5e2  jz      loc_18000E773
0x18000e5e8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e5ef  jnz     loc_18000E773
0x18000e5f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e5fc  test    rax, rax
0x18000e5ff  jz      short loc_18000E60E
0x18000e601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e606  test    al, al
0x18000e608  jnz     loc_18000E773
0x18000e60e  lea     rsi, [rdi+8]
0x18000e612  mov     rcx, rsi; SRWLock
0x18000e615  call    cs:__imp_AcquireSRWLockExclusive
0x18000e61b  mov     eax, [rdi]
0x18000e61d  test    eax, eax
0x18000e61f  jz      loc_18000E764
0x18000e625  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e62c  jnz     loc_18000E764
0x18000e632  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e639  test    rax, rax
0x18000e63c  jz      short loc_18000E64B
0x18000e63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e643  test    al, al
0x18000e645  jnz     loc_18000E764
0x18000e64b  xor     r15d, r15d
0x18000e64e  lea     edx, [r15+10h]; unsigned __int64
0x18000e652  lea     rcx, [rdi+20h]; this
0x18000e656  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000e65b  test    al, al
0x18000e65d  jz      short loc_18000E6B7
0x18000e65f  mov     rcx, [rdi+28h]; void *
0x18000e663  mov     rax, [rdi+30h]
0x18000e667  sub     rax, rcx
0x18000e66a  cmp     rcx, [rdi+30h]
0x18000e66e  sbb     r8, r8
0x18000e671  and     r8, rax; Size
0x18000e674  test    rcx, rcx
0x18000e677  jnz     short loc_18000E687
0x18000e679  call    cs:__imp__o__errno
0x18000e67f  mov     dword ptr [rax], 16h
0x18000e685  jmp     short loc_18000E6AD
0x18000e687  cmp     r8, 10h
0x18000e68b  jb      short loc_18000E69A
0x18000e68d  mov     [rcx], r14d
0x18000e690  mov     [rcx+4], r15d
0x18000e694  mov     [rcx+8], rbp
0x18000e698  jmp     short loc_18000E6B2
0x18000e69a  xor     edx, edx; Val
0x18000e69c  call    memset_0
0x18000e6a1  call    cs:__imp__o__errno
0x18000e6a7  mov     dword ptr [rax], 22h ; '"'
0x18000e6ad  call    _invalid_parameter_noinfo
0x18000e6b2  add     qword ptr [rdi+28h], 10h
0x18000e6b7  cmp     [rdi+18h], r15b
0x18000e6bb  jnz     loc_18000E764
0x18000e6c1  cmp     [rdi+10h], r15
0x18000e6c5  jnz     short loc_18000E734
0x18000e6c7  call    cs:__imp_GetLastError
0x18000e6cd  mov     r14d, eax
0x18000e6d0  xor     r8d, r8d; pcbe
0x18000e6d3  mov     rdx, rdi; pv
0x18000e6d6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e6dd  call    cs:__imp_CreateThreadpoolTimer
0x18000e6e3  mov     r15, rax
0x18000e6e6  mov     rbp, [rdi+10h]
0x18000e6ea  test    rbp, rbp
0x18000e6ed  jz      short loc_18000E727
0x18000e6ef  call    cs:__imp_GetLastError
0x18000e6f5  mov     ebx, eax
0x18000e6f7  xor     r9d, r9d; msWindowLength
0x18000e6fa  xor     r8d, r8d; msPeriod
0x18000e6fd  xor     edx, edx; pftDueTime
0x18000e6ff  mov     rcx, rbp; pti
0x18000e702  call    cs:__imp_SetThreadpoolTimer
0x18000e708  mov     edx, 1; fCancelPendingCallbacks
0x18000e70d  mov     rcx, rbp; pti
0x18000e710  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e716  mov     rcx, rbp; pti
0x18000e719  call    cs:__imp_CloseThreadpoolTimer
0x18000e71f  mov     ecx, ebx; dwErrCode
0x18000e721  call    cs:__imp_SetLastError
0x18000e727  mov     [rdi+10h], r15
0x18000e72b  mov     ecx, r14d; dwErrCode
0x18000e72e  call    cs:__imp_SetLastError
0x18000e734  mov     rcx, [rdi+10h]; pti
0x18000e738  test    rcx, rcx
0x18000e73b  jz      short loc_18000E764
0x18000e73d  mov     rax, 0FFFFFFFF4D2FA200h
0x18000e747  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000e74c  mov     r9d, 124F8h; msWindowLength
0x18000e752  xor     r8d, r8d; msPeriod
0x18000e755  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000e75a  call    cs:__imp_SetThreadpoolTimer
0x18000e760  mov     byte ptr [rdi+18h], 1
0x18000e764  test    rsi, rsi
0x18000e767  jz      short loc_18000E773
0x18000e769  mov     rcx, rsi; SRWLock
0x18000e76c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e772  nop
0x18000e773  add     rsp, 28h
0x18000e777  pop     r15
0x18000e779  pop     r14
0x18000e77b  pop     rdi
0x18000e77c  pop     rsi
0x18000e77d  pop     rbp
0x18000e77e  pop     rbx
0x18000e77f  retn
```
