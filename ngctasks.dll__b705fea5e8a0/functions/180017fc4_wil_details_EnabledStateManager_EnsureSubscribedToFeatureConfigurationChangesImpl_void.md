# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180017fc4`
- end: `0x180018056`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `146`
- prototype: `__int64 __fastcall(wil::details::EnabledStateManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017f9c`

## callees

- `0x180008c94`
- `0x18000ee40`
- `0x180017fc4`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        wil::details::EnabledStateManager *this)
{
  _QWORD *v2; // rdi
  unsigned int v3; // ebx
  void (__fastcall *v4)(char *, __int64 (__fastcall *)(void *), wil::details::EnabledStateManager *); // rax
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_DWORD *)this )
    return 0;
  wil::srwlock::lock_exclusive((char *)this + 8, &v6);
  v2 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
  {
    v3 = *((_DWORD *)this + 7);
  }
  else
  {
    *v2 = 0;
    v4 = (void (__fastcall *)(char *, __int64 (__fastcall *)(void *), wil::details::EnabledStateManager *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v4 = (void (__fastcall *)(char *, __int64 (__fastcall *)(void *), wil::details::EnabledStateManager *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v4((char *)this + 96, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
    }
    if ( *v2 )
    {
      *((_DWORD *)this + 7) = 1;
      v3 = 1;
    }
    else
    {
      v3 = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  return v3;
}

```

## disassembly

```asm
0x180017fc4  mov     [rsp+arg_8], rbx
0x180017fc9  push    rdi
0x180017fca  sub     rsp, 20h
0x180017fce  mov     rbx, rcx
0x180017fd1  mov     eax, [rcx]
0x180017fd3  test    eax, eax
0x180017fd5  jz      short loc_180018049
0x180017fd7  add     rcx, 8
0x180017fdb  lea     rdx, [rsp+28h+arg_0]
0x180017fe0  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180017fe5  lea     rdi, [rbx+60h]
0x180017fe9  cmp     qword ptr [rdi], 0
0x180017fed  jz      short loc_180017FF5
0x180017fef  mov     ebx, [rbx+1Ch]
0x180017ff2  nop
0x180017ff3  jmp     short loc_18001803B
0x180017ff5  mov     qword ptr [rdi], 0
0x180017ffc  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180018003  test    rax, rax
0x180018006  jnz     short loc_180018014
0x180018008  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001800f  test    rax, rax
0x180018012  jz      short loc_180018026
0x180018014  mov     r8, rbx
0x180018017  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001801e  mov     rcx, rdi
0x180018021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018026  cmp     qword ptr [rdi], 0
0x18001802a  jnz     short loc_180018030
0x18001802c  xor     ebx, ebx
0x18001802e  jmp     short loc_18001803B
0x180018030  nop
0x180018031  mov     eax, 1
0x180018036  mov     [rbx+1Ch], eax
0x180018039  mov     ebx, eax
0x18001803b  lea     rcx, [rsp+28h+arg_0]
0x180018040  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018045  mov     eax, ebx
0x180018047  jmp     short loc_18001804B
0x180018049  xor     eax, eax
0x18001804b  mov     rbx, [rsp+28h+arg_8]
0x180018050  add     rsp, 20h
0x180018054  pop     rdi
0x180018055  retn
```
