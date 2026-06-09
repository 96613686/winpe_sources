# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180011448`
- end: `0x180011600`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012a60`

## callees

- `0x180002eb2`
- `0x180002efc`
- `0x18000ae9c`
- `0x180011448`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800114f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011521`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800114f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011521`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011495`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011495`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001156f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001156f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011582`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800115da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011582`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800115da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001155d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001155d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011599`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011599`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011590`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011590`

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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x180011448  push    rbx
0x18001144a  push    rbp
0x18001144b  push    rsi
0x18001144c  push    rdi
0x18001144d  push    r14
0x18001144f  push    r15
0x180011451  sub     rsp, 28h
0x180011455  mov     rbp, r8
0x180011458  mov     r14d, edx
0x18001145b  mov     rdi, rcx
0x18001145e  mov     eax, [rcx]
0x180011460  test    eax, eax
0x180011462  jz      loc_1800115F3
0x180011468  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001146f  jnz     loc_1800115F3
0x180011475  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001147c  test    rax, rax
0x18001147f  jz      short loc_18001148E
0x180011481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011486  test    al, al
0x180011488  jnz     loc_1800115F3
0x18001148e  lea     rsi, [rdi+8]
0x180011492  mov     rcx, rsi; SRWLock
0x180011495  call    cs:__imp_AcquireSRWLockExclusive
0x18001149b  mov     eax, [rdi]
0x18001149d  test    eax, eax
0x18001149f  jz      loc_1800115E4
0x1800114a5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800114ac  jnz     loc_1800115E4
0x1800114b2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800114b9  test    rax, rax
0x1800114bc  jz      short loc_1800114CB
0x1800114be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114c3  test    al, al
0x1800114c5  jnz     loc_1800115E4
0x1800114cb  xor     r15d, r15d
0x1800114ce  lea     edx, [r15+10h]; unsigned __int64
0x1800114d2  lea     rcx, [rdi+20h]; this
0x1800114d6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800114db  test    al, al
0x1800114dd  jz      short loc_180011537
0x1800114df  mov     rcx, [rdi+28h]; void *
0x1800114e3  mov     rax, [rdi+30h]
0x1800114e7  sub     rax, rcx
0x1800114ea  cmp     rcx, [rdi+30h]
0x1800114ee  sbb     r8, r8
0x1800114f1  and     r8, rax; Size
0x1800114f4  test    rcx, rcx
0x1800114f7  jnz     short loc_180011507
0x1800114f9  call    cs:__imp__o__errno
0x1800114ff  mov     dword ptr [rax], 16h
0x180011505  jmp     short loc_18001152D
0x180011507  cmp     r8, 10h
0x18001150b  jb      short loc_18001151A
0x18001150d  mov     [rcx], r14d
0x180011510  mov     [rcx+4], r15d
0x180011514  mov     [rcx+8], rbp
0x180011518  jmp     short loc_180011532
0x18001151a  xor     edx, edx; Val
0x18001151c  call    memset_0
0x180011521  call    cs:__imp__o__errno
0x180011527  mov     dword ptr [rax], 22h ; '"'
0x18001152d  call    _invalid_parameter_noinfo
0x180011532  add     qword ptr [rdi+28h], 10h
0x180011537  cmp     [rdi+18h], r15b
0x18001153b  jnz     loc_1800115E4
0x180011541  cmp     [rdi+10h], r15
0x180011545  jnz     short loc_1800115B4
0x180011547  call    cs:__imp_GetLastError
0x18001154d  mov     r14d, eax
0x180011550  xor     r8d, r8d; pcbe
0x180011553  mov     rdx, rdi; pv
0x180011556  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001155d  call    cs:__imp_CreateThreadpoolTimer
0x180011563  mov     r15, rax
0x180011566  mov     rbp, [rdi+10h]
0x18001156a  test    rbp, rbp
0x18001156d  jz      short loc_1800115A7
0x18001156f  call    cs:__imp_GetLastError
0x180011575  mov     ebx, eax
0x180011577  xor     r9d, r9d; msWindowLength
0x18001157a  xor     r8d, r8d; msPeriod
0x18001157d  xor     edx, edx; pftDueTime
0x18001157f  mov     rcx, rbp; pti
0x180011582  call    cs:__imp_SetThreadpoolTimer
0x180011588  mov     edx, 1; fCancelPendingCallbacks
0x18001158d  mov     rcx, rbp; pti
0x180011590  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011596  mov     rcx, rbp; pti
0x180011599  call    cs:__imp_CloseThreadpoolTimer
0x18001159f  mov     ecx, ebx; dwErrCode
0x1800115a1  call    cs:__imp_SetLastError
0x1800115a7  mov     [rdi+10h], r15
0x1800115ab  mov     ecx, r14d; dwErrCode
0x1800115ae  call    cs:__imp_SetLastError
0x1800115b4  mov     rcx, [rdi+10h]; pti
0x1800115b8  test    rcx, rcx
0x1800115bb  jz      short loc_1800115E4
0x1800115bd  mov     rax, 0FFFFFFFF4D2FA200h
0x1800115c7  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800115cc  mov     r9d, 124F8h; msWindowLength
0x1800115d2  xor     r8d, r8d; msPeriod
0x1800115d5  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800115da  call    cs:__imp_SetThreadpoolTimer
0x1800115e0  mov     byte ptr [rdi+18h], 1
0x1800115e4  test    rsi, rsi
0x1800115e7  jz      short loc_1800115F3
0x1800115e9  mov     rcx, rsi; SRWLock
0x1800115ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800115f2  nop
0x1800115f3  add     rsp, 28h
0x1800115f7  pop     r15
0x1800115f9  pop     r14
0x1800115fb  pop     rdi
0x1800115fc  pop     rsi
0x1800115fd  pop     rbp
0x1800115fe  pop     rbx
0x1800115ff  retn
```
