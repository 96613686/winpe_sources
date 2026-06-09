# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007e38`
- end: `0x180007fd3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a810`

## callees

- `0x180002eb2`
- `0x180002efc`
- `0x180007e38`
- `0x18000ae9c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ecf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ef9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ecf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ef9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007fad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007f72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007f69`

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
0x180007e38  push    rbx
0x180007e3a  push    rbp
0x180007e3b  push    rsi
0x180007e3c  push    rdi
0x180007e3d  push    r14
0x180007e3f  push    r15
0x180007e41  sub     rsp, 38h
0x180007e45  mov     ebp, r9d
0x180007e48  movzx   ebx, r8w
0x180007e4c  mov     r14d, edx
0x180007e4f  mov     rdi, rcx
0x180007e52  cmp     byte ptr [rcx], 0
0x180007e55  jz      loc_180007FC6
0x180007e5b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007e62  jnz     loc_180007FC6
0x180007e68  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007e6f  test    rax, rax
0x180007e72  jz      short loc_180007E81
0x180007e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e79  test    al, al
0x180007e7b  jnz     loc_180007FC6
0x180007e81  lea     rsi, [rdi+28h]
0x180007e85  mov     rcx, rsi; SRWLock
0x180007e88  call    cs:__imp_AcquireSRWLockExclusive
0x180007e8e  xor     eax, eax
0x180007e90  mov     word ptr [rsp+68h+var_48+6], ax
0x180007e95  mov     dword ptr [rsp+68h+var_48], r14d
0x180007e9a  mov     word ptr [rsp+68h+var_48+4], bx
0x180007e9f  lea     rbx, [rdi+0E8h]
0x180007ea6  lea     edx, [rax+0Ch]; unsigned __int64
0x180007ea9  mov     rcx, rbx; this
0x180007eac  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007eb1  test    al, al
0x180007eb3  jz      short loc_180007F0F
0x180007eb5  mov     rcx, [rbx+8]; void *
0x180007eb9  mov     rax, [rbx+10h]
0x180007ebd  sub     rax, rcx
0x180007ec0  cmp     rcx, [rbx+10h]
0x180007ec4  sbb     r8, r8
0x180007ec7  and     r8, rax; Size
0x180007eca  test    rcx, rcx
0x180007ecd  jnz     short loc_180007EDD
0x180007ecf  call    cs:__imp__o__errno
0x180007ed5  mov     dword ptr [rax], 16h
0x180007edb  jmp     short loc_180007F05
0x180007edd  cmp     r8, 0Ch
0x180007ee1  jb      short loc_180007EF2
0x180007ee3  movsd   xmm0, [rsp+68h+var_48]
0x180007ee9  movsd   qword ptr [rcx], xmm0
0x180007eed  mov     [rcx+8], ebp
0x180007ef0  jmp     short loc_180007F0A
0x180007ef2  xor     edx, edx; Val
0x180007ef4  call    memset_0
0x180007ef9  call    cs:__imp__o__errno
0x180007eff  mov     dword ptr [rax], 22h ; '"'
0x180007f05  call    _invalid_parameter_noinfo
0x180007f0a  add     qword ptr [rbx+8], 0Ch
0x180007f0f  cmp     byte ptr [rdi+40h], 0
0x180007f13  jnz     loc_180007FB7
0x180007f19  cmp     qword ptr [rdi+38h], 0
0x180007f1e  jnz     short loc_180007F8D
0x180007f20  call    cs:__imp_GetLastError
0x180007f26  mov     r14d, eax
0x180007f29  xor     r8d, r8d; pcbe
0x180007f2c  mov     rdx, rdi; pv
0x180007f2f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007f36  call    cs:__imp_CreateThreadpoolTimer
0x180007f3c  mov     r15, rax
0x180007f3f  mov     rbp, [rdi+38h]
0x180007f43  test    rbp, rbp
0x180007f46  jz      short loc_180007F80
0x180007f48  call    cs:__imp_GetLastError
0x180007f4e  mov     ebx, eax
0x180007f50  xor     r9d, r9d; msWindowLength
0x180007f53  xor     r8d, r8d; msPeriod
0x180007f56  xor     edx, edx; pftDueTime
0x180007f58  mov     rcx, rbp; pti
0x180007f5b  call    cs:__imp_SetThreadpoolTimer
0x180007f61  mov     edx, 1; fCancelPendingCallbacks
0x180007f66  mov     rcx, rbp; pti
0x180007f69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007f6f  mov     rcx, rbp; pti
0x180007f72  call    cs:__imp_CloseThreadpoolTimer
0x180007f78  mov     ecx, ebx; dwErrCode
0x180007f7a  call    cs:__imp_SetLastError
0x180007f80  mov     [rdi+38h], r15
0x180007f84  mov     ecx, r14d; dwErrCode
0x180007f87  call    cs:__imp_SetLastError
0x180007f8d  mov     rcx, [rdi+38h]; pti
0x180007f91  test    rcx, rcx
0x180007f94  jz      short loc_180007FB7
0x180007f96  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180007f9f  mov     r9d, 4E2h; msWindowLength
0x180007fa5  xor     r8d, r8d; msPeriod
0x180007fa8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180007fad  call    cs:__imp_SetThreadpoolTimer
0x180007fb3  mov     byte ptr [rdi+40h], 1
0x180007fb7  test    rsi, rsi
0x180007fba  jz      short loc_180007FC6
0x180007fbc  mov     rcx, rsi; SRWLock
0x180007fbf  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fc5  nop
0x180007fc6  add     rsp, 38h
0x180007fca  pop     r15
0x180007fcc  pop     r14
0x180007fce  pop     rdi
0x180007fcf  pop     rsi
0x180007fd0  pop     rbp
0x180007fd1  pop     rbx
0x180007fd2  retn
```
