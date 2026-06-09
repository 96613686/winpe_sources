# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800086ac`
- end: `0x180008740`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008684`

## callees

- `0x180007c28`
- `0x1800086ac`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086c6`

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
0x1800086ac  mov     [rsp+arg_8], rbx
0x1800086b1  push    rdi
0x1800086b2  sub     rsp, 20h
0x1800086b6  mov     rdi, rcx
0x1800086b9  mov     eax, [rcx]
0x1800086bb  test    eax, eax
0x1800086bd  jz      short loc_180008733
0x1800086bf  lea     rbx, [rcx+8]
0x1800086c3  mov     rcx, rbx; SRWLock
0x1800086c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800086cc  mov     [rsp+28h+arg_0], rbx
0x1800086d1  lea     rbx, [rdi+60h]
0x1800086d5  cmp     qword ptr [rbx], 0
0x1800086d9  jz      short loc_1800086E1
0x1800086db  mov     ebx, [rdi+1Ch]
0x1800086de  nop
0x1800086df  jmp     short loc_180008725
0x1800086e1  mov     qword ptr [rbx], 0
0x1800086e8  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800086ef  test    rax, rax
0x1800086f2  jnz     short loc_180008700
0x1800086f4  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800086fb  test    rax, rax
0x1800086fe  jz      short loc_180008712
0x180008700  mov     r8, rdi
0x180008703  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000870a  mov     rcx, rbx
0x18000870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008712  cmp     qword ptr [rbx], 0
0x180008716  jnz     short loc_18000871C
0x180008718  xor     ebx, ebx
0x18000871a  jmp     short loc_180008725
0x18000871c  nop
0x18000871d  mov     ebx, 1
0x180008722  mov     [rdi+1Ch], ebx
0x180008725  lea     rcx, [rsp+28h+arg_0]
0x18000872a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000872f  mov     eax, ebx
0x180008731  jmp     short loc_180008735
0x180008733  xor     eax, eax
0x180008735  mov     rbx, [rsp+28h+arg_8]
0x18000873a  add     rsp, 20h
0x18000873e  pop     rdi
0x18000873f  retn
```
