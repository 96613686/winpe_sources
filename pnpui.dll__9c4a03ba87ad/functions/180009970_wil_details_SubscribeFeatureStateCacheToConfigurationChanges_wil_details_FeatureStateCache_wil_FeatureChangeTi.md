# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009970`
- end: `0x180009a3b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000798c`

## callees

- `0x180009970`
- `0x18000a5e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800099fe`
- `msvcrt!memcpy_s` at `0x1800099fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000999c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000999c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a25`

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
      && a3 == dword_18001425C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180014280, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180014290 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180014290),
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
0x180009970  mov     [rsp+arg_0], rbx
0x180009975  mov     [rsp+arg_8], rsi
0x18000997a  push    rdi
0x18000997b  sub     rsp, 30h
0x18000997f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009985  mov     esi, r8d
0x180009988  mov     ebx, edx
0x18000998a  mov     rdi, rcx
0x18000998d  test    eax, eax
0x18000998f  jz      loc_180009A2B
0x180009995  lea     rcx, SRWLock; SRWLock
0x18000999c  call    cs:__imp_AcquireSRWLockExclusive
0x1800099a2  mov     eax, cs:dword_18001425C
0x1800099a8  test    esi, esi
0x1800099aa  jz      short loc_180009A0D
0x1800099ac  cmp     esi, eax
0x1800099ae  jnz     short loc_180009A0D
0x1800099b0  mov     esi, 10h
0x1800099b5  mov     [rsp+38h+var_14], 0
0x1800099bd  mov     edx, esi; unsigned __int64
0x1800099bf  mov     [rsp+38h+Source], ebx
0x1800099c3  lea     rcx, qword_180014280; this
0x1800099ca  mov     [rsp+38h+var_10], rdi
0x1800099cf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800099d4  test    al, al
0x1800099d6  jz      short loc_180009A0D
0x1800099d8  mov     rcx, cs:Destination; Destination
0x1800099df  lea     r8, [rsp+38h+Source]; Source
0x1800099e4  mov     rax, cs:qword_180014290
0x1800099eb  mov     r9d, esi; SourceSize
0x1800099ee  sub     rax, rcx
0x1800099f1  cmp     rcx, cs:qword_180014290
0x1800099f8  sbb     rdx, rdx
0x1800099fb  and     rdx, rax; DestinationSize
0x1800099fe  call    cs:__imp_memcpy_s
0x180009a04  add     cs:Destination, rsi
0x180009a0b  jmp     short loc_180009A1E
0x180009a0d  neg     ebx
0x180009a0f  sbb     eax, eax
0x180009a11  and     eax, 83Ah
0x180009a16  add     eax, 0FFFFF7C1h
0x180009a1b  lock and [rdi], eax
0x180009a1e  lea     rcx, SRWLock; SRWLock
0x180009a25  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a2b  mov     rbx, [rsp+38h+arg_0]
0x180009a30  mov     rsi, [rsp+38h+arg_8]
0x180009a35  add     rsp, 30h
0x180009a39  pop     rdi
0x180009a3a  retn
```
