# adpcmIsValidFormat

- ea: `0x180002910`
- end: `0x180002981`
- name: `adpcmIsValidFormat`
- size: `113`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fe4`
- `0x1800021b8`
- `0x1800025a0`

## callees

- `0x180002910`

## pseudocode

```c
_BOOL8 __fastcall adpcmIsValidFormat(_WORD *a1)
{
  unsigned int v2; // r9d
  unsigned int v3; // ecx
  _BOOL8 result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *a1 == 2 && a1[7] == 4 && (unsigned __int16)(a1[1] - 1) <= 1u && a1[8] >= 0x20u )
    {
      v2 = (unsigned __int16)a1[6];
      v3 = (unsigned __int16)a1[1];
      if ( 7 * v3 <= v2 && a1[9] == (unsigned __int16)(8 * (v2 - (7 << (v3 >> 1))) / (4 << (v3 >> 1))) + 2 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002910  mov     r8, rcx
0x180002913  test    rcx, rcx
0x180002916  jz      short loc_18000297E
0x180002918  cmp     word ptr [rcx], 2
0x18000291c  jnz     short loc_18000297E
0x18000291e  mov     r10d, 4
0x180002924  cmp     [rcx+0Eh], r10w
0x180002929  jnz     short loc_18000297E
0x18000292b  movzx   eax, word ptr [rcx+2]
0x18000292f  lea     r11d, [r10-3]
0x180002933  sub     ax, r11w
0x180002937  cmp     ax, r11w
0x18000293b  ja      short loc_18000297E
0x18000293d  cmp     word ptr [rcx+10h], 20h ; ' '
0x180002942  jb      short loc_18000297E
0x180002944  movzx   r9d, word ptr [rcx+0Ch]
0x180002949  movzx   ecx, word ptr [rcx+2]
0x18000294d  imul    eax, ecx, 7
0x180002950  cmp     eax, r9d
0x180002953  ja      short loc_18000297E
0x180002955  shr     ecx, 1
0x180002957  lea     edx, [r10+3]
0x18000295b  shl     edx, cl
0x18000295d  sub     r9d, edx
0x180002960  shl     r10d, cl
0x180002963  shl     r9d, 3
0x180002967  xor     edx, edx
0x180002969  mov     eax, r9d
0x18000296c  div     r10d
0x18000296f  add     ax, 2
0x180002973  cmp     [r8+12h], ax
0x180002978  jnz     short loc_18000297E
0x18000297a  mov     eax, r11d
0x18000297d  retn
0x18000297e  xor     eax, eax
0x180002980  retn
```
