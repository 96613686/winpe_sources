# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008b70`
- end: `0x180008c10`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005fb4`
- `0x18000fbb0`
- `0x18000fc98`
- `0x18000fe10`
- `0x1800284ec`
- `0x1800285d4`
- `0x1800286bc`
- `0x1800287a4`
- `0x18002891c`
- `0x180028a94`
- `0x180028c0c`
- `0x180028cf4`
- `0x180028ddc`
- `0x180028ec4`
- `0x18002903c`
- `0x180029124`
- `0x18002920c`

## callees

- `0x180008b70`
- `0x180009abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b98`

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
      || a3 != dword_1800464C4
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800464E8, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_0], rbx
0x180008b75  mov     [rsp+arg_8], rsi
0x180008b7a  push    rdi
0x180008b7b  sub     rsp, 30h
0x180008b7f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008b85  mov     esi, r8d
0x180008b88  mov     ebx, edx
0x180008b8a  mov     rdi, rcx
0x180008b8d  test    eax, eax
0x180008b8f  jz      short loc_180008BFF
0x180008b91  lea     rcx, SRWLock; SRWLock
0x180008b98  call    cs:__imp_AcquireSRWLockExclusive
0x180008b9f  nop     dword ptr [rax+rax+00h]
0x180008ba4  mov     eax, cs:dword_1800464C4
0x180008baa  test    esi, esi
0x180008bac  jz      short loc_180008BDB
0x180008bae  cmp     esi, eax
0x180008bb0  jnz     short loc_180008BDB
0x180008bb2  and     [rsp+38h+var_14], 0
0x180008bb7  lea     rdx, [rsp+38h+Source]; Source
0x180008bbc  mov     r8d, 10h; SourceSize
0x180008bc2  mov     [rsp+38h+Source], ebx
0x180008bc6  lea     rcx, qword_1800464E8; this
0x180008bcd  mov     [rsp+38h+var_10], rdi
0x180008bd2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008bd7  test    al, al
0x180008bd9  jnz     short loc_180008BEC
0x180008bdb  neg     ebx
0x180008bdd  sbb     eax, eax
0x180008bdf  and     eax, 83Ah
0x180008be4  add     eax, 0FFFFF7C1h
0x180008be9  lock and [rdi], eax
0x180008bec  lea     rcx, SRWLock; SRWLock
0x180008bf3  call    cs:__imp_ReleaseSRWLockExclusive
0x180008bfa  nop     dword ptr [rax+rax+00h]
0x180008bff  mov     rbx, [rsp+38h+arg_0]
0x180008c04  mov     rsi, [rsp+38h+arg_8]
0x180008c09  add     rsp, 30h
0x180008c0d  pop     rdi
0x180008c0e  retn
```
