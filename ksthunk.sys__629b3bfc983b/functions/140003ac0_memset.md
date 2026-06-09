# memset

- ea: `0x140003ac0`
- end: `0x140003bc7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d90`
- `0x140001e00`
- `0x140002660`
- `0x140002dc8`
- `0x1400036e0`
- `0x140004050`
- `0x14000a6c0`
- `0x14000af44`
- `0x14000b064`

## callees

- `0x140003ac0`
- `0x140003c00`

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
0x140003ac0  mov     rax, rcx
0x140003ac3  movzx   edx, dl
0x140003ac6  mov     r9, 101010101010101h
0x140003ad0  imul    rdx, r9
0x140003ad4  movq    xmm0, rdx
0x140003ad9  movlhps xmm0, xmm0
0x140003adc  cmp     r8, 40h ; '@'
0x140003ae0  jb      short loc_140003B50
0x140003ae2  test    cs:__isa_info, 2
0x140003ae9  jz      short loc_140003AF8
0x140003aeb  cmp     r8, 320h
0x140003af2  jnb     __memset_repmovs
0x140003af8  movups  xmmword ptr [rcx], xmm0
0x140003afb  add     r8, rcx
0x140003afe  add     rcx, 10h
0x140003b02  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140003b06  sub     r8, rcx
0x140003b09  cmp     r8, 40h ; '@'
0x140003b0d  jb      short loc_140003B56
0x140003b0f  lea     rdx, [rcx+r8-10h]
0x140003b14  lea     r9, [rcx+r8-30h]
0x140003b19  and     r9, 0FFFFFFFFFFFFFFF0h
0x140003b1d  shr     r8, 6
0x140003b21  movaps  xmmword ptr [rcx], xmm0
0x140003b24  movaps  xmmword ptr [rcx+10h], xmm0
0x140003b28  add     rcx, 40h ; '@'
0x140003b2c  dec     r8
0x140003b2f  movaps  xmmword ptr [rcx-20h], xmm0
0x140003b33  movaps  xmmword ptr [rcx-10h], xmm0
0x140003b37  jnz     short loc_140003B21
0x140003b39  movaps  xmmword ptr [r9], xmm0
0x140003b3d  movaps  xmmword ptr [r9+10h], xmm0
0x140003b42  movaps  xmmword ptr [r9+20h], xmm0
0x140003b47  movups  xmmword ptr [rdx], xmm0
0x140003b4a  retn
0x140003b50  cmp     r8, 10h
0x140003b54  jb      short loc_140003B80
0x140003b56  lea     r9, [r8+rcx-10h]
0x140003b5b  and     r8, 20h
0x140003b5f  movups  xmmword ptr [rcx], xmm0
0x140003b62  shr     r8, 1
0x140003b65  movups  xmmword ptr [r9], xmm0
0x140003b69  movups  xmmword ptr [rcx+r8], xmm0
0x140003b6e  neg     r8
0x140003b71  movups  xmmword ptr [r9+r8], xmm0
0x140003b76  retn
0x140003b80  cmp     r8, 4
0x140003b84  jb      short loc_140003BB0
0x140003b86  lea     r9, [r8+rcx-4]
0x140003b8b  and     r8, 8
0x140003b8f  mov     [rcx], edx
0x140003b91  shr     r8, 1
0x140003b94  mov     [r9], edx
0x140003b97  mov     [rcx+r8], edx
0x140003b9b  neg     r8
0x140003b9e  mov     [r9+r8], edx
0x140003ba2  retn
0x140003bb0  test    r8, r8
0x140003bb3  jz      short locret_140003BC6
0x140003bb5  mov     [rcx], dl
0x140003bb7  lea     r9, [rcx+r8-2]
0x140003bbc  cmp     r8, 1
0x140003bc0  jz      short locret_140003BC6
0x140003bc2  mov     [r9], dx
0x140003bc6  retn
```
