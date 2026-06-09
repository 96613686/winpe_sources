# memmove

- ea: `0x140004ec0`
- end: `0x14000516a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025c8`
- `0x14000b310`
- `0x14000d078`

## callees

- `0x140004ec0`

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
0x140004ec0  mov     rax, rcx
0x140004ec3  cmp     r8, 8
0x140004ec7  jb      short loc_140004F00
0x140004ec9  cmp     r8, 10h
0x140004ecd  ja      short loc_140004EE0
0x140004ecf  mov     r11, [rdx]
0x140004ed2  mov     rdx, [rdx+r8-8]
0x140004ed7  mov     [rcx], r11
0x140004eda  mov     [rcx+r8-8], rdx
0x140004edf  retn
0x140004ee0  cmp     r8, 20h ; ' '
0x140004ee4  ja      short loc_140004F40
0x140004ee6  movups  xmm0, xmmword ptr [rdx]
0x140004ee9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x140004eef  movups  xmmword ptr [rcx], xmm0
0x140004ef2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x140004ef8  retn
0x140004f00  test    r8, r8
0x140004f03  jz      short locret_140004F1A
0x140004f05  sub     rdx, rcx
0x140004f08  jb      short loc_140004F20
0x140004f0a  mov     r11b, [rcx+rdx]
0x140004f0e  inc     rcx
0x140004f11  dec     r8
0x140004f14  mov     [rcx-1], r11b
0x140004f18  jnz     short loc_140004F0A
0x140004f1a  retn
0x140004f20  add     rcx, r8
0x140004f23  mov     r11b, [rcx+rdx-1]
0x140004f28  dec     rcx
0x140004f2b  dec     r8
0x140004f2e  mov     [rcx], r11b
0x140004f31  jnz     short loc_140004F23
0x140004f33  retn
0x140004f40  lea     r11, [rdx+r8]
0x140004f44  sub     rdx, rcx
0x140004f47  jnb     short loc_140004F52
0x140004f49  cmp     r11, rcx
0x140004f4c  ja      loc_1400050C0
0x140004f52  movups  xmm0, xmmword ptr [rcx+rdx]
0x140004f56  add     rcx, 10h
0x140004f5a  test    cl, 0Fh
0x140004f5d  jz      short loc_140004F71
0x140004f5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140004f63  movups  xmm1, xmmword ptr [rcx+rdx]
0x140004f67  movups  xmmword ptr [rax], xmm0
0x140004f6a  movaps  xmm0, xmm1
0x140004f6d  add     rcx, 10h
0x140004f71  add     r8, rax
0x140004f74  sub     r8, rcx
0x140004f77  mov     r9, r8
0x140004f7a  shr     r9, 6
0x140004f7e  jz      short loc_140004FEF
0x140004f80  cmp     r9, 1000h
0x140004f87  ja      loc_140005040
0x140004f8d  and     r8, 3Fh
0x140004f91  jmp     short loc_140004FC0
0x140004fc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x140004fc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140004fc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x140004fce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140004fd3  movaps  xmmword ptr [rcx-10h], xmm0
0x140004fd7  add     rcx, 40h ; '@'
0x140004fdb  dec     r9
0x140004fde  movaps  xmmword ptr [rcx-40h], xmm1
0x140004fe2  movaps  xmmword ptr [rcx-30h], xmm2
0x140004fe6  movaps  xmmword ptr [rcx-20h], xmm3
0x140004fea  movaps  xmm0, xmm4
0x140004fed  jnz     short loc_140004FC0
0x140004fef  mov     r9, r8
0x140004ff2  shr     r9, 4
0x140004ff6  jz      short loc_140005011
0x140004ff8  nop     dword ptr [rax+rax+00000000h]
0x140005000  movaps  xmmword ptr [rcx-10h], xmm0
0x140005004  movups  xmm0, xmmword ptr [rcx+rdx]
0x140005008  add     rcx, 10h
0x14000500c  dec     r9
0x14000500f  jnz     short loc_140005000
0x140005011  and     r8, 0Fh
0x140005015  jz      short loc_140005025
0x140005017  lea     r11, [rcx+r8-10h]
0x14000501c  movups  xmm1, xmmword ptr [r11+rdx]
0x140005021  movups  xmmword ptr [r11], xmm1
0x140005025  movaps  xmmword ptr [rcx-10h], xmm0
0x140005029  retn
0x140005040  mov     r9, r8
0x140005043  shr     r9, 6
0x140005047  and     r8, 3Fh
0x14000504b  prefetchnta byte ptr [rcx+rdx+40h]
0x140005050  jmp     short loc_140005080
0x140005080  movups  xmm1, xmmword ptr [rcx+rdx]
0x140005084  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140005089  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000508e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140005093  movntps xmmword ptr [rcx-10h], xmm0
0x140005097  add     rcx, 40h ; '@'
0x14000509b  prefetchnta byte ptr [rcx+rdx+40h]
0x1400050a0  dec     r9
0x1400050a3  movntps xmmword ptr [rcx-40h], xmm1
0x1400050a7  movntps xmmword ptr [rcx-30h], xmm2
0x1400050ab  movntps xmmword ptr [rcx-20h], xmm3
0x1400050af  movaps  xmm0, xmm4
0x1400050b2  jnz     short loc_140005080
0x1400050b4  sfence
0x1400050b7  jmp     loc_140004FEF
0x1400050c0  add     rcx, r8
0x1400050c3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x1400050c8  sub     rcx, 10h
0x1400050cc  sub     r8, 10h
0x1400050d0  test    cl, 0Fh
0x1400050d3  jz      short loc_1400050ED
0x1400050d5  mov     r11, rcx
0x1400050d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400050dc  movups  xmm1, xmmword ptr [rcx+rdx]
0x1400050e0  movups  xmmword ptr [r11], xmm0
0x1400050e4  movaps  xmm0, xmm1
0x1400050e7  mov     r8, rcx
0x1400050ea  sub     r8, rax
0x1400050ed  mov     r9, r8
0x1400050f0  shr     r9, 6
0x1400050f4  jz      short loc_14000512F
0x1400050f6  and     r8, 3Fh
0x1400050fa  jmp     short loc_140005100
0x140005100  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x140005105  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000510a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000510f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x140005114  movaps  xmmword ptr [rcx], xmm0
0x140005117  sub     rcx, 40h ; '@'
0x14000511b  dec     r9
0x14000511e  movaps  xmmword ptr [rcx+30h], xmm1
0x140005122  movaps  xmmword ptr [rcx+20h], xmm2
0x140005126  movaps  xmmword ptr [rcx+10h], xmm3
0x14000512a  movaps  xmm0, xmm4
0x14000512d  jnz     short loc_140005100
0x14000512f  mov     r9, r8
0x140005132  shr     r9, 4
0x140005136  jz      short loc_140005151
0x140005138  nop     dword ptr [rax+rax+00000000h]
0x140005140  movaps  xmmword ptr [rcx], xmm0
0x140005143  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x140005148  sub     rcx, 10h
0x14000514c  dec     r9
0x14000514f  jnz     short loc_140005140
0x140005151  and     r8, 0Fh
0x140005155  jz      short loc_140005166
0x140005157  mov     r11, rcx
0x14000515a  sub     r11, r8
0x14000515d  movups  xmm1, xmmword ptr [r11+rdx]
0x140005162  movups  xmmword ptr [r11], xmm1
0x140005166  movaps  xmmword ptr [rcx], xmm0
0x140005169  retn
```
