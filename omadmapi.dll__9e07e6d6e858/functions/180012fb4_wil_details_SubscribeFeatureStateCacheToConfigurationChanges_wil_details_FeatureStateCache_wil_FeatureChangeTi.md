# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180012fb4`
- end: `0x18001308b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ca60`
- `0x18000ded4`

## callees

- `0x18000649c`
- `0x180012fb4`
- `0x180013f2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001306e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001306e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012fe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012fe0`

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
      && a3 == dword_180032914
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180032948, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180032958 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180032958),
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
0x180012fb4  mov     [rsp+arg_0], rbx
0x180012fb9  mov     [rsp+arg_8], rsi
0x180012fbe  push    rdi
0x180012fbf  sub     rsp, 30h
0x180012fc3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012fc9  mov     esi, r8d
0x180012fcc  mov     ebx, edx
0x180012fce  mov     rdi, rcx
0x180012fd1  test    eax, eax
0x180012fd3  jz      loc_18001307A
0x180012fd9  lea     rcx, SRWLock; SRWLock
0x180012fe0  call    cs:__imp_AcquireSRWLockExclusive
0x180012fe7  nop     dword ptr [rax+rax+00h]
0x180012fec  mov     eax, cs:dword_180032914
0x180012ff2  test    esi, esi
0x180012ff4  jz      short loc_180013056
0x180012ff6  cmp     esi, eax
0x180012ff8  jnz     short loc_180013056
0x180012ffa  mov     esi, 10h
0x180012fff  mov     [rsp+38h+var_14], 0
0x180013007  mov     edx, esi; unsigned __int64
0x180013009  mov     [rsp+38h+Source], ebx
0x18001300d  lea     rcx, qword_180032948; this
0x180013014  mov     [rsp+38h+var_10], rdi
0x180013019  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001301e  test    al, al
0x180013020  jz      short loc_180013056
0x180013022  mov     rcx, cs:Destination; Destination
0x180013029  lea     r8, [rsp+38h+Source]; Source
0x18001302e  mov     rax, cs:qword_180032958
0x180013035  mov     r9d, esi; SourceSize
0x180013038  sub     rax, rcx
0x18001303b  cmp     rcx, cs:qword_180032958
0x180013042  sbb     rdx, rdx
0x180013045  and     rdx, rax; DestinationSize
0x180013048  call    memcpy_s
0x18001304d  add     cs:Destination, rsi
0x180013054  jmp     short loc_180013067
0x180013056  neg     ebx
0x180013058  sbb     eax, eax
0x18001305a  and     eax, 83Ah
0x18001305f  add     eax, 0FFFFF7C1h
0x180013064  lock and [rdi], eax
0x180013067  lea     rcx, SRWLock; SRWLock
0x18001306e  call    cs:__imp_ReleaseSRWLockExclusive
0x180013075  nop     dword ptr [rax+rax+00h]
0x18001307a  mov     rbx, [rsp+38h+arg_0]
0x18001307f  mov     rsi, [rsp+38h+arg_8]
0x180013084  add     rsp, 30h
0x180013088  pop     rdi
0x180013089  retn
```
