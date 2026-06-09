# DiscpGetDefaultiScsiName

- ea: `0x180009c74`
- end: `0x180009cb1`
- name: `DiscpGetDefaultiScsiName`
- size: `61`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800034a0`
- `0x1800039d0`
- `0x180009f14`
- `0x18000d960`
- `0x18000f7f8`

## import_xrefs

- `ISCSIUM!DiscpCopyUnicodeString` at `0x180009c94`
- `ISCSIUM!DiscpCopyUnicodeString` at `0x180009c94`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ca3`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ca3`
- `ntdll!RtlEnterCriticalSection` at `0x180009c84`
- `ntdll!RtlEnterCriticalSection` at `0x180009c84`

## pseudocode

```c
__int64 __fastcall DiscpGetDefaultiScsiName(__int64 a1)
{
  RtlEnterCriticalSection(&DiscpCritSection);
  LODWORD(a1) = DiscpCopyUnicodeString(a1, DiscpiScsiNodeName);
  RtlLeaveCriticalSection(&DiscpCritSection);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180009c74  push    rbx
0x180009c76  sub     rsp, 20h
0x180009c7a  mov     rbx, rcx
0x180009c7d  lea     rcx, DiscpCritSection; CriticalSection
0x180009c84  call    cs:__imp_RtlEnterCriticalSection
0x180009c8a  mov     rdx, cs:DiscpiScsiNodeName
0x180009c91  mov     rcx, rbx
0x180009c94  call    cs:__imp_DiscpCopyUnicodeString
0x180009c9a  lea     rcx, DiscpCritSection; CriticalSection
0x180009ca1  mov     ebx, eax
0x180009ca3  call    cs:__imp_RtlLeaveCriticalSection
0x180009ca9  mov     eax, ebx
0x180009cab  add     rsp, 20h
0x180009caf  pop     rbx
0x180009cb0  retn
```
