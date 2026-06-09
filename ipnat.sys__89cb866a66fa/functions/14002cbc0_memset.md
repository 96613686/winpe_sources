# memset

- ea: `0x14002cbc0`
- end: `0x14002ccc7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x1400067d0`
- `0x1400078cc`
- `0x14000c49c`
- `0x14000cbec`
- `0x14000d8b0`
- `0x14000e868`
- `0x1400101b8`
- `0x140010404`
- `0x14001066c`
- `0x140011e00`
- `0x140014bac`
- `0x1400179cc`
- `0x1400196d4`
- `0x140020224`
- `0x140022320`
- `0x140024cc0`
- `0x14002863c`
- `0x140028c0c`
- `0x14002be04`
- `0x14002c034`
- `0x14002e020`
- `0x1400423d0`
- `0x140042f4c`
- `0x140043010`
- `0x1400431e8`
- `0x140043734`
- `0x14004419c`
- `0x140044310`
- `0x140045078`

## callees

- `0x14002cbc0`
- `0x14002cd00`

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
0x14002cbc0  mov     rax, rcx
0x14002cbc3  movzx   edx, dl
0x14002cbc6  mov     r9, 101010101010101h
0x14002cbd0  imul    rdx, r9
0x14002cbd4  movq    xmm0, rdx
0x14002cbd9  movlhps xmm0, xmm0
0x14002cbdc  cmp     r8, 40h ; '@'
0x14002cbe0  jb      short loc_14002CC50
0x14002cbe2  test    cs:__isa_info, 2
0x14002cbe9  jz      short loc_14002CBF8
0x14002cbeb  cmp     r8, 320h
0x14002cbf2  jnb     __memset_repmovs
0x14002cbf8  movups  xmmword ptr [rcx], xmm0
0x14002cbfb  add     r8, rcx
0x14002cbfe  add     rcx, 10h
0x14002cc02  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14002cc06  sub     r8, rcx
0x14002cc09  cmp     r8, 40h ; '@'
0x14002cc0d  jb      short loc_14002CC56
0x14002cc0f  lea     rdx, [rcx+r8-10h]
0x14002cc14  lea     r9, [rcx+r8-30h]
0x14002cc19  and     r9, 0FFFFFFFFFFFFFFF0h
0x14002cc1d  shr     r8, 6
0x14002cc21  movaps  xmmword ptr [rcx], xmm0
0x14002cc24  movaps  xmmword ptr [rcx+10h], xmm0
0x14002cc28  add     rcx, 40h ; '@'
0x14002cc2c  dec     r8
0x14002cc2f  movaps  xmmword ptr [rcx-20h], xmm0
0x14002cc33  movaps  xmmword ptr [rcx-10h], xmm0
0x14002cc37  jnz     short loc_14002CC21
0x14002cc39  movaps  xmmword ptr [r9], xmm0
0x14002cc3d  movaps  xmmword ptr [r9+10h], xmm0
0x14002cc42  movaps  xmmword ptr [r9+20h], xmm0
0x14002cc47  movups  xmmword ptr [rdx], xmm0
0x14002cc4a  retn
0x14002cc50  cmp     r8, 10h
0x14002cc54  jb      short loc_14002CC80
0x14002cc56  lea     r9, [r8+rcx-10h]
0x14002cc5b  and     r8, 20h
0x14002cc5f  movups  xmmword ptr [rcx], xmm0
0x14002cc62  shr     r8, 1
0x14002cc65  movups  xmmword ptr [r9], xmm0
0x14002cc69  movups  xmmword ptr [rcx+r8], xmm0
0x14002cc6e  neg     r8
0x14002cc71  movups  xmmword ptr [r9+r8], xmm0
0x14002cc76  retn
0x14002cc80  cmp     r8, 4
0x14002cc84  jb      short loc_14002CCB0
0x14002cc86  lea     r9, [r8+rcx-4]
0x14002cc8b  and     r8, 8
0x14002cc8f  mov     [rcx], edx
0x14002cc91  shr     r8, 1
0x14002cc94  mov     [r9], edx
0x14002cc97  mov     [rcx+r8], edx
0x14002cc9b  neg     r8
0x14002cc9e  mov     [r9+r8], edx
0x14002cca2  retn
0x14002ccb0  test    r8, r8
0x14002ccb3  jz      short locret_14002CCC6
0x14002ccb5  mov     [rcx], dl
0x14002ccb7  lea     r9, [rcx+r8-2]
0x14002ccbc  cmp     r8, 1
0x14002ccc0  jz      short locret_14002CCC6
0x14002ccc2  mov     [r9], dx
0x14002ccc6  retn
```
