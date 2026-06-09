# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180005e58`
- end: `0x180005f23`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e6a8`
- `0x18000e874`
- `0x18000e9e8`
- `0x18000eb5c`
- `0x18000ecd0`
- `0x18000ee44`
- `0x18000efb8`
- `0x18000f098`
- `0x18000f178`
- `0x18000f258`
- `0x18000f338`
- `0x18000f418`
- `0x18000fafc`

## callees

- `0x180005e58`
- `0x180006318`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005ee6`
- `msvcrt!memcpy_s` at `0x180005ee6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f0d`

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
    if ( a3
      && a3 == dword_18001E2F4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001E318, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_18001E328 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_18001E328),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180005e58  mov     [rsp+arg_0], rbx
0x180005e5d  mov     [rsp+arg_8], rsi
0x180005e62  push    rdi
0x180005e63  sub     rsp, 30h
0x180005e67  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005e6d  mov     esi, r8d
0x180005e70  mov     ebx, edx
0x180005e72  mov     rdi, rcx
0x180005e75  test    eax, eax
0x180005e77  jz      loc_180005F13
0x180005e7d  lea     rcx, SRWLock; SRWLock
0x180005e84  call    cs:__imp_AcquireSRWLockExclusive
0x180005e8a  mov     eax, cs:dword_18001E2F4
0x180005e90  test    esi, esi
0x180005e92  jz      short loc_180005EF5
0x180005e94  cmp     esi, eax
0x180005e96  jnz     short loc_180005EF5
0x180005e98  mov     esi, 10h
0x180005e9d  mov     [rsp+38h+var_14], 0
0x180005ea5  mov     edx, esi; unsigned __int64
0x180005ea7  mov     [rsp+38h+Source], ebx
0x180005eab  lea     rcx, qword_18001E318; this
0x180005eb2  mov     [rsp+38h+var_10], rdi
0x180005eb7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005ebc  test    al, al
0x180005ebe  jz      short loc_180005EF5
0x180005ec0  mov     rcx, cs:Destination; Destination
0x180005ec7  lea     r8, [rsp+38h+Source]; Source
0x180005ecc  mov     rax, cs:qword_18001E328
0x180005ed3  mov     r9d, esi; SourceSize
0x180005ed6  sub     rax, rcx
0x180005ed9  cmp     rcx, cs:qword_18001E328
0x180005ee0  sbb     rdx, rdx
0x180005ee3  and     rdx, rax; DestinationSize
0x180005ee6  call    cs:__imp_memcpy_s
0x180005eec  add     cs:Destination, rsi
0x180005ef3  jmp     short loc_180005F06
0x180005ef5  neg     ebx
0x180005ef7  sbb     eax, eax
0x180005ef9  and     eax, 83Ah
0x180005efe  add     eax, 0FFFFF7C1h
0x180005f03  lock and [rdi], eax
0x180005f06  lea     rcx, SRWLock; SRWLock
0x180005f0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f13  mov     rbx, [rsp+38h+arg_0]
0x180005f18  mov     rsi, [rsp+38h+arg_8]
0x180005f1d  add     rsp, 30h
0x180005f21  pop     rdi
0x180005f22  retn
```
