# __memset_spec_ermsb

- ea: `0x140001800`
- end: `0x140001907`
- name: `__memset_spec_ermsb`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001800`
- `0x140001940`

## pseudocode

```c
__int64 __fastcall _memset_spec_ermsb(char *a1, unsigned __int8 a2, unsigned __int64 a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  unsigned __int64 v9; // r8
  __m128 *v10; // r9
  unsigned __int64 v11; // r8
  char *v12; // r9
  unsigned __int64 v13; // r8

  result = (__int64)a1;
  v4 = 0x101010101010101LL * a2;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( a3 >= 0x40 )
  {
    if ( a3 >= 0x320 )
      return _memset_spec_ermsb_repmovsb();
    *(__m128 *)a1 = v5;
    v6 = &a1[a3];
    a1 = (char *)((unsigned __int64)(a1 + 16) & 0xFFFFFFFFFFFFFFF0uLL);
    a3 = v6 - a1;
    if ( a3 >= 0x40 )
    {
      v7 = (__m128 *)&a1[a3 - 16];
      v8 = (_OWORD *)((unsigned __int64)&a1[a3 - 48] & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = a3 >> 6;
      do
      {
        *(__m128 *)a1 = v5;
        *((__m128 *)a1 + 1) = v5;
        a1 += 64;
        --v9;
        *((__m128 *)a1 - 2) = v5;
        *((__m128 *)a1 - 1) = v5;
      }
      while ( v9 );
      *v8 = v5;
      v8[1] = v5;
      v8[2] = v5;
      *v7 = v5;
      return result;
    }
LABEL_8:
    v10 = (__m128 *)&a1[a3 - 16];
    *(__m128 *)a1 = v5;
    v11 = (a3 & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)&a1[v11] = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( a3 >= 0x10 )
    goto LABEL_8;
  if ( a3 < 4 )
  {
    if ( a3 )
    {
      *a1 = v4;
      if ( a3 != 1 )
        *(_WORD *)&a1[a3 - 2] = v4;
    }
  }
  else
  {
    v12 = &a1[a3 - 4];
    *(_DWORD *)a1 = v4;
    v13 = (a3 & 8) >> 1;
    *(_DWORD *)v12 = v4;
    *(_DWORD *)&a1[v13] = v4;
    *(_DWORD *)&v12[-v13] = v4;
  }
  return result;
}

```

## disassembly

```asm
0x140001800  mov     rax, rcx
0x140001803  movzx   edx, dl
0x140001806  mov     r9, 101010101010101h
0x140001810  imul    rdx, r9
0x140001814  movq    xmm0, rdx
0x140001819  movlhps xmm0, xmm0
0x14000181c  cmp     r8, 40h ; '@'
0x140001820  jb      short loc_140001890
0x140001822  cmp     r8, 320h
0x140001829  jnb     __memset_spec_ermsb_repmovsb
0x14000182f  movups  xmmword ptr [rcx], xmm0
0x140001832  add     r8, rcx
0x140001835  add     rcx, 10h
0x140001839  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000183d  sub     r8, rcx
0x140001840  cmp     r8, 40h ; '@'
0x140001844  jb      short loc_140001896
0x140001846  lea     rdx, [rcx+r8-10h]
0x14000184b  lea     r9, [rcx+r8-30h]
0x140001850  and     r9, 0FFFFFFFFFFFFFFF0h
0x140001854  shr     r8, 6
0x140001858  movaps  xmmword ptr [rcx], xmm0
0x14000185b  movaps  xmmword ptr [rcx+10h], xmm0
0x14000185f  add     rcx, 40h ; '@'
0x140001863  dec     r8
0x140001866  movaps  xmmword ptr [rcx-20h], xmm0
0x14000186a  movaps  xmmword ptr [rcx-10h], xmm0
0x14000186e  jnz     short loc_140001858
0x140001870  movaps  xmmword ptr [r9], xmm0
0x140001874  movaps  xmmword ptr [r9+10h], xmm0
0x140001879  movaps  xmmword ptr [r9+20h], xmm0
0x14000187e  movups  xmmword ptr [rdx], xmm0
0x140001881  retn
0x140001890  cmp     r8, 10h
0x140001894  jb      short loc_1400018C0
0x140001896  lea     r9, [r8+rcx-10h]
0x14000189b  and     r8, 20h
0x14000189f  movups  xmmword ptr [rcx], xmm0
0x1400018a2  shr     r8, 1
0x1400018a5  movups  xmmword ptr [r9], xmm0
0x1400018a9  movups  xmmword ptr [rcx+r8], xmm0
0x1400018ae  neg     r8
0x1400018b1  movups  xmmword ptr [r9+r8], xmm0
0x1400018b6  retn
0x1400018c0  cmp     r8, 4
0x1400018c4  jb      short loc_1400018F0
0x1400018c6  lea     r9, [r8+rcx-4]
0x1400018cb  and     r8, 8
0x1400018cf  mov     [rcx], edx
0x1400018d1  shr     r8, 1
0x1400018d4  mov     [r9], edx
0x1400018d7  mov     [rcx+r8], edx
0x1400018db  neg     r8
0x1400018de  mov     [r9+r8], edx
0x1400018e2  retn
0x1400018f0  test    r8, r8
0x1400018f3  jz      short locret_140001906
0x1400018f5  mov     [rcx], dl
0x1400018f7  lea     r9, [rcx+r8-2]
0x1400018fc  cmp     r8, 1
0x140001900  jz      short locret_140001906
0x140001902  mov     [r9], dx
0x140001906  retn
```
