# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000eacc`
- end: `0x18000ec67`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014b10`

## callees

- `0x1800038c6`
- `0x180003940`
- `0x18000eacc`
- `0x180015d60`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb8d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000ebca`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000ebca`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ebef`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ec41`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ebef`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ec41`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000eb1c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000eb1c`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ec06`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ec06`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ec53`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ec53`
- `KERNEL32!GetLastError` at `0x18000ebb4`
- `KERNEL32!GetLastError` at `0x18000ebdc`
- `KERNEL32!GetLastError` at `0x18000ebb4`
- `KERNEL32!GetLastError` at `0x18000ebdc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ebfd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ebfd`
- `KERNEL32!SetLastError` at `0x18000ec0e`
- `KERNEL32!SetLastError` at `0x18000ec1b`
- `KERNEL32!SetLastError` at `0x18000ec0e`
- `KERNEL32!SetLastError` at `0x18000ec1b`

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
0x18000eacc  push    rbx
0x18000eace  push    rbp
0x18000eacf  push    rsi
0x18000ead0  push    rdi
0x18000ead1  push    r14
0x18000ead3  push    r15
0x18000ead5  sub     rsp, 38h
0x18000ead9  mov     ebp, r9d
0x18000eadc  movzx   ebx, r8w
0x18000eae0  mov     r14d, edx
0x18000eae3  mov     rdi, rcx
0x18000eae6  cmp     byte ptr [rcx], 0
0x18000eae9  jz      loc_18000EC5A
0x18000eaef  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000eaf6  jnz     loc_18000EC5A
0x18000eafc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000eb03  test    rax, rax
0x18000eb06  jz      short loc_18000EB15
0x18000eb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb0d  test    al, al
0x18000eb0f  jnz     loc_18000EC5A
0x18000eb15  lea     rsi, [rdi+28h]
0x18000eb19  mov     rcx, rsi; SRWLock
0x18000eb1c  call    cs:__imp_AcquireSRWLockExclusive
0x18000eb22  xor     eax, eax
0x18000eb24  mov     word ptr [rsp+68h+var_48+6], ax
0x18000eb29  mov     dword ptr [rsp+68h+var_48], r14d
0x18000eb2e  mov     word ptr [rsp+68h+var_48+4], bx
0x18000eb33  lea     rbx, [rdi+0E8h]
0x18000eb3a  lea     edx, [rax+0Ch]; unsigned __int64
0x18000eb3d  mov     rcx, rbx; this
0x18000eb40  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000eb45  test    al, al
0x18000eb47  jz      short loc_18000EBA3
0x18000eb49  mov     rcx, [rbx+8]; void *
0x18000eb4d  mov     rax, [rbx+10h]
0x18000eb51  sub     rax, rcx
0x18000eb54  cmp     rcx, [rbx+10h]
0x18000eb58  sbb     r8, r8
0x18000eb5b  and     r8, rax; Size
0x18000eb5e  test    rcx, rcx
0x18000eb61  jnz     short loc_18000EB71
0x18000eb63  call    cs:__imp__o__errno
0x18000eb69  mov     dword ptr [rax], 16h
0x18000eb6f  jmp     short loc_18000EB99
0x18000eb71  cmp     r8, 0Ch
0x18000eb75  jb      short loc_18000EB86
0x18000eb77  movsd   xmm0, [rsp+68h+var_48]
0x18000eb7d  movsd   qword ptr [rcx], xmm0
0x18000eb81  mov     [rcx+8], ebp
0x18000eb84  jmp     short loc_18000EB9E
0x18000eb86  xor     edx, edx; Val
0x18000eb88  call    memset_0
0x18000eb8d  call    cs:__imp__o__errno
0x18000eb93  mov     dword ptr [rax], 22h ; '"'
0x18000eb99  call    _invalid_parameter_noinfo
0x18000eb9e  add     qword ptr [rbx+8], 0Ch
0x18000eba3  cmp     byte ptr [rdi+40h], 0
0x18000eba7  jnz     loc_18000EC4B
0x18000ebad  cmp     qword ptr [rdi+38h], 0
0x18000ebb2  jnz     short loc_18000EC21
0x18000ebb4  call    cs:__imp_GetLastError
0x18000ebba  mov     r14d, eax
0x18000ebbd  xor     r8d, r8d; pcbe
0x18000ebc0  mov     rdx, rdi; pv
0x18000ebc3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ebca  call    cs:__imp_CreateThreadpoolTimer
0x18000ebd0  mov     r15, rax
0x18000ebd3  mov     rbp, [rdi+38h]
0x18000ebd7  test    rbp, rbp
0x18000ebda  jz      short loc_18000EC14
0x18000ebdc  call    cs:__imp_GetLastError
0x18000ebe2  mov     ebx, eax
0x18000ebe4  xor     r9d, r9d; msWindowLength
0x18000ebe7  xor     r8d, r8d; msPeriod
0x18000ebea  xor     edx, edx; pftDueTime
0x18000ebec  mov     rcx, rbp; pti
0x18000ebef  call    cs:__imp_SetThreadpoolTimer
0x18000ebf5  mov     edx, 1; fCancelPendingCallbacks
0x18000ebfa  mov     rcx, rbp; pti
0x18000ebfd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ec03  mov     rcx, rbp; pti
0x18000ec06  call    cs:__imp_CloseThreadpoolTimer
0x18000ec0c  mov     ecx, ebx; dwErrCode
0x18000ec0e  call    cs:__imp_SetLastError
0x18000ec14  mov     [rdi+38h], r15
0x18000ec18  mov     ecx, r14d; dwErrCode
0x18000ec1b  call    cs:__imp_SetLastError
0x18000ec21  mov     rcx, [rdi+38h]; pti
0x18000ec25  test    rcx, rcx
0x18000ec28  jz      short loc_18000EC4B
0x18000ec2a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ec33  mov     r9d, 4E2h; msWindowLength
0x18000ec39  xor     r8d, r8d; msPeriod
0x18000ec3c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ec41  call    cs:__imp_SetThreadpoolTimer
0x18000ec47  mov     byte ptr [rdi+40h], 1
0x18000ec4b  test    rsi, rsi
0x18000ec4e  jz      short loc_18000EC5A
0x18000ec50  mov     rcx, rsi; SRWLock
0x18000ec53  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ec59  nop
0x18000ec5a  add     rsp, 38h
0x18000ec5e  pop     r15
0x18000ec60  pop     r14
0x18000ec62  pop     rdi
0x18000ec63  pop     rsi
0x18000ec64  pop     rbp
0x18000ec65  pop     rbx
0x18000ec66  retn
```
