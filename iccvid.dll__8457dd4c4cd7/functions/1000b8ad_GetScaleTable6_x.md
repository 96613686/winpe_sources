# GetScaleTable6(x)

- ea: `0x1000b8ad`
- end: `0x1000b8ce`
- name: `_GetScaleTable6@4`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1000b8e0`
- `0x1000c2a0`

## callees

- `0x1000b8ad`

## pseudocode

```c
char __fastcall GetScaleTable6(__int16 a1)
{
  if ( a1 < 0 )
    return 0;
  if ( a1 >= 384 )
    return 63;
  return ScaleTable6[a1];
}

```

## disassembly

```asm
0x1000b8ad  xor     eax, eax
0x1000b8af  cmp     ax, cx
0x1000b8b2  jg      short loc_1000B8CB
0x1000b8b4  mov     eax, 180h
0x1000b8b9  cmp     cx, ax
0x1000b8bc  jge     short loc_1000B8C8
0x1000b8be  movsx   eax, cx
0x1000b8c1  mov     al, ds:_ScaleTable6[eax]
0x1000b8c7  retn
0x1000b8c8  mov     al, 3Fh ; '?'
0x1000b8ca  retn
0x1000b8cb  xor     al, al
0x1000b8cd  retn
```
