# CSOperationDispatcher::Enqueue(std::function<void (void)>)

- ea: `0x180020660`
- end: `0x18002094d`
- name: `?Enqueue@CSOperationDispatcher@@QEAA?AV?$shared_ptr@VWaitableOperation@@@std@@V?$function@$$A6AXXZ@3@@Z`
- size: `749`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `7`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180020ce0`
- `0x1800223d0`
- `0x180023010`
- `0x180025b08`
- `0x180025d28`
- `0x180025dec`
- `0x180026b90`

## callees

- `0x1800139d0`
- `0x180013a74`
- `0x18001de80`
- `0x18001e62c`
- `0x18001e6f4`
- `0x18001e84c`
- `0x180020660`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800206bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800206bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800208a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800208a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800207b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020909`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800207b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020909`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800207f9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800207f9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020750`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020750`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002088e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002088e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CSOperationDispatcher::Enqueue(char *pv, _QWORD *a2, __int64 a3)
{
  __int64 v3; // r13
  _QWORD *v4; // r14
  RTL_SRWLOCK *v6; // r12
  __int64 v7; // rax
  volatile signed __int32 *v8; // r15
  __int64 v9; // rdx
  const char *v10; // r9
  __int64 v11; // rax
  volatile signed __int32 *v12; // rsi
  RTL_SRWLOCK *v13; // r12
  __int64 v14; // rax
  volatile signed __int32 *v15; // r15
  __int64 v16; // rax
  volatile signed __int32 *v17; // rsi
  __int64 v18; // rcx
  char v20[8]; // [rsp+38h] [rbp-40h] BYREF
  volatile signed __int32 *v21; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  *a2 = 0;
  a2[1] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
  {
    v6 = (RTL_SRWLOCK *)(pv + 48);
    AcquireSRWLockExclusive((PSRWLOCK)pv + 6);
    try
    {
      if ( pv[57] )
      {
        v11 = std::make_shared<EmptyWaitableOperation,>(v20);
        std::shared_ptr<WaitableOperation>::operator=(v4, v11);
        v12 = v21;
        if ( v21 )
        {
          if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
      }
      else
      {
        v7 = std::make_shared<WaitableOperation,std::function<void (void)> &>(v20, v3);
        std::shared_ptr<WaitableOperation>::operator=(v4, v7);
        v8 = v21;
        if ( v21 )
        {
          if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
            if ( !_InterlockedDecrement(v8 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
          }
        }
        std::queue<std::shared_ptr<WaitableOperation>>::emplace<std::shared_ptr<WaitableOperation> &>(pv + 8, v4);
        if ( !pv[56] && CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated((struct _TP_WORK **)pv) )
        {
          SubmitThreadpoolWork(*(PTP_WORK *)pv);
          pv[56] = 1;
        }
      }
      if ( v6 )
        ReleaseSRWLockExclusive(v6);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\Utils.h",
        v10);
      v3 = a3;
      v4 = a2;
    }
  }
  else
  {
    v13 = (RTL_SRWLOCK *)(pv + 48);
    AcquireSRWLockExclusive((PSRWLOCK)pv + 6);
    if ( pv[57] )
    {
      v16 = std::make_shared<EmptyWaitableOperation,>(v20);
      std::shared_ptr<WaitableOperation>::operator=(v4, v16);
      v17 = v21;
      if ( v21 )
      {
        if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
    }
    else
    {
      ResetEvent(*((HANDLE *)pv + 8));
      v14 = std::make_shared<WaitableOperation,std::function<void (void)> &>(v20, v3);
      std::shared_ptr<WaitableOperation>::operator=(v4, v14);
      v15 = v21;
      if ( v21 )
      {
        if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( !_InterlockedDecrement(v15 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      std::queue<std::shared_ptr<WaitableOperation>>::emplace<std::shared_ptr<WaitableOperation> &>(pv + 8, v4);
      if ( !pv[56] )
      {
        if ( CreateThread(0, 0, CSOperationDispatcher::ThreadThunk, pv, 0, (LPDWORD)pv + 18) )
          pv[56] = 1;
        else
          SetEvent(*((HANDLE *)pv + 8));
      }
    }
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
  }
  v18 = *(_QWORD *)(v3 + 56);
  if ( v18 )
  {
    LOBYTE(v9) = v18 != v3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 32LL))(v18, v9);
    *(_QWORD *)(v3 + 56) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180020660  mov     rax, rsp
0x180020663  mov     [rax+8], rsi
0x180020667  mov     [rax+18h], r8
0x18002066b  mov     [rax+10h], rdx
0x18002066f  push    rdi
0x180020670  push    r12
0x180020672  push    r13
0x180020674  push    r14
0x180020676  push    r15
0x180020678  sub     rsp, 50h
0x18002067c  mov     r13, r8
0x18002067f  mov     r14, rdx
0x180020682  mov     rsi, rcx
0x180020685  mov     dword ptr [rax-48h], 0
0x18002068c  mov     qword ptr [rdx], 0
0x180020693  mov     qword ptr [rdx+8], 0
0x18002069b  mov     dword ptr [rax-48h], 1
0x1800206a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x1800206a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x1800206ae  test    al, al
0x1800206b0  jz      loc_1800207D6
0x1800206b6  lea     r12, [rsi+30h]
0x1800206ba  mov     rcx, r12; SRWLock
0x1800206bd  call    cs:__imp_AcquireSRWLockExclusive
0x1800206c3  mov     [rsp+78h+arg_18], r12
0x1800206cb  lea     rcx, [rsp+78h+var_40]
0x1800206d0  cmp     byte ptr [rsi+39h], 0
0x1800206d4  jnz     loc_18002075C
0x1800206da  mov     rdx, r13
0x1800206dd  call    ??$make_shared@VWaitableOperation@@AEAV?$function@$$A6AXXZ@std@@@std@@YA?AV?$shared_ptr@VWaitableOperation@@@0@AEAV?$function@$$A6AXXZ@0@@Z; std::make_shared<WaitableOperation,std::function<void (void)> &>(std::function<void (void)> &)
0x1800206e2  mov     rdx, rax
0x1800206e5  mov     rcx, r14
0x1800206e8  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x1800206ed  mov     r15, [rsp+78h+var_38]
0x1800206f2  test    r15, r15
0x1800206f5  jz      short loc_18002072F
0x1800206f7  or      edi, 0FFFFFFFFh
0x1800206fa  mov     eax, edi
0x1800206fc  lock xadd [r15+8], eax
0x180020702  add     eax, edi
0x180020704  jnz     short loc_18002072F
0x180020706  mov     rax, [r15]
0x180020709  mov     rcx, r15
0x18002070c  mov     rax, [rax]
0x18002070f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020714  mov     eax, edi
0x180020716  lock xadd [r15+0Ch], eax
0x18002071c  add     eax, edi
0x18002071e  jnz     short loc_18002072F
0x180020720  mov     rax, [r15]
0x180020723  mov     rcx, r15
0x180020726  mov     rax, [rax+8]
0x18002072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072f  lea     rcx, [rsi+8]
0x180020733  mov     rdx, r14
0x180020736  call    ??$emplace@AEAV?$shared_ptr@VWaitableOperation@@@std@@@?$queue@V?$shared_ptr@VWaitableOperation@@@std@@V?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@2@@std@@QEAA?A_TAEAV?$shared_ptr@VWaitableOperation@@@1@@Z
0x18002073b  cmp     byte ptr [rsi+38h], 0
0x18002073f  jnz     short loc_1800207AD
0x180020741  mov     rcx, rsi; pv
0x180020744  call    ?_TryEnsureThreadpoolWorkCreated@CSOperationDispatcher@@AEAA_NXZ; CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(void)
0x180020749  test    al, al
0x18002074b  jz      short loc_1800207AD
0x18002074d  mov     rcx, [rsi]; pwk
0x180020750  call    cs:__imp_SubmitThreadpoolWork
0x180020756  mov     byte ptr [rsi+38h], 1
0x18002075a  jmp     short loc_1800207AD
0x18002075c  call    ??$make_shared@VEmptyWaitableOperation@@$$V@std@@YA?AV?$shared_ptr@VEmptyWaitableOperation@@@0@XZ; std::make_shared<EmptyWaitableOperation,>(void)
0x180020761  mov     rdx, rax
0x180020764  mov     rcx, r14
0x180020767  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x18002076c  mov     rsi, [rsp+78h+var_38]
0x180020771  test    rsi, rsi
0x180020774  jz      short loc_1800207AD
0x180020776  or      edi, 0FFFFFFFFh
0x180020779  mov     eax, edi
0x18002077b  lock xadd [rsi+8], eax
0x180020780  add     eax, edi
0x180020782  jnz     short loc_1800207AD
0x180020784  mov     rax, [rsi]
0x180020787  mov     rcx, rsi
0x18002078a  mov     rax, [rax]
0x18002078d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020792  mov     eax, edi
0x180020794  lock xadd [rsi+0Ch], eax
0x180020799  add     eax, edi
0x18002079b  jnz     short loc_1800207AD
0x18002079d  mov     rax, [rsi]
0x1800207a0  mov     rcx, rsi
0x1800207a3  mov     rax, [rax+8]
0x1800207a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207ac  nop
0x1800207ad  test    r12, r12
0x1800207b0  jz      short loc_1800207BC
0x1800207b2  mov     rcx, r12; SRWLock
0x1800207b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800207bb  nop
0x1800207bc  jmp     loc_180020910
0x1800207c1  mov     r13, [rsp+78h+arg_10]
0x1800207c9  mov     r14, [rsp+78h+arg_8]
0x1800207d1  jmp     loc_180020910
0x1800207d6  lea     r12, [rsi+30h]
0x1800207da  mov     rcx, r12; SRWLock
0x1800207dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800207e3  mov     [rsp+78h+arg_18], r12
0x1800207eb  cmp     byte ptr [rsi+39h], 0
0x1800207ef  jnz     loc_1800208AB
0x1800207f5  mov     rcx, [rsi+40h]; hEvent
0x1800207f9  call    cs:__imp_ResetEvent
0x1800207ff  mov     rdx, r13
0x180020802  lea     rcx, [rsp+78h+var_40]
0x180020807  call    ??$make_shared@VWaitableOperation@@AEAV?$function@$$A6AXXZ@std@@@std@@YA?AV?$shared_ptr@VWaitableOperation@@@0@AEAV?$function@$$A6AXXZ@0@@Z; std::make_shared<WaitableOperation,std::function<void (void)> &>(std::function<void (void)> &)
0x18002080c  mov     rdx, rax
0x18002080f  mov     rcx, r14
0x180020812  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x180020817  mov     r15, [rsp+78h+var_38]
0x18002081c  test    r15, r15
0x18002081f  jz      short loc_180020859
0x180020821  or      edi, 0FFFFFFFFh
0x180020824  mov     eax, edi
0x180020826  lock xadd [r15+8], eax
0x18002082c  add     eax, edi
0x18002082e  jnz     short loc_180020859
0x180020830  mov     rax, [r15]
0x180020833  mov     rcx, r15
0x180020836  mov     rax, [rax]
0x180020839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002083e  mov     eax, edi
0x180020840  lock xadd [r15+0Ch], eax
0x180020846  add     eax, edi
0x180020848  jnz     short loc_180020859
0x18002084a  mov     rax, [r15]
0x18002084d  mov     rcx, r15
0x180020850  mov     rax, [rax+8]
0x180020854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020859  lea     rcx, [rsi+8]
0x18002085d  mov     rdx, r14
0x180020860  call    ??$emplace@AEAV?$shared_ptr@VWaitableOperation@@@std@@@?$queue@V?$shared_ptr@VWaitableOperation@@@std@@V?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@2@@std@@QEAA?A_TAEAV?$shared_ptr@VWaitableOperation@@@1@@Z
0x180020865  cmp     byte ptr [rsi+38h], 0
0x180020869  jnz     loc_180020901
0x18002086f  lea     rax, [rsi+48h]
0x180020873  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180020878  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180020880  mov     r9, rsi; lpParameter
0x180020883  lea     r8, ?ThreadThunk@CSOperationDispatcher@@SAKPEAX@Z; lpStartAddress
0x18002088a  xor     edx, edx; dwStackSize
0x18002088c  xor     ecx, ecx; lpThreadAttributes
0x18002088e  call    cs:__imp_CreateThread
0x180020894  test    rax, rax
0x180020897  jz      short loc_18002089F
0x180020899  mov     byte ptr [rsi+38h], 1
0x18002089d  jmp     short loc_180020901
0x18002089f  mov     rcx, [rsi+40h]; hEvent
0x1800208a3  call    cs:__imp_SetEvent
0x1800208a9  jmp     short loc_180020901
0x1800208ab  lea     rcx, [rsp+78h+var_40]
0x1800208b0  call    ??$make_shared@VEmptyWaitableOperation@@$$V@std@@YA?AV?$shared_ptr@VEmptyWaitableOperation@@@0@XZ; std::make_shared<EmptyWaitableOperation,>(void)
0x1800208b5  mov     rdx, rax
0x1800208b8  mov     rcx, r14
0x1800208bb  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x1800208c0  mov     rsi, [rsp+78h+var_38]
0x1800208c5  test    rsi, rsi
0x1800208c8  jz      short loc_180020901
0x1800208ca  or      edi, 0FFFFFFFFh
0x1800208cd  mov     eax, edi
0x1800208cf  lock xadd [rsi+8], eax
0x1800208d4  add     eax, edi
0x1800208d6  jnz     short loc_180020901
0x1800208d8  mov     rax, [rsi]
0x1800208db  mov     rcx, rsi
0x1800208de  mov     rax, [rax]
0x1800208e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208e6  mov     eax, edi
0x1800208e8  lock xadd [rsi+0Ch], eax
0x1800208ed  add     eax, edi
0x1800208ef  jnz     short loc_180020901
0x1800208f1  mov     rax, [rsi]
0x1800208f4  mov     rcx, rsi
0x1800208f7  mov     rax, [rax+8]
0x1800208fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020900  nop
0x180020901  test    r12, r12
0x180020904  jz      short loc_180020910
0x180020906  mov     rcx, r12; SRWLock
0x180020909  call    cs:__imp_ReleaseSRWLockExclusive
0x18002090f  nop
0x180020910  mov     rcx, [r13+38h]
0x180020914  test    rcx, rcx
0x180020917  jz      short loc_180020933
0x180020919  mov     rax, [rcx]
0x18002091c  cmp     rcx, r13
0x18002091f  setnz   dl
0x180020922  mov     rax, [rax+20h]
0x180020926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002092b  mov     qword ptr [r13+38h], 0
0x180020933  mov     rax, r14
0x180020936  mov     rsi, [rsp+78h+arg_0]
0x18002093e  add     rsp, 50h
0x180020942  pop     r15
0x180020944  pop     r14
0x180020946  pop     r13
0x180020948  pop     r12
0x18002094a  pop     rdi
0x18002094b  retn
```
