# ___doserrno

- ea: `0x1002d6a8`
- end: `0x1002d6bb`
- name: `___doserrno`
- size: `19`
- prototype: `unsigned int *__cdecl()`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x1002d6bb`
- `0x10034055`
- `0x10034171`
- `0x10034242`
- `0x100373d2`
- `0x100374c1`
- `0x10037d26`
- `0x1003bc6c`
- `0x1003bcf2`
- `0x1003c2b7`
- `0x1003c3cb`
- `0x1003cc3f`
- `0x1003cd5e`

## callees

- `0x1002d6a8`
- `0x1002f0b3`

## pseudocode

```c
unsigned int *__cdecl __doserrno()
{
  DWORD *v0; // eax

  v0 = _getptd_noexit();
  if ( v0 )
    return v0 + 3;
  else
    return (unsigned int *)&dword_1003FE1C;
}

```

## disassembly

```asm
0x1002d6a8  call    __getptd_noexit
0x1002d6ad  test    eax, eax
0x1002d6af  jnz     short loc_1002D6B7
0x1002d6b1  mov     eax, offset dword_1003FE1C
0x1002d6b6  retn
0x1002d6b7  add     eax, 0Ch
0x1002d6ba  retn
```
