# GetBounding24(x)

- ea: `0x1000ccc4`
- end: `0x1000cce5`
- name: `_GetBounding24@4`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1000ccf0`
- `0x1000d260`
- `0x1000d7d0`

## callees

- `0x1000ccc4`

## pseudocode

```c
char __fastcall GetBounding24(__int16 a1)
{
  if ( a1 < 0 )
    return 0;
  if ( a1 >= 384 )
    return -1;
  return Bounding24[a1];
}

```

## disassembly

```asm
0x1000ccc4  xor     eax, eax
0x1000ccc6  cmp     ax, cx
0x1000ccc9  jg      short loc_1000CCE2
0x1000cccb  mov     eax, 180h
0x1000ccd0  cmp     cx, ax
0x1000ccd3  jge     short loc_1000CCDF
0x1000ccd5  movsx   eax, cx
0x1000ccd8  mov     al, ds:_Bounding24[eax]
0x1000ccde  retn
0x1000ccdf  or      al, 0FFh
0x1000cce1  retn
0x1000cce2  xor     al, al
0x1000cce4  retn
```
