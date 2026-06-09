# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000fd04`
- end: `0x18000fe8c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800111d0`

## callees

- `0x180006318`
- `0x18000fd04`
- `0x180012040`
- `0x180013010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000fdb2`
- `msvcrt!memcpy_s` at `0x18000fdb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fd62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fd62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fe6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fe6c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fe1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fe1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fe08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fe5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fe08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fe5a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fe16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fe16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fde3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fde3`

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
0x18000fd04  push    rbx
0x18000fd06  push    rbp
0x18000fd07  push    rsi
0x18000fd08  push    rdi
0x18000fd09  push    r14
0x18000fd0b  push    r15
0x18000fd0d  sub     rsp, 48h
0x18000fd11  mov     rax, cs:__security_cookie
0x18000fd18  xor     rax, rsp
0x18000fd1b  mov     [rsp+78h+var_40], rax
0x18000fd20  cmp     byte ptr [rcx], 0
0x18000fd23  mov     r14d, r9d
0x18000fd26  movzx   ebp, r8w
0x18000fd2a  mov     ebx, edx
0x18000fd2c  mov     rdi, rcx
0x18000fd2f  jz      loc_18000FE72
0x18000fd35  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fd3c  jnz     loc_18000FE72
0x18000fd42  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fd49  test    rax, rax
0x18000fd4c  jz      short loc_18000FD5B
0x18000fd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd53  test    al, al
0x18000fd55  jnz     loc_18000FE72
0x18000fd5b  lea     rsi, [rdi+28h]
0x18000fd5f  mov     rcx, rsi; SRWLock
0x18000fd62  call    cs:__imp_AcquireSRWLockExclusive
0x18000fd68  xor     eax, eax
0x18000fd6a  mov     [rsp+78h+Source], ebx
0x18000fd6e  mov     [rsp+78h+var_4C], bp
0x18000fd73  lea     rbx, [rdi+0E8h]
0x18000fd7a  mov     rcx, rbx; this
0x18000fd7d  mov     [rsp+78h+var_4A], ax
0x18000fd82  mov     [rsp+78h+var_48], r14d
0x18000fd87  lea     ebp, [rax+0Ch]
0x18000fd8a  mov     edx, ebp; unsigned __int64
0x18000fd8c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000fd91  test    al, al
0x18000fd93  jz      short loc_18000FDBC
0x18000fd95  mov     rcx, [rbx+8]; Destination
0x18000fd99  lea     r8, [rsp+78h+Source]; Source
0x18000fd9e  mov     rax, [rbx+10h]
0x18000fda2  mov     r9d, ebp; SourceSize
0x18000fda5  sub     rax, rcx
0x18000fda8  cmp     rcx, [rbx+10h]
0x18000fdac  sbb     rdx, rdx
0x18000fdaf  and     rdx, rax; DestinationSize
0x18000fdb2  call    cs:__imp_memcpy_s
0x18000fdb8  add     [rbx+8], rbp
0x18000fdbc  cmp     byte ptr [rdi+40h], 0
0x18000fdc0  jnz     loc_18000FE64
0x18000fdc6  cmp     qword ptr [rdi+38h], 0
0x18000fdcb  jnz     short loc_18000FE3A
0x18000fdcd  call    cs:__imp_GetLastError
0x18000fdd3  xor     r8d, r8d; pcbe
0x18000fdd6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000fddd  mov     rdx, rdi; pv
0x18000fde0  mov     r14d, eax
0x18000fde3  call    cs:__imp_CreateThreadpoolTimer
0x18000fde9  mov     rbp, [rdi+38h]
0x18000fded  mov     r15, rax
0x18000fdf0  test    rbp, rbp
0x18000fdf3  jz      short loc_18000FE2D
0x18000fdf5  call    cs:__imp_GetLastError
0x18000fdfb  xor     r9d, r9d; msWindowLength
0x18000fdfe  xor     r8d, r8d; msPeriod
0x18000fe01  xor     edx, edx; pftDueTime
0x18000fe03  mov     rcx, rbp; pti
0x18000fe06  mov     ebx, eax
0x18000fe08  call    cs:__imp_SetThreadpoolTimer
0x18000fe0e  mov     edx, 1; fCancelPendingCallbacks
0x18000fe13  mov     rcx, rbp; pti
0x18000fe16  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000fe1c  mov     rcx, rbp; pti
0x18000fe1f  call    cs:__imp_CloseThreadpoolTimer
0x18000fe25  mov     ecx, ebx; dwErrCode
0x18000fe27  call    cs:__imp_SetLastError
0x18000fe2d  mov     ecx, r14d; dwErrCode
0x18000fe30  mov     [rdi+38h], r15
0x18000fe34  call    cs:__imp_SetLastError
0x18000fe3a  mov     rcx, [rdi+38h]; pti
0x18000fe3e  test    rcx, rcx
0x18000fe41  jz      short loc_18000FE64
0x18000fe43  mov     r9d, 4E2h; msWindowLength
0x18000fe49  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000fe52  xor     r8d, r8d; msPeriod
0x18000fe55  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000fe5a  call    cs:__imp_SetThreadpoolTimer
0x18000fe60  mov     byte ptr [rdi+40h], 1
0x18000fe64  test    rsi, rsi
0x18000fe67  jz      short loc_18000FE72
0x18000fe69  mov     rcx, rsi; SRWLock
0x18000fe6c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fe72  mov     rcx, [rsp+78h+var_40]
0x18000fe77  xor     rcx, rsp; StackCookie
0x18000fe7a  call    __security_check_cookie
0x18000fe7f  add     rsp, 48h
0x18000fe83  pop     r15
0x18000fe85  pop     r14
0x18000fe87  pop     rdi
0x18000fe88  pop     rsi
0x18000fe89  pop     rbp
0x18000fe8a  pop     rbx
0x18000fe8b  retn
```
