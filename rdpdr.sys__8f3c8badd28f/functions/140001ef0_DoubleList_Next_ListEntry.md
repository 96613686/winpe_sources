# DoubleList::Next(ListEntry *)

- ea: `0x140001ef0`
- end: `0x140001f01`
- name: `?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z`
- size: `17`
- prototype: `struct ListEntry *__fastcall(DoubleList *__hidden this, struct ListEntry *)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x140011b3c`
- `0x140019aa4`
- `0x14001d504`
- `0x14001dafc`
- `0x14001dcb4`
- `0x140024360`
- `0x140026380`
- `0x1400268e0`
- `0x140026a48`
- `0x140027f30`
- `0x140027fe0`
- `0x140029c90`
- `0x14002ac20`
- `0x14002be98`
- `0x14002c940`

## pseudocode

```c
struct ListEntry *__fastcall DoubleList::Next(DoubleList *this, struct ListEntry *a2)
{
  struct ListEntry *result; // rax

  result = 0;
  if ( *(DoubleList **)a2 != (DoubleList *)((char *)this + 16) )
    return *(struct ListEntry **)a2;
  return result;
}

```

## disassembly

```asm
0x140001ef0  mov     r8, [rdx]
0x140001ef3  xor     eax, eax
0x140001ef5  add     rcx, 10h
0x140001ef9  cmp     r8, rcx
0x140001efc  cmovnz  rax, r8
0x140001f00  retn
```
