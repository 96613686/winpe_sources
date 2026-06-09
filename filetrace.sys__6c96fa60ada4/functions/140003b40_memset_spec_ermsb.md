# __memset_spec_ermsb

- ea: `0x140003b40`
- end: `0x140003c47`
- name: `__memset_spec_ermsb`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003b40`
- `0x140003c80`

## pseudocode

```c
__int64 __fastcall _memset_spec_ermsb(char *a1, unsigned __int8 a2, unsigned __int64 a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  unsigned __int64 v9; // r8
  __m128 *v10; // r9
  unsigned __int64 v11; // r8
  char *v12; // r9
  unsigned __int64 v13; // r8

  result = (__int64)a1;
  v4 = 0x101010101010101LL * a2;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( a3 >= 0x40 )
  {
    if ( a3 >= 0x320 )
      return _memset_spec_ermsb_repmovsb();
    *(__m128 *)a1 = v5;
    v6 = &a1[a3];
    a1 = (char *)((unsigned __int64)(a1 + 16) & 0xFFFFFFFFFFFFFFF0uLL);
    a3 = v6 - a1;
    if ( a3 >= 0x40 )
    {
      v7 = (__m128 *)&a1[a3 - 16];
      v8 = (_OWORD *)((unsigned __int64)&a1[a3 - 48] & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = a3 >> 6;
      do
      {
        *(__m128 *)a1 = v5;
        *((__m128 *)a1 + 1) = v5;
        a1 += 64;
        --v9;
        *((__m128 *)a1 - 2) = v5;
        *((__m128 *)a1 - 1) = v5;
      }
      while ( v9 );
      *v8 = v5;
      v8[1] = v5;
      v8[2] = v5;
      *v7 = v5;
      return result;
    }
LABEL_8:
    v10 = (__m128 *)&a1[a3 - 16];
    *(__m128 *)a1 = v5;
    v11 = (a3 & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)&a1[v11] = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( a3 >= 0x10 )
    goto LABEL_8;
  if ( a3 < 4 )
  {
    if ( a3 )
    {
      *a1 = v4;
      if ( a3 != 1 )
        *(_WORD *)&a1[a3 - 2] = v4;
    }
  }
  else
  {
    v12 = &a1[a3 - 4];
    *(_DWORD *)a1 = v4;
    v13 = (a3 & 8) >> 1;
    *(_DWORD *)v12 = v4;
    *(_DWORD *)&a1[v13] = v4;
    *(_DWORD *)&v12[-v13] = v4;
  }
  return result;
}

```

## disassembly

```asm
0x140003b40  mov     rax, rcx
0x140003b43  movzx   edx, dl
0x140003b46  mov     r9, 101010101010101h
0x140003b50  imul    rdx, r9
0x140003b54  movq    xmm0, rdx
0x140003b59  movlhps xmm0, xmm0
0x140003b5c  cmp     r8, 40h ; '@'
0x140003b60  jb      short loc_140003BD0
0x140003b62  cmp     r8, 320h
0x140003b69  jnb     __memset_spec_ermsb_repmovsb
0x140003b6f  movups  xmmword ptr [rcx], xmm0
0x140003b72  add     r8, rcx
0x140003b75  add     rcx, 10h
0x140003b79  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140003b7d  sub     r8, rcx
0x140003b80  cmp     r8, 40h ; '@'
0x140003b84  jb      short loc_140003BD6
0x140003b86  lea     rdx, [rcx+r8-10h]
0x140003b8b  lea     r9, [rcx+r8-30h]
0x140003b90  and     r9, 0FFFFFFFFFFFFFFF0h
0x140003b94  shr     r8, 6
0x140003b98  movaps  xmmword ptr [rcx], xmm0
0x140003b9b  movaps  xmmword ptr [rcx+10h], xmm0
0x140003b9f  add     rcx, 40h ; '@'
0x140003ba3  dec     r8
0x140003ba6  movaps  xmmword ptr [rcx-20h], xmm0
0x140003baa  movaps  xmmword ptr [rcx-10h], xmm0
0x140003bae  jnz     short loc_140003B98
0x140003bb0  movaps  xmmword ptr [r9], xmm0
0x140003bb4  movaps  xmmword ptr [r9+10h], xmm0
0x140003bb9  movaps  xmmword ptr [r9+20h], xmm0
0x140003bbe  movups  xmmword ptr [rdx], xmm0
0x140003bc1  retn
0x140003bd0  cmp     r8, 10h
0x140003bd4  jb      short loc_140003C00
0x140003bd6  lea     r9, [r8+rcx-10h]
0x140003bdb  and     r8, 20h
0x140003bdf  movups  xmmword ptr [rcx], xmm0
0x140003be2  shr     r8, 1
0x140003be5  movups  xmmword ptr [r9], xmm0
0x140003be9  movups  xmmword ptr [rcx+r8], xmm0
0x140003bee  neg     r8
0x140003bf1  movups  xmmword ptr [r9+r8], xmm0
0x140003bf6  retn
0x140003c00  cmp     r8, 4
0x140003c04  jb      short loc_140003C30
0x140003c06  lea     r9, [r8+rcx-4]
0x140003c0b  and     r8, 8
0x140003c0f  mov     [rcx], edx
0x140003c11  shr     r8, 1
0x140003c14  mov     [r9], edx
0x140003c17  mov     [rcx+r8], edx
0x140003c1b  neg     r8
0x140003c1e  mov     [r9+r8], edx
0x140003c22  retn
0x140003c30  test    r8, r8
0x140003c33  jz      short locret_140003C46
0x140003c35  mov     [rcx], dl
0x140003c37  lea     r9, [rcx+r8-2]
0x140003c3c  cmp     r8, 1
0x140003c40  jz      short locret_140003C46
0x140003c42  mov     [r9], dx
0x140003c46  retn
```
