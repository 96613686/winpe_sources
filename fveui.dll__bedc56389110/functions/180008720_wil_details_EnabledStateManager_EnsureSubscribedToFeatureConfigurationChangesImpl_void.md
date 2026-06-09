# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180008720`
- end: `0x1800087b4`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800086f8`

## callees

- `0x18000474c`
- `0x180008720`
- `0x18002d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000873a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000873a`

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
0x180008720  mov     [rsp+arg_8], rbx
0x180008725  push    rdi
0x180008726  sub     rsp, 20h
0x18000872a  mov     rdi, rcx
0x18000872d  mov     eax, [rcx]
0x18000872f  test    eax, eax
0x180008731  jz      short loc_1800087A7
0x180008733  lea     rbx, [rcx+8]
0x180008737  mov     rcx, rbx; SRWLock
0x18000873a  call    cs:__imp_AcquireSRWLockExclusive
0x180008740  mov     [rsp+28h+arg_0], rbx
0x180008745  lea     rbx, [rdi+60h]
0x180008749  cmp     qword ptr [rbx], 0
0x18000874d  jz      short loc_180008755
0x18000874f  mov     ebx, [rdi+1Ch]
0x180008752  nop
0x180008753  jmp     short loc_180008799
0x180008755  mov     qword ptr [rbx], 0
0x18000875c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008763  test    rax, rax
0x180008766  jnz     short loc_180008774
0x180008768  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000876f  test    rax, rax
0x180008772  jz      short loc_180008786
0x180008774  mov     r8, rdi
0x180008777  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000877e  mov     rcx, rbx
0x180008781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008786  cmp     qword ptr [rbx], 0
0x18000878a  jnz     short loc_180008790
0x18000878c  xor     ebx, ebx
0x18000878e  jmp     short loc_180008799
0x180008790  nop
0x180008791  mov     ebx, 1
0x180008796  mov     [rdi+1Ch], ebx
0x180008799  lea     rcx, [rsp+28h+arg_0]
0x18000879e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800087a3  mov     eax, ebx
0x1800087a5  jmp     short loc_1800087A9
0x1800087a7  xor     eax, eax
0x1800087a9  mov     rbx, [rsp+28h+arg_8]
0x1800087ae  add     rsp, 20h
0x1800087b2  pop     rdi
0x1800087b3  retn
```
