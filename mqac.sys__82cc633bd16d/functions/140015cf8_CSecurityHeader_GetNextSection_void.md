# CSecurityHeader::GetNextSection(void)

- ea: `0x140015cf8`
- end: `0x140015d75`
- name: `?GetNextSection@CSecurityHeader@@QEBAPEADXZ`
- size: `125`
- prototype: `char *__fastcall(CSecurityHeader *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012dc4`
- `0x140015e04`

## callees

- `0x140015cf8`

## pseudocode

```c
char *__fastcall CSecurityHeader::GetNextSection(CSecurityHeader *this)
{
  __m128i v1; // xmm1
  __int64 v2; // rax
  char *result; // rax
  __int64 i; // rcx
  _QWORD v5[2]; // [rsp+0h] [rbp-48h]
  __m128 v6; // [rsp+10h] [rbp-38h]
  unsigned __int64 v7; // [rsp+20h] [rbp-28h]
  unsigned __int64 v8; // [rsp+28h] [rbp-20h]
  unsigned __int64 v9; // [rsp+30h] [rbp-18h]

  v1 = _mm_cvtsi32_si128(*(_DWORD *)((char *)this + 2));
  v2 = *((unsigned __int16 *)this + 3) + 3LL;
  v5[0] = this;
  v5[1] = 16;
  v6 = _mm_and_ps(
         (__m128)_mm_add_epi64(_mm_unpacklo_epi32(_mm_unpacklo_epi16(v1, (__m128i)0LL), (__m128i)0LL), (__m128i)_xmm),
         (__m128)_xmm_fffffffffffffffcfffffffffffffffc);
  v7 = v2 & 0xFFFFFFFFFFFFFFFCuLL;
  v8 = (*((unsigned int *)this + 2) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
  v9 = (*((unsigned int *)this + 3) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
  result = 0;
  for ( i = 0; i != 7; ++i )
    result += v5[i];
  return result;
}

```

## disassembly

```asm
0x140015cf8  mov     r11, rsp
0x140015cfb  sub     rsp, 48h
0x140015cff  movd    xmm1, dword ptr [rcx+2]
0x140015d04  xorps   xmm0, xmm0
0x140015d07  movzx   eax, word ptr [rcx+6]
0x140015d0b  add     rax, 3
0x140015d0f  mov     [rsp+48h+var_48], rcx
0x140015d13  and     rax, 0FFFFFFFFFFFFFFFCh
0x140015d17  punpcklwd xmm1, xmm0
0x140015d1b  punpckldq xmm1, xmm0
0x140015d1f  paddq   xmm1, cs:__xmm@00000000000000030000000000000003
0x140015d27  andps   xmm1, cs:__xmm@fffffffffffffffcfffffffffffffffc
0x140015d2e  mov     qword ptr [r11-40h], 10h
0x140015d36  movdqu  [rsp+48h+var_38], xmm1
0x140015d3c  mov     [r11-28h], rax
0x140015d40  mov     eax, [rcx+8]
0x140015d43  add     rax, 3
0x140015d47  and     rax, 0FFFFFFFFFFFFFFFCh
0x140015d4b  mov     [r11-20h], rax
0x140015d4f  mov     eax, [rcx+0Ch]
0x140015d52  add     rax, 3
0x140015d56  and     rax, 0FFFFFFFFFFFFFFFCh
0x140015d5a  mov     [r11-18h], rax
0x140015d5e  xor     eax, eax
0x140015d60  xor     ecx, ecx
0x140015d62  add     rax, [rsp+rcx*8+48h+var_48]
0x140015d66  inc     rcx
0x140015d69  cmp     rcx, 7
0x140015d6d  jnz     short loc_140015D62
0x140015d6f  add     rsp, 48h
0x140015d73  retn
```
