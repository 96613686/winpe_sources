# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180011940`
- end: `0x1800119ce`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `17`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e038`
- `0x18001405c`
- `0x1800156c0`
- `0x1800157a0`
- `0x180015880`
- `0x180019e78`
- `0x180019f58`
- `0x18001a038`
- `0x18001a118`
- `0x18001a1f8`
- `0x18001a2d8`
- `0x18001a3b8`
- `0x18001a498`
- `0x18001a578`
- `0x18001a658`
- `0x18001a738`
- `0x18001a818`

## callees

- `0x180007cd0`
- `0x180011940`
- `0x180012f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011965`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011965`

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
      || a3 != dword_180053FE4
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180054008, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180011940  push    rbx
0x180011942  push    rbp
0x180011943  push    rsi
0x180011944  push    rdi
0x180011945  sub     rsp, 38h
0x180011949  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001194f  mov     esi, r8d
0x180011952  mov     ebx, edx
0x180011954  mov     rdi, rcx
0x180011957  test    eax, eax
0x180011959  jz      short loc_1800119C5
0x18001195b  lea     rbp, SRWLock
0x180011962  mov     rcx, rbp; SRWLock
0x180011965  call    cs:__imp_AcquireSRWLockExclusive
0x18001196b  mov     eax, cs:dword_180053FE4
0x180011971  mov     [rsp+58h+arg_18], rbp
0x180011976  test    esi, esi
0x180011978  jz      short loc_1800119AA
0x18001197a  cmp     esi, eax
0x18001197c  jnz     short loc_1800119AA
0x18001197e  mov     r8d, 10h; unsigned __int64
0x180011984  mov     [rsp+58h+var_34], 0
0x18001198c  lea     rdx, [rsp+58h+var_38]; void *
0x180011991  mov     [rsp+58h+var_38], ebx
0x180011995  lea     rcx, qword_180054008; this
0x18001199c  mov     [rsp+58h+var_30], rdi
0x1800119a1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800119a6  test    al, al
0x1800119a8  jnz     short loc_1800119BB
0x1800119aa  neg     ebx
0x1800119ac  sbb     eax, eax
0x1800119ae  and     eax, 83Ah
0x1800119b3  add     eax, 0FFFFF7C1h
0x1800119b8  lock and [rdi], eax
0x1800119bb  lea     rcx, [rsp+58h+arg_18]
0x1800119c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800119c5  add     rsp, 38h
0x1800119c9  pop     rdi
0x1800119ca  pop     rsi
0x1800119cb  pop     rbp
0x1800119cc  pop     rbx
0x1800119cd  retn
```
