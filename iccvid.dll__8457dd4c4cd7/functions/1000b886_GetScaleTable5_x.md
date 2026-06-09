# GetScaleTable5(x)

- ea: `0x1000b886`
- end: `0x1000b8a7`
- name: `_GetScaleTable5@4`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1000a640`
- `0x1000af30`
- `0x1000b8e0`
- `0x1000c2a0`

## callees

- `0x1000b886`

## pseudocode

```c
char __fastcall GetScaleTable5(__int16 a1)
{
  if ( a1 < 0 )
    return 0;
  if ( a1 >= 384 )
    return 31;
  return ScaleTable5[a1];
}

```

## disassembly

```asm
0x1000b886  xor     eax, eax
0x1000b888  cmp     ax, cx
0x1000b88b  jg      short loc_1000B8A4
0x1000b88d  mov     eax, 180h
0x1000b892  cmp     cx, ax
0x1000b895  jge     short loc_1000B8A1
0x1000b897  movsx   eax, cx
0x1000b89a  mov     al, ds:_ScaleTable5[eax]
0x1000b8a0  retn
0x1000b8a1  mov     al, 1Fh
0x1000b8a3  retn
0x1000b8a4  xor     al, al
0x1000b8a6  retn
```
