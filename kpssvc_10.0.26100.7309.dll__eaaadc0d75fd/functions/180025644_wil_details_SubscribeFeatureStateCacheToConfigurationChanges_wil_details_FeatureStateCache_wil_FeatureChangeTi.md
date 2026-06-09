# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180025644`
- end: `0x1800256e3`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d678`
- `0x18001e3b8`

## callees

- `0x180025644`
- `0x180026440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800256c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800256c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002566b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002566b`

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
      || a3 != dword_18003A364
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003A398, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180025644  mov     [rsp+arg_0], rbx
0x180025649  mov     [rsp+arg_8], rsi
0x18002564e  push    rdi
0x18002564f  sub     rsp, 30h
0x180025653  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002565a  mov     esi, r8d
0x18002565d  mov     ebx, edx
0x18002565f  mov     rdi, rcx
0x180025662  jz      short loc_1800256D2
0x180025664  lea     rcx, SRWLock; SRWLock
0x18002566b  call    cs:__imp_AcquireSRWLockExclusive
0x180025672  nop     dword ptr [rax+rax+00h]
0x180025677  mov     eax, cs:dword_18003A364
0x18002567d  test    esi, esi
0x18002567f  jz      short loc_1800256AE
0x180025681  cmp     esi, eax
0x180025683  jnz     short loc_1800256AE
0x180025685  and     [rsp+38h+var_14], 0
0x18002568a  lea     rdx, [rsp+38h+Source]; Source
0x18002568f  mov     r8d, 10h; SourceSize
0x180025695  mov     [rsp+38h+Source], ebx
0x180025699  lea     rcx, qword_18003A398; this
0x1800256a0  mov     [rsp+38h+var_10], rdi
0x1800256a5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800256aa  test    al, al
0x1800256ac  jnz     short loc_1800256BF
0x1800256ae  neg     ebx
0x1800256b0  sbb     eax, eax
0x1800256b2  and     eax, 83Ah
0x1800256b7  add     eax, 0FFFFF7C1h
0x1800256bc  lock and [rdi], eax
0x1800256bf  lea     rcx, SRWLock; SRWLock
0x1800256c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800256cd  nop     dword ptr [rax+rax+00h]
0x1800256d2  mov     rbx, [rsp+38h+arg_0]
0x1800256d7  mov     rsi, [rsp+38h+arg_8]
0x1800256dc  add     rsp, 30h
0x1800256e0  pop     rdi
0x1800256e1  retn
```
