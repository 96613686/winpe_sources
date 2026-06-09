# Container::Manager::Core::Details::MemoryManager::OnContainerResuming(Container::Manager::Core::Details::ContainerMemoryContext &,CmTraceProvider::ResumeContainerStateTransition const &)

- ea: `0x18007b3f0`
- end: `0x18007b659`
- name: `?OnContainerResuming@MemoryManager@Details@Core@Manager@Container@@QEAAXAEAUContainerMemoryContext@2345@AEBVResumeContainerStateTransition@CmTraceProvider@@@Z`
- size: `617`
- prototype: `void __fastcall(Container::Manager::Core::Details::MemoryManager *__hidden this, struct Container::Manager::Core::Details::ContainerMemoryContext *, const struct CmTraceProvider::ResumeContainerStateTransition *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x1800aa830`

## callees

- `0x180004bd0`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000b49c`
- `0x1800103a4`
- `0x18007a934`
- `0x18007afd4`
- `0x18007b000`
- `0x18007b3f0`
- `0x18007c6b4`
- `0x18007c7ac`
- `0x18007d4b4`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18007b462`
- `ntdll!NtQueryInformationThread` at `0x18007b462`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18007b48a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18007b48a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b422`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b574`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b5de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b422`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b574`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b5de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b4bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b5be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b620`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b4bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b5be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b42e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b5ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b42e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b5ea`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::MemoryManager::OnContainerResuming(
        RTL_SRWLOCK *this,
        struct Container::Manager::Core::Details::ContainerMemoryContext *a2,
        const struct CmTraceProvider::ResumeContainerStateTransition *a3)
{
  unsigned int v6; // ebp
  Container::Manager::Core::Details *MemoryHostingProcess; // rax
  void *v8; // rdx
  unsigned __int64 ProcessPrivateWorkingSetBytes; // rax
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r15
  __int64 v12; // rbx
  __int64 v13; // rax
  Container::Manager::Core::Details::MemoryManager *v14; // rcx
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD v16[34]; // [rsp+40h] [rbp-198h] BYREF
  __int64 v17; // [rsp+150h] [rbp-88h]

  AcquireSRWLockExclusive(this);
  LODWORD(this[1].Ptr) = GetCurrentThreadId();
  *((_DWORD *)a2 + 11) = 0;
  if ( *((_DWORD *)a2 + 13) )
  {
    NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadActualBasePriority, &this[11], 4u, 0);
    Container::Manager::Core::Details::MemoryManager::CheckUpdateRemediationThreadPriority((Container::Manager::Core::Details::MemoryManager *)this);
    while ( *((_DWORD *)a2 + 13) )
    {
      LODWORD(this[1].Ptr) = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)a2 + 7, this, 0xFFFFFFFF, 0);
      LODWORD(this[1].Ptr) = GetCurrentThreadId();
    }
  }
  v6 = *((_DWORD *)a2 + 12);
  if ( (v6 & 2) != 0 )
  {
    LODWORD(this[1].Ptr) = 0;
    ReleaseSRWLockExclusive(this);
    MemoryHostingProcess = (Container::Manager::Core::Details *)Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(a2);
    ProcessPrivateWorkingSetBytes = Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(
                                      MemoryHostingProcess,
                                      v8);
    v10 = *((_QWORD *)a2 + 13);
    v11 = v10;
    if ( ProcessPrivateWorkingSetBytes < v10 )
      v11 = ProcessPrivateWorkingSetBytes;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v16,
      "ResumeContainerStateTransition_InSwap");
    v16[0] = &CmTraceProvider::ResumeContainerStateTransition_InSwap::`vftable';
    v12 = *((_QWORD *)a3 + 34);
    wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v16, SRWLock);
    v13 = v17;
    *(_OWORD *)(v17 + 24) = *(_OWORD *)(v12 + 8);
    *(_BYTE *)(v13 + 4) = 1;
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    CmTraceProvider::ResumeContainerStateTransition_InSwap::StartActivity(
      (CmTraceProvider::ResumeContainerStateTransition_InSwap *)v16,
      v6,
      *((_QWORD *)a2 + 13),
      v10 - v11);
    Container::Manager::Core::Details::MemoryManager::InSwapContainer(v14, a2);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, 0);
    AcquireSRWLockExclusive(this);
    LODWORD(this[1].Ptr) = GetCurrentThreadId();
    v16[0] = &CmTraceProvider::ResumeContainerStateTransition_InSwap::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v16);
  }
  else if ( (v6 & 1) != 0 )
  {
    LODWORD(this[1].Ptr) = 0;
    ReleaseSRWLockExclusive(this);
    Container::Manager::Core::Details::MemoryManager::ReprioritizeContainerPrivateWorkingSet(
      (Container::Manager::Core::Details::MemoryManager *)this,
      a2,
      5u);
    AcquireSRWLockExclusive(this);
    LODWORD(this[1].Ptr) = GetCurrentThreadId();
  }
  *((_DWORD *)a2 + 12) = 0;
  *((_QWORD *)a2 + 8) = 0;
  *((_QWORD *)a2 + 13) = 0;
  *((_QWORD *)a2 + 14) = 0;
  *((_QWORD *)a2 + 15) = 0;
  *((_QWORD *)a2 + 16) = 0;
  if ( this )
  {
    LODWORD(this[1].Ptr) = 0;
    ReleaseSRWLockExclusive(this);
  }
}

```

## disassembly

```asm
0x18007b3f0  mov     [rsp+arg_10], rbx
0x18007b3f5  push    rbp
0x18007b3f6  push    rsi
0x18007b3f7  push    rdi
0x18007b3f8  push    r12
0x18007b3fa  push    r13
0x18007b3fc  push    r14
0x18007b3fe  push    r15
0x18007b400  sub     rsp, 1A0h
0x18007b407  mov     rax, cs:__security_cookie
0x18007b40e  xor     rax, rsp
0x18007b411  mov     [rsp+1D8h+var_48], rax
0x18007b419  mov     r13, r8
0x18007b41c  mov     rsi, rdx
0x18007b41f  mov     rdi, rcx
0x18007b422  call    cs:__imp_AcquireSRWLockExclusive
0x18007b429  nop     dword ptr [rax+rax+00h]
0x18007b42e  call    cs:__imp_GetCurrentThreadId
0x18007b435  nop     dword ptr [rax+rax+00h]
0x18007b43a  mov     [rdi+8], eax
0x18007b43d  xor     r12d, r12d
0x18007b440  mov     [rsi+2Ch], r12d
0x18007b444  cmp     [rsi+34h], r12d
0x18007b448  jz      short loc_18007B4AB
0x18007b44a  lea     r8, [rdi+58h]; ThreadInformation
0x18007b44e  mov     [rsp+1D8h+ReturnLength], r12; ReturnLength
0x18007b453  lea     edx, [r12+19h]; ThreadInformationClass
0x18007b458  lea     rcx, [r12-2]; ThreadHandle
0x18007b45d  lea     r9d, [r12+4]; ThreadInformationLength
0x18007b462  call    cs:__imp_NtQueryInformationThread
0x18007b469  nop     dword ptr [rax+rax+00h]
0x18007b46e  mov     rcx, rdi; this
0x18007b471  call    ?CheckUpdateRemediationThreadPriority@MemoryManager@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::MemoryManager::CheckUpdateRemediationThreadPriority(void)
0x18007b476  jmp     short loc_18007B4A5
0x18007b478  mov     [rdi+8], r12d
0x18007b47c  xor     r9d, r9d; Flags
0x18007b47f  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18007b483  mov     rdx, rdi; SRWLock
0x18007b486  lea     rcx, [rsi+38h]; ConditionVariable
0x18007b48a  call    cs:__imp_SleepConditionVariableSRW
0x18007b491  nop     dword ptr [rax+rax+00h]
0x18007b496  call    cs:__imp_GetCurrentThreadId
0x18007b49d  nop     dword ptr [rax+rax+00h]
0x18007b4a2  mov     [rdi+8], eax
0x18007b4a5  cmp     [rsi+34h], r12d
0x18007b4a9  jnz     short loc_18007B478
0x18007b4ab  mov     ebp, [rsi+30h]
0x18007b4ae  test    bpl, 2
0x18007b4b2  jz      loc_18007B5B1
0x18007b4b8  mov     [rdi+8], r12d
0x18007b4bc  mov     rcx, rdi; SRWLock
0x18007b4bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b4c6  nop     dword ptr [rax+rax+00h]
0x18007b4cb  mov     rcx, rsi; this
0x18007b4ce  call    ?GetMemoryHostingProcess@ContainerMemoryContext@Details@Core@Manager@Container@@QEBAPEAXXZ; Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(void)
0x18007b4d3  mov     rcx, rax; this
0x18007b4d6  call    ?QueryProcessPrivateWorkingSetBytes@Details@Core@Manager@Container@@YA_KPEAX@Z; Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(void *)
0x18007b4db  mov     r14, [rsi+68h]
0x18007b4df  mov     r15, r14
0x18007b4e2  cmp     rax, r14
0x18007b4e5  cmovb   r15, rax
0x18007b4e9  lea     rdx, aResumecontaine_3; "ResumeContainerStateTransition_InSwap"
0x18007b4f0  lea     rcx, [rsp+1D8h+var_198]
0x18007b4f5  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007b4fa  lea     rax, ??_7ResumeContainerStateTransition_InSwap@CmTraceProvider@@6B@; const CmTraceProvider::ResumeContainerStateTransition_InSwap::`vftable'
0x18007b501  mov     [rsp+1D8h+var_198], rax
0x18007b506  mov     rbx, [r13+110h]
0x18007b50d  lea     rdx, [rsp+1D8h+SRWLock]
0x18007b512  lea     rcx, [rsp+1D8h+var_198]
0x18007b517  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007b51c  mov     rax, [rsp+1D8h+var_88]
0x18007b524  movups  xmm0, xmmword ptr [rbx+8]
0x18007b528  movdqu  xmmword ptr [rax+18h], xmm0
0x18007b52d  mov     byte ptr [rax+4], 1
0x18007b531  mov     rcx, [rsp+1D8h+SRWLock]; SRWLock
0x18007b536  test    rcx, rcx
0x18007b539  jz      short loc_18007B547
0x18007b53b  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b542  nop     dword ptr [rax+rax+00h]
0x18007b547  sub     r14, r15
0x18007b54a  mov     r9, r14; unsigned __int64
0x18007b54d  mov     r8, [rsi+68h]; unsigned __int64
0x18007b551  mov     edx, ebp; unsigned int
0x18007b553  lea     rcx, [rsp+1D8h+var_198]; this
0x18007b558  call    ?StartActivity@ResumeContainerStateTransition_InSwap@CmTraceProvider@@QEAAXK_K0@Z; CmTraceProvider::ResumeContainerStateTransition_InSwap::StartActivity(ulong,unsigned __int64,unsigned __int64)
0x18007b55d  mov     rdx, rsi; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x18007b560  call    ?InSwapContainer@MemoryManager@Details@Core@Manager@Container@@AEBAXAEBUContainerMemoryContext@2345@@Z; Container::Manager::Core::Details::MemoryManager::InSwapContainer(Container::Manager::Core::Details::ContainerMemoryContext const &)
0x18007b565  xor     edx, edx
0x18007b567  lea     rcx, [rsp+1D8h+var_198]
0x18007b56c  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007b571  mov     rcx, rdi; SRWLock
0x18007b574  call    cs:__imp_AcquireSRWLockExclusive
0x18007b57b  nop     dword ptr [rax+rax+00h]
0x18007b580  call    cs:__imp_GetCurrentThreadId
0x18007b587  nop     dword ptr [rax+rax+00h]
0x18007b58c  mov     [rdi+8], eax
0x18007b58f  lea     rax, ??_7ResumeContainerStateTransition_InSwap@CmTraceProvider@@6B@; const CmTraceProvider::ResumeContainerStateTransition_InSwap::`vftable'
0x18007b596  mov     [rsp+1D8h+var_198], rax
0x18007b59b  lea     rcx, [rsp+1D8h+var_198]
0x18007b5a0  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18007b5a5  lea     rcx, [rsp+1D8h+var_198]
0x18007b5aa  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18007b5af  jmp     short loc_18007B5F9
0x18007b5b1  test    bpl, 1
0x18007b5b5  jz      short loc_18007B5F9
0x18007b5b7  mov     [rdi+8], r12d
0x18007b5bb  mov     rcx, rdi; SRWLock
0x18007b5be  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b5c5  nop     dword ptr [rax+rax+00h]
0x18007b5ca  mov     r8d, 5; unsigned int
0x18007b5d0  mov     rdx, rsi; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x18007b5d3  mov     rcx, rdi; this
0x18007b5d6  call    ?ReprioritizeContainerPrivateWorkingSet@MemoryManager@Details@Core@Manager@Container@@AEBAXAEBUContainerMemoryContext@2345@K@Z; Container::Manager::Core::Details::MemoryManager::ReprioritizeContainerPrivateWorkingSet(Container::Manager::Core::Details::ContainerMemoryContext const &,ulong)
0x18007b5db  mov     rcx, rdi; SRWLock
0x18007b5de  call    cs:__imp_AcquireSRWLockExclusive
0x18007b5e5  nop     dword ptr [rax+rax+00h]
0x18007b5ea  call    cs:__imp_GetCurrentThreadId
0x18007b5f1  nop     dword ptr [rax+rax+00h]
0x18007b5f6  mov     [rdi+8], eax
0x18007b5f9  mov     [rsi+30h], r12d
0x18007b5fd  mov     [rsi+40h], r12
0x18007b601  mov     [rsi+68h], r12
0x18007b605  mov     [rsi+70h], r12
0x18007b609  mov     [rsi+78h], r12
0x18007b60d  mov     [rsi+80h], r12
0x18007b614  test    rdi, rdi
0x18007b617  jz      short loc_18007B62D
0x18007b619  mov     [rdi+8], r12d
0x18007b61d  mov     rcx, rdi; SRWLock
0x18007b620  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b627  nop     dword ptr [rax+rax+00h]
0x18007b62c  nop
0x18007b62d  mov     rcx, [rsp+1D8h+var_48]
0x18007b635  xor     rcx, rsp; StackCookie
0x18007b638  call    __security_check_cookie
0x18007b63d  mov     rbx, [rsp+1D8h+arg_10]
0x18007b645  add     rsp, 1A0h
0x18007b64c  pop     r15
0x18007b64e  pop     r14
0x18007b650  pop     r13
0x18007b652  pop     r12
0x18007b654  pop     rdi
0x18007b655  pop     rsi
0x18007b656  pop     rbp
0x18007b657  retn
```
