# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180005538`
- end: `0x1800055cc`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005510`

## callees

- `0x180003fd8`
- `0x180005538`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005552`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005552`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-18h] BYREF

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
0x180005538  mov     [rsp+arg_8], rbx
0x18000553d  push    rdi
0x18000553e  sub     rsp, 30h
0x180005542  mov     eax, [rcx]
0x180005544  mov     rdi, rcx
0x180005547  test    eax, eax
0x180005549  jz      short loc_1800055BF
0x18000554b  lea     rbx, [rcx+8]
0x18000554f  mov     rcx, rbx; SRWLock
0x180005552  call    cs:__imp_AcquireSRWLockExclusive
0x180005558  mov     [rsp+38h+var_18], rbx
0x18000555d  lea     rbx, [rdi+60h]
0x180005561  cmp     qword ptr [rbx], 0
0x180005565  jz      short loc_18000556D
0x180005567  mov     ebx, [rdi+1Ch]
0x18000556a  nop
0x18000556b  jmp     short loc_1800055B1
0x18000556d  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005574  mov     qword ptr [rbx], 0
0x18000557b  test    rax, rax
0x18000557e  jnz     short loc_18000558C
0x180005580  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005587  test    rax, rax
0x18000558a  jz      short loc_18000559E
0x18000558c  mov     r8, rdi
0x18000558f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005596  mov     rcx, rbx
0x180005599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000559e  cmp     qword ptr [rbx], 0
0x1800055a2  jnz     short loc_1800055A8
0x1800055a4  xor     ebx, ebx
0x1800055a6  jmp     short loc_1800055B1
0x1800055a8  mov     ebx, 1
0x1800055ad  nop
0x1800055ae  mov     [rdi+1Ch], ebx
0x1800055b1  lea     rcx, [rsp+38h+var_18]
0x1800055b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800055bb  mov     eax, ebx
0x1800055bd  jmp     short loc_1800055C1
0x1800055bf  xor     eax, eax
0x1800055c1  mov     rbx, [rsp+38h+arg_8]
0x1800055c6  add     rsp, 30h
0x1800055ca  pop     rdi
0x1800055cb  retn
```
