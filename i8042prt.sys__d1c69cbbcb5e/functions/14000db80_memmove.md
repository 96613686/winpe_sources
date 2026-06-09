# memmove

- ea: `0x14000db80`
- end: `0x14000de2a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140007090`
- `0x140007c20`
- `0x1400178b0`
- `0x14001b830`
- `0x14001c808`
- `0x140021078`

## callees

- `0x14000db80`

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
0x14000db80  mov     rax, rcx
0x14000db83  cmp     r8, 8
0x14000db87  jb      short loc_14000DBC0
0x14000db89  cmp     r8, 10h
0x14000db8d  ja      short loc_14000DBA0
0x14000db8f  mov     r11, [rdx]
0x14000db92  mov     rdx, [rdx+r8-8]
0x14000db97  mov     [rcx], r11
0x14000db9a  mov     [rcx+r8-8], rdx
0x14000db9f  retn
0x14000dba0  cmp     r8, 20h ; ' '
0x14000dba4  ja      short loc_14000DC00
0x14000dba6  movups  xmm0, xmmword ptr [rdx]
0x14000dba9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14000dbaf  movups  xmmword ptr [rcx], xmm0
0x14000dbb2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14000dbb8  retn
0x14000dbc0  test    r8, r8
0x14000dbc3  jz      short locret_14000DBDA
0x14000dbc5  sub     rdx, rcx
0x14000dbc8  jb      short loc_14000DBE0
0x14000dbca  mov     r11b, [rcx+rdx]
0x14000dbce  inc     rcx
0x14000dbd1  dec     r8
0x14000dbd4  mov     [rcx-1], r11b
0x14000dbd8  jnz     short loc_14000DBCA
0x14000dbda  retn
0x14000dbe0  add     rcx, r8
0x14000dbe3  mov     r11b, [rcx+rdx-1]
0x14000dbe8  dec     rcx
0x14000dbeb  dec     r8
0x14000dbee  mov     [rcx], r11b
0x14000dbf1  jnz     short loc_14000DBE3
0x14000dbf3  retn
0x14000dc00  lea     r11, [rdx+r8]
0x14000dc04  sub     rdx, rcx
0x14000dc07  jnb     short loc_14000DC12
0x14000dc09  cmp     r11, rcx
0x14000dc0c  ja      loc_14000DD80
0x14000dc12  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000dc16  add     rcx, 10h
0x14000dc1a  test    cl, 0Fh
0x14000dc1d  jz      short loc_14000DC31
0x14000dc1f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000dc23  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000dc27  movups  xmmword ptr [rax], xmm0
0x14000dc2a  movaps  xmm0, xmm1
0x14000dc2d  add     rcx, 10h
0x14000dc31  add     r8, rax
0x14000dc34  sub     r8, rcx
0x14000dc37  mov     r9, r8
0x14000dc3a  shr     r9, 6
0x14000dc3e  jz      short loc_14000DCAF
0x14000dc40  cmp     r9, 1000h
0x14000dc47  ja      loc_14000DD00
0x14000dc4d  and     r8, 3Fh
0x14000dc51  jmp     short loc_14000DC80
0x14000dc80  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000dc84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000dc89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000dc8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000dc93  movaps  xmmword ptr [rcx-10h], xmm0
0x14000dc97  add     rcx, 40h ; '@'
0x14000dc9b  dec     r9
0x14000dc9e  movaps  xmmword ptr [rcx-40h], xmm1
0x14000dca2  movaps  xmmword ptr [rcx-30h], xmm2
0x14000dca6  movaps  xmmword ptr [rcx-20h], xmm3
0x14000dcaa  movaps  xmm0, xmm4
0x14000dcad  jnz     short loc_14000DC80
0x14000dcaf  mov     r9, r8
0x14000dcb2  shr     r9, 4
0x14000dcb6  jz      short loc_14000DCD1
0x14000dcb8  nop     dword ptr [rax+rax+00000000h]
0x14000dcc0  movaps  xmmword ptr [rcx-10h], xmm0
0x14000dcc4  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000dcc8  add     rcx, 10h
0x14000dccc  dec     r9
0x14000dccf  jnz     short loc_14000DCC0
0x14000dcd1  and     r8, 0Fh
0x14000dcd5  jz      short loc_14000DCE5
0x14000dcd7  lea     r11, [rcx+r8-10h]
0x14000dcdc  movups  xmm1, xmmword ptr [r11+rdx]
0x14000dce1  movups  xmmword ptr [r11], xmm1
0x14000dce5  movaps  xmmword ptr [rcx-10h], xmm0
0x14000dce9  retn
0x14000dd00  mov     r9, r8
0x14000dd03  shr     r9, 6
0x14000dd07  and     r8, 3Fh
0x14000dd0b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000dd10  jmp     short loc_14000DD40
0x14000dd40  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000dd44  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000dd49  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000dd4e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000dd53  movntps xmmword ptr [rcx-10h], xmm0
0x14000dd57  add     rcx, 40h ; '@'
0x14000dd5b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000dd60  dec     r9
0x14000dd63  movntps xmmword ptr [rcx-40h], xmm1
0x14000dd67  movntps xmmword ptr [rcx-30h], xmm2
0x14000dd6b  movntps xmmword ptr [rcx-20h], xmm3
0x14000dd6f  movaps  xmm0, xmm4
0x14000dd72  jnz     short loc_14000DD40
0x14000dd74  sfence
0x14000dd77  jmp     loc_14000DCAF
0x14000dd80  add     rcx, r8
0x14000dd83  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000dd88  sub     rcx, 10h
0x14000dd8c  sub     r8, 10h
0x14000dd90  test    cl, 0Fh
0x14000dd93  jz      short loc_14000DDAD
0x14000dd95  mov     r11, rcx
0x14000dd98  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000dd9c  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000dda0  movups  xmmword ptr [r11], xmm0
0x14000dda4  movaps  xmm0, xmm1
0x14000dda7  mov     r8, rcx
0x14000ddaa  sub     r8, rax
0x14000ddad  mov     r9, r8
0x14000ddb0  shr     r9, 6
0x14000ddb4  jz      short loc_14000DDEF
0x14000ddb6  and     r8, 3Fh
0x14000ddba  jmp     short loc_14000DDC0
0x14000ddc0  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14000ddc5  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000ddca  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000ddcf  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14000ddd4  movaps  xmmword ptr [rcx], xmm0
0x14000ddd7  sub     rcx, 40h ; '@'
0x14000dddb  dec     r9
0x14000ddde  movaps  xmmword ptr [rcx+30h], xmm1
0x14000dde2  movaps  xmmword ptr [rcx+20h], xmm2
0x14000dde6  movaps  xmmword ptr [rcx+10h], xmm3
0x14000ddea  movaps  xmm0, xmm4
0x14000dded  jnz     short loc_14000DDC0
0x14000ddef  mov     r9, r8
0x14000ddf2  shr     r9, 4
0x14000ddf6  jz      short loc_14000DE11
0x14000ddf8  nop     dword ptr [rax+rax+00000000h]
0x14000de00  movaps  xmmword ptr [rcx], xmm0
0x14000de03  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000de08  sub     rcx, 10h
0x14000de0c  dec     r9
0x14000de0f  jnz     short loc_14000DE00
0x14000de11  and     r8, 0Fh
0x14000de15  jz      short loc_14000DE26
0x14000de17  mov     r11, rcx
0x14000de1a  sub     r11, r8
0x14000de1d  movups  xmm1, xmmword ptr [r11+rdx]
0x14000de22  movups  xmmword ptr [r11], xmm1
0x14000de26  movaps  xmmword ptr [rcx], xmm0
0x14000de29  retn
```
