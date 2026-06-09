# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800113c4`
- end: `0x18001148f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008aa0`
- `0x180008c74`
- `0x180008d54`
- `0x180008ec8`
- `0x18000903c`
- `0x1800091b0`
- `0x180009330`
- `0x180009410`
- `0x1800094f0`
- `0x1800095d0`
- `0x1800096b0`
- `0x18000ab34`

## callees

- `0x1800113c4`
- `0x1800124ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011452`
- `msvcrt!memcpy_s` at `0x180011452`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011479`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011479`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113f0`

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
      && a3 == dword_18001D394
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001D3B8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_18001D3C8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_18001D3C8),
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
0x1800113c4  mov     [rsp+arg_0], rbx
0x1800113c9  mov     [rsp+arg_8], rsi
0x1800113ce  push    rdi
0x1800113cf  sub     rsp, 30h
0x1800113d3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800113d9  mov     esi, r8d
0x1800113dc  mov     ebx, edx
0x1800113de  mov     rdi, rcx
0x1800113e1  test    eax, eax
0x1800113e3  jz      loc_18001147F
0x1800113e9  lea     rcx, SRWLock; SRWLock
0x1800113f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800113f6  mov     eax, cs:dword_18001D394
0x1800113fc  test    esi, esi
0x1800113fe  jz      short loc_180011461
0x180011400  cmp     esi, eax
0x180011402  jnz     short loc_180011461
0x180011404  mov     esi, 10h
0x180011409  mov     [rsp+38h+var_14], 0
0x180011411  mov     edx, esi; unsigned __int64
0x180011413  mov     [rsp+38h+Source], ebx
0x180011417  lea     rcx, qword_18001D3B8; this
0x18001141e  mov     [rsp+38h+var_10], rdi
0x180011423  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011428  test    al, al
0x18001142a  jz      short loc_180011461
0x18001142c  mov     rcx, cs:Destination; Destination
0x180011433  lea     r8, [rsp+38h+Source]; Source
0x180011438  mov     rax, cs:qword_18001D3C8
0x18001143f  mov     r9d, esi; SourceSize
0x180011442  sub     rax, rcx
0x180011445  cmp     rcx, cs:qword_18001D3C8
0x18001144c  sbb     rdx, rdx
0x18001144f  and     rdx, rax; DestinationSize
0x180011452  call    cs:__imp_memcpy_s
0x180011458  add     cs:Destination, rsi
0x18001145f  jmp     short loc_180011472
0x180011461  neg     ebx
0x180011463  sbb     eax, eax
0x180011465  and     eax, 83Ah
0x18001146a  add     eax, 0FFFFF7C1h
0x18001146f  lock and [rdi], eax
0x180011472  lea     rcx, SRWLock; SRWLock
0x180011479  call    cs:__imp_ReleaseSRWLockExclusive
0x18001147f  mov     rbx, [rsp+38h+arg_0]
0x180011484  mov     rsi, [rsp+38h+arg_8]
0x180011489  add     rsp, 30h
0x18001148d  pop     rdi
0x18001148e  retn
```
