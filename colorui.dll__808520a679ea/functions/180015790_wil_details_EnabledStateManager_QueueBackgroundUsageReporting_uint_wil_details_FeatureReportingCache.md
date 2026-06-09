# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180015790`
- end: `0x180015923`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015ab8`

## callees

- `0x18000b464`
- `0x180015790`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015850`
- `msvcrt!memcpy_s` at `0x180015850`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800158b4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800158b4`
- `KERNEL32!GetLastError` at `0x18001586b`
- `KERNEL32!GetLastError` at `0x180015893`
- `KERNEL32!GetLastError` at `0x18001586b`
- `KERNEL32!GetLastError` at `0x180015893`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015910`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015910`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800158bd`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800158bd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800157dc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800157dc`
- `KERNEL32!SetThreadpoolTimer` at `0x1800158a6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800158fe`
- `KERNEL32!SetThreadpoolTimer` at `0x1800158a6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800158fe`
- `KERNEL32!CreateThreadpoolTimer` at `0x180015881`
- `KERNEL32!CreateThreadpoolTimer` at `0x180015881`
- `KERNEL32!SetLastError` at `0x1800158c5`
- `KERNEL32!SetLastError` at `0x1800158d2`
- `KERNEL32!SetLastError` at `0x1800158c5`
- `KERNEL32!SetLastError` at `0x1800158d2`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
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
      v13 = a3;
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
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
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
0x180015790  push    rbx
0x180015792  push    rbp
0x180015793  push    rsi
0x180015794  push    rdi
0x180015795  push    r14
0x180015797  push    r15
0x180015799  sub     rsp, 38h
0x18001579d  mov     eax, [rcx]
0x18001579f  mov     rbx, r8
0x1800157a2  mov     ebp, edx
0x1800157a4  mov     rdi, rcx
0x1800157a7  test    eax, eax
0x1800157a9  jz      loc_180015916
0x1800157af  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800157b6  jnz     loc_180015916
0x1800157bc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800157c3  test    rax, rax
0x1800157c6  jz      short loc_1800157D5
0x1800157c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157cd  test    al, al
0x1800157cf  jnz     loc_180015916
0x1800157d5  lea     rsi, [rdi+8]
0x1800157d9  mov     rcx, rsi; SRWLock
0x1800157dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800157e2  mov     eax, [rdi]
0x1800157e4  test    eax, eax
0x1800157e6  jz      loc_180015908
0x1800157ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800157f3  jnz     loc_180015908
0x1800157f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180015800  test    rax, rax
0x180015803  jz      short loc_180015812
0x180015805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580a  test    al, al
0x18001580c  jnz     loc_180015908
0x180015812  xor     eax, eax
0x180015814  mov     [rsp+68h+Source], ebp
0x180015818  lea     rcx, [rdi+20h]; this
0x18001581c  mov     [rsp+68h+var_44], eax
0x180015820  mov     [rsp+68h+var_40], rbx
0x180015825  lea     ebp, [rax+10h]
0x180015828  mov     edx, ebp; unsigned __int64
0x18001582a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001582f  test    al, al
0x180015831  jz      short loc_18001585A
0x180015833  mov     rcx, [rdi+28h]; Destination
0x180015837  lea     r8, [rsp+68h+Source]; Source
0x18001583c  mov     rax, [rdi+30h]
0x180015840  mov     r9d, ebp; SourceSize
0x180015843  sub     rax, rcx
0x180015846  cmp     rcx, [rdi+30h]
0x18001584a  sbb     rdx, rdx
0x18001584d  and     rdx, rax; DestinationSize
0x180015850  call    cs:__imp_memcpy_s
0x180015856  add     [rdi+28h], rbp
0x18001585a  cmp     byte ptr [rdi+18h], 0
0x18001585e  jnz     loc_180015908
0x180015864  cmp     qword ptr [rdi+10h], 0
0x180015869  jnz     short loc_1800158D8
0x18001586b  call    cs:__imp_GetLastError
0x180015871  xor     r8d, r8d; pcbe
0x180015874  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001587b  mov     rdx, rdi; pv
0x18001587e  mov     r14d, eax
0x180015881  call    cs:__imp_CreateThreadpoolTimer
0x180015887  mov     rbp, [rdi+10h]
0x18001588b  mov     r15, rax
0x18001588e  test    rbp, rbp
0x180015891  jz      short loc_1800158CB
0x180015893  call    cs:__imp_GetLastError
0x180015899  xor     r9d, r9d; msWindowLength
0x18001589c  xor     r8d, r8d; msPeriod
0x18001589f  xor     edx, edx; pftDueTime
0x1800158a1  mov     rcx, rbp; pti
0x1800158a4  mov     ebx, eax
0x1800158a6  call    cs:__imp_SetThreadpoolTimer
0x1800158ac  mov     edx, 1; fCancelPendingCallbacks
0x1800158b1  mov     rcx, rbp; pti
0x1800158b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800158ba  mov     rcx, rbp; pti
0x1800158bd  call    cs:__imp_CloseThreadpoolTimer
0x1800158c3  mov     ecx, ebx; dwErrCode
0x1800158c5  call    cs:__imp_SetLastError
0x1800158cb  mov     ecx, r14d; dwErrCode
0x1800158ce  mov     [rdi+10h], r15
0x1800158d2  call    cs:__imp_SetLastError
0x1800158d8  mov     rcx, [rdi+10h]; pti
0x1800158dc  test    rcx, rcx
0x1800158df  jz      short loc_180015908
0x1800158e1  mov     rax, 0FFFFFFFF4D2FA200h
0x1800158eb  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800158f0  mov     r9d, 124F8h; msWindowLength
0x1800158f6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800158fb  xor     r8d, r8d; msPeriod
0x1800158fe  call    cs:__imp_SetThreadpoolTimer
0x180015904  mov     byte ptr [rdi+18h], 1
0x180015908  test    rsi, rsi
0x18001590b  jz      short loc_180015916
0x18001590d  mov     rcx, rsi; SRWLock
0x180015910  call    cs:__imp_ReleaseSRWLockExclusive
0x180015916  add     rsp, 38h
0x18001591a  pop     r15
0x18001591c  pop     r14
0x18001591e  pop     rdi
0x18001591f  pop     rsi
0x180015920  pop     rbp
0x180015921  pop     rbx
0x180015922  retn
```
