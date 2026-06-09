# pcmIsValidFormat

- ea: `0x180002988`
- end: `0x1800029e8`
- name: `pcmIsValidFormat`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fe4`
- `0x1800021b8`
- `0x1800025a0`

## callees

- `0x180002988`

## pseudocode

```c
_BOOL8 __fastcall pcmIsValidFormat(__int64 a1)
{
  unsigned int v2; // ecx
  int v3; // r8d
  _BOOL8 result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *(_WORD *)a1 == 1 && ((*(_WORD *)(a1 + 14) - 8) & 0xFFF7) == 0 )
    {
      v2 = *(unsigned __int16 *)(a1 + 2);
      if ( (unsigned __int16)(v2 - 1) <= 1u )
      {
        v3 = *(unsigned __int16 *)(a1 + 14) >> 3 << (v2 >> 1);
        if ( v3 == *(unsigned __int16 *)(a1 + 12) && *(_DWORD *)(a1 + 4) * v3 == *(_DWORD *)(a1 + 8) )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002988  mov     rdx, rcx
0x18000298b  test    rcx, rcx
0x18000298e  jz      short loc_1800029E5
0x180002990  mov     r9d, 1
0x180002996  cmp     [rcx], r9w
0x18000299a  jnz     short loc_1800029E5
0x18000299c  movzx   eax, word ptr [rcx+0Eh]
0x1800029a0  mov     ecx, 0FFF7h
0x1800029a5  sub     ax, 8
0x1800029a9  test    cx, ax
0x1800029ac  jnz     short loc_1800029E5
0x1800029ae  movzx   ecx, word ptr [rdx+2]
0x1800029b2  movzx   eax, cx
0x1800029b5  sub     ax, r9w
0x1800029b9  cmp     ax, r9w
0x1800029bd  ja      short loc_1800029E5
0x1800029bf  movzx   r8d, word ptr [rdx+0Eh]
0x1800029c4  shr     ecx, 1
0x1800029c6  shr     r8d, 3
0x1800029ca  shl     r8d, cl
0x1800029cd  movzx   ecx, word ptr [rdx+0Ch]
0x1800029d1  cmp     r8d, ecx
0x1800029d4  jnz     short loc_1800029E5
0x1800029d6  imul    r8d, [rdx+4]
0x1800029db  cmp     r8d, [rdx+8]
0x1800029df  jnz     short loc_1800029E5
0x1800029e1  mov     eax, r9d
0x1800029e4  retn
0x1800029e5  xor     eax, eax
0x1800029e7  retn
```
