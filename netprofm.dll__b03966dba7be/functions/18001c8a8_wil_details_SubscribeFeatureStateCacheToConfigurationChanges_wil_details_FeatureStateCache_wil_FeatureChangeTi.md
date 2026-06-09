# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001c8a8`
- end: `0x18001c93d`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `149`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018b78`
- `0x1800198f8`
- `0x18002398c`
- `0x180023a80`
- `0x180023b74`
- `0x180023c68`
- `0x180023d5c`
- `0x180023e50`
- `0x180023f44`
- `0x180024038`
- `0x18002412c`
- `0x180024220`
- `0x180024314`

## callees

- `0x180015bc0`
- `0x18001c8a8`
- `0x18001d57c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c8d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c8d0`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  RTL_SRWLOCK *v6; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v8; // [rsp+30h] [rbp-28h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_18005FC88);
    v6 = &stru_18005FC88;
    if ( !a3
      || a3 != dword_18005FC9C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005FCC0, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  }
}

```

## disassembly

```asm
0x18001c8a8  mov     [rsp+arg_10], rbx
0x18001c8ad  push    rbp
0x18001c8ae  push    rsi
0x18001c8af  push    rdi
0x18001c8b0  sub     rsp, 40h
0x18001c8b4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001c8ba  mov     esi, r8d
0x18001c8bd  mov     edi, edx
0x18001c8bf  mov     rbx, rcx
0x18001c8c2  test    eax, eax
0x18001c8c4  jz      short loc_18001C930
0x18001c8c6  lea     rbp, stru_18005FC88
0x18001c8cd  mov     rcx, rbp; SRWLock
0x18001c8d0  call    cs:__imp_AcquireSRWLockExclusive
0x18001c8d6  mov     eax, cs:dword_18005FC9C
0x18001c8dc  mov     [rsp+58h+var_38], rbp
0x18001c8e1  test    esi, esi
0x18001c8e3  jz      short loc_18001C915
0x18001c8e5  cmp     esi, eax
0x18001c8e7  jnz     short loc_18001C915
0x18001c8e9  mov     r8d, 10h; unsigned __int64
0x18001c8ef  mov     [rsp+58h+var_2C], 0
0x18001c8f7  lea     rdx, [rsp+58h+var_30]; void *
0x18001c8fc  mov     [rsp+58h+var_30], edi
0x18001c900  lea     rcx, qword_18005FCC0; this
0x18001c907  mov     [rsp+58h+var_28], rbx
0x18001c90c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001c911  test    al, al
0x18001c913  jnz     short loc_18001C926
0x18001c915  neg     edi
0x18001c917  sbb     eax, eax
0x18001c919  and     eax, 83Ah
0x18001c91e  add     eax, 0FFFFF7C1h
0x18001c923  lock and [rbx], eax
0x18001c926  lea     rcx, [rsp+58h+var_38]
0x18001c92b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001c930  mov     rbx, [rsp+58h+arg_10]
0x18001c935  add     rsp, 40h
0x18001c939  pop     rdi
0x18001c93a  pop     rsi
0x18001c93b  pop     rbp
0x18001c93c  retn
```
