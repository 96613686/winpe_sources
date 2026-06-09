# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800140e0`
- end: `0x180014180`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000cd18`
- `0x18000ce08`
- `0x18000cef8`
- `0x18000e634`

## callees

- `0x1800140e0`
- `0x1800183b4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180014108`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014108`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014163`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014163`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180030424
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&unk_180030448, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800140e0  mov     [rsp+arg_0], rbx
0x1800140e5  mov     [rsp+arg_8], rsi
0x1800140ea  push    rdi
0x1800140eb  sub     rsp, 30h
0x1800140ef  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800140f5  mov     esi, r8d
0x1800140f8  mov     ebx, edx
0x1800140fa  mov     rdi, rcx
0x1800140fd  test    eax, eax
0x1800140ff  jz      short loc_18001416F
0x180014101  lea     rcx, SRWLock; SRWLock
0x180014108  call    cs:__imp_AcquireSRWLockExclusive
0x18001410f  nop     dword ptr [rax+rax+00h]
0x180014114  mov     eax, cs:dword_180030424
0x18001411a  test    esi, esi
0x18001411c  jz      short loc_18001414B
0x18001411e  cmp     esi, eax
0x180014120  jnz     short loc_18001414B
0x180014122  and     [rsp+38h+var_14], 0
0x180014127  lea     rdx, [rsp+38h+Source]; Source
0x18001412c  mov     r8d, 10h; SourceSize
0x180014132  mov     [rsp+38h+Source], ebx
0x180014136  lea     rcx, unk_180030448; this
0x18001413d  mov     [rsp+38h+var_10], rdi
0x180014142  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014147  test    al, al
0x180014149  jnz     short loc_18001415C
0x18001414b  neg     ebx
0x18001414d  sbb     eax, eax
0x18001414f  and     eax, 83Ah
0x180014154  add     eax, 0FFFFF7C1h
0x180014159  lock and [rdi], eax
0x18001415c  lea     rcx, SRWLock; SRWLock
0x180014163  call    cs:__imp_ReleaseSRWLockExclusive
0x18001416a  nop     dword ptr [rax+rax+00h]
0x18001416f  mov     rbx, [rsp+38h+arg_0]
0x180014174  mov     rsi, [rsp+38h+arg_8]
0x180014179  add     rsp, 30h
0x18001417d  pop     rdi
0x18001417e  retn
```
