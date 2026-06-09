# CSOperationDispatcher::Enqueue(uchar *,unsigned __int64,std::function<void (uchar *,unsigned __int64)>)

- ea: `0x180020354`
- end: `0x180020658`
- name: `?Enqueue@CSOperationDispatcher@@QEAA?AV?$shared_ptr@VWaitableOperation@@@std@@PEAE_KV?$function@$$A6AXPEAE_K@Z@3@@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800285d0`

## callees

- `0x1800139d0`
- `0x180013a74`
- `0x18001de80`
- `0x18001e62c`
- `0x18001e6f4`
- `0x18001e790`
- `0x180020354`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800203ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800203ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800205af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800205af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800204b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800204b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020615`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800204f0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800204f0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020452`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180020452`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002059a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002059a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *CSOperationDispatcher::Enqueue(char *pv, _QWORD *a2, ...)
{
  _QWORD *v2; // r14
  RTL_SRWLOCK *v4; // r12
  __int64 v5; // rax
  volatile signed __int32 *v6; // r15
  __int64 v7; // rdx
  const char *v8; // r9
  __int64 v9; // rax
  volatile signed __int32 *v10; // rsi
  RTL_SRWLOCK *v11; // r12
  __int64 v12; // rax
  volatile signed __int32 *v13; // r15
  __int64 v14; // rax
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // rcx
  char v19[8]; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int32 *v20; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v24; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+90h] [rbp+18h]
  __int64 v26; // [rsp+98h] [rbp+20h] BYREF
  va_list va1; // [rsp+98h] [rbp+20h]
  __int64 v28; // [rsp+A0h] [rbp+28h]
  va_list va2; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v24 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v26 = va_arg(va2, _QWORD);
  v28 = va_arg(va2, _QWORD);
  v2 = a2;
  *a2 = 0;
  a2[1] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
  {
    v4 = (RTL_SRWLOCK *)(pv + 48);
    AcquireSRWLockExclusive((PSRWLOCK)pv + 6);
    try
    {
      if ( pv[57] )
      {
        v9 = std::make_shared<EmptyWaitableOperation,>(v19);
        std::shared_ptr<WaitableOperation>::operator=(v2, v9);
        v10 = v20;
        if ( v20 )
        {
          if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
      }
      else
      {
        v5 = std::make_shared<WaitableOperation,std::function<void (unsigned char *,unsigned __int64)> &,unsigned char * &,unsigned __int64 &>(
               v19,
               v28,
               (__int64 *)va,
               (__int64 *)va1);
        std::shared_ptr<WaitableOperation>::operator=(v2, v5);
        v6 = v20;
        if ( v20 )
        {
          if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
            if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
          }
        }
        std::queue<std::shared_ptr<WaitableOperation>>::emplace<std::shared_ptr<WaitableOperation> &>(pv + 8, v2);
        if ( !pv[56] && CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated((struct _TP_WORK **)pv) )
        {
          SubmitThreadpoolWork(*(PTP_WORK *)pv);
          pv[56] = 1;
        }
      }
      if ( v4 )
        ReleaseSRWLockExclusive(v4);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\Utils.h",
        v8);
      v2 = a2;
    }
  }
  else
  {
    v11 = (RTL_SRWLOCK *)(pv + 48);
    AcquireSRWLockExclusive((PSRWLOCK)pv + 6);
    if ( pv[57] )
    {
      v14 = std::make_shared<EmptyWaitableOperation,>(v19);
      std::shared_ptr<WaitableOperation>::operator=(v2, v14);
      v15 = v20;
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
    }
    else
    {
      ResetEvent(*((HANDLE *)pv + 8));
      v12 = std::make_shared<WaitableOperation,std::function<void (unsigned char *,unsigned __int64)> &,unsigned char * &,unsigned __int64 &>(
              v19,
              v28,
              (__int64 *)va,
              (__int64 *)va1);
      std::shared_ptr<WaitableOperation>::operator=(v2, v12);
      v13 = v20;
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      std::queue<std::shared_ptr<WaitableOperation>>::emplace<std::shared_ptr<WaitableOperation> &>(pv + 8, v2);
      if ( !pv[56] )
      {
        if ( CreateThread(0, 0, CSOperationDispatcher::ThreadThunk, pv, 0, (LPDWORD)pv + 18) )
          pv[56] = 1;
        else
          SetEvent(*((HANDLE *)pv + 8));
      }
    }
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
  }
  v16 = v28;
  v17 = *(_QWORD *)(v28 + 56);
  if ( v17 )
  {
    LOBYTE(v7) = v17 != v28;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v7);
    *(_QWORD *)(v16 + 56) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180020354  mov     rax, rsp
0x180020357  mov     [rax+20h], r9
0x18002035b  mov     [rax+18h], r8
0x18002035f  mov     [rax+10h], rdx
0x180020363  push    rsi
0x180020364  push    rdi
0x180020365  push    r12
0x180020367  push    r14
0x180020369  push    r15
0x18002036b  sub     rsp, 50h
0x18002036f  mov     r14, rdx
0x180020372  mov     rsi, rcx
0x180020375  mov     dword ptr [rax-48h], 0
0x18002037c  mov     qword ptr [rdx], 0
0x180020383  mov     qword ptr [rdx+8], 0
0x18002038b  mov     dword ptr [rax-48h], 1
0x180020392  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x180020399  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x18002039e  test    al, al
0x1800203a0  jz      loc_1800204D0
0x1800203a6  lea     r12, [rsi+30h]
0x1800203aa  mov     rcx, r12; SRWLock
0x1800203ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800203b3  mov     [rsp+78h+var_40], r12
0x1800203b8  lea     rcx, [rsp+78h+var_38]
0x1800203bd  cmp     byte ptr [rsi+39h], 0
0x1800203c1  jnz     loc_18002045E
0x1800203c7  lea     r9, [rsp+78h+arg_18]
0x1800203cf  lea     r8, [rsp+78h+arg_10]
0x1800203d7  mov     rdx, [rsp+78h+arg_20]
0x1800203df  call    ??$make_shared@VWaitableOperation@@AEAV?$function@$$A6AXPEAE_K@Z@std@@AEAPEAEAEA_K@std@@YA?AV?$shared_ptr@VWaitableOperation@@@0@AEAV?$function@$$A6AXPEAE_K@Z@0@AEAPEAEAEA_K@Z; std::make_shared<WaitableOperation,std::function<void (uchar *,unsigned __int64)> &,uchar * &,unsigned __int64 &>(std::function<void (uchar *,unsigned __int64)> &,uchar * &,unsigned __int64 &)
0x1800203e4  mov     rdx, rax
0x1800203e7  mov     rcx, r14
0x1800203ea  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x1800203ef  mov     r15, [rsp+78h+var_30]
0x1800203f4  test    r15, r15
0x1800203f7  jz      short loc_180020431
0x1800203f9  or      edi, 0FFFFFFFFh
0x1800203fc  mov     eax, edi
0x1800203fe  lock xadd [r15+8], eax
0x180020404  add     eax, edi
0x180020406  jnz     short loc_180020431
0x180020408  mov     rax, [r15]
0x18002040b  mov     rcx, r15
0x18002040e  mov     rax, [rax]
0x180020411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020416  mov     eax, edi
0x180020418  lock xadd [r15+0Ch], eax
0x18002041e  add     eax, edi
0x180020420  jnz     short loc_180020431
0x180020422  mov     rax, [r15]
0x180020425  mov     rcx, r15
0x180020428  mov     rax, [rax+8]
0x18002042c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020431  lea     rcx, [rsi+8]
0x180020435  mov     rdx, r14
0x180020438  call    ??$emplace@AEAV?$shared_ptr@VWaitableOperation@@@std@@@?$queue@V?$shared_ptr@VWaitableOperation@@@std@@V?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@2@@std@@QEAA?A_TAEAV?$shared_ptr@VWaitableOperation@@@1@@Z
0x18002043d  cmp     byte ptr [rsi+38h], 0
0x180020441  jnz     short loc_1800204AF
0x180020443  mov     rcx, rsi; pv
0x180020446  call    ?_TryEnsureThreadpoolWorkCreated@CSOperationDispatcher@@AEAA_NXZ; CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(void)
0x18002044b  test    al, al
0x18002044d  jz      short loc_1800204AF
0x18002044f  mov     rcx, [rsi]; pwk
0x180020452  call    cs:__imp_SubmitThreadpoolWork
0x180020458  mov     byte ptr [rsi+38h], 1
0x18002045c  jmp     short loc_1800204AF
0x18002045e  call    ??$make_shared@VEmptyWaitableOperation@@$$V@std@@YA?AV?$shared_ptr@VEmptyWaitableOperation@@@0@XZ; std::make_shared<EmptyWaitableOperation,>(void)
0x180020463  mov     rdx, rax
0x180020466  mov     rcx, r14
0x180020469  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x18002046e  mov     rsi, [rsp+78h+var_30]
0x180020473  test    rsi, rsi
0x180020476  jz      short loc_1800204AF
0x180020478  or      edi, 0FFFFFFFFh
0x18002047b  mov     eax, edi
0x18002047d  lock xadd [rsi+8], eax
0x180020482  add     eax, edi
0x180020484  jnz     short loc_1800204AF
0x180020486  mov     rax, [rsi]
0x180020489  mov     rcx, rsi
0x18002048c  mov     rax, [rax]
0x18002048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020494  mov     eax, edi
0x180020496  lock xadd [rsi+0Ch], eax
0x18002049b  add     eax, edi
0x18002049d  jnz     short loc_1800204AF
0x18002049f  mov     rax, [rsi]
0x1800204a2  mov     rcx, rsi
0x1800204a5  mov     rax, [rax+8]
0x1800204a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ae  nop
0x1800204af  test    r12, r12
0x1800204b2  jz      short loc_1800204BE
0x1800204b4  mov     rcx, r12; SRWLock
0x1800204b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800204bd  nop
0x1800204be  jmp     loc_18002061C
0x1800204c3  mov     r14, [rsp+78h+arg_8]
0x1800204cb  jmp     loc_18002061C
0x1800204d0  lea     r12, [rsi+30h]
0x1800204d4  mov     rcx, r12; SRWLock
0x1800204d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800204dd  mov     [rsp+78h+var_40], r12
0x1800204e2  cmp     byte ptr [rsi+39h], 0
0x1800204e6  jnz     loc_1800205B7
0x1800204ec  mov     rcx, [rsi+40h]; hEvent
0x1800204f0  call    cs:__imp_ResetEvent
0x1800204f6  lea     r9, [rsp+78h+arg_18]
0x1800204fe  lea     r8, [rsp+78h+arg_10]
0x180020506  mov     rdx, [rsp+78h+arg_20]
0x18002050e  lea     rcx, [rsp+78h+var_38]
0x180020513  call    ??$make_shared@VWaitableOperation@@AEAV?$function@$$A6AXPEAE_K@Z@std@@AEAPEAEAEA_K@std@@YA?AV?$shared_ptr@VWaitableOperation@@@0@AEAV?$function@$$A6AXPEAE_K@Z@0@AEAPEAEAEA_K@Z; std::make_shared<WaitableOperation,std::function<void (uchar *,unsigned __int64)> &,uchar * &,unsigned __int64 &>(std::function<void (uchar *,unsigned __int64)> &,uchar * &,unsigned __int64 &)
0x180020518  mov     rdx, rax
0x18002051b  mov     rcx, r14
0x18002051e  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x180020523  mov     r15, [rsp+78h+var_30]
0x180020528  test    r15, r15
0x18002052b  jz      short loc_180020565
0x18002052d  or      edi, 0FFFFFFFFh
0x180020530  mov     eax, edi
0x180020532  lock xadd [r15+8], eax
0x180020538  add     eax, edi
0x18002053a  jnz     short loc_180020565
0x18002053c  mov     rax, [r15]
0x18002053f  mov     rcx, r15
0x180020542  mov     rax, [rax]
0x180020545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002054a  mov     eax, edi
0x18002054c  lock xadd [r15+0Ch], eax
0x180020552  add     eax, edi
0x180020554  jnz     short loc_180020565
0x180020556  mov     rax, [r15]
0x180020559  mov     rcx, r15
0x18002055c  mov     rax, [rax+8]
0x180020560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020565  lea     rcx, [rsi+8]
0x180020569  mov     rdx, r14
0x18002056c  call    ??$emplace@AEAV?$shared_ptr@VWaitableOperation@@@std@@@?$queue@V?$shared_ptr@VWaitableOperation@@@std@@V?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@2@@std@@QEAA?A_TAEAV?$shared_ptr@VWaitableOperation@@@1@@Z
0x180020571  cmp     byte ptr [rsi+38h], 0
0x180020575  jnz     loc_18002060D
0x18002057b  lea     rax, [rsi+48h]
0x18002057f  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180020584  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18002058c  mov     r9, rsi; lpParameter
0x18002058f  lea     r8, ?ThreadThunk@CSOperationDispatcher@@SAKPEAX@Z; lpStartAddress
0x180020596  xor     edx, edx; dwStackSize
0x180020598  xor     ecx, ecx; lpThreadAttributes
0x18002059a  call    cs:__imp_CreateThread
0x1800205a0  test    rax, rax
0x1800205a3  jz      short loc_1800205AB
0x1800205a5  mov     byte ptr [rsi+38h], 1
0x1800205a9  jmp     short loc_18002060D
0x1800205ab  mov     rcx, [rsi+40h]; hEvent
0x1800205af  call    cs:__imp_SetEvent
0x1800205b5  jmp     short loc_18002060D
0x1800205b7  lea     rcx, [rsp+78h+var_38]
0x1800205bc  call    ??$make_shared@VEmptyWaitableOperation@@$$V@std@@YA?AV?$shared_ptr@VEmptyWaitableOperation@@@0@XZ; std::make_shared<EmptyWaitableOperation,>(void)
0x1800205c1  mov     rdx, rax
0x1800205c4  mov     rcx, r14
0x1800205c7  call    ??4?$shared_ptr@VWaitableOperation@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WaitableOperation>::operator=(std::shared_ptr<WaitableOperation> &&)
0x1800205cc  mov     rsi, [rsp+78h+var_30]
0x1800205d1  test    rsi, rsi
0x1800205d4  jz      short loc_18002060D
0x1800205d6  or      edi, 0FFFFFFFFh
0x1800205d9  mov     eax, edi
0x1800205db  lock xadd [rsi+8], eax
0x1800205e0  add     eax, edi
0x1800205e2  jnz     short loc_18002060D
0x1800205e4  mov     rax, [rsi]
0x1800205e7  mov     rcx, rsi
0x1800205ea  mov     rax, [rax]
0x1800205ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205f2  mov     eax, edi
0x1800205f4  lock xadd [rsi+0Ch], eax
0x1800205f9  add     eax, edi
0x1800205fb  jnz     short loc_18002060D
0x1800205fd  mov     rax, [rsi]
0x180020600  mov     rcx, rsi
0x180020603  mov     rax, [rax+8]
0x180020607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002060c  nop
0x18002060d  test    r12, r12
0x180020610  jz      short loc_18002061C
0x180020612  mov     rcx, r12; SRWLock
0x180020615  call    cs:__imp_ReleaseSRWLockExclusive
0x18002061b  nop
0x18002061c  mov     rdi, [rsp+78h+arg_20]
0x180020624  mov     rcx, [rdi+38h]
0x180020628  test    rcx, rcx
0x18002062b  jz      short loc_180020647
0x18002062d  mov     rax, [rcx]
0x180020630  cmp     rcx, rdi
0x180020633  setnz   dl
0x180020636  mov     rax, [rax+20h]
0x18002063a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002063f  mov     qword ptr [rdi+38h], 0
0x180020647  mov     rax, r14
0x18002064a  add     rsp, 50h
0x18002064e  pop     r15
0x180020650  pop     r14
0x180020652  pop     r12
0x180020654  pop     rdi
0x180020655  pop     rsi
0x180020656  retn
```
