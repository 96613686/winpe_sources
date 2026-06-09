# pcmReadSample_S16M08

- ea: `0x180012440`
- end: `0x180012466`
- name: `pcmReadSample_S16M08`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
unsigned __int8 *__fastcall pcmReadSample_S16M08(unsigned __int8 *a1, int *a2)
{
  unsigned __int8 *result; // rax

  result = a1 + 1;
  *a2 = (unsigned __int16)((*a1 ^ 0xFF80) << 8) | ((unsigned __int16)((*a1 ^ 0xFF80) << 8) << 16);
  return result;
}

```

## disassembly

```asm
0x180012440  movzx   eax, byte ptr [rcx]
0x180012443  mov     r8d, 0FF80h
0x180012449  xor     ax, r8w
0x18001244d  shl     ax, 8
0x180012451  movzx   eax, ax
0x180012454  mov     r8d, eax
0x180012457  shl     r8d, 10h
0x18001245b  or      r8d, eax
0x18001245e  lea     rax, [rcx+1]
0x180012462  mov     [rdx], r8d
0x180012465  retn
```
