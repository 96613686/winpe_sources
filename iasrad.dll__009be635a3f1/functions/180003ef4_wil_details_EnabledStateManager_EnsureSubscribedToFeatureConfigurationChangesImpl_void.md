# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180003ef4`
- end: `0x180003f88`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003ecc`

## callees

- `0x180003338`
- `0x180003ef4`
- `0x180030010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180003f0e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003f0e`

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
0x180003ef4  mov     [rsp+arg_8], rbx
0x180003ef9  push    rdi
0x180003efa  sub     rsp, 20h
0x180003efe  mov     rdi, rcx
0x180003f01  mov     eax, [rcx]
0x180003f03  test    eax, eax
0x180003f05  jz      short loc_180003F7B
0x180003f07  lea     rbx, [rcx+8]
0x180003f0b  mov     rcx, rbx; SRWLock
0x180003f0e  call    cs:__imp_AcquireSRWLockExclusive
0x180003f14  mov     [rsp+28h+arg_0], rbx
0x180003f19  lea     rbx, [rdi+60h]
0x180003f1d  cmp     qword ptr [rbx], 0
0x180003f21  jz      short loc_180003F29
0x180003f23  mov     ebx, [rdi+1Ch]
0x180003f26  nop
0x180003f27  jmp     short loc_180003F6D
0x180003f29  mov     qword ptr [rbx], 0
0x180003f30  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180003f37  test    rax, rax
0x180003f3a  jnz     short loc_180003F48
0x180003f3c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180003f43  test    rax, rax
0x180003f46  jz      short loc_180003F5A
0x180003f48  mov     r8, rdi
0x180003f4b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180003f52  mov     rcx, rbx
0x180003f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f5a  cmp     qword ptr [rbx], 0
0x180003f5e  jnz     short loc_180003F64
0x180003f60  xor     ebx, ebx
0x180003f62  jmp     short loc_180003F6D
0x180003f64  nop
0x180003f65  mov     ebx, 1
0x180003f6a  mov     [rdi+1Ch], ebx
0x180003f6d  lea     rcx, [rsp+28h+arg_0]
0x180003f72  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180003f77  mov     eax, ebx
0x180003f79  jmp     short loc_180003F7D
0x180003f7b  xor     eax, eax
0x180003f7d  mov     rbx, [rsp+28h+arg_8]
0x180003f82  add     rsp, 20h
0x180003f86  pop     rdi
0x180003f87  retn
```
