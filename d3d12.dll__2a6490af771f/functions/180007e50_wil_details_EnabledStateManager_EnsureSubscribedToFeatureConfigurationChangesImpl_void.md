# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180007e50`
- end: `0x180007ee4`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007e28`

## callees

- `0x180007e50`
- `0x18000a1e4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e6a`

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
0x180007e50  mov     [rsp+arg_8], rbx
0x180007e55  push    rdi
0x180007e56  sub     rsp, 20h
0x180007e5a  mov     rdi, rcx
0x180007e5d  mov     eax, [rcx]
0x180007e5f  test    eax, eax
0x180007e61  jz      short loc_180007ED7
0x180007e63  lea     rbx, [rcx+8]
0x180007e67  mov     rcx, rbx; SRWLock
0x180007e6a  call    cs:__imp_AcquireSRWLockExclusive
0x180007e70  mov     [rsp+28h+arg_0], rbx
0x180007e75  lea     rbx, [rdi+60h]
0x180007e79  cmp     qword ptr [rbx], 0
0x180007e7d  jz      short loc_180007E85
0x180007e7f  mov     ebx, [rdi+1Ch]
0x180007e82  nop
0x180007e83  jmp     short loc_180007EC9
0x180007e85  mov     qword ptr [rbx], 0
0x180007e8c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007e93  test    rax, rax
0x180007e96  jnz     short loc_180007EA4
0x180007e98  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007e9f  test    rax, rax
0x180007ea2  jz      short loc_180007EB6
0x180007ea4  mov     r8, rdi
0x180007ea7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180007eae  mov     rcx, rbx
0x180007eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb6  cmp     qword ptr [rbx], 0
0x180007eba  jnz     short loc_180007EC0
0x180007ebc  xor     ebx, ebx
0x180007ebe  jmp     short loc_180007EC9
0x180007ec0  nop
0x180007ec1  mov     ebx, 1
0x180007ec6  mov     [rdi+1Ch], ebx
0x180007ec9  lea     rcx, [rsp+28h+arg_0]
0x180007ece  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007ed3  mov     eax, ebx
0x180007ed5  jmp     short loc_180007ED9
0x180007ed7  xor     eax, eax
0x180007ed9  mov     rbx, [rsp+28h+arg_8]
0x180007ede  add     rsp, 20h
0x180007ee2  pop     rdi
0x180007ee3  retn
```
