# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1400080ac`
- end: `0x140008140`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008084`

## callees

- `0x140004dcc`
- `0x1400080ac`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400080c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400080c6`

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
0x1400080ac  mov     [rsp+arg_8], rbx
0x1400080b1  push    rdi
0x1400080b2  sub     rsp, 20h
0x1400080b6  mov     eax, [rcx]
0x1400080b8  mov     rdi, rcx
0x1400080bb  test    eax, eax
0x1400080bd  jz      short loc_140008133
0x1400080bf  lea     rbx, [rcx+8]
0x1400080c3  mov     rcx, rbx; SRWLock
0x1400080c6  call    cs:__imp_AcquireSRWLockExclusive
0x1400080cc  mov     [rsp+28h+arg_0], rbx
0x1400080d1  lea     rbx, [rdi+60h]
0x1400080d5  cmp     qword ptr [rbx], 0
0x1400080d9  jz      short loc_1400080E1
0x1400080db  mov     ebx, [rdi+1Ch]
0x1400080de  nop
0x1400080df  jmp     short loc_140008125
0x1400080e1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400080e8  mov     qword ptr [rbx], 0
0x1400080ef  test    rax, rax
0x1400080f2  jnz     short loc_140008100
0x1400080f4  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400080fb  test    rax, rax
0x1400080fe  jz      short loc_140008112
0x140008100  mov     r8, rdi
0x140008103  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x14000810a  mov     rcx, rbx
0x14000810d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008112  cmp     qword ptr [rbx], 0
0x140008116  jnz     short loc_14000811C
0x140008118  xor     ebx, ebx
0x14000811a  jmp     short loc_140008125
0x14000811c  mov     ebx, 1
0x140008121  nop
0x140008122  mov     [rdi+1Ch], ebx
0x140008125  lea     rcx, [rsp+28h+arg_0]
0x14000812a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000812f  mov     eax, ebx
0x140008131  jmp     short loc_140008135
0x140008133  xor     eax, eax
0x140008135  mov     rbx, [rsp+28h+arg_8]
0x14000813a  add     rsp, 20h
0x14000813e  pop     rdi
0x14000813f  retn
```
