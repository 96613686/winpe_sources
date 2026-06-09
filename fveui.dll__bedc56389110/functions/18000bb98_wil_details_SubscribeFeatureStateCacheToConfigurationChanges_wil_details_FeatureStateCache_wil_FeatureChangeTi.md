# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000bb98`
- end: `0x18000bc26`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009688`
- `0x1800164c8`
- `0x18002611c`
- `0x1800261fc`
- `0x1800263a8`
- `0x180026488`
- `0x180026568`
- `0x1800266c8`
- `0x180026828`
- `0x180026988`
- `0x180026ae8`
- `0x180026bc8`
- `0x180026ca8`
- `0x180026d88`
- `0x180026e68`

## callees

- `0x18000474c`
- `0x18000bb98`
- `0x18000d92c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000bbbd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000bbbd`

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
      || a3 != dword_18003DD0C
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003DD30, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x18000bb98  push    rbx
0x18000bb9a  push    rbp
0x18000bb9b  push    rsi
0x18000bb9c  push    rdi
0x18000bb9d  sub     rsp, 38h
0x18000bba1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000bba7  mov     esi, r8d
0x18000bbaa  mov     ebx, edx
0x18000bbac  mov     rdi, rcx
0x18000bbaf  test    eax, eax
0x18000bbb1  jz      short loc_18000BC1D
0x18000bbb3  lea     rbp, SRWLock
0x18000bbba  mov     rcx, rbp; SRWLock
0x18000bbbd  call    cs:__imp_AcquireSRWLockExclusive
0x18000bbc3  mov     eax, cs:dword_18003DD0C
0x18000bbc9  mov     [rsp+58h+arg_18], rbp
0x18000bbce  test    esi, esi
0x18000bbd0  jz      short loc_18000BC02
0x18000bbd2  cmp     esi, eax
0x18000bbd4  jnz     short loc_18000BC02
0x18000bbd6  mov     r8d, 10h; unsigned __int64
0x18000bbdc  mov     [rsp+58h+var_34], 0
0x18000bbe4  lea     rdx, [rsp+58h+var_38]; void *
0x18000bbe9  mov     [rsp+58h+var_38], ebx
0x18000bbed  lea     rcx, qword_18003DD30; this
0x18000bbf4  mov     [rsp+58h+var_30], rdi
0x18000bbf9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000bbfe  test    al, al
0x18000bc00  jnz     short loc_18000BC13
0x18000bc02  neg     ebx
0x18000bc04  sbb     eax, eax
0x18000bc06  and     eax, 83Ah
0x18000bc0b  add     eax, 0FFFFF7C1h
0x18000bc10  lock and [rdi], eax
0x18000bc13  lea     rcx, [rsp+58h+arg_18]
0x18000bc18  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bc1d  add     rsp, 38h
0x18000bc21  pop     rdi
0x18000bc22  pop     rsi
0x18000bc23  pop     rbp
0x18000bc24  pop     rbx
0x18000bc25  retn
```
