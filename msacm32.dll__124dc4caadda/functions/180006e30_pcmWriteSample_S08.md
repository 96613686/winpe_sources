# pcmWriteSample_S08

- ea: `0x180006e30`
- end: `0x180006e4e`
- name: `pcmWriteSample_S08`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180006e30`

## pseudocode

```c
_WORD *__fastcall pcmWriteSample_S08(_WORD *a1, unsigned __int64 a2, __int16 a3)
{
  if ( a2 <= (unsigned __int64)a1 || a2 - (unsigned __int64)a1 < 2 )
    return (_WORD *)a2;
  *a1 = a3;
  return a1 + 1;
}

```

## disassembly

```asm
0x180006e30  cmp     rdx, rcx
0x180006e33  jbe     short loc_180006E4A
0x180006e35  mov     rax, rdx
0x180006e38  sub     rax, rcx
0x180006e3b  cmp     rax, 2
0x180006e3f  jb      short loc_180006E4A
0x180006e41  mov     [rcx], r8w
0x180006e45  lea     rax, [rcx+2]
0x180006e49  retn
0x180006e4a  mov     rax, rdx
0x180006e4d  retn
```
