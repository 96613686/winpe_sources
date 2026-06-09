# pcmIsValidFormat

- ea: `0x180002b54`
- end: `0x180002bad`
- name: `pcmIsValidFormat`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002488`
- `0x1800025bc`
- `0x180002834`

## callees

- `0x180002b54`

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
      if ( (_WORD)v2 == 1 && ((*(_WORD *)(a1 + 14) - 8) & 0xFFF7) == 0 )
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
0x180002b54  mov     r8, rcx
0x180002b57  test    rcx, rcx
0x180002b5a  jz      short loc_180002BAA
0x180002b5c  mov     r10d, 1
0x180002b62  cmp     r10w, [rcx]
0x180002b66  jnz     short loc_180002BAA
0x180002b68  movzx   ecx, word ptr [rcx+2]
0x180002b6c  cmp     cx, r10w
0x180002b70  jnz     short loc_180002BAA
0x180002b72  movzx   eax, word ptr [r8+0Eh]
0x180002b77  mov     edx, 0FFF7h
0x180002b7c  sub     ax, 8
0x180002b80  test    dx, ax
0x180002b83  jnz     short loc_180002BAA
0x180002b85  movzx   edx, word ptr [r8+0Eh]
0x180002b8a  movzx   r9d, word ptr [r8+0Ch]
0x180002b8f  shr     edx, 3
0x180002b92  shr     ecx, 1
0x180002b94  shl     edx, cl
0x180002b96  cmp     edx, r9d
0x180002b99  jnz     short loc_180002BAA
0x180002b9b  imul    r9d, [r8+4]
0x180002ba0  cmp     r9d, [r8+8]
0x180002ba4  jnz     short loc_180002BAA
0x180002ba6  mov     eax, r10d
0x180002ba9  retn
0x180002baa  xor     eax, eax
0x180002bac  retn
```
