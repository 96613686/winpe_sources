# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005248`
- end: `0x1800052cb`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `131`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005598`
- `0x18000705c`
- `0x180008104`

## callees

- `0x1800046d0`
- `0x1800048f8`
- `0x180004be4`
- `0x180005248`
- `0x180005c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005289`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005289`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 Shared; // rsi
  bool v3; // zf
  RTL_SRWLOCK *v5; // [rsp+30h] [rbp+8h] BYREF
  char v6; // [rsp+38h] [rbp+10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    if ( this[3].Ptr )
      Shared = 0;
    else
      Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(&this[1]);
    AcquireSRWLockExclusive(this + 4);
    v3 = this[3].Ptr == 0;
    v5 = this + 4;
    if ( v3 )
      this[3].Ptr = (PVOID)Shared;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180005248  mov     [rsp+arg_10], rbx
0x18000524d  mov     [rsp+arg_18], rsi
0x180005252  push    rdi
0x180005253  sub     rsp, 20h
0x180005257  cmp     qword ptr [rcx+18h], 0
0x18000525c  mov     rdi, rcx
0x18000525f  jnz     short loc_1800052B3
0x180005261  lea     rcx, [rsp+28h+arg_8]; this
0x180005266  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000526b  cmp     qword ptr [rdi+18h], 0
0x180005270  jz      short loc_180005276
0x180005272  xor     esi, esi
0x180005274  jmp     short loc_180005282
0x180005276  lea     rcx, [rdi+8]
0x18000527a  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x18000527f  mov     rsi, rax
0x180005282  lea     rbx, [rdi+20h]
0x180005286  mov     rcx, rbx; SRWLock
0x180005289  call    cs:__imp_AcquireSRWLockExclusive
0x18000528f  cmp     qword ptr [rdi+18h], 0
0x180005294  mov     [rsp+28h+arg_0], rbx
0x180005299  jnz     short loc_18000529F
0x18000529b  mov     [rdi+18h], rsi
0x18000529f  lea     rcx, [rsp+28h+arg_0]
0x1800052a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800052a9  lea     rcx, [rsp+28h+arg_8]; this
0x1800052ae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800052b3  cmp     qword ptr [rdi+18h], 0
0x1800052b8  mov     rbx, [rsp+28h+arg_10]
0x1800052bd  mov     rsi, [rsp+28h+arg_18]
0x1800052c2  setnz   al
0x1800052c5  add     rsp, 20h
0x1800052c9  pop     rdi
0x1800052ca  retn
```
