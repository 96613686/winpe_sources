# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140008f34`
- end: `0x140009012`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `222`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400052e0`
- `0x140005fe0`
- `0x14000f964`
- `0x14000fadc`

## callees

- `0x140008f34`
- `0x14000a33c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008fc8`
- `msvcrt!memcpy_s` at `0x140008fc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008ff5`

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
    AcquireSRWLockExclusive(&stru_1400239F0);
    if ( a3
      && a3 == dword_140023A04
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140023A38, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140023A48 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140023A48),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&stru_1400239F0);
  }
}

```

## disassembly

```asm
0x140008f34  mov     [rsp+arg_0], rbx
0x140008f39  mov     [rsp+arg_8], rsi
0x140008f3e  push    rdi
0x140008f3f  sub     rsp, 30h
0x140008f43  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140008f49  mov     esi, r8d
0x140008f4c  mov     ebx, edx
0x140008f4e  mov     rdi, rcx
0x140008f51  test    eax, eax
0x140008f53  jz      loc_140009001
0x140008f59  lea     rcx, stru_1400239F0; SRWLock
0x140008f60  call    cs:__imp_AcquireSRWLockExclusive
0x140008f67  nop     dword ptr [rax+rax+00h]
0x140008f6c  mov     eax, cs:dword_140023A04
0x140008f72  test    esi, esi
0x140008f74  jz      short loc_140008FDD
0x140008f76  cmp     esi, eax
0x140008f78  jnz     short loc_140008FDD
0x140008f7a  mov     esi, 10h
0x140008f7f  mov     [rsp+38h+var_14], 0
0x140008f87  mov     edx, esi; unsigned __int64
0x140008f89  mov     [rsp+38h+Source], ebx
0x140008f8d  lea     rcx, qword_140023A38; this
0x140008f94  mov     [rsp+38h+var_10], rdi
0x140008f99  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008f9e  test    al, al
0x140008fa0  jz      short loc_140008FDD
0x140008fa2  mov     rcx, cs:Destination; Destination
0x140008fa9  lea     r8, [rsp+38h+Source]; Source
0x140008fae  mov     rax, cs:qword_140023A48
0x140008fb5  mov     r9d, esi; SourceSize
0x140008fb8  sub     rax, rcx
0x140008fbb  cmp     rcx, cs:qword_140023A48
0x140008fc2  sbb     rdx, rdx
0x140008fc5  and     rdx, rax; DestinationSize
0x140008fc8  call    cs:__imp_memcpy_s
0x140008fcf  nop     dword ptr [rax+rax+00h]
0x140008fd4  add     cs:Destination, rsi
0x140008fdb  jmp     short loc_140008FEE
0x140008fdd  neg     ebx
0x140008fdf  sbb     eax, eax
0x140008fe1  and     eax, 83Ah
0x140008fe6  add     eax, 0FFFFF7C1h
0x140008feb  lock and [rdi], eax
0x140008fee  lea     rcx, stru_1400239F0; SRWLock
0x140008ff5  call    cs:__imp_ReleaseSRWLockExclusive
0x140008ffc  nop     dword ptr [rax+rax+00h]
0x140009001  mov     rbx, [rsp+38h+arg_0]
0x140009006  mov     rsi, [rsp+38h+arg_8]
0x14000900b  add     rsp, 30h
0x14000900f  pop     rdi
0x140009010  retn
```
