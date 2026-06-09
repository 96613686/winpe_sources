# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18003b334`
- end: `0x18003b3c8`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003b30c`

## callees

- `0x18003af20`
- `0x18003b334`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b34e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b34e`

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
0x18003b334  mov     [rsp+arg_8], rbx
0x18003b339  push    rdi
0x18003b33a  sub     rsp, 20h
0x18003b33e  mov     eax, [rcx]
0x18003b340  mov     rdi, rcx
0x18003b343  test    eax, eax
0x18003b345  jz      short loc_18003B3BB
0x18003b347  lea     rbx, [rcx+8]
0x18003b34b  mov     rcx, rbx; SRWLock
0x18003b34e  call    cs:__imp_AcquireSRWLockExclusive
0x18003b354  mov     [rsp+28h+arg_0], rbx
0x18003b359  lea     rbx, [rdi+60h]
0x18003b35d  cmp     qword ptr [rbx], 0
0x18003b361  jz      short loc_18003B369
0x18003b363  mov     ebx, [rdi+1Ch]
0x18003b366  nop
0x18003b367  jmp     short loc_18003B3AD
0x18003b369  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18003b370  mov     qword ptr [rbx], 0
0x18003b377  test    rax, rax
0x18003b37a  jnz     short loc_18003B388
0x18003b37c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18003b383  test    rax, rax
0x18003b386  jz      short loc_18003B39A
0x18003b388  mov     r8, rdi
0x18003b38b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18003b392  mov     rcx, rbx
0x18003b395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b39a  cmp     qword ptr [rbx], 0
0x18003b39e  jnz     short loc_18003B3A4
0x18003b3a0  xor     ebx, ebx
0x18003b3a2  jmp     short loc_18003B3AD
0x18003b3a4  mov     ebx, 1
0x18003b3a9  nop
0x18003b3aa  mov     [rdi+1Ch], ebx
0x18003b3ad  lea     rcx, [rsp+28h+arg_0]
0x18003b3b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003b3b7  mov     eax, ebx
0x18003b3b9  jmp     short loc_18003B3BD
0x18003b3bb  xor     eax, eax
0x18003b3bd  mov     rbx, [rsp+28h+arg_8]
0x18003b3c2  add     rsp, 20h
0x18003b3c6  pop     rdi
0x18003b3c7  retn
```
