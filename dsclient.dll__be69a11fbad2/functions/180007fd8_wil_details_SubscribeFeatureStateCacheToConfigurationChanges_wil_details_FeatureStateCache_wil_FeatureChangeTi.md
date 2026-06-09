# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180007fd8`
- end: `0x180008066`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005fa8`

## callees

- `0x1800048f8`
- `0x180007fd8`
- `0x180008c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007ffd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007ffd`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v8; // [rsp+78h] [rbp+20h] BYREF

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_18000F1DC
      || (v6[1] = 0, v6[0] = a2, v7 = a1, !wil::details_abi::heap_buffer::push_back((void **)qword_18000F200, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180007fd8  push    rbx
0x180007fda  push    rbp
0x180007fdb  push    rsi
0x180007fdc  push    rdi
0x180007fdd  sub     rsp, 38h
0x180007fe1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007fe7  mov     esi, r8d
0x180007fea  mov     ebx, edx
0x180007fec  mov     rdi, rcx
0x180007fef  test    eax, eax
0x180007ff1  jz      short loc_18000805D
0x180007ff3  lea     rbp, SRWLock
0x180007ffa  mov     rcx, rbp; SRWLock
0x180007ffd  call    cs:__imp_AcquireSRWLockExclusive
0x180008003  mov     eax, cs:dword_18000F1DC
0x180008009  mov     [rsp+58h+arg_18], rbp
0x18000800e  test    esi, esi
0x180008010  jz      short loc_180008042
0x180008012  cmp     esi, eax
0x180008014  jnz     short loc_180008042
0x180008016  mov     r8d, 10h; unsigned __int64
0x18000801c  mov     [rsp+58h+var_34], 0
0x180008024  lea     rdx, [rsp+58h+var_38]; void *
0x180008029  mov     [rsp+58h+var_38], ebx
0x18000802d  lea     rcx, qword_18000F200; this
0x180008034  mov     [rsp+58h+var_30], rdi
0x180008039  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000803e  test    al, al
0x180008040  jnz     short loc_180008053
0x180008042  neg     ebx
0x180008044  sbb     eax, eax
0x180008046  and     eax, 83Ah
0x18000804b  add     eax, 0FFFFF7C1h
0x180008050  lock and [rdi], eax
0x180008053  lea     rcx, [rsp+58h+arg_18]
0x180008058  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000805d  add     rsp, 38h
0x180008061  pop     rdi
0x180008062  pop     rsi
0x180008063  pop     rbp
0x180008064  pop     rbx
0x180008065  retn
```
