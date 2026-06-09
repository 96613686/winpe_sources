# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180013298`
- end: `0x18001332c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013270`

## callees

- `0x180011514`
- `0x180013298`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800132b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800132b2`

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
0x180013298  mov     [rsp+arg_8], rbx
0x18001329d  push    rdi
0x18001329e  sub     rsp, 20h
0x1800132a2  mov     rdi, rcx
0x1800132a5  mov     eax, [rcx]
0x1800132a7  test    eax, eax
0x1800132a9  jz      short loc_18001331F
0x1800132ab  lea     rbx, [rcx+8]
0x1800132af  mov     rcx, rbx; SRWLock
0x1800132b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800132b8  mov     [rsp+28h+arg_0], rbx
0x1800132bd  lea     rbx, [rdi+60h]
0x1800132c1  cmp     qword ptr [rbx], 0
0x1800132c5  jz      short loc_1800132CD
0x1800132c7  mov     ebx, [rdi+1Ch]
0x1800132ca  nop
0x1800132cb  jmp     short loc_180013311
0x1800132cd  mov     qword ptr [rbx], 0
0x1800132d4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800132db  test    rax, rax
0x1800132de  jnz     short loc_1800132EC
0x1800132e0  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800132e7  test    rax, rax
0x1800132ea  jz      short loc_1800132FE
0x1800132ec  mov     r8, rdi
0x1800132ef  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800132f6  mov     rcx, rbx
0x1800132f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fe  cmp     qword ptr [rbx], 0
0x180013302  jnz     short loc_180013308
0x180013304  xor     ebx, ebx
0x180013306  jmp     short loc_180013311
0x180013308  nop
0x180013309  mov     ebx, 1
0x18001330e  mov     [rdi+1Ch], ebx
0x180013311  lea     rcx, [rsp+28h+arg_0]
0x180013316  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001331b  mov     eax, ebx
0x18001331d  jmp     short loc_180013321
0x18001331f  xor     eax, eax
0x180013321  mov     rbx, [rsp+28h+arg_8]
0x180013326  add     rsp, 20h
0x18001332a  pop     rdi
0x18001332b  retn
```
