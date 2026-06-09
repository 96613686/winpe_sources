# memmove

- ea: `0x14000bb80`
- end: `0x14000be2a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x140001658`
- `0x14000420c`
- `0x14000500c`
- `0x140005c68`
- `0x140006ca0`
- `0x1400083b0`
- `0x14000a69c`
- `0x14000b0d8`
- `0x14000ba50`
- `0x14000ba60`
- `0x140024b24`
- `0x14002d668`
- `0x140031a00`
- `0x140032fd8`
- `0x140033878`
- `0x1400346f0`
- `0x140037ac0`
- `0x140038b78`
- `0x140038f1c`
- `0x14003b380`
- `0x14003b724`
- `0x14003f240`
- `0x140044508`
- `0x140045c88`
- `0x140045d4c`

## callees

- `0x14000bb80`

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
0x14000bb80  mov     rax, rcx
0x14000bb83  cmp     r8, 8
0x14000bb87  jb      short loc_14000BBC0
0x14000bb89  cmp     r8, 10h
0x14000bb8d  ja      short loc_14000BBA0
0x14000bb8f  mov     r11, [rdx]
0x14000bb92  mov     rdx, [rdx+r8-8]
0x14000bb97  mov     [rcx], r11
0x14000bb9a  mov     [rcx+r8-8], rdx
0x14000bb9f  retn
0x14000bba0  cmp     r8, 20h ; ' '
0x14000bba4  ja      short loc_14000BC00
0x14000bba6  movups  xmm0, xmmword ptr [rdx]
0x14000bba9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14000bbaf  movups  xmmword ptr [rcx], xmm0
0x14000bbb2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14000bbb8  retn
0x14000bbc0  test    r8, r8
0x14000bbc3  jz      short locret_14000BBDA
0x14000bbc5  sub     rdx, rcx
0x14000bbc8  jb      short loc_14000BBE0
0x14000bbca  mov     r11b, [rcx+rdx]
0x14000bbce  inc     rcx
0x14000bbd1  dec     r8
0x14000bbd4  mov     [rcx-1], r11b
0x14000bbd8  jnz     short loc_14000BBCA
0x14000bbda  retn
0x14000bbe0  add     rcx, r8
0x14000bbe3  mov     r11b, [rcx+rdx-1]
0x14000bbe8  dec     rcx
0x14000bbeb  dec     r8
0x14000bbee  mov     [rcx], r11b
0x14000bbf1  jnz     short loc_14000BBE3
0x14000bbf3  retn
0x14000bc00  lea     r11, [rdx+r8]
0x14000bc04  sub     rdx, rcx
0x14000bc07  jnb     short loc_14000BC12
0x14000bc09  cmp     r11, rcx
0x14000bc0c  ja      loc_14000BD80
0x14000bc12  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000bc16  add     rcx, 10h
0x14000bc1a  test    cl, 0Fh
0x14000bc1d  jz      short loc_14000BC31
0x14000bc1f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000bc23  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000bc27  movups  xmmword ptr [rax], xmm0
0x14000bc2a  movaps  xmm0, xmm1
0x14000bc2d  add     rcx, 10h
0x14000bc31  add     r8, rax
0x14000bc34  sub     r8, rcx
0x14000bc37  mov     r9, r8
0x14000bc3a  shr     r9, 6
0x14000bc3e  jz      short loc_14000BCAF
0x14000bc40  cmp     r9, 1000h
0x14000bc47  ja      loc_14000BD00
0x14000bc4d  and     r8, 3Fh
0x14000bc51  jmp     short loc_14000BC80
0x14000bc80  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000bc84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000bc89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000bc8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000bc93  movaps  xmmword ptr [rcx-10h], xmm0
0x14000bc97  add     rcx, 40h ; '@'
0x14000bc9b  dec     r9
0x14000bc9e  movaps  xmmword ptr [rcx-40h], xmm1
0x14000bca2  movaps  xmmword ptr [rcx-30h], xmm2
0x14000bca6  movaps  xmmword ptr [rcx-20h], xmm3
0x14000bcaa  movaps  xmm0, xmm4
0x14000bcad  jnz     short loc_14000BC80
0x14000bcaf  mov     r9, r8
0x14000bcb2  shr     r9, 4
0x14000bcb6  jz      short loc_14000BCD1
0x14000bcb8  nop     dword ptr [rax+rax+00000000h]
0x14000bcc0  movaps  xmmword ptr [rcx-10h], xmm0
0x14000bcc4  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000bcc8  add     rcx, 10h
0x14000bccc  dec     r9
0x14000bccf  jnz     short loc_14000BCC0
0x14000bcd1  and     r8, 0Fh
0x14000bcd5  jz      short loc_14000BCE5
0x14000bcd7  lea     r11, [rcx+r8-10h]
0x14000bcdc  movups  xmm1, xmmword ptr [r11+rdx]
0x14000bce1  movups  xmmword ptr [r11], xmm1
0x14000bce5  movaps  xmmword ptr [rcx-10h], xmm0
0x14000bce9  retn
0x14000bd00  mov     r9, r8
0x14000bd03  shr     r9, 6
0x14000bd07  and     r8, 3Fh
0x14000bd0b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000bd10  jmp     short loc_14000BD40
0x14000bd40  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000bd44  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000bd49  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000bd4e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000bd53  movntps xmmword ptr [rcx-10h], xmm0
0x14000bd57  add     rcx, 40h ; '@'
0x14000bd5b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000bd60  dec     r9
0x14000bd63  movntps xmmword ptr [rcx-40h], xmm1
0x14000bd67  movntps xmmword ptr [rcx-30h], xmm2
0x14000bd6b  movntps xmmword ptr [rcx-20h], xmm3
0x14000bd6f  movaps  xmm0, xmm4
0x14000bd72  jnz     short loc_14000BD40
0x14000bd74  sfence
0x14000bd77  jmp     loc_14000BCAF
0x14000bd80  add     rcx, r8
0x14000bd83  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000bd88  sub     rcx, 10h
0x14000bd8c  sub     r8, 10h
0x14000bd90  test    cl, 0Fh
0x14000bd93  jz      short loc_14000BDAD
0x14000bd95  mov     r11, rcx
0x14000bd98  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000bd9c  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000bda0  movups  xmmword ptr [r11], xmm0
0x14000bda4  movaps  xmm0, xmm1
0x14000bda7  mov     r8, rcx
0x14000bdaa  sub     r8, rax
0x14000bdad  mov     r9, r8
0x14000bdb0  shr     r9, 6
0x14000bdb4  jz      short loc_14000BDEF
0x14000bdb6  and     r8, 3Fh
0x14000bdba  jmp     short loc_14000BDC0
0x14000bdc0  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14000bdc5  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000bdca  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000bdcf  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14000bdd4  movaps  xmmword ptr [rcx], xmm0
0x14000bdd7  sub     rcx, 40h ; '@'
0x14000bddb  dec     r9
0x14000bdde  movaps  xmmword ptr [rcx+30h], xmm1
0x14000bde2  movaps  xmmword ptr [rcx+20h], xmm2
0x14000bde6  movaps  xmmword ptr [rcx+10h], xmm3
0x14000bdea  movaps  xmm0, xmm4
0x14000bded  jnz     short loc_14000BDC0
0x14000bdef  mov     r9, r8
0x14000bdf2  shr     r9, 4
0x14000bdf6  jz      short loc_14000BE11
0x14000bdf8  nop     dword ptr [rax+rax+00000000h]
0x14000be00  movaps  xmmword ptr [rcx], xmm0
0x14000be03  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000be08  sub     rcx, 10h
0x14000be0c  dec     r9
0x14000be0f  jnz     short loc_14000BE00
0x14000be11  and     r8, 0Fh
0x14000be15  jz      short loc_14000BE26
0x14000be17  mov     r11, rcx
0x14000be1a  sub     r11, r8
0x14000be1d  movups  xmm1, xmmword ptr [r11+rdx]
0x14000be22  movups  xmmword ptr [r11], xmm1
0x14000be26  movaps  xmmword ptr [rcx], xmm0
0x14000be29  retn
```
