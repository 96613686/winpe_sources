# memmove

- ea: `0x14000c1c0`
- end: `0x14000c46a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a20`
- `0x140025610`

## callees

- `0x14000c1c0`

## pseudocode

```c
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  void *result; // rax
  __int64 v4; // r11
  __int64 v5; // rdx
  __int128 v6; // xmm1
  bool v7; // cf
  signed __int64 v8; // rdx
  char v9; // r11
  _BYTE *v10; // rcx
  char v11; // r11
  char *v12; // r11
  signed __int64 v13; // rdx
  __m128 v14; // xmm0
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  __m128 v17; // xmm1
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r9
  __int128 v20; // xmm1
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __m128 v23; // xmm4
  unsigned __int64 j; // r9
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  __m128 v27; // xmm1
  __m128 v28; // xmm2
  __m128 v29; // xmm3
  __m128 v30; // xmm4
  char *v31; // rcx
  __int128 v32; // xmm0
  unsigned __int64 v33; // rcx
  size_t v34; // r8
  _OWORD *v35; // r11
  __int128 v36; // xmm1
  size_t v37; // r9
  __int128 v38; // xmm1
  __int128 v39; // xmm2
  __int128 v40; // xmm3
  __int128 v41; // xmm4
  size_t i; // r9
  size_t v43; // r8

  result = a1;
  if ( Size < 8 )
  {
    if ( Size )
    {
      v7 = Src < a1;
      v8 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 )
      {
        v10 = (char *)a1 + Size;
        do
        {
          v11 = v10[v8 - 1];
          --v10;
          --Size;
          *v10 = v11;
        }
        while ( Size );
      }
      else
      {
        do
        {
          v9 = *((_BYTE *)a1 + v8);
          a1 = (char *)a1 + 1;
          --Size;
          *((char *)a1 - 1) = v9;
        }
        while ( Size );
      }
    }
  }
  else if ( Size > 0x10 )
  {
    if ( Size > 0x20 )
    {
      v12 = (char *)Src + Size;
      v7 = Src < a1;
      v13 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 && v12 > a1 )
      {
        v31 = (char *)a1 + Size;
        v32 = *(_OWORD *)&v31[v13 - 16];
        v33 = (unsigned __int64)(v31 - 16);
        v34 = Size - 16;
        if ( (v33 & 0xF) != 0 )
        {
          v35 = (_OWORD *)v33;
          v33 &= 0xFFFFFFFFFFFFFFF0uLL;
          v36 = *(_OWORD *)(v33 + v13);
          *v35 = v32;
          v32 = v36;
          v34 = v33 - (_QWORD)result;
        }
        v37 = v34 >> 6;
        if ( v34 >> 6 )
        {
          v34 &= 0x3Fu;
          do
          {
            v38 = *(_OWORD *)(v33 + v13 - 16);
            v39 = *(_OWORD *)(v33 + v13 - 32);
            v40 = *(_OWORD *)(v33 + v13 - 48);
            v41 = *(_OWORD *)(v33 + v13 - 64);
            *(_OWORD *)v33 = v32;
            v33 -= 64LL;
            --v37;
            *(_OWORD *)(v33 + 48) = v38;
            *(_OWORD *)(v33 + 32) = v39;
            *(_OWORD *)(v33 + 16) = v40;
            v32 = v41;
          }
          while ( v37 );
        }
        for ( i = v34 >> 4; i; --i )
        {
          *(_OWORD *)v33 = v32;
          v32 = *(_OWORD *)(v33 + v13 - 16);
          v33 -= 16LL;
        }
        v43 = v34 & 0xF;
        if ( v43 )
          *(_OWORD *)(v33 - v43) = *(_OWORD *)(v33 - v43 + v13);
        *(_OWORD *)v33 = v32;
      }
      else
      {
        v14 = *(__m128 *)((char *)a1 + v13);
        v15 = (unsigned __int64)a1 + 16;
        if ( (v15 & 0xF) != 0 )
        {
          v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
          v17 = *(__m128 *)(v16 + v13);
          *(__m128 *)result = v14;
          v14 = v17;
          v15 = v16 + 16;
        }
        v18 = (unsigned __int64)result + Size - v15;
        v19 = v18 >> 6;
        if ( v18 >> 6 )
        {
          if ( v19 > 0x1000 )
          {
            v26 = v18 >> 6;
            v18 &= 0x3Fu;
            _mm_prefetch((const char *)(v15 + v13 + 64), 0);
            do
            {
              v27 = *(__m128 *)(v15 + v13);
              v28 = *(__m128 *)(v15 + v13 + 16);
              v29 = *(__m128 *)(v15 + v13 + 32);
              v30 = *(__m128 *)(v15 + v13 + 48);
              _mm_stream_ps((float *)(v15 - 16), v14);
              v15 += 64LL;
              _mm_prefetch((const char *)(v15 + v13 + 64), 0);
              --v26;
              _mm_stream_ps((float *)(v15 - 64), v27);
              _mm_stream_ps((float *)(v15 - 48), v28);
              _mm_stream_ps((float *)(v15 - 32), v29);
              v14 = v30;
            }
            while ( v26 );
            _mm_sfence();
          }
          else
          {
            v18 &= 0x3Fu;
            do
            {
              v20 = *(_OWORD *)(v15 + v13);
              v21 = *(_OWORD *)(v15 + v13 + 16);
              v22 = *(_OWORD *)(v15 + v13 + 32);
              v23 = *(__m128 *)(v15 + v13 + 48);
              *(__m128 *)(v15 - 16) = v14;
              v15 += 64LL;
              --v19;
              *(_OWORD *)(v15 - 64) = v20;
              *(_OWORD *)(v15 - 48) = v21;
              *(_OWORD *)(v15 - 32) = v22;
              v14 = v23;
            }
            while ( v19 );
          }
        }
        for ( j = v18 >> 4; j; --j )
        {
          *(__m128 *)(v15 - 16) = v14;
          v14 = *(__m128 *)(v15 + v13);
          v15 += 16LL;
        }
        v25 = v18 & 0xF;
        if ( v25 )
          *(_OWORD *)(v15 + v25 - 16) = *(_OWORD *)(v15 + v25 - 16 + v13);
        *(__m128 *)(v15 - 16) = v14;
      }
    }
    else
    {
      v6 = *(_OWORD *)((char *)Src + Size - 16);
      *(_OWORD *)a1 = *(_OWORD *)Src;
      *(_OWORD *)((char *)a1 + Size - 16) = v6;
    }
  }
  else
  {
    v4 = *(_QWORD *)Src;
    v5 = *(_QWORD *)((char *)Src + Size - 8);
    *(_QWORD *)a1 = v4;
    *(_QWORD *)((char *)a1 + Size - 8) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000c1c0  mov     rax, rcx
0x14000c1c3  cmp     r8, 8
0x14000c1c7  jb      short loc_14000C200
0x14000c1c9  cmp     r8, 10h
0x14000c1cd  ja      short loc_14000C1E0
0x14000c1cf  mov     r11, [rdx]
0x14000c1d2  mov     rdx, [rdx+r8-8]
0x14000c1d7  mov     [rcx], r11
0x14000c1da  mov     [rcx+r8-8], rdx
0x14000c1df  retn
0x14000c1e0  cmp     r8, 20h ; ' '
0x14000c1e4  ja      short loc_14000C240
0x14000c1e6  movups  xmm0, xmmword ptr [rdx]
0x14000c1e9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14000c1ef  movups  xmmword ptr [rcx], xmm0
0x14000c1f2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14000c1f8  retn
0x14000c200  test    r8, r8
0x14000c203  jz      short locret_14000C21A
0x14000c205  sub     rdx, rcx
0x14000c208  jb      short loc_14000C220
0x14000c20a  mov     r11b, [rcx+rdx]
0x14000c20e  inc     rcx
0x14000c211  dec     r8
0x14000c214  mov     [rcx-1], r11b
0x14000c218  jnz     short loc_14000C20A
0x14000c21a  retn
0x14000c220  add     rcx, r8
0x14000c223  mov     r11b, [rcx+rdx-1]
0x14000c228  dec     rcx
0x14000c22b  dec     r8
0x14000c22e  mov     [rcx], r11b
0x14000c231  jnz     short loc_14000C223
0x14000c233  retn
0x14000c240  lea     r11, [rdx+r8]
0x14000c244  sub     rdx, rcx
0x14000c247  jnb     short loc_14000C252
0x14000c249  cmp     r11, rcx
0x14000c24c  ja      loc_14000C3C0
0x14000c252  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000c256  add     rcx, 10h
0x14000c25a  test    cl, 0Fh
0x14000c25d  jz      short loc_14000C271
0x14000c25f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000c263  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000c267  movups  xmmword ptr [rax], xmm0
0x14000c26a  movaps  xmm0, xmm1
0x14000c26d  add     rcx, 10h
0x14000c271  add     r8, rax
0x14000c274  sub     r8, rcx
0x14000c277  mov     r9, r8
0x14000c27a  shr     r9, 6
0x14000c27e  jz      short loc_14000C2EF
0x14000c280  cmp     r9, 1000h
0x14000c287  ja      loc_14000C340
0x14000c28d  and     r8, 3Fh
0x14000c291  jmp     short loc_14000C2C0
0x14000c2c0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000c2c4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000c2c9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000c2ce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000c2d3  movaps  xmmword ptr [rcx-10h], xmm0
0x14000c2d7  add     rcx, 40h ; '@'
0x14000c2db  dec     r9
0x14000c2de  movaps  xmmword ptr [rcx-40h], xmm1
0x14000c2e2  movaps  xmmword ptr [rcx-30h], xmm2
0x14000c2e6  movaps  xmmword ptr [rcx-20h], xmm3
0x14000c2ea  movaps  xmm0, xmm4
0x14000c2ed  jnz     short loc_14000C2C0
0x14000c2ef  mov     r9, r8
0x14000c2f2  shr     r9, 4
0x14000c2f6  jz      short loc_14000C311
0x14000c2f8  nop     dword ptr [rax+rax+00000000h]
0x14000c300  movaps  xmmword ptr [rcx-10h], xmm0
0x14000c304  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000c308  add     rcx, 10h
0x14000c30c  dec     r9
0x14000c30f  jnz     short loc_14000C300
0x14000c311  and     r8, 0Fh
0x14000c315  jz      short loc_14000C325
0x14000c317  lea     r11, [rcx+r8-10h]
0x14000c31c  movups  xmm1, xmmword ptr [r11+rdx]
0x14000c321  movups  xmmword ptr [r11], xmm1
0x14000c325  movaps  xmmword ptr [rcx-10h], xmm0
0x14000c329  retn
0x14000c340  mov     r9, r8
0x14000c343  shr     r9, 6
0x14000c347  and     r8, 3Fh
0x14000c34b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000c350  jmp     short loc_14000C380
0x14000c380  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000c384  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000c389  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000c38e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000c393  movntps xmmword ptr [rcx-10h], xmm0
0x14000c397  add     rcx, 40h ; '@'
0x14000c39b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000c3a0  dec     r9
0x14000c3a3  movntps xmmword ptr [rcx-40h], xmm1
0x14000c3a7  movntps xmmword ptr [rcx-30h], xmm2
0x14000c3ab  movntps xmmword ptr [rcx-20h], xmm3
0x14000c3af  movaps  xmm0, xmm4
0x14000c3b2  jnz     short loc_14000C380
0x14000c3b4  sfence
0x14000c3b7  jmp     loc_14000C2EF
0x14000c3c0  add     rcx, r8
0x14000c3c3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000c3c8  sub     rcx, 10h
0x14000c3cc  sub     r8, 10h
0x14000c3d0  test    cl, 0Fh
0x14000c3d3  jz      short loc_14000C3ED
0x14000c3d5  mov     r11, rcx
0x14000c3d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000c3dc  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000c3e0  movups  xmmword ptr [r11], xmm0
0x14000c3e4  movaps  xmm0, xmm1
0x14000c3e7  mov     r8, rcx
0x14000c3ea  sub     r8, rax
0x14000c3ed  mov     r9, r8
0x14000c3f0  shr     r9, 6
0x14000c3f4  jz      short loc_14000C42F
0x14000c3f6  and     r8, 3Fh
0x14000c3fa  jmp     short loc_14000C400
0x14000c400  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14000c405  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000c40a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000c40f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14000c414  movaps  xmmword ptr [rcx], xmm0
0x14000c417  sub     rcx, 40h ; '@'
0x14000c41b  dec     r9
0x14000c41e  movaps  xmmword ptr [rcx+30h], xmm1
0x14000c422  movaps  xmmword ptr [rcx+20h], xmm2
0x14000c426  movaps  xmmword ptr [rcx+10h], xmm3
0x14000c42a  movaps  xmm0, xmm4
0x14000c42d  jnz     short loc_14000C400
0x14000c42f  mov     r9, r8
0x14000c432  shr     r9, 4
0x14000c436  jz      short loc_14000C451
0x14000c438  nop     dword ptr [rax+rax+00000000h]
0x14000c440  movaps  xmmword ptr [rcx], xmm0
0x14000c443  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000c448  sub     rcx, 10h
0x14000c44c  dec     r9
0x14000c44f  jnz     short loc_14000C440
0x14000c451  and     r8, 0Fh
0x14000c455  jz      short loc_14000C466
0x14000c457  mov     r11, rcx
0x14000c45a  sub     r11, r8
0x14000c45d  movups  xmm1, xmmword ptr [r11+rdx]
0x14000c462  movups  xmmword ptr [r11], xmm1
0x14000c466  movaps  xmmword ptr [rcx], xmm0
0x14000c469  retn
```
