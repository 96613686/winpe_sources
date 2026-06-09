# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000acdc`
- end: `0x18000ae77`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f7e0`

## callees

- `0x180002ea2`
- `0x180002ef8`
- `0x18000acdc`
- `0x18000fc94`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad73`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad73`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ae16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ae16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000adff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000adff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000adda`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000adda`

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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
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
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000acdc  push    rbx
0x18000acde  push    rbp
0x18000acdf  push    rsi
0x18000ace0  push    rdi
0x18000ace1  push    r14
0x18000ace3  push    r15
0x18000ace5  sub     rsp, 38h
0x18000ace9  mov     ebp, r9d
0x18000acec  movzx   ebx, r8w
0x18000acf0  mov     r14d, edx
0x18000acf3  mov     rdi, rcx
0x18000acf6  cmp     byte ptr [rcx], 0
0x18000acf9  jz      loc_18000AE6A
0x18000acff  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ad06  jnz     loc_18000AE6A
0x18000ad0c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ad13  test    rax, rax
0x18000ad16  jz      short loc_18000AD25
0x18000ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1d  test    al, al
0x18000ad1f  jnz     loc_18000AE6A
0x18000ad25  lea     rsi, [rdi+28h]
0x18000ad29  mov     rcx, rsi; SRWLock
0x18000ad2c  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad32  xor     eax, eax
0x18000ad34  mov     word ptr [rsp+68h+var_48+6], ax
0x18000ad39  mov     dword ptr [rsp+68h+var_48], r14d
0x18000ad3e  mov     word ptr [rsp+68h+var_48+4], bx
0x18000ad43  lea     rbx, [rdi+0E8h]
0x18000ad4a  lea     edx, [rax+0Ch]; unsigned __int64
0x18000ad4d  mov     rcx, rbx; this
0x18000ad50  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ad55  test    al, al
0x18000ad57  jz      short loc_18000ADB3
0x18000ad59  mov     rcx, [rbx+8]; void *
0x18000ad5d  mov     rax, [rbx+10h]
0x18000ad61  sub     rax, rcx
0x18000ad64  cmp     rcx, [rbx+10h]
0x18000ad68  sbb     r8, r8
0x18000ad6b  and     r8, rax; Size
0x18000ad6e  test    rcx, rcx
0x18000ad71  jnz     short loc_18000AD81
0x18000ad73  call    cs:__imp__o__errno
0x18000ad79  mov     dword ptr [rax], 16h
0x18000ad7f  jmp     short loc_18000ADA9
0x18000ad81  cmp     r8, 0Ch
0x18000ad85  jb      short loc_18000AD96
0x18000ad87  movsd   xmm0, [rsp+68h+var_48]
0x18000ad8d  movsd   qword ptr [rcx], xmm0
0x18000ad91  mov     [rcx+8], ebp
0x18000ad94  jmp     short loc_18000ADAE
0x18000ad96  xor     edx, edx; Val
0x18000ad98  call    memset_0
0x18000ad9d  call    cs:__imp__o__errno
0x18000ada3  mov     dword ptr [rax], 22h ; '"'
0x18000ada9  call    _invalid_parameter_noinfo
0x18000adae  add     qword ptr [rbx+8], 0Ch
0x18000adb3  cmp     byte ptr [rdi+40h], 0
0x18000adb7  jnz     loc_18000AE5B
0x18000adbd  cmp     qword ptr [rdi+38h], 0
0x18000adc2  jnz     short loc_18000AE31
0x18000adc4  call    cs:__imp_GetLastError
0x18000adca  mov     r14d, eax
0x18000adcd  xor     r8d, r8d; pcbe
0x18000add0  mov     rdx, rdi; pv
0x18000add3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000adda  call    cs:__imp_CreateThreadpoolTimer
0x18000ade0  mov     r15, rax
0x18000ade3  mov     rbp, [rdi+38h]
0x18000ade7  test    rbp, rbp
0x18000adea  jz      short loc_18000AE24
0x18000adec  call    cs:__imp_GetLastError
0x18000adf2  mov     ebx, eax
0x18000adf4  xor     r9d, r9d; msWindowLength
0x18000adf7  xor     r8d, r8d; msPeriod
0x18000adfa  xor     edx, edx; pftDueTime
0x18000adfc  mov     rcx, rbp; pti
0x18000adff  call    cs:__imp_SetThreadpoolTimer
0x18000ae05  mov     edx, 1; fCancelPendingCallbacks
0x18000ae0a  mov     rcx, rbp; pti
0x18000ae0d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ae13  mov     rcx, rbp; pti
0x18000ae16  call    cs:__imp_CloseThreadpoolTimer
0x18000ae1c  mov     ecx, ebx; dwErrCode
0x18000ae1e  call    cs:__imp_SetLastError
0x18000ae24  mov     [rdi+38h], r15
0x18000ae28  mov     ecx, r14d; dwErrCode
0x18000ae2b  call    cs:__imp_SetLastError
0x18000ae31  mov     rcx, [rdi+38h]; pti
0x18000ae35  test    rcx, rcx
0x18000ae38  jz      short loc_18000AE5B
0x18000ae3a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ae43  mov     r9d, 4E2h; msWindowLength
0x18000ae49  xor     r8d, r8d; msPeriod
0x18000ae4c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ae51  call    cs:__imp_SetThreadpoolTimer
0x18000ae57  mov     byte ptr [rdi+40h], 1
0x18000ae5b  test    rsi, rsi
0x18000ae5e  jz      short loc_18000AE6A
0x18000ae60  mov     rcx, rsi; SRWLock
0x18000ae63  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae69  nop
0x18000ae6a  add     rsp, 38h
0x18000ae6e  pop     r15
0x18000ae70  pop     r14
0x18000ae72  pop     rdi
0x18000ae73  pop     rsi
0x18000ae74  pop     rbp
0x18000ae75  pop     rbx
0x18000ae76  retn
```
