# NormaliseFrequencies

- ea: `0x180005a94`
- end: `0x180005b02`
- name: `NormaliseFrequencies`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026e0`
- `0x180005e58`

## callees

- `0x180005a94`

## pseudocode

```c
__int64 __fastcall NormaliseFrequencies(__int64 a1, __int64 a2)
{
  __m128 si128; // xmm3
  __int64 i; // rax
  __m128 v4; // xmm2
  __m128 v5; // xmm0
  __int64 result; // rax
  __m128 v7; // xmm2
  __m128 v8; // xmm0

  si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  for ( i = 0; i != 32; i += 8 )
  {
    v4 = (__m128)_mm_srli_epi16(_mm_loadu_si128((const __m128i *)(a2 + 2 * i)), 1u);
    v5 = (__m128)_mm_cmpeq_epi16((__m128i)v4, (__m128i)0LL);
    *(__m128 *)(a2 + 2 * i) = _mm_or_ps(_mm_and_ps(v5, si128), _mm_andnot_ps(v5, v4));
  }
  for ( result = 0; result != 288; result += 8 )
  {
    v7 = (__m128)_mm_srli_epi16(_mm_loadu_si128((const __m128i *)(a1 + 2 * result)), 1u);
    v8 = (__m128)_mm_cmpeq_epi16((__m128i)v7, (__m128i)0LL);
    *(__m128 *)(a1 + 2 * result) = _mm_or_ps(_mm_and_ps(v8, si128), _mm_andnot_ps(v8, v7));
  }
  return result;
}

```

## disassembly

```asm
0x180005a94  movdqa  xmm3, cs:__xmm@00010001000100010001000100010001
0x180005a9c  xorps   xmm4, xmm4
0x180005a9f  xor     eax, eax
0x180005aa1  movdqu  xmm2, xmmword ptr [rdx+rax*2]
0x180005aa6  psrlw   xmm2, 1
0x180005aab  movdqa  xmm1, xmm2
0x180005aaf  pcmpeqw xmm1, xmm4
0x180005ab3  movdqa  xmm0, xmm1
0x180005ab7  andnps  xmm1, xmm2
0x180005aba  andps   xmm0, xmm3
0x180005abd  orps    xmm0, xmm1
0x180005ac0  movdqu  xmmword ptr [rdx+rax*2], xmm0
0x180005ac5  add     rax, 8
0x180005ac9  cmp     rax, 20h ; ' '
0x180005acd  jnz     short loc_180005AA1
0x180005acf  xor     eax, eax
0x180005ad1  movdqu  xmm2, xmmword ptr [rcx+rax*2]
0x180005ad6  psrlw   xmm2, 1
0x180005adb  movdqa  xmm1, xmm2
0x180005adf  pcmpeqw xmm1, xmm4
0x180005ae3  movdqa  xmm0, xmm1
0x180005ae7  andnps  xmm1, xmm2
0x180005aea  andps   xmm0, xmm3
0x180005aed  orps    xmm0, xmm1
0x180005af0  movdqu  xmmword ptr [rcx+rax*2], xmm0
0x180005af5  add     rax, 8
0x180005af9  cmp     rax, 120h
0x180005aff  jnz     short loc_180005AD1
0x180005b01  retn
```
