# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001200c`
- end: `0x1800120a1`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `149`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010684`
- `0x18003f44c`
- `0x18003f540`
- `0x18003f634`
- `0x18003f728`
- `0x18003f81c`
- `0x18003f910`
- `0x18003fa04`
- `0x18003faf8`

## callees

- `0x18000f0b4`
- `0x18001200c`
- `0x180013644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012034`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012034`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v8[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v9; // [rsp+30h] [rbp-28h]

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v7 = &SRWLock;
    if ( !a3
      || a3 != dword_180068974
      || (v8[1] = 0,
          v8[0] = a2,
          v9 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180068998, v8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001200c  mov     [rsp+arg_10], rbx
0x180012011  push    rbp
0x180012012  push    rsi
0x180012013  push    rdi
0x180012014  sub     rsp, 40h
0x180012018  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001201e  mov     esi, r8d
0x180012021  mov     edi, edx
0x180012023  mov     rbx, rcx
0x180012026  test    eax, eax
0x180012028  jz      short loc_180012094
0x18001202a  lea     rbp, SRWLock
0x180012031  mov     rcx, rbp; SRWLock
0x180012034  call    cs:__imp_AcquireSRWLockExclusive
0x18001203a  mov     eax, cs:dword_180068974
0x180012040  mov     [rsp+58h+var_38], rbp
0x180012045  test    esi, esi
0x180012047  jz      short loc_180012079
0x180012049  cmp     esi, eax
0x18001204b  jnz     short loc_180012079
0x18001204d  mov     r8d, 10h; unsigned __int64
0x180012053  mov     [rsp+58h+var_2C], 0
0x18001205b  lea     rdx, [rsp+58h+var_30]; void *
0x180012060  mov     [rsp+58h+var_30], edi
0x180012064  lea     rcx, qword_180068998; this
0x18001206b  mov     [rsp+58h+var_28], rbx
0x180012070  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012075  test    al, al
0x180012077  jnz     short loc_18001208A
0x180012079  neg     edi
0x18001207b  sbb     eax, eax
0x18001207d  and     eax, 83Ah
0x180012082  add     eax, 0FFFFF7C1h
0x180012087  lock and [rbx], eax
0x18001208a  lea     rcx, [rsp+58h+var_38]
0x18001208f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012094  mov     rbx, [rsp+58h+arg_10]
0x180012099  add     rsp, 40h
0x18001209d  pop     rdi
0x18001209e  pop     rsi
0x18001209f  pop     rbp
0x1800120a0  retn
```
