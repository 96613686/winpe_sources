# pcmReadSample_S08M16

- ea: `0x1800123d0`
- end: `0x1800123f9`
- name: `pcmReadSample_S08M16`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_WORD *__fastcall pcmReadSample_S08M16(_WORD *a1, _WORD *a2)
{
  *a2 = *a1 ^ (unsigned __int8)(*(_BYTE *)a1 ^ HIBYTE(*a1)) ^ 0x8080;
  return a1 + 1;
}

```

## disassembly

```asm
0x1800123d0  movzx   eax, word ptr [rcx]
0x1800123d3  mov     r8d, 0FFh
0x1800123d9  shr     ax, 8
0x1800123dd  xor     ax, [rcx]
0x1800123e0  and     ax, r8w
0x1800123e4  mov     r8d, 8080h
0x1800123ea  xor     ax, [rcx]
0x1800123ed  xor     ax, r8w
0x1800123f1  mov     [rdx], ax
0x1800123f4  lea     rax, [rcx+2]
0x1800123f8  retn
```
