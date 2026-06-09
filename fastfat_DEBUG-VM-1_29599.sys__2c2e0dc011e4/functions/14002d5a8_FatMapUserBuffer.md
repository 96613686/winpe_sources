# FatMapUserBuffer

- ea: `0x14002d5a8`
- end: `0x14002d607`
- name: `FatMapUserBuffer`
- size: `95`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14002d918`
- `0x14002e0cc`
- `0x14002ed1c`
- `0x140036d14`
- `0x140037240`
- `0x140037ab0`
- `0x14003f6e0`
- `0x14003fcfc`
- `0x14004573c`
- `0x14004af08`

## callees

- `0x14002d5a8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002d5e4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002d5e4`
- `ntoskrnl!ExRaiseStatus` at `0x14002d5fa`
- `ntoskrnl!ExRaiseStatus` at `0x14002d5fa`

## pseudocode

```c
PVOID __fastcall FatMapUserBuffer(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  PVOID result; // rax

  v2 = *(_QWORD *)(a2 + 8);
  if ( !v2 )
    return *(PVOID *)(a2 + 112);
  if ( (*(_BYTE *)(v2 + 10) & 5) != 0 )
    result = *(PVOID *)(v2 + 24);
  else
    result = MmMapLockedPagesSpecifyCache((PMDL)v2, 0, MmCached, 0, 0, 0x40000010u);
  if ( !result )
    ExRaiseStatus(-1073741670);
  return result;
}

```

## disassembly

```asm
0x14002d5a8  sub     rsp, 38h
0x14002d5ac  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14002d5b0  test    rcx, rcx
0x14002d5b3  jnz     short loc_14002D5BF
0x14002d5b5  mov     rax, [rdx+70h]
0x14002d5b9  add     rsp, 38h
0x14002d5bd  retn
0x14002d5bf  test    byte ptr [rcx+0Ah], 5
0x14002d5c3  jz      short loc_14002D5CB
0x14002d5c5  mov     rax, [rcx+18h]
0x14002d5c9  jmp     short loc_14002D5F0
0x14002d5cb  xor     r9d, r9d; RequestedAddress
0x14002d5ce  mov     [rsp+38h+Priority], 40000010h; Priority
0x14002d5d6  xor     edx, edx; AccessMode
0x14002d5d8  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002d5e0  lea     r8d, [r9+1]; CacheType
0x14002d5e4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002d5eb  nop     dword ptr [rax+rax+00h]
0x14002d5f0  test    rax, rax
0x14002d5f3  jnz     short loc_14002D5B9
0x14002d5f5  mov     ecx, 0C000009Ah; Status
0x14002d5fa  call    cs:__imp_ExRaiseStatus
```
