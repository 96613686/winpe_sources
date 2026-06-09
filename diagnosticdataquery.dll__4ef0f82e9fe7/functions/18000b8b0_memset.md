# memset

- ea: `0x18000b8b0`
- end: `0x18000bc38`
- name: `memset`
- size: `904`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000562c`
- `0x18000589c`
- `0x180005b30`
- `0x1800060c8`
- `0x180006a04`
- `0x180007b90`
- `0x180007db0`
- `0x180008860`
- `0x180008b78`

## callees

- `0x18000b890`
- `0x18000b8b0`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v5; // r11
  char *v7; // rcx
  __m128i v8; // xmm0
  __int64 v10; // r9
  __int64 v15; // r9
  __m128i *v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r9

  result = a1;
  v5 = 0x101010101010101LL * (unsigned __int8)Val;
  v7 = (char *)a1 + Size;
  switch ( Size )
  {
    case 0uLL:
      return result;
    case 1uLL:
      goto LABEL_5;
    case 2uLL:
      goto LABEL_8;
    case 3uLL:
      goto LABEL_4;
    case 4uLL:
      goto LABEL_12;
    case 5uLL:
      goto LABEL_10;
    case 6uLL:
      goto LABEL_7;
    case 7uLL:
      goto LABEL_3;
    case 8uLL:
      *((_QWORD *)v7 - 1) = v5;
      return result;
    case 9uLL:
      *(_QWORD *)(v7 - 9) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xAuLL:
      *(_QWORD *)(v7 - 10) = v5;
      *((_WORD *)v7 - 1) = v5;
      return result;
    case 0xBuLL:
      *(_QWORD *)(v7 - 11) = v5;
      *(_WORD *)(v7 - 3) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xCuLL:
      *(_QWORD *)(v7 - 12) = v5;
LABEL_12:
      *((_DWORD *)v7 - 1) = v5;
      return result;
    case 0xDuLL:
      *(_QWORD *)(v7 - 13) = v5;
LABEL_10:
      *(_DWORD *)(v7 - 5) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xEuLL:
      *(_QWORD *)(v7 - 14) = v5;
LABEL_7:
      *(_DWORD *)(v7 - 6) = v5;
LABEL_8:
      *((_WORD *)v7 - 1) = v5;
      return result;
    case 0xFuLL:
      *(_QWORD *)(v7 - 15) = v5;
LABEL_3:
      *(_DWORD *)(v7 - 7) = v5;
LABEL_4:
      *(_WORD *)(v7 - 3) = v5;
LABEL_5:
      *(v7 - 1) = Val;
      return result;
    default:
      v8 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v5, (__m128i)(unsigned __int64)v5);
      if ( Size <= 0x20 )
      {
        *(__m128i *)a1 = v8;
        *(__m128i *)((char *)a1 + Size - 16) = v8;
        return result;
      }
      if ( (unsigned int)_isa_available < 3 )
      {
        if ( Size <= _memset_fast_string_threshold || (_favor & 2) == 0 )
        {
          v15 = ((unsigned __int8)a1 & 0xF) - 16LL;
          v16 = (__m128i *)((char *)a1 - v15);
          v17 = v15 + Size;
          if ( v17 > 0x80 )
          {
            do
            {
              *v16 = v8;
              v16[1] = v8;
              v16[2] = v8;
              v16[3] = v8;
              v16[4] = v8;
              v16[5] = v8;
              v16[6] = v8;
              v16[7] = v8;
              v16 += 8;
              v17 -= 128LL;
            }
            while ( v17 >= 0x80 );
          }
          v18 = (v17 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v18 >> 4 )
          {
            case 0uLL:
              goto LABEL_60;
            case 1uLL:
              goto LABEL_59;
            case 2uLL:
              goto LABEL_58;
            case 3uLL:
              goto LABEL_57;
            case 4uLL:
              goto LABEL_56;
            case 5uLL:
              goto LABEL_55;
            case 6uLL:
              goto LABEL_54;
            case 7uLL:
              goto LABEL_53;
            case 8uLL:
              *(__m128i *)((char *)&v16[-8] + v18) = v8;
LABEL_53:
              *(__m128i *)((char *)&v16[-7] + v18) = v8;
LABEL_54:
              *(__m128i *)((char *)&v16[-6] + v18) = v8;
LABEL_55:
              *(__m128i *)((char *)&v16[-5] + v18) = v8;
LABEL_56:
              *(__m128i *)((char *)&v16[-4] + v18) = v8;
LABEL_57:
              *(__m128i *)((char *)&v16[-3] + v18) = v8;
LABEL_58:
              *(__m128i *)((char *)&v16[-2] + v18) = v8;
LABEL_59:
              *(__m128i *)((char *)&v16[-1] + v17) = v8;
LABEL_60:
              *(__m128i *)result = v8;
              break;
          }
          return result;
        }
        return (void *)memset_repstos(a1);
      }
      if ( Size > _memset_fast_string_threshold && Size <= _memset_nt_threshold && (_favor & 2) != 0 )
        return (void *)memset_repstos(a1);
      __asm { vinsertf128 ymm0, ymm0, xmm0, 1 }
      v10 = ((unsigned __int8)a1 & 0x1F) - 32LL;
      _RCX = (char *)a1 - v10;
      _R8 = v10 + Size;
      if ( _R8 <= 0x100 )
        goto LABEL_26;
      if ( _R8 <= _memset_nt_threshold )
      {
        do
        {
          __asm
          {
            vmovdqa ymmword ptr [rcx], ymm0
            vmovdqa ymmword ptr [rcx+20h], ymm0
            vmovdqa ymmword ptr [rcx+40h], ymm0
            vmovdqa ymmword ptr [rcx+60h], ymm0
            vmovdqa ymmword ptr [rcx+80h], ymm0
            vmovdqa ymmword ptr [rcx+0A0h], ymm0
            vmovdqa ymmword ptr [rcx+0C0h], ymm0
            vmovdqa ymmword ptr [rcx+0E0h], ymm0
          }
          _RCX += 256;
          _R8 -= 256LL;
        }
        while ( _R8 >= 0x100 );
LABEL_26:
        _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto LABEL_35;
          case 1uLL:
            goto LABEL_34;
          case 2uLL:
            goto LABEL_33;
          case 3uLL:
            goto LABEL_32;
          case 4uLL:
            goto LABEL_31;
          case 5uLL:
            goto LABEL_30;
          case 6uLL:
            goto LABEL_29;
          case 7uLL:
            goto LABEL_28;
          case 8uLL:
            __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018000BA44 case 8 }
LABEL_28:
            __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018000BA44 case 7 }
LABEL_29:
            __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018000BA44 case 6 }
LABEL_30:
            __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018000BA44 case 5 }
LABEL_31:
            __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018000BA44 case 4 }
LABEL_32:
            __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018000BA44 case 3 }
LABEL_33:
            __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018000BA44 case 2 }
LABEL_34:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018000BA44 case 1 }
LABEL_35:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BA44 case 0
              vzeroupper
            }
            break;
        }
        return result;
      }
      do
      {
        __asm
        {
          vmovntdq ymmword ptr [rcx], ymm0
          vmovntdq ymmword ptr [rcx+20h], ymm0
          vmovntdq ymmword ptr [rcx+40h], ymm0
          vmovntdq ymmword ptr [rcx+60h], ymm0
          vmovntdq ymmword ptr [rcx+80h], ymm0
          vmovntdq ymmword ptr [rcx+0A0h], ymm0
          vmovntdq ymmword ptr [rcx+0C0h], ymm0
          vmovntdq ymmword ptr [rcx+0E0h], ymm0
        }
        _RCX += 256;
        _R8 -= 256LL;
      }
      while ( _R8 >= 0x100 );
      _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
      switch ( _R9 >> 5 )
      {
        case 0uLL:
          goto LABEL_46;
        case 1uLL:
          goto LABEL_45;
        case 2uLL:
          goto LABEL_44;
        case 3uLL:
          goto LABEL_43;
        case 4uLL:
          goto LABEL_42;
        case 5uLL:
          goto LABEL_41;
        case 6uLL:
          goto LABEL_40;
        case 7uLL:
          goto LABEL_39;
        case 8uLL:
          __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018000BB04 case 8 }
LABEL_39:
          __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018000BB04 case 7 }
LABEL_40:
          __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018000BB04 case 6 }
LABEL_41:
          __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018000BB04 case 5 }
LABEL_42:
          __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018000BB04 case 4 }
LABEL_43:
          __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018000BB04 case 3 }
LABEL_44:
          __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018000BB04 case 2 }
LABEL_45:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018000BB04 case 1 }
LABEL_46:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BB04 case 0 }
          _mm_sfence();
          __asm { vzeroupper }
          break;
      }
      return result;
  }
}

```

## disassembly

```asm
0x18000b8b0  mov     rax, rcx
0x18000b8b3  mov     r9, rcx
0x18000b8b6  lea     r10, cs:180000000h
0x18000b8bd  movzx   edx, dl
0x18000b8c0  mov     r11, 101010101010101h
0x18000b8ca  imul    r11, rdx
0x18000b8ce  movq    xmm0, r11
0x18000b8d3  cmp     r8, 0Fh; switch 16 cases
0x18000b8d7  ja      def_18000B8EE; jumptable 000000018000B8EE default case
0x18000b8dd  nop     dword ptr [rax]
0x18000b8e0  add     rcx, r8
0x18000b8e3  mov     r9d, ds:(jpt_18000B8EE - 180000000h)[r10+r8*4]
0x18000b8eb  add     r9, r10
0x18000b8ee  jmp     r9; switch jump
0x18000b8f1  mov     [rcx-0Fh], r11; jumptable 000000018000B8EE case 15
0x18000b8f5  mov     [rcx-7], r11d; jumptable 000000018000B8EE case 7
0x18000b8f9  mov     [rcx-3], r11w; jumptable 000000018000B8EE case 3
0x18000b8fe  mov     [rcx-1], r11b; jumptable 000000018000B8EE case 1
0x18000b902  retn; jumptable 000000018000B8EE case 0
0x18000b903  mov     [rcx-0Eh], r11; jumptable 000000018000B8EE case 14
0x18000b907  mov     [rcx-6], r11d; jumptable 000000018000B8EE case 6
0x18000b90b  mov     [rcx-2], r11w; jumptable 000000018000B8EE case 2
0x18000b910  retn
0x18000b920  mov     [rcx-0Dh], r11; jumptable 000000018000B8EE case 13
0x18000b924  mov     [rcx-5], r11d; jumptable 000000018000B8EE case 5
0x18000b928  mov     [rcx-1], r11b
0x18000b92c  retn
0x18000b930  mov     [rcx-0Ch], r11; jumptable 000000018000B8EE case 12
0x18000b934  mov     [rcx-4], r11d; jumptable 000000018000B8EE case 4
0x18000b938  retn
0x18000b939  mov     [rcx-0Bh], r11; jumptable 000000018000B8EE case 11
0x18000b93d  mov     [rcx-3], r11w
0x18000b942  mov     [rcx-1], r11b
0x18000b946  retn
0x18000b947  mov     [rcx-9], r11; jumptable 000000018000B8EE case 9
0x18000b94b  mov     [rcx-1], r11b
0x18000b94f  retn
0x18000b950  mov     [rcx-0Ah], r11; jumptable 000000018000B8EE case 10
0x18000b954  mov     [rcx-2], r11w
0x18000b959  retn
0x18000b95a  mov     [rcx-8], r11; jumptable 000000018000B8EE case 8
0x18000b95e  retn
0x18000b960  punpcklqdq xmm0, xmm0; jumptable 000000018000B8EE default case
0x18000b964  cmp     r8, 20h ; ' '
0x18000b968  ja      short loc_18000B976
0x18000b96a  movdqu  xmmword ptr [rcx], xmm0
0x18000b96e  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x18000b975  retn
0x18000b976  cmp     cs:__isa_available, 3
0x18000b97d  jb      loc_18000BB60
0x18000b983  cmp     r8, cs:__memset_fast_string_threshold
0x18000b98a  jbe     short loc_18000B9A2
0x18000b98c  cmp     r8, cs:__memset_nt_threshold
0x18000b993  ja      short loc_18000B9A2
0x18000b995  test    byte ptr cs:__favor, 2
0x18000b99c  jnz     memset_repstos
0x18000b9a2  vinsertf128 ymm0, ymm0, xmm0, 1
0x18000b9a8  mov     r9, rcx
0x18000b9ab  and     r9, 1Fh
0x18000b9af  sub     r9, 20h ; ' '
0x18000b9b3  sub     rcx, r9
0x18000b9b6  sub     rdx, r9
0x18000b9b9  add     r8, r9
0x18000b9bc  cmp     r8, 100h
0x18000b9c3  jbe     short loc_18000BA2A
0x18000b9c5  cmp     r8, cs:__memset_nt_threshold
0x18000b9cc  ja      loc_18000BAA0
0x18000b9d2  nop     word ptr [rax+rax+00000000h]
0x18000b9e0  vmovdqa ymmword ptr [rcx], ymm0
0x18000b9e4  vmovdqa ymmword ptr [rcx+20h], ymm0
0x18000b9e9  vmovdqa ymmword ptr [rcx+40h], ymm0
0x18000b9ee  vmovdqa ymmword ptr [rcx+60h], ymm0
0x18000b9f3  vmovdqa ymmword ptr [rcx+80h], ymm0
0x18000b9fb  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x18000ba03  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x18000ba0b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x18000ba13  add     rcx, 100h
0x18000ba1a  sub     r8, 100h
0x18000ba21  cmp     r8, 100h
0x18000ba28  jnb     short loc_18000B9E0
0x18000ba2a  lea     r9, [r8+1Fh]
0x18000ba2e  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000ba32  mov     r11, r9
0x18000ba35  shr     r11, 5
0x18000ba39  mov     r11d, ds:(jpt_18000BA44 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000ba41  add     r11, r10
0x18000ba44  jmp     r11; switch jump
0x18000ba47  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018000BA44 case 8
0x18000ba51  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018000BA44 case 7
0x18000ba5b  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018000BA44 case 6
0x18000ba65  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018000BA44 case 5
0x18000ba6f  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018000BA44 case 4
0x18000ba76  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018000BA44 case 3
0x18000ba7d  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018000BA44 case 2
0x18000ba84  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018000BA44 case 1
0x18000ba8b  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BA44 case 0
0x18000ba8f  vzeroupper
0x18000ba92  retn
0x18000baa0  vmovntdq ymmword ptr [rcx], ymm0
0x18000baa4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x18000baa9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x18000baae  vmovntdq ymmword ptr [rcx+60h], ymm0
0x18000bab3  vmovntdq ymmword ptr [rcx+80h], ymm0
0x18000babb  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x18000bac3  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x18000bacb  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x18000bad3  add     rcx, 100h
0x18000bada  sub     r8, 100h
0x18000bae1  cmp     r8, 100h
0x18000bae8  jnb     short loc_18000BAA0
0x18000baea  lea     r9, [r8+1Fh]
0x18000baee  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000baf2  mov     r11, r9
0x18000baf5  shr     r11, 5
0x18000baf9  mov     r11d, ds:(jpt_18000BB04 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000bb01  add     r11, r10
0x18000bb04  jmp     r11; switch jump
0x18000bb07  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018000BB04 case 8
0x18000bb11  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018000BB04 case 7
0x18000bb1b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018000BB04 case 6
0x18000bb25  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018000BB04 case 5
0x18000bb2f  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018000BB04 case 4
0x18000bb36  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018000BB04 case 3
0x18000bb3d  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018000BB04 case 2
0x18000bb44  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018000BB04 case 1
0x18000bb4b  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BB04 case 0
0x18000bb4f  sfence
0x18000bb52  vzeroupper
0x18000bb55  retn
0x18000bb60  cmp     r8, cs:__memset_fast_string_threshold
0x18000bb67  jbe     short loc_18000BB76
0x18000bb69  test    byte ptr cs:__favor, 2
0x18000bb70  jnz     memset_repstos
0x18000bb76  mov     r9, rcx
0x18000bb79  and     r9, 0Fh
0x18000bb7d  sub     r9, 10h
0x18000bb81  sub     rcx, r9
0x18000bb84  sub     rdx, r9
0x18000bb87  add     r8, r9
0x18000bb8a  cmp     r8, 80h
0x18000bb91  jbe     short loc_18000BBDE
0x18000bb93  nop     word ptr [rax+rax+00000000h]
0x18000bba0  movdqa  xmmword ptr [rcx], xmm0
0x18000bba4  movdqa  xmmword ptr [rcx+10h], xmm0
0x18000bba9  movdqa  xmmword ptr [rcx+20h], xmm0
0x18000bbae  movdqa  xmmword ptr [rcx+30h], xmm0
0x18000bbb3  movdqa  xmmword ptr [rcx+40h], xmm0
0x18000bbb8  movdqa  xmmword ptr [rcx+50h], xmm0
0x18000bbbd  movdqa  xmmword ptr [rcx+60h], xmm0
0x18000bbc2  movdqa  xmmword ptr [rcx+70h], xmm0
0x18000bbc7  add     rcx, 80h
0x18000bbce  sub     r8, 80h
0x18000bbd5  cmp     r8, 80h
0x18000bbdc  jnb     short loc_18000BBA0
0x18000bbde  lea     r9, [r8+0Fh]
0x18000bbe2  and     r9, 0FFFFFFFFFFFFFFF0h
0x18000bbe6  mov     r11, r9
0x18000bbe9  shr     r11, 4
0x18000bbed  mov     r11d, ds:(jpt_18000BBF8 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000bbf5  add     r11, r10
0x18000bbf8  jmp     r11; switch jump
0x18000bbfb  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 000000018000BBF8 case 8
0x18000bc02  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 000000018000BBF8 case 7
0x18000bc09  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 000000018000BBF8 case 6
0x18000bc10  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 000000018000BBF8 case 5
0x18000bc17  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 000000018000BBF8 case 4
0x18000bc1e  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 000000018000BBF8 case 3
0x18000bc25  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 000000018000BBF8 case 2
0x18000bc2c  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 000000018000BBF8 case 1
0x18000bc33  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018000BBF8 case 0
0x18000bc37  retn
```
