# memset

- ea: `0x14000c4c0`
- end: `0x14000c5c7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001714`
- `0x14000440c`
- `0x140004690`
- `0x140005d74`
- `0x1400065fc`
- `0x14000d020`
- `0x140020124`
- `0x140025610`
- `0x140025a80`
- `0x140026330`

## callees

- `0x14000c4c0`
- `0x14000c600`

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
      return (void *)_memset_repmovs(a1, v4, Size);
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
0x14000c4c0  mov     rax, rcx
0x14000c4c3  movzx   edx, dl
0x14000c4c6  mov     r9, 101010101010101h
0x14000c4d0  imul    rdx, r9
0x14000c4d4  movq    xmm0, rdx
0x14000c4d9  movlhps xmm0, xmm0
0x14000c4dc  cmp     r8, 40h ; '@'
0x14000c4e0  jb      short loc_14000C550
0x14000c4e2  test    cs:__isa_info, 2
0x14000c4e9  jz      short loc_14000C4F8
0x14000c4eb  cmp     r8, 320h
0x14000c4f2  jnb     __memset_repmovs
0x14000c4f8  movups  xmmword ptr [rcx], xmm0
0x14000c4fb  add     r8, rcx
0x14000c4fe  add     rcx, 10h
0x14000c502  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000c506  sub     r8, rcx
0x14000c509  cmp     r8, 40h ; '@'
0x14000c50d  jb      short loc_14000C556
0x14000c50f  lea     rdx, [rcx+r8-10h]
0x14000c514  lea     r9, [rcx+r8-30h]
0x14000c519  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000c51d  shr     r8, 6
0x14000c521  movaps  xmmword ptr [rcx], xmm0
0x14000c524  movaps  xmmword ptr [rcx+10h], xmm0
0x14000c528  add     rcx, 40h ; '@'
0x14000c52c  dec     r8
0x14000c52f  movaps  xmmword ptr [rcx-20h], xmm0
0x14000c533  movaps  xmmword ptr [rcx-10h], xmm0
0x14000c537  jnz     short loc_14000C521
0x14000c539  movaps  xmmword ptr [r9], xmm0
0x14000c53d  movaps  xmmword ptr [r9+10h], xmm0
0x14000c542  movaps  xmmword ptr [r9+20h], xmm0
0x14000c547  movups  xmmword ptr [rdx], xmm0
0x14000c54a  retn
0x14000c550  cmp     r8, 10h
0x14000c554  jb      short loc_14000C580
0x14000c556  lea     r9, [r8+rcx-10h]
0x14000c55b  and     r8, 20h
0x14000c55f  movups  xmmword ptr [rcx], xmm0
0x14000c562  shr     r8, 1
0x14000c565  movups  xmmword ptr [r9], xmm0
0x14000c569  movups  xmmword ptr [rcx+r8], xmm0
0x14000c56e  neg     r8
0x14000c571  movups  xmmword ptr [r9+r8], xmm0
0x14000c576  retn
0x14000c580  cmp     r8, 4
0x14000c584  jb      short loc_14000C5B0
0x14000c586  lea     r9, [r8+rcx-4]
0x14000c58b  and     r8, 8
0x14000c58f  mov     [rcx], edx
0x14000c591  shr     r8, 1
0x14000c594  mov     [r9], edx
0x14000c597  mov     [rcx+r8], edx
0x14000c59b  neg     r8
0x14000c59e  mov     [r9+r8], edx
0x14000c5a2  retn
0x14000c5b0  test    r8, r8
0x14000c5b3  jz      short locret_14000C5C6
0x14000c5b5  mov     [rcx], dl
0x14000c5b7  lea     r9, [rcx+r8-2]
0x14000c5bc  cmp     r8, 1
0x14000c5c0  jz      short locret_14000C5C6
0x14000c5c2  mov     [r9], dx
0x14000c5c6  retn
```
