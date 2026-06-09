# NbtValidateReceiveRequest

- ea: `0x1400280f4`
- end: `0x14002813d`
- name: `NbtValidateReceiveRequest`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010680`
- `0x140021c1c`
- `0x14002f40c`

## callees

- `0x1400280f4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028122`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028122`

## pseudocode

```c
PVOID __fastcall NbtValidateReceiveRequest(__int64 a1)
{
  struct _MDL *i; // rbx
  PVOID result; // rax

  for ( i = *(struct _MDL **)(a1 + 8); i; i = i->Next )
  {
    if ( (i->MdlFlags & 5) == 0 )
      result = MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000010u);
  }
  return result;
}

```

## disassembly

```asm
0x1400280f4  push    rbx
0x1400280f6  sub     rsp, 30h
0x1400280fa  mov     rbx, [rcx+8]
0x1400280fe  jmp     short loc_140028131
0x140028100  test    byte ptr [rbx+0Ah], 5
0x140028104  jnz     short loc_14002812E
0x140028106  xor     r9d, r9d; RequestedAddress
0x140028109  mov     [rsp+38h+Priority], 40000010h; Priority
0x140028111  xor     edx, edx; AccessMode
0x140028113  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002811b  mov     rcx, rbx; MemoryDescriptorList
0x14002811e  lea     r8d, [r9+1]; CacheType
0x140028122  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140028129  nop     dword ptr [rax+rax+00h]
0x14002812e  mov     rbx, [rbx]
0x140028131  test    rbx, rbx
0x140028134  jnz     short loc_140028100
0x140028136  add     rsp, 30h
0x14002813a  pop     rbx
0x14002813b  retn
```
