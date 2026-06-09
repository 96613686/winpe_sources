# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x140006048`
- end: `0x1400060dc`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006020`

## callees

- `0x1400050dc`
- `0x140006048`
- `0x140027010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140006062`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006062`

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
0x140006048  mov     [rsp+arg_8], rbx
0x14000604d  push    rdi
0x14000604e  sub     rsp, 20h
0x140006052  mov     rdi, rcx
0x140006055  mov     eax, [rcx]
0x140006057  test    eax, eax
0x140006059  jz      short loc_1400060CF
0x14000605b  lea     rbx, [rcx+8]
0x14000605f  mov     rcx, rbx; SRWLock
0x140006062  call    cs:__imp_AcquireSRWLockExclusive
0x140006068  mov     [rsp+28h+arg_0], rbx
0x14000606d  lea     rbx, [rdi+60h]
0x140006071  cmp     qword ptr [rbx], 0
0x140006075  jz      short loc_14000607D
0x140006077  mov     ebx, [rdi+1Ch]
0x14000607a  nop
0x14000607b  jmp     short loc_1400060C1
0x14000607d  mov     qword ptr [rbx], 0
0x140006084  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000608b  test    rax, rax
0x14000608e  jnz     short loc_14000609C
0x140006090  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140006097  test    rax, rax
0x14000609a  jz      short loc_1400060AE
0x14000609c  mov     r8, rdi
0x14000609f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1400060a6  mov     rcx, rbx
0x1400060a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060ae  cmp     qword ptr [rbx], 0
0x1400060b2  jnz     short loc_1400060B8
0x1400060b4  xor     ebx, ebx
0x1400060b6  jmp     short loc_1400060C1
0x1400060b8  nop
0x1400060b9  mov     ebx, 1
0x1400060be  mov     [rdi+1Ch], ebx
0x1400060c1  lea     rcx, [rsp+28h+arg_0]
0x1400060c6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400060cb  mov     eax, ebx
0x1400060cd  jmp     short loc_1400060D1
0x1400060cf  xor     eax, eax
0x1400060d1  mov     rbx, [rsp+28h+arg_8]
0x1400060d6  add     rsp, 20h
0x1400060da  pop     rdi
0x1400060db  retn
```
