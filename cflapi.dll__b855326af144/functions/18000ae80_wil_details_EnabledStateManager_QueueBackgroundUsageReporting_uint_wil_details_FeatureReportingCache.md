# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000ae80`
- end: `0x18000b038`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c584`

## callees

- `0x180002ea2`
- `0x180002ef8`
- `0x18000ae80`
- `0x18000fc94`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af31`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af31`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000af59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b024`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b024`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aecd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afe6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afe6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000afc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000afc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000afd1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000afd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000afba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b012`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000afba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b012`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af95`

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
0x18000ae80  push    rbx
0x18000ae82  push    rbp
0x18000ae83  push    rsi
0x18000ae84  push    rdi
0x18000ae85  push    r14
0x18000ae87  push    r15
0x18000ae89  sub     rsp, 28h
0x18000ae8d  mov     rbp, r8
0x18000ae90  mov     r14d, edx
0x18000ae93  mov     rdi, rcx
0x18000ae96  mov     eax, [rcx]
0x18000ae98  test    eax, eax
0x18000ae9a  jz      loc_18000B02B
0x18000aea0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000aea7  jnz     loc_18000B02B
0x18000aead  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aeb4  test    rax, rax
0x18000aeb7  jz      short loc_18000AEC6
0x18000aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebe  test    al, al
0x18000aec0  jnz     loc_18000B02B
0x18000aec6  lea     rsi, [rdi+8]
0x18000aeca  mov     rcx, rsi; SRWLock
0x18000aecd  call    cs:__imp_AcquireSRWLockExclusive
0x18000aed3  mov     eax, [rdi]
0x18000aed5  test    eax, eax
0x18000aed7  jz      loc_18000B01C
0x18000aedd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000aee4  jnz     loc_18000B01C
0x18000aeea  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aef1  test    rax, rax
0x18000aef4  jz      short loc_18000AF03
0x18000aef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefb  test    al, al
0x18000aefd  jnz     loc_18000B01C
0x18000af03  xor     r15d, r15d
0x18000af06  lea     edx, [r15+10h]; unsigned __int64
0x18000af0a  lea     rcx, [rdi+20h]; this
0x18000af0e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000af13  test    al, al
0x18000af15  jz      short loc_18000AF6F
0x18000af17  mov     rcx, [rdi+28h]; void *
0x18000af1b  mov     rax, [rdi+30h]
0x18000af1f  sub     rax, rcx
0x18000af22  cmp     rcx, [rdi+30h]
0x18000af26  sbb     r8, r8
0x18000af29  and     r8, rax; Size
0x18000af2c  test    rcx, rcx
0x18000af2f  jnz     short loc_18000AF3F
0x18000af31  call    cs:__imp__o__errno
0x18000af37  mov     dword ptr [rax], 16h
0x18000af3d  jmp     short loc_18000AF65
0x18000af3f  cmp     r8, 10h
0x18000af43  jb      short loc_18000AF52
0x18000af45  mov     [rcx], r14d
0x18000af48  mov     [rcx+4], r15d
0x18000af4c  mov     [rcx+8], rbp
0x18000af50  jmp     short loc_18000AF6A
0x18000af52  xor     edx, edx; Val
0x18000af54  call    memset_0
0x18000af59  call    cs:__imp__o__errno
0x18000af5f  mov     dword ptr [rax], 22h ; '"'
0x18000af65  call    _invalid_parameter_noinfo
0x18000af6a  add     qword ptr [rdi+28h], 10h
0x18000af6f  cmp     [rdi+18h], r15b
0x18000af73  jnz     loc_18000B01C
0x18000af79  cmp     [rdi+10h], r15
0x18000af7d  jnz     short loc_18000AFEC
0x18000af7f  call    cs:__imp_GetLastError
0x18000af85  mov     r14d, eax
0x18000af88  xor     r8d, r8d; pcbe
0x18000af8b  mov     rdx, rdi; pv
0x18000af8e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000af95  call    cs:__imp_CreateThreadpoolTimer
0x18000af9b  mov     r15, rax
0x18000af9e  mov     rbp, [rdi+10h]
0x18000afa2  test    rbp, rbp
0x18000afa5  jz      short loc_18000AFDF
0x18000afa7  call    cs:__imp_GetLastError
0x18000afad  mov     ebx, eax
0x18000afaf  xor     r9d, r9d; msWindowLength
0x18000afb2  xor     r8d, r8d; msPeriod
0x18000afb5  xor     edx, edx; pftDueTime
0x18000afb7  mov     rcx, rbp; pti
0x18000afba  call    cs:__imp_SetThreadpoolTimer
0x18000afc0  mov     edx, 1; fCancelPendingCallbacks
0x18000afc5  mov     rcx, rbp; pti
0x18000afc8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000afce  mov     rcx, rbp; pti
0x18000afd1  call    cs:__imp_CloseThreadpoolTimer
0x18000afd7  mov     ecx, ebx; dwErrCode
0x18000afd9  call    cs:__imp_SetLastError
0x18000afdf  mov     [rdi+10h], r15
0x18000afe3  mov     ecx, r14d; dwErrCode
0x18000afe6  call    cs:__imp_SetLastError
0x18000afec  mov     rcx, [rdi+10h]; pti
0x18000aff0  test    rcx, rcx
0x18000aff3  jz      short loc_18000B01C
0x18000aff5  mov     rax, 0FFFFFFFF4D2FA200h
0x18000afff  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000b004  mov     r9d, 124F8h; msWindowLength
0x18000b00a  xor     r8d, r8d; msPeriod
0x18000b00d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000b012  call    cs:__imp_SetThreadpoolTimer
0x18000b018  mov     byte ptr [rdi+18h], 1
0x18000b01c  test    rsi, rsi
0x18000b01f  jz      short loc_18000B02B
0x18000b021  mov     rcx, rsi; SRWLock
0x18000b024  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b02a  nop
0x18000b02b  add     rsp, 28h
0x18000b02f  pop     r15
0x18000b031  pop     r14
0x18000b033  pop     rdi
0x18000b034  pop     rsi
0x18000b035  pop     rbp
0x18000b036  pop     rbx
0x18000b037  retn
```
