# Container::Manager::Core::Details::HeartbeatMonitor::DumpCollectionThread(void)

- ea: `0x180076d7c`
- end: `0x180076fd1`
- name: `?DumpCollectionThread@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAXXZ`
- size: `597`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180076fe0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18001063c`
- `0x180043c94`
- `0x18004b37c`
- `0x1800769dc`
- `0x180076d7c`
- `0x18007721c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076da8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076e4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076ef4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076f51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076da8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076e4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076ef4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076f51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076e21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076f23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076e21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076f23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076fa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076f00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076f00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076f5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::HeartbeatMonitor::DumpCollectionThread(PSRWLOCK SRWLock)
{
  PSRWLOCK v2; // rsi
  _QWORD *Ptr; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // r14
  int v7; // ebx
  Container::Manager::Core::Details::InProcClientContainerHandle *v8; // rbx
  Container::Manager::Core::Details::HeartbeatMonitor *v9; // rcx
  int v10; // ebx
  Container::Manager::Core::Details::InProcClientContainerHandle *v11; // rbx
  Container::Manager::Core::Details::InProcClientContainerHandle *v12; // [rsp+20h] [rbp-E0h] BYREF
  struct _GUID v13; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v14[42]; // [rsp+40h] [rbp-C0h] BYREF

  AcquireSRWLockExclusive(SRWLock);
  LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  v2 = SRWLock + 7;
  while ( 1 )
  {
    Ptr = v2->Ptr;
    if ( v2->Ptr == v2 )
      break;
    v4 = *Ptr;
    if ( *(_QWORD **)(*Ptr + 8LL) != Ptr || (v5 = (_QWORD *)Ptr[1], (_QWORD *)*v5 != Ptr) )
      __fastfail(3u);
    v6 = Ptr - 2;
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    *(_OWORD *)Ptr = 0;
    v13 = *(struct _GUID *)Ptr[2];
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    v12 = 0;
    v7 = Container::Manager::Core::Details::OpenInProcClientContainerHandle(&v13, 1, &v12);
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( v7 >= 0 )
    {
      *((_DWORD *)v6 + 16) = 2;
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v14,
        "HeartbeatMonitor_CollectHangDump");
      v14[0] = &CmTraceProvider::HeartbeatMonitor_CollectHangDump::`vftable';
      CmTraceProvider::HeartbeatMonitor_CollectHangDump::StartActivity(
        (CmTraceProvider::HeartbeatMonitor_CollectHangDump *)v14,
        &v13);
      v10 = Container::Manager::Core::Details::HeartbeatMonitor::CollectHangDump(
              v9,
              (const struct Container::Manager::Core::Details::ContainerHeartbeatContext *)v6);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v14,
        (unsigned int)v10);
      AcquireSRWLockExclusive(SRWLock);
      GetCurrentThreadId();
      *((_DWORD *)v6 + 16) = ((v10 >> 31) & 1) + 3;
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
      v11 = v12;
      if ( v12 )
      {
        Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v12);
        operator delete(v11, (const struct std::nothrow_t *)0x28);
      }
      AcquireSRWLockExclusive(SRWLock);
      LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
      v14[0] = &CmTraceProvider::HeartbeatMonitor_CollectHangDump::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v14);
    }
    else
    {
      v8 = v12;
      if ( v12 )
      {
        Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v12);
        operator delete(v8, (const struct std::nothrow_t *)0x28);
      }
    }
  }
  LODWORD(SRWLock[2].Ptr) &= ~0x10u;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(SRWLock);
  }
}

```

## disassembly

```asm
0x180076d7c  push    rbp
0x180076d7e  push    rbx
0x180076d7f  push    rsi
0x180076d80  push    rdi
0x180076d81  push    r13
0x180076d83  push    r14
0x180076d85  lea     rbp, [rsp-0A8h]
0x180076d8d  sub     rsp, 1A8h
0x180076d94  mov     rax, cs:__security_cookie
0x180076d9b  xor     rax, rsp
0x180076d9e  mov     [rbp+0D0h+var_40], rax
0x180076da5  mov     rdi, rcx
0x180076da8  call    cs:__imp_AcquireSRWLockExclusive
0x180076daf  nop     dword ptr [rax+rax+00h]
0x180076db4  call    cs:__imp_GetCurrentThreadId
0x180076dbb  nop     dword ptr [rax+rax+00h]
0x180076dc0  mov     [rdi+8], eax
0x180076dc3  lea     rsi, [rdi+38h]
0x180076dc7  lea     r13, ??_7HeartbeatMonitor_CollectHangDump@CmTraceProvider@@6B@; const CmTraceProvider::HeartbeatMonitor_CollectHangDump::`vftable'
0x180076dce  mov     rax, [rsi]
0x180076dd1  cmp     rax, rsi
0x180076dd4  jz      loc_180076F91
0x180076dda  mov     rcx, [rax]
0x180076ddd  cmp     [rcx+8], rax
0x180076de1  jnz     loc_180076F8A
0x180076de7  mov     rdx, [rax+8]
0x180076deb  cmp     [rdx], rax
0x180076dee  jnz     loc_180076F8A
0x180076df4  lea     r14, [rax-10h]
0x180076df8  mov     [rdx], rcx
0x180076dfb  mov     [rcx+8], rdx
0x180076dff  xorps   xmm0, xmm0
0x180076e02  movups  xmmword ptr [rax], xmm0
0x180076e05  mov     rax, [r14+20h]
0x180076e09  movups  xmm0, xmmword ptr [rax]
0x180076e0c  movdqu  xmmword ptr [rsp+1D0h+var_1A0.Data1], xmm0
0x180076e12  test    rdi, rdi
0x180076e15  jz      short loc_180076E2D
0x180076e17  mov     dword ptr [rdi+8], 0
0x180076e1e  mov     rcx, rdi; SRWLock
0x180076e21  call    cs:__imp_ReleaseSRWLockExclusive
0x180076e28  nop     dword ptr [rax+rax+00h]
0x180076e2d  mov     [rsp+1D0h+var_1B0], 0
0x180076e36  lea     r8, [rsp+1D0h+var_1B0]
0x180076e3b  mov     edx, 1
0x180076e40  lea     rcx, [rsp+1D0h+var_1A0]
0x180076e45  call    ?OpenInProcClientContainerHandle@Details@Core@Manager@Container@@YAJAEBU_GUID@@W4_CMS_CLIENT_ID@@AEAV?$unique_ptr@VInProcClientContainerHandle@Details@Core@Manager@Container@@U?$default_delete@VInProcClientContainerHandle@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::OpenInProcClientContainerHandle(_GUID const &,_CMS_CLIENT_ID,wistd::unique_ptr<Container::Manager::Core::Details::InProcClientContainerHandle,wistd::default_delete<Container::Manager::Core::Details::InProcClientContainerHandle>> &)
0x180076e4a  mov     ebx, eax
0x180076e4c  mov     rcx, rdi; SRWLock
0x180076e4f  call    cs:__imp_AcquireSRWLockExclusive
0x180076e56  nop     dword ptr [rax+rax+00h]
0x180076e5b  call    cs:__imp_GetCurrentThreadId
0x180076e62  nop     dword ptr [rax+rax+00h]
0x180076e67  mov     [rdi+8], eax
0x180076e6a  test    ebx, ebx
0x180076e6c  jns     short loc_180076E96
0x180076e6e  mov     rbx, [rsp+1D0h+var_1B0]
0x180076e73  test    rbx, rbx
0x180076e76  jz      loc_180076DCE
0x180076e7c  mov     rcx, rbx; this
0x180076e7f  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x180076e84  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180076e89  mov     rcx, rbx; void *
0x180076e8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076e91  jmp     loc_180076DCE
0x180076e96  mov     dword ptr [r14+40h], 2
0x180076e9e  mov     dword ptr [rdi+8], 0
0x180076ea5  mov     rcx, rdi; SRWLock
0x180076ea8  call    cs:__imp_ReleaseSRWLockExclusive
0x180076eaf  nop     dword ptr [rax+rax+00h]
0x180076eb4  nop
0x180076eb5  lea     rdx, aHeartbeatmonit; "HeartbeatMonitor_CollectHangDump"
0x180076ebc  lea     rcx, [rsp+1D0h+var_190]
0x180076ec1  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180076ec6  mov     [rsp+1D0h+var_190], r13
0x180076ecb  lea     rdx, [rsp+1D0h+var_1A0]; struct _GUID *
0x180076ed0  lea     rcx, [rsp+1D0h+var_190]; this
0x180076ed5  call    ?StartActivity@HeartbeatMonitor_CollectHangDump@CmTraceProvider@@QEAAXAEBU_GUID@@@Z; CmTraceProvider::HeartbeatMonitor_CollectHangDump::StartActivity(_GUID const &)
0x180076eda  nop
0x180076edb  mov     rdx, r14; struct Container::Manager::Core::Details::ContainerHeartbeatContext *
0x180076ede  call    ?CollectHangDump@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAJAEBUContainerHeartbeatContext@2345@@Z; Container::Manager::Core::Details::HeartbeatMonitor::CollectHangDump(Container::Manager::Core::Details::ContainerHeartbeatContext const &)
0x180076ee3  mov     ebx, eax
0x180076ee5  mov     edx, eax
0x180076ee7  lea     rcx, [rsp+1D0h+var_190]
0x180076eec  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180076ef1  mov     rcx, rdi; SRWLock
0x180076ef4  call    cs:__imp_AcquireSRWLockExclusive
0x180076efb  nop     dword ptr [rax+rax+00h]
0x180076f00  call    cs:__imp_GetCurrentThreadId
0x180076f07  nop     dword ptr [rax+rax+00h]
0x180076f0c  sar     ebx, 1Fh
0x180076f0f  and     ebx, 1
0x180076f12  add     ebx, 3
0x180076f15  mov     [r14+40h], ebx
0x180076f19  mov     dword ptr [rdi+8], 0
0x180076f20  mov     rcx, rdi; SRWLock
0x180076f23  call    cs:__imp_ReleaseSRWLockExclusive
0x180076f2a  nop     dword ptr [rax+rax+00h]
0x180076f2f  mov     rbx, [rsp+1D0h+var_1B0]
0x180076f34  test    rbx, rbx
0x180076f37  jz      short loc_180076F4E
0x180076f39  mov     rcx, rbx; this
0x180076f3c  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x180076f41  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180076f46  mov     rcx, rbx; void *
0x180076f49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076f4e  mov     rcx, rdi; SRWLock
0x180076f51  call    cs:__imp_AcquireSRWLockExclusive
0x180076f58  nop     dword ptr [rax+rax+00h]
0x180076f5d  call    cs:__imp_GetCurrentThreadId
0x180076f64  nop     dword ptr [rax+rax+00h]
0x180076f69  mov     [rdi+8], eax
0x180076f6c  mov     [rsp+1D0h+var_190], r13
0x180076f71  lea     rcx, [rsp+1D0h+var_190]
0x180076f76  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180076f7b  lea     rcx, [rsp+1D0h+var_190]
0x180076f80  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180076f85  jmp     loc_180076DCE
0x180076f8a  mov     ecx, 3
0x180076f8f  int     29h; Win8: RtlFailFast(ecx)
0x180076f91  and     dword ptr [rdi+10h], 0FFFFFFEFh
0x180076f95  test    rdi, rdi
0x180076f98  jz      short loc_180076FB1
0x180076f9a  mov     dword ptr [rdi+8], 0
0x180076fa1  mov     rcx, rdi; SRWLock
0x180076fa4  call    cs:__imp_ReleaseSRWLockExclusive
0x180076fab  nop     dword ptr [rax+rax+00h]
0x180076fb0  nop
0x180076fb1  mov     rcx, [rbp+0D0h+var_40]
0x180076fb8  xor     rcx, rsp; StackCookie
0x180076fbb  call    __security_check_cookie
0x180076fc0  add     rsp, 1A8h
0x180076fc7  pop     r14
0x180076fc9  pop     r13
0x180076fcb  pop     rdi
0x180076fcc  pop     rsi
0x180076fcd  pop     rbx
0x180076fce  pop     rbp
0x180076fcf  retn
```
