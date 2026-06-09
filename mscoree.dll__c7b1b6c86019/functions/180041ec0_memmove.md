# memmove

- ea: `0x180041ec0`
- end: `0x18004216a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x180002710`
- `0x180004660`
- `0x180008624`
- `0x18000b348`
- `0x18001181c`
- `0x1800121c0`
- `0x1800142c8`
- `0x180017db4`
- `0x18001def0`
- `0x18001e240`
- `0x18001f950`
- `0x1800262e0`
- `0x1800263f0`
- `0x180028d98`
- `0x180028f48`
- `0x18002a8b4`
- `0x18002b7b4`
- `0x18002b888`
- `0x18002bc3c`
- `0x18002c468`
- `0x18002c748`
- `0x18002d57c`
- `0x18002d800`
- `0x18002dccc`
- `0x18002e810`
- `0x180031a48`
- `0x180033a24`
- `0x1800341fc`
- `0x180035008`
- `0x1800353b4`
- `0x180035938`
- `0x180035f64`
- `0x18003852c`
- `0x1800386e0`
- `0x180038c18`
- `0x18003902c`
- `0x180039b1c`
- `0x180039b94`
- `0x18003a880`
- `0x18003ed54`

## callees

- `0x180041ec0`

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
0x180041ec0  mov     rax, rcx
0x180041ec3  cmp     r8, 8
0x180041ec7  jb      short loc_180041F00
0x180041ec9  cmp     r8, 10h
0x180041ecd  ja      short loc_180041EE0
0x180041ecf  mov     r11, [rdx]
0x180041ed2  mov     rdx, [rdx+r8-8]
0x180041ed7  mov     [rcx], r11
0x180041eda  mov     [rcx+r8-8], rdx
0x180041edf  retn
0x180041ee0  cmp     r8, 20h ; ' '
0x180041ee4  ja      short loc_180041F40
0x180041ee6  movups  xmm0, xmmword ptr [rdx]
0x180041ee9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x180041eef  movups  xmmword ptr [rcx], xmm0
0x180041ef2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x180041ef8  retn
0x180041f00  test    r8, r8
0x180041f03  jz      short locret_180041F1A
0x180041f05  sub     rdx, rcx
0x180041f08  jb      short loc_180041F20
0x180041f0a  mov     r11b, [rcx+rdx]
0x180041f0e  inc     rcx
0x180041f11  dec     r8
0x180041f14  mov     [rcx-1], r11b
0x180041f18  jnz     short loc_180041F0A
0x180041f1a  retn
0x180041f20  add     rcx, r8
0x180041f23  mov     r11b, [rcx+rdx-1]
0x180041f28  dec     rcx
0x180041f2b  dec     r8
0x180041f2e  mov     [rcx], r11b
0x180041f31  jnz     short loc_180041F23
0x180041f33  retn
0x180041f40  lea     r11, [rdx+r8]
0x180041f44  sub     rdx, rcx
0x180041f47  jnb     short loc_180041F52
0x180041f49  cmp     r11, rcx
0x180041f4c  ja      loc_1800420C0
0x180041f52  movups  xmm0, xmmword ptr [rcx+rdx]
0x180041f56  add     rcx, 10h
0x180041f5a  test    cl, 0Fh
0x180041f5d  jz      short loc_180041F71
0x180041f5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180041f63  movups  xmm1, xmmword ptr [rcx+rdx]
0x180041f67  movups  xmmword ptr [rax], xmm0
0x180041f6a  movaps  xmm0, xmm1
0x180041f6d  add     rcx, 10h
0x180041f71  add     r8, rax
0x180041f74  sub     r8, rcx
0x180041f77  mov     r9, r8
0x180041f7a  shr     r9, 6
0x180041f7e  jz      short loc_180041FEF
0x180041f80  cmp     r9, 1000h
0x180041f87  ja      loc_180042040
0x180041f8d  and     r8, 3Fh
0x180041f91  jmp     short loc_180041FC0
0x180041fc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x180041fc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x180041fc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x180041fce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x180041fd3  movaps  xmmword ptr [rcx-10h], xmm0
0x180041fd7  add     rcx, 40h ; '@'
0x180041fdb  dec     r9
0x180041fde  movaps  xmmword ptr [rcx-40h], xmm1
0x180041fe2  movaps  xmmword ptr [rcx-30h], xmm2
0x180041fe6  movaps  xmmword ptr [rcx-20h], xmm3
0x180041fea  movaps  xmm0, xmm4
0x180041fed  jnz     short loc_180041FC0
0x180041fef  mov     r9, r8
0x180041ff2  shr     r9, 4
0x180041ff6  jz      short loc_180042011
0x180041ff8  nop     dword ptr [rax+rax+00000000h]
0x180042000  movaps  xmmword ptr [rcx-10h], xmm0
0x180042004  movups  xmm0, xmmword ptr [rcx+rdx]
0x180042008  add     rcx, 10h
0x18004200c  dec     r9
0x18004200f  jnz     short loc_180042000
0x180042011  and     r8, 0Fh
0x180042015  jz      short loc_180042025
0x180042017  lea     r11, [rcx+r8-10h]
0x18004201c  movups  xmm1, xmmword ptr [r11+rdx]
0x180042021  movups  xmmword ptr [r11], xmm1
0x180042025  movaps  xmmword ptr [rcx-10h], xmm0
0x180042029  retn
0x180042040  mov     r9, r8
0x180042043  shr     r9, 6
0x180042047  and     r8, 3Fh
0x18004204b  prefetchnta byte ptr [rcx+rdx+40h]
0x180042050  jmp     short loc_180042080
0x180042080  movups  xmm1, xmmword ptr [rcx+rdx]
0x180042084  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x180042089  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x18004208e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x180042093  movntps xmmword ptr [rcx-10h], xmm0
0x180042097  add     rcx, 40h ; '@'
0x18004209b  prefetchnta byte ptr [rcx+rdx+40h]
0x1800420a0  dec     r9
0x1800420a3  movntps xmmword ptr [rcx-40h], xmm1
0x1800420a7  movntps xmmword ptr [rcx-30h], xmm2
0x1800420ab  movntps xmmword ptr [rcx-20h], xmm3
0x1800420af  movaps  xmm0, xmm4
0x1800420b2  jnz     short loc_180042080
0x1800420b4  sfence
0x1800420b7  jmp     loc_180041FEF
0x1800420c0  add     rcx, r8
0x1800420c3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x1800420c8  sub     rcx, 10h
0x1800420cc  sub     r8, 10h
0x1800420d0  test    cl, 0Fh
0x1800420d3  jz      short loc_1800420ED
0x1800420d5  mov     r11, rcx
0x1800420d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800420dc  movups  xmm1, xmmword ptr [rcx+rdx]
0x1800420e0  movups  xmmword ptr [r11], xmm0
0x1800420e4  movaps  xmm0, xmm1
0x1800420e7  mov     r8, rcx
0x1800420ea  sub     r8, rax
0x1800420ed  mov     r9, r8
0x1800420f0  shr     r9, 6
0x1800420f4  jz      short loc_18004212F
0x1800420f6  and     r8, 3Fh
0x1800420fa  jmp     short loc_180042100
0x180042100  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x180042105  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x18004210a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x18004210f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x180042114  movaps  xmmword ptr [rcx], xmm0
0x180042117  sub     rcx, 40h ; '@'
0x18004211b  dec     r9
0x18004211e  movaps  xmmword ptr [rcx+30h], xmm1
0x180042122  movaps  xmmword ptr [rcx+20h], xmm2
0x180042126  movaps  xmmword ptr [rcx+10h], xmm3
0x18004212a  movaps  xmm0, xmm4
0x18004212d  jnz     short loc_180042100
0x18004212f  mov     r9, r8
0x180042132  shr     r9, 4
0x180042136  jz      short loc_180042151
0x180042138  nop     dword ptr [rax+rax+00000000h]
0x180042140  movaps  xmmword ptr [rcx], xmm0
0x180042143  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x180042148  sub     rcx, 10h
0x18004214c  dec     r9
0x18004214f  jnz     short loc_180042140
0x180042151  and     r8, 0Fh
0x180042155  jz      short loc_180042166
0x180042157  mov     r11, rcx
0x18004215a  sub     r11, r8
0x18004215d  movups  xmm1, xmmword ptr [r11+rdx]
0x180042162  movups  xmmword ptr [r11], xmm1
0x180042166  movaps  xmmword ptr [rcx], xmm0
0x180042169  retn
```
