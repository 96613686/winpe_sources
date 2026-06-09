# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001b038`
- end: `0x18001b103`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012918`
- `0x180012aec`
- `0x180012c6c`
- `0x1800130b0`

## callees

- `0x18001b038`
- `0x180021370`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b0c6`
- `msvcrt!memcpy_s` at `0x18001b0c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b064`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b064`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b0ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b0ed`

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
    AcquireSRWLockExclusive(&stru_18004A490);
    if ( a3
      && a3 == dword_18004A4A4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18004A4C8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_18004A4D8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_18004A4D8),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&stru_18004A490);
  }
}

```

## disassembly

```asm
0x18001b038  mov     [rsp+arg_0], rbx
0x18001b03d  mov     [rsp+arg_8], rsi
0x18001b042  push    rdi
0x18001b043  sub     rsp, 30h
0x18001b047  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001b04d  mov     esi, r8d
0x18001b050  mov     ebx, edx
0x18001b052  mov     rdi, rcx
0x18001b055  test    eax, eax
0x18001b057  jz      loc_18001B0F3
0x18001b05d  lea     rcx, stru_18004A490; SRWLock
0x18001b064  call    cs:__imp_AcquireSRWLockExclusive
0x18001b06a  mov     eax, cs:dword_18004A4A4
0x18001b070  test    esi, esi
0x18001b072  jz      short loc_18001B0D5
0x18001b074  cmp     esi, eax
0x18001b076  jnz     short loc_18001B0D5
0x18001b078  mov     esi, 10h
0x18001b07d  mov     [rsp+38h+var_14], 0
0x18001b085  mov     edx, esi; unsigned __int64
0x18001b087  mov     [rsp+38h+Source], ebx
0x18001b08b  lea     rcx, qword_18004A4C8; this
0x18001b092  mov     [rsp+38h+var_10], rdi
0x18001b097  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b09c  test    al, al
0x18001b09e  jz      short loc_18001B0D5
0x18001b0a0  mov     rcx, cs:Destination; Destination
0x18001b0a7  lea     r8, [rsp+38h+Source]; Source
0x18001b0ac  mov     rax, cs:qword_18004A4D8
0x18001b0b3  mov     r9d, esi; SourceSize
0x18001b0b6  sub     rax, rcx
0x18001b0b9  cmp     rcx, cs:qword_18004A4D8
0x18001b0c0  sbb     rdx, rdx
0x18001b0c3  and     rdx, rax; DestinationSize
0x18001b0c6  call    cs:__imp_memcpy_s
0x18001b0cc  add     cs:Destination, rsi
0x18001b0d3  jmp     short loc_18001B0E6
0x18001b0d5  neg     ebx
0x18001b0d7  sbb     eax, eax
0x18001b0d9  and     eax, 83Ah
0x18001b0de  add     eax, 0FFFFF7C1h
0x18001b0e3  lock and [rdi], eax
0x18001b0e6  lea     rcx, stru_18004A490; SRWLock
0x18001b0ed  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b0f3  mov     rbx, [rsp+38h+arg_0]
0x18001b0f8  mov     rsi, [rsp+38h+arg_8]
0x18001b0fd  add     rsp, 30h
0x18001b101  pop     rdi
0x18001b102  retn
```
