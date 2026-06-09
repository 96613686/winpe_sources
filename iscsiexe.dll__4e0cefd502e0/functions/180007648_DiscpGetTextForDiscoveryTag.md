# DiscpGetTextForDiscoveryTag

- ea: `0x180007648`
- end: `0x1800076d4`
- name: `DiscpGetTextForDiscoveryTag`
- size: `140`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180006c30`
- `0x180011df0`

## callees

- `0x180007648`

## import_xrefs

- `ISCSIUM!DiscpDuplicateString` at `0x18000766b`
- `ISCSIUM!DiscpDuplicateString` at `0x1800076ad`
- `ISCSIUM!DiscpDuplicateString` at `0x18000766b`
- `ISCSIUM!DiscpDuplicateString` at `0x1800076ad`
- `ntdll!RtlLeaveCriticalSection` at `0x1800076bc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800076bc`
- `ntdll!RtlEnterCriticalSection` at `0x18000767c`
- `ntdll!RtlEnterCriticalSection` at `0x18000767c`

## string_xrefs

- `0x180007661`: `Manually Configured:`

## pseudocode

```c
__int64 __fastcall DiscpGetTextForDiscoveryTag(int a1, __int64 a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rdx

  if ( a1 == 2 )
  {
    return (unsigned int)DiscpDuplicateString(a2, L"Manually Configured:");
  }
  else
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    v5 = DiscpDiscoveryTagList;
    v4 = -268500923;
    while ( v5 != (_DWORD *)&DiscpDiscoveryTagList )
    {
      if ( v5[4] == a1 )
      {
        v4 = DiscpDuplicateString(a2, v5 + 6);
        break;
      }
      v5 = *(_DWORD **)v5;
    }
    RtlLeaveCriticalSection(&DiscpCritSection);
  }
  return v4;
}

```

## disassembly

```asm
0x180007648  mov     [rsp+arg_0], rbx
0x18000764d  mov     [rsp+arg_8], rsi
0x180007652  push    rdi
0x180007653  sub     rsp, 20h
0x180007657  mov     rsi, rdx
0x18000765a  mov     edi, ecx
0x18000765c  cmp     ecx, 2
0x18000765f  jnz     short loc_180007675
0x180007661  lea     rdx, aManuallyConfig; "Manually Configured:"
0x180007668  mov     rcx, rsi
0x18000766b  call    cs:__imp_DiscpDuplicateString
0x180007671  mov     ebx, eax
0x180007673  jmp     short loc_1800076C2
0x180007675  lea     rcx, DiscpCritSection; CriticalSection
0x18000767c  call    cs:__imp_RtlEnterCriticalSection
0x180007682  mov     rdx, cs:DiscpDiscoveryTagList
0x180007689  lea     rax, DiscpDiscoveryTagList
0x180007690  mov     ebx, 0EFFF0045h
0x180007695  jmp     short loc_18000769F
0x180007697  cmp     [rdx+10h], edi
0x18000769a  jz      short loc_1800076A6
0x18000769c  mov     rdx, [rdx]
0x18000769f  cmp     rdx, rax
0x1800076a2  jnz     short loc_180007697
0x1800076a4  jmp     short loc_1800076B5
0x1800076a6  add     rdx, 18h
0x1800076aa  mov     rcx, rsi
0x1800076ad  call    cs:__imp_DiscpDuplicateString
0x1800076b3  mov     ebx, eax
0x1800076b5  lea     rcx, DiscpCritSection; CriticalSection
0x1800076bc  call    cs:__imp_RtlLeaveCriticalSection
0x1800076c2  mov     rsi, [rsp+28h+arg_8]
0x1800076c7  mov     eax, ebx
0x1800076c9  mov     rbx, [rsp+28h+arg_0]
0x1800076ce  add     rsp, 20h
0x1800076d2  pop     rdi
0x1800076d3  retn
```
