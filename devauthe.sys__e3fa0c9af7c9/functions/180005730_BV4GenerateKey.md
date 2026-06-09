# BV4GenerateKey

- ea: `0x180005730`
- end: `0x180005833`
- name: `BV4GenerateKey`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005984`
- `0x180005f7c`

## callees

- `0x180005730`

## pseudocode

```c
char __fastcall BV4GenerateKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r10
  __int64 v4; // r11
  __int64 v5; // rcx
  __m128i v7; // xmm0
  __m128i v8; // xmm0
  __int64 i; // r9
  unsigned int v10; // ecx
  char v11; // r8
  int v12; // eax
  __int64 v13; // r9
  int *v14; // r11
  __int64 v15; // r10
  int v16; // ebx
  char v17; // dl
  char result; // al

  v3 = 0;
  LOBYTE(v4) = 0;
  word_18000C760 = 0;
  v5 = 0;
  do
  {
    v7 = (__m128i)_mm_and_ps(
                    (__m128)_mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v5), 0), (__m128i)_xmm),
                    (__m128)_xmm);
    v8 = _mm_packus_epi16(v7, v7);
    *(_DWORD *)((char *)sBV4KEY + v5) = _mm_cvtsi128_si32(_mm_packus_epi16(v8, v8));
    v5 = (unsigned int)(v5 + 4);
  }
  while ( (unsigned int)v5 < 0x100 );
  for ( i = 0; i != 256; ++i )
  {
    v10 = v3 + 1;
    v11 = *((_BYTE *)sBV4KEY + i);
    v4 = (unsigned __int8)(v11 + v4 + *(_BYTE *)(v3 + a3));
    *((_BYTE *)sBV4KEY + i) = *((_BYTE *)sBV4KEY + v4);
    v12 = v3;
    v3 = 0;
    *((_BYTE *)sBV4KEY + v4) = v11;
    if ( v12 != 7 )
      v3 = v10;
  }
  LOBYTE(v13) = word_18000C760;
  v14 = &dword_18000C764;
  LOBYTE(v15) = HIBYTE(word_18000C760);
  v16 = 132;
  do
  {
    v13 = (unsigned __int8)(v13 + 1);
    v17 = *((_BYTE *)sBV4KEY + v13);
    v15 = (unsigned __int8)(v17 + v15);
    *((_BYTE *)sBV4KEY + v13) = *((_BYTE *)sBV4KEY + v15);
    *((_BYTE *)sBV4KEY + v15) = v17;
    result = *((_BYTE *)sBV4KEY + (unsigned __int8)(v17 + *((_BYTE *)sBV4KEY + v13)));
    *(_BYTE *)v14 = result;
    v14 = (int *)((char *)v14 + 1);
    --v16;
  }
  while ( v16 );
  LOBYTE(word_18000C760) = v13;
  HIBYTE(word_18000C760) = v15;
  return result;
}

```

## disassembly

```asm
0x180005730  mov     [rsp+arg_0], rbx
0x180005735  mov     [rsp+arg_8], rdi
0x18000573a  xor     r10d, r10d
0x18000573d  lea     rdi, sBV4KEY
0x180005744  xor     r11d, r11d
0x180005747  mov     cs:word_18000C760, r10w
0x18000574f  xor     ecx, ecx
0x180005751  mov     rbx, r8
0x180005754  movd    xmm0, ecx
0x180005758  pshufd  xmm0, xmm0, 0
0x18000575d  paddd   xmm0, cs:__xmm@00000003000000020000000100000000
0x180005765  andps   xmm0, cs:__xmm@000000ff000000ff000000ff000000ff
0x18000576c  packuswb xmm0, xmm0
0x180005770  packuswb xmm0, xmm0
0x180005774  movd    dword ptr [rcx+rdi], xmm0
0x180005779  add     ecx, 4
0x18000577c  cmp     ecx, 100h
0x180005782  jb      short loc_180005754
0x180005784  xor     r9d, r9d
0x180005787  movzx   edx, byte ptr [r10+rbx]
0x18000578c  lea     ecx, [r10+1]
0x180005790  movzx   r8d, byte ptr [r9+rdi]
0x180005795  add     edx, r11d
0x180005798  add     edx, r8d
0x18000579b  movzx   r11d, dl
0x18000579f  mov     al, [r11+rdi]
0x1800057a3  mov     [r9+rdi], al
0x1800057a7  mov     eax, r10d
0x1800057aa  xor     r10d, r10d
0x1800057ad  mov     [r11+rdi], r8b
0x1800057b1  cmp     eax, 7
0x1800057b4  cmovnz  r10d, ecx
0x1800057b8  inc     r9
0x1800057bb  cmp     r9, 100h
0x1800057c2  jnz     short loc_180005787
0x1800057c4  movzx   r9d, byte ptr cs:word_18000C760
0x1800057cc  lea     r11, dword_18000C764
0x1800057d3  movzx   r10d, byte ptr cs:word_18000C760+1
0x1800057db  mov     ebx, 84h
0x1800057e0  lea     eax, [r9+1]
0x1800057e4  movzx   r9d, al
0x1800057e8  movzx   edx, byte ptr [r9+rdi]
0x1800057ed  lea     eax, [rdx+r10]
0x1800057f1  movzx   r10d, al
0x1800057f5  mov     al, [r10+rdi]
0x1800057f9  mov     [r9+rdi], al
0x1800057fd  mov     [r10+rdi], dl
0x180005801  movzx   eax, byte ptr [r9+rdi]
0x180005806  add     eax, edx
0x180005808  movzx   eax, al
0x18000580b  mov     al, [rax+rdi]
0x18000580e  mov     [r11], al
0x180005811  inc     r11
0x180005814  add     ebx, 0FFFFFFFFh
0x180005817  jnz     short loc_1800057E0
0x180005819  mov     rbx, [rsp+arg_0]
0x18000581e  mov     rdi, [rsp+arg_8]
0x180005823  mov     byte ptr cs:word_18000C760, r9b
0x18000582a  mov     byte ptr cs:word_18000C760+1, r10b
0x180005831  retn
```
