# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::MinUpdateInterval(std::chrono::duration<__int64,std::ratio<1,10000000>>)

- ea: `0x18001d3b8`
- end: `0x18001d42a`
- name: `?MinUpdateInterval@GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@QEAAXV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18001de40`
- `0x18001de70`

## callees

- `0x180007c28`
- `0x18001c1bc`
- `0x18001ca30`
- `0x18001d3b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d3d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d3d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::MinUpdateInterval(
        RTL_SRWLOCK *this,
        PVOID a2)
{
  RTL_SRWLOCK *v4; // rdi
  unsigned int *v5; // rax
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+38h] [rbp+10h] BYREF

  v4 = this + 11;
  AcquireSRWLockExclusive(this + 11);
  v7 = v4;
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::CheckClosed((winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession *)this);
  if ( a2 != this[15].Ptr )
  {
    this[15].Ptr = a2;
    v5 = (unsigned int *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1000>>,__int64,std::ratio<1,10000000>,0>(&v8);
    (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[14].Ptr + 48LL))(this[14].Ptr, *v5);
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x18001d3b8  mov     [rsp+arg_10], rbx
0x18001d3bd  mov     [rsp+arg_18], rsi
0x18001d3c2  push    rdi
0x18001d3c3  sub     rsp, 20h
0x18001d3c7  mov     rbx, rdx
0x18001d3ca  mov     rsi, rcx
0x18001d3cd  lea     rdi, [rcx+58h]
0x18001d3d1  mov     rcx, rdi; SRWLock
0x18001d3d4  call    cs:__imp_AcquireSRWLockExclusive
0x18001d3da  mov     [rsp+28h+arg_0], rdi
0x18001d3df  mov     rcx, rsi; this
0x18001d3e2  call    ?CheckClosed@GraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession::CheckClosed(void)
0x18001d3e7  lea     rdx, [rsi+78h]
0x18001d3eb  cmp     rbx, [rdx]
0x18001d3ee  jz      short loc_18001D410
0x18001d3f0  mov     [rdx], rbx
0x18001d3f3  lea     rcx, [rsp+28h+arg_8]
0x18001d3f8  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$0DOI@@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1000>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18001d3fd  mov     rcx, [rsi+70h]
0x18001d401  mov     r8, [rcx]
0x18001d404  mov     edx, [rax]
0x18001d406  mov     rax, [r8+30h]
0x18001d40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40f  nop
0x18001d410  lea     rcx, [rsp+28h+arg_0]
0x18001d415  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d41a  mov     rbx, [rsp+28h+arg_10]
0x18001d41f  mov     rsi, [rsp+28h+arg_18]
0x18001d424  add     rsp, 20h
0x18001d428  pop     rdi
0x18001d429  retn
```
