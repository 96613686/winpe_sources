# __errno

- ea: `0x1002d6dc`
- end: `0x1002d6ef`
- name: `__errno`
- size: `19`
- prototype: `int *__cdecl()`
- caller_count: `75`
- callee_count: `2`
- tags: ``

## callers

- `0x10024740`
- `0x1002c520`
- `0x1002caf0`
- `0x1002cb69`
- `0x1002cdf5`
- `0x1002d562`
- `0x1002d6bb`
- `0x1002d730`
- `0x1002d804`
- `0x1002d9e1`
- `0x1002da74`
- `0x1002df32`
- `0x1002df6a`
- `0x1002dffc`
- `0x1002e0f7`
- `0x1002eb6e`
- `0x1002f268`
- `0x1002f856`
- `0x1002fbd0`
- `0x1002fd21`
- `0x1002fdef`
- `0x1002fedb`
- `0x1002ff9c`
- `0x100308ab`
- `0x10030969`
- `0x10030c59`
- `0x10032382`
- `0x100325d2`
- `0x10032721`
- `0x100334b0`
- `0x10034055`
- `0x10034171`
- `0x100341ed`
- `0x10034242`
- `0x10034efc`
- `0x10035a4e`
- `0x10035d83`
- `0x100360c6`
- `0x10036235`
- `0x100366af`
- `0x100368f4`
- `0x10036c5e`
- `0x10036d9d`
- `0x10037004`
- `0x1003711c`
- `0x10037188`
- `0x1003735a`
- `0x1003737e`
- `0x100373d2`
- `0x100374c1`

## callees

- `0x1002d6dc`
- `0x1002f0b3`

## pseudocode

```c
int *__cdecl _errno()
{
  DWORD *v0; // eax

  v0 = _getptd_noexit();
  if ( v0 )
    return (int *)(v0 + 2);
  else
    return &dword_1003FE18;
}

```

## disassembly

```asm
0x1002d6dc  call    __getptd_noexit
0x1002d6e1  test    eax, eax
0x1002d6e3  jnz     short loc_1002D6EB
0x1002d6e5  mov     eax, offset dword_1003FE18
0x1002d6ea  retn
0x1002d6eb  add     eax, 8
0x1002d6ee  retn
```
