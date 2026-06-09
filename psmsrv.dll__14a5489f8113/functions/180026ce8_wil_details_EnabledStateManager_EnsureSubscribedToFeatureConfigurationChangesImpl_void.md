# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180026ce8`
- end: `0x180026d7c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026cc0`

## callees

- `0x18001ae8c`
- `0x180026ce8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026d02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026d02`

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
0x180026ce8  mov     [rsp+arg_8], rbx
0x180026ced  push    rdi
0x180026cee  sub     rsp, 20h
0x180026cf2  mov     eax, [rcx]
0x180026cf4  mov     rdi, rcx
0x180026cf7  test    eax, eax
0x180026cf9  jz      short loc_180026D6F
0x180026cfb  lea     rbx, [rcx+8]
0x180026cff  mov     rcx, rbx; SRWLock
0x180026d02  call    cs:__imp_AcquireSRWLockExclusive
0x180026d08  mov     [rsp+28h+arg_0], rbx
0x180026d0d  lea     rbx, [rdi+60h]
0x180026d11  cmp     qword ptr [rbx], 0
0x180026d15  jz      short loc_180026D1D
0x180026d17  mov     ebx, [rdi+1Ch]
0x180026d1a  nop
0x180026d1b  jmp     short loc_180026D61
0x180026d1d  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180026d24  mov     qword ptr [rbx], 0
0x180026d2b  test    rax, rax
0x180026d2e  jnz     short loc_180026D3C
0x180026d30  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180026d37  test    rax, rax
0x180026d3a  jz      short loc_180026D4E
0x180026d3c  mov     r8, rdi
0x180026d3f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180026d46  mov     rcx, rbx
0x180026d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d4e  cmp     qword ptr [rbx], 0
0x180026d52  jnz     short loc_180026D58
0x180026d54  xor     ebx, ebx
0x180026d56  jmp     short loc_180026D61
0x180026d58  mov     ebx, 1
0x180026d5d  nop
0x180026d5e  mov     [rdi+1Ch], ebx
0x180026d61  lea     rcx, [rsp+28h+arg_0]
0x180026d66  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026d6b  mov     eax, ebx
0x180026d6d  jmp     short loc_180026D71
0x180026d6f  xor     eax, eax
0x180026d71  mov     rbx, [rsp+28h+arg_8]
0x180026d76  add     rsp, 20h
0x180026d7a  pop     rdi
0x180026d7b  retn
```
