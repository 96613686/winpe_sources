# CAudioTimeCompression::findMaxCorrelationFFT2(Chunk *,__int64,Chunk *,__int64,__int64,__int64 *,int)

- ea: `0x1800504f0`
- end: `0x180050f57`
- name: `?findMaxCorrelationFFT2@CAudioTimeCompression@@IEAAJPEAVChunk@@_J0_J2PEA_JH@Z`
- size: `2663`
- prototype: `__int64 __usercall@<rax>(CAudioTimeCompression *__hidden this@<rcx>, struct Chunk *@<rdx>, __int64@<r8>, struct Chunk *@<r9>, __int64, __int64, __int64 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004f4c0`

## callees

- `0x1800021a8`
- `0x18004eec0`
- `0x1800504f0`
- `0x180088750`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::findMaxCorrelationFFT2(
        CAudioTimeCompression *this,
        struct Chunk *a2,
        __int64 a3,
        struct Chunk *a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        int a8)
{
  __int64 v8; // r10
  __int64 v10; // rbp
  int v11; // r15d
  int v12; // esi
  unsigned int v13; // ecx
  int v16; // edi
  int v17; // r14d
  signed int v18; // r9d
  __int64 result; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // r13d
  int v24; // ebp
  int v25; // eax
  int v26; // r9d
  int v27; // edx
  __int64 v28; // rcx
  float v29; // xmm0_4
  float v30; // xmm1_4
  float v31; // xmm0_4
  float v32; // xmm0_4
  __int64 v33; // r8
  __int64 v34; // rcx
  float *v35; // r12
  _QWORD *v36; // r14
  float *v37; // r15
  bool v38; // sf
  int v39; // ecx
  __int64 v40; // rax
  int v41; // r9d
  __int64 v42; // rcx
  __int64 v43; // r8
  __m128 v44; // xmm1
  int v45; // r10d
  _QWORD *v46; // rdx
  float v47; // xmm2_4
  __int64 v48; // rcx
  float v49; // xmm3_4
  float v50; // xmm3_4
  float v51; // xmm2_4
  float v52; // xmm2_4
  float v53; // xmm3_4
  float v54; // xmm2_4
  float v55; // xmm3_4
  __int64 v56; // r8
  float v57; // xmm2_4
  float v58; // xmm0_4
  int v59; // r8d
  int v60; // r10d
  char *v61; // rdx
  float v62; // xmm2_4
  float v63; // xmm3_4
  char *v64; // r11
  float v65; // xmm3_4
  float v66; // xmm2_4
  __int64 v67; // rax
  float v68; // xmm2_4
  float v69; // xmm3_4
  __int64 v70; // r9
  float v71; // xmm2_4
  float v72; // xmm3_4
  __int64 v73; // r9
  float v74; // xmm2_4
  float v75; // xmm0_4
  int v76; // edx
  float v77; // xmm2_4
  __int64 v78; // rcx
  unsigned __int32 v79; // xmm8_4
  float v80; // xmm6_4
  float v81; // xmm4_4
  float v82; // xmm5_4
  float v83; // xmm4_4
  float v84; // xmm5_4
  float v85; // xmm4_4
  float *v86; // [rsp+40h] [rbp-88h]
  int v87; // [rsp+D0h] [rbp+8h]
  unsigned int v89; // [rsp+F8h] [rbp+30h]

  v8 = a6;
  v10 = a5;
  v11 = a8;
  v12 = a6 - a5;
  v13 = *((_DWORD *)this + 2);
  v16 = 1;
  v17 = a6 - a5 + a8;
  if ( v13 <= 0xBB80 )
  {
    v18 = 1;
    v87 = 1;
  }
  else
  {
    v18 = (v13 + 47999) / 0xBB80;
    v87 = v18;
    if ( v18 < 1 )
      return 2147500037LL;
    v17 /= v18;
    v12 = v17 - a8 / v18;
    a8 /= v18;
    v11 /= v18;
    if ( v18 > 2 )
      return 2147500037LL;
  }
  if ( v17 > 2048 )
  {
    v20 = *a7;
    v17 = 2048;
    v12 = 2048 - v11;
    v21 = v18 * (2048 - v11) / 2;
    if ( *a7 - a5 > v21 )
    {
      v10 = v20 - v21;
      a5 = v20 - v21;
    }
    v8 = v10 + v18 * (2048 - v11);
  }
  v22 = *((_QWORD *)this + 27) + *((int *)this + 19);
  if ( v10 <= v22 && v22 <= v8 )
  {
    *a7 = v22;
    return 0;
  }
  v23 = 0;
  v24 = 1;
  v25 = 0;
  while ( v24 < v17 )
  {
    v24 *= 2;
    if ( ++v25 >= 32 )
    {
      v24 = 0;
      break;
    }
  }
  result = CAudioTimeCompression::ChannelDownMix(this, a4, a5, v17, v18, *((float **)this + 20), *((_DWORD *)this + 38));
  if ( (int)result >= 0 )
  {
    v26 = v17 - 1;
    v27 = 0;
    **((_DWORD **)this + 23) = 0;
    if ( v17 - 1 >= 4 )
    {
      do
      {
        v28 = v27;
        v27 += 4;
        v29 = *(float *)(*((_QWORD *)this + 20) + 4 * v28);
        *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 4) = (float)(v29 * v29)
                                                         + *(float *)(*((_QWORD *)this + 23) + 4 * v28);
        v30 = *(float *)(*((_QWORD *)this + 20) + 4 * v28 + 4);
        *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 8) = (float)(v30 * v30)
                                                         + *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 4);
        v31 = *(float *)(*((_QWORD *)this + 20) + 4 * v28 + 8);
        *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 12) = (float)(v31 * v31)
                                                          + *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 8);
        v32 = *(float *)(*((_QWORD *)this + 20) + 4 * v28 + 12);
        *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 16) = (float)(v32 * v32)
                                                          + *(float *)(*((_QWORD *)this + 23) + 4 * v28 + 12);
      }
      while ( v27 < v17 - 4 );
    }
    if ( v27 < v26 )
    {
      v33 = v27;
      do
      {
        v34 = 4 * v33++;
        ++v27;
        *(float *)(*((_QWORD *)this + 23) + 4 * v33) = (float)(*(float *)(v34 + *((_QWORD *)this + 20))
                                                             * *(float *)(v34 + *((_QWORD *)this + 20)))
                                                     + *(float *)(v34 + *((_QWORD *)this + 23));
      }
      while ( v27 < v26 );
    }
    memset_0((void *)(*((_QWORD *)this + 20) + 4LL * v17), 0, 4LL * (v24 - v17));
    result = CAudioTimeCompression::ChannelDownMix(
               this,
               a2,
               a3,
               v11,
               v87,
               *((float **)this + 21),
               *((_DWORD *)this + 38));
    if ( (int)result >= 0 )
    {
      memset_0((void *)(*((_QWORD *)this + 21) + 4LL * v11), 0, 4LL * (v24 - v11));
      if ( v24 < 2 || v24 > *((_DWORD *)this + 50) || (v24 & 1) != 0 )
      {
        return 2147942487LL;
      }
      else
      {
        v35 = (float *)*((_QWORD *)this + 20);
        v36 = (_QWORD *)((char *)this + 176);
        v37 = (float *)*((_QWORD *)this + 21);
        v86 = (float *)*((_QWORD *)this + 22);
        result = (*((__int64 (__fastcall **)(_QWORD, float *, _QWORD))this + 17))(
                   *((_QWORD *)this + 16),
                   v35,
                   (unsigned __int16)v24);
        v89 = result;
        v38 = (int)result < 0;
        if ( (_DWORD)result )
          goto LABEL_33;
        result = (*((__int64 (__fastcall **)(_QWORD, float *, _QWORD))this + 17))(
                   *((_QWORD *)this + 16),
                   v37,
                   (unsigned __int16)v24);
        v89 = result;
        v38 = (int)result < 0;
        if ( (_DWORD)result )
          goto LABEL_33;
        v39 = 2;
        *v86 = *v35 * *v37;
        v86[1] = v35[1] * v37[1];
        if ( v24 > 3 )
        {
          do
          {
            v40 = v39;
            v39 += 2;
            v86[v40] = (float)(v35[v40 + 1] * v37[v40 + 1]) + (float)(v37[v40] * v35[v40]);
            v86[v40 + 1] = (float)(v35[v40 + 1] * v37[v40]) - (float)(v35[v40] * v37[v40 + 1]);
          }
          while ( v39 + 1 < v24 );
        }
        result = (*((__int64 (__fastcall **)(_QWORD, float *, _QWORD))this + 18))(
                   *((_QWORD *)this + 16),
                   v86,
                   (unsigned __int16)v24);
        v89 = result;
        v38 = (int)result < 0;
        if ( (_DWORD)result )
        {
LABEL_33:
          if ( v38 )
            return result;
        }
        else
        {
          v89 = 0;
        }
        if ( *(_DWORD *)this )
        {
          v41 = 0;
          if ( v12 > 3 )
          {
            do
            {
              v42 = v41 + a8;
              v43 = v41;
              v41 += 4;
              v44 = _mm_sqrt_ps(
                      _mm_sub_ps(
                        *(__m128 *)(*((_QWORD *)this + 23) + 4 * v42),
                        *(__m128 *)(*((_QWORD *)this + 23) + 4 * v43)));
              *(__m128 *)(*((_QWORD *)this + 24) + 4 * v43) = _mm_and_ps(
                                                                _mm_div_ps(*(__m128 *)(*v36 + 4 * v43), v44),
                                                                _mm_cmpneq_ps(v44, (__m128)0LL));
            }
            while ( v41 + 3 < v12 );
          }
          if ( v41 < v12 )
          {
            if ( v12 - v41 >= 4 )
            {
              v45 = v41 + a8;
              v46 = (_QWORD *)((char *)this + 176);
              do
              {
                v47 = 0.0;
                v48 = v41;
                v49 = fsqrt(*(float *)(*((_QWORD *)this + 23) + 4LL * v45) - *(float *)(*((_QWORD *)this + 23)
                                                                                      + 4LL * v41));
                if ( v49 != 0.0 )
                  v47 = *(float *)(*v46 + 4LL * v41) / v49;
                v50 = 0.0;
                *(float *)(*((_QWORD *)this + 24) + 4LL * v41) = v47;
                v51 = fsqrt(
                        *(float *)(*((_QWORD *)this + 23) + 4LL * v45 + 4)
                      - *(float *)(*((_QWORD *)this + 23) + 4LL * v41 + 4));
                v46 = (_QWORD *)((char *)this + 176);
                if ( v51 != 0.0 )
                  v50 = *(float *)(*v36 + 4LL * v41 + 4) / v51;
                v52 = 0.0;
                *(float *)(*((_QWORD *)this + 24) + 4LL * v41 + 4) = v50;
                v53 = fsqrt(
                        *(float *)(*((_QWORD *)this + 23) + 4LL * v45 + 8)
                      - *(float *)(*((_QWORD *)this + 23) + 4LL * v41 + 8));
                if ( v53 != 0.0 )
                {
                  v46 = (_QWORD *)((char *)this + 176);
                  v52 = *(float *)(*v36 + 4LL * v41 + 8) / v53;
                }
                *(float *)(*((_QWORD *)this + 24) + 4LL * v41 + 8) = v52;
                v54 = 0.0;
                v55 = fsqrt(
                        *(float *)(*((_QWORD *)this + 23) + 4LL * v45 + 12)
                      - *(float *)(*((_QWORD *)this + 23) + 4LL * v41 + 12));
                if ( v55 != 0.0 )
                {
                  v46 = (_QWORD *)((char *)this + 176);
                  v54 = *(float *)(*v36 + 4LL * v41 + 12) / v55;
                }
                v41 += 4;
                v45 += 4;
                *(float *)(*((_QWORD *)this + 24) + 4 * v48 + 12) = v54;
              }
              while ( v41 < v12 - 3 );
            }
            if ( v41 < v12 )
            {
              v56 = v41;
              do
              {
                v57 = fsqrt(
                        *(float *)(*((_QWORD *)this + 23) + 4LL * (v41 + a8))
                      - *(float *)(*((_QWORD *)this + 23) + 4 * v56));
                if ( v57 == 0.0 )
                  v58 = 0.0;
                else
                  v58 = *(float *)(*v36 + 4 * v56) / v57;
                ++v41;
                *(float *)(*((_QWORD *)this + 24) + 4 * v56++) = v58;
              }
              while ( v41 < v12 );
            }
          }
        }
        else
        {
          v59 = 0;
          if ( v12 >= 4 )
          {
            v60 = a8;
            v61 = (char *)this + 176;
            do
            {
              v62 = 0.0;
              v63 = fsqrt(*(float *)(*((_QWORD *)this + 23) + 4LL * v60) - *(float *)(*((_QWORD *)this + 23) + 4LL * v59));
              if ( v63 == 0.0 )
              {
                v64 = v61;
              }
              else
              {
                v64 = (char *)this + 176;
                v62 = *(float *)(*v36 + 4LL * v59) / v63;
              }
              v65 = 0.0;
              *(float *)(*((_QWORD *)this + 24) + 4LL * v59) = v62;
              v66 = fsqrt(
                      *(float *)(*((_QWORD *)this + 23) + 4LL * v60 + 4)
                    - *(float *)(*((_QWORD *)this + 23) + 4LL * v59 + 4));
              if ( v66 != 0.0 )
              {
                v67 = *(_QWORD *)v61;
                v61 = v64;
                v65 = *(float *)(v67 + 4LL * v59 + 4) / v66;
              }
              v68 = 0.0;
              *(float *)(*((_QWORD *)this + 24) + 4LL * v59 + 4) = v65;
              v69 = fsqrt(
                      *(float *)(*((_QWORD *)this + 23) + 4LL * v60 + 8)
                    - *(float *)(*((_QWORD *)this + 23) + 4LL * v59 + 8));
              if ( v69 != 0.0 )
                v68 = *(float *)(*(_QWORD *)v61 + 4LL * v59 + 8) / v69;
              v70 = v59;
              *(float *)(*((_QWORD *)this + 24) + 4LL * v59 + 8) = v68;
              v71 = 0.0;
              v72 = fsqrt(
                      *(float *)(*((_QWORD *)this + 23) + 4LL * v60 + 12)
                    - *(float *)(*((_QWORD *)this + 23) + 4LL * v59 + 12));
              if ( v72 == 0.0 )
                v61 = (char *)this + 176;
              else
                v71 = *(float *)(*(_QWORD *)v61 + 4LL * v59 + 12) / v72;
              v59 += 4;
              v60 += 4;
              *(float *)(*((_QWORD *)this + 24) + 4 * v70 + 12) = v71;
            }
            while ( v59 < v12 - 3 );
          }
          if ( v59 < v12 )
          {
            v73 = v59;
            do
            {
              v74 = fsqrt(
                      *(float *)(*((_QWORD *)this + 23) + 4LL * (v59 + a8))
                    - *(float *)(*((_QWORD *)this + 23) + 4 * v73));
              if ( v74 == 0.0 )
                v75 = 0.0;
              else
                v75 = *(float *)(*((_QWORD *)this + 22) + 4 * v73) / v74;
              ++v59;
              *(float *)(*((_QWORD *)this + 24) + 4 * v73++) = v75;
            }
            while ( v59 < v12 );
          }
        }
        v76 = v12 - 1;
        if ( v12 - 1 > 1 )
        {
          v77 = FLOAT_N3_4028235e38;
          v78 = *((_QWORD *)this + 24);
          v79 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
          v80 = (float)v12 * 0.5;
          if ( v12 - 2 < 4 )
            goto LABEL_104;
          do
          {
            v81 = *(float *)(v78 + 4LL * v16);
            if ( v81 >= *(float *)(v78 + 4LL * v16 - 4)
              && v81 >= *(float *)(v78 + 4LL * v16 + 4)
              && (float)((float)(1.0
                               - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v16 - v80) & v79) * 0.5)
                                       / (float)v12))
                       * v81) > v77 )
            {
              v77 = (float)(1.0
                          - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v16 - v80) & v79) * 0.5) / (float)v12))
                  * v81;
              v23 = v16;
            }
            v82 = *(float *)(v78 + 4LL * v16 + 4);
            if ( v81 <= v82
              && v82 >= *(float *)(v78 + 4LL * v16 + 8)
              && (float)((float)(1.0
                               - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 1) - v80) & v79) * 0.5)
                                       / (float)v12))
                       * v82) > v77 )
            {
              v77 = (float)(1.0
                          - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 1) - v80) & v79) * 0.5)
                                  / (float)v12))
                  * v82;
              v23 = v16 + 1;
            }
            v83 = *(float *)(v78 + 4LL * v16 + 8);
            if ( v82 <= v83
              && v83 >= *(float *)(v78 + 4LL * v16 + 12)
              && (float)((float)(1.0
                               - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 2) - v80) & v79) * 0.5)
                                       / (float)v12))
                       * v83) > v77 )
            {
              v77 = (float)(1.0
                          - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 2) - v80) & v79) * 0.5)
                                  / (float)v12))
                  * v83;
              v23 = v16 + 2;
            }
            v84 = *(float *)(v78 + 4LL * v16 + 12);
            if ( v83 <= v84
              && v84 >= *(float *)(v78 + 4LL * v16 + 16)
              && (float)((float)(1.0
                               - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 3) - v80) & v79) * 0.5)
                                       / (float)v12))
                       * v84) > v77 )
            {
              v77 = (float)(1.0
                          - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(v16 + 3) - v80) & v79) * 0.5)
                                  / (float)v12))
                  * v84;
              v23 = v16 + 3;
            }
            v16 += 4;
          }
          while ( v16 < v12 - 4 );
          if ( v16 < v76 )
          {
LABEL_104:
            do
            {
              v85 = *(float *)(v78 + 4LL * v16);
              if ( v85 >= *(float *)(v78 + 4LL * v16 - 4)
                && v85 >= *(float *)(v78 + 4LL * v16 + 4)
                && (float)((float)(1.0
                                 - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v16 - v80) & v79) * 0.5)
                                         / (float)v12))
                         * v85) > v77 )
              {
                v77 = (float)(1.0
                            - (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v16 - v80) & v79) * 0.5)
                                    / (float)v12))
                    * v85;
                v23 = v16;
              }
              ++v16;
            }
            while ( v16 < v76 );
          }
        }
        *a7 = a5 + v87 * v23;
        return v89;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800504f0  mov     [rsp+arg_8], rdx
0x1800504f5  push    rbx
0x1800504f6  push    rbp
0x1800504f7  push    rsi
0x1800504f8  push    rdi
0x1800504f9  push    r12
0x1800504fb  push    r14
0x1800504fd  push    r15
0x1800504ff  sub     rsp, 90h
0x180050506  mov     r10, [rsp+0C8h+arg_28]
0x18005050e  mov     rbx, rcx
0x180050511  mov     rbp, [rsp+0C8h+arg_20]
0x180050519  mov     esi, r10d
0x18005051c  mov     r15d, [rsp+0C8h+arg_38]
0x180050524  sub     esi, ebp
0x180050526  mov     ecx, [rcx+8]
0x180050529  mov     r11, r9
0x18005052c  mov     r12, r8
0x18005052f  mov     edi, 1
0x180050534  lea     r14d, [rsi+r15]
0x180050538  cmp     ecx, 0BB80h
0x18005053e  jbe     short loc_180050591
0x180050540  add     ecx, 0BB7Fh
0x180050546  mov     eax, 57619F1h
0x18005054b  mul     ecx
0x18005054d  mov     r9d, edx
0x180050550  shr     r9d, 0Ah
0x180050554  mov     [rsp+0C8h+arg_0], r9d
0x18005055c  cmp     r9d, edi
0x18005055f  jl      short loc_180050587
0x180050561  mov     eax, r14d
0x180050564  cdq
0x180050565  idiv    r9d
0x180050568  mov     r14d, eax
0x18005056b  mov     eax, r15d
0x18005056e  cdq
0x18005056f  mov     esi, r14d
0x180050572  idiv    r9d
0x180050575  sub     esi, eax
0x180050577  mov     [rsp+0C8h+arg_38], eax
0x18005057e  mov     r15d, eax
0x180050581  cmp     r9d, 2
0x180050585  jle     short loc_18005059B
0x180050587  mov     eax, 80004005h
0x18005058c  jmp     loc_180050F44
0x180050591  mov     r9d, edi
0x180050594  mov     [rsp+0C8h+arg_0], edi
0x18005059b  mov     [rsp+0C8h+arg_10], r13
0x1800505a3  mov     r13, [rsp+0C8h+arg_30]
0x1800505ab  cmp     r14d, 800h
0x1800505b2  jle     short loc_1800505F2
0x1800505b4  mov     r8, [r13+0]
0x1800505b8  mov     esi, 800h
0x1800505bd  mov     r14d, esi
0x1800505c0  sub     esi, r15d
0x1800505c3  mov     ecx, esi
0x1800505c5  imul    ecx, r9d
0x1800505c9  mov     eax, ecx
0x1800505cb  cdq
0x1800505cc  sub     eax, edx
0x1800505ce  sar     eax, 1
0x1800505d0  movsxd  rdx, eax
0x1800505d3  mov     rax, r8
0x1800505d6  sub     rax, rbp
0x1800505d9  cmp     rax, rdx
0x1800505dc  jle     short loc_1800505EC
0x1800505de  mov     rbp, r8
0x1800505e1  sub     rbp, rdx
0x1800505e4  mov     [rsp+0C8h+arg_20], rbp
0x1800505ec  movsxd  r10, ecx
0x1800505ef  add     r10, rbp
0x1800505f2  movsxd  rdx, dword ptr [rbx+4Ch]
0x1800505f6  add     rdx, [rbx+0D8h]
0x1800505fd  cmp     rbp, rdx
0x180050600  jg      short loc_180050616
0x180050602  cmp     rdx, r10
0x180050605  jg      short loc_180050616
0x180050607  mov     [r13+0], rdx
0x18005060b  xor     r13d, r13d
0x18005060e  mov     eax, r13d
0x180050611  jmp     loc_180050F3C
0x180050616  xor     r13d, r13d
0x180050619  mov     ebp, edi
0x18005061b  mov     eax, r13d
0x18005061e  xchg    ax, ax
0x180050620  cmp     ebp, r14d
0x180050623  jge     short loc_180050631
0x180050625  add     ebp, ebp
0x180050627  inc     eax
0x180050629  cmp     eax, 20h ; ' '
0x18005062c  jl      short loc_180050620
0x18005062e  mov     ebp, r13d
0x180050631  mov     eax, [rbx+98h]
0x180050637  mov     rdx, r11; struct Chunk *
0x18005063a  mov     r8, [rsp+0C8h+arg_20]; __int64
0x180050642  mov     rcx, rbx; this
0x180050645  mov     [rsp+0C8h+var_98], eax; int
0x180050649  mov     rax, [rbx+0A0h]
0x180050650  mov     [rsp+0C8h+var_A0], rax; float *
0x180050655  mov     [rsp+0C8h+var_A8], r9d; int
0x18005065a  mov     r9d, r14d; int
0x18005065d  call    ?ChannelDownMix@CAudioTimeCompression@@IEAAJPEAVChunk@@_JHHPEAMH@Z; CAudioTimeCompression::ChannelDownMix(Chunk *,__int64,int,int,float *,int)
0x180050662  test    eax, eax
0x180050664  js      loc_180050F3C
0x18005066a  mov     rax, [rbx+0B8h]
0x180050671  lea     r9d, [r14-1]
0x180050675  mov     edx, r13d
0x180050678  mov     [rax], r13d
0x18005067b  cmp     r9d, 4
0x18005067f  jl      loc_18005072D
0x180050685  lea     r8d, [r9-3]
0x180050689  nop     dword ptr [rax+00000000h]
0x180050690  mov     rax, [rbx+0A0h]
0x180050697  movsxd  rcx, edx
0x18005069a  add     edx, 4
0x18005069d  movss   xmm0, dword ptr [rax+rcx*4]
0x1800506a2  mov     rax, [rbx+0B8h]
0x1800506a9  mulss   xmm0, xmm0
0x1800506ad  addss   xmm0, dword ptr [rax+rcx*4]
0x1800506b2  movss   dword ptr [rax+rcx*4+4], xmm0
0x1800506b8  mov     rax, [rbx+0A0h]
0x1800506bf  movss   xmm1, dword ptr [rax+rcx*4+4]
0x1800506c5  mov     rax, [rbx+0B8h]
0x1800506cc  mulss   xmm1, xmm1
0x1800506d0  addss   xmm1, dword ptr [rax+rcx*4+4]
0x1800506d6  movss   dword ptr [rax+rcx*4+8], xmm1
0x1800506dc  mov     rax, [rbx+0A0h]
0x1800506e3  movss   xmm0, dword ptr [rax+rcx*4+8]
0x1800506e9  mov     rax, [rbx+0B8h]
0x1800506f0  mulss   xmm0, xmm0
0x1800506f4  addss   xmm0, dword ptr [rax+rcx*4+8]
0x1800506fa  movss   dword ptr [rax+rcx*4+0Ch], xmm0
0x180050700  mov     rax, [rbx+0A0h]
0x180050707  movss   xmm0, dword ptr [rax+rcx*4+0Ch]
0x18005070d  mov     rax, [rbx+0B8h]
0x180050714  mulss   xmm0, xmm0
0x180050718  addss   xmm0, dword ptr [rax+rcx*4+0Ch]
0x18005071e  movss   dword ptr [rax+rcx*4+10h], xmm0
0x180050724  cmp     edx, r8d
0x180050727  jl      loc_180050690
0x18005072d  cmp     edx, r9d
0x180050730  jge     short loc_180050769
0x180050732  movsxd  r8, edx
0x180050735  mov     rax, [rbx+0A0h]
0x18005073c  lea     rcx, ds:0[r8*4]
0x180050744  inc     r8
0x180050747  inc     edx
0x180050749  movss   xmm0, dword ptr [rcx+rax]
0x18005074e  mov     rax, [rbx+0B8h]
0x180050755  mulss   xmm0, xmm0
0x180050759  addss   xmm0, dword ptr [rcx+rax]
0x18005075e  movss   dword ptr [rax+r8*4], xmm0
0x180050764  cmp     edx, r9d
0x180050767  jl      short loc_180050735
0x180050769  mov     eax, ebp
0x18005076b  movsxd  rcx, r14d
0x18005076e  sub     eax, r14d
0x180050771  xor     edx, edx; Val
0x180050773  movsxd  r8, eax
0x180050776  mov     rax, [rbx+0A0h]
0x18005077d  shl     r8, 2; Size
0x180050781  lea     rcx, [rax+rcx*4]; void *
0x180050785  call    memset_0
0x18005078a  mov     eax, [rbx+98h]
0x180050790  mov     r9d, r15d; int
0x180050793  mov     rdx, [rsp+0C8h+arg_8]; struct Chunk *
0x18005079b  mov     r8, r12; __int64
0x18005079e  mov     [rsp+0C8h+var_98], eax; int
0x1800507a2  mov     rcx, rbx; this
0x1800507a5  mov     rax, [rbx+0A8h]
0x1800507ac  mov     [rsp+0C8h+var_A0], rax; float *
0x1800507b1  mov     eax, [rsp+0C8h+arg_0]
0x1800507b8  mov     [rsp+0C8h+var_A8], eax; int
0x1800507bc  call    ?ChannelDownMix@CAudioTimeCompression@@IEAAJPEAVChunk@@_JHHPEAMH@Z; CAudioTimeCompression::ChannelDownMix(Chunk *,__int64,int,int,float *,int)
0x1800507c1  test    eax, eax
0x1800507c3  js      loc_180050F3C
0x1800507c9  mov     eax, ebp
0x1800507cb  movsxd  rcx, r15d
0x1800507ce  sub     eax, r15d
0x1800507d1  xor     edx, edx; Val
0x1800507d3  movsxd  r8, eax
0x1800507d6  mov     rax, [rbx+0A8h]
0x1800507dd  shl     r8, 2; Size
0x1800507e1  lea     rcx, [rax+rcx*4]; void *
0x1800507e5  call    memset_0
0x1800507ea  cmp     ebp, 2
0x1800507ed  jl      loc_180050F37
0x1800507f3  cmp     ebp, [rbx+0C8h]
0x1800507f9  jg      loc_180050F37
0x1800507ff  test    dil, bpl
0x180050802  jnz     loc_180050F37
0x180050808  mov     r12, [rbx+0A0h]
0x18005080f  lea     r14, [rbx+0B0h]
0x180050816  mov     rax, [r14]
0x180050819  movzx   r8d, bp
0x18005081d  mov     rcx, [rbx+80h]
0x180050824  mov     rdx, r12
0x180050827  mov     r15, [rbx+0A8h]
0x18005082e  mov     [rsp+0C8h+var_88], rax
0x180050833  mov     rax, [rbx+88h]
0x18005083a  call    cs:__guard_dispatch_icall_fptr
0x180050840  mov     dword ptr [rsp+0C8h+arg_28], eax
0x180050847  test    eax, eax
0x180050849  jnz     loc_180050930
0x18005084f  mov     rcx, [rbx+80h]
0x180050856  movzx   r8d, bp
0x18005085a  mov     rax, [rbx+88h]
0x180050861  mov     rdx, r15
0x180050864  call    cs:__guard_dispatch_icall_fptr
0x18005086a  mov     dword ptr [rsp+0C8h+arg_28], eax
0x180050871  test    eax, eax
0x180050873  jnz     loc_180050930
0x180050879  movss   xmm0, dword ptr [r12]
0x18005087f  mov     ecx, 2
0x180050884  mulss   xmm0, dword ptr [r15]
0x180050889  mov     rdx, [rsp+0C8h+var_88]
0x18005088e  movss   dword ptr [rdx], xmm0
0x180050892  movss   xmm1, dword ptr [r12+4]
0x180050899  mulss   xmm1, dword ptr [r15+4]
0x18005089f  movss   dword ptr [rdx+4], xmm1
0x1800508a4  cmp     ebp, 3
0x1800508a7  jle     short loc_180050904
0x1800508a9  nop     dword ptr [rax+00000000h]
0x1800508b0  movsxd  rax, ecx
0x1800508b3  add     ecx, 2
0x1800508b6  movss   xmm0, dword ptr [r15+rax*4]
0x1800508bc  mulss   xmm0, dword ptr [r12+rax*4]
0x1800508c2  movss   xmm1, dword ptr [r12+rax*4+4]
0x1800508c9  mulss   xmm1, dword ptr [r15+rax*4+4]
0x1800508d0  addss   xmm1, xmm0
0x1800508d4  movss   dword ptr [rdx+rax*4], xmm1
0x1800508d9  movss   xmm2, dword ptr [r12+rax*4+4]
0x1800508e0  movss   xmm0, dword ptr [r12+rax*4]
0x1800508e6  mulss   xmm2, dword ptr [r15+rax*4]
0x1800508ec  mulss   xmm0, dword ptr [r15+rax*4+4]
0x1800508f3  subss   xmm2, xmm0
0x1800508f7  movss   dword ptr [rdx+rax*4+4], xmm2
0x1800508fd  lea     eax, [rcx+1]
0x180050900  cmp     eax, ebp
0x180050902  jl      short loc_1800508B0
0x180050904  mov     rcx, [rbx+80h]
0x18005090b  movzx   r8d, bp
0x18005090f  mov     rax, [rbx+90h]
0x180050916  call    cs:__guard_dispatch_icall_fptr
0x18005091c  mov     dword ptr [rsp+0C8h+arg_28], eax
0x180050923  test    eax, eax
0x180050925  jnz     short loc_180050930
0x180050927  mov     dword ptr [rsp+0C8h+arg_28], eax
0x18005092e  jmp     short loc_180050936
0x180050930  js      loc_180050F3C
0x180050936  mov     ebp, [rsp+0C8h+arg_38]
0x18005093d  cmp     [rbx], r13d
0x180050940  jz      loc_180050B49
0x180050946  mov     r9d, r13d
0x180050949  cmp     esi, 3
0x18005094c  jle     short loc_18005099A
0x18005094e  xchg    ax, ax
0x180050950  mov     rdx, [rbx+0B8h]
0x180050957  lea     eax, [r9+rbp]
0x18005095b  movsxd  rcx, eax
0x18005095e  mov     rax, [r14]
0x180050961  movsxd  r8, r9d
0x180050964  add     r9d, 4
0x180050968  movups  xmm0, xmmword ptr [rdx+rcx*4]
0x18005096c  subps   xmm0, xmmword ptr [rdx+r8*4]
0x180050971  movups  xmm2, xmmword ptr [rax+r8*4]
0x180050976  mov     rax, [rbx+0C0h]
0x18005097d  sqrtps  xmm1, xmm0
0x180050980  xorps   xmm0, xmm0
0x180050983  divps   xmm2, xmm1
0x180050986  cmpneqps xmm1, xmm0
0x18005098a  andps   xmm2, xmm1
0x18005098d  movups  xmmword ptr [rax+r8*4], xmm2
0x180050992  lea     eax, [r9+3]
0x180050996  cmp     eax, esi
0x180050998  jl      short loc_180050950
0x18005099a  cmp     r9d, esi
0x18005099d  jge     loc_180050CF2
0x1800509a3  mov     eax, esi
0x1800509a5  xorps   xmm1, xmm1
0x1800509a8  sub     eax, r9d
0x1800509ab  cmp     eax, 4
0x1800509ae  jl      loc_180050AE9
0x1800509b4  lea     r11d, [rsi-3]
0x1800509b8  lea     r10d, [r9+rbp]
0x1800509bc  lea     rdx, [rbx+0B0h]
0x1800509c3  nop     dword ptr [rax+00h]
0x1800509c7  nop     word ptr [rax+rax+00000000h]
0x1800509d0  mov     rax, [rbx+0B8h]
0x1800509d7  xorps   xmm3, xmm3
0x1800509da  movsxd  r8, r10d
0x1800509dd  movaps  xmm2, xmm1
0x1800509e0  movsxd  rcx, r9d
0x1800509e3  movss   xmm0, dword ptr [rax+r8*4]
0x1800509e9  subss   xmm0, dword ptr [rax+rcx*4]
0x1800509ee  sqrtss  xmm3, xmm0
0x1800509f2  ucomiss xmm3, xmm1
0x1800509f5  jz      short loc_180050A03
0x1800509f7  mov     rax, [rdx]
0x1800509fa  movss   xmm2, dword ptr [rax+rcx*4]
  ... truncated ...
```
