# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1400096d0`
- end: `0x14000975e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007a20`
- `0x14000cb24`
- `0x14000cc04`
- `0x14000cce4`
- `0x14000cdc4`
- `0x14000cea4`
- `0x14000cf84`
- `0x14000d064`
- `0x14000d144`
- `0x14000d224`
- `0x14000d304`
- `0x14000d3e4`
- `0x14000d4c4`

## callees

- `0x140006e08`
- `0x1400096d0`
- `0x14000a76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096f5`

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
      || a3 != dword_140021244
      || (v6[1] = 0, v6[0] = a2, v7 = a1, !wil::details_abi::heap_buffer::push_back((void **)qword_140021268, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x1400096d0  push    rbx
0x1400096d2  push    rbp
0x1400096d3  push    rsi
0x1400096d4  push    rdi
0x1400096d5  sub     rsp, 38h
0x1400096d9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400096df  mov     esi, r8d
0x1400096e2  mov     ebx, edx
0x1400096e4  mov     rdi, rcx
0x1400096e7  test    eax, eax
0x1400096e9  jz      short loc_140009755
0x1400096eb  lea     rbp, SRWLock
0x1400096f2  mov     rcx, rbp; SRWLock
0x1400096f5  call    cs:__imp_AcquireSRWLockExclusive
0x1400096fb  mov     eax, cs:dword_140021244
0x140009701  mov     [rsp+58h+arg_18], rbp
0x140009706  test    esi, esi
0x140009708  jz      short loc_14000973A
0x14000970a  cmp     esi, eax
0x14000970c  jnz     short loc_14000973A
0x14000970e  mov     r8d, 10h; unsigned __int64
0x140009714  mov     [rsp+58h+var_34], 0
0x14000971c  lea     rdx, [rsp+58h+var_38]; void *
0x140009721  mov     [rsp+58h+var_38], ebx
0x140009725  lea     rcx, qword_140021268; this
0x14000972c  mov     [rsp+58h+var_30], rdi
0x140009731  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140009736  test    al, al
0x140009738  jnz     short loc_14000974B
0x14000973a  neg     ebx
0x14000973c  sbb     eax, eax
0x14000973e  and     eax, 83Ah
0x140009743  add     eax, 0FFFFF7C1h
0x140009748  lock and [rdi], eax
0x14000974b  lea     rcx, [rsp+58h+arg_18]
0x140009750  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140009755  add     rsp, 38h
0x140009759  pop     rdi
0x14000975a  pop     rsi
0x14000975b  pop     rbp
0x14000975c  pop     rbx
0x14000975d  retn
```
