# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180011110`
- end: `0x1800111a4`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800110e8`

## callees

- `0x18000df10`
- `0x180011110`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001112a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001112a`

## pseudocode

```c
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
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    v3->Ptr = 0;
    if ( v5
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
0x180011110  mov     [rsp+arg_8], rbx
0x180011115  push    rdi
0x180011116  sub     rsp, 20h
0x18001111a  mov     eax, [rcx]
0x18001111c  mov     rdi, rcx
0x18001111f  test    eax, eax
0x180011121  jz      short loc_180011197
0x180011123  lea     rbx, [rcx+8]
0x180011127  mov     rcx, rbx; SRWLock
0x18001112a  call    cs:__imp_AcquireSRWLockExclusive
0x180011130  mov     [rsp+28h+arg_0], rbx
0x180011135  lea     rbx, [rdi+60h]
0x180011139  cmp     qword ptr [rbx], 0
0x18001113d  jz      short loc_180011145
0x18001113f  mov     ebx, [rdi+1Ch]
0x180011142  nop
0x180011143  jmp     short loc_180011189
0x180011145  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001114c  mov     qword ptr [rbx], 0
0x180011153  test    rax, rax
0x180011156  jnz     short loc_180011164
0x180011158  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001115f  test    rax, rax
0x180011162  jz      short loc_180011176
0x180011164  mov     r8, rdi
0x180011167  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001116e  mov     rcx, rbx
0x180011171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011176  cmp     qword ptr [rbx], 0
0x18001117a  jnz     short loc_180011180
0x18001117c  xor     ebx, ebx
0x18001117e  jmp     short loc_180011189
0x180011180  mov     ebx, 1
0x180011185  nop
0x180011186  mov     [rdi+1Ch], ebx
0x180011189  lea     rcx, [rsp+28h+arg_0]
0x18001118e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011193  mov     eax, ebx
0x180011195  jmp     short loc_180011199
0x180011197  xor     eax, eax
0x180011199  mov     rbx, [rsp+28h+arg_8]
0x18001119e  add     rsp, 20h
0x1800111a2  pop     rdi
0x1800111a3  retn
```
