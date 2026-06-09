# pcmIsValidFormat

- ea: `0x180002d70`
- end: `0x180002dd0`
- name: `pcmIsValidFormat`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002460`
- `0x1800025f8`
- `0x180002988`

## callees

- `0x180002d70`

## pseudocode

```c
_BOOL8 __fastcall pcmIsValidFormat(__int64 a1)
{
  unsigned int v2; // ecx
  int v3; // r9d
  _BOOL8 result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *(_WORD *)a1 == 1 )
    {
      v2 = *(unsigned __int16 *)(a1 + 2);
      if ( (unsigned __int16)(v2 - 1) <= 1u && ((*(_WORD *)(a1 + 14) - 8) & 0xFFF7) == 0 )
      {
        v3 = *(unsigned __int16 *)(a1 + 12);
        if ( *(unsigned __int16 *)(a1 + 14) >> 3 << (v2 >> 1) == v3 && *(_DWORD *)(a1 + 4) * v3 == *(_DWORD *)(a1 + 8) )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d70  mov     r8, rcx
0x180002d73  test    rcx, rcx
0x180002d76  jz      short loc_180002DCD
0x180002d78  mov     r10d, 1
0x180002d7e  cmp     r10w, [rcx]
0x180002d82  jnz     short loc_180002DCD
0x180002d84  movzx   ecx, word ptr [rcx+2]
0x180002d88  movzx   eax, cx
0x180002d8b  sub     ax, r10w
0x180002d8f  cmp     ax, r10w
0x180002d93  ja      short loc_180002DCD
0x180002d95  movzx   eax, word ptr [r8+0Eh]
0x180002d9a  mov     edx, 0FFF7h
0x180002d9f  sub     ax, 8
0x180002da3  test    dx, ax
0x180002da6  jnz     short loc_180002DCD
0x180002da8  movzx   edx, word ptr [r8+0Eh]
0x180002dad  movzx   r9d, word ptr [r8+0Ch]
0x180002db2  shr     edx, 3
0x180002db5  shr     ecx, 1
0x180002db7  shl     edx, cl
0x180002db9  cmp     edx, r9d
0x180002dbc  jnz     short loc_180002DCD
0x180002dbe  imul    r9d, [r8+4]
0x180002dc3  cmp     r9d, [r8+8]
0x180002dc7  jnz     short loc_180002DCD
0x180002dc9  mov     eax, r10d
0x180002dcc  retn
0x180002dcd  xor     eax, eax
0x180002dcf  retn
```
