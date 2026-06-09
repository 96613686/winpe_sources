# __memset_spec_plain

- ea: `0x140003d00`
- end: `0x140003df7`
- name: `__memset_spec_plain`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003d00`

## pseudocode

```c
_OWORD *__fastcall _memset_spec_plain(_OWORD *a1, unsigned __int8 a2, unsigned __int64 a3)
{
  _OWORD *result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  unsigned __int64 v9; // r8
  __m128 *v10; // r9
  unsigned __int64 v11; // r8
  _DWORD *v12; // r9
  unsigned __int64 v13; // r8

  result = a1;
  v4 = 0x101010101010101LL * a2;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( a3 >= 0x40 )
  {
    *a1 = v5;
    v6 = (char *)a1 + a3;
    a1 = (_OWORD *)((unsigned __int64)(a1 + 1) & 0xFFFFFFFFFFFFFFF0uLL);
    a3 = v6 - (char *)a1;
    if ( a3 >= 0x40 )
    {
      v7 = (__m128 *)((char *)a1 + a3 - 16);
      v8 = (_OWORD *)(((unsigned __int64)a1 + a3 - 48) & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = a3 >> 6;
      do
      {
        *a1 = v5;
        a1[1] = v5;
        a1 += 4;
        --v9;
        *(a1 - 2) = v5;
        *(a1 - 1) = v5;
      }
      while ( v9 );
      *v8 = v5;
      v8[1] = v5;
      v8[2] = v5;
      *v7 = v5;
      return result;
    }
LABEL_7:
    v10 = (__m128 *)((char *)a1 + a3 - 16);
    *a1 = v5;
    v11 = (a3 & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)((char *)a1 + v11) = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( a3 >= 0x10 )
    goto LABEL_7;
  if ( a3 < 4 )
  {
    if ( a3 )
    {
      *(_BYTE *)a1 = v4;
      if ( a3 != 1 )
        *(_WORD *)((char *)a1 + a3 - 2) = v4;
    }
  }
  else
  {
    v12 = (_DWORD *)((char *)a1 + a3 - 4);
    *(_DWORD *)a1 = v4;
    v13 = (a3 & 8) >> 1;
    *v12 = v4;
    *(_DWORD *)((char *)a1 + v13) = v4;
    *(_DWORD *)((char *)v12 - v13) = v4;
  }
  return result;
}

```

## disassembly

```asm
0x140003d00  mov     rax, rcx
0x140003d03  movzx   edx, dl
0x140003d06  mov     r9, 101010101010101h
0x140003d10  imul    rdx, r9
0x140003d14  movq    xmm0, rdx
0x140003d19  movlhps xmm0, xmm0
0x140003d1c  cmp     r8, 40h ; '@'
0x140003d20  jb      short loc_140003D80
0x140003d22  movups  xmmword ptr [rcx], xmm0
0x140003d25  add     r8, rcx
0x140003d28  add     rcx, 10h
0x140003d2c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140003d30  sub     r8, rcx
0x140003d33  cmp     r8, 40h ; '@'
0x140003d37  jb      short loc_140003D86
0x140003d39  lea     rdx, [rcx+r8-10h]
0x140003d3e  lea     r9, [rcx+r8-30h]
0x140003d43  and     r9, 0FFFFFFFFFFFFFFF0h
0x140003d47  shr     r8, 6
0x140003d4b  movaps  xmmword ptr [rcx], xmm0
0x140003d4e  movaps  xmmword ptr [rcx+10h], xmm0
0x140003d52  add     rcx, 40h ; '@'
0x140003d56  dec     r8
0x140003d59  movaps  xmmword ptr [rcx-20h], xmm0
0x140003d5d  movaps  xmmword ptr [rcx-10h], xmm0
0x140003d61  jnz     short loc_140003D4B
0x140003d63  movaps  xmmword ptr [r9], xmm0
0x140003d67  movaps  xmmword ptr [r9+10h], xmm0
0x140003d6c  movaps  xmmword ptr [r9+20h], xmm0
0x140003d71  movups  xmmword ptr [rdx], xmm0
0x140003d74  retn
0x140003d80  cmp     r8, 10h
0x140003d84  jb      short loc_140003DB0
0x140003d86  lea     r9, [r8+rcx-10h]
0x140003d8b  and     r8, 20h
0x140003d8f  movups  xmmword ptr [rcx], xmm0
0x140003d92  shr     r8, 1
0x140003d95  movups  xmmword ptr [r9], xmm0
0x140003d99  movups  xmmword ptr [rcx+r8], xmm0
0x140003d9e  neg     r8
0x140003da1  movups  xmmword ptr [r9+r8], xmm0
0x140003da6  retn
0x140003db0  cmp     r8, 4
0x140003db4  jb      short loc_140003DE0
0x140003db6  lea     r9, [r8+rcx-4]
0x140003dbb  and     r8, 8
0x140003dbf  mov     [rcx], edx
0x140003dc1  shr     r8, 1
0x140003dc4  mov     [r9], edx
0x140003dc7  mov     [rcx+r8], edx
0x140003dcb  neg     r8
0x140003dce  mov     [r9+r8], edx
0x140003dd2  retn
0x140003de0  test    r8, r8
0x140003de3  jz      short locret_140003DF6
0x140003de5  mov     [rcx], dl
0x140003de7  lea     r9, [rcx+r8-2]
0x140003dec  cmp     r8, 1
0x140003df0  jz      short locret_140003DF6
0x140003df2  mov     [r9], dx
0x140003df6  retn
```
