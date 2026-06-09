# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000bfdc`
- end: `0x14000c0b3`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `215`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009040`
- `0x14000e44c`
- `0x1400152d4`
- `0x1400167c4`
- `0x140016944`
- `0x140016abc`
- `0x14002c024`
- `0x1400333a8`
- `0x14003ac50`
- `0x14003adc8`
- `0x1400473f4`
- `0x14004c098`
- `0x14004cfa4`
- `0x1400529c8`
- `0x14005cc0c`
- `0x14005cdd0`
- `0x14005cf94`
- `0x140065568`

## callees

- `0x14000bfdc`
- `0x14000d0ac`
- `0x14000ded8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c096`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c096`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c008`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c008`

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
      && a3 == dword_140084B74
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140084BA8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140084BB8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140084BB8),
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
0x14000bfdc  mov     [rsp+arg_0], rbx
0x14000bfe1  mov     [rsp+arg_8], rsi
0x14000bfe6  push    rdi
0x14000bfe7  sub     rsp, 30h
0x14000bfeb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000bff1  mov     esi, r8d
0x14000bff4  mov     ebx, edx
0x14000bff6  mov     rdi, rcx
0x14000bff9  test    eax, eax
0x14000bffb  jz      loc_14000C0A2
0x14000c001  lea     rcx, SRWLock; SRWLock
0x14000c008  call    cs:__imp_AcquireSRWLockExclusive
0x14000c00f  nop     dword ptr [rax+rax+00h]
0x14000c014  mov     eax, cs:dword_140084B74
0x14000c01a  test    esi, esi
0x14000c01c  jz      short loc_14000C07E
0x14000c01e  cmp     esi, eax
0x14000c020  jnz     short loc_14000C07E
0x14000c022  mov     esi, 10h
0x14000c027  mov     [rsp+38h+var_14], 0
0x14000c02f  mov     edx, esi; unsigned __int64
0x14000c031  mov     [rsp+38h+Source], ebx
0x14000c035  lea     rcx, qword_140084BA8; this
0x14000c03c  mov     [rsp+38h+var_10], rdi
0x14000c041  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000c046  test    al, al
0x14000c048  jz      short loc_14000C07E
0x14000c04a  mov     rcx, cs:Destination; Destination
0x14000c051  lea     r8, [rsp+38h+Source]; Source
0x14000c056  mov     rax, cs:qword_140084BB8
0x14000c05d  mov     r9d, esi; SourceSize
0x14000c060  sub     rax, rcx
0x14000c063  cmp     rcx, cs:qword_140084BB8
0x14000c06a  sbb     rdx, rdx
0x14000c06d  and     rdx, rax; DestinationSize
0x14000c070  call    memcpy_s
0x14000c075  add     cs:Destination, rsi
0x14000c07c  jmp     short loc_14000C08F
0x14000c07e  neg     ebx
0x14000c080  sbb     eax, eax
0x14000c082  and     eax, 83Ah
0x14000c087  add     eax, 0FFFFF7C1h
0x14000c08c  lock and [rdi], eax
0x14000c08f  lea     rcx, SRWLock; SRWLock
0x14000c096  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c09d  nop     dword ptr [rax+rax+00h]
0x14000c0a2  mov     rbx, [rsp+38h+arg_0]
0x14000c0a7  mov     rsi, [rsp+38h+arg_8]
0x14000c0ac  add     rsp, 30h
0x14000c0b0  pop     rdi
0x14000c0b1  retn
```
