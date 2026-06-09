# __memset_spec_plain

- ea: `0x1400019c0`
- end: `0x140001ab7`
- name: `__memset_spec_plain`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400019c0`

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
0x1400019c0  mov     rax, rcx
0x1400019c3  movzx   edx, dl
0x1400019c6  mov     r9, 101010101010101h
0x1400019d0  imul    rdx, r9
0x1400019d4  movq    xmm0, rdx
0x1400019d9  movlhps xmm0, xmm0
0x1400019dc  cmp     r8, 40h ; '@'
0x1400019e0  jb      short loc_140001A40
0x1400019e2  movups  xmmword ptr [rcx], xmm0
0x1400019e5  add     r8, rcx
0x1400019e8  add     rcx, 10h
0x1400019ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400019f0  sub     r8, rcx
0x1400019f3  cmp     r8, 40h ; '@'
0x1400019f7  jb      short loc_140001A46
0x1400019f9  lea     rdx, [rcx+r8-10h]
0x1400019fe  lea     r9, [rcx+r8-30h]
0x140001a03  and     r9, 0FFFFFFFFFFFFFFF0h
0x140001a07  shr     r8, 6
0x140001a0b  movaps  xmmword ptr [rcx], xmm0
0x140001a0e  movaps  xmmword ptr [rcx+10h], xmm0
0x140001a12  add     rcx, 40h ; '@'
0x140001a16  dec     r8
0x140001a19  movaps  xmmword ptr [rcx-20h], xmm0
0x140001a1d  movaps  xmmword ptr [rcx-10h], xmm0
0x140001a21  jnz     short loc_140001A0B
0x140001a23  movaps  xmmword ptr [r9], xmm0
0x140001a27  movaps  xmmword ptr [r9+10h], xmm0
0x140001a2c  movaps  xmmword ptr [r9+20h], xmm0
0x140001a31  movups  xmmword ptr [rdx], xmm0
0x140001a34  retn
0x140001a40  cmp     r8, 10h
0x140001a44  jb      short loc_140001A70
0x140001a46  lea     r9, [r8+rcx-10h]
0x140001a4b  and     r8, 20h
0x140001a4f  movups  xmmword ptr [rcx], xmm0
0x140001a52  shr     r8, 1
0x140001a55  movups  xmmword ptr [r9], xmm0
0x140001a59  movups  xmmword ptr [rcx+r8], xmm0
0x140001a5e  neg     r8
0x140001a61  movups  xmmword ptr [r9+r8], xmm0
0x140001a66  retn
0x140001a70  cmp     r8, 4
0x140001a74  jb      short loc_140001AA0
0x140001a76  lea     r9, [r8+rcx-4]
0x140001a7b  and     r8, 8
0x140001a7f  mov     [rcx], edx
0x140001a81  shr     r8, 1
0x140001a84  mov     [r9], edx
0x140001a87  mov     [rcx+r8], edx
0x140001a8b  neg     r8
0x140001a8e  mov     [r9+r8], edx
0x140001a92  retn
0x140001aa0  test    r8, r8
0x140001aa3  jz      short locret_140001AB6
0x140001aa5  mov     [rcx], dl
0x140001aa7  lea     r9, [rcx+r8-2]
0x140001aac  cmp     r8, 1
0x140001ab0  jz      short locret_140001AB6
0x140001ab2  mov     [r9], dx
0x140001ab6  retn
```
