# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180022240`
- end: `0x1800222ce`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020730`

## callees

- `0x180011c60`
- `0x180022240`
- `0x180022eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022265`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022265`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v9; // [rsp+78h] [rbp+20h] BYREF

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v9 = &SRWLock;
    if ( !a3
      || a3 != dword_18003353C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180033560, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x180022240  push    rbx
0x180022242  push    rbp
0x180022243  push    rsi
0x180022244  push    rdi
0x180022245  sub     rsp, 38h
0x180022249  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002224f  mov     esi, r8d
0x180022252  mov     ebx, edx
0x180022254  mov     rdi, rcx
0x180022257  test    eax, eax
0x180022259  jz      short loc_1800222C5
0x18002225b  lea     rbp, SRWLock
0x180022262  mov     rcx, rbp; SRWLock
0x180022265  call    cs:__imp_AcquireSRWLockExclusive
0x18002226b  mov     eax, cs:dword_18003353C
0x180022271  mov     [rsp+58h+arg_18], rbp
0x180022276  test    esi, esi
0x180022278  jz      short loc_1800222AA
0x18002227a  cmp     esi, eax
0x18002227c  jnz     short loc_1800222AA
0x18002227e  mov     r8d, 10h; unsigned __int64
0x180022284  mov     [rsp+58h+var_34], 0
0x18002228c  lea     rdx, [rsp+58h+var_38]; void *
0x180022291  mov     [rsp+58h+var_38], ebx
0x180022295  lea     rcx, qword_180033560; this
0x18002229c  mov     [rsp+58h+var_30], rdi
0x1800222a1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800222a6  test    al, al
0x1800222a8  jnz     short loc_1800222BB
0x1800222aa  neg     ebx
0x1800222ac  sbb     eax, eax
0x1800222ae  and     eax, 83Ah
0x1800222b3  add     eax, 0FFFFF7C1h
0x1800222b8  lock and [rdi], eax
0x1800222bb  lea     rcx, [rsp+58h+arg_18]
0x1800222c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800222c5  add     rsp, 38h
0x1800222c9  pop     rdi
0x1800222ca  pop     rsi
0x1800222cb  pop     rbp
0x1800222cc  pop     rbx
0x1800222cd  retn
```
