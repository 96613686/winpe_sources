# DoubleList::First(void)

- ea: `0x140001c50`
- end: `0x140001c62`
- name: `?First@DoubleList@@QEAAPEAVListEntry@@XZ`
- size: `18`
- prototype: `struct ListEntry *__fastcall(DoubleList *__hidden this)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x140011b3c`
- `0x140019aa4`
- `0x14001d504`
- `0x14001dafc`
- `0x14001dcb4`
- `0x14001fbd8`
- `0x14001fd20`
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
struct ListEntry *__fastcall DoubleList::First(DoubleList *this)
{
  struct ListEntry *result; // rax

  result = 0;
  if ( *((DoubleList **)this + 2) != (DoubleList *)((char *)this + 16) )
    return (struct ListEntry *)*((_QWORD *)this + 2);
  return result;
}

```

## disassembly

```asm
0x140001c50  mov     rdx, [rcx+10h]
0x140001c54  add     rcx, 10h
0x140001c58  xor     eax, eax
0x140001c5a  cmp     rdx, rcx
0x140001c5d  cmovnz  rax, rdx
0x140001c61  retn
```
