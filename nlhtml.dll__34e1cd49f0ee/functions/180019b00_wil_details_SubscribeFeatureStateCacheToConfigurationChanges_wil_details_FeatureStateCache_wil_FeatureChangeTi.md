# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180019b00`
- end: `0x180019b8e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800178ec`
- `0x18001b554`
- `0x18001b634`
- `0x18001b714`
- `0x18001d09c`
- `0x18001d17c`
- `0x18001d25c`
- `0x18001d33c`
- `0x18001d41c`
- `0x18001d4fc`
- `0x18001d5dc`
- `0x18001d6bc`
- `0x18001d79c`
- `0x18001d87c`
- `0x18001d95c`
- `0x18001da3c`

## callees

- `0x180016120`
- `0x180019b00`
- `0x18001a850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019b25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019b25`

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
      || a3 != dword_18003DEA4
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003DEC8, v7, 0x10u)) )
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
0x180019b00  push    rbx
0x180019b02  push    rbp
0x180019b03  push    rsi
0x180019b04  push    rdi
0x180019b05  sub     rsp, 38h
0x180019b09  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180019b0f  mov     esi, r8d
0x180019b12  mov     ebx, edx
0x180019b14  mov     rdi, rcx
0x180019b17  test    eax, eax
0x180019b19  jz      short loc_180019B85
0x180019b1b  lea     rbp, SRWLock
0x180019b22  mov     rcx, rbp; SRWLock
0x180019b25  call    cs:__imp_AcquireSRWLockExclusive
0x180019b2b  mov     eax, cs:dword_18003DEA4
0x180019b31  mov     [rsp+58h+arg_18], rbp
0x180019b36  test    esi, esi
0x180019b38  jz      short loc_180019B6A
0x180019b3a  cmp     esi, eax
0x180019b3c  jnz     short loc_180019B6A
0x180019b3e  mov     r8d, 10h; unsigned __int64
0x180019b44  mov     [rsp+58h+var_34], 0
0x180019b4c  lea     rdx, [rsp+58h+var_38]; void *
0x180019b51  mov     [rsp+58h+var_38], ebx
0x180019b55  lea     rcx, qword_18003DEC8; this
0x180019b5c  mov     [rsp+58h+var_30], rdi
0x180019b61  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019b66  test    al, al
0x180019b68  jnz     short loc_180019B7B
0x180019b6a  neg     ebx
0x180019b6c  sbb     eax, eax
0x180019b6e  and     eax, 83Ah
0x180019b73  add     eax, 0FFFFF7C1h
0x180019b78  lock and [rdi], eax
0x180019b7b  lea     rcx, [rsp+58h+arg_18]
0x180019b80  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019b85  add     rsp, 38h
0x180019b89  pop     rdi
0x180019b8a  pop     rsi
0x180019b8b  pop     rbp
0x180019b8c  pop     rbx
0x180019b8d  retn
```
