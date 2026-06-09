# pcmReadSample_M16M16

- ea: `0x180006ee0`
- end: `0x180006eeb`
- name: `pcmReadSample_M16M16`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_WORD *__fastcall pcmReadSample_M16M16(_WORD *a1, _WORD *a2)
{
  *a2 = *a1;
  return a1 + 1;
}

```

## disassembly

```asm
0x180006ee0  movzx   eax, word ptr [rcx]
0x180006ee3  mov     [rdx], ax
0x180006ee6  lea     rax, [rcx+2]
0x180006eea  retn
```
