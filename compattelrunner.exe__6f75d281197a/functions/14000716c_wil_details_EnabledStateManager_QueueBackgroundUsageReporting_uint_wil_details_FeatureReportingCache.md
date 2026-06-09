# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000716c`
- end: `0x140007324`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140008718`

## callees

- `0x1400025ba`
- `0x1400026c0`
- `0x14000716c`
- `0x14000a3ac`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000721d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007245`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000721d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007245`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400071b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400071b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007310`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007310`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400072c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400072d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400072c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400072d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000726b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000726b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007293`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400072b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400072b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007281`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007281`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400072bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400072bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400072a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400072fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400072a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400072fe`

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
0x14000716c  push    rbx
0x14000716e  push    rbp
0x14000716f  push    rsi
0x140007170  push    rdi
0x140007171  push    r14
0x140007173  push    r15
0x140007175  sub     rsp, 28h
0x140007179  mov     rbp, r8
0x14000717c  mov     r14d, edx
0x14000717f  mov     rdi, rcx
0x140007182  mov     eax, [rcx]
0x140007184  test    eax, eax
0x140007186  jz      loc_140007317
0x14000718c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007193  jnz     loc_140007317
0x140007199  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400071a0  test    rax, rax
0x1400071a3  jz      short loc_1400071B2
0x1400071a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071aa  test    al, al
0x1400071ac  jnz     loc_140007317
0x1400071b2  lea     rsi, [rdi+8]
0x1400071b6  mov     rcx, rsi; SRWLock
0x1400071b9  call    cs:__imp_AcquireSRWLockExclusive
0x1400071bf  mov     eax, [rdi]
0x1400071c1  test    eax, eax
0x1400071c3  jz      loc_140007308
0x1400071c9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400071d0  jnz     loc_140007308
0x1400071d6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400071dd  test    rax, rax
0x1400071e0  jz      short loc_1400071EF
0x1400071e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071e7  test    al, al
0x1400071e9  jnz     loc_140007308
0x1400071ef  xor     r15d, r15d
0x1400071f2  lea     edx, [r15+10h]; unsigned __int64
0x1400071f6  lea     rcx, [rdi+20h]; this
0x1400071fa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400071ff  test    al, al
0x140007201  jz      short loc_14000725B
0x140007203  mov     rcx, [rdi+28h]; void *
0x140007207  mov     rax, [rdi+30h]
0x14000720b  sub     rax, rcx
0x14000720e  cmp     rcx, [rdi+30h]
0x140007212  sbb     r8, r8
0x140007215  and     r8, rax; Size
0x140007218  test    rcx, rcx
0x14000721b  jnz     short loc_14000722B
0x14000721d  call    cs:__imp__o__errno
0x140007223  mov     dword ptr [rax], 16h
0x140007229  jmp     short loc_140007251
0x14000722b  cmp     r8, 10h
0x14000722f  jb      short loc_14000723E
0x140007231  mov     [rcx], r14d
0x140007234  mov     [rcx+4], r15d
0x140007238  mov     [rcx+8], rbp
0x14000723c  jmp     short loc_140007256
0x14000723e  xor     edx, edx; Val
0x140007240  call    memset_0
0x140007245  call    cs:__imp__o__errno
0x14000724b  mov     dword ptr [rax], 22h ; '"'
0x140007251  call    _invalid_parameter_noinfo
0x140007256  add     qword ptr [rdi+28h], 10h
0x14000725b  cmp     [rdi+18h], r15b
0x14000725f  jnz     loc_140007308
0x140007265  cmp     [rdi+10h], r15
0x140007269  jnz     short loc_1400072D8
0x14000726b  call    cs:__imp_GetLastError
0x140007271  mov     r14d, eax
0x140007274  xor     r8d, r8d; pcbe
0x140007277  mov     rdx, rdi; pv
0x14000727a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007281  call    cs:__imp_CreateThreadpoolTimer
0x140007287  mov     r15, rax
0x14000728a  mov     rbp, [rdi+10h]
0x14000728e  test    rbp, rbp
0x140007291  jz      short loc_1400072CB
0x140007293  call    cs:__imp_GetLastError
0x140007299  mov     ebx, eax
0x14000729b  xor     r9d, r9d; msWindowLength
0x14000729e  xor     r8d, r8d; msPeriod
0x1400072a1  xor     edx, edx; pftDueTime
0x1400072a3  mov     rcx, rbp; pti
0x1400072a6  call    cs:__imp_SetThreadpoolTimer
0x1400072ac  mov     edx, 1; fCancelPendingCallbacks
0x1400072b1  mov     rcx, rbp; pti
0x1400072b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400072ba  mov     rcx, rbp; pti
0x1400072bd  call    cs:__imp_CloseThreadpoolTimer
0x1400072c3  mov     ecx, ebx; dwErrCode
0x1400072c5  call    cs:__imp_SetLastError
0x1400072cb  mov     [rdi+10h], r15
0x1400072cf  mov     ecx, r14d; dwErrCode
0x1400072d2  call    cs:__imp_SetLastError
0x1400072d8  mov     rcx, [rdi+10h]; pti
0x1400072dc  test    rcx, rcx
0x1400072df  jz      short loc_140007308
0x1400072e1  mov     rax, 0FFFFFFFF4D2FA200h
0x1400072eb  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1400072f0  mov     r9d, 124F8h; msWindowLength
0x1400072f6  xor     r8d, r8d; msPeriod
0x1400072f9  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1400072fe  call    cs:__imp_SetThreadpoolTimer
0x140007304  mov     byte ptr [rdi+18h], 1
0x140007308  test    rsi, rsi
0x14000730b  jz      short loc_140007317
0x14000730d  mov     rcx, rsi; SRWLock
0x140007310  call    cs:__imp_ReleaseSRWLockExclusive
0x140007316  nop
0x140007317  add     rsp, 28h
0x14000731b  pop     r15
0x14000731d  pop     r14
0x14000731f  pop     rdi
0x140007320  pop     rsi
0x140007321  pop     rbp
0x140007322  pop     rbx
0x140007323  retn
```
