# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180012c18`
- end: `0x180012cac`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012bf0`

## callees

- `0x18000acac`
- `0x180012c18`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012c32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012c32`

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
0x180012c18  mov     [rsp+arg_8], rbx
0x180012c1d  push    rdi
0x180012c1e  sub     rsp, 20h
0x180012c22  mov     rdi, rcx
0x180012c25  mov     eax, [rcx]
0x180012c27  test    eax, eax
0x180012c29  jz      short loc_180012C9F
0x180012c2b  lea     rbx, [rcx+8]
0x180012c2f  mov     rcx, rbx; SRWLock
0x180012c32  call    cs:__imp_AcquireSRWLockExclusive
0x180012c38  mov     [rsp+28h+arg_0], rbx
0x180012c3d  lea     rbx, [rdi+60h]
0x180012c41  cmp     qword ptr [rbx], 0
0x180012c45  jz      short loc_180012C4D
0x180012c47  mov     ebx, [rdi+1Ch]
0x180012c4a  nop
0x180012c4b  jmp     short loc_180012C91
0x180012c4d  mov     qword ptr [rbx], 0
0x180012c54  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180012c5b  test    rax, rax
0x180012c5e  jnz     short loc_180012C6C
0x180012c60  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180012c67  test    rax, rax
0x180012c6a  jz      short loc_180012C7E
0x180012c6c  mov     r8, rdi
0x180012c6f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180012c76  mov     rcx, rbx
0x180012c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c7e  cmp     qword ptr [rbx], 0
0x180012c82  jnz     short loc_180012C88
0x180012c84  xor     ebx, ebx
0x180012c86  jmp     short loc_180012C91
0x180012c88  nop
0x180012c89  mov     ebx, 1
0x180012c8e  mov     [rdi+1Ch], ebx
0x180012c91  lea     rcx, [rsp+28h+arg_0]
0x180012c96  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012c9b  mov     eax, ebx
0x180012c9d  jmp     short loc_180012CA1
0x180012c9f  xor     eax, eax
0x180012ca1  mov     rbx, [rsp+28h+arg_8]
0x180012ca6  add     rsp, 20h
0x180012caa  pop     rdi
0x180012cab  retn
```
