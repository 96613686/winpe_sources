# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800279fc`
- end: `0x180027a90`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800279d4`

## callees

- `0x18001f7b4`
- `0x1800279fc`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027a16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027a16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v7 = v2;
  v3 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
  }
  else
  {
    v3->Ptr = 0;
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v5(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
    }
    if ( v3->Ptr )
    {
      Ptr_high = 1;
      HIDWORD(this[3].Ptr) = 1;
    }
    else
    {
      Ptr_high = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  return Ptr_high;
}

```

## disassembly

```asm
0x1800279fc  mov     [rsp+arg_8], rbx
0x180027a01  push    rdi
0x180027a02  sub     rsp, 20h
0x180027a06  mov     rdi, rcx
0x180027a09  mov     eax, [rcx]
0x180027a0b  test    eax, eax
0x180027a0d  jz      short loc_180027A83
0x180027a0f  lea     rbx, [rcx+8]
0x180027a13  mov     rcx, rbx; SRWLock
0x180027a16  call    cs:__imp_AcquireSRWLockExclusive
0x180027a1c  mov     [rsp+28h+arg_0], rbx
0x180027a21  lea     rbx, [rdi+60h]
0x180027a25  cmp     qword ptr [rbx], 0
0x180027a29  jz      short loc_180027A31
0x180027a2b  mov     ebx, [rdi+1Ch]
0x180027a2e  nop
0x180027a2f  jmp     short loc_180027A75
0x180027a31  mov     qword ptr [rbx], 0
0x180027a38  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180027a3f  test    rax, rax
0x180027a42  jnz     short loc_180027A50
0x180027a44  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180027a4b  test    rax, rax
0x180027a4e  jz      short loc_180027A62
0x180027a50  mov     r8, rdi
0x180027a53  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180027a5a  mov     rcx, rbx
0x180027a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a62  cmp     qword ptr [rbx], 0
0x180027a66  jnz     short loc_180027A6C
0x180027a68  xor     ebx, ebx
0x180027a6a  jmp     short loc_180027A75
0x180027a6c  nop
0x180027a6d  mov     ebx, 1
0x180027a72  mov     [rdi+1Ch], ebx
0x180027a75  lea     rcx, [rsp+28h+arg_0]
0x180027a7a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180027a7f  mov     eax, ebx
0x180027a81  jmp     short loc_180027A85
0x180027a83  xor     eax, eax
0x180027a85  mov     rbx, [rsp+28h+arg_8]
0x180027a8a  add     rsp, 20h
0x180027a8e  pop     rdi
0x180027a8f  retn
```
