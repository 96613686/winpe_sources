# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000eb80`
- end: `0x18000ec14`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000eb58`

## callees

- `0x18000cad8`
- `0x18000eb80`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eb9a`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *); // rax
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
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    v3->Ptr = 0;
    if ( v5
      || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v5(
        this + 12,
        `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
        this);
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
0x18000eb80  mov     [rsp+arg_8], rbx
0x18000eb85  push    rdi
0x18000eb86  sub     rsp, 20h
0x18000eb8a  mov     eax, [rcx]
0x18000eb8c  mov     rdi, rcx
0x18000eb8f  test    eax, eax
0x18000eb91  jz      short loc_18000EC07
0x18000eb93  lea     rbx, [rcx+8]
0x18000eb97  mov     rcx, rbx; SRWLock
0x18000eb9a  call    cs:__imp_AcquireSRWLockExclusive
0x18000eba0  mov     [rsp+28h+arg_0], rbx
0x18000eba5  lea     rbx, [rdi+60h]
0x18000eba9  cmp     qword ptr [rbx], 0
0x18000ebad  jz      short loc_18000EBB5
0x18000ebaf  mov     ebx, [rdi+1Ch]
0x18000ebb2  nop
0x18000ebb3  jmp     short loc_18000EBF9
0x18000ebb5  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ebbc  mov     qword ptr [rbx], 0
0x18000ebc3  test    rax, rax
0x18000ebc6  jnz     short loc_18000EBD4
0x18000ebc8  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ebcf  test    rax, rax
0x18000ebd2  jz      short loc_18000EBE6
0x18000ebd4  mov     r8, rdi
0x18000ebd7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000ebde  mov     rcx, rbx
0x18000ebe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe6  cmp     qword ptr [rbx], 0
0x18000ebea  jnz     short loc_18000EBF0
0x18000ebec  xor     ebx, ebx
0x18000ebee  jmp     short loc_18000EBF9
0x18000ebf0  mov     ebx, 1
0x18000ebf5  nop
0x18000ebf6  mov     [rdi+1Ch], ebx
0x18000ebf9  lea     rcx, [rsp+28h+arg_0]
0x18000ebfe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ec03  mov     eax, ebx
0x18000ec05  jmp     short loc_18000EC09
0x18000ec07  xor     eax, eax
0x18000ec09  mov     rbx, [rsp+28h+arg_8]
0x18000ec0e  add     rsp, 20h
0x18000ec12  pop     rdi
0x18000ec13  retn
```
