# pcmReadSample_S16S08

- ea: `0x180012470`
- end: `0x18001249d`
- name: `pcmReadSample_S16S08`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_WORD *__fastcall pcmReadSample_S16S08(_WORD *a1, unsigned int *a2)
{
  _WORD *result; // rax

  result = a1 + 1;
  *a2 = ((((unsigned __int16)*a1 ^ 0x8080) & 0xFFFFFF00) << 16) | (unsigned __int16)((*a1 ^ 0x8080) << 8);
  return result;
}

```

## disassembly

```asm
0x180012470  movzx   r9d, word ptr [rcx]
0x180012474  xor     r9d, 8080h
0x18001247b  movzx   eax, r9w
0x18001247f  and     r9d, 0FFFFFF00h
0x180012486  shl     ax, 8
0x18001248a  movzx   r8d, ax
0x18001248e  lea     rax, [rcx+2]
0x180012492  shl     r9d, 10h
0x180012496  or      r8d, r9d
0x180012499  mov     [rdx], r8d
0x18001249c  retn
```
