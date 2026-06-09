# memset

- ea: `0x14003b0c0`
- end: `0x14003b1c7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `60`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f10`
- `0x1400029d0`
- `0x140005de0`
- `0x1400081f0`
- `0x140009f60`
- `0x14000adb0`
- `0x14000fa80`
- `0x140010870`
- `0x140014d04`
- `0x140014d98`
- `0x1400150f0`
- `0x140015b48`
- `0x140016380`
- `0x14001643c`
- `0x140016cb8`
- `0x14001a688`
- `0x14001add0`
- `0x14001d6b0`
- `0x14001e69c`
- `0x14001ea54`
- `0x14001f178`
- `0x14001f904`
- `0x14001fe8c`
- `0x140020508`
- `0x140020884`
- `0x140020fa8`
- `0x1400219e8`
- `0x140022054`
- `0x14002246c`
- `0x140022c5c`
- `0x14002372c`
- `0x140023dd0`
- `0x140024720`
- `0x140024c60`
- `0x140025484`
- `0x140025be0`
- `0x1400273f0`
- `0x140028870`
- `0x140028d14`
- `0x140029290`
- `0x140029e34`
- `0x14002a518`
- `0x14002a5f0`
- `0x14002b82c`
- `0x14002b8f8`
- `0x14002c4c4`
- `0x14002fa64`
- `0x1400316d0`
- `0x140035384`
- `0x14003677c`

## callees

- `0x14003b0c0`
- `0x14003b200`

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
0x14003b0c0  mov     rax, rcx
0x14003b0c3  movzx   edx, dl
0x14003b0c6  mov     r9, 101010101010101h
0x14003b0d0  imul    rdx, r9
0x14003b0d4  movq    xmm0, rdx
0x14003b0d9  movlhps xmm0, xmm0
0x14003b0dc  cmp     r8, 40h ; '@'
0x14003b0e0  jb      short loc_14003B150
0x14003b0e2  test    cs:__isa_info, 2
0x14003b0e9  jz      short loc_14003B0F8
0x14003b0eb  cmp     r8, 320h
0x14003b0f2  jnb     __memset_repmovs
0x14003b0f8  movups  xmmword ptr [rcx], xmm0
0x14003b0fb  add     r8, rcx
0x14003b0fe  add     rcx, 10h
0x14003b102  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14003b106  sub     r8, rcx
0x14003b109  cmp     r8, 40h ; '@'
0x14003b10d  jb      short loc_14003B156
0x14003b10f  lea     rdx, [rcx+r8-10h]
0x14003b114  lea     r9, [rcx+r8-30h]
0x14003b119  and     r9, 0FFFFFFFFFFFFFFF0h
0x14003b11d  shr     r8, 6
0x14003b121  movaps  xmmword ptr [rcx], xmm0
0x14003b124  movaps  xmmword ptr [rcx+10h], xmm0
0x14003b128  add     rcx, 40h ; '@'
0x14003b12c  dec     r8
0x14003b12f  movaps  xmmword ptr [rcx-20h], xmm0
0x14003b133  movaps  xmmword ptr [rcx-10h], xmm0
0x14003b137  jnz     short loc_14003B121
0x14003b139  movaps  xmmword ptr [r9], xmm0
0x14003b13d  movaps  xmmword ptr [r9+10h], xmm0
0x14003b142  movaps  xmmword ptr [r9+20h], xmm0
0x14003b147  movups  xmmword ptr [rdx], xmm0
0x14003b14a  retn
0x14003b150  cmp     r8, 10h
0x14003b154  jb      short loc_14003B180
0x14003b156  lea     r9, [r8+rcx-10h]
0x14003b15b  and     r8, 20h
0x14003b15f  movups  xmmword ptr [rcx], xmm0
0x14003b162  shr     r8, 1
0x14003b165  movups  xmmword ptr [r9], xmm0
0x14003b169  movups  xmmword ptr [rcx+r8], xmm0
0x14003b16e  neg     r8
0x14003b171  movups  xmmword ptr [r9+r8], xmm0
0x14003b176  retn
0x14003b180  cmp     r8, 4
0x14003b184  jb      short loc_14003B1B0
0x14003b186  lea     r9, [r8+rcx-4]
0x14003b18b  and     r8, 8
0x14003b18f  mov     [rcx], edx
0x14003b191  shr     r8, 1
0x14003b194  mov     [r9], edx
0x14003b197  mov     [rcx+r8], edx
0x14003b19b  neg     r8
0x14003b19e  mov     [r9+r8], edx
0x14003b1a2  retn
0x14003b1b0  test    r8, r8
0x14003b1b3  jz      short locret_14003B1C6
0x14003b1b5  mov     [rcx], dl
0x14003b1b7  lea     r9, [rcx+r8-2]
0x14003b1bc  cmp     r8, 1
0x14003b1c0  jz      short locret_14003B1C6
0x14003b1c2  mov     [r9], dx
0x14003b1c6  retn
```
