# memmove

- ea: `0x14003adc0`
- end: `0x14003b06a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `45`
- callee_count: `1`
- tags: ``

## callers

- `0x140003510`
- `0x140005de0`
- `0x140008e10`
- `0x14000b680`
- `0x14000be20`
- `0x14000c370`
- `0x14000d4cc`
- `0x140010870`
- `0x140014bdc`
- `0x140014c64`
- `0x140014d04`
- `0x140014d98`
- `0x140014e1c`
- `0x140014ff4`
- `0x1400150f0`
- `0x140015988`
- `0x140015b48`
- `0x140016634`
- `0x140019044`
- `0x1400196a8`
- `0x14001a950`
- `0x14002030c`
- `0x140023dd0`
- `0x140024720`
- `0x140025040`
- `0x140028478`
- `0x140028870`
- `0x140029f20`
- `0x14002bc4c`
- `0x14002bf9c`
- `0x14002c2e0`
- `0x14002f040`
- `0x14002f744`
- `0x14003083c`
- `0x1400316d0`
- `0x140033dc0`
- `0x1400379c4`
- `0x140038850`
- `0x14003896c`
- `0x1400395d8`
- `0x14003972c`
- `0x140039910`
- `0x140039db8`
- `0x14003a5b8`
- `0x140046350`

## callees

- `0x14003adc0`

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
0x14003adc0  mov     rax, rcx
0x14003adc3  cmp     r8, 8
0x14003adc7  jb      short loc_14003AE00
0x14003adc9  cmp     r8, 10h
0x14003adcd  ja      short loc_14003ADE0
0x14003adcf  mov     r11, [rdx]
0x14003add2  mov     rdx, [rdx+r8-8]
0x14003add7  mov     [rcx], r11
0x14003adda  mov     [rcx+r8-8], rdx
0x14003addf  retn
0x14003ade0  cmp     r8, 20h ; ' '
0x14003ade4  ja      short loc_14003AE40
0x14003ade6  movups  xmm0, xmmword ptr [rdx]
0x14003ade9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14003adef  movups  xmmword ptr [rcx], xmm0
0x14003adf2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14003adf8  retn
0x14003ae00  test    r8, r8
0x14003ae03  jz      short locret_14003AE1A
0x14003ae05  sub     rdx, rcx
0x14003ae08  jb      short loc_14003AE20
0x14003ae0a  mov     r11b, [rcx+rdx]
0x14003ae0e  inc     rcx
0x14003ae11  dec     r8
0x14003ae14  mov     [rcx-1], r11b
0x14003ae18  jnz     short loc_14003AE0A
0x14003ae1a  retn
0x14003ae20  add     rcx, r8
0x14003ae23  mov     r11b, [rcx+rdx-1]
0x14003ae28  dec     rcx
0x14003ae2b  dec     r8
0x14003ae2e  mov     [rcx], r11b
0x14003ae31  jnz     short loc_14003AE23
0x14003ae33  retn
0x14003ae40  lea     r11, [rdx+r8]
0x14003ae44  sub     rdx, rcx
0x14003ae47  jnb     short loc_14003AE52
0x14003ae49  cmp     r11, rcx
0x14003ae4c  ja      loc_14003AFC0
0x14003ae52  movups  xmm0, xmmword ptr [rcx+rdx]
0x14003ae56  add     rcx, 10h
0x14003ae5a  test    cl, 0Fh
0x14003ae5d  jz      short loc_14003AE71
0x14003ae5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14003ae63  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003ae67  movups  xmmword ptr [rax], xmm0
0x14003ae6a  movaps  xmm0, xmm1
0x14003ae6d  add     rcx, 10h
0x14003ae71  add     r8, rax
0x14003ae74  sub     r8, rcx
0x14003ae77  mov     r9, r8
0x14003ae7a  shr     r9, 6
0x14003ae7e  jz      short loc_14003AEEF
0x14003ae80  cmp     r9, 1000h
0x14003ae87  ja      loc_14003AF40
0x14003ae8d  and     r8, 3Fh
0x14003ae91  jmp     short loc_14003AEC0
0x14003aec0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003aec4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14003aec9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14003aece  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14003aed3  movaps  xmmword ptr [rcx-10h], xmm0
0x14003aed7  add     rcx, 40h ; '@'
0x14003aedb  dec     r9
0x14003aede  movaps  xmmword ptr [rcx-40h], xmm1
0x14003aee2  movaps  xmmword ptr [rcx-30h], xmm2
0x14003aee6  movaps  xmmword ptr [rcx-20h], xmm3
0x14003aeea  movaps  xmm0, xmm4
0x14003aeed  jnz     short loc_14003AEC0
0x14003aeef  mov     r9, r8
0x14003aef2  shr     r9, 4
0x14003aef6  jz      short loc_14003AF11
0x14003aef8  nop     dword ptr [rax+rax+00000000h]
0x14003af00  movaps  xmmword ptr [rcx-10h], xmm0
0x14003af04  movups  xmm0, xmmword ptr [rcx+rdx]
0x14003af08  add     rcx, 10h
0x14003af0c  dec     r9
0x14003af0f  jnz     short loc_14003AF00
0x14003af11  and     r8, 0Fh
0x14003af15  jz      short loc_14003AF25
0x14003af17  lea     r11, [rcx+r8-10h]
0x14003af1c  movups  xmm1, xmmword ptr [r11+rdx]
0x14003af21  movups  xmmword ptr [r11], xmm1
0x14003af25  movaps  xmmword ptr [rcx-10h], xmm0
0x14003af29  retn
0x14003af40  mov     r9, r8
0x14003af43  shr     r9, 6
0x14003af47  and     r8, 3Fh
0x14003af4b  prefetchnta byte ptr [rcx+rdx+40h]
0x14003af50  jmp     short loc_14003AF80
0x14003af80  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003af84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14003af89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14003af8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14003af93  movntps xmmword ptr [rcx-10h], xmm0
0x14003af97  add     rcx, 40h ; '@'
0x14003af9b  prefetchnta byte ptr [rcx+rdx+40h]
0x14003afa0  dec     r9
0x14003afa3  movntps xmmword ptr [rcx-40h], xmm1
0x14003afa7  movntps xmmword ptr [rcx-30h], xmm2
0x14003afab  movntps xmmword ptr [rcx-20h], xmm3
0x14003afaf  movaps  xmm0, xmm4
0x14003afb2  jnz     short loc_14003AF80
0x14003afb4  sfence
0x14003afb7  jmp     loc_14003AEEF
0x14003afc0  add     rcx, r8
0x14003afc3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14003afc8  sub     rcx, 10h
0x14003afcc  sub     r8, 10h
0x14003afd0  test    cl, 0Fh
0x14003afd3  jz      short loc_14003AFED
0x14003afd5  mov     r11, rcx
0x14003afd8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14003afdc  movups  xmm1, xmmword ptr [rcx+rdx]
0x14003afe0  movups  xmmword ptr [r11], xmm0
0x14003afe4  movaps  xmm0, xmm1
0x14003afe7  mov     r8, rcx
0x14003afea  sub     r8, rax
0x14003afed  mov     r9, r8
0x14003aff0  shr     r9, 6
0x14003aff4  jz      short loc_14003B02F
0x14003aff6  and     r8, 3Fh
0x14003affa  jmp     short loc_14003B000
0x14003b000  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14003b005  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14003b00a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14003b00f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14003b014  movaps  xmmword ptr [rcx], xmm0
0x14003b017  sub     rcx, 40h ; '@'
0x14003b01b  dec     r9
0x14003b01e  movaps  xmmword ptr [rcx+30h], xmm1
0x14003b022  movaps  xmmword ptr [rcx+20h], xmm2
0x14003b026  movaps  xmmword ptr [rcx+10h], xmm3
0x14003b02a  movaps  xmm0, xmm4
0x14003b02d  jnz     short loc_14003B000
0x14003b02f  mov     r9, r8
0x14003b032  shr     r9, 4
0x14003b036  jz      short loc_14003B051
0x14003b038  nop     dword ptr [rax+rax+00000000h]
0x14003b040  movaps  xmmword ptr [rcx], xmm0
0x14003b043  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14003b048  sub     rcx, 10h
0x14003b04c  dec     r9
0x14003b04f  jnz     short loc_14003B040
0x14003b051  and     r8, 0Fh
0x14003b055  jz      short loc_14003B066
0x14003b057  mov     r11, rcx
0x14003b05a  sub     r11, r8
0x14003b05d  movups  xmm1, xmmword ptr [r11+rdx]
0x14003b062  movups  xmmword ptr [r11], xmm1
0x14003b066  movaps  xmmword ptr [rcx], xmm0
0x14003b069  retn
```
