# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400058dc`
- end: `0x140005a77`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140007ed0`

## callees

- `0x14000202e`
- `0x1400020d0`
- `0x1400058dc`
- `0x1400084fc`
- `0x14001c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005973`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000599d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005973`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000599d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000592c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000592c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005a63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a2b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400059da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400059da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400059ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400059ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005a51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005a16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005a16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005a0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005a0d`

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
0x1400058dc  push    rbx
0x1400058de  push    rbp
0x1400058df  push    rsi
0x1400058e0  push    rdi
0x1400058e1  push    r14
0x1400058e3  push    r15
0x1400058e5  sub     rsp, 38h
0x1400058e9  mov     ebp, r9d
0x1400058ec  movzx   ebx, r8w
0x1400058f0  mov     r14d, edx
0x1400058f3  mov     rdi, rcx
0x1400058f6  cmp     byte ptr [rcx], 0
0x1400058f9  jz      loc_140005A6A
0x1400058ff  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140005906  jnz     loc_140005A6A
0x14000590c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005913  test    rax, rax
0x140005916  jz      short loc_140005925
0x140005918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000591d  test    al, al
0x14000591f  jnz     loc_140005A6A
0x140005925  lea     rsi, [rdi+28h]
0x140005929  mov     rcx, rsi; SRWLock
0x14000592c  call    cs:__imp_AcquireSRWLockExclusive
0x140005932  xor     eax, eax
0x140005934  mov     word ptr [rsp+68h+var_48+6], ax
0x140005939  mov     dword ptr [rsp+68h+var_48], r14d
0x14000593e  mov     word ptr [rsp+68h+var_48+4], bx
0x140005943  lea     rbx, [rdi+0E8h]
0x14000594a  lea     edx, [rax+0Ch]; unsigned __int64
0x14000594d  mov     rcx, rbx; this
0x140005950  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140005955  test    al, al
0x140005957  jz      short loc_1400059B3
0x140005959  mov     rcx, [rbx+8]; void *
0x14000595d  mov     rax, [rbx+10h]
0x140005961  sub     rax, rcx
0x140005964  cmp     rcx, [rbx+10h]
0x140005968  sbb     r8, r8
0x14000596b  and     r8, rax; Size
0x14000596e  test    rcx, rcx
0x140005971  jnz     short loc_140005981
0x140005973  call    cs:__imp__o__errno
0x140005979  mov     dword ptr [rax], 16h
0x14000597f  jmp     short loc_1400059A9
0x140005981  cmp     r8, 0Ch
0x140005985  jb      short loc_140005996
0x140005987  movsd   xmm0, [rsp+68h+var_48]
0x14000598d  movsd   qword ptr [rcx], xmm0
0x140005991  mov     [rcx+8], ebp
0x140005994  jmp     short loc_1400059AE
0x140005996  xor     edx, edx; Val
0x140005998  call    memset_0
0x14000599d  call    cs:__imp__o__errno
0x1400059a3  mov     dword ptr [rax], 22h ; '"'
0x1400059a9  call    _invalid_parameter_noinfo
0x1400059ae  add     qword ptr [rbx+8], 0Ch
0x1400059b3  cmp     byte ptr [rdi+40h], 0
0x1400059b7  jnz     loc_140005A5B
0x1400059bd  cmp     qword ptr [rdi+38h], 0
0x1400059c2  jnz     short loc_140005A31
0x1400059c4  call    cs:__imp_GetLastError
0x1400059ca  mov     r14d, eax
0x1400059cd  xor     r8d, r8d; pcbe
0x1400059d0  mov     rdx, rdi; pv
0x1400059d3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400059da  call    cs:__imp_CreateThreadpoolTimer
0x1400059e0  mov     r15, rax
0x1400059e3  mov     rbp, [rdi+38h]
0x1400059e7  test    rbp, rbp
0x1400059ea  jz      short loc_140005A24
0x1400059ec  call    cs:__imp_GetLastError
0x1400059f2  mov     ebx, eax
0x1400059f4  xor     r9d, r9d; msWindowLength
0x1400059f7  xor     r8d, r8d; msPeriod
0x1400059fa  xor     edx, edx; pftDueTime
0x1400059fc  mov     rcx, rbp; pti
0x1400059ff  call    cs:__imp_SetThreadpoolTimer
0x140005a05  mov     edx, 1; fCancelPendingCallbacks
0x140005a0a  mov     rcx, rbp; pti
0x140005a0d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005a13  mov     rcx, rbp; pti
0x140005a16  call    cs:__imp_CloseThreadpoolTimer
0x140005a1c  mov     ecx, ebx; dwErrCode
0x140005a1e  call    cs:__imp_SetLastError
0x140005a24  mov     [rdi+38h], r15
0x140005a28  mov     ecx, r14d; dwErrCode
0x140005a2b  call    cs:__imp_SetLastError
0x140005a31  mov     rcx, [rdi+38h]; pti
0x140005a35  test    rcx, rcx
0x140005a38  jz      short loc_140005A5B
0x140005a3a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140005a43  mov     r9d, 4E2h; msWindowLength
0x140005a49  xor     r8d, r8d; msPeriod
0x140005a4c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140005a51  call    cs:__imp_SetThreadpoolTimer
0x140005a57  mov     byte ptr [rdi+40h], 1
0x140005a5b  test    rsi, rsi
0x140005a5e  jz      short loc_140005A6A
0x140005a60  mov     rcx, rsi; SRWLock
0x140005a63  call    cs:__imp_ReleaseSRWLockExclusive
0x140005a69  nop
0x140005a6a  add     rsp, 38h
0x140005a6e  pop     r15
0x140005a70  pop     r14
0x140005a72  pop     rdi
0x140005a73  pop     rsi
0x140005a74  pop     rbp
0x140005a75  pop     rbx
0x140005a76  retn
```
