# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180011a20`
- end: `0x180011ab4`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001fc20`

## callees

- `0x180011a20`
- `0x180011c60`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011a3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011a3a`

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
0x180011a20  mov     [rsp+arg_8], rbx
0x180011a25  push    rdi
0x180011a26  sub     rsp, 20h
0x180011a2a  mov     rdi, rcx
0x180011a2d  mov     eax, [rcx]
0x180011a2f  test    eax, eax
0x180011a31  jz      short loc_180011AA7
0x180011a33  lea     rbx, [rcx+8]
0x180011a37  mov     rcx, rbx; SRWLock
0x180011a3a  call    cs:__imp_AcquireSRWLockExclusive
0x180011a40  mov     [rsp+28h+arg_0], rbx
0x180011a45  lea     rbx, [rdi+60h]
0x180011a49  cmp     qword ptr [rbx], 0
0x180011a4d  jz      short loc_180011A55
0x180011a4f  mov     ebx, [rdi+1Ch]
0x180011a52  nop
0x180011a53  jmp     short loc_180011A99
0x180011a55  mov     qword ptr [rbx], 0
0x180011a5c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180011a63  test    rax, rax
0x180011a66  jnz     short loc_180011A74
0x180011a68  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180011a6f  test    rax, rax
0x180011a72  jz      short loc_180011A86
0x180011a74  mov     r8, rdi
0x180011a77  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180011a7e  mov     rcx, rbx
0x180011a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a86  cmp     qword ptr [rbx], 0
0x180011a8a  jnz     short loc_180011A90
0x180011a8c  xor     ebx, ebx
0x180011a8e  jmp     short loc_180011A99
0x180011a90  nop
0x180011a91  mov     ebx, 1
0x180011a96  mov     [rdi+1Ch], ebx
0x180011a99  lea     rcx, [rsp+28h+arg_0]
0x180011a9e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011aa3  mov     eax, ebx
0x180011aa5  jmp     short loc_180011AA9
0x180011aa7  xor     eax, eax
0x180011aa9  mov     rbx, [rsp+28h+arg_8]
0x180011aae  add     rsp, 20h
0x180011ab2  pop     rdi
0x180011ab3  retn
```
