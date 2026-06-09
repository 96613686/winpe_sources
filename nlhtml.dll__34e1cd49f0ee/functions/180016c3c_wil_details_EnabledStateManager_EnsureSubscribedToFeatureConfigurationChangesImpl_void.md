# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180016c3c`
- end: `0x180016cd0`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016c14`

## callees

- `0x180016120`
- `0x180016c3c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c56`

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
0x180016c3c  mov     [rsp+arg_8], rbx
0x180016c41  push    rdi
0x180016c42  sub     rsp, 20h
0x180016c46  mov     rdi, rcx
0x180016c49  mov     eax, [rcx]
0x180016c4b  test    eax, eax
0x180016c4d  jz      short loc_180016CC3
0x180016c4f  lea     rbx, [rcx+8]
0x180016c53  mov     rcx, rbx; SRWLock
0x180016c56  call    cs:__imp_AcquireSRWLockExclusive
0x180016c5c  mov     [rsp+28h+arg_0], rbx
0x180016c61  lea     rbx, [rdi+60h]
0x180016c65  cmp     qword ptr [rbx], 0
0x180016c69  jz      short loc_180016C71
0x180016c6b  mov     ebx, [rdi+1Ch]
0x180016c6e  nop
0x180016c6f  jmp     short loc_180016CB5
0x180016c71  mov     qword ptr [rbx], 0
0x180016c78  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180016c7f  test    rax, rax
0x180016c82  jnz     short loc_180016C90
0x180016c84  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180016c8b  test    rax, rax
0x180016c8e  jz      short loc_180016CA2
0x180016c90  mov     r8, rdi
0x180016c93  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180016c9a  mov     rcx, rbx
0x180016c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ca2  cmp     qword ptr [rbx], 0
0x180016ca6  jnz     short loc_180016CAC
0x180016ca8  xor     ebx, ebx
0x180016caa  jmp     short loc_180016CB5
0x180016cac  nop
0x180016cad  mov     ebx, 1
0x180016cb2  mov     [rdi+1Ch], ebx
0x180016cb5  lea     rcx, [rsp+28h+arg_0]
0x180016cba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016cbf  mov     eax, ebx
0x180016cc1  jmp     short loc_180016CC5
0x180016cc3  xor     eax, eax
0x180016cc5  mov     rbx, [rsp+28h+arg_8]
0x180016cca  add     rsp, 20h
0x180016cce  pop     rdi
0x180016ccf  retn
```
