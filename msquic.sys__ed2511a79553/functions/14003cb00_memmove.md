# memmove

- ea: `0x14003cb00`
- end: `0x14003cdaa`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `71`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001b00`
- `0x140001d6c`
- `0x140002840`
- `0x1400033e0`
- `0x140003edc`
- `0x140004e2c`
- `0x14000524c`
- `0x14000577c`
- `0x140007b30`
- `0x140008944`
- `0x14000a120`
- `0x14000db70`
- `0x1400123c0`
- `0x140015480`
- `0x140015b70`
- `0x140016e30`
- `0x1400188f0`
- `0x140019040`
- `0x140019ecc`
- `0x14001b3c0`
- `0x14001bd68`
- `0x14001be88`
- `0x14001c294`
- `0x14001c664`
- `0x14001f464`
- `0x140021898`
- `0x140021b60`
- `0x140021e20`
- `0x140021fb0`
- `0x140022c28`
- `0x140022d10`
- `0x140023724`
- `0x1400258c0`
- `0x14002636c`
- `0x140026f1c`
- `0x140028ce4`
- `0x14002a180`
- `0x14002c014`
- `0x14002c9d0`
- `0x14002ea74`
- `0x14002eb78`
- `0x14002f3c4`
- `0x14002fbf8`
- `0x14002fdc4`
- `0x140030388`
- `0x140033e30`
- `0x140035480`
- `0x140035a24`
- `0x140035c4c`

## callees

- `0x14003cb00`

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
0x14003cb00  mov     rax, rcx
0x14003cb03  cmp     r8, 8
0x14003cb07  jb      short loc_14003CB40
0x14003cb09  cmp     r8, 10h
0x14003cb0d  ja      short loc_14003CB20
0x14003cb0f  mov     r11, [rdx]
0x14003cb12  mov     rdx, [rdx+r8-8]
0x14003cb17  mov     [rcx], r11
0x14003cb1a  mov     [rcx+r8-8], rdx
0x14003cb1f  retn
0x14003cb20  cmp     r8, 20h ; ' '
0x14003cb24  ja      short loc_14003CB80
0x14003cb26  movups  xmm0, xmmword ptr [rdx]
0x14003cb29  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14003cb2f  movups  xmmword ptr [rcx], xmm0
0x14003cb32  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14003cb38  retn
0x14003cb40  test    r8, r8
0x14003cb43  jz      short locret_14003CB5A
0x14003cb45  sub     rdx, rcx
0x14003cb48  jb      short loc_14003CB60
0x14003cb4a  mov     r11b, [rcx+rdx]
0x14003cb4e  inc     rcx
0x14003cb51  dec     r8
0x14003cb54  mov     [rcx-1], r11b
0x14003cb58  jnz     short loc_14003CB4A
0x14003cb5a  retn
0x14003cb60  add     rcx, r8
0x14003cb63  mov     r11b, [rcx+rdx-1]
0x14003cb68  dec     rcx
0x14003cb6b  dec     r8
0x14003cb6e  mov     [rcx], r11b
0x14003cb71  jnz     short loc_14003CB63
0x14003cb73  retn
0x14003cb80  lea     r11, [rdx+r8]
0x14003cb84  sub     rdx, rcx
0x14003cb87  jnb     short loc_14003CB92
0x14003cb89  cmp     r11, rcx
0x14003cb8c  ja      loc_14003CD00
0x14003cb92  movups  xmm0, xmmword ptr [rcx+rdx]
0x14003cb96  add     rcx, 10h
0x14003cb9a  test    cl, 0Fh
0x14003cb9d  jz      short loc_14003CBB1
0x14003cb9f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14003cba3  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003cba7  movups  xmmword ptr [rax], xmm0
0x14003cbaa  movaps  xmm0, xmm1
0x14003cbad  add     rcx, 10h
0x14003cbb1  add     r8, rax
0x14003cbb4  sub     r8, rcx
0x14003cbb7  mov     r9, r8
0x14003cbba  shr     r9, 6
0x14003cbbe  jz      short loc_14003CC2F
0x14003cbc0  cmp     r9, 1000h
0x14003cbc7  ja      loc_14003CC80
0x14003cbcd  and     r8, 3Fh
0x14003cbd1  jmp     short loc_14003CC00
0x14003cc00  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003cc04  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14003cc09  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14003cc0e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14003cc13  movaps  xmmword ptr [rcx-10h], xmm0
0x14003cc17  add     rcx, 40h ; '@'
0x14003cc1b  dec     r9
0x14003cc1e  movaps  xmmword ptr [rcx-40h], xmm1
0x14003cc22  movaps  xmmword ptr [rcx-30h], xmm2
0x14003cc26  movaps  xmmword ptr [rcx-20h], xmm3
0x14003cc2a  movaps  xmm0, xmm4
0x14003cc2d  jnz     short loc_14003CC00
0x14003cc2f  mov     r9, r8
0x14003cc32  shr     r9, 4
0x14003cc36  jz      short loc_14003CC51
0x14003cc38  nop     dword ptr [rax+rax+00000000h]
0x14003cc40  movaps  xmmword ptr [rcx-10h], xmm0
0x14003cc44  movups  xmm0, xmmword ptr [rcx+rdx]
0x14003cc48  add     rcx, 10h
0x14003cc4c  dec     r9
0x14003cc4f  jnz     short loc_14003CC40
0x14003cc51  and     r8, 0Fh
0x14003cc55  jz      short loc_14003CC65
0x14003cc57  lea     r11, [rcx+r8-10h]
0x14003cc5c  movups  xmm1, xmmword ptr [r11+rdx]
0x14003cc61  movups  xmmword ptr [r11], xmm1
0x14003cc65  movaps  xmmword ptr [rcx-10h], xmm0
0x14003cc69  retn
0x14003cc80  mov     r9, r8
0x14003cc83  shr     r9, 6
0x14003cc87  and     r8, 3Fh
0x14003cc8b  prefetchnta byte ptr [rcx+rdx+40h]
0x14003cc90  jmp     short loc_14003CCC0
0x14003ccc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003ccc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14003ccc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14003ccce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14003ccd3  movntps xmmword ptr [rcx-10h], xmm0
0x14003ccd7  add     rcx, 40h ; '@'
0x14003ccdb  prefetchnta byte ptr [rcx+rdx+40h]
0x14003cce0  dec     r9
0x14003cce3  movntps xmmword ptr [rcx-40h], xmm1
0x14003cce7  movntps xmmword ptr [rcx-30h], xmm2
0x14003cceb  movntps xmmword ptr [rcx-20h], xmm3
0x14003ccef  movaps  xmm0, xmm4
0x14003ccf2  jnz     short loc_14003CCC0
0x14003ccf4  sfence
0x14003ccf7  jmp     loc_14003CC2F
0x14003cd00  add     rcx, r8
0x14003cd03  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14003cd08  sub     rcx, 10h
0x14003cd0c  sub     r8, 10h
0x14003cd10  test    cl, 0Fh
0x14003cd13  jz      short loc_14003CD2D
0x14003cd15  mov     r11, rcx
0x14003cd18  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14003cd1c  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003cd20  movups  xmmword ptr [r11], xmm0
0x14003cd24  movaps  xmm0, xmm1
0x14003cd27  mov     r8, rcx
0x14003cd2a  sub     r8, rax
0x14003cd2d  mov     r9, r8
0x14003cd30  shr     r9, 6
0x14003cd34  jz      short loc_14003CD6F
0x14003cd36  and     r8, 3Fh
0x14003cd3a  jmp     short loc_14003CD40
0x14003cd40  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14003cd45  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14003cd4a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14003cd4f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14003cd54  movaps  xmmword ptr [rcx], xmm0
0x14003cd57  sub     rcx, 40h ; '@'
0x14003cd5b  dec     r9
0x14003cd5e  movaps  xmmword ptr [rcx+30h], xmm1
0x14003cd62  movaps  xmmword ptr [rcx+20h], xmm2
0x14003cd66  movaps  xmmword ptr [rcx+10h], xmm3
0x14003cd6a  movaps  xmm0, xmm4
0x14003cd6d  jnz     short loc_14003CD40
0x14003cd6f  mov     r9, r8
0x14003cd72  shr     r9, 4
0x14003cd76  jz      short loc_14003CD91
0x14003cd78  nop     dword ptr [rax+rax+00000000h]
0x14003cd80  movaps  xmmword ptr [rcx], xmm0
0x14003cd83  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14003cd88  sub     rcx, 10h
0x14003cd8c  dec     r9
0x14003cd8f  jnz     short loc_14003CD80
0x14003cd91  and     r8, 0Fh
0x14003cd95  jz      short loc_14003CDA6
0x14003cd97  mov     r11, rcx
0x14003cd9a  sub     r11, r8
0x14003cd9d  movups  xmm1, xmmword ptr [r11+rdx]
0x14003cda2  movups  xmmword ptr [r11], xmm1
0x14003cda6  movaps  xmmword ptr [rcx], xmm0
0x14003cda9  retn
```
