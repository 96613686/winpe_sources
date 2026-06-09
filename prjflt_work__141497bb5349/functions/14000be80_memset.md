# memset

- ea: `0x14000be80`
- end: `0x14000bf87`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x140001658`
- `0x140001b3c`
- `0x1400047cc`
- `0x14000500c`
- `0x140007694`
- `0x140007990`
- `0x140009880`
- `0x14000a69c`
- `0x14000ba70`
- `0x140014090`
- `0x140021c5c`
- `0x140023470`
- `0x1400249dc`
- `0x140028464`
- `0x140032fd8`
- `0x140034428`
- `0x1400346f0`
- `0x1400349fc`
- `0x140035060`
- `0x140035238`
- `0x140037b8c`
- `0x140038f1c`
- `0x14003f240`
- `0x140040670`
- `0x1400422ec`
- `0x140045c88`
- `0x140045d4c`
- `0x140045f24`
- `0x140046470`
- `0x1400466bc`

## callees

- `0x14000be80`
- `0x14000bfc0`

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
0x14000be80  mov     rax, rcx
0x14000be83  movzx   edx, dl
0x14000be86  mov     r9, 101010101010101h
0x14000be90  imul    rdx, r9
0x14000be94  movq    xmm0, rdx
0x14000be99  movlhps xmm0, xmm0
0x14000be9c  cmp     r8, 40h ; '@'
0x14000bea0  jb      short loc_14000BF10
0x14000bea2  test    cs:__isa_info, 2
0x14000bea9  jz      short loc_14000BEB8
0x14000beab  cmp     r8, 320h
0x14000beb2  jnb     __memset_repmovs
0x14000beb8  movups  xmmword ptr [rcx], xmm0
0x14000bebb  add     r8, rcx
0x14000bebe  add     rcx, 10h
0x14000bec2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000bec6  sub     r8, rcx
0x14000bec9  cmp     r8, 40h ; '@'
0x14000becd  jb      short loc_14000BF16
0x14000becf  lea     rdx, [rcx+r8-10h]
0x14000bed4  lea     r9, [rcx+r8-30h]
0x14000bed9  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000bedd  shr     r8, 6
0x14000bee1  movaps  xmmword ptr [rcx], xmm0
0x14000bee4  movaps  xmmword ptr [rcx+10h], xmm0
0x14000bee8  add     rcx, 40h ; '@'
0x14000beec  dec     r8
0x14000beef  movaps  xmmword ptr [rcx-20h], xmm0
0x14000bef3  movaps  xmmword ptr [rcx-10h], xmm0
0x14000bef7  jnz     short loc_14000BEE1
0x14000bef9  movaps  xmmword ptr [r9], xmm0
0x14000befd  movaps  xmmword ptr [r9+10h], xmm0
0x14000bf02  movaps  xmmword ptr [r9+20h], xmm0
0x14000bf07  movups  xmmword ptr [rdx], xmm0
0x14000bf0a  retn
0x14000bf10  cmp     r8, 10h
0x14000bf14  jb      short loc_14000BF40
0x14000bf16  lea     r9, [r8+rcx-10h]
0x14000bf1b  and     r8, 20h
0x14000bf1f  movups  xmmword ptr [rcx], xmm0
0x14000bf22  shr     r8, 1
0x14000bf25  movups  xmmword ptr [r9], xmm0
0x14000bf29  movups  xmmword ptr [rcx+r8], xmm0
0x14000bf2e  neg     r8
0x14000bf31  movups  xmmword ptr [r9+r8], xmm0
0x14000bf36  retn
0x14000bf40  cmp     r8, 4
0x14000bf44  jb      short loc_14000BF70
0x14000bf46  lea     r9, [r8+rcx-4]
0x14000bf4b  and     r8, 8
0x14000bf4f  mov     [rcx], edx
0x14000bf51  shr     r8, 1
0x14000bf54  mov     [r9], edx
0x14000bf57  mov     [rcx+r8], edx
0x14000bf5b  neg     r8
0x14000bf5e  mov     [r9+r8], edx
0x14000bf62  retn
0x14000bf70  test    r8, r8
0x14000bf73  jz      short locret_14000BF86
0x14000bf75  mov     [rcx], dl
0x14000bf77  lea     r9, [rcx+r8-2]
0x14000bf7c  cmp     r8, 1
0x14000bf80  jz      short locret_14000BF86
0x14000bf82  mov     [r9], dx
0x14000bf86  retn
```
