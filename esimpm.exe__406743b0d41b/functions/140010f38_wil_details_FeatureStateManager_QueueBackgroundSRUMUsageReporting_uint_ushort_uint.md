# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140010f38`
- end: `0x1400110d3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140013840`

## callees

- `0x140003a6e`
- `0x140003b28`
- `0x140010f38`
- `0x140013f7c`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010fcf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010ff9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010fcf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400110bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400110bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010f88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011048`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001107a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011087`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001107a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011087`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140011036`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140011036`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140011072`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140011072`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140011069`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140011069`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001105b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400110ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001105b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400110ad`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x140010f38  push    rbx
0x140010f3a  push    rbp
0x140010f3b  push    rsi
0x140010f3c  push    rdi
0x140010f3d  push    r14
0x140010f3f  push    r15
0x140010f41  sub     rsp, 38h
0x140010f45  mov     ebp, r9d
0x140010f48  movzx   ebx, r8w
0x140010f4c  mov     r14d, edx
0x140010f4f  mov     rdi, rcx
0x140010f52  cmp     byte ptr [rcx], 0
0x140010f55  jz      loc_1400110C6
0x140010f5b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010f62  jnz     loc_1400110C6
0x140010f68  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010f6f  test    rax, rax
0x140010f72  jz      short loc_140010F81
0x140010f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f79  test    al, al
0x140010f7b  jnz     loc_1400110C6
0x140010f81  lea     rsi, [rdi+28h]
0x140010f85  mov     rcx, rsi; SRWLock
0x140010f88  call    cs:__imp_AcquireSRWLockExclusive
0x140010f8e  xor     eax, eax
0x140010f90  mov     word ptr [rsp+68h+var_48+6], ax
0x140010f95  mov     dword ptr [rsp+68h+var_48], r14d
0x140010f9a  mov     word ptr [rsp+68h+var_48+4], bx
0x140010f9f  lea     rbx, [rdi+0E8h]
0x140010fa6  lea     edx, [rax+0Ch]; unsigned __int64
0x140010fa9  mov     rcx, rbx; this
0x140010fac  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140010fb1  test    al, al
0x140010fb3  jz      short loc_14001100F
0x140010fb5  mov     rcx, [rbx+8]; void *
0x140010fb9  mov     rax, [rbx+10h]
0x140010fbd  sub     rax, rcx
0x140010fc0  cmp     rcx, [rbx+10h]
0x140010fc4  sbb     r8, r8
0x140010fc7  and     r8, rax; Size
0x140010fca  test    rcx, rcx
0x140010fcd  jnz     short loc_140010FDD
0x140010fcf  call    cs:__imp__o__errno
0x140010fd5  mov     dword ptr [rax], 16h
0x140010fdb  jmp     short loc_140011005
0x140010fdd  cmp     r8, 0Ch
0x140010fe1  jb      short loc_140010FF2
0x140010fe3  movsd   xmm0, [rsp+68h+var_48]
0x140010fe9  movsd   qword ptr [rcx], xmm0
0x140010fed  mov     [rcx+8], ebp
0x140010ff0  jmp     short loc_14001100A
0x140010ff2  xor     edx, edx; Val
0x140010ff4  call    memset_0
0x140010ff9  call    cs:__imp__o__errno
0x140010fff  mov     dword ptr [rax], 22h ; '"'
0x140011005  call    _invalid_parameter_noinfo
0x14001100a  add     qword ptr [rbx+8], 0Ch
0x14001100f  cmp     byte ptr [rdi+40h], 0
0x140011013  jnz     loc_1400110B7
0x140011019  cmp     qword ptr [rdi+38h], 0
0x14001101e  jnz     short loc_14001108D
0x140011020  call    cs:__imp_GetLastError
0x140011026  mov     r14d, eax
0x140011029  xor     r8d, r8d; pcbe
0x14001102c  mov     rdx, rdi; pv
0x14001102f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140011036  call    cs:__imp_CreateThreadpoolTimer
0x14001103c  mov     r15, rax
0x14001103f  mov     rbp, [rdi+38h]
0x140011043  test    rbp, rbp
0x140011046  jz      short loc_140011080
0x140011048  call    cs:__imp_GetLastError
0x14001104e  mov     ebx, eax
0x140011050  xor     r9d, r9d; msWindowLength
0x140011053  xor     r8d, r8d; msPeriod
0x140011056  xor     edx, edx; pftDueTime
0x140011058  mov     rcx, rbp; pti
0x14001105b  call    cs:__imp_SetThreadpoolTimer
0x140011061  mov     edx, 1; fCancelPendingCallbacks
0x140011066  mov     rcx, rbp; pti
0x140011069  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001106f  mov     rcx, rbp; pti
0x140011072  call    cs:__imp_CloseThreadpoolTimer
0x140011078  mov     ecx, ebx; dwErrCode
0x14001107a  call    cs:__imp_SetLastError
0x140011080  mov     [rdi+38h], r15
0x140011084  mov     ecx, r14d; dwErrCode
0x140011087  call    cs:__imp_SetLastError
0x14001108d  mov     rcx, [rdi+38h]; pti
0x140011091  test    rcx, rcx
0x140011094  jz      short loc_1400110B7
0x140011096  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14001109f  mov     r9d, 4E2h; msWindowLength
0x1400110a5  xor     r8d, r8d; msPeriod
0x1400110a8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1400110ad  call    cs:__imp_SetThreadpoolTimer
0x1400110b3  mov     byte ptr [rdi+40h], 1
0x1400110b7  test    rsi, rsi
0x1400110ba  jz      short loc_1400110C6
0x1400110bc  mov     rcx, rsi; SRWLock
0x1400110bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1400110c5  nop
0x1400110c6  add     rsp, 38h
0x1400110ca  pop     r15
0x1400110cc  pop     r14
0x1400110ce  pop     rdi
0x1400110cf  pop     rsi
0x1400110d0  pop     rbp
0x1400110d1  pop     rbx
0x1400110d2  retn
```
