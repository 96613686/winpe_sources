# pcmReadSample_S16M16

- ea: `0x180006e60`
- end: `0x180006e75`
- name: `pcmReadSample_S16M16`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
unsigned __int16 *__fastcall pcmReadSample_S16M16(unsigned __int16 *a1, int *a2)
{
  unsigned __int16 *result; // rax

  result = a1 + 1;
  *a2 = *a1 | (*a1 << 16);
  return result;
}

```

## disassembly

```asm
0x180006e60  movzx   eax, word ptr [rcx]
0x180006e63  mov     r8d, eax
0x180006e66  shl     r8d, 10h
0x180006e6a  or      r8d, eax
0x180006e6d  lea     rax, [rcx+2]
0x180006e71  mov     [rdx], r8d
0x180006e74  retn
```
