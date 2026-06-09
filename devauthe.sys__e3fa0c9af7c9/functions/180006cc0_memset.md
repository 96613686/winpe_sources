# memset

- ea: `0x180006cc0`
- end: `0x180006dc7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180001020`
- `0x18000118c`
- `0x180001700`
- `0x180001980`
- `0x1800026e8`
- `0x180003320`
- `0x1800036a0`
- `0x1800037ac`
- `0x180003e20`
- `0x180004ccc`
- `0x180005020`
- `0x180008010`

## callees

- `0x180006cc0`
- `0x180006e00`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  size_t v9; // r8
  __m128 *v10; // r9
  size_t v11; // r8
  _DWORD *v12; // r9
  size_t v13; // r8

  result = a1;
  v4 = 0x101010101010101LL * (unsigned __int8)Val;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( Size >= 0x40 )
  {
    if ( (_isa_info & 2) != 0 && Size >= 0x320 )
      return (void *)_memset_repmovs();
    *(__m128 *)a1 = v5;
    v6 = (char *)a1 + Size;
    a1 = (void *)(((unsigned __int64)a1 + 16) & 0xFFFFFFFFFFFFFFF0uLL);
    Size = v6 - (_BYTE *)a1;
    if ( Size >= 0x40 )
    {
      v7 = (__m128 *)((char *)a1 + Size - 16);
      v8 = (_OWORD *)(((unsigned __int64)a1 + Size - 48) & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = Size >> 6;
      do
      {
        *(__m128 *)a1 = v5;
        *((__m128 *)a1 + 1) = v5;
        a1 = (char *)a1 + 64;
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
LABEL_9:
    v10 = (__m128 *)((char *)a1 + Size - 16);
    *(__m128 *)a1 = v5;
    v11 = (Size & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)((char *)a1 + v11) = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( Size >= 0x10 )
    goto LABEL_9;
  if ( Size < 4 )
  {
    if ( Size )
    {
      *(_BYTE *)a1 = v4;
      if ( Size != 1 )
        *(_WORD *)((char *)a1 + Size - 2) = v4;
    }
  }
  else
  {
    v12 = (char *)a1 + Size - 4;
    *(_DWORD *)a1 = v4;
    v13 = (Size & 8) >> 1;
    *v12 = v4;
    *(_DWORD *)((char *)a1 + v13) = v4;
    *(_DWORD *)((char *)v12 - v13) = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180006cc0  mov     rax, rcx
0x180006cc3  movzx   edx, dl
0x180006cc6  mov     r9, 101010101010101h
0x180006cd0  imul    rdx, r9
0x180006cd4  movq    xmm0, rdx
0x180006cd9  movlhps xmm0, xmm0
0x180006cdc  cmp     r8, 40h ; '@'
0x180006ce0  jb      short loc_180006D50
0x180006ce2  test    cs:__isa_info, 2
0x180006ce9  jz      short loc_180006CF8
0x180006ceb  cmp     r8, 320h
0x180006cf2  jnb     __memset_repmovs
0x180006cf8  movups  xmmword ptr [rcx], xmm0
0x180006cfb  add     r8, rcx
0x180006cfe  add     rcx, 10h
0x180006d02  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180006d06  sub     r8, rcx
0x180006d09  cmp     r8, 40h ; '@'
0x180006d0d  jb      short loc_180006D56
0x180006d0f  lea     rdx, [rcx+r8-10h]
0x180006d14  lea     r9, [rcx+r8-30h]
0x180006d19  and     r9, 0FFFFFFFFFFFFFFF0h
0x180006d1d  shr     r8, 6
0x180006d21  movaps  xmmword ptr [rcx], xmm0
0x180006d24  movaps  xmmword ptr [rcx+10h], xmm0
0x180006d28  add     rcx, 40h ; '@'
0x180006d2c  dec     r8
0x180006d2f  movaps  xmmword ptr [rcx-20h], xmm0
0x180006d33  movaps  xmmword ptr [rcx-10h], xmm0
0x180006d37  jnz     short loc_180006D21
0x180006d39  movaps  xmmword ptr [r9], xmm0
0x180006d3d  movaps  xmmword ptr [r9+10h], xmm0
0x180006d42  movaps  xmmword ptr [r9+20h], xmm0
0x180006d47  movups  xmmword ptr [rdx], xmm0
0x180006d4a  retn
0x180006d50  cmp     r8, 10h
0x180006d54  jb      short loc_180006D80
0x180006d56  lea     r9, [r8+rcx-10h]
0x180006d5b  and     r8, 20h
0x180006d5f  movups  xmmword ptr [rcx], xmm0
0x180006d62  shr     r8, 1
0x180006d65  movups  xmmword ptr [r9], xmm0
0x180006d69  movups  xmmword ptr [rcx+r8], xmm0
0x180006d6e  neg     r8
0x180006d71  movups  xmmword ptr [r9+r8], xmm0
0x180006d76  retn
0x180006d80  cmp     r8, 4
0x180006d84  jb      short loc_180006DB0
0x180006d86  lea     r9, [r8+rcx-4]
0x180006d8b  and     r8, 8
0x180006d8f  mov     [rcx], edx
0x180006d91  shr     r8, 1
0x180006d94  mov     [r9], edx
0x180006d97  mov     [rcx+r8], edx
0x180006d9b  neg     r8
0x180006d9e  mov     [r9+r8], edx
0x180006da2  retn
0x180006db0  test    r8, r8
0x180006db3  jz      short locret_180006DC6
0x180006db5  mov     [rcx], dl
0x180006db7  lea     r9, [rcx+r8-2]
0x180006dbc  cmp     r8, 1
0x180006dc0  jz      short locret_180006DC6
0x180006dc2  mov     [r9], dx
0x180006dc6  retn
```
