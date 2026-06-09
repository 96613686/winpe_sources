# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800069f8`
- end: `0x180006b93`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009bf0`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x1800069f8`
- `0x18000a270`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ab9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006a48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006b1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006b6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006b1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006b6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006b29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006b29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006af6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006af6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006b32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006b32`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800069f8  push    rbx
0x1800069fa  push    rbp
0x1800069fb  push    rsi
0x1800069fc  push    rdi
0x1800069fd  push    r14
0x1800069ff  push    r15
0x180006a01  sub     rsp, 38h
0x180006a05  mov     ebp, r9d
0x180006a08  movzx   ebx, r8w
0x180006a0c  mov     r14d, edx
0x180006a0f  mov     rdi, rcx
0x180006a12  cmp     byte ptr [rcx], 0
0x180006a15  jz      loc_180006B86
0x180006a1b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006a22  jnz     loc_180006B86
0x180006a28  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006a2f  test    rax, rax
0x180006a32  jz      short loc_180006A41
0x180006a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a39  test    al, al
0x180006a3b  jnz     loc_180006B86
0x180006a41  lea     rsi, [rdi+28h]
0x180006a45  mov     rcx, rsi; SRWLock
0x180006a48  call    cs:__imp_AcquireSRWLockExclusive
0x180006a4e  xor     eax, eax
0x180006a50  mov     word ptr [rsp+68h+var_48+6], ax
0x180006a55  mov     dword ptr [rsp+68h+var_48], r14d
0x180006a5a  mov     word ptr [rsp+68h+var_48+4], bx
0x180006a5f  lea     rbx, [rdi+0E8h]
0x180006a66  lea     edx, [rax+0Ch]; unsigned __int64
0x180006a69  mov     rcx, rbx; this
0x180006a6c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006a71  test    al, al
0x180006a73  jz      short loc_180006ACF
0x180006a75  mov     rcx, [rbx+8]; void *
0x180006a79  mov     rax, [rbx+10h]
0x180006a7d  sub     rax, rcx
0x180006a80  cmp     rcx, [rbx+10h]
0x180006a84  sbb     r8, r8
0x180006a87  and     r8, rax; Size
0x180006a8a  test    rcx, rcx
0x180006a8d  jnz     short loc_180006A9D
0x180006a8f  call    cs:__imp__o__errno
0x180006a95  mov     dword ptr [rax], 16h
0x180006a9b  jmp     short loc_180006AC5
0x180006a9d  cmp     r8, 0Ch
0x180006aa1  jb      short loc_180006AB2
0x180006aa3  movsd   xmm0, [rsp+68h+var_48]
0x180006aa9  movsd   qword ptr [rcx], xmm0
0x180006aad  mov     [rcx+8], ebp
0x180006ab0  jmp     short loc_180006ACA
0x180006ab2  xor     edx, edx; Val
0x180006ab4  call    memset_0
0x180006ab9  call    cs:__imp__o__errno
0x180006abf  mov     dword ptr [rax], 22h ; '"'
0x180006ac5  call    _invalid_parameter_noinfo
0x180006aca  add     qword ptr [rbx+8], 0Ch
0x180006acf  cmp     byte ptr [rdi+40h], 0
0x180006ad3  jnz     loc_180006B77
0x180006ad9  cmp     qword ptr [rdi+38h], 0
0x180006ade  jnz     short loc_180006B4D
0x180006ae0  call    cs:__imp_GetLastError
0x180006ae6  mov     r14d, eax
0x180006ae9  xor     r8d, r8d; pcbe
0x180006aec  mov     rdx, rdi; pv
0x180006aef  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006af6  call    cs:__imp_CreateThreadpoolTimer
0x180006afc  mov     r15, rax
0x180006aff  mov     rbp, [rdi+38h]
0x180006b03  test    rbp, rbp
0x180006b06  jz      short loc_180006B40
0x180006b08  call    cs:__imp_GetLastError
0x180006b0e  mov     ebx, eax
0x180006b10  xor     r9d, r9d; msWindowLength
0x180006b13  xor     r8d, r8d; msPeriod
0x180006b16  xor     edx, edx; pftDueTime
0x180006b18  mov     rcx, rbp; pti
0x180006b1b  call    cs:__imp_SetThreadpoolTimer
0x180006b21  mov     edx, 1; fCancelPendingCallbacks
0x180006b26  mov     rcx, rbp; pti
0x180006b29  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006b2f  mov     rcx, rbp; pti
0x180006b32  call    cs:__imp_CloseThreadpoolTimer
0x180006b38  mov     ecx, ebx; dwErrCode
0x180006b3a  call    cs:__imp_SetLastError
0x180006b40  mov     [rdi+38h], r15
0x180006b44  mov     ecx, r14d; dwErrCode
0x180006b47  call    cs:__imp_SetLastError
0x180006b4d  mov     rcx, [rdi+38h]; pti
0x180006b51  test    rcx, rcx
0x180006b54  jz      short loc_180006B77
0x180006b56  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006b5f  mov     r9d, 4E2h; msWindowLength
0x180006b65  xor     r8d, r8d; msPeriod
0x180006b68  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180006b6d  call    cs:__imp_SetThreadpoolTimer
0x180006b73  mov     byte ptr [rdi+40h], 1
0x180006b77  test    rsi, rsi
0x180006b7a  jz      short loc_180006B86
0x180006b7c  mov     rcx, rsi; SRWLock
0x180006b7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b85  nop
0x180006b86  add     rsp, 38h
0x180006b8a  pop     r15
0x180006b8c  pop     r14
0x180006b8e  pop     rdi
0x180006b8f  pop     rsi
0x180006b90  pop     rbp
0x180006b91  pop     rbx
0x180006b92  retn
```
