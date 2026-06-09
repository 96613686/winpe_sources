# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000ec70`
- end: `0x18000ee28`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010688`

## callees

- `0x1800038c6`
- `0x180003940`
- `0x18000ec70`
- `0x180015d60`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed49`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000ed85`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000ed85`
- `KERNEL32!SetThreadpoolTimer` at `0x18000edaa`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ee02`
- `KERNEL32!SetThreadpoolTimer` at `0x18000edaa`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ee02`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ecbd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ecbd`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000edc1`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000edc1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ee14`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ee14`
- `KERNEL32!GetLastError` at `0x18000ed6f`
- `KERNEL32!GetLastError` at `0x18000ed97`
- `KERNEL32!GetLastError` at `0x18000ed6f`
- `KERNEL32!GetLastError` at `0x18000ed97`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000edb8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000edb8`
- `KERNEL32!SetLastError` at `0x18000edc9`
- `KERNEL32!SetLastError` at `0x18000edd6`
- `KERNEL32!SetLastError` at `0x18000edc9`
- `KERNEL32!SetLastError` at `0x18000edd6`

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
0x18000ec70  push    rbx
0x18000ec72  push    rbp
0x18000ec73  push    rsi
0x18000ec74  push    rdi
0x18000ec75  push    r14
0x18000ec77  push    r15
0x18000ec79  sub     rsp, 28h
0x18000ec7d  mov     rbp, r8
0x18000ec80  mov     r14d, edx
0x18000ec83  mov     rdi, rcx
0x18000ec86  mov     eax, [rcx]
0x18000ec88  test    eax, eax
0x18000ec8a  jz      loc_18000EE1B
0x18000ec90  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ec97  jnz     loc_18000EE1B
0x18000ec9d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000eca4  test    rax, rax
0x18000eca7  jz      short loc_18000ECB6
0x18000eca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecae  test    al, al
0x18000ecb0  jnz     loc_18000EE1B
0x18000ecb6  lea     rsi, [rdi+8]
0x18000ecba  mov     rcx, rsi; SRWLock
0x18000ecbd  call    cs:__imp_AcquireSRWLockExclusive
0x18000ecc3  mov     eax, [rdi]
0x18000ecc5  test    eax, eax
0x18000ecc7  jz      loc_18000EE0C
0x18000eccd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ecd4  jnz     loc_18000EE0C
0x18000ecda  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ece1  test    rax, rax
0x18000ece4  jz      short loc_18000ECF3
0x18000ece6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eceb  test    al, al
0x18000eced  jnz     loc_18000EE0C
0x18000ecf3  xor     r15d, r15d
0x18000ecf6  lea     edx, [r15+10h]; unsigned __int64
0x18000ecfa  lea     rcx, [rdi+20h]; this
0x18000ecfe  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ed03  test    al, al
0x18000ed05  jz      short loc_18000ED5F
0x18000ed07  mov     rcx, [rdi+28h]; void *
0x18000ed0b  mov     rax, [rdi+30h]
0x18000ed0f  sub     rax, rcx
0x18000ed12  cmp     rcx, [rdi+30h]
0x18000ed16  sbb     r8, r8
0x18000ed19  and     r8, rax; Size
0x18000ed1c  test    rcx, rcx
0x18000ed1f  jnz     short loc_18000ED2F
0x18000ed21  call    cs:__imp__o__errno
0x18000ed27  mov     dword ptr [rax], 16h
0x18000ed2d  jmp     short loc_18000ED55
0x18000ed2f  cmp     r8, 10h
0x18000ed33  jb      short loc_18000ED42
0x18000ed35  mov     [rcx], r14d
0x18000ed38  mov     [rcx+4], r15d
0x18000ed3c  mov     [rcx+8], rbp
0x18000ed40  jmp     short loc_18000ED5A
0x18000ed42  xor     edx, edx; Val
0x18000ed44  call    memset_0
0x18000ed49  call    cs:__imp__o__errno
0x18000ed4f  mov     dword ptr [rax], 22h ; '"'
0x18000ed55  call    _invalid_parameter_noinfo
0x18000ed5a  add     qword ptr [rdi+28h], 10h
0x18000ed5f  cmp     [rdi+18h], r15b
0x18000ed63  jnz     loc_18000EE0C
0x18000ed69  cmp     [rdi+10h], r15
0x18000ed6d  jnz     short loc_18000EDDC
0x18000ed6f  call    cs:__imp_GetLastError
0x18000ed75  mov     r14d, eax
0x18000ed78  xor     r8d, r8d; pcbe
0x18000ed7b  mov     rdx, rdi; pv
0x18000ed7e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ed85  call    cs:__imp_CreateThreadpoolTimer
0x18000ed8b  mov     r15, rax
0x18000ed8e  mov     rbp, [rdi+10h]
0x18000ed92  test    rbp, rbp
0x18000ed95  jz      short loc_18000EDCF
0x18000ed97  call    cs:__imp_GetLastError
0x18000ed9d  mov     ebx, eax
0x18000ed9f  xor     r9d, r9d; msWindowLength
0x18000eda2  xor     r8d, r8d; msPeriod
0x18000eda5  xor     edx, edx; pftDueTime
0x18000eda7  mov     rcx, rbp; pti
0x18000edaa  call    cs:__imp_SetThreadpoolTimer
0x18000edb0  mov     edx, 1; fCancelPendingCallbacks
0x18000edb5  mov     rcx, rbp; pti
0x18000edb8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000edbe  mov     rcx, rbp; pti
0x18000edc1  call    cs:__imp_CloseThreadpoolTimer
0x18000edc7  mov     ecx, ebx; dwErrCode
0x18000edc9  call    cs:__imp_SetLastError
0x18000edcf  mov     [rdi+10h], r15
0x18000edd3  mov     ecx, r14d; dwErrCode
0x18000edd6  call    cs:__imp_SetLastError
0x18000eddc  mov     rcx, [rdi+10h]; pti
0x18000ede0  test    rcx, rcx
0x18000ede3  jz      short loc_18000EE0C
0x18000ede5  mov     rax, 0FFFFFFFF4D2FA200h
0x18000edef  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000edf4  mov     r9d, 124F8h; msWindowLength
0x18000edfa  xor     r8d, r8d; msPeriod
0x18000edfd  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000ee02  call    cs:__imp_SetThreadpoolTimer
0x18000ee08  mov     byte ptr [rdi+18h], 1
0x18000ee0c  test    rsi, rsi
0x18000ee0f  jz      short loc_18000EE1B
0x18000ee11  mov     rcx, rsi; SRWLock
0x18000ee14  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ee1a  nop
0x18000ee1b  add     rsp, 28h
0x18000ee1f  pop     r15
0x18000ee21  pop     r14
0x18000ee23  pop     rdi
0x18000ee24  pop     rsi
0x18000ee25  pop     rbp
0x18000ee26  pop     rbx
0x18000ee27  retn
```
