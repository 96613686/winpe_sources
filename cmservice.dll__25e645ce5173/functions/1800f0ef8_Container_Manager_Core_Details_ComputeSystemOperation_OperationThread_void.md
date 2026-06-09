# Container::Manager::Core::Details::ComputeSystemOperation::OperationThread(void)

- ea: `0x1800f0ef8`
- end: `0x1800f153c`
- name: `?OperationThread@ComputeSystemOperation@Details@Core@Manager@Container@@AEAAJXZ`
- size: `1604`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ComputeSystemOperation *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f1550`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x18003dbf8`
- `0x18003f7d8`
- `0x1800471dc`
- `0x180049918`
- `0x18005a30c`
- `0x1800615ec`
- `0x1800d6fc0`
- `0x1800efefc`
- `0x1800f0ef8`
- `0x1800f1604`
- `0x1800f8d40`
- `0x180124df0`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f0fcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f110f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f11a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f0fcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f110f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f11a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1072`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f10c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1154`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f124a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1072`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f10c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1154`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f1211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f124a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0fd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f111b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f11ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0fd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f111b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f11ac`

## string_xrefs

- `0x1800f0f57`: `onecore\base\gendrv\silos\clem\core\lib\computesystemoperation.cpp`
- `0x1800f100f`: `onecore\base\gendrv\silos\clem\core\lib\computesystemoperation.cpp`
- `0x1800f1100`: `onecore\base\gendrv\silos\clem\core\lib\computesystemoperation.cpp`
- `0x1800f14d0`: `onecore\base\gendrv\silos\clem\core\lib\computesystemoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemOperation::OperationThread(
        Container::Manager::Core::Details::ComputeSystemOperation *this)
{
  RTL_SRWLOCK *v2; // rbx
  const struct _GUID *Id; // rax
  int v4; // eax
  unsigned int v5; // r14d
  void *v6; // rdi
  __int64 v8; // r8
  unsigned int v9; // r15d
  int v10; // eax
  void *v11; // rdi
  const char *v12; // r9
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  int v19; // eax
  void *v20; // rdi
  unsigned int *v21; // rdi
  void *v22; // rdi
  void *v23; // rdi
  void *v24; // rdi
  unsigned int v25; // esi
  void *v26; // rdi
  void *v27[2]; // [rsp+20h] [rbp-38h] BYREF
  utl::_RefCountBase *v28; // [rsp+30h] [rbp-28h]
  void *v29[2]; // [rsp+38h] [rbp-20h] BYREF
  utl::_RefCountBase *v30; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  char *v32; // [rsp+90h] [rbp+38h] BYREF

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 23);
  Id = Container::Manager::Core::ResourceHandle::GetId(*((Container::Manager::Core::ResourceHandle **)this + 30));
  Container::Manager::Core::Details::ComputeReaper::WaitForStorageCleanupIfNeeded(v2, Id);
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v4 = Container::Manager::Core::ResourceHandle::RequestExclusiveAccess(*((_QWORD *)this + 30), v27);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
      (const char *)(unsigned int)v4,
      (int)v27[0]);
    Csl::AsyncOperation<void>::Cleanup(v27);
    if ( v28 )
      utl::_RefCountBase::_DecStrong(v28);
    v6 = v27[0];
    if ( !v27[0] )
      return v5;
LABEL_5:
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v27[0]);
    operator delete(v6, (const struct std::nothrow_t *)0x30);
    return v5;
  }
  if ( !*((_DWORD *)v27[1] + 1) || (v5 = -2147023436, *(_DWORD *)v27[1] == -2147023436) )
  {
    v25 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x28B,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            (const char *)0x20,
            (unsigned int)v27[0]);
    Csl::AsyncOperation<void>::Cleanup(v27);
    if ( v28 )
      utl::_RefCountBase::_DecStrong(v28);
    v26 = v27[0];
    if ( v27[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v27[0]);
      operator delete(v26, (const struct std::nothrow_t *)0x30);
    }
    return v25;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 5);
    *((_DWORD *)this + 12) = GetCurrentThreadId();
    v32 = (char *)this + 40;
    v8 = *(unsigned int *)(*((_QWORD *)this + 21) + 440LL);
    *((_DWORD *)this + 23) = 3;
    v9 = Container::Manager::Core::Details::ComputeSystemOperation::QueueAndWaitForPhysicalStateTransition(
           this,
           &v32,
           v8);
    if ( v9 == -2147023436 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)this + 21) + 96LL) & 0x10000) != 0 )
      {
        v10 = Container::Manager::Core::Details::ComputeSystemOperation::CrashComputeSystemLocked(this);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2A2,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            (const char *)(unsigned int)v10,
            (int)v27[0]);
      }
      goto LABEL_14;
    }
    if ( (v9 & 0x80000000) != 0 )
    {
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A5,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
        (const char *)v9,
        (int)v27[0]);
      *((_DWORD *)this + 12) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
      Csl::AsyncOperation<void>::Cleanup(v27);
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      goto LABEL_16;
    }
    *((_DWORD *)this + 12) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
    if ( *(_QWORD *)this )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))this)(*((_QWORD *)this + 2));
      if ( (v9 & 0x80000000) != 0 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)this + 21) + 96LL) & 0x10000) != 0 )
        {
          AcquireSRWLockExclusive((PSRWLOCK)this + 5);
          *((_DWORD *)this + 12) = GetCurrentThreadId();
          v13 = Container::Manager::Core::Details::ComputeSystemOperation::CrashComputeSystemLocked(this);
          if ( v13 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2B3,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
              (const char *)(unsigned int)v13,
              (int)v27[0]);
          *((_DWORD *)this + 12) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B6,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
          (const char *)v9,
          (int)v27[0]);
        Csl::AsyncOperation<void>::Cleanup(v27);
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
        goto LABEL_16;
      }
    }
    if ( *((_QWORD *)this + 1) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 5);
      *((_DWORD *)this + 12) = GetCurrentThreadId();
      v32 = (char *)this + 40;
      *((_DWORD *)this + 23) = 4;
      if ( !*((_BYTE *)this + 116) )
        *((_BYTE *)this + 116) = 1;
      *((_DWORD *)this + 28) = 0;
      v14 = Container::Manager::Core::Details::ComputeSystemOperation::QueueAndWaitForPhysicalStateTransition(
              this,
              &v32,
              0xFFFFFFFFLL);
      v9 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C7,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
          (const char *)(unsigned int)v14,
          (int)v27[0]);
        if ( this != (Container::Manager::Core::Details::ComputeSystemOperation *)-40LL )
        {
          *((_DWORD *)this + 12) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
        }
        Csl::AsyncOperation<void>::Cleanup(v27);
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
        goto LABEL_16;
      }
      if ( this != (Container::Manager::Core::Details::ComputeSystemOperation *)-40LL )
      {
        *((_DWORD *)this + 12) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
      }
      v15 = (*((__int64 (__fastcall **)(_QWORD))this + 1))(*((_QWORD *)this + 2));
      v9 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
          (const char *)(unsigned int)v15,
          (int)v27[0]);
        Csl::AsyncOperation<void>::Cleanup(v27);
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
LABEL_16:
        v11 = v27[0];
        if ( !v27[0] )
          return v9;
LABEL_17:
        Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v27[0]);
        operator delete(v11, (const struct std::nothrow_t *)0x30);
        return v9;
      }
    }
    v16 = *((_DWORD *)this + 6);
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 != 1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x2EB,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            v12);
        v18 = Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(
                *((PSRWLOCK *)this + 17),
                0);
        v5 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E3,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            (const char *)(unsigned int)v18,
            (int)v27[0]);
          Csl::AsyncOperation<void>::Cleanup(v27);
          if ( v28 )
            utl::_RefCountBase::_DecStrong(v28);
          goto LABEL_67;
        }
      }
      else
      {
        *(_OWORD *)v29 = 0;
        v30 = 0;
        v19 = Container::Manager::Hcs::ComputeSystem::ShutdownAsync(*((_QWORD *)this + 27), v29);
        v9 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2DA,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            (const char *)(unsigned int)v19,
            (int)v27[0]);
          Csl::AsyncOperation<void>::Cleanup(v29);
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
          v20 = v29[0];
          if ( v29[0] )
          {
            Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v29[0]);
            operator delete(v20, (const struct std::nothrow_t *)0x30);
          }
          Csl::AsyncOperation<void>::Cleanup(v27);
          if ( v28 )
            utl::_RefCountBase::_DecStrong(v28);
          v11 = v27[0];
          if ( !v27[0] )
            return v9;
          goto LABEL_17;
        }
        v21 = (unsigned int *)v29[1];
        if ( !(unsigned __int8)wil::slim_event_t<1>::wait((char *)v29[1] + 4) || (v5 = *v21, (*v21 & 0x80000000) != 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2DC,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
            (const char *)v5,
            (int)v27[0]);
          Csl::AsyncOperation<void>::Cleanup(v29);
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
          v22 = v29[0];
          if ( v29[0] )
          {
            Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v29[0]);
            operator delete(v22, (const struct std::nothrow_t *)0x30);
          }
          Csl::AsyncOperation<void>::Cleanup(v27);
          if ( v28 )
            utl::_RefCountBase::_DecStrong(v28);
LABEL_67:
          v6 = v27[0];
          if ( !v27[0] )
            return v5;
          goto LABEL_5;
        }
        Csl::AsyncOperation<void>::Cleanup(v29);
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        v23 = v29[0];
        if ( v29[0] )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v29[0]);
          operator delete(v23, (const struct std::nothrow_t *)0x30);
        }
      }
    }
    Csl::AsyncOperation<void>::Cleanup(v27);
    if ( v28 )
      utl::_RefCountBase::_DecStrong(v28);
    v24 = v27[0];
    if ( v27[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>((_DWORD *)v27[0]);
      operator delete(v24, (const struct std::nothrow_t *)0x30);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800f0ef8  push    rbp
0x1800f0efa  push    rbx
0x1800f0efb  push    rsi
0x1800f0efc  push    rdi
0x1800f0efd  push    r14
0x1800f0eff  push    r15
0x1800f0f01  mov     rbp, rsp
0x1800f0f04  sub     rsp, 58h
0x1800f0f08  mov     rdi, rcx
0x1800f0f0b  mov     rbx, [rcx+0B8h]
0x1800f0f12  mov     rcx, [rcx+0F0h]; this
0x1800f0f19  call    ?GetId@ResourceHandle@Core@Manager@Container@@QEBAAEBU_GUID@@XZ; Container::Manager::Core::ResourceHandle::GetId(void)
0x1800f0f1e  mov     rdx, rax; struct _GUID *
0x1800f0f21  mov     rcx, rbx; SRWLock
0x1800f0f24  call    ?WaitForStorageCleanupIfNeeded@ComputeReaper@Details@Core@Manager@Container@@QEBAXAEBU_GUID@@@Z; Container::Manager::Core::Details::ComputeReaper::WaitForStorageCleanupIfNeeded(_GUID const &)
0x1800f0f29  xorps   xmm0, xmm0
0x1800f0f2c  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800f0f31  mov     [rbp+var_28], 0
0x1800f0f39  lea     rdx, [rbp+var_38]
0x1800f0f3d  mov     rcx, [rdi+0F0h]
0x1800f0f44  call    ?RequestExclusiveAccess@ResourceHandle@Core@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Core::ResourceHandle::RequestExclusiveAccess(Csl::AsyncOperation<void> &)
0x1800f0f49  mov     r14d, eax
0x1800f0f4c  test    eax, eax
0x1800f0f4e  jns     short loc_1800F0FA7
0x1800f0f50  mov     rcx, [rbp+30h]; this
0x1800f0f54  mov     r9d, eax; char *
0x1800f0f57  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f0f5e  mov     edx, 280h; void *
0x1800f0f63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0f68  lea     rcx, [rbp+var_38]
0x1800f0f6c  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f0f71  nop
0x1800f0f72  mov     rcx, [rbp+var_28]; this
0x1800f0f76  test    rcx, rcx
0x1800f0f79  jz      short loc_1800F0F81
0x1800f0f7b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f0f80  nop
0x1800f0f81  mov     rdi, [rbp+var_38]
0x1800f0f85  test    rdi, rdi
0x1800f0f88  jz      short loc_1800F0F9F
0x1800f0f8a  mov     rcx, rdi
0x1800f0f8d  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f0f92  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800f0f97  mov     rcx, rdi; void *
0x1800f0f9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f0f9f  mov     eax, r14d
0x1800f0fa2  jmp     loc_1800F151C
0x1800f0fa7  mov     rcx, [rbp+var_38+8]
0x1800f0fab  mov     eax, [rcx+4]
0x1800f0fae  test    eax, eax
0x1800f0fb0  jz      loc_1800F14C6
0x1800f0fb6  mov     r14d, 800705B4h
0x1800f0fbc  cmp     [rcx], r14d
0x1800f0fbf  jz      loc_1800F14C6
0x1800f0fc5  lea     rbx, [rdi+28h]
0x1800f0fc9  mov     rcx, rbx; SRWLock
0x1800f0fcc  call    cs:__imp_AcquireSRWLockExclusive
0x1800f0fd3  nop     dword ptr [rax+rax+00h]
0x1800f0fd8  call    cs:__imp_GetCurrentThreadId
0x1800f0fdf  nop     dword ptr [rax+rax+00h]
0x1800f0fe4  mov     [rbx+8], eax
0x1800f0fe7  mov     [rbp+arg_0], rbx
0x1800f0feb  mov     rax, [rdi+0A8h]
0x1800f0ff2  mov     r8d, [rax+1B8h]
0x1800f0ff9  mov     dword ptr [rdi+5Ch], 3
0x1800f1000  lea     rdx, [rbp+arg_0]
0x1800f1004  mov     rcx, rdi
0x1800f1007  call    ?QueueAndWaitForPhysicalStateTransition@ComputeSystemOperation@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@K@Z; Container::Manager::Core::Details::ComputeSystemOperation::QueueAndWaitForPhysicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &,ulong)
0x1800f100c  mov     r15d, eax
0x1800f100f  lea     rsi, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f1016  cmp     eax, r14d
0x1800f1019  jnz     short loc_1800F104F
0x1800f101b  mov     rcx, [rdi+0A8h]
0x1800f1022  mov     ecx, [rcx+60h]
0x1800f1025  shr     ecx, 10h
0x1800f1028  test    cl, 1
0x1800f102b  jz      short loc_1800F1054
0x1800f102d  mov     rcx, rdi; this
0x1800f1030  call    ?CrashComputeSystemLocked@ComputeSystemOperation@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::ComputeSystemOperation::CrashComputeSystemLocked(void)
0x1800f1035  mov     rcx, [rbp+30h]; this
0x1800f1039  test    eax, eax
0x1800f103b  jns     short loc_1800F1054
0x1800f103d  mov     r9d, eax; char *
0x1800f1040  mov     r8, rsi; unsigned int
0x1800f1043  mov     edx, 2A2h; void *
0x1800f1048  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f104d  jmp     short loc_1800F1054
0x1800f104f  test    r15d, r15d
0x1800f1052  jns     short loc_1800F10BD
0x1800f1054  mov     rcx, [rbp+30h]; this
0x1800f1058  mov     r9d, r15d; char *
0x1800f105b  mov     r8, rsi; unsigned int
0x1800f105e  mov     edx, 2A5h; void *
0x1800f1063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1068  mov     dword ptr [rbx+8], 0
0x1800f106f  mov     rcx, rbx; SRWLock
0x1800f1072  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f1079  nop     dword ptr [rax+rax+00h]
0x1800f107e  lea     rcx, [rbp+var_38]
0x1800f1082  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f1087  nop
0x1800f1088  mov     rcx, [rbp+var_28]; this
0x1800f108c  test    rcx, rcx
0x1800f108f  jz      short loc_1800F1097
0x1800f1091  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f1096  nop
0x1800f1097  mov     rdi, [rbp+var_38]
0x1800f109b  test    rdi, rdi
0x1800f109e  jz      short loc_1800F10B5
0x1800f10a0  mov     rcx, rdi
0x1800f10a3  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f10a8  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800f10ad  mov     rcx, rdi; void *
0x1800f10b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f10b5  mov     eax, r15d
0x1800f10b8  jmp     loc_1800F151C
0x1800f10bd  mov     dword ptr [rbx+8], 0
0x1800f10c4  mov     rcx, rbx; SRWLock
0x1800f10c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f10ce  nop     dword ptr [rax+rax+00h]
0x1800f10d3  mov     rax, [rdi]
0x1800f10d6  test    rax, rax
0x1800f10d9  jz      loc_1800F1192
0x1800f10df  mov     rcx, [rdi+10h]
0x1800f10e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f10e8  mov     r15d, eax
0x1800f10eb  test    eax, eax
0x1800f10ed  jns     loc_1800F1192
0x1800f10f3  mov     rcx, [rdi+0A8h]
0x1800f10fa  mov     ecx, [rcx+60h]
0x1800f10fd  shr     ecx, 10h
0x1800f1100  lea     rsi, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f1107  test    cl, 1
0x1800f110a  jz      short loc_1800F1160
0x1800f110c  mov     rcx, rbx; SRWLock
0x1800f110f  call    cs:__imp_AcquireSRWLockExclusive
0x1800f1116  nop     dword ptr [rax+rax+00h]
0x1800f111b  call    cs:__imp_GetCurrentThreadId
0x1800f1122  nop     dword ptr [rax+rax+00h]
0x1800f1127  mov     [rbx+8], eax
0x1800f112a  mov     rcx, rdi; this
0x1800f112d  call    ?CrashComputeSystemLocked@ComputeSystemOperation@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::ComputeSystemOperation::CrashComputeSystemLocked(void)
0x1800f1132  mov     rcx, [rbp+30h]; this
0x1800f1136  test    eax, eax
0x1800f1138  jns     short loc_1800F114A
0x1800f113a  mov     r9d, eax; char *
0x1800f113d  mov     r8, rsi; unsigned int
0x1800f1140  mov     edx, 2B3h; void *
0x1800f1145  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f114a  mov     dword ptr [rbx+8], 0
0x1800f1151  mov     rcx, rbx; SRWLock
0x1800f1154  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f115b  nop     dword ptr [rax+rax+00h]
0x1800f1160  mov     rcx, [rbp+30h]; this
0x1800f1164  mov     r9d, r15d; char *
0x1800f1167  mov     r8, rsi; unsigned int
0x1800f116a  mov     edx, 2B6h; void *
0x1800f116f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1174  lea     rcx, [rbp+var_38]
0x1800f1178  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f117d  nop
0x1800f117e  mov     rcx, [rbp+var_28]; this
0x1800f1182  test    rcx, rcx
0x1800f1185  jz      short loc_1800F118D
0x1800f1187  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f118c  nop
0x1800f118d  jmp     loc_1800F1097
0x1800f1192  cmp     qword ptr [rdi+8], 0
0x1800f1197  jz      loc_1800F129C
0x1800f119d  mov     rcx, rbx; SRWLock
0x1800f11a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800f11a7  nop     dword ptr [rax+rax+00h]
0x1800f11ac  call    cs:__imp_GetCurrentThreadId
0x1800f11b3  nop     dword ptr [rax+rax+00h]
0x1800f11b8  mov     [rbx+8], eax
0x1800f11bb  mov     [rbp+arg_0], rbx
0x1800f11bf  mov     dword ptr [rdi+5Ch], 4
0x1800f11c6  cmp     byte ptr [rdi+74h], 0
0x1800f11ca  jnz     short loc_1800F11D0
0x1800f11cc  mov     byte ptr [rdi+74h], 1
0x1800f11d0  mov     dword ptr [rdi+70h], 0
0x1800f11d7  or      r8d, 0FFFFFFFFh
0x1800f11db  lea     rdx, [rbp+arg_0]
0x1800f11df  mov     rcx, rdi
0x1800f11e2  call    ?QueueAndWaitForPhysicalStateTransition@ComputeSystemOperation@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@K@Z; Container::Manager::Core::Details::ComputeSystemOperation::QueueAndWaitForPhysicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &,ulong)
0x1800f11e7  mov     r15d, eax
0x1800f11ea  test    eax, eax
0x1800f11ec  jns     short loc_1800F123B
0x1800f11ee  mov     rcx, [rbp+30h]; this
0x1800f11f2  mov     r9d, eax; char *
0x1800f11f5  mov     r8, rsi; unsigned int
0x1800f11f8  mov     edx, 2C7h; void *
0x1800f11fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1202  test    rbx, rbx
0x1800f1205  jz      short loc_1800F121D
0x1800f1207  mov     dword ptr [rbx+8], 0
0x1800f120e  mov     rcx, rbx; SRWLock
0x1800f1211  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f1218  nop     dword ptr [rax+rax+00h]
0x1800f121d  lea     rcx, [rbp+var_38]
0x1800f1221  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f1226  nop
0x1800f1227  mov     rcx, [rbp+var_28]; this
0x1800f122b  test    rcx, rcx
0x1800f122e  jz      short loc_1800F1236
0x1800f1230  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f1235  nop
0x1800f1236  jmp     loc_1800F1097
0x1800f123b  test    rbx, rbx
0x1800f123e  jz      short loc_1800F1256
0x1800f1240  mov     dword ptr [rbx+8], 0
0x1800f1247  mov     rcx, rbx; SRWLock
0x1800f124a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f1251  nop     dword ptr [rax+rax+00h]
0x1800f1256  mov     rcx, [rdi+10h]
0x1800f125a  mov     rax, [rdi+8]
0x1800f125e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1263  mov     r15d, eax
0x1800f1266  test    eax, eax
0x1800f1268  jns     short loc_1800F129C
0x1800f126a  mov     rcx, [rbp+30h]; this
0x1800f126e  mov     r9d, eax; char *
0x1800f1271  mov     r8, rsi; unsigned int
0x1800f1274  mov     edx, 2CCh; void *
0x1800f1279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f127e  lea     rcx, [rbp+var_38]
0x1800f1282  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f1287  nop
0x1800f1288  mov     rcx, [rbp+var_28]; this
0x1800f128c  test    rcx, rcx
0x1800f128f  jz      short loc_1800F1297
0x1800f1291  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f1296  nop
0x1800f1297  jmp     loc_1800F1097
0x1800f129c  mov     ecx, [rdi+18h]
0x1800f129f  mov     ebx, 30h ; '0'
0x1800f12a4  test    ecx, ecx
0x1800f12a6  jz      loc_1800F148D
0x1800f12ac  sub     ecx, 1
0x1800f12af  jz      short loc_1800F1305
0x1800f12b1  cmp     ecx, 1
0x1800f12b4  jnz     loc_1800F152A
0x1800f12ba  xor     edx, edx; bool
0x1800f12bc  mov     rcx, [rdi+88h]; SRWLock
0x1800f12c3  call    ?Terminate@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@QEAAJ_N@Z; Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(bool)
0x1800f12c8  mov     r14d, eax
0x1800f12cb  test    eax, eax
0x1800f12cd  jns     loc_1800F148D
0x1800f12d3  mov     rcx, [rbp+30h]; this
0x1800f12d7  mov     r9d, eax; char *
0x1800f12da  mov     r8, rsi; unsigned int
0x1800f12dd  mov     edx, 2E3h; void *
0x1800f12e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f12e7  lea     rcx, [rbp+var_38]
0x1800f12eb  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f12f0  nop
0x1800f12f1  mov     rcx, [rbp+var_28]; this
0x1800f12f5  test    rcx, rcx
0x1800f12f8  jz      short loc_1800F1300
0x1800f12fa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f12ff  nop
0x1800f1300  jmp     loc_1800F143B
0x1800f1305  xorps   xmm0, xmm0
0x1800f1308  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800f130d  mov     [rbp+var_10], 0
0x1800f1315  lea     rdx, [rbp+var_20]
0x1800f1319  mov     rcx, [rdi+0D8h]
0x1800f1320  call    ?ShutdownAsync@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::ShutdownAsync(Csl::AsyncOperation<void> &)
0x1800f1325  mov     r15d, eax
0x1800f1328  test    eax, eax
0x1800f132a  jns     loc_1800F13B3
0x1800f1330  mov     rcx, [rbp+30h]; this
0x1800f1334  mov     r9d, eax; char *
0x1800f1337  mov     r8, rsi; unsigned int
0x1800f133a  mov     edx, 2DAh; void *
0x1800f133f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1344  lea     rcx, [rbp+var_20]
0x1800f1348  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f134d  nop
0x1800f134e  mov     rcx, [rbp+var_10]; this
0x1800f1352  test    rcx, rcx
0x1800f1355  jz      short loc_1800F135D
0x1800f1357  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f135c  nop
0x1800f135d  mov     rdi, [rbp+var_20]
0x1800f1361  mov     ebx, 30h ; '0'
0x1800f1366  test    rdi, rdi
0x1800f1369  jz      short loc_1800F137D
0x1800f136b  mov     rcx, rdi
0x1800f136e  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f1373  mov     edx, ebx; struct std::nothrow_t *
0x1800f1375  mov     rcx, rdi; void *
0x1800f1378  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f137d  lea     rcx, [rbp+var_38]
0x1800f1381  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f1386  nop
0x1800f1387  mov     rcx, [rbp+var_28]; this
0x1800f138b  test    rcx, rcx
0x1800f138e  jz      short loc_1800F1396
0x1800f1390  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
  ... truncated ...
```
