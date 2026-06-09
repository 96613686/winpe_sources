# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180007750`
- end: `0x180007907`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `439`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008fac`

## callees

- `0x180002b1a`
- `0x180002b60`
- `0x180007750`
- `0x18000a570`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007801`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007829`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007801`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007829`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000779d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000779d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000784f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000784f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800078a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800078a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000788a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800078e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000788a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800078e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007865`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007865`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007898`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007898`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v12; // r15
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
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
          v12 = ThreadpoolTimer;
          if ( Ptr )
          {
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = v12;
          SetLastError(LastError);
        }
        v14 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v14 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
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
0x180007750  push    rbx
0x180007752  push    rbp
0x180007753  push    rsi
0x180007754  push    rdi
0x180007755  push    r14
0x180007757  push    r15
0x180007759  sub     rsp, 28h
0x18000775d  mov     eax, [rcx]
0x18000775f  mov     rbp, r8
0x180007762  mov     r14d, edx
0x180007765  mov     rdi, rcx
0x180007768  test    eax, eax
0x18000776a  jz      loc_1800078FA
0x180007770  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007777  jnz     loc_1800078FA
0x18000777d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007784  test    rax, rax
0x180007787  jz      short loc_180007796
0x180007789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778e  test    al, al
0x180007790  jnz     loc_1800078FA
0x180007796  lea     rsi, [rdi+8]
0x18000779a  mov     rcx, rsi; SRWLock
0x18000779d  call    cs:__imp_AcquireSRWLockExclusive
0x1800077a3  mov     eax, [rdi]
0x1800077a5  test    eax, eax
0x1800077a7  jz      loc_1800078EC
0x1800077ad  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800077b4  jnz     loc_1800078EC
0x1800077ba  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800077c1  test    rax, rax
0x1800077c4  jz      short loc_1800077D3
0x1800077c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cb  test    al, al
0x1800077cd  jnz     loc_1800078EC
0x1800077d3  xor     r15d, r15d
0x1800077d6  lea     rcx, [rdi+20h]; this
0x1800077da  lea     edx, [r15+10h]; unsigned __int64
0x1800077de  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800077e3  test    al, al
0x1800077e5  jz      short loc_18000783F
0x1800077e7  mov     rcx, [rdi+28h]; void *
0x1800077eb  mov     rax, [rdi+30h]
0x1800077ef  sub     rax, rcx
0x1800077f2  cmp     rcx, [rdi+30h]
0x1800077f6  sbb     r8, r8
0x1800077f9  and     r8, rax; Size
0x1800077fc  test    rcx, rcx
0x1800077ff  jnz     short loc_18000780F
0x180007801  call    cs:__imp__o__errno
0x180007807  mov     dword ptr [rax], 16h
0x18000780d  jmp     short loc_180007835
0x18000780f  cmp     r8, 10h
0x180007813  jb      short loc_180007822
0x180007815  mov     [rcx], r14d
0x180007818  mov     [rcx+4], r15d
0x18000781c  mov     [rcx+8], rbp
0x180007820  jmp     short loc_18000783A
0x180007822  xor     edx, edx; Val
0x180007824  call    memset_0
0x180007829  call    cs:__imp__o__errno
0x18000782f  mov     dword ptr [rax], 22h ; '"'
0x180007835  call    _invalid_parameter_noinfo
0x18000783a  add     qword ptr [rdi+28h], 10h
0x18000783f  cmp     [rdi+18h], r15b
0x180007843  jnz     loc_1800078EC
0x180007849  cmp     [rdi+10h], r15
0x18000784d  jnz     short loc_1800078BC
0x18000784f  call    cs:__imp_GetLastError
0x180007855  xor     r8d, r8d; pcbe
0x180007858  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000785f  mov     rdx, rdi; pv
0x180007862  mov     r14d, eax
0x180007865  call    cs:__imp_CreateThreadpoolTimer
0x18000786b  mov     rbp, [rdi+10h]
0x18000786f  mov     r15, rax
0x180007872  test    rbp, rbp
0x180007875  jz      short loc_1800078AF
0x180007877  call    cs:__imp_GetLastError
0x18000787d  xor     r9d, r9d; msWindowLength
0x180007880  xor     r8d, r8d; msPeriod
0x180007883  xor     edx, edx; pftDueTime
0x180007885  mov     rcx, rbp; pti
0x180007888  mov     ebx, eax
0x18000788a  call    cs:__imp_SetThreadpoolTimer
0x180007890  mov     edx, 1; fCancelPendingCallbacks
0x180007895  mov     rcx, rbp; pti
0x180007898  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000789e  mov     rcx, rbp; pti
0x1800078a1  call    cs:__imp_CloseThreadpoolTimer
0x1800078a7  mov     ecx, ebx; dwErrCode
0x1800078a9  call    cs:__imp_SetLastError
0x1800078af  mov     ecx, r14d; dwErrCode
0x1800078b2  mov     [rdi+10h], r15
0x1800078b6  call    cs:__imp_SetLastError
0x1800078bc  mov     rcx, [rdi+10h]; pti
0x1800078c0  test    rcx, rcx
0x1800078c3  jz      short loc_1800078EC
0x1800078c5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800078cf  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800078d4  mov     r9d, 124F8h; msWindowLength
0x1800078da  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800078df  xor     r8d, r8d; msPeriod
0x1800078e2  call    cs:__imp_SetThreadpoolTimer
0x1800078e8  mov     byte ptr [rdi+18h], 1
0x1800078ec  test    rsi, rsi
0x1800078ef  jz      short loc_1800078FA
0x1800078f1  mov     rcx, rsi; SRWLock
0x1800078f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078fa  add     rsp, 28h
0x1800078fe  pop     r15
0x180007900  pop     r14
0x180007902  pop     rdi
0x180007903  pop     rsi
0x180007904  pop     rbp
0x180007905  pop     rbx
0x180007906  retn
```
