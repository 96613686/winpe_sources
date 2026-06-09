# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000be08`
- end: `0x18000bedf`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `215`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008e78`
- `0x1800149f4`
- `0x18001c944`
- `0x18001cb08`
- `0x18001cc80`
- `0x18001e98c`
- `0x180027e74`
- `0x180027fec`
- `0x1800281b0`
- `0x180028328`
- `0x18002f04c`
- `0x180036a74`
- `0x1800451d8`

## callees

- `0x18000be08`
- `0x18000ce0c`
- `0x180013bfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bec2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bec2`

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
      && a3 == dword_1800708A4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800708D8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800708E8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800708E8),
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
0x18000be08  mov     [rsp+arg_0], rbx
0x18000be0d  mov     [rsp+arg_8], rsi
0x18000be12  push    rdi
0x18000be13  sub     rsp, 30h
0x18000be17  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000be1d  mov     esi, r8d
0x18000be20  mov     ebx, edx
0x18000be22  mov     rdi, rcx
0x18000be25  test    eax, eax
0x18000be27  jz      loc_18000BECE
0x18000be2d  lea     rcx, SRWLock; SRWLock
0x18000be34  call    cs:__imp_AcquireSRWLockExclusive
0x18000be3b  nop     dword ptr [rax+rax+00h]
0x18000be40  mov     eax, cs:dword_1800708A4
0x18000be46  test    esi, esi
0x18000be48  jz      short loc_18000BEAA
0x18000be4a  cmp     esi, eax
0x18000be4c  jnz     short loc_18000BEAA
0x18000be4e  mov     esi, 10h
0x18000be53  mov     [rsp+38h+var_14], 0
0x18000be5b  mov     edx, esi; unsigned __int64
0x18000be5d  mov     [rsp+38h+Source], ebx
0x18000be61  lea     rcx, qword_1800708D8; this
0x18000be68  mov     [rsp+38h+var_10], rdi
0x18000be6d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000be72  test    al, al
0x18000be74  jz      short loc_18000BEAA
0x18000be76  mov     rcx, cs:Destination; Destination
0x18000be7d  lea     r8, [rsp+38h+Source]; Source
0x18000be82  mov     rax, cs:qword_1800708E8
0x18000be89  mov     r9d, esi; SourceSize
0x18000be8c  sub     rax, rcx
0x18000be8f  cmp     rcx, cs:qword_1800708E8
0x18000be96  sbb     rdx, rdx
0x18000be99  and     rdx, rax; DestinationSize
0x18000be9c  call    memcpy_s
0x18000bea1  add     cs:Destination, rsi
0x18000bea8  jmp     short loc_18000BEBB
0x18000beaa  neg     ebx
0x18000beac  sbb     eax, eax
0x18000beae  and     eax, 83Ah
0x18000beb3  add     eax, 0FFFFF7C1h
0x18000beb8  lock and [rdi], eax
0x18000bebb  lea     rcx, SRWLock; SRWLock
0x18000bec2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bec9  nop     dword ptr [rax+rax+00h]
0x18000bece  mov     rbx, [rsp+38h+arg_0]
0x18000bed3  mov     rsi, [rsp+38h+arg_8]
0x18000bed8  add     rsp, 30h
0x18000bedc  pop     rdi
0x18000bedd  retn
```
