# CAssociationContext::AddChildSetMember(CAssociationContext *)

- ea: `0x1800545c8`
- end: `0x18005474e`
- name: `?AddChildSetMember@CAssociationContext@@QEAAJPEAV1@@Z`
- size: `390`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *pv, struct CAssociationContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800465c0`

## callees

- `0x180005798`
- `0x180019cbc`
- `0x180023890`
- `0x18002aa34`
- `0x180034c00`
- `0x180042be8`
- `0x180049d68`
- `0x180053cb0`
- `0x1800545c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800546a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800546a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180054715`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180054715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800545ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800545ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800545ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800545ff`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005462a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005462a`

## string_xrefs

- `0x180054638`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x1800546b8`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall CAssociationContext::AddChildSetMember(RTL_SRWLOCK *pv, struct CAssociationContext *a2)
{
  HANDLE CurrentProcess; // rdi
  void *v5; // rbx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  _QWORD *Ptr; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  const char *v11; // r9
  struct _TP_WAIT *v12; // rbx
  _QWORD *v13; // rdx
  struct _TP_WAIT *v15; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HANDLE TargetHandle; // [rsp+88h] [rbp+38h] BYREF
  struct _TP_WAIT *v18; // [rsp+90h] [rbp+40h] BYREF
  RTL_SRWLOCK *v19; // [rsp+98h] [rbp+48h] BYREF

  TargetHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v5 = (void *)*((_QWORD *)a2 + 55);
  v6 = GetCurrentProcess();
  if ( DuplicateHandle(v6, v5, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    wil::AcquireSRWLockExclusive(&v19, pv + 53);
    v18 = (struct _TP_WAIT *)TargetHandle;
    Ptr = pv[58].Ptr;
    if ( Ptr == pv[59].Ptr )
    {
      std::vector<CChallengeContext *>::_Emplace_reallocate<CChallengeContext *>(&pv[57], Ptr, &v18);
    }
    else
    {
      *Ptr = TargetHandle;
      pv[58].Ptr = (char *)pv[58].Ptr + 8;
    }
    TargetHandle = 0;
    ThreadpoolWait = CreateThreadpoolWait(CAssociationContext::SetFinalizeWaitCallback, pv, 0);
    v12 = ThreadpoolWait;
    v18 = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v15 = ThreadpoolWait;
      v13 = pv[69].Ptr;
      if ( v13 == pv[70].Ptr )
      {
        std::vector<_TP_WAIT *>::_Emplace_reallocate<_TP_WAIT *>(&pv[68], v13, &v15);
      }
      else
      {
        *v13 = ThreadpoolWait;
        pv[69].Ptr = (char *)pv[69].Ptr + 8;
      }
      SetThreadpoolWait(v12, *((HANDLE *)a2 + 55), 0);
      v18 = 0;
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(&v18);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v19);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x677,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
                    v11);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(&v18);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v19);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x66A,
                  (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
                  v7);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800545c8  push    rbp
0x1800545ca  push    rbx
0x1800545cb  push    rsi
0x1800545cc  push    rdi
0x1800545cd  push    r14
0x1800545cf  mov     rbp, rsp
0x1800545d2  sub     rsp, 50h
0x1800545d6  mov     r14, rdx
0x1800545d9  mov     rsi, rcx
0x1800545dc  mov     [rbp+TargetHandle], 0
0x1800545e4  xor     edx, edx
0x1800545e6  lea     rcx, [rbp+TargetHandle]
0x1800545ea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800545ef  call    cs:__imp_GetCurrentProcess
0x1800545f5  mov     rdi, rax
0x1800545f8  mov     rbx, [r14+1B8h]
0x1800545ff  call    cs:__imp_GetCurrentProcess
0x180054605  mov     [rsp+50h+dwOptions], 2; dwOptions
0x18005460d  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x180054615  mov     [rsp+50h+dwDesiredAccess], 0; dwDesiredAccess
0x18005461d  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180054621  mov     r8, rdi; hTargetProcessHandle
0x180054624  mov     rdx, rbx; hSourceHandle
0x180054627  mov     rcx, rax; hSourceProcessHandle
0x18005462a  call    cs:__imp_DuplicateHandle
0x180054630  test    eax, eax
0x180054632  jnz     short loc_180054650
0x180054634  mov     rcx, [rbp+28h]; this
0x180054638  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x18005463f  mov     edx, 66Ah; void *
0x180054644  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054649  mov     ebx, eax
0x18005464b  jmp     loc_180054738
0x180054650  lea     rdx, [rsi+1A8h]
0x180054657  lea     rcx, [rbp+arg_18]
0x18005465b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180054660  nop
0x180054661  lea     rcx, [rsi+1C8h]
0x180054668  mov     rax, [rbp+TargetHandle]
0x18005466c  mov     [rbp+arg_10], rax
0x180054670  mov     rdx, [rcx+8]
0x180054674  cmp     rdx, [rcx+10h]
0x180054678  jz      short loc_180054684
0x18005467a  mov     [rdx], rax
0x18005467d  add     qword ptr [rcx+8], 8
0x180054682  jmp     short loc_18005468D
0x180054684  lea     r8, [rbp+arg_10]
0x180054688  call    ??$_Emplace_reallocate@PEAVCChallengeContext@@@?$vector@PEAVCChallengeContext@@V?$allocator@PEAVCChallengeContext@@@std@@@std@@AEAAPEAPEAVCChallengeContext@@QEAPEAV2@$$QEAPEAV2@@Z; std::vector<CChallengeContext *>::_Emplace_reallocate<CChallengeContext *>(CChallengeContext * * const,CChallengeContext * &&)
0x18005468d  mov     [rbp+TargetHandle], 0
0x180054695  xor     r8d, r8d; pcbe
0x180054698  mov     rdx, rsi; pv
0x18005469b  lea     rcx, ?SetFinalizeWaitCallback@CAssociationContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800546a2  call    cs:__imp_CreateThreadpoolWait
0x1800546a8  mov     rbx, rax
0x1800546ab  mov     [rbp+arg_10], rax
0x1800546af  test    rax, rax
0x1800546b2  jnz     short loc_1800546E0
0x1800546b4  mov     rcx, [rbp+28h]; this
0x1800546b8  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x1800546bf  mov     edx, 677h; void *
0x1800546c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800546c9  mov     ebx, eax
0x1800546cb  lea     rcx, [rbp+arg_10]
0x1800546cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x1800546d4  nop
0x1800546d5  lea     rcx, [rbp+arg_18]
0x1800546d9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800546de  jmp     short loc_180054738
0x1800546e0  lea     rcx, [rsi+220h]
0x1800546e7  mov     [rbp+var_10], rbx
0x1800546eb  mov     rdx, [rcx+8]
0x1800546ef  cmp     rdx, [rcx+10h]
0x1800546f3  jz      short loc_1800546FF
0x1800546f5  mov     [rdx], rbx
0x1800546f8  add     qword ptr [rcx+8], 8
0x1800546fd  jmp     short loc_180054708
0x1800546ff  lea     r8, [rbp+var_10]
0x180054703  call    ??$_Emplace_reallocate@PEAU_TP_WAIT@@@?$vector@PEAU_TP_WAIT@@V?$allocator@PEAU_TP_WAIT@@@std@@@std@@AEAAPEAPEAU_TP_WAIT@@QEAPEAU2@$$QEAPEAU2@@Z; std::vector<_TP_WAIT *>::_Emplace_reallocate<_TP_WAIT *>(_TP_WAIT * * const,_TP_WAIT * &&)
0x180054708  xor     r8d, r8d; pftTimeout
0x18005470b  mov     rdx, [r14+1B8h]; h
0x180054712  mov     rcx, rbx; pwa
0x180054715  call    cs:__imp_SetThreadpoolWait
0x18005471b  mov     [rbp+arg_10], 0
0x180054723  lea     rcx, [rbp+arg_10]
0x180054727  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x18005472c  nop
0x18005472d  lea     rcx, [rbp+arg_18]
0x180054731  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180054736  xor     ebx, ebx
0x180054738  lea     rcx, [rbp+TargetHandle]
0x18005473c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180054741  mov     eax, ebx
0x180054743  add     rsp, 50h
0x180054747  pop     r14
0x180054749  pop     rdi
0x18005474a  pop     rsi
0x18005474b  pop     rbx
0x18005474c  pop     rbp
0x18005474d  retn
```
