# memset

- ea: `0x14001fd40`
- end: `0x14001fe47`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140001460`
- `0x140002ec8`
- `0x1400060c4`
- `0x140008460`
- `0x14000a5f0`
- `0x14000d740`
- `0x14000d83c`
- `0x14000ef48`
- `0x14001f0e8`
- `0x14001f2f4`
- `0x14001f880`
- `0x140021020`
- `0x140032fb0`
- `0x140033b90`
- `0x140034a80`
- `0x140034e38`
- `0x140035ab8`
- `0x140037080`

## callees

- `0x14001fd40`
- `0x14001fe80`

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
0x14001fd40  mov     rax, rcx
0x14001fd43  movzx   edx, dl
0x14001fd46  mov     r9, 101010101010101h
0x14001fd50  imul    rdx, r9
0x14001fd54  movq    xmm0, rdx
0x14001fd59  movlhps xmm0, xmm0
0x14001fd5c  cmp     r8, 40h ; '@'
0x14001fd60  jb      short loc_14001FDD0
0x14001fd62  test    cs:__isa_info, 2
0x14001fd69  jz      short loc_14001FD78
0x14001fd6b  cmp     r8, 320h
0x14001fd72  jnb     __memset_repmovs
0x14001fd78  movups  xmmword ptr [rcx], xmm0
0x14001fd7b  add     r8, rcx
0x14001fd7e  add     rcx, 10h
0x14001fd82  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001fd86  sub     r8, rcx
0x14001fd89  cmp     r8, 40h ; '@'
0x14001fd8d  jb      short loc_14001FDD6
0x14001fd8f  lea     rdx, [rcx+r8-10h]
0x14001fd94  lea     r9, [rcx+r8-30h]
0x14001fd99  and     r9, 0FFFFFFFFFFFFFFF0h
0x14001fd9d  shr     r8, 6
0x14001fda1  movaps  xmmword ptr [rcx], xmm0
0x14001fda4  movaps  xmmword ptr [rcx+10h], xmm0
0x14001fda8  add     rcx, 40h ; '@'
0x14001fdac  dec     r8
0x14001fdaf  movaps  xmmword ptr [rcx-20h], xmm0
0x14001fdb3  movaps  xmmword ptr [rcx-10h], xmm0
0x14001fdb7  jnz     short loc_14001FDA1
0x14001fdb9  movaps  xmmword ptr [r9], xmm0
0x14001fdbd  movaps  xmmword ptr [r9+10h], xmm0
0x14001fdc2  movaps  xmmword ptr [r9+20h], xmm0
0x14001fdc7  movups  xmmword ptr [rdx], xmm0
0x14001fdca  retn
0x14001fdd0  cmp     r8, 10h
0x14001fdd4  jb      short loc_14001FE00
0x14001fdd6  lea     r9, [r8+rcx-10h]
0x14001fddb  and     r8, 20h
0x14001fddf  movups  xmmword ptr [rcx], xmm0
0x14001fde2  shr     r8, 1
0x14001fde5  movups  xmmword ptr [r9], xmm0
0x14001fde9  movups  xmmword ptr [rcx+r8], xmm0
0x14001fdee  neg     r8
0x14001fdf1  movups  xmmword ptr [r9+r8], xmm0
0x14001fdf6  retn
0x14001fe00  cmp     r8, 4
0x14001fe04  jb      short loc_14001FE30
0x14001fe06  lea     r9, [r8+rcx-4]
0x14001fe0b  and     r8, 8
0x14001fe0f  mov     [rcx], edx
0x14001fe11  shr     r8, 1
0x14001fe14  mov     [r9], edx
0x14001fe17  mov     [rcx+r8], edx
0x14001fe1b  neg     r8
0x14001fe1e  mov     [r9+r8], edx
0x14001fe22  retn
0x14001fe30  test    r8, r8
0x14001fe33  jz      short locret_14001FE46
0x14001fe35  mov     [rcx], dl
0x14001fe37  lea     r9, [rcx+r8-2]
0x14001fe3c  cmp     r8, 1
0x14001fe40  jz      short locret_14001FE46
0x14001fe42  mov     [r9], dx
0x14001fe46  retn
```
