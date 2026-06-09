# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008f44`
- end: `0x1800090df`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b8e0`

## callees

- `0x180003b36`
- `0x180003bc8`
- `0x180008f44`
- `0x18000bf4c`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fdb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009005`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fdb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009005`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009086`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009093`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009086`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000902c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000902c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009054`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009067`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009067`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009042`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009042`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000907e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000907e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009075`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009075`

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
                          `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x180008f44  push    rbx
0x180008f46  push    rbp
0x180008f47  push    rsi
0x180008f48  push    rdi
0x180008f49  push    r14
0x180008f4b  push    r15
0x180008f4d  sub     rsp, 38h
0x180008f51  mov     ebp, r9d
0x180008f54  movzx   ebx, r8w
0x180008f58  mov     r14d, edx
0x180008f5b  mov     rdi, rcx
0x180008f5e  cmp     byte ptr [rcx], 0
0x180008f61  jz      loc_1800090D2
0x180008f67  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008f6e  jnz     loc_1800090D2
0x180008f74  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008f7b  test    rax, rax
0x180008f7e  jz      short loc_180008F8D
0x180008f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f85  test    al, al
0x180008f87  jnz     loc_1800090D2
0x180008f8d  lea     rsi, [rdi+28h]
0x180008f91  mov     rcx, rsi; SRWLock
0x180008f94  call    cs:__imp_AcquireSRWLockExclusive
0x180008f9a  xor     eax, eax
0x180008f9c  mov     word ptr [rsp+68h+var_48+6], ax
0x180008fa1  mov     dword ptr [rsp+68h+var_48], r14d
0x180008fa6  mov     word ptr [rsp+68h+var_48+4], bx
0x180008fab  lea     rbx, [rdi+0E8h]
0x180008fb2  lea     edx, [rax+0Ch]; unsigned __int64
0x180008fb5  mov     rcx, rbx; this
0x180008fb8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008fbd  test    al, al
0x180008fbf  jz      short loc_18000901B
0x180008fc1  mov     rcx, [rbx+8]; void *
0x180008fc5  mov     rax, [rbx+10h]
0x180008fc9  sub     rax, rcx
0x180008fcc  cmp     rcx, [rbx+10h]
0x180008fd0  sbb     r8, r8
0x180008fd3  and     r8, rax; Size
0x180008fd6  test    rcx, rcx
0x180008fd9  jnz     short loc_180008FE9
0x180008fdb  call    cs:__imp__o__errno
0x180008fe1  mov     dword ptr [rax], 16h
0x180008fe7  jmp     short loc_180009011
0x180008fe9  cmp     r8, 0Ch
0x180008fed  jb      short loc_180008FFE
0x180008fef  movsd   xmm0, [rsp+68h+var_48]
0x180008ff5  movsd   qword ptr [rcx], xmm0
0x180008ff9  mov     [rcx+8], ebp
0x180008ffc  jmp     short loc_180009016
0x180008ffe  xor     edx, edx; Val
0x180009000  call    memset_0
0x180009005  call    cs:__imp__o__errno
0x18000900b  mov     dword ptr [rax], 22h ; '"'
0x180009011  call    _invalid_parameter_noinfo
0x180009016  add     qword ptr [rbx+8], 0Ch
0x18000901b  cmp     byte ptr [rdi+40h], 0
0x18000901f  jnz     loc_1800090C3
0x180009025  cmp     qword ptr [rdi+38h], 0
0x18000902a  jnz     short loc_180009099
0x18000902c  call    cs:__imp_GetLastError
0x180009032  mov     r14d, eax
0x180009035  xor     r8d, r8d; pcbe
0x180009038  mov     rdx, rdi; pv
0x18000903b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009042  call    cs:__imp_CreateThreadpoolTimer
0x180009048  mov     r15, rax
0x18000904b  mov     rbp, [rdi+38h]
0x18000904f  test    rbp, rbp
0x180009052  jz      short loc_18000908C
0x180009054  call    cs:__imp_GetLastError
0x18000905a  mov     ebx, eax
0x18000905c  xor     r9d, r9d; msWindowLength
0x18000905f  xor     r8d, r8d; msPeriod
0x180009062  xor     edx, edx; pftDueTime
0x180009064  mov     rcx, rbp; pti
0x180009067  call    cs:__imp_SetThreadpoolTimer
0x18000906d  mov     edx, 1; fCancelPendingCallbacks
0x180009072  mov     rcx, rbp; pti
0x180009075  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000907b  mov     rcx, rbp; pti
0x18000907e  call    cs:__imp_CloseThreadpoolTimer
0x180009084  mov     ecx, ebx; dwErrCode
0x180009086  call    cs:__imp_SetLastError
0x18000908c  mov     [rdi+38h], r15
0x180009090  mov     ecx, r14d; dwErrCode
0x180009093  call    cs:__imp_SetLastError
0x180009099  mov     rcx, [rdi+38h]; pti
0x18000909d  test    rcx, rcx
0x1800090a0  jz      short loc_1800090C3
0x1800090a2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800090ab  mov     r9d, 4E2h; msWindowLength
0x1800090b1  xor     r8d, r8d; msPeriod
0x1800090b4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800090b9  call    cs:__imp_SetThreadpoolTimer
0x1800090bf  mov     byte ptr [rdi+40h], 1
0x1800090c3  test    rsi, rsi
0x1800090c6  jz      short loc_1800090D2
0x1800090c8  mov     rcx, rsi; SRWLock
0x1800090cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090d1  nop
0x1800090d2  add     rsp, 38h
0x1800090d6  pop     r15
0x1800090d8  pop     r14
0x1800090da  pop     rdi
0x1800090db  pop     rsi
0x1800090dc  pop     rbp
0x1800090dd  pop     rbx
0x1800090de  retn
```
