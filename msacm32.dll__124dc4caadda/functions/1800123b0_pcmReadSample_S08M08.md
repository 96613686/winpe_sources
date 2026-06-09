# pcmReadSample_S08M08

- ea: `0x1800123b0`
- end: `0x1800123c9`
- name: `pcmReadSample_S08M08`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
unsigned __int8 *__fastcall pcmReadSample_S08M08(unsigned __int8 *a1, _WORD *a2)
{
  unsigned __int8 *result; // rax

  result = a1 + 1;
  *a2 = *a1 | (*a1 << 8);
  return result;
}

```

## disassembly

```asm
0x1800123b0  movzx   eax, byte ptr [rcx]
0x1800123b3  movzx   r8d, ax
0x1800123b7  shl     r8w, 8
0x1800123bc  or      r8w, ax
0x1800123c0  lea     rax, [rcx+1]
0x1800123c4  mov     [rdx], r8w
0x1800123c8  retn
```
