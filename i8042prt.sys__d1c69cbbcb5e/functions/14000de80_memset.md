# memset

- ea: `0x14000de80`
- end: `0x14000df87`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f020`
- `0x1400178b0`
- `0x1400183a4`
- `0x140018bf0`
- `0x14001c590`
- `0x14001c808`
- `0x140021078`

## callees

- `0x14000de80`
- `0x14000dfc0`

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
0x14000de80  mov     rax, rcx
0x14000de83  movzx   edx, dl
0x14000de86  mov     r9, 101010101010101h
0x14000de90  imul    rdx, r9
0x14000de94  movq    xmm0, rdx
0x14000de99  movlhps xmm0, xmm0
0x14000de9c  cmp     r8, 40h ; '@'
0x14000dea0  jb      short loc_14000DF10
0x14000dea2  test    cs:__isa_info, 2
0x14000dea9  jz      short loc_14000DEB8
0x14000deab  cmp     r8, 320h
0x14000deb2  jnb     __memset_repmovs
0x14000deb8  movups  xmmword ptr [rcx], xmm0
0x14000debb  add     r8, rcx
0x14000debe  add     rcx, 10h
0x14000dec2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000dec6  sub     r8, rcx
0x14000dec9  cmp     r8, 40h ; '@'
0x14000decd  jb      short loc_14000DF16
0x14000decf  lea     rdx, [rcx+r8-10h]
0x14000ded4  lea     r9, [rcx+r8-30h]
0x14000ded9  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000dedd  shr     r8, 6
0x14000dee1  movaps  xmmword ptr [rcx], xmm0
0x14000dee4  movaps  xmmword ptr [rcx+10h], xmm0
0x14000dee8  add     rcx, 40h ; '@'
0x14000deec  dec     r8
0x14000deef  movaps  xmmword ptr [rcx-20h], xmm0
0x14000def3  movaps  xmmword ptr [rcx-10h], xmm0
0x14000def7  jnz     short loc_14000DEE1
0x14000def9  movaps  xmmword ptr [r9], xmm0
0x14000defd  movaps  xmmword ptr [r9+10h], xmm0
0x14000df02  movaps  xmmword ptr [r9+20h], xmm0
0x14000df07  movups  xmmword ptr [rdx], xmm0
0x14000df0a  retn
0x14000df10  cmp     r8, 10h
0x14000df14  jb      short loc_14000DF40
0x14000df16  lea     r9, [r8+rcx-10h]
0x14000df1b  and     r8, 20h
0x14000df1f  movups  xmmword ptr [rcx], xmm0
0x14000df22  shr     r8, 1
0x14000df25  movups  xmmword ptr [r9], xmm0
0x14000df29  movups  xmmword ptr [rcx+r8], xmm0
0x14000df2e  neg     r8
0x14000df31  movups  xmmword ptr [r9+r8], xmm0
0x14000df36  retn
0x14000df40  cmp     r8, 4
0x14000df44  jb      short loc_14000DF70
0x14000df46  lea     r9, [r8+rcx-4]
0x14000df4b  and     r8, 8
0x14000df4f  mov     [rcx], edx
0x14000df51  shr     r8, 1
0x14000df54  mov     [r9], edx
0x14000df57  mov     [rcx+r8], edx
0x14000df5b  neg     r8
0x14000df5e  mov     [r9+r8], edx
0x14000df62  retn
0x14000df70  test    r8, r8
0x14000df73  jz      short locret_14000DF86
0x14000df75  mov     [rcx], dl
0x14000df77  lea     r9, [rcx+r8-2]
0x14000df7c  cmp     r8, 1
0x14000df80  jz      short locret_14000DF86
0x14000df82  mov     [r9], dx
0x14000df86  retn
```
