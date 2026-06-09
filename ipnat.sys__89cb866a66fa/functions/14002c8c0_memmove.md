# memmove

- ea: `0x14002c8c0`
- end: `0x14002cb6a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027d0`
- `0x140005d10`
- `0x14000bed0`
- `0x14000cf88`
- `0x14001c45c`
- `0x1400423d0`
- `0x140042840`
- `0x140042f4c`
- `0x140043010`
- `0x140044310`

## callees

- `0x14002c8c0`

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
0x14002c8c0  mov     rax, rcx
0x14002c8c3  cmp     r8, 8
0x14002c8c7  jb      short loc_14002C900
0x14002c8c9  cmp     r8, 10h
0x14002c8cd  ja      short loc_14002C8E0
0x14002c8cf  mov     r11, [rdx]
0x14002c8d2  mov     rdx, [rdx+r8-8]
0x14002c8d7  mov     [rcx], r11
0x14002c8da  mov     [rcx+r8-8], rdx
0x14002c8df  retn
0x14002c8e0  cmp     r8, 20h ; ' '
0x14002c8e4  ja      short loc_14002C940
0x14002c8e6  movups  xmm0, xmmword ptr [rdx]
0x14002c8e9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14002c8ef  movups  xmmword ptr [rcx], xmm0
0x14002c8f2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14002c8f8  retn
0x14002c900  test    r8, r8
0x14002c903  jz      short locret_14002C91A
0x14002c905  sub     rdx, rcx
0x14002c908  jb      short loc_14002C920
0x14002c90a  mov     r11b, [rcx+rdx]
0x14002c90e  inc     rcx
0x14002c911  dec     r8
0x14002c914  mov     [rcx-1], r11b
0x14002c918  jnz     short loc_14002C90A
0x14002c91a  retn
0x14002c920  add     rcx, r8
0x14002c923  mov     r11b, [rcx+rdx-1]
0x14002c928  dec     rcx
0x14002c92b  dec     r8
0x14002c92e  mov     [rcx], r11b
0x14002c931  jnz     short loc_14002C923
0x14002c933  retn
0x14002c940  lea     r11, [rdx+r8]
0x14002c944  sub     rdx, rcx
0x14002c947  jnb     short loc_14002C952
0x14002c949  cmp     r11, rcx
0x14002c94c  ja      loc_14002CAC0
0x14002c952  movups  xmm0, xmmword ptr [rcx+rdx]
0x14002c956  add     rcx, 10h
0x14002c95a  test    cl, 0Fh
0x14002c95d  jz      short loc_14002C971
0x14002c95f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14002c963  movups  xmm1, xmmword ptr [rcx+rdx]
0x14002c967  movups  xmmword ptr [rax], xmm0
0x14002c96a  movaps  xmm0, xmm1
0x14002c96d  add     rcx, 10h
0x14002c971  add     r8, rax
0x14002c974  sub     r8, rcx
0x14002c977  mov     r9, r8
0x14002c97a  shr     r9, 6
0x14002c97e  jz      short loc_14002C9EF
0x14002c980  cmp     r9, 1000h
0x14002c987  ja      loc_14002CA40
0x14002c98d  and     r8, 3Fh
0x14002c991  jmp     short loc_14002C9C0
0x14002c9c0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14002c9c4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14002c9c9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14002c9ce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14002c9d3  movaps  xmmword ptr [rcx-10h], xmm0
0x14002c9d7  add     rcx, 40h ; '@'
0x14002c9db  dec     r9
0x14002c9de  movaps  xmmword ptr [rcx-40h], xmm1
0x14002c9e2  movaps  xmmword ptr [rcx-30h], xmm2
0x14002c9e6  movaps  xmmword ptr [rcx-20h], xmm3
0x14002c9ea  movaps  xmm0, xmm4
0x14002c9ed  jnz     short loc_14002C9C0
0x14002c9ef  mov     r9, r8
0x14002c9f2  shr     r9, 4
0x14002c9f6  jz      short loc_14002CA11
0x14002c9f8  nop     dword ptr [rax+rax+00000000h]
0x14002ca00  movaps  xmmword ptr [rcx-10h], xmm0
0x14002ca04  movups  xmm0, xmmword ptr [rcx+rdx]
0x14002ca08  add     rcx, 10h
0x14002ca0c  dec     r9
0x14002ca0f  jnz     short loc_14002CA00
0x14002ca11  and     r8, 0Fh
0x14002ca15  jz      short loc_14002CA25
0x14002ca17  lea     r11, [rcx+r8-10h]
0x14002ca1c  movups  xmm1, xmmword ptr [r11+rdx]
0x14002ca21  movups  xmmword ptr [r11], xmm1
0x14002ca25  movaps  xmmword ptr [rcx-10h], xmm0
0x14002ca29  retn
0x14002ca40  mov     r9, r8
0x14002ca43  shr     r9, 6
0x14002ca47  and     r8, 3Fh
0x14002ca4b  prefetchnta byte ptr [rcx+rdx+40h]
0x14002ca50  jmp     short loc_14002CA80
0x14002ca80  movups  xmm1, xmmword ptr [rcx+rdx]
0x14002ca84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14002ca89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14002ca8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14002ca93  movntps xmmword ptr [rcx-10h], xmm0
0x14002ca97  add     rcx, 40h ; '@'
0x14002ca9b  prefetchnta byte ptr [rcx+rdx+40h]
0x14002caa0  dec     r9
0x14002caa3  movntps xmmword ptr [rcx-40h], xmm1
0x14002caa7  movntps xmmword ptr [rcx-30h], xmm2
0x14002caab  movntps xmmword ptr [rcx-20h], xmm3
0x14002caaf  movaps  xmm0, xmm4
0x14002cab2  jnz     short loc_14002CA80
0x14002cab4  sfence
0x14002cab7  jmp     loc_14002C9EF
0x14002cac0  add     rcx, r8
0x14002cac3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14002cac8  sub     rcx, 10h
0x14002cacc  sub     r8, 10h
0x14002cad0  test    cl, 0Fh
0x14002cad3  jz      short loc_14002CAED
0x14002cad5  mov     r11, rcx
0x14002cad8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14002cadc  movups  xmm1, xmmword ptr [rcx+rdx]
0x14002cae0  movups  xmmword ptr [r11], xmm0
0x14002cae4  movaps  xmm0, xmm1
0x14002cae7  mov     r8, rcx
0x14002caea  sub     r8, rax
0x14002caed  mov     r9, r8
0x14002caf0  shr     r9, 6
0x14002caf4  jz      short loc_14002CB2F
0x14002caf6  and     r8, 3Fh
0x14002cafa  jmp     short loc_14002CB00
0x14002cb00  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14002cb05  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14002cb0a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14002cb0f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14002cb14  movaps  xmmword ptr [rcx], xmm0
0x14002cb17  sub     rcx, 40h ; '@'
0x14002cb1b  dec     r9
0x14002cb1e  movaps  xmmword ptr [rcx+30h], xmm1
0x14002cb22  movaps  xmmword ptr [rcx+20h], xmm2
0x14002cb26  movaps  xmmword ptr [rcx+10h], xmm3
0x14002cb2a  movaps  xmm0, xmm4
0x14002cb2d  jnz     short loc_14002CB00
0x14002cb2f  mov     r9, r8
0x14002cb32  shr     r9, 4
0x14002cb36  jz      short loc_14002CB51
0x14002cb38  nop     dword ptr [rax+rax+00000000h]
0x14002cb40  movaps  xmmword ptr [rcx], xmm0
0x14002cb43  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14002cb48  sub     rcx, 10h
0x14002cb4c  dec     r9
0x14002cb4f  jnz     short loc_14002CB40
0x14002cb51  and     r8, 0Fh
0x14002cb55  jz      short loc_14002CB66
0x14002cb57  mov     r11, rcx
0x14002cb5a  sub     r11, r8
0x14002cb5d  movups  xmm1, xmmword ptr [r11+rdx]
0x14002cb62  movups  xmmword ptr [r11], xmm1
0x14002cb66  movaps  xmmword ptr [rcx], xmm0
0x14002cb69  retn
```
