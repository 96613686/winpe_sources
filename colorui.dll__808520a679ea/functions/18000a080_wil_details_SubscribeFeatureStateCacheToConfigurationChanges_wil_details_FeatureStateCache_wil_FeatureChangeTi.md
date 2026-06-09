# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000a080`
- end: `0x18000a14b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006798`
- `0x180014030`
- `0x180014110`

## callees

- `0x18000a080`
- `0x18000b464`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a10e`
- `msvcrt!memcpy_s` at `0x18000a10e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a135`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a135`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a0ac`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a0ac`

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
      && a3 == dword_1800214BC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800214E0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800214F0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800214F0),
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
0x18000a080  mov     [rsp+arg_0], rbx
0x18000a085  mov     [rsp+arg_8], rsi
0x18000a08a  push    rdi
0x18000a08b  sub     rsp, 30h
0x18000a08f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a095  mov     esi, r8d
0x18000a098  mov     ebx, edx
0x18000a09a  mov     rdi, rcx
0x18000a09d  test    eax, eax
0x18000a09f  jz      loc_18000A13B
0x18000a0a5  lea     rcx, SRWLock; SRWLock
0x18000a0ac  call    cs:__imp_AcquireSRWLockExclusive
0x18000a0b2  mov     eax, cs:dword_1800214BC
0x18000a0b8  test    esi, esi
0x18000a0ba  jz      short loc_18000A11D
0x18000a0bc  cmp     esi, eax
0x18000a0be  jnz     short loc_18000A11D
0x18000a0c0  mov     esi, 10h
0x18000a0c5  mov     [rsp+38h+var_14], 0
0x18000a0cd  mov     edx, esi; unsigned __int64
0x18000a0cf  mov     [rsp+38h+Source], ebx
0x18000a0d3  lea     rcx, qword_1800214E0; this
0x18000a0da  mov     [rsp+38h+var_10], rdi
0x18000a0df  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a0e4  test    al, al
0x18000a0e6  jz      short loc_18000A11D
0x18000a0e8  mov     rcx, cs:Destination; Destination
0x18000a0ef  lea     r8, [rsp+38h+Source]; Source
0x18000a0f4  mov     rax, cs:qword_1800214F0
0x18000a0fb  mov     r9d, esi; SourceSize
0x18000a0fe  sub     rax, rcx
0x18000a101  cmp     rcx, cs:qword_1800214F0
0x18000a108  sbb     rdx, rdx
0x18000a10b  and     rdx, rax; DestinationSize
0x18000a10e  call    cs:__imp_memcpy_s
0x18000a114  add     cs:Destination, rsi
0x18000a11b  jmp     short loc_18000A12E
0x18000a11d  neg     ebx
0x18000a11f  sbb     eax, eax
0x18000a121  and     eax, 83Ah
0x18000a126  add     eax, 0FFFFF7C1h
0x18000a12b  lock and [rdi], eax
0x18000a12e  lea     rcx, SRWLock; SRWLock
0x18000a135  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a13b  mov     rbx, [rsp+38h+arg_0]
0x18000a140  mov     rsi, [rsp+38h+arg_8]
0x18000a145  add     rsp, 30h
0x18000a149  pop     rdi
0x18000a14a  retn
```
