# pcmReadSample_S08S16

- ea: `0x180012400`
- end: `0x18001242d`
- name: `pcmReadSample_S08S16`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_DWORD *__fastcall pcmReadSample_S08S16(_DWORD *a1, _WORD *a2)
{
  _DWORD *result; // rax

  result = a1 + 1;
  *a2 = (BYTE1(*a1) | HIWORD(*a1) & 0xFF00) ^ 0x8080;
  return result;
}

```

## disassembly

```asm
0x180012400  mov     eax, [rcx]
0x180012402  mov     r9d, 0FF00h
0x180012408  mov     r8d, eax
0x18001240b  shr     ax, 8
0x18001240f  shr     r8d, 10h
0x180012413  and     r8w, r9w
0x180012417  or      r8w, ax
0x18001241b  mov     eax, 8080h
0x180012420  xor     r8w, ax
0x180012424  lea     rax, [rcx+4]
0x180012428  mov     [rdx], r8w
0x18001242c  retn
```
