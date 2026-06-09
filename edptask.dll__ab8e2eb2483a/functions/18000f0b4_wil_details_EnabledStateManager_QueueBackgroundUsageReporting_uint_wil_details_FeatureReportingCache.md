# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f0b4`
- end: `0x18000f248`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010468`

## callees

- `0x18000f0b4`
- `0x1800124ac`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f174`
- `msvcrt!memcpy_s` at `0x18000f174`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f234`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f234`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f100`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f18f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f18f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f1e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f1e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f1a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f1a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f1d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f1d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f1ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f222`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f1ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f222`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v12 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
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
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18000f0b4  push    rbx
0x18000f0b6  push    rbp
0x18000f0b7  push    rsi
0x18000f0b8  push    rdi
0x18000f0b9  push    r14
0x18000f0bb  push    r15
0x18000f0bd  sub     rsp, 38h
0x18000f0c1  mov     rbx, r8
0x18000f0c4  mov     ebp, edx
0x18000f0c6  mov     rdi, rcx
0x18000f0c9  mov     eax, [rcx]
0x18000f0cb  test    eax, eax
0x18000f0cd  jz      loc_18000F23B
0x18000f0d3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f0da  jnz     loc_18000F23B
0x18000f0e0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f0e7  test    rax, rax
0x18000f0ea  jz      short loc_18000F0F9
0x18000f0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f1  test    al, al
0x18000f0f3  jnz     loc_18000F23B
0x18000f0f9  lea     rsi, [rdi+8]
0x18000f0fd  mov     rcx, rsi; SRWLock
0x18000f100  call    cs:__imp_AcquireSRWLockExclusive
0x18000f106  mov     eax, [rdi]
0x18000f108  test    eax, eax
0x18000f10a  jz      loc_18000F22C
0x18000f110  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f117  jnz     loc_18000F22C
0x18000f11d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f124  test    rax, rax
0x18000f127  jz      short loc_18000F136
0x18000f129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f12e  test    al, al
0x18000f130  jnz     loc_18000F22C
0x18000f136  mov     [rsp+68h+Source], ebp
0x18000f13a  xor     eax, eax
0x18000f13c  mov     [rsp+68h+var_44], eax
0x18000f140  mov     [rsp+68h+var_40], rbx
0x18000f145  lea     ebp, [rax+10h]
0x18000f148  mov     edx, ebp; unsigned __int64
0x18000f14a  lea     rcx, [rdi+20h]; this
0x18000f14e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f153  test    al, al
0x18000f155  jz      short loc_18000F17E
0x18000f157  mov     rcx, [rdi+28h]; Destination
0x18000f15b  mov     rax, [rdi+30h]
0x18000f15f  sub     rax, rcx
0x18000f162  cmp     rcx, [rdi+30h]
0x18000f166  sbb     rdx, rdx
0x18000f169  and     rdx, rax; DestinationSize
0x18000f16c  mov     r9d, ebp; SourceSize
0x18000f16f  lea     r8, [rsp+68h+Source]; Source
0x18000f174  call    cs:__imp_memcpy_s
0x18000f17a  add     [rdi+28h], rbp
0x18000f17e  cmp     byte ptr [rdi+18h], 0
0x18000f182  jnz     loc_18000F22C
0x18000f188  cmp     qword ptr [rdi+10h], 0
0x18000f18d  jnz     short loc_18000F1FC
0x18000f18f  call    cs:__imp_GetLastError
0x18000f195  mov     r14d, eax
0x18000f198  xor     r8d, r8d; pcbe
0x18000f19b  mov     rdx, rdi; pv
0x18000f19e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f1a5  call    cs:__imp_CreateThreadpoolTimer
0x18000f1ab  mov     r15, rax
0x18000f1ae  mov     rbp, [rdi+10h]
0x18000f1b2  test    rbp, rbp
0x18000f1b5  jz      short loc_18000F1EF
0x18000f1b7  call    cs:__imp_GetLastError
0x18000f1bd  mov     ebx, eax
0x18000f1bf  xor     r9d, r9d; msWindowLength
0x18000f1c2  xor     r8d, r8d; msPeriod
0x18000f1c5  xor     edx, edx; pftDueTime
0x18000f1c7  mov     rcx, rbp; pti
0x18000f1ca  call    cs:__imp_SetThreadpoolTimer
0x18000f1d0  mov     edx, 1; fCancelPendingCallbacks
0x18000f1d5  mov     rcx, rbp; pti
0x18000f1d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f1de  mov     rcx, rbp; pti
0x18000f1e1  call    cs:__imp_CloseThreadpoolTimer
0x18000f1e7  mov     ecx, ebx; dwErrCode
0x18000f1e9  call    cs:__imp_SetLastError
0x18000f1ef  mov     [rdi+10h], r15
0x18000f1f3  mov     ecx, r14d; dwErrCode
0x18000f1f6  call    cs:__imp_SetLastError
0x18000f1fc  mov     rcx, [rdi+10h]; pti
0x18000f200  test    rcx, rcx
0x18000f203  jz      short loc_18000F22C
0x18000f205  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f20f  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000f214  mov     r9d, 124F8h; msWindowLength
0x18000f21a  xor     r8d, r8d; msPeriod
0x18000f21d  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000f222  call    cs:__imp_SetThreadpoolTimer
0x18000f228  mov     byte ptr [rdi+18h], 1
0x18000f22c  test    rsi, rsi
0x18000f22f  jz      short loc_18000F23B
0x18000f231  mov     rcx, rsi; SRWLock
0x18000f234  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f23a  nop
0x18000f23b  add     rsp, 38h
0x18000f23f  pop     r15
0x18000f241  pop     r14
0x18000f243  pop     rdi
0x18000f244  pop     rsi
0x18000f245  pop     rbp
0x18000f246  pop     rbx
0x18000f247  retn
```
