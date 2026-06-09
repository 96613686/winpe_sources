# DiscpFindTargetByDiscoveryMechanism

- ea: `0x1800064f8`
- end: `0x180006592`
- name: `DiscpFindTargetByDiscoveryMechanism`
- size: `154`
- prototype: `__int64 __fastcall(__int64, wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001fb8`
- `0x180006c30`

## callees

- `0x1800061a8`
- `0x1800064f8`
- `0x180006598`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006530`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006530`
- `ntdll!RtlLeaveCriticalSection` at `0x18000657a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000657a`
- `ntdll!RtlEnterCriticalSection` at `0x180006520`
- `ntdll!RtlEnterCriticalSection` at `0x180006520`

## string_xrefs

- `0x180006526`: `Manually Configured:`

## pseudocode

```c
__int64 __fastcall DiscpFindTargetByDiscoveryMechanism(__int64 a1, wchar_t *a2, __int64 a3)
{
  __int64 v6; // rdx
  unsigned int TargetByTag; // ebx
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( !(unsigned int)_o__wcsicmp(a2, L"Manually Configured:") )
  {
    v6 = 2;
    goto LABEL_6;
  }
  if ( !(unsigned int)DiscpFindDiscoveryTag(a2, 1, &v9) )
  {
    v6 = *(unsigned int *)(v9 + 16);
LABEL_6:
    TargetByTag = DiscpFindTargetByTag(a1, v6, a3);
    goto LABEL_7;
  }
  TargetByTag = -268500923;
LABEL_7:
  RtlLeaveCriticalSection(&DiscpCritSection);
  return TargetByTag;
}

```

## disassembly

```asm
0x1800064f8  mov     [rsp+arg_0], rbx
0x1800064fd  mov     [rsp+arg_8], rsi
0x180006502  push    rdi
0x180006503  sub     rsp, 20h
0x180006507  mov     rsi, rcx
0x18000650a  mov     [rsp+28h+arg_18], 0
0x180006513  lea     rcx, DiscpCritSection; CriticalSection
0x18000651a  mov     rdi, r8
0x18000651d  mov     rbx, rdx
0x180006520  call    cs:__imp_RtlEnterCriticalSection
0x180006526  lea     rdx, aManuallyConfig; "Manually Configured:"
0x18000652d  mov     rcx, rbx
0x180006530  call    cs:__imp__o__wcsicmp
0x180006536  test    eax, eax
0x180006538  jz      short loc_180006561
0x18000653a  lea     r8, [rsp+28h+arg_18]
0x18000653f  mov     edx, 1
0x180006544  mov     rcx, rbx; pszSrc
0x180006547  call    DiscpFindDiscoveryTag
0x18000654c  test    eax, eax
0x18000654e  jnz     short loc_18000655A
0x180006550  mov     rax, [rsp+28h+arg_18]
0x180006555  mov     edx, [rax+10h]
0x180006558  jmp     short loc_180006566
0x18000655a  mov     ebx, 0EFFF0045h
0x18000655f  jmp     short loc_180006573
0x180006561  mov     edx, 2
0x180006566  mov     r8, rdi
0x180006569  mov     rcx, rsi
0x18000656c  call    DiscpFindTargetByTag
0x180006571  mov     ebx, eax
0x180006573  lea     rcx, DiscpCritSection; CriticalSection
0x18000657a  call    cs:__imp_RtlLeaveCriticalSection
0x180006580  mov     rsi, [rsp+28h+arg_8]
0x180006585  mov     eax, ebx
0x180006587  mov     rbx, [rsp+28h+arg_0]
0x18000658c  add     rsp, 20h
0x180006590  pop     rdi
0x180006591  retn
```
