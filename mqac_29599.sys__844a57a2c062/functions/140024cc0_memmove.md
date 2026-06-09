# memmove

- ea: `0x140024cc0`
- end: `0x140024f6a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1400095e0`
- `0x14000c388`
- `0x14000e488`
- `0x14000e5f4`
- `0x14000e710`
- `0x14000e834`
- `0x140011300`
- `0x140012838`
- `0x14001288c`
- `0x140012dc4`
- `0x140014980`
- `0x140015e04`
- `0x140019020`
- `0x14001bd4c`
- `0x14002186c`
- `0x14002f270`

## callees

- `0x140024cc0`

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
0x140024cc0  mov     rax, rcx
0x140024cc3  cmp     r8, 8
0x140024cc7  jb      short loc_140024D00
0x140024cc9  cmp     r8, 10h
0x140024ccd  ja      short loc_140024CE0
0x140024ccf  mov     r11, [rdx]
0x140024cd2  mov     rdx, [rdx+r8-8]
0x140024cd7  mov     [rcx], r11
0x140024cda  mov     [rcx+r8-8], rdx
0x140024cdf  retn
0x140024ce0  cmp     r8, 20h ; ' '
0x140024ce4  ja      short loc_140024D40
0x140024ce6  movups  xmm0, xmmword ptr [rdx]
0x140024ce9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x140024cef  movups  xmmword ptr [rcx], xmm0
0x140024cf2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x140024cf8  retn
0x140024d00  test    r8, r8
0x140024d03  jz      short locret_140024D1A
0x140024d05  sub     rdx, rcx
0x140024d08  jb      short loc_140024D20
0x140024d0a  mov     r11b, [rcx+rdx]
0x140024d0e  inc     rcx
0x140024d11  dec     r8
0x140024d14  mov     [rcx-1], r11b
0x140024d18  jnz     short loc_140024D0A
0x140024d1a  retn
0x140024d20  add     rcx, r8
0x140024d23  mov     r11b, [rcx+rdx-1]
0x140024d28  dec     rcx
0x140024d2b  dec     r8
0x140024d2e  mov     [rcx], r11b
0x140024d31  jnz     short loc_140024D23
0x140024d33  retn
0x140024d40  lea     r11, [rdx+r8]
0x140024d44  sub     rdx, rcx
0x140024d47  jnb     short loc_140024D52
0x140024d49  cmp     r11, rcx
0x140024d4c  ja      loc_140024EC0
0x140024d52  movups  xmm0, xmmword ptr [rcx+rdx]
0x140024d56  add     rcx, 10h
0x140024d5a  test    cl, 0Fh
0x140024d5d  jz      short loc_140024D71
0x140024d5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140024d63  movups  xmm1, xmmword ptr [rcx+rdx]
0x140024d67  movups  xmmword ptr [rax], xmm0
0x140024d6a  movaps  xmm0, xmm1
0x140024d6d  add     rcx, 10h
0x140024d71  add     r8, rax
0x140024d74  sub     r8, rcx
0x140024d77  mov     r9, r8
0x140024d7a  shr     r9, 6
0x140024d7e  jz      short loc_140024DEF
0x140024d80  cmp     r9, 1000h
0x140024d87  ja      loc_140024E40
0x140024d8d  and     r8, 3Fh
0x140024d91  jmp     short loc_140024DC0
0x140024dc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x140024dc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140024dc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x140024dce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140024dd3  movaps  xmmword ptr [rcx-10h], xmm0
0x140024dd7  add     rcx, 40h ; '@'
0x140024ddb  dec     r9
0x140024dde  movaps  xmmword ptr [rcx-40h], xmm1
0x140024de2  movaps  xmmword ptr [rcx-30h], xmm2
0x140024de6  movaps  xmmword ptr [rcx-20h], xmm3
0x140024dea  movaps  xmm0, xmm4
0x140024ded  jnz     short loc_140024DC0
0x140024def  mov     r9, r8
0x140024df2  shr     r9, 4
0x140024df6  jz      short loc_140024E11
0x140024df8  nop     dword ptr [rax+rax+00000000h]
0x140024e00  movaps  xmmword ptr [rcx-10h], xmm0
0x140024e04  movups  xmm0, xmmword ptr [rcx+rdx]
0x140024e08  add     rcx, 10h
0x140024e0c  dec     r9
0x140024e0f  jnz     short loc_140024E00
0x140024e11  and     r8, 0Fh
0x140024e15  jz      short loc_140024E25
0x140024e17  lea     r11, [rcx+r8-10h]
0x140024e1c  movups  xmm1, xmmword ptr [r11+rdx]
0x140024e21  movups  xmmword ptr [r11], xmm1
0x140024e25  movaps  xmmword ptr [rcx-10h], xmm0
0x140024e29  retn
0x140024e40  mov     r9, r8
0x140024e43  shr     r9, 6
0x140024e47  and     r8, 3Fh
0x140024e4b  prefetchnta byte ptr [rcx+rdx+40h]
0x140024e50  jmp     short loc_140024E80
0x140024e80  movups  xmm1, xmmword ptr [rcx+rdx]
0x140024e84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140024e89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x140024e8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140024e93  movntps xmmword ptr [rcx-10h], xmm0
0x140024e97  add     rcx, 40h ; '@'
0x140024e9b  prefetchnta byte ptr [rcx+rdx+40h]
0x140024ea0  dec     r9
0x140024ea3  movntps xmmword ptr [rcx-40h], xmm1
0x140024ea7  movntps xmmword ptr [rcx-30h], xmm2
0x140024eab  movntps xmmword ptr [rcx-20h], xmm3
0x140024eaf  movaps  xmm0, xmm4
0x140024eb2  jnz     short loc_140024E80
0x140024eb4  sfence
0x140024eb7  jmp     loc_140024DEF
0x140024ec0  add     rcx, r8
0x140024ec3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x140024ec8  sub     rcx, 10h
0x140024ecc  sub     r8, 10h
0x140024ed0  test    cl, 0Fh
0x140024ed3  jz      short loc_140024EED
0x140024ed5  mov     r11, rcx
0x140024ed8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140024edc  movups  xmm1, xmmword ptr [rcx+rdx]
0x140024ee0  movups  xmmword ptr [r11], xmm0
0x140024ee4  movaps  xmm0, xmm1
0x140024ee7  mov     r8, rcx
0x140024eea  sub     r8, rax
0x140024eed  mov     r9, r8
0x140024ef0  shr     r9, 6
0x140024ef4  jz      short loc_140024F2F
0x140024ef6  and     r8, 3Fh
0x140024efa  jmp     short loc_140024F00
0x140024f00  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x140024f05  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x140024f0a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x140024f0f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x140024f14  movaps  xmmword ptr [rcx], xmm0
0x140024f17  sub     rcx, 40h ; '@'
0x140024f1b  dec     r9
0x140024f1e  movaps  xmmword ptr [rcx+30h], xmm1
0x140024f22  movaps  xmmword ptr [rcx+20h], xmm2
0x140024f26  movaps  xmmword ptr [rcx+10h], xmm3
0x140024f2a  movaps  xmm0, xmm4
0x140024f2d  jnz     short loc_140024F00
0x140024f2f  mov     r9, r8
0x140024f32  shr     r9, 4
0x140024f36  jz      short loc_140024F51
0x140024f38  nop     dword ptr [rax+rax+00000000h]
0x140024f40  movaps  xmmword ptr [rcx], xmm0
0x140024f43  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x140024f48  sub     rcx, 10h
0x140024f4c  dec     r9
0x140024f4f  jnz     short loc_140024F40
0x140024f51  and     r8, 0Fh
0x140024f55  jz      short loc_140024F66
0x140024f57  mov     r11, rcx
0x140024f5a  sub     r11, r8
0x140024f5d  movups  xmm1, xmmword ptr [r11+rdx]
0x140024f62  movups  xmmword ptr [r11], xmm1
0x140024f66  movaps  xmmword ptr [rcx], xmm0
0x140024f69  retn
```
