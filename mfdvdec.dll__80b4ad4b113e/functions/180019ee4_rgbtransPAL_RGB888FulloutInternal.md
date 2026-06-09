# rgbtransPAL_RGB888FulloutInternal

- ea: `0x180019ee4`
- end: `0x18001a148`
- name: `rgbtransPAL_RGB888FulloutInternal`
- size: `612`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a150`
- `0x18001a170`

## callees

- `0x180019ee4`

## pseudocode

```c
__int64 __fastcall rgbtransPAL_RGB888FulloutInternal(const __m128i *a1, _QWORD *a2, int a3, __int64 a4)
{
  const __m128i *v4; // r10
  int v5; // r11d
  const __m128i *v6; // rbx
  __int64 v7; // r8
  int v8; // eax
  __m128i v9; // xmm4
  _QWORD *v10; // rcx
  __m128i v11; // xmm2
  __m128i v12; // xmm0
  __m128i v13; // xmm10
  __m128i v14; // xmm1
  __m128 v15; // xmm2
  __m128i v16; // xmm9
  __m128i v17; // xmm3
  __m128 v18; // xmm10
  __m128 v19; // xmm1
  __m128i v20; // xmm2
  __m128i v21; // xmm7
  __m128i v22; // xmm6
  __m128i v23; // xmm1
  __m128 v24; // xmm5
  __m128i v25; // xmm3
  __m128i v26; // xmm4
  __m128i v27; // xmm5
  __m128i v28; // xmm8
  __m128i v29; // xmm1
  __m128i v30; // xmm1
  __m128i v31; // xmm2
  const __m128i *v32; // rcx
  __int64 result; // rax

  v4 = a1 + 4;
  v5 = 0;
  v6 = a1;
  v7 = a3 - 48 + 24LL;
  do
  {
    v8 = 2;
    do
    {
      v9 = _mm_loadl_epi64((const __m128i *)(a4 + 32));
      v10 = a2;
      v11 = _mm_loadl_epi64(v4 + 1);
      v12 = _mm_mulhi_epi16(_mm_loadl_epi64(v4), _mm_loadl_epi64((const __m128i *)a4));
      v13 = _mm_unpacklo_epi16(
              _mm_adds_epi16(_mm_mulhi_epi16(_mm_loadl_epi64((const __m128i *)(a4 + 8)), v11), v9),
              _mm_adds_epi16(v12, v9));
      v14 = _mm_unpacklo_epi16(
              _mm_adds_epi16(
                _mm_subs_epi16(
                  _mm_mulhi_epi16(_mm_loadl_epi64((const __m128i *)(a4 + 16)), v11),
                  _mm_srai_epi16(v12, 1u)),
                v9),
              (__m128i)0LL);
      v15 = (__m128)_mm_unpacklo_epi16(v13, v14);
      v16 = _mm_mulhi_epi16(_mm_loadl_epi64((const __m128i *)(a4 + 24)), _mm_loadl_epi64(v6));
      v17 = (__m128i)_mm_or_ps((__m128)_mm_slli_epi64((__m128i)v15, 0x30u), v15);
      v18 = (__m128)_mm_unpacklo_epi16(_mm_srli_si128(v13, 8), _mm_srli_si128(v14, 8));
      v19 = (__m128)_mm_srli_si128((__m128i)v15, 8);
      v20 = _mm_unpacklo_epi16(v16, v16);
      v21 = (__m128i)_mm_or_ps((__m128)_mm_slli_epi64((__m128i)v19, 0x30u), v19);
      v22 = _mm_srli_si128(v20, 8);
      v23 = _mm_adds_epi16(
              _mm_unpacklo_epi32(_mm_srli_epi64(v20, 0x20u), v22),
              _mm_unpacklo_epi32(_mm_srli_epi64(v17, 0x10u), v21));
      v24 = (__m128)_mm_srli_si128((__m128i)v18, 8);
      *a2 = _mm_packus_epi16(_mm_unpacklo_epi64(_mm_adds_epi16(_mm_unpacklo_epi16(v20, v16), v17), v23), v23).m128i_u64[0];
      v25 = _mm_mulhi_epi16(
              _mm_loadl_epi64((const __m128i *)&v6->m128i_u64[1]),
              _mm_loadl_epi64((const __m128i *)(a4 + 24)));
      v26 = (__m128i)_mm_or_ps((__m128)_mm_slli_epi64((__m128i)v24, 0x30u), v24);
      v27 = _mm_unpacklo_epi16(v25, v25);
      v28 = (__m128i)_mm_or_ps((__m128)_mm_slli_epi64((__m128i)v18, 0x30u), v18);
      v29 = _mm_adds_epi16(_mm_unpacklo_epi16(v27, v25), v28);
      v21.m128i_i64[0] = _mm_packus_epi16(
                           _mm_unpacklo_epi64(
                             _mm_adds_epi16(
                               _mm_srli_si128(_mm_unpacklo_epi32(v21, _mm_slli_epi64(v21, 0x10u)), 8),
                               _mm_srli_si128(_mm_unpacklo_epi16(v16, v22), 8)),
                             v29),
                           v29).m128i_u64[0];
      v30 = _mm_srli_si128(v27, 8);
      a2[1] = v21.m128i_i64[0];
      v4 = (const __m128i *)((char *)v4 + 8);
      ++v6;
      v31 = _mm_adds_epi16(
              _mm_srli_si128(_mm_unpacklo_epi32(v26, _mm_slli_epi64(v26, 0x10u)), 8),
              _mm_srli_si128(_mm_unpacklo_epi16(v25, v30), 8));
      a2[2] = _mm_packus_epi16(
                _mm_unpacklo_epi64(
                  _mm_adds_epi16(
                    _mm_unpacklo_epi32(_mm_srli_epi64(v28, 0x10u), v26),
                    _mm_unpacklo_epi32(_mm_srli_epi64(v27, 0x20u), v30)),
                  v31),
                v31).m128i_u64[0];
      a2 += 3;
      --v8;
    }
    while ( v8 );
    ++v5;
    a2 = (_QWORD *)((char *)v10 + v7);
    v32 = v4 + 5;
    if ( (v5 & 7) != 0 )
    {
      v4 -= 7;
      result = 64;
      if ( (v5 & 3) != 2 )
        v4 = v32;
    }
    else
    {
      v4 += 5;
      result = -672;
    }
    v6 = (const __m128i *)((char *)v6 + result);
  }
  while ( v5 < 16 );
  return result;
}

```

## disassembly

```asm
0x180019ee4  mov     rax, rsp
0x180019ee7  push    rbx
0x180019ee8  sub     rsp, 50h
0x180019eec  movaps  xmmword ptr [rax-18h], xmm6
0x180019ef0  lea     r10, [rcx+40h]
0x180019ef4  movaps  xmmword ptr [rax-28h], xmm7
0x180019ef8  xor     r11d, r11d
0x180019efb  movaps  xmmword ptr [rax-38h], xmm8
0x180019f00  mov     rbx, rcx
0x180019f03  movaps  xmmword ptr [rax-48h], xmm9
0x180019f08  lea     eax, [r8-30h]
0x180019f0c  movsxd  r8, eax
0x180019f0f  add     r8, 18h
0x180019f13  movaps  [rsp+58h+var_58], xmm10
0x180019f18  mov     eax, 2
0x180019f1d  movq    xmm4, qword ptr [r9+20h]
0x180019f23  mov     rcx, rdx
0x180019f26  movq    xmm2, qword ptr [r10+10h]
0x180019f2c  movq    xmm0, qword ptr [r9]
0x180019f31  movq    xmm3, qword ptr [r10]
0x180019f36  movq    xmm10, qword ptr [r9+8]
0x180019f3c  movq    xmm1, qword ptr [r9+10h]
0x180019f42  movq    xmm9, qword ptr [r9+18h]
0x180019f48  pmulhw  xmm1, xmm2
0x180019f4c  pmulhw  xmm3, xmm0
0x180019f50  pmulhw  xmm10, xmm2
0x180019f55  movdqa  xmm0, xmm3
0x180019f59  psraw   xmm3, 1
0x180019f5e  psubsw  xmm1, xmm3
0x180019f62  paddsw  xmm0, xmm4
0x180019f66  paddsw  xmm1, xmm4
0x180019f6a  paddsw  xmm10, xmm4
0x180019f6f  punpcklwd xmm10, xmm0
0x180019f74  xorps   xmm0, xmm0
0x180019f77  punpcklwd xmm1, xmm0
0x180019f7b  movdqa  xmm2, xmm10
0x180019f80  movq    xmm0, qword ptr [rbx]
0x180019f84  punpcklwd xmm2, xmm1
0x180019f88  pmulhw  xmm9, xmm0
0x180019f8d  movdqa  xmm3, xmm2
0x180019f91  psrldq  xmm1, 8
0x180019f96  psllq   xmm3, 30h ; '0'
0x180019f9b  orps    xmm3, xmm2
0x180019f9e  psrldq  xmm10, 8
0x180019fa4  punpcklwd xmm10, xmm1
0x180019fa9  movdqa  xmm0, xmm3
0x180019fad  movdqa  xmm1, xmm2
0x180019fb1  psrlq   xmm0, 10h
0x180019fb6  psrldq  xmm1, 8
0x180019fbb  movdqa  xmm2, xmm9
0x180019fc0  movdqa  xmm7, xmm1
0x180019fc4  punpcklwd xmm2, xmm9
0x180019fc9  psllq   xmm7, 30h ; '0'
0x180019fce  movdqa  xmm6, xmm2
0x180019fd2  orps    xmm7, xmm1
0x180019fd5  psrldq  xmm6, 8
0x180019fda  punpckldq xmm0, xmm7
0x180019fde  movdqa  xmm1, xmm2
0x180019fe2  psrlq   xmm1, 20h ; ' '
0x180019fe7  movdqa  xmm5, xmm10
0x180019fec  punpckldq xmm1, xmm6
0x180019ff0  movdqa  xmm8, xmm10
0x180019ff5  paddsw  xmm1, xmm0
0x180019ff9  punpcklwd xmm2, xmm9
0x180019ffe  paddsw  xmm2, xmm3
0x18001a002  psrldq  xmm5, 8
0x18001a007  punpcklqdq xmm2, xmm1
0x18001a00b  movdqa  xmm4, xmm5
0x18001a00f  packuswb xmm2, xmm1
0x18001a013  movq    qword ptr [rdx], xmm2
0x18001a017  movq    xmm0, qword ptr [r9+18h]
0x18001a01d  movq    xmm3, qword ptr [rbx+8]
0x18001a022  pmulhw  xmm3, xmm0
0x18001a026  movdqa  xmm0, xmm7
0x18001a02a  psllq   xmm0, 10h
0x18001a02f  punpckldq xmm7, xmm0
0x18001a033  psrldq  xmm7, 8
0x18001a038  psllq   xmm4, 30h ; '0'
0x18001a03d  orps    xmm4, xmm5
0x18001a040  psllq   xmm8, 30h ; '0'
0x18001a046  movdqa  xmm5, xmm3
0x18001a04a  punpcklwd xmm9, xmm6
0x18001a04f  punpcklwd xmm5, xmm3
0x18001a053  orps    xmm8, xmm10
0x18001a057  movdqa  xmm1, xmm5
0x18001a05b  psrldq  xmm9, 8
0x18001a061  punpcklwd xmm1, xmm3
0x18001a065  paddsw  xmm7, xmm9
0x18001a06a  paddsw  xmm1, xmm8
0x18001a06f  movdqa  xmm0, xmm4
0x18001a073  punpcklqdq xmm7, xmm1
0x18001a077  packuswb xmm7, xmm1
0x18001a07b  movdqa  xmm1, xmm5
0x18001a07f  psrldq  xmm1, 8
0x18001a084  movq    qword ptr [rdx+8], xmm7
0x18001a089  psllq   xmm0, 10h
0x18001a08e  psrlq   xmm8, 10h
0x18001a094  lea     r10, [r10+8]
0x18001a098  punpckldq xmm8, xmm4
0x18001a09d  movdqa  xmm2, xmm4
0x18001a0a1  punpckldq xmm2, xmm0
0x18001a0a5  add     rbx, 10h
0x18001a0a9  punpcklwd xmm3, xmm1
0x18001a0ad  psrlq   xmm5, 20h ; ' '
0x18001a0b2  psrldq  xmm2, 8
0x18001a0b7  psrldq  xmm3, 8
0x18001a0bc  paddsw  xmm2, xmm3
0x18001a0c0  punpckldq xmm5, xmm1
0x18001a0c4  paddsw  xmm8, xmm5
0x18001a0c9  punpcklqdq xmm8, xmm2
0x18001a0ce  packuswb xmm8, xmm2
0x18001a0d3  movq    qword ptr [rdx+10h], xmm8
0x18001a0d9  add     rdx, 18h
0x18001a0dd  sub     eax, 1
0x18001a0e0  jnz     loc_180019F1D
0x18001a0e6  inc     r11d
0x18001a0e9  lea     rdx, [rcx+r8]
0x18001a0ed  lea     rcx, [r10+50h]
0x18001a0f1  test    r11b, 7
0x18001a0f5  jz      short loc_18001A110
0x18001a0f7  mov     eax, r11d
0x18001a0fa  lea     r10, [rcx-0C0h]
0x18001a101  and     al, 3
0x18001a103  cmp     al, 2
0x18001a105  mov     eax, 40h ; '@'
0x18001a10a  cmovnz  r10, rcx
0x18001a10e  jmp     short loc_18001A11A
0x18001a110  mov     r10, rcx
0x18001a113  mov     rax, 0FFFFFFFFFFFFFD60h
0x18001a11a  add     rbx, rax
0x18001a11d  cmp     r11d, 10h
0x18001a121  jl      loc_180019F18
0x18001a127  movaps  xmm6, [rsp+58h+var_18]
0x18001a12c  movaps  xmm7, [rsp+58h+var_28]
0x18001a131  movaps  xmm8, [rsp+58h+var_38]
0x18001a137  movaps  xmm9, [rsp+58h+var_48]
0x18001a13d  movaps  xmm10, [rsp+58h+var_58]
0x18001a142  add     rsp, 50h
0x18001a146  pop     rbx
0x18001a147  retn
```
