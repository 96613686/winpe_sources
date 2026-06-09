# memmove

- ea: `0x180024fb0`
- end: `0x18002562d`
- name: `memmove`
- size: `1661`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x1800037a0`
- `0x180004570`
- `0x180005240`
- `0x180006b60`
- `0x18000a120`
- `0x18000c1c0`
- `0x18000e820`
- `0x18000f2d0`
- `0x1800113a0`
- `0x180012fa4`
- `0x180014660`
- `0x180019794`
- `0x18001b0f0`
- `0x18001c26c`
- `0x18001e014`
- `0x18001e0dc`
- `0x18001edb0`
- `0x18001fb58`
- `0x180020a70`
- `0x180021778`
- `0x180021cbc`
- `0x1800222f0`
- `0x180022420`
- `0x180022608`
- `0x1800229a4`
- `0x180022fa8`
- `0x180023ac4`

## callees

- `0x180024f90`
- `0x180024fb0`

## pseudocode

```c
void *__cdecl memmove(void *_RCX, const void *Src, size_t Size)
{
  void *result; // rax
  int v4; // ecx
  __int16 v5; // r9
  char v6; // r10
  __int16 v7; // cx
  char v8; // r9
  __int16 v9; // r8
  char v10; // r9
  int v11; // ecx
  __int16 v12; // r9
  char v13; // r8
  int v14; // ecx
  char v15; // r9
  __int16 v16; // cx
  char v17; // cl
  int v18; // ecx
  __int16 v19; // r8
  char v20; // r8
  __m128i v21; // xmm2
  char *v22; // r9
  char *v23; // r9
  __int64 v26; // r9
  __m128i v59; // xmm0
  __m128i v60; // xmm5
  __int64 v61; // r9
  __m128i v62; // xmm2
  __m128i v63; // xmm3
  __m128i v64; // xmm4
  __m128i v65; // xmm2
  __m128i v66; // xmm3
  __m128i v67; // xmm4
  size_t v68; // r9
  __int128 v69; // xmm2
  signed __int64 v70; // rdx
  char *v71; // rcx
  __int128 v72; // xmm0
  unsigned __int64 v73; // rcx
  size_t v74; // r8
  _OWORD *v75; // r9
  __int128 v76; // xmm1
  size_t v77; // r9
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  size_t i; // r9

  result = _RCX;
  switch ( Size )
  {
    case 0uLL:
      return result;
    case 1uLL:
      *(_BYTE *)_RCX = *(_BYTE *)Src;
      return result;
    case 2uLL:
      *(_WORD *)_RCX = *(_WORD *)Src;
      return result;
    case 3uLL:
      v13 = *((_BYTE *)Src + 2);
      *(_WORD *)_RCX = *(_WORD *)Src;
      *((_BYTE *)_RCX + 2) = v13;
      return result;
    case 4uLL:
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      return result;
    case 5uLL:
      v20 = *((_BYTE *)Src + 4);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_BYTE *)_RCX + 4) = v20;
      return result;
    case 6uLL:
      v19 = *((_WORD *)Src + 2);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_WORD *)_RCX + 2) = v19;
      return result;
    case 7uLL:
      v9 = *((_WORD *)Src + 2);
      v10 = *((_BYTE *)Src + 6);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_WORD *)_RCX + 2) = v9;
      *((_BYTE *)_RCX + 6) = v10;
      return result;
    case 8uLL:
      *(_QWORD *)_RCX = *(_QWORD *)Src;
      return result;
    case 9uLL:
      v17 = *((_BYTE *)Src + 8);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_BYTE *)result + 8) = v17;
      return result;
    case 0xAuLL:
      v16 = *((_WORD *)Src + 4);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v16;
      return result;
    case 0xBuLL:
      v7 = *((_WORD *)Src + 4);
      v8 = *((_BYTE *)Src + 10);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v7;
      *((_BYTE *)result + 10) = v8;
      return result;
    case 0xCuLL:
      v18 = *((_DWORD *)Src + 2);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v18;
      return result;
    case 0xDuLL:
      v14 = *((_DWORD *)Src + 2);
      v15 = *((_BYTE *)Src + 12);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v14;
      *((_BYTE *)result + 12) = v15;
      return result;
    case 0xEuLL:
      v11 = *((_DWORD *)Src + 2);
      v12 = *((_WORD *)Src + 6);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v11;
      *((_WORD *)result + 6) = v12;
      return result;
    case 0xFuLL:
      v4 = *((_DWORD *)Src + 2);
      v5 = *((_WORD *)Src + 6);
      v6 = *((_BYTE *)Src + 14);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v4;
      *((_WORD *)result + 6) = v5;
      *((_BYTE *)result + 14) = v6;
      return result;
    default:
      if ( Size <= 0x20 )
      {
        v21 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
        *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
        *(__m128i *)((char *)_RCX + Size - 16) = v21;
        return result;
      }
      v22 = (char *)Src + Size;
      if ( _RCX <= Src )
        v22 = (char *)_RCX;
      if ( _RCX < v22 )
      {
        v69 = *(_OWORD *)Src;
        v70 = (_BYTE *)Src - (_BYTE *)_RCX;
        v71 = (char *)_RCX + Size;
        v72 = *(_OWORD *)&v71[v70 - 16];
        v73 = (unsigned __int64)(v71 - 16);
        v74 = Size - 16;
        if ( (v73 & 0xF) != 0 )
        {
          v75 = (_OWORD *)v73;
          v73 &= 0xFFFFFFFFFFFFFFF0uLL;
          v76 = v72;
          v72 = *(_OWORD *)(v73 + v70);
          *v75 = v76;
          v74 = v73 - (_QWORD)result;
        }
        v77 = v74 >> 7;
        if ( v74 >> 7 )
        {
          for ( *(_OWORD *)v73 = v72; ; *(_OWORD *)v73 = v83 )
          {
            v78 = *(_OWORD *)(v73 + v70 - 16);
            v79 = *(_OWORD *)(v73 + v70 - 32);
            v73 -= 128LL;
            *(_OWORD *)(v73 + 112) = v78;
            *(_OWORD *)(v73 + 96) = v79;
            v80 = *(_OWORD *)(v73 + v70 + 64);
            --v77;
            *(_OWORD *)(v73 + 80) = *(_OWORD *)(v73 + v70 + 80);
            *(_OWORD *)(v73 + 64) = v80;
            v81 = *(_OWORD *)(v73 + v70 + 32);
            *(_OWORD *)(v73 + 48) = *(_OWORD *)(v73 + v70 + 48);
            *(_OWORD *)(v73 + 32) = v81;
            v82 = *(_OWORD *)(v73 + v70 + 16);
            v83 = *(_OWORD *)(v73 + v70);
            if ( !v77 )
              break;
            *(_OWORD *)(v73 + 16) = v82;
          }
          *(_OWORD *)(v73 + 16) = v82;
          v74 &= 0x7Fu;
          v72 = v83;
        }
        for ( i = v74 >> 4; i; --i )
        {
          *(_OWORD *)v73 = v72;
          v73 -= 16LL;
          v72 = *(_OWORD *)(v73 + v70);
        }
        if ( (v74 & 0xF) != 0 )
          *(_OWORD *)result = v69;
        *(_OWORD *)v73 = v72;
        return result;
      }
      if ( (unsigned int)_isa_available < 3 )
      {
        if ( Size <= 0x800 || (_favor & 2) == 0 )
        {
          v59 = _mm_loadu_si128((const __m128i *)Src);
          v60 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
          if ( Size > 0x80 )
          {
            v61 = ((unsigned __int8)_RCX & 0xF) - 16LL;
            _RCX = (char *)_RCX - v61;
            Src = (char *)Src - v61;
            Size += v61;
            if ( Size > 0x80 )
            {
              do
              {
                v62 = _mm_loadu_si128((const __m128i *)Src + 1);
                v63 = _mm_loadu_si128((const __m128i *)Src + 2);
                v64 = _mm_loadu_si128((const __m128i *)Src + 3);
                *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
                *((__m128i *)_RCX + 1) = v62;
                *((__m128i *)_RCX + 2) = v63;
                *((__m128i *)_RCX + 3) = v64;
                v65 = _mm_loadu_si128((const __m128i *)Src + 5);
                v66 = _mm_loadu_si128((const __m128i *)Src + 6);
                v67 = _mm_loadu_si128((const __m128i *)Src + 7);
                *((__m128i *)_RCX + 4) = _mm_loadu_si128((const __m128i *)Src + 4);
                *((__m128i *)_RCX + 5) = v65;
                *((__m128i *)_RCX + 6) = v66;
                *((__m128i *)_RCX + 7) = v67;
                _RCX = (char *)_RCX + 128;
                Src = (char *)Src + 128;
                Size -= 128LL;
              }
              while ( Size >= 0x80 );
            }
          }
          v68 = (Size + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v68 >> 4 )
          {
            case 0uLL:
              goto LABEL_68;
            case 1uLL:
              goto LABEL_67;
            case 2uLL:
              goto LABEL_66;
            case 3uLL:
              goto LABEL_65;
            case 4uLL:
              goto LABEL_64;
            case 5uLL:
              goto LABEL_63;
            case 6uLL:
              goto LABEL_62;
            case 7uLL:
              goto LABEL_61;
            case 8uLL:
              *(__m128i *)((char *)_RCX + v68 - 128) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 128));
LABEL_61:
              *(__m128i *)((char *)_RCX + v68 - 112) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 112));
LABEL_62:
              *(__m128i *)((char *)_RCX + v68 - 96) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 96));
LABEL_63:
              *(__m128i *)((char *)_RCX + v68 - 80) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 80));
LABEL_64:
              *(__m128i *)((char *)_RCX + v68 - 64) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 64));
LABEL_65:
              *(__m128i *)((char *)_RCX + v68 - 48) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 48));
LABEL_66:
              *(__m128i *)((char *)_RCX + v68 - 32) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 32));
LABEL_67:
              *(__m128i *)((char *)_RCX + Size - 16) = v60;
LABEL_68:
              *(__m128i *)result = v59;
              break;
          }
          return result;
        }
        return (void *)memcpy_repmovs();
      }
      if ( Size > 0x2000 && Size <= 0x180000 )
      {
        v23 = (char *)_RCX + 64;
        if ( _RCX > Src )
          v23 = (char *)Src;
        if ( v23 <= Src && (_favor & 2) != 0 )
          return (void *)memcpy_repmovs();
      }
      __asm
      {
        vmovdqu ymm0, ymmword ptr [rdx]
        vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
      }
      if ( Size <= 0x100
        || (v26 = ((unsigned __int8)_RCX & 0x1F) - 32LL,
            _RCX = (char *)_RCX - v26,
            Src = (char *)Src - v26,
            Size += v26,
            Size <= 0x100) )
      {
LABEL_33:
        _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto LABEL_42;
          case 1uLL:
            goto LABEL_41;
          case 2uLL:
            goto LABEL_40;
          case 3uLL:
            goto LABEL_39;
          case 4uLL:
            goto LABEL_38;
          case 5uLL:
            goto LABEL_37;
          case 6uLL:
            goto LABEL_36;
          case 7uLL:
            goto LABEL_35;
          case 8uLL:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180025232 case 8
              vmovdqu ymmword ptr [rcx+r9-100h], ymm1
            }
LABEL_35:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180025232 case 7
              vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
            }
LABEL_36:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180025232 case 6
              vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
            }
LABEL_37:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180025232 case 5
              vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
            }
LABEL_38:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180025232 case 4
              vmovdqu ymmword ptr [rcx+r9-80h], ymm1
            }
LABEL_39:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180025232 case 3
              vmovdqu ymmword ptr [rcx+r9-60h], ymm1
            }
LABEL_40:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180025232 case 2
              vmovdqu ymmword ptr [rcx+r9-40h], ymm1
            }
LABEL_41:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180025232 case 1 }
LABEL_42:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180025232 case 0
              vzeroupper
            }
            break;
        }
        return result;
      }
      if ( Size <= 0x180000 )
      {
        do
        {
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx]
            vmovdqu ymm2, ymmword ptr [rdx+20h]
            vmovdqu ymm3, ymmword ptr [rdx+40h]
            vmovdqu ymm4, ymmword ptr [rdx+60h]
            vmovdqa ymmword ptr [rcx], ymm1
            vmovdqa ymmword ptr [rcx+20h], ymm2
            vmovdqa ymmword ptr [rcx+40h], ymm3
            vmovdqa ymmword ptr [rcx+60h], ymm4
            vmovdqu ymm1, ymmword ptr [rdx+80h]
            vmovdqu ymm2, ymmword ptr [rdx+0A0h]
            vmovdqu ymm3, ymmword ptr [rdx+0C0h]
            vmovdqu ymm4, ymmword ptr [rdx+0E0h]
            vmovdqa ymmword ptr [rcx+80h], ymm1
            vmovdqa ymmword ptr [rcx+0A0h], ymm2
            vmovdqa ymmword ptr [rcx+0C0h], ymm3
            vmovdqa ymmword ptr [rcx+0E0h], ymm4
          }
          _RCX = (char *)_RCX + 256;
          Src = (char *)Src + 256;
          Size -= 256LL;
        }
        while ( Size >= 0x100 );
        goto LABEL_33;
      }
      do
      {
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx]
          vmovdqu ymm2, ymmword ptr [rdx+20h]
          vmovdqu ymm3, ymmword ptr [rdx+40h]
          vmovdqu ymm4, ymmword ptr [rdx+60h]
          vmovntdq ymmword ptr [rcx], ymm1
          vmovntdq ymmword ptr [rcx+20h], ymm2
          vmovntdq ymmword ptr [rcx+40h], ymm3
          vmovntdq ymmword ptr [rcx+60h], ymm4
          vmovdqu ymm1, ymmword ptr [rdx+80h]
          vmovdqu ymm2, ymmword ptr [rdx+0A0h]
          vmovdqu ymm3, ymmword ptr [rdx+0C0h]
          vmovdqu ymm4, ymmword ptr [rdx+0E0h]
          vmovntdq ymmword ptr [rcx+80h], ymm1
          vmovntdq ymmword ptr [rcx+0A0h], ymm2
          vmovntdq ymmword ptr [rcx+0C0h], ymm3
          vmovntdq ymmword ptr [rcx+0E0h], ymm4
        }
        _RCX = (char *)_RCX + 256;
        Src = (char *)Src + 256;
        Size -= 256LL;
      }
      while ( Size >= 0x100 );
      _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
      switch ( _R9 >> 5 )
      {
        case 0uLL:
          goto LABEL_53;
        case 1uLL:
          goto LABEL_52;
        case 2uLL:
          goto LABEL_51;
        case 3uLL:
          goto LABEL_50;
        case 4uLL:
          goto LABEL_49;
        case 5uLL:
          goto LABEL_48;
        case 6uLL:
          goto LABEL_47;
        case 7uLL:
          goto LABEL_46;
        case 8uLL:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180025362 case 8
            vmovntdq ymmword ptr [rcx+r9-100h], ymm1
          }
LABEL_46:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180025362 case 7
            vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
          }
LABEL_47:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180025362 case 6
            vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
          }
LABEL_48:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180025362 case 5
            vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
          }
LABEL_49:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180025362 case 4
            vmovntdq ymmword ptr [rcx+r9-80h], ymm1
          }
LABEL_50:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180025362 case 3
            vmovntdq ymmword ptr [rcx+r9-60h], ymm1
          }
LABEL_51:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180025362 case 2
            vmovntdq ymmword ptr [rcx+r9-40h], ymm1
          }
LABEL_52:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180025362 case 1 }
LABEL_53:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180025362 case 0 }
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
0x180024fb0  mov     rax, rcx
0x180024fb3  lea     r10, __ImageBase
0x180024fba  cmp     r8, 0Fh; switch 16 cases
0x180024fbe  ja      def_180024FDB; jumptable 0000000180024FDB default case
0x180024fc4  nop     word ptr [rax+rax+00000000h]
0x180024fd0  mov     r9d, ds:(jpt_180024FDB - 180000000h)[r10+r8*4]
0x180024fd8  add     r9, r10
0x180024fdb  jmp     r9; switch jump
0x180024fde  retn; jumptable 0000000180024FDB case 0
0x180024fe0  mov     r8, [rdx]; jumptable 0000000180024FDB case 15
0x180024fe3  mov     ecx, [rdx+8]
0x180024fe6  movzx   r9d, word ptr [rdx+0Ch]
0x180024feb  movzx   r10d, byte ptr [rdx+0Eh]
0x180024ff0  mov     [rax], r8
0x180024ff3  mov     [rax+8], ecx
0x180024ff6  mov     [rax+0Ch], r9w
0x180024ffb  mov     [rax+0Eh], r10b
0x180024fff  retn
0x180025000  mov     r8, [rdx]; jumptable 0000000180024FDB case 11
0x180025003  movzx   ecx, word ptr [rdx+8]
0x180025007  movzx   r9d, byte ptr [rdx+0Ah]
0x18002500c  mov     [rax], r8
0x18002500f  mov     [rax+8], cx
0x180025013  mov     [rax+0Ah], r9b
0x180025017  retn
0x180025018  movzx   ecx, word ptr [rdx]; jumptable 0000000180024FDB case 2
0x18002501b  mov     [rax], cx
0x18002501e  retn
0x180025020  mov     ecx, [rdx]; jumptable 0000000180024FDB case 7
0x180025022  movzx   r8d, word ptr [rdx+4]
0x180025027  movzx   r9d, byte ptr [rdx+6]
0x18002502c  mov     [rax], ecx
0x18002502e  mov     [rax+4], r8w
0x180025033  mov     [rax+6], r9b
0x180025037  retn
0x180025038  mov     r8, [rdx]; jumptable 0000000180024FDB case 14
0x18002503b  mov     ecx, [rdx+8]
0x18002503e  movzx   r9d, word ptr [rdx+0Ch]
0x180025043  mov     [rax], r8
0x180025046  mov     [rax+8], ecx
0x180025049  mov     [rax+0Ch], r9w
0x18002504e  retn
0x18002504f  movzx   ecx, word ptr [rdx]; jumptable 0000000180024FDB case 3
0x180025052  movzx   r8d, byte ptr [rdx+2]
0x180025057  mov     [rax], cx
0x18002505a  mov     [rax+2], r8b
0x18002505e  retn
0x180025060  mov     r8, [rdx]; jumptable 0000000180024FDB case 13
0x180025063  mov     ecx, [rdx+8]
0x180025066  movzx   r9d, byte ptr [rdx+0Ch]
0x18002506b  mov     [rax], r8
0x18002506e  mov     [rax+8], ecx
0x180025071  mov     [rax+0Ch], r9b
0x180025075  retn
0x180025076  mov     r8, [rdx]; jumptable 0000000180024FDB case 10
0x180025079  movzx   ecx, word ptr [rdx+8]
0x18002507d  mov     [rax], r8
0x180025080  mov     [rax+8], cx
0x180025084  retn
0x180025085  mov     r8, [rdx]; jumptable 0000000180024FDB case 9
0x180025088  movzx   ecx, byte ptr [rdx+8]
0x18002508c  mov     [rax], r8
0x18002508f  mov     [rax+8], cl
0x180025092  retn
0x180025093  mov     r8, [rdx]; jumptable 0000000180024FDB case 12
0x180025096  mov     ecx, [rdx+8]
0x180025099  mov     [rax], r8
0x18002509c  mov     [rax+8], ecx
0x18002509f  retn
0x1800250a0  mov     ecx, [rdx]; jumptable 0000000180024FDB case 6
0x1800250a2  movzx   r8d, word ptr [rdx+4]
0x1800250a7  mov     [rax], ecx
0x1800250a9  mov     [rax+4], r8w
0x1800250ae  retn
0x1800250af  mov     ecx, [rdx]; jumptable 0000000180024FDB case 5
0x1800250b1  movzx   r8d, byte ptr [rdx+4]
0x1800250b6  mov     [rax], ecx
0x1800250b8  mov     [rax+4], r8b
0x1800250bc  retn
0x1800250bd  mov     rcx, [rdx]; jumptable 0000000180024FDB case 8
0x1800250c0  mov     [rax], rcx
0x1800250c3  retn
0x1800250c4  movzx   ecx, byte ptr [rdx]; jumptable 0000000180024FDB case 1
0x1800250c7  mov     [rax], cl
0x1800250c9  retn
0x1800250ca  mov     ecx, [rdx]; jumptable 0000000180024FDB case 4
0x1800250cc  mov     [rax], ecx
0x1800250ce  retn
0x1800250d0  cmp     r8, 20h ; ' '; jumptable 0000000180024FDB default case
0x1800250d4  ja      short loc_1800250ED
0x1800250d6  movdqu  xmm1, xmmword ptr [rdx]
0x1800250da  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x1800250e1  movdqu  xmmword ptr [rcx], xmm1
0x1800250e5  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x1800250ec  retn
0x1800250ed  lea     r9, [rdx+r8]
0x1800250f1  cmp     rcx, rdx
0x1800250f4  cmovbe  r9, rcx
0x1800250f8  cmp     rcx, r9
0x1800250fb  jb      loc_180025550
0x180025101  cmp     cs:__isa_available, 3
0x180025108  jb      loc_180025400
0x18002510e  cmp     r8, 2000h
0x180025115  jbe     short loc_18002513D
0x180025117  cmp     r8, 180000h
0x18002511e  ja      short loc_18002513D
0x180025120  lea     r9, [rcx+40h]
0x180025124  cmp     rcx, rdx
0x180025127  cmova   r9, rdx
0x18002512b  cmp     r9, rdx
0x18002512e  ja      short loc_18002513D
0x180025130  test    cs:__favor, 2
0x180025137  jnz     memcpy_repmovs
0x18002513d  vmovdqu ymm0, ymmword ptr [rdx]
0x180025141  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x180025148  cmp     r8, 100h
0x18002514f  jbe     loc_180025218
0x180025155  mov     r9, rcx
0x180025158  and     r9, 1Fh
0x18002515c  sub     r9, 20h ; ' '
0x180025160  sub     rcx, r9
0x180025163  sub     rdx, r9
0x180025166  add     r8, r9
0x180025169  cmp     r8, 100h
0x180025170  jbe     loc_180025218
0x180025176  cmp     r8, 180000h
0x18002517d  ja      loc_1800252C0
0x180025183  nop     word ptr [rax+rax+00000000h]
0x180025190  vmovdqu ymm1, ymmword ptr [rdx]
0x180025194  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x180025199  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18002519e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x1800251a3  vmovdqa ymmword ptr [rcx], ymm1
0x1800251a7  vmovdqa ymmword ptr [rcx+20h], ymm2
0x1800251ac  vmovdqa ymmword ptr [rcx+40h], ymm3
0x1800251b1  vmovdqa ymmword ptr [rcx+60h], ymm4
0x1800251b6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x1800251be  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x1800251c6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x1800251ce  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x1800251d6  vmovdqa ymmword ptr [rcx+80h], ymm1
0x1800251de  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x1800251e6  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x1800251ee  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x1800251f6  add     rcx, 100h
0x1800251fd  add     rdx, 100h
0x180025204  sub     r8, 100h
0x18002520b  cmp     r8, 100h
0x180025212  jnb     loc_180025190
0x180025218  lea     r9, [r8+1Fh]
0x18002521c  and     r9, 0FFFFFFFFFFFFFFE0h
0x180025220  mov     r11, r9
0x180025223  shr     r11, 5
0x180025227  mov     r11d, ds:(jpt_180025232 - 180000000h)[r10+r11*4]; switch 9 cases
0x18002522f  add     r11, r10
0x180025232  jmp     r11; switch jump
0x180025235  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180025232 case 8
0x18002523f  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x180025249  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180025232 case 7
0x180025253  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18002525d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180025232 case 6
0x180025267  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x180025271  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180025232 case 5
0x18002527b  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x180025285  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180025232 case 4
0x18002528c  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x180025293  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180025232 case 3
0x18002529a  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x1800252a1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180025232 case 2
0x1800252a8  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x1800252af  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180025232 case 1
0x1800252b6  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180025232 case 0
0x1800252ba  vzeroupper
0x1800252bd  retn
0x1800252c0  vmovdqu ymm1, ymmword ptr [rdx]
0x1800252c4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x1800252c9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x1800252ce  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x1800252d3  vmovntdq ymmword ptr [rcx], ymm1
0x1800252d7  vmovntdq ymmword ptr [rcx+20h], ymm2
0x1800252dc  vmovntdq ymmword ptr [rcx+40h], ymm3
0x1800252e1  vmovntdq ymmword ptr [rcx+60h], ymm4
0x1800252e6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x1800252ee  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x1800252f6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x1800252fe  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x180025306  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18002530e  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x180025316  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18002531e  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x180025326  add     rcx, 100h
0x18002532d  add     rdx, 100h
0x180025334  sub     r8, 100h
0x18002533b  cmp     r8, 100h
0x180025342  jnb     loc_1800252C0
0x180025348  lea     r9, [r8+1Fh]
0x18002534c  and     r9, 0FFFFFFFFFFFFFFE0h
0x180025350  mov     r11, r9
0x180025353  shr     r11, 5
0x180025357  mov     r11d, ds:(jpt_180025362 - 180000000h)[r10+r11*4]; switch 9 cases
0x18002535f  add     r11, r10
0x180025362  jmp     r11; switch jump
0x180025365  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180025362 case 8
0x18002536f  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x180025379  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180025362 case 7
0x180025383  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x18002538d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180025362 case 6
0x180025397  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x1800253a1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180025362 case 5
0x1800253ab  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x1800253b5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180025362 case 4
0x1800253bc  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x1800253c3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180025362 case 3
0x1800253ca  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x1800253d1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180025362 case 2
0x1800253d8  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x1800253df  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180025362 case 1
0x1800253e6  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180025362 case 0
0x1800253ea  sfence
0x1800253ed  vzeroupper
0x1800253f0  retn
0x180025400  cmp     r8, 800h
0x180025407  jbe     short loc_180025416
0x180025409  test    cs:__favor, 2
0x180025410  jnz     memcpy_repmovs
0x180025416  movdqu  xmm0, xmmword ptr [rdx]
0x18002541a  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x180025421  cmp     r8, 80h
0x180025428  jbe     loc_1800254BC
0x18002542e  mov     r9, rcx
0x180025431  and     r9, 0Fh
0x180025435  sub     r9, 10h
0x180025439  sub     rcx, r9
0x18002543c  sub     rdx, r9
0x18002543f  add     r8, r9
0x180025442  cmp     r8, 80h
0x180025449  jbe     short loc_1800254BC
0x18002544b  nop     dword ptr [rax+rax+00h]
0x180025450  movdqu  xmm1, xmmword ptr [rdx]
0x180025454  movdqu  xmm2, xmmword ptr [rdx+10h]
0x180025459  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18002545e  movdqu  xmm4, xmmword ptr [rdx+30h]
0x180025463  movdqa  xmmword ptr [rcx], xmm1
0x180025467  movdqa  xmmword ptr [rcx+10h], xmm2
0x18002546c  movdqa  xmmword ptr [rcx+20h], xmm3
0x180025471  movdqa  xmmword ptr [rcx+30h], xmm4
0x180025476  movdqu  xmm1, xmmword ptr [rdx+40h]
0x18002547b  movdqu  xmm2, xmmword ptr [rdx+50h]
0x180025480  movdqu  xmm3, xmmword ptr [rdx+60h]
0x180025485  movdqu  xmm4, xmmword ptr [rdx+70h]
0x18002548a  movdqa  xmmword ptr [rcx+40h], xmm1
0x18002548f  movdqa  xmmword ptr [rcx+50h], xmm2
0x180025494  movdqa  xmmword ptr [rcx+60h], xmm3
0x180025499  movdqa  xmmword ptr [rcx+70h], xmm4
0x18002549e  add     rcx, 80h
0x1800254a5  add     rdx, 80h
0x1800254ac  sub     r8, 80h
0x1800254b3  cmp     r8, 80h
0x1800254ba  jnb     short loc_180025450
0x1800254bc  lea     r9, [r8+0Fh]
0x1800254c0  and     r9, 0FFFFFFFFFFFFFFF0h
0x1800254c4  mov     r11, r9
0x1800254c7  shr     r11, 4
0x1800254cb  mov     r11d, ds:(jpt_1800254D6 - 180000000h)[r10+r11*4]; switch 9 cases
0x1800254d3  add     r11, r10
0x1800254d6  jmp     r11; switch jump
0x1800254d9  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 00000001800254D6 case 8
0x1800254e0  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x1800254e7  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 00000001800254D6 case 7
0x1800254ee  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x1800254f5  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 00000001800254D6 case 6
0x1800254fc  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x180025503  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 00000001800254D6 case 5
0x18002550a  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x180025511  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 00000001800254D6 case 4
0x180025518  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18002551f  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 00000001800254D6 case 3
0x180025526  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18002552d  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 00000001800254D6 case 2
0x180025534  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18002553b  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 00000001800254D6 case 1
0x180025542  movdqu  xmmword ptr [rax], xmm0; jumptable 00000001800254D6 case 0
0x180025546  retn
0x180025550  movups  xmm2, xmmword ptr [rdx]
0x180025553  sub     rdx, rcx
0x180025556  add     rcx, r8
0x180025559  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18002555e  sub     rcx, 10h
0x180025562  sub     r8, 10h
0x180025566  test    cl, 0Fh
0x180025569  jz      short loc_180025583
0x18002556b  mov     r9, rcx
0x18002556e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180025572  movups  xmm1, xmm0
0x180025575  movups  xmm0, xmmword ptr [rcx+rdx]
0x180025579  movups  xmmword ptr [r9], xmm1
0x18002557d  mov     r8, rcx
0x180025580  sub     r8, rax
0x180025583  mov     r9, r8
0x180025586  shr     r9, 7
  ... truncated ...
```
