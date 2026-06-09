# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b604`
- end: `0x18000b692`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800088d4`
- `0x18000916c`

## callees

- `0x180007984`
- `0x18000b604`
- `0x18000ca44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b629`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b629`

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
      || a3 != dword_18001C5BC
      || (v6[1] = 0, v6[0] = a2, v7 = a1, !wil::details_abi::heap_buffer::push_back((void **)qword_18001C5E0, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x18000b604  push    rbx
0x18000b606  push    rbp
0x18000b607  push    rsi
0x18000b608  push    rdi
0x18000b609  sub     rsp, 38h
0x18000b60d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b613  mov     esi, r8d
0x18000b616  mov     ebx, edx
0x18000b618  mov     rdi, rcx
0x18000b61b  test    eax, eax
0x18000b61d  jz      short loc_18000B689
0x18000b61f  lea     rbp, SRWLock
0x18000b626  mov     rcx, rbp; SRWLock
0x18000b629  call    cs:__imp_AcquireSRWLockExclusive
0x18000b62f  mov     eax, cs:dword_18001C5BC
0x18000b635  mov     [rsp+58h+arg_18], rbp
0x18000b63a  test    esi, esi
0x18000b63c  jz      short loc_18000B66E
0x18000b63e  cmp     esi, eax
0x18000b640  jnz     short loc_18000B66E
0x18000b642  mov     r8d, 10h; unsigned __int64
0x18000b648  mov     [rsp+58h+var_34], 0
0x18000b650  lea     rdx, [rsp+58h+var_38]; void *
0x18000b655  mov     [rsp+58h+var_38], ebx
0x18000b659  lea     rcx, qword_18001C5E0; this
0x18000b660  mov     [rsp+58h+var_30], rdi
0x18000b665  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b66a  test    al, al
0x18000b66c  jnz     short loc_18000B67F
0x18000b66e  neg     ebx
0x18000b670  sbb     eax, eax
0x18000b672  and     eax, 83Ah
0x18000b677  add     eax, 0FFFFF7C1h
0x18000b67c  lock and [rdi], eax
0x18000b67f  lea     rcx, [rsp+58h+arg_18]
0x18000b684  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b689  add     rsp, 38h
0x18000b68d  pop     rdi
0x18000b68e  pop     rsi
0x18000b68f  pop     rbp
0x18000b690  pop     rbx
0x18000b691  retn
```
