# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180028adc`
- end: `0x180028b70`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028ab4`

## callees

- `0x180027a6c`
- `0x180028adc`
- `0x180034010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180028af6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180028af6`

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
0x180028adc  mov     [rsp+arg_8], rbx
0x180028ae1  push    rdi
0x180028ae2  sub     rsp, 20h
0x180028ae6  mov     rdi, rcx
0x180028ae9  mov     eax, [rcx]
0x180028aeb  test    eax, eax
0x180028aed  jz      short loc_180028B63
0x180028aef  lea     rbx, [rcx+8]
0x180028af3  mov     rcx, rbx; SRWLock
0x180028af6  call    cs:__imp_AcquireSRWLockExclusive
0x180028afc  mov     [rsp+28h+arg_0], rbx
0x180028b01  lea     rbx, [rdi+60h]
0x180028b05  cmp     qword ptr [rbx], 0
0x180028b09  jz      short loc_180028B11
0x180028b0b  mov     ebx, [rdi+1Ch]
0x180028b0e  nop
0x180028b0f  jmp     short loc_180028B55
0x180028b11  mov     qword ptr [rbx], 0
0x180028b18  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180028b1f  test    rax, rax
0x180028b22  jnz     short loc_180028B30
0x180028b24  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180028b2b  test    rax, rax
0x180028b2e  jz      short loc_180028B42
0x180028b30  mov     r8, rdi
0x180028b33  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180028b3a  mov     rcx, rbx
0x180028b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b42  cmp     qword ptr [rbx], 0
0x180028b46  jnz     short loc_180028B4C
0x180028b48  xor     ebx, ebx
0x180028b4a  jmp     short loc_180028B55
0x180028b4c  nop
0x180028b4d  mov     ebx, 1
0x180028b52  mov     [rdi+1Ch], ebx
0x180028b55  lea     rcx, [rsp+28h+arg_0]
0x180028b5a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028b5f  mov     eax, ebx
0x180028b61  jmp     short loc_180028B65
0x180028b63  xor     eax, eax
0x180028b65  mov     rbx, [rsp+28h+arg_8]
0x180028b6a  add     rsp, 20h
0x180028b6e  pop     rdi
0x180028b6f  retn
```
