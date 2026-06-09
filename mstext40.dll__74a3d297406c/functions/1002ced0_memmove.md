# _memmove

- ea: `0x1002ced0`
- end: `0x1002d514`
- name: `_memmove`
- size: `1604`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x10028bb0`
- `0x1002fbd0`
- `0x10030225`
- `0x100334b0`

## callees

- `0x1002ced0`

## pseudocode

```c
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  const __m128i *v3; // esi
  signed int v4; // ecx
  __m128i *v5; // edi
  __int64 v6; // xmm1_8
  __m128i si128; // xmm1
  const __m128i *v8; // esi
  __m128i v9; // xmm3
  __m128i v10; // xmm0
  __m128i v11; // xmm5
  __m128i v12; // xmm1
  const __m128i *v13; // esi
  __m128i v14; // xmm3
  __m128i v15; // xmm0
  __m128i v16; // xmm5
  __m128i v17; // xmm1
  const __m128i *v18; // esi
  __m128i v19; // xmm3
  __m128i v20; // xmm0
  __m128i v21; // xmm5
  __m128i v22; // xmm1
  __int32 v23; // eax
  __int64 v24; // xmm1_8
  size_t v25; // ecx
  void *result; // eax
  char *v27; // esi
  char *v28; // edi
  size_t v29; // ecx
  int v30; // eax
  unsigned int v31; // edx
  unsigned int v32; // ecx
  unsigned int j; // edx
  __m128i v34; // xmm1
  __m128i v35; // xmm2
  __m128i v36; // xmm3
  __m128i v37; // xmm5
  __m128i v38; // xmm6
  __m128i v39; // xmm7
  unsigned int k; // edx
  unsigned int v41; // ecx
  char v42; // al
  unsigned int m; // ecx
  int v44; // ecx
  unsigned int v45; // eax
  int v46; // ecx
  unsigned int i; // eax
  size_t v48; // [esp-8h] [ebp-10h]

  v3 = (const __m128i *)Src;
  v4 = Size;
  v5 = (__m128i *)a1;
  if ( a1 > Src && a1 < (char *)Src + Size )
  {
    v27 = (char *)Src + Size - 4;
    v28 = (char *)a1 + Size - 4;
    if ( ((unsigned __int8)v28 & 3) == 0 )
    {
      v29 = Size >> 2;
      if ( Size >> 2 >= 8 )
      {
        while ( v29 )
        {
          *(_DWORD *)v28 = *(_DWORD *)v27;
          v27 -= 4;
          v28 -= 4;
          --v29;
        }
        switch ( Size & 3 )
        {
          case 0u:
            goto TrailDown0_0;
          case 1u:
            goto TrailDown1_0;
          case 2u:
            goto TrailDown2_0;
          case 3u:
            goto TrailDown3_0;
        }
      }
      switch ( Size & 3 )
      {
        case 0u:
          goto TrailDown0_0;
        case 1u:
          goto TrailDown1_0;
        case 2u:
          goto TrailDown2_0;
        case 3u:
          goto TrailDown3_0;
      }
    }
    switch ( Size )
    {
      case 0u:
TrailDown0_0:
        result = a1;
        break;
      case 1u:
TrailDown1_0:
        v28[3] = v27[3];
        result = a1;
        break;
      case 2u:
TrailDown2_0:
        v28[3] = v27[3];
        v28[2] = v27[2];
        result = a1;
        break;
      case 3u:
TrailDown3_0:
        v28[3] = v27[3];
        v28[2] = v27[2];
        v28[1] = v27[1];
        result = a1;
        break;
      default:
        __asm { jmp     dword ptr ds:(ByteCopyDown_0+4)[eax*4] }
        return result;
    }
  }
  else
  {
    if ( _bittest(&__favor, 1u) )
    {
      qmemcpy(a1, Src, Size);
      return a1;
    }
    if ( Size < 0x80 )
      goto Dword_align_0;
    if ( (((unsigned int)Src ^ (unsigned int)a1) & 0xF) != 0 || !_bittest(&__isa_enabled, 1u) )
    {
      if ( _bittest(&__favor, 0) )
      {
        if ( ((unsigned __int8)a1 & 3) == 0 )
        {
          if ( ((unsigned __int8)Src & 3) == 0 )
          {
            if ( ((unsigned __int8)a1 & 4) != 0 )
            {
              v4 = Size - 4;
              v3 = (const __m128i *)((char *)Src + 4);
              *(_DWORD *)a1 = *(_DWORD *)Src;
              v5 = (__m128i *)((char *)a1 + 4);
            }
            if ( ((unsigned __int8)v5 & 8) != 0 )
            {
              v6 = v3->m128i_i64[0];
              v4 -= 8;
              v3 = (const __m128i *)((char *)v3 + 8);
              v5->m128i_i64[0] = v6;
              v5 = (__m128i *)((char *)v5 + 8);
            }
            if ( ((unsigned __int8)v3 & 7) != 0 )
            {
              if ( ((unsigned __int8)v3 & 8) != 0 )
              {
                si128 = _mm_load_si128((const __m128i *)((char *)v3 - 12));
                v8 = (const __m128i *)((char *)v3 - 12);
                do
                {
                  v9 = _mm_load_si128(v8 + 1);
                  v4 -= 48;
                  v10 = _mm_load_si128(v8 + 2);
                  v11 = _mm_load_si128(v8 + 3);
                  v8 += 3;
                  *v5 = _mm_alignr_epi8(v9, si128, 12);
                  v5[1] = _mm_alignr_epi8(v10, v9, 12);
                  si128 = v11;
                  v5[2] = _mm_alignr_epi8(v11, v10, 12);
                  v5 += 3;
                }
                while ( v4 >= 48 );
                v3 = (const __m128i *)((char *)&v8->m128i_u64[1] + 4);
              }
              else
              {
                v17 = _mm_load_si128((const __m128i *)((char *)v3 - 4));
                v18 = (const __m128i *)((char *)v3 - 4);
                do
                {
                  v19 = _mm_load_si128(v18 + 1);
                  v4 -= 48;
                  v20 = _mm_load_si128(v18 + 2);
                  v21 = _mm_load_si128(v18 + 3);
                  v18 += 3;
                  *v5 = _mm_alignr_epi8(v19, v17, 4);
                  v5[1] = _mm_alignr_epi8(v20, v19, 4);
                  v17 = v21;
                  v5[2] = _mm_alignr_epi8(v21, v20, 4);
                  v5 += 3;
                }
                while ( v4 >= 48 );
                v3 = (const __m128i *)((char *)v18->m128i_i64 + 4);
              }
            }
            else
            {
              v12 = _mm_load_si128((const __m128i *)((char *)v3 - 8));
              v13 = (const __m128i *)((char *)v3 - 8);
              do
              {
                v14 = _mm_load_si128(v13 + 1);
                v4 -= 48;
                v15 = _mm_load_si128(v13 + 2);
                v16 = _mm_load_si128(v13 + 3);
                v13 += 3;
                *v5 = _mm_alignr_epi8(v14, v12, 8);
                v5[1] = _mm_alignr_epi8(v15, v14, 8);
                v12 = v16;
                v5[2] = _mm_alignr_epi8(v16, v15, 8);
                v5 += 3;
              }
              while ( v4 >= 48 );
              v3 = (const __m128i *)&v13->m128i_u64[1];
            }
            while ( v4 >= 16 )
            {
              v22 = _mm_loadu_si128(v3);
              v4 -= 16;
              ++v3;
              *v5++ = v22;
            }
            if ( (v4 & 4) != 0 )
            {
              v23 = v3->m128i_i32[0];
              v4 -= 4;
              v3 = (const __m128i *)((char *)v3 + 4);
              v5->m128i_i32[0] = v23;
              v5 = (__m128i *)((char *)v5 + 4);
            }
            if ( (v4 & 8) != 0 )
            {
              v24 = v3->m128i_i64[0];
              v4 -= 8;
              v3 = (const __m128i *)((char *)v3 + 8);
              v5->m128i_i64[0] = v24;
              v5 = (__m128i *)((char *)v5 + 8);
            }
            switch ( v4 )
            {
              case 0:
                return a1;
              case 1:
                goto TrailUp1_0;
              case 2:
                goto TrailUp2_0;
              case 3:
                goto TrailUp3_0;
            }
          }
          goto Dword_align_Ok_0;
        }
        goto CopyLeadUp_0;
      }
Dword_align_0:
      if ( ((unsigned __int8)a1 & 3) == 0 )
      {
Dword_align_Ok_0:
        v25 = Size >> 2;
        switch ( v25 )
        {
          case 0u:
            goto UnwindUp0_0;
          case 1u:
            goto UnwindUp1_0;
          case 2u:
            goto UnwindUp2_0;
          case 3u:
            goto UnwindUp3_0;
          case 4u:
            goto UnwindUp4_0;
          case 5u:
            goto UnwindUp5_0;
          case 6u:
            goto UnwindUp6_0;
          case 7u:
            *((_DWORD *)a1 + v25 - 7) = *((_DWORD *)Src + v25 - 7);
UnwindUp6_0:
            *((_DWORD *)a1 + v25 - 6) = *((_DWORD *)Src + v25 - 6);
UnwindUp5_0:
            *((_DWORD *)a1 + v25 - 5) = *((_DWORD *)Src + v25 - 5);
UnwindUp4_0:
            *((_DWORD *)a1 + v25 - 4) = *((_DWORD *)Src + v25 - 4);
UnwindUp3_0:
            *((_DWORD *)a1 + v25 - 3) = *((_DWORD *)Src + v25 - 3);
UnwindUp2_0:
            *((_DWORD *)a1 + v25 - 2) = *((_DWORD *)Src + v25 - 2);
UnwindUp1_0:
            *((_DWORD *)a1 + v25 - 1) = *((_DWORD *)Src + v25 - 1);
            v3 = (const __m128i *)((char *)Src + 4 * v25);
            v5 = (__m128i *)((char *)a1 + 4 * v25);
UnwindUp0_0:
            switch ( Size & 3 )
            {
              case 0u:
                return a1;
              case 1u:
                goto TrailUp1_0;
              case 2u:
                goto TrailUp2_0;
              case 3u:
                goto TrailUp3_0;
            }
          default:
            qmemcpy(a1, Src, 4 * v25);
            v3 = (const __m128i *)((char *)Src + 4 * v25);
            v5 = (__m128i *)((char *)a1 + 4 * v25);
            switch ( Size & 3 )
            {
              case 0u:
                return a1;
              case 1u:
TrailUp1_0:
                v5->m128i_i8[0] = v3->m128i_i8[0];
                result = a1;
                break;
              case 2u:
TrailUp2_0:
                v5->m128i_i8[0] = v3->m128i_i8[0];
                v5->m128i_i8[1] = v3->m128i_i8[1];
                result = a1;
                break;
              case 3u:
TrailUp3_0:
                v5->m128i_i8[0] = v3->m128i_i8[0];
                v5->m128i_i8[1] = v3->m128i_i8[1];
                v5->m128i_i8[2] = v3->m128i_i8[2];
                result = a1;
                break;
            }
            break;
        }
        return result;
      }
CopyLeadUp_0:
      if ( Size >= 4 )
        __asm { jmp     dword ptr ds:(CopyUnwindUp_0+4)[eax*4] }
      __asm { jmp     dword ptr ds:TrailUp0_0[ecx*4]; jumptable 1002D0D9 case 0 }
    }
    v30 = (unsigned __int8)Src & 0xF;
    if ( ((unsigned __int8)Src & 0xF) != 0 )
    {
      v48 = Size - (16 - v30);
      v45 = 16 - v30;
      v46 = v45 & 3;
      if ( (v45 & 3) != 0 )
      {
        do
        {
          v5->m128i_i8[0] = v3->m128i_i8[0];
          v3 = (const __m128i *)((char *)v3 + 1);
          v5 = (__m128i *)((char *)v5 + 1);
          --v46;
        }
        while ( v46 );
      }
      for ( i = v45 >> 2; i; --i )
      {
        v5->m128i_i32[0] = v3->m128i_i32[0];
        v3 = (const __m128i *)((char *)v3 + 4);
        v5 = (__m128i *)((char *)v5 + 4);
      }
      v4 = v48;
    }
    v31 = v4;
    v32 = v4 & 0x7F;
    for ( j = v31 >> 7; j; --j )
    {
      v34 = _mm_load_si128(v3 + 1);
      v35 = _mm_load_si128(v3 + 2);
      v36 = _mm_load_si128(v3 + 3);
      *v5 = _mm_load_si128(v3);
      v5[1] = v34;
      v5[2] = v35;
      v5[3] = v36;
      v37 = _mm_load_si128(v3 + 5);
      v38 = _mm_load_si128(v3 + 6);
      v39 = _mm_load_si128(v3 + 7);
      v5[4] = _mm_load_si128(v3 + 4);
      v5[5] = v37;
      v5[6] = v38;
      v5[7] = v39;
      v3 += 8;
      v5 += 8;
    }
    if ( v32 )
    {
      for ( k = v32 >> 4; k; --k )
        *v5++ = _mm_load_si128(v3++);
      v41 = v32 & 0xF;
      if ( v41 )
      {
        v42 = v41;
        for ( m = v41 >> 2; m; --m )
        {
          v5->m128i_i32[0] = v3->m128i_i32[0];
          v3 = (const __m128i *)((char *)v3 + 4);
          v5 = (__m128i *)((char *)v5 + 4);
        }
        v44 = v42 & 3;
        if ( (v42 & 3) != 0 )
        {
          do
          {
            v5->m128i_i8[0] = v3->m128i_i8[0];
            v3 = (const __m128i *)((char *)v3 + 1);
            v5 = (__m128i *)((char *)v5 + 1);
            --v44;
          }
          while ( v44 );
        }
      }
    }
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x1002ced0  push    edi
0x1002ced1  push    esi
0x1002ced2  mov     esi, [esp+8+Src]
0x1002ced6  mov     ecx, [esp+8+Size]
0x1002ceda  mov     edi, [esp+8+arg_0]
0x1002cede  mov     eax, ecx
0x1002cee0  mov     edx, ecx
0x1002cee2  add     eax, esi
0x1002cee4  cmp     edi, esi
0x1002cee6  jbe     short CopyUp_0
0x1002cee8  cmp     edi, eax
0x1002ceea  jb      CopyDown_0
0x1002cef0  bt      ___favor, 1
0x1002cef8  jnb     short CopyUpSSE2Check_0
0x1002cefa  rep movsb
0x1002cefc  jmp     TrailUp0_0; jumptable 1002D0D9 case 0
0x1002cf01  cmp     ecx, 80h
0x1002cf07  jb      Dword_align_0
0x1002cf0d  mov     eax, edi
0x1002cf0f  xor     eax, esi
0x1002cf11  test    eax, 0Fh
0x1002cf16  jnz     short AtomChk_0
0x1002cf18  bt      ___isa_enabled, 1
0x1002cf20  jb      VEC_memcpy_0
0x1002cf26  bt      ___favor, 0
0x1002cf2e  jnb     Dword_align_0
0x1002cf34  test    edi, 3
0x1002cf3a  jnz     CopyLeadUp_0
0x1002cf40  test    esi, 3
0x1002cf46  jnz     Dword_align_Ok_0
0x1002cf4c  bt      edi, 2
0x1002cf50  jnb     short PalignHead8_0
0x1002cf52  mov     eax, [esi]
0x1002cf54  sub     ecx, 4
0x1002cf57  lea     esi, [esi+4]
0x1002cf5a  mov     [edi], eax
0x1002cf5c  lea     edi, [edi+4]
0x1002cf5f  bt      edi, 3
0x1002cf63  jnb     short PalignLoop_0
0x1002cf65  movq    xmm1, qword ptr [esi]
0x1002cf69  sub     ecx, 8
0x1002cf6c  lea     esi, [esi+8]
0x1002cf6f  movq    qword ptr [edi], xmm1
0x1002cf73  lea     edi, [edi+8]
0x1002cf76  test    esi, 7
0x1002cf7c  jz      short MovPalign8_0
0x1002cf7e  bt      esi, 3
0x1002cf82  jnb     MovPalign4_0
0x1002cf88  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x1002cf8d  lea     esi, [esi-0Ch]
0x1002cf90  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002cf95  sub     ecx, 30h ; '0'
0x1002cf98  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002cf9d  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002cfa2  lea     esi, [esi+30h]
0x1002cfa5  cmp     ecx, 30h ; '0'
0x1002cfa8  movdqa  xmm2, xmm3
0x1002cfac  palignr xmm3, xmm1, 0Ch
0x1002cfb2  movdqa  xmmword ptr [edi], xmm3
0x1002cfb6  movdqa  xmm4, xmm0
0x1002cfba  palignr xmm0, xmm2, 0Ch
0x1002cfc0  movdqa  xmmword ptr [edi+10h], xmm0
0x1002cfc5  movdqa  xmm1, xmm5
0x1002cfc9  palignr xmm5, xmm4, 0Ch
0x1002cfcf  movdqa  xmmword ptr [edi+20h], xmm5
0x1002cfd4  lea     edi, [edi+30h]
0x1002cfd7  jge     short PalignLoop12_0
0x1002cfd9  lea     esi, [esi+0Ch]
0x1002cfdc  jmp     PalignTail_0
0x1002cfe1  movdqa  xmm1, xmmword ptr [esi-8]
0x1002cfe6  lea     esi, [esi-8]
0x1002cfe9  lea     ecx, [ecx+0]
0x1002cfec  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002cff1  sub     ecx, 30h ; '0'
0x1002cff4  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002cff9  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002cffe  lea     esi, [esi+30h]
0x1002d001  cmp     ecx, 30h ; '0'
0x1002d004  movdqa  xmm2, xmm3
0x1002d008  palignr xmm3, xmm1, 8
0x1002d00e  movdqa  xmmword ptr [edi], xmm3
0x1002d012  movdqa  xmm4, xmm0
0x1002d016  palignr xmm0, xmm2, 8
0x1002d01c  movdqa  xmmword ptr [edi+10h], xmm0
0x1002d021  movdqa  xmm1, xmm5
0x1002d025  palignr xmm5, xmm4, 8
0x1002d02b  movdqa  xmmword ptr [edi+20h], xmm5
0x1002d030  lea     edi, [edi+30h]
0x1002d033  jge     short PalignLoop8_0
0x1002d035  lea     esi, [esi+8]
0x1002d038  jmp     short PalignTail_0
0x1002d03a  movdqa  xmm1, xmmword ptr [esi-4]
0x1002d03f  lea     esi, [esi-4]
0x1002d042  mov     edi, edi
0x1002d044  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002d049  sub     ecx, 30h ; '0'
0x1002d04c  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002d051  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002d056  lea     esi, [esi+30h]
0x1002d059  cmp     ecx, 30h ; '0'
0x1002d05c  movdqa  xmm2, xmm3
0x1002d060  palignr xmm3, xmm1, 4
0x1002d066  movdqa  xmmword ptr [edi], xmm3
0x1002d06a  movdqa  xmm4, xmm0
0x1002d06e  palignr xmm0, xmm2, 4
0x1002d074  movdqa  xmmword ptr [edi+10h], xmm0
0x1002d079  movdqa  xmm1, xmm5
0x1002d07d  palignr xmm5, xmm4, 4
0x1002d083  movdqa  xmmword ptr [edi+20h], xmm5
0x1002d088  lea     edi, [edi+30h]
0x1002d08b  jge     short PalignLoop4_0
0x1002d08d  lea     esi, [esi+4]
0x1002d090  cmp     ecx, 10h
0x1002d093  jl      short PalignTail4_0
0x1002d095  movdqu  xmm1, xmmword ptr [esi]
0x1002d099  sub     ecx, 10h
0x1002d09c  lea     esi, [esi+10h]
0x1002d09f  movdqa  xmmword ptr [edi], xmm1
0x1002d0a3  lea     edi, [edi+10h]
0x1002d0a6  jmp     short PalignTail_0
0x1002d0a8  bt      ecx, 2
0x1002d0ac  jnb     short PalignTail8_0
0x1002d0ae  mov     eax, [esi]
0x1002d0b0  sub     ecx, 4
0x1002d0b3  lea     esi, [esi+4]
0x1002d0b6  mov     [edi], eax
0x1002d0b8  lea     edi, [edi+4]
0x1002d0bb  bt      ecx, 3
0x1002d0bf  jnb     short PalignTailLE3_0
0x1002d0c1  movq    xmm1, qword ptr [esi]
0x1002d0c5  sub     ecx, 8
0x1002d0c8  lea     esi, [esi+8]
0x1002d0cb  movq    qword ptr [edi], xmm1
0x1002d0cf  lea     edi, [edi+8]
0x1002d0d2  mov     eax, ds:jpt_1002D0D9[ecx*4]; switch 4 cases
0x1002d0d9  jmp     eax; switch jump
0x1002d0db  test    edi, 3
0x1002d0e1  jnz     short CopyLeadUp_0
0x1002d0e3  shr     ecx, 2
0x1002d0e6  and     edx, 3
0x1002d0e9  cmp     ecx, 8; switch 8 cases
0x1002d0ec  jb      short CopyUnwindUp_0
0x1002d0ee  rep movsd; jumptable 1002D118 default case
0x1002d0f0  jmp     ds:jpt_1002D0D9[edx*4]; switch 4 cases
0x1002d0f8  mov     eax, edi
0x1002d0fa  mov     edx, 3
0x1002d0ff  sub     ecx, 4
0x1002d102  jb      short ByteCopyUp_0
0x1002d104  and     eax, 3
0x1002d107  add     ecx, eax
0x1002d109  jmp     dword ptr ds:(CopyUnwindUp_0+4)[eax*4]
0x1002d110  jmp     dword ptr ds:TrailUp0_0[ecx*4]; jumptable 1002D0D9 case 0
0x1002d118  jmp     ds:jpt_1002D118[ecx*4]; switch jump
0x1002d12c  and     edx, ecx
0x1002d12e  mov     al, [esi]
0x1002d130  mov     [edi], al
0x1002d132  mov     al, [esi+1]
0x1002d135  mov     [edi+1], al
0x1002d138  mov     al, [esi+2]
0x1002d13b  shr     ecx, 2
0x1002d13e  mov     [edi+2], al
0x1002d141  add     esi, 3
0x1002d144  add     edi, 3
0x1002d147  cmp     ecx, 8
0x1002d14a  jb      short CopyUnwindUp_0
0x1002d14c  rep movsd
0x1002d14e  jmp     ds:jpt_1002D0D9[edx*4]; switch 4 cases
0x1002d158  and     edx, ecx
0x1002d15a  mov     al, [esi]
0x1002d15c  mov     [edi], al
0x1002d15e  mov     al, [esi+1]
0x1002d161  shr     ecx, 2
0x1002d164  mov     [edi+1], al
0x1002d167  add     esi, 2
0x1002d16a  add     edi, 2
0x1002d16d  cmp     ecx, 8
0x1002d170  jb      short CopyUnwindUp_0
0x1002d172  rep movsd
0x1002d174  jmp     ds:jpt_1002D0D9[edx*4]; switch 4 cases
0x1002d17c  and     edx, ecx
0x1002d17e  mov     al, [esi]
0x1002d180  mov     [edi], al
0x1002d182  add     esi, 1
0x1002d185  shr     ecx, 2
0x1002d188  add     edi, 1
0x1002d18b  cmp     ecx, 8
0x1002d18e  jb      short CopyUnwindUp_0
0x1002d190  rep movsd
0x1002d192  jmp     ds:jpt_1002D0D9[edx*4]; switch 4 cases
0x1002d1bc  mov     eax, [esi+ecx*4-1Ch]; jumptable 1002D118 case 7
0x1002d1c0  mov     [edi+ecx*4-1Ch], eax
0x1002d1c4  mov     eax, [esi+ecx*4-18h]; jumptable 1002D118 case 6
0x1002d1c8  mov     [edi+ecx*4-18h], eax
0x1002d1cc  mov     eax, [esi+ecx*4-14h]; jumptable 1002D118 case 5
0x1002d1d0  mov     [edi+ecx*4-14h], eax
0x1002d1d4  mov     eax, [esi+ecx*4-10h]; jumptable 1002D118 case 4
0x1002d1d8  mov     [edi+ecx*4-10h], eax
0x1002d1dc  mov     eax, [esi+ecx*4-0Ch]; jumptable 1002D118 case 3
0x1002d1e0  mov     [edi+ecx*4-0Ch], eax
0x1002d1e4  mov     eax, [esi+ecx*4-8]; jumptable 1002D118 case 2
0x1002d1e8  mov     [edi+ecx*4-8], eax
0x1002d1ec  mov     eax, [esi+ecx*4-4]; jumptable 1002D118 case 1
0x1002d1f0  mov     [edi+ecx*4-4], eax
0x1002d1f4  lea     eax, ds:0[ecx*4]
0x1002d1fb  add     esi, eax
0x1002d1fd  add     edi, eax
0x1002d1ff  jmp     ds:jpt_1002D0D9[edx*4]; jumptable 1002D118 case 0
0x1002d218  mov     eax, [esp+8+arg_0]; jumptable 1002D0D9 case 0
0x1002d21c  pop     esi
0x1002d21d  pop     edi
0x1002d21e  retn
0x1002d220  mov     al, [esi]; jumptable 1002D0D9 case 1
0x1002d222  mov     [edi], al
0x1002d224  mov     eax, [esp+8+arg_0]
0x1002d228  pop     esi
0x1002d229  pop     edi
0x1002d22a  retn
0x1002d22c  mov     al, [esi]; jumptable 1002D0D9 case 2
0x1002d22e  mov     [edi], al
0x1002d230  mov     al, [esi+1]
0x1002d233  mov     [edi+1], al
0x1002d236  mov     eax, [esp+8+arg_0]
0x1002d23a  pop     esi
0x1002d23b  pop     edi
0x1002d23c  retn
0x1002d240  mov     al, [esi]; jumptable 1002D0D9 case 3
0x1002d242  mov     [edi], al
0x1002d244  mov     al, [esi+1]
0x1002d247  mov     [edi+1], al
0x1002d24a  mov     al, [esi+2]
0x1002d24d  mov     [edi+2], al
0x1002d250  mov     eax, [esp+8+arg_0]
0x1002d254  pop     esi
0x1002d255  pop     edi
0x1002d256  retn
0x1002d258  lea     esi, [ecx+esi-4]
0x1002d25c  lea     edi, [ecx+edi-4]
0x1002d260  test    edi, 3
0x1002d266  jnz     short CopyLeadDown_0
0x1002d268  shr     ecx, 2
0x1002d26b  and     edx, 3
0x1002d26e  cmp     ecx, 8
0x1002d271  jb      short CopyUnwindDown_0
0x1002d273  std
0x1002d274  rep movsd
0x1002d276  cld
0x1002d277  jmp     ds:jpt_1002D2A4[edx*4]; switch 4 cases
0x1002d280  neg     ecx
0x1002d282  jmp     ds:jpt_1002D282[ecx*4]; switch 1 cases
0x1002d28c  mov     eax, edi
0x1002d28e  mov     edx, 3
0x1002d293  cmp     ecx, 4; switch 4 cases
0x1002d296  jb      short ByteCopyDown_0
0x1002d298  and     eax, 3; jumptable 1002D2A4 default case
0x1002d29b  sub     ecx, eax
0x1002d29d  jmp     dword ptr ds:(ByteCopyDown_0+4)[eax*4]
0x1002d2a4  jmp     ds:jpt_1002D2A4[ecx*4]; switch jump
0x1002d2b8  mov     al, [esi+3]
0x1002d2bb  and     edx, ecx
0x1002d2bd  mov     [edi+3], al
0x1002d2c0  sub     esi, 1
0x1002d2c3  shr     ecx, 2
0x1002d2c6  sub     edi, 1
0x1002d2c9  cmp     ecx, 8
0x1002d2cc  jb      short CopyUnwindDown_0
0x1002d2ce  std
0x1002d2cf  rep movsd
0x1002d2d1  cld
0x1002d2d2  jmp     ds:jpt_1002D2A4[edx*4]; switch 4 cases
0x1002d2dc  mov     al, [esi+3]
0x1002d2df  and     edx, ecx
0x1002d2e1  mov     [edi+3], al
0x1002d2e4  mov     al, [esi+2]
0x1002d2e7  shr     ecx, 2
0x1002d2ea  mov     [edi+2], al
0x1002d2ed  sub     esi, 2
0x1002d2f0  sub     edi, 2
0x1002d2f3  cmp     ecx, 8
0x1002d2f6  jb      short CopyUnwindDown_0
0x1002d2f8  std
0x1002d2f9  rep movsd
0x1002d2fb  cld
0x1002d2fc  jmp     ds:jpt_1002D2A4[edx*4]; switch 4 cases
0x1002d304  mov     al, [esi+3]
0x1002d307  and     edx, ecx
0x1002d309  mov     [edi+3], al
0x1002d30c  mov     al, [esi+2]
0x1002d30f  mov     [edi+2], al
0x1002d312  mov     al, [esi+1]
0x1002d315  shr     ecx, 2
0x1002d318  mov     [edi+1], al
0x1002d31b  sub     esi, 3
0x1002d31e  sub     edi, 3
0x1002d321  cmp     ecx, 8
0x1002d324  jb      CopyUnwindDown_0
0x1002d32a  std
0x1002d32b  rep movsd
0x1002d32d  cld
0x1002d32e  jmp     ds:jpt_1002D2A4[edx*4]; switch 4 cases
0x1002d358  mov     eax, [esi+ecx*4+1Ch]
  ... truncated ...
```
