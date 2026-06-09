# _memcpy

- ea: `0x1002ba60`
- end: `0x1002c0a4`
- name: `_memcpy`
- size: `1604`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x10009800`
- `0x10009e20`
- `0x1000a050`
- `0x1000a0f0`
- `0x1000aea0`
- `0x1000b310`
- `0x1000bab0`
- `0x10015960`
- `0x10015cb0`
- `0x10016150`
- `0x100161d0`
- `0x10016620`
- `0x100167e0`
- `0x1001d2f0`
- `0x1001d6a0`
- `0x1001d870`
- `0x10020080`
- `0x10020780`
- `0x10020c10`
- `0x10021550`
- `0x10021670`
- `0x100288d0`
- `0x10028a60`
- `0x10029520`
- `0x100295f0`
- `0x100296d0`
- `0x10029770`
- `0x10029f00`
- `0x1002a6d0`
- `0x10030b7b`

## callees

- `0x1002ba60`

## pseudocode

```c
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
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
            goto TrailDown0;
          case 1u:
            goto TrailDown1;
          case 2u:
            goto TrailDown2;
          case 3u:
            goto TrailDown3;
        }
      }
      switch ( Size & 3 )
      {
        case 0u:
          goto TrailDown0;
        case 1u:
          goto TrailDown1;
        case 2u:
          goto TrailDown2;
        case 3u:
          goto TrailDown3;
      }
    }
    switch ( Size )
    {
      case 0u:
TrailDown0:
        result = a1;
        break;
      case 1u:
TrailDown1:
        v28[3] = v27[3];
        result = a1;
        break;
      case 2u:
TrailDown2:
        v28[3] = v27[3];
        v28[2] = v27[2];
        result = a1;
        break;
      case 3u:
TrailDown3:
        v28[3] = v27[3];
        v28[2] = v27[2];
        v28[1] = v27[1];
        result = a1;
        break;
      default:
        __asm { jmp     dword ptr ds:(ByteCopyDown+4)[eax*4] }
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
      goto Dword_align;
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
                goto TrailUp1;
              case 2:
                goto TrailUp2;
              case 3:
                goto TrailUp3;
            }
          }
          goto Dword_align_Ok;
        }
        goto CopyLeadUp;
      }
Dword_align:
      if ( ((unsigned __int8)a1 & 3) == 0 )
      {
Dword_align_Ok:
        v25 = Size >> 2;
        switch ( v25 )
        {
          case 0u:
            goto UnwindUp0;
          case 1u:
            goto UnwindUp1;
          case 2u:
            goto UnwindUp2;
          case 3u:
            goto UnwindUp3;
          case 4u:
            goto UnwindUp4;
          case 5u:
            goto UnwindUp5;
          case 6u:
            goto UnwindUp6;
          case 7u:
            *((_DWORD *)a1 + v25 - 7) = *((_DWORD *)Src + v25 - 7);
UnwindUp6:
            *((_DWORD *)a1 + v25 - 6) = *((_DWORD *)Src + v25 - 6);
UnwindUp5:
            *((_DWORD *)a1 + v25 - 5) = *((_DWORD *)Src + v25 - 5);
UnwindUp4:
            *((_DWORD *)a1 + v25 - 4) = *((_DWORD *)Src + v25 - 4);
UnwindUp3:
            *((_DWORD *)a1 + v25 - 3) = *((_DWORD *)Src + v25 - 3);
UnwindUp2:
            *((_DWORD *)a1 + v25 - 2) = *((_DWORD *)Src + v25 - 2);
UnwindUp1:
            *((_DWORD *)a1 + v25 - 1) = *((_DWORD *)Src + v25 - 1);
            v3 = (const __m128i *)((char *)Src + 4 * v25);
            v5 = (__m128i *)((char *)a1 + 4 * v25);
UnwindUp0:
            switch ( Size & 3 )
            {
              case 0u:
                return a1;
              case 1u:
                goto TrailUp1;
              case 2u:
                goto TrailUp2;
              case 3u:
                goto TrailUp3;
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
TrailUp1:
                v5->m128i_i8[0] = v3->m128i_i8[0];
                result = a1;
                break;
              case 2u:
TrailUp2:
                v5->m128i_i8[0] = v3->m128i_i8[0];
                v5->m128i_i8[1] = v3->m128i_i8[1];
                result = a1;
                break;
              case 3u:
TrailUp3:
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
CopyLeadUp:
      if ( Size >= 4 )
        __asm { jmp     dword ptr ds:(CopyUnwindUp+4)[eax*4] }
      __asm { jmp     dword ptr ds:TrailUp0[ecx*4]; jumptable 1002BC69 case 0 }
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
0x1002ba60  push    edi
0x1002ba61  push    esi
0x1002ba62  mov     esi, [esp+8+Src]
0x1002ba66  mov     ecx, [esp+8+Size]
0x1002ba6a  mov     edi, [esp+8+arg_0]
0x1002ba6e  mov     eax, ecx
0x1002ba70  mov     edx, ecx
0x1002ba72  add     eax, esi
0x1002ba74  cmp     edi, esi
0x1002ba76  jbe     short CopyUp
0x1002ba78  cmp     edi, eax
0x1002ba7a  jb      CopyDown
0x1002ba80  bt      ___favor, 1
0x1002ba88  jnb     short CopyUpSSE2Check
0x1002ba8a  rep movsb
0x1002ba8c  jmp     TrailUp0; jumptable 1002BC69 case 0
0x1002ba91  cmp     ecx, 80h
0x1002ba97  jb      Dword_align
0x1002ba9d  mov     eax, edi
0x1002ba9f  xor     eax, esi
0x1002baa1  test    eax, 0Fh
0x1002baa6  jnz     short AtomChk
0x1002baa8  bt      ___isa_enabled, 1
0x1002bab0  jb      VEC_memcpy
0x1002bab6  bt      ___favor, 0
0x1002babe  jnb     Dword_align
0x1002bac4  test    edi, 3
0x1002baca  jnz     CopyLeadUp
0x1002bad0  test    esi, 3
0x1002bad6  jnz     Dword_align_Ok
0x1002badc  bt      edi, 2
0x1002bae0  jnb     short PalignHead8
0x1002bae2  mov     eax, [esi]
0x1002bae4  sub     ecx, 4
0x1002bae7  lea     esi, [esi+4]
0x1002baea  mov     [edi], eax
0x1002baec  lea     edi, [edi+4]
0x1002baef  bt      edi, 3
0x1002baf3  jnb     short PalignLoop
0x1002baf5  movq    xmm1, qword ptr [esi]
0x1002baf9  sub     ecx, 8
0x1002bafc  lea     esi, [esi+8]
0x1002baff  movq    qword ptr [edi], xmm1
0x1002bb03  lea     edi, [edi+8]
0x1002bb06  test    esi, 7
0x1002bb0c  jz      short MovPalign8
0x1002bb0e  bt      esi, 3
0x1002bb12  jnb     MovPalign4
0x1002bb18  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x1002bb1d  lea     esi, [esi-0Ch]
0x1002bb20  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002bb25  sub     ecx, 30h ; '0'
0x1002bb28  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002bb2d  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002bb32  lea     esi, [esi+30h]
0x1002bb35  cmp     ecx, 30h ; '0'
0x1002bb38  movdqa  xmm2, xmm3
0x1002bb3c  palignr xmm3, xmm1, 0Ch
0x1002bb42  movdqa  xmmword ptr [edi], xmm3
0x1002bb46  movdqa  xmm4, xmm0
0x1002bb4a  palignr xmm0, xmm2, 0Ch
0x1002bb50  movdqa  xmmword ptr [edi+10h], xmm0
0x1002bb55  movdqa  xmm1, xmm5
0x1002bb59  palignr xmm5, xmm4, 0Ch
0x1002bb5f  movdqa  xmmword ptr [edi+20h], xmm5
0x1002bb64  lea     edi, [edi+30h]
0x1002bb67  jge     short PalignLoop12
0x1002bb69  lea     esi, [esi+0Ch]
0x1002bb6c  jmp     PalignTail
0x1002bb71  movdqa  xmm1, xmmword ptr [esi-8]
0x1002bb76  lea     esi, [esi-8]
0x1002bb79  lea     ecx, [ecx+0]
0x1002bb7c  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002bb81  sub     ecx, 30h ; '0'
0x1002bb84  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002bb89  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002bb8e  lea     esi, [esi+30h]
0x1002bb91  cmp     ecx, 30h ; '0'
0x1002bb94  movdqa  xmm2, xmm3
0x1002bb98  palignr xmm3, xmm1, 8
0x1002bb9e  movdqa  xmmword ptr [edi], xmm3
0x1002bba2  movdqa  xmm4, xmm0
0x1002bba6  palignr xmm0, xmm2, 8
0x1002bbac  movdqa  xmmword ptr [edi+10h], xmm0
0x1002bbb1  movdqa  xmm1, xmm5
0x1002bbb5  palignr xmm5, xmm4, 8
0x1002bbbb  movdqa  xmmword ptr [edi+20h], xmm5
0x1002bbc0  lea     edi, [edi+30h]
0x1002bbc3  jge     short PalignLoop8
0x1002bbc5  lea     esi, [esi+8]
0x1002bbc8  jmp     short PalignTail
0x1002bbca  movdqa  xmm1, xmmword ptr [esi-4]
0x1002bbcf  lea     esi, [esi-4]
0x1002bbd2  mov     edi, edi
0x1002bbd4  movdqa  xmm3, xmmword ptr [esi+10h]
0x1002bbd9  sub     ecx, 30h ; '0'
0x1002bbdc  movdqa  xmm0, xmmword ptr [esi+20h]
0x1002bbe1  movdqa  xmm5, xmmword ptr [esi+30h]
0x1002bbe6  lea     esi, [esi+30h]
0x1002bbe9  cmp     ecx, 30h ; '0'
0x1002bbec  movdqa  xmm2, xmm3
0x1002bbf0  palignr xmm3, xmm1, 4
0x1002bbf6  movdqa  xmmword ptr [edi], xmm3
0x1002bbfa  movdqa  xmm4, xmm0
0x1002bbfe  palignr xmm0, xmm2, 4
0x1002bc04  movdqa  xmmword ptr [edi+10h], xmm0
0x1002bc09  movdqa  xmm1, xmm5
0x1002bc0d  palignr xmm5, xmm4, 4
0x1002bc13  movdqa  xmmword ptr [edi+20h], xmm5
0x1002bc18  lea     edi, [edi+30h]
0x1002bc1b  jge     short PalignLoop4
0x1002bc1d  lea     esi, [esi+4]
0x1002bc20  cmp     ecx, 10h
0x1002bc23  jl      short PalignTail4
0x1002bc25  movdqu  xmm1, xmmword ptr [esi]
0x1002bc29  sub     ecx, 10h
0x1002bc2c  lea     esi, [esi+10h]
0x1002bc2f  movdqa  xmmword ptr [edi], xmm1
0x1002bc33  lea     edi, [edi+10h]
0x1002bc36  jmp     short PalignTail
0x1002bc38  bt      ecx, 2
0x1002bc3c  jnb     short PalignTail8
0x1002bc3e  mov     eax, [esi]
0x1002bc40  sub     ecx, 4
0x1002bc43  lea     esi, [esi+4]
0x1002bc46  mov     [edi], eax
0x1002bc48  lea     edi, [edi+4]
0x1002bc4b  bt      ecx, 3
0x1002bc4f  jnb     short PalignTailLE3
0x1002bc51  movq    xmm1, qword ptr [esi]
0x1002bc55  sub     ecx, 8
0x1002bc58  lea     esi, [esi+8]
0x1002bc5b  movq    qword ptr [edi], xmm1
0x1002bc5f  lea     edi, [edi+8]
0x1002bc62  mov     eax, ds:jpt_1002BC69[ecx*4]; switch 4 cases
0x1002bc69  jmp     eax; switch jump
0x1002bc6b  test    edi, 3
0x1002bc71  jnz     short CopyLeadUp
0x1002bc73  shr     ecx, 2
0x1002bc76  and     edx, 3
0x1002bc79  cmp     ecx, 8; switch 8 cases
0x1002bc7c  jb      short CopyUnwindUp
0x1002bc7e  rep movsd; jumptable 1002BCA8 default case
0x1002bc80  jmp     ds:jpt_1002BC69[edx*4]; switch 4 cases
0x1002bc88  mov     eax, edi
0x1002bc8a  mov     edx, 3
0x1002bc8f  sub     ecx, 4
0x1002bc92  jb      short ByteCopyUp
0x1002bc94  and     eax, 3
0x1002bc97  add     ecx, eax
0x1002bc99  jmp     dword ptr ds:(CopyUnwindUp+4)[eax*4]
0x1002bca0  jmp     dword ptr ds:TrailUp0[ecx*4]; jumptable 1002BC69 case 0
0x1002bca8  jmp     ds:jpt_1002BCA8[ecx*4]; switch jump
0x1002bcbc  and     edx, ecx
0x1002bcbe  mov     al, [esi]
0x1002bcc0  mov     [edi], al
0x1002bcc2  mov     al, [esi+1]
0x1002bcc5  mov     [edi+1], al
0x1002bcc8  mov     al, [esi+2]
0x1002bccb  shr     ecx, 2
0x1002bcce  mov     [edi+2], al
0x1002bcd1  add     esi, 3
0x1002bcd4  add     edi, 3
0x1002bcd7  cmp     ecx, 8
0x1002bcda  jb      short CopyUnwindUp
0x1002bcdc  rep movsd
0x1002bcde  jmp     ds:jpt_1002BC69[edx*4]; switch 4 cases
0x1002bce8  and     edx, ecx
0x1002bcea  mov     al, [esi]
0x1002bcec  mov     [edi], al
0x1002bcee  mov     al, [esi+1]
0x1002bcf1  shr     ecx, 2
0x1002bcf4  mov     [edi+1], al
0x1002bcf7  add     esi, 2
0x1002bcfa  add     edi, 2
0x1002bcfd  cmp     ecx, 8
0x1002bd00  jb      short CopyUnwindUp
0x1002bd02  rep movsd
0x1002bd04  jmp     ds:jpt_1002BC69[edx*4]; switch 4 cases
0x1002bd0c  and     edx, ecx
0x1002bd0e  mov     al, [esi]
0x1002bd10  mov     [edi], al
0x1002bd12  add     esi, 1
0x1002bd15  shr     ecx, 2
0x1002bd18  add     edi, 1
0x1002bd1b  cmp     ecx, 8
0x1002bd1e  jb      short CopyUnwindUp
0x1002bd20  rep movsd
0x1002bd22  jmp     ds:jpt_1002BC69[edx*4]; switch 4 cases
0x1002bd4c  mov     eax, [esi+ecx*4-1Ch]; jumptable 1002BCA8 case 7
0x1002bd50  mov     [edi+ecx*4-1Ch], eax
0x1002bd54  mov     eax, [esi+ecx*4-18h]; jumptable 1002BCA8 case 6
0x1002bd58  mov     [edi+ecx*4-18h], eax
0x1002bd5c  mov     eax, [esi+ecx*4-14h]; jumptable 1002BCA8 case 5
0x1002bd60  mov     [edi+ecx*4-14h], eax
0x1002bd64  mov     eax, [esi+ecx*4-10h]; jumptable 1002BCA8 case 4
0x1002bd68  mov     [edi+ecx*4-10h], eax
0x1002bd6c  mov     eax, [esi+ecx*4-0Ch]; jumptable 1002BCA8 case 3
0x1002bd70  mov     [edi+ecx*4-0Ch], eax
0x1002bd74  mov     eax, [esi+ecx*4-8]; jumptable 1002BCA8 case 2
0x1002bd78  mov     [edi+ecx*4-8], eax
0x1002bd7c  mov     eax, [esi+ecx*4-4]; jumptable 1002BCA8 case 1
0x1002bd80  mov     [edi+ecx*4-4], eax
0x1002bd84  lea     eax, ds:0[ecx*4]
0x1002bd8b  add     esi, eax
0x1002bd8d  add     edi, eax
0x1002bd8f  jmp     ds:jpt_1002BC69[edx*4]; jumptable 1002BCA8 case 0
0x1002bda8  mov     eax, [esp+8+arg_0]; jumptable 1002BC69 case 0
0x1002bdac  pop     esi
0x1002bdad  pop     edi
0x1002bdae  retn
0x1002bdb0  mov     al, [esi]; jumptable 1002BC69 case 1
0x1002bdb2  mov     [edi], al
0x1002bdb4  mov     eax, [esp+8+arg_0]
0x1002bdb8  pop     esi
0x1002bdb9  pop     edi
0x1002bdba  retn
0x1002bdbc  mov     al, [esi]; jumptable 1002BC69 case 2
0x1002bdbe  mov     [edi], al
0x1002bdc0  mov     al, [esi+1]
0x1002bdc3  mov     [edi+1], al
0x1002bdc6  mov     eax, [esp+8+arg_0]
0x1002bdca  pop     esi
0x1002bdcb  pop     edi
0x1002bdcc  retn
0x1002bdd0  mov     al, [esi]; jumptable 1002BC69 case 3
0x1002bdd2  mov     [edi], al
0x1002bdd4  mov     al, [esi+1]
0x1002bdd7  mov     [edi+1], al
0x1002bdda  mov     al, [esi+2]
0x1002bddd  mov     [edi+2], al
0x1002bde0  mov     eax, [esp+8+arg_0]
0x1002bde4  pop     esi
0x1002bde5  pop     edi
0x1002bde6  retn
0x1002bde8  lea     esi, [ecx+esi-4]
0x1002bdec  lea     edi, [ecx+edi-4]
0x1002bdf0  test    edi, 3
0x1002bdf6  jnz     short CopyLeadDown
0x1002bdf8  shr     ecx, 2
0x1002bdfb  and     edx, 3
0x1002bdfe  cmp     ecx, 8
0x1002be01  jb      short CopyUnwindDown
0x1002be03  std
0x1002be04  rep movsd
0x1002be06  cld
0x1002be07  jmp     ds:jpt_1002BE34[edx*4]; switch 4 cases
0x1002be10  neg     ecx
0x1002be12  jmp     ds:jpt_1002BE12[ecx*4]; switch 1 cases
0x1002be1c  mov     eax, edi
0x1002be1e  mov     edx, 3
0x1002be23  cmp     ecx, 4; switch 4 cases
0x1002be26  jb      short ByteCopyDown
0x1002be28  and     eax, 3; jumptable 1002BE34 default case
0x1002be2b  sub     ecx, eax
0x1002be2d  jmp     dword ptr ds:(ByteCopyDown+4)[eax*4]
0x1002be34  jmp     ds:jpt_1002BE34[ecx*4]; switch jump
0x1002be48  mov     al, [esi+3]
0x1002be4b  and     edx, ecx
0x1002be4d  mov     [edi+3], al
0x1002be50  sub     esi, 1
0x1002be53  shr     ecx, 2
0x1002be56  sub     edi, 1
0x1002be59  cmp     ecx, 8
0x1002be5c  jb      short CopyUnwindDown
0x1002be5e  std
0x1002be5f  rep movsd
0x1002be61  cld
0x1002be62  jmp     ds:jpt_1002BE34[edx*4]; switch 4 cases
0x1002be6c  mov     al, [esi+3]
0x1002be6f  and     edx, ecx
0x1002be71  mov     [edi+3], al
0x1002be74  mov     al, [esi+2]
0x1002be77  shr     ecx, 2
0x1002be7a  mov     [edi+2], al
0x1002be7d  sub     esi, 2
0x1002be80  sub     edi, 2
0x1002be83  cmp     ecx, 8
0x1002be86  jb      short CopyUnwindDown
0x1002be88  std
0x1002be89  rep movsd
0x1002be8b  cld
0x1002be8c  jmp     ds:jpt_1002BE34[edx*4]; switch 4 cases
0x1002be94  mov     al, [esi+3]
0x1002be97  and     edx, ecx
0x1002be99  mov     [edi+3], al
0x1002be9c  mov     al, [esi+2]
0x1002be9f  mov     [edi+2], al
0x1002bea2  mov     al, [esi+1]
0x1002bea5  shr     ecx, 2
0x1002bea8  mov     [edi+1], al
0x1002beab  sub     esi, 3
0x1002beae  sub     edi, 3
0x1002beb1  cmp     ecx, 8
0x1002beb4  jb      CopyUnwindDown
0x1002beba  std
0x1002bebb  rep movsd
0x1002bebd  cld
0x1002bebe  jmp     ds:jpt_1002BE34[edx*4]; switch 4 cases
0x1002bee8  mov     eax, [esi+ecx*4+1Ch]
  ... truncated ...
```
