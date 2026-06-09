# pcmIsValidFormat

- ea: `0x1800035e8`
- end: `0x18000364e`
- name: `pcmIsValidFormat`
- size: `102`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da4`
- `0x180002f10`
- `0x180003218`

## callees

- `0x1800035e8`

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
      if ( *(_DWORD *)(a1 + 4) )
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
  }
  return result;
}

```

## disassembly

```asm
0x1800035e8  mov     r8, rcx
0x1800035eb  test    rcx, rcx
0x1800035ee  jz      short loc_18000364B
0x1800035f0  mov     r10d, 1
0x1800035f6  cmp     r10w, [rcx]
0x1800035fa  jnz     short loc_18000364B
0x1800035fc  cmp     dword ptr [rcx+4], 0
0x180003600  jz      short loc_18000364B
0x180003602  movzx   ecx, word ptr [rcx+2]
0x180003606  movzx   eax, cx
0x180003609  sub     ax, r10w
0x18000360d  cmp     ax, r10w
0x180003611  ja      short loc_18000364B
0x180003613  movzx   eax, word ptr [r8+0Eh]
0x180003618  mov     edx, 0FFF7h
0x18000361d  sub     ax, 8
0x180003621  test    dx, ax
0x180003624  jnz     short loc_18000364B
0x180003626  movzx   edx, word ptr [r8+0Eh]
0x18000362b  movzx   r9d, word ptr [r8+0Ch]
0x180003630  shr     edx, 3
0x180003633  shr     ecx, 1
0x180003635  shl     edx, cl
0x180003637  cmp     edx, r9d
0x18000363a  jnz     short loc_18000364B
0x18000363c  imul    r9d, [r8+4]
0x180003641  cmp     r9d, [r8+8]
0x180003645  jnz     short loc_18000364B
0x180003647  mov     eax, r10d
0x18000364a  retn
0x18000364b  xor     eax, eax
0x18000364d  retn
```
