# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007818`
- end: `0x1800079a0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aea0`

## callees

- `0x180007818`
- `0x18000b464`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800078c6`
- `msvcrt!memcpy_s` at `0x1800078c6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000792a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000792a`
- `KERNEL32!GetLastError` at `0x1800078e1`
- `KERNEL32!GetLastError` at `0x180007909`
- `KERNEL32!GetLastError` at `0x1800078e1`
- `KERNEL32!GetLastError` at `0x180007909`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007980`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007980`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007933`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007933`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007876`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007876`
- `KERNEL32!SetThreadpoolTimer` at `0x18000791c`
- `KERNEL32!SetThreadpoolTimer` at `0x18000796e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000791c`
- `KERNEL32!SetThreadpoolTimer` at `0x18000796e`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800078f7`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800078f7`
- `KERNEL32!SetLastError` at `0x18000793b`
- `KERNEL32!SetLastError` at `0x180007948`
- `KERNEL32!SetLastError` at `0x18000793b`
- `KERNEL32!SetLastError` at `0x180007948`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x180007818  push    rbx
0x18000781a  push    rbp
0x18000781b  push    rsi
0x18000781c  push    rdi
0x18000781d  push    r14
0x18000781f  push    r15
0x180007821  sub     rsp, 48h
0x180007825  mov     rax, cs:__security_cookie
0x18000782c  xor     rax, rsp
0x18000782f  mov     [rsp+78h+var_40], rax
0x180007834  cmp     byte ptr [rcx], 0
0x180007837  mov     r14d, r9d
0x18000783a  movzx   ebp, r8w
0x18000783e  mov     ebx, edx
0x180007840  mov     rdi, rcx
0x180007843  jz      loc_180007986
0x180007849  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007850  jnz     loc_180007986
0x180007856  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000785d  test    rax, rax
0x180007860  jz      short loc_18000786F
0x180007862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007867  test    al, al
0x180007869  jnz     loc_180007986
0x18000786f  lea     rsi, [rdi+28h]
0x180007873  mov     rcx, rsi; SRWLock
0x180007876  call    cs:__imp_AcquireSRWLockExclusive
0x18000787c  xor     eax, eax
0x18000787e  mov     [rsp+78h+Source], ebx
0x180007882  mov     [rsp+78h+var_4C], bp
0x180007887  lea     rbx, [rdi+0E8h]
0x18000788e  mov     rcx, rbx; this
0x180007891  mov     [rsp+78h+var_4A], ax
0x180007896  mov     [rsp+78h+var_48], r14d
0x18000789b  lea     ebp, [rax+0Ch]
0x18000789e  mov     edx, ebp; unsigned __int64
0x1800078a0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800078a5  test    al, al
0x1800078a7  jz      short loc_1800078D0
0x1800078a9  mov     rcx, [rbx+8]; Destination
0x1800078ad  lea     r8, [rsp+78h+Source]; Source
0x1800078b2  mov     rax, [rbx+10h]
0x1800078b6  mov     r9d, ebp; SourceSize
0x1800078b9  sub     rax, rcx
0x1800078bc  cmp     rcx, [rbx+10h]
0x1800078c0  sbb     rdx, rdx
0x1800078c3  and     rdx, rax; DestinationSize
0x1800078c6  call    cs:__imp_memcpy_s
0x1800078cc  add     [rbx+8], rbp
0x1800078d0  cmp     byte ptr [rdi+40h], 0
0x1800078d4  jnz     loc_180007978
0x1800078da  cmp     qword ptr [rdi+38h], 0
0x1800078df  jnz     short loc_18000794E
0x1800078e1  call    cs:__imp_GetLastError
0x1800078e7  xor     r8d, r8d; pcbe
0x1800078ea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800078f1  mov     rdx, rdi; pv
0x1800078f4  mov     r14d, eax
0x1800078f7  call    cs:__imp_CreateThreadpoolTimer
0x1800078fd  mov     rbp, [rdi+38h]
0x180007901  mov     r15, rax
0x180007904  test    rbp, rbp
0x180007907  jz      short loc_180007941
0x180007909  call    cs:__imp_GetLastError
0x18000790f  xor     r9d, r9d; msWindowLength
0x180007912  xor     r8d, r8d; msPeriod
0x180007915  xor     edx, edx; pftDueTime
0x180007917  mov     rcx, rbp; pti
0x18000791a  mov     ebx, eax
0x18000791c  call    cs:__imp_SetThreadpoolTimer
0x180007922  mov     edx, 1; fCancelPendingCallbacks
0x180007927  mov     rcx, rbp; pti
0x18000792a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007930  mov     rcx, rbp; pti
0x180007933  call    cs:__imp_CloseThreadpoolTimer
0x180007939  mov     ecx, ebx; dwErrCode
0x18000793b  call    cs:__imp_SetLastError
0x180007941  mov     ecx, r14d; dwErrCode
0x180007944  mov     [rdi+38h], r15
0x180007948  call    cs:__imp_SetLastError
0x18000794e  mov     rcx, [rdi+38h]; pti
0x180007952  test    rcx, rcx
0x180007955  jz      short loc_180007978
0x180007957  mov     r9d, 4E2h; msWindowLength
0x18000795d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180007966  xor     r8d, r8d; msPeriod
0x180007969  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000796e  call    cs:__imp_SetThreadpoolTimer
0x180007974  mov     byte ptr [rdi+40h], 1
0x180007978  test    rsi, rsi
0x18000797b  jz      short loc_180007986
0x18000797d  mov     rcx, rsi; SRWLock
0x180007980  call    cs:__imp_ReleaseSRWLockExclusive
0x180007986  mov     rcx, [rsp+78h+var_40]
0x18000798b  xor     rcx, rsp; StackCookie
0x18000798e  call    __security_check_cookie
0x180007993  add     rsp, 48h
0x180007997  pop     r15
0x180007999  pop     r14
0x18000799b  pop     rdi
0x18000799c  pop     rsi
0x18000799d  pop     rbp
0x18000799e  pop     rbx
0x18000799f  retn
```
