# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800052fc`
- end: `0x180005390`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800052d4`

## callees

- `0x1800048f8`
- `0x1800052fc`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005316`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005316`

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
0x1800052fc  mov     [rsp+arg_8], rbx
0x180005301  push    rdi
0x180005302  sub     rsp, 20h
0x180005306  mov     eax, [rcx]
0x180005308  mov     rdi, rcx
0x18000530b  test    eax, eax
0x18000530d  jz      short loc_180005383
0x18000530f  lea     rbx, [rcx+8]
0x180005313  mov     rcx, rbx; SRWLock
0x180005316  call    cs:__imp_AcquireSRWLockExclusive
0x18000531c  mov     [rsp+28h+arg_0], rbx
0x180005321  lea     rbx, [rdi+60h]
0x180005325  cmp     qword ptr [rbx], 0
0x180005329  jz      short loc_180005331
0x18000532b  mov     ebx, [rdi+1Ch]
0x18000532e  nop
0x18000532f  jmp     short loc_180005375
0x180005331  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005338  mov     qword ptr [rbx], 0
0x18000533f  test    rax, rax
0x180005342  jnz     short loc_180005350
0x180005344  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000534b  test    rax, rax
0x18000534e  jz      short loc_180005362
0x180005350  mov     r8, rdi
0x180005353  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000535a  mov     rcx, rbx
0x18000535d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005362  cmp     qword ptr [rbx], 0
0x180005366  jnz     short loc_18000536C
0x180005368  xor     ebx, ebx
0x18000536a  jmp     short loc_180005375
0x18000536c  mov     ebx, 1
0x180005371  nop
0x180005372  mov     [rdi+1Ch], ebx
0x180005375  lea     rcx, [rsp+28h+arg_0]
0x18000537a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000537f  mov     eax, ebx
0x180005381  jmp     short loc_180005385
0x180005383  xor     eax, eax
0x180005385  mov     rbx, [rsp+28h+arg_8]
0x18000538a  add     rsp, 20h
0x18000538e  pop     rdi
0x18000538f  retn
```
