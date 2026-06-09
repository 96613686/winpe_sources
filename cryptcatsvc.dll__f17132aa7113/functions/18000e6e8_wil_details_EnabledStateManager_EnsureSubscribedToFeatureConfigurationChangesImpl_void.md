# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000e6e8`
- end: `0x18000e786`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `158`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e6c0`

## callees

- `0x18000b5ec`
- `0x18000e6e8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e70c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e70c`

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
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v7[1] = -2;
  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v7[0] = v2;
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
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v7);
  return Ptr_high;
}

```

## disassembly

```asm
0x18000e6e8  push    rdi
0x18000e6ea  sub     rsp, 30h
0x18000e6ee  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x18000e6f7  mov     [rsp+38h+arg_8], rbx
0x18000e6fc  mov     rdi, rcx
0x18000e6ff  mov     eax, [rcx]
0x18000e701  test    eax, eax
0x18000e703  jz      short loc_18000E779
0x18000e705  lea     rbx, [rcx+8]
0x18000e709  mov     rcx, rbx; SRWLock
0x18000e70c  call    cs:__imp_AcquireSRWLockExclusive
0x18000e712  mov     [rsp+38h+var_18], rbx
0x18000e717  lea     rbx, [rdi+60h]
0x18000e71b  cmp     qword ptr [rbx], 0
0x18000e71f  jz      short loc_18000E727
0x18000e721  mov     ebx, [rdi+1Ch]
0x18000e724  nop
0x18000e725  jmp     short loc_18000E76B
0x18000e727  mov     qword ptr [rbx], 0
0x18000e72e  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000e735  test    rax, rax
0x18000e738  jnz     short loc_18000E746
0x18000e73a  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000e741  test    rax, rax
0x18000e744  jz      short loc_18000E758
0x18000e746  mov     r8, rdi
0x18000e749  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000e750  mov     rcx, rbx
0x18000e753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e758  cmp     qword ptr [rbx], 0
0x18000e75c  jnz     short loc_18000E762
0x18000e75e  xor     ebx, ebx
0x18000e760  jmp     short loc_18000E76B
0x18000e762  nop
0x18000e763  mov     ebx, 1
0x18000e768  mov     [rdi+1Ch], ebx
0x18000e76b  lea     rcx, [rsp+38h+var_18]
0x18000e770  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e775  mov     eax, ebx
0x18000e777  jmp     short loc_18000E77B
0x18000e779  xor     eax, eax
0x18000e77b  mov     rbx, [rsp+38h+arg_8]
0x18000e780  add     rsp, 30h
0x18000e784  pop     rdi
0x18000e785  retn
```
