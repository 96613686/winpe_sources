# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800084d0`
- end: `0x180008564`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800084a8`

## callees

- `0x180007984`
- `0x1800084d0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084ea`

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
0x1800084d0  mov     [rsp+arg_8], rbx
0x1800084d5  push    rdi
0x1800084d6  sub     rsp, 20h
0x1800084da  mov     rdi, rcx
0x1800084dd  mov     eax, [rcx]
0x1800084df  test    eax, eax
0x1800084e1  jz      short loc_180008557
0x1800084e3  lea     rbx, [rcx+8]
0x1800084e7  mov     rcx, rbx; SRWLock
0x1800084ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800084f0  mov     [rsp+28h+arg_0], rbx
0x1800084f5  lea     rbx, [rdi+60h]
0x1800084f9  cmp     qword ptr [rbx], 0
0x1800084fd  jz      short loc_180008505
0x1800084ff  mov     ebx, [rdi+1Ch]
0x180008502  nop
0x180008503  jmp     short loc_180008549
0x180008505  mov     qword ptr [rbx], 0
0x18000850c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008513  test    rax, rax
0x180008516  jnz     short loc_180008524
0x180008518  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000851f  test    rax, rax
0x180008522  jz      short loc_180008536
0x180008524  mov     r8, rdi
0x180008527  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000852e  mov     rcx, rbx
0x180008531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008536  cmp     qword ptr [rbx], 0
0x18000853a  jnz     short loc_180008540
0x18000853c  xor     ebx, ebx
0x18000853e  jmp     short loc_180008549
0x180008540  nop
0x180008541  mov     ebx, 1
0x180008546  mov     [rdi+1Ch], ebx
0x180008549  lea     rcx, [rsp+28h+arg_0]
0x18000854e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008553  mov     eax, ebx
0x180008555  jmp     short loc_180008559
0x180008557  xor     eax, eax
0x180008559  mov     rbx, [rsp+28h+arg_8]
0x18000855e  add     rsp, 20h
0x180008562  pop     rdi
0x180008563  retn
```
