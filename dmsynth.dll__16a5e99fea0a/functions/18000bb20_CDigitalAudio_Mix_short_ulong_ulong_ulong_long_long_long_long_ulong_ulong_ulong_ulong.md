# CDigitalAudio::Mix(short * *,ulong,ulong,ulong,long,long *,long *,long,ulong,ulong,ulong,ulong)

- ea: `0x18000bb20`
- end: `0x18000c6fe`
- name: `?Mix@CDigitalAudio@@QEAAHPEAPEAFKKKJPEAJ1JKKKK@Z`
- size: `3038`
- prototype: `__int64 __usercall@<rax>(CDigitalAudio *__hidden this@<rcx>, __int16 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int nDenominator, int, int *, void *, int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18000c710`
- `0x18000d3b0`

## callees

- `0x1800014f0`
- `0x18000a4a0`
- `0x18000a660`
- `0x18000a8b0`
- `0x18000aa70`
- `0x18000bb20`
- `0x18000d0f0`
- `0x180013710`
- `0x180013ae0`
- `0x180013fb0`
- `0x180014380`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd08`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd28`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd4a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd85`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be31`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be50`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be6f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd08`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd28`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd4a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000bd85`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be31`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be50`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000be6f`

## pseudocode

```c
__int64 __fastcall CDigitalAudio::Mix(
        CDigitalAudio *this,
        __int16 **a2,
        unsigned int a3,
        int a4,
        unsigned int nDenominator,
        int a6,
        int *a7,
        _DWORD *a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13)
{
  unsigned int v14; // r13d
  __int16 **v15; // rsi
  int v17; // eax
  int v18; // r11d
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  _BYTE *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // ecx
  int v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // eax
  int v34; // ecx
  int v35; // eax
  int v36; // r11d
  int v37; // r15d
  int v38; // eax
  int v39; // ecx
  void *v40; // r12
  __int64 v41; // rbp
  __int64 v42; // rdi
  int v43; // eax
  int v44; // ecx
  int v45; // ebp
  _DWORD *v46; // r11
  unsigned int v47; // eax
  unsigned __int64 *v48; // r10
  unsigned __int64 v49; // r8
  unsigned __int64 v50; // rdx
  __int64 v51; // r9
  __int64 v52; // rcx
  int v53; // ecx
  int v54; // eax
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rdx
  __int64 *v57; // rcx
  unsigned __int64 v58; // rdx
  __int64 v59; // rax
  int v60; // r8d
  __int64 v61; // rax
  int v62; // edx
  int v63; // edi
  int v64; // r8d
  unsigned int v65; // edx
  __int64 v66; // rax
  unsigned __int64 v67; // rcx
  __int64 v68; // r8
  int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 *v72; // rax
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // r8
  __int64 v78; // rcx
  _BYTE *v79; // rax
  __int64 v80; // r8
  __int64 v81; // r9
  unsigned int v82; // r9d
  __m128i v83; // xmm0
  __int64 v84; // rdx
  __m128i v85; // xmm2
  __m128i v86; // xmm2
  __int64 v87; // rax
  unsigned int v88; // r9d
  __m128i v89; // xmm0
  __int64 v90; // rdx
  __m128i v91; // xmm2
  __m128i v92; // xmm2
  __int64 v93; // rax
  int nNumerator; // [rsp+70h] [rbp-108h]
  int v95; // [rsp+74h] [rbp-104h]
  int v96; // [rsp+78h] [rbp-100h]
  int v97; // [rsp+7Ch] [rbp-FCh]
  int v98; // [rsp+80h] [rbp-F8h]
  int v99; // [rsp+84h] [rbp-F4h]
  unsigned int v101; // [rsp+90h] [rbp-E8h]
  unsigned int v103; // [rsp+98h] [rbp-E0h]
  int v104; // [rsp+A0h] [rbp-D8h]
  int v105; // [rsp+B0h] [rbp-C8h] BYREF
  int v106; // [rsp+B4h] [rbp-C4h]

  v14 = nDenominator;
  v15 = a2;
  if ( !nDenominator )
  {
    v17 = *((_DWORD *)this + 14) * CDigitalAudio::PRELToPFRACT(a9);
    *((_DWORD *)this + 16) = v18;
    *((_DWORD *)this + 15) = v17 >> 12;
    *((_DWORD *)this + 32) = a11;
    *((_DWORD *)this + 33) = a12;
    *((_DWORD *)this + 34) = a13;
    return 1;
  }
  v20 = *((_QWORD *)this + 20);
  if ( v20 && *(_DWORD *)(v20 + 68) )
  {
    v21 = *(_QWORD *)(*((_QWORD *)this + 19) + 8LL);
    if ( !*(_BYTE *)(v21 + 51) )
      return 1;
    *(_BYTE *)(v21 + 50) = 1;
    v22 = (__int64 *)*((_QWORD *)this + 19);
    v23 = v22[1];
    if ( !*(_BYTE *)(v23 + 52) )
    {
      v24 = *v22;
      if ( !*v22 )
        v24 = *(_QWORD *)v22[2];
      v25 = *(_QWORD *)(v24 + 8);
      if ( *(_BYTE *)(v25 + 51) )
      {
        v26 = *(_BYTE **)(v25 + 32);
        v27 = (unsigned int)(*(_DWORD *)(v23 + 8) - 1);
        v28 = *(_QWORD *)(v23 + 32);
        if ( *((_BYTE *)this + 32) == 2 )
          *(_BYTE *)(v27 + v28) = *v26;
        else
          *(_WORD *)(v28 + 2 * v27) = *(_WORD *)v26;
        *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 19) + 8LL) + 52LL) = 1;
      }
    }
  }
  if ( !*(_QWORD *)this || !*(_QWORD *)(*(_QWORD *)this + 32LL) )
    return 0;
  v29 = a9 - *((_DWORD *)this + 16);
  *((_DWORD *)this + 16) = a9;
  v30 = -v29;
  if ( v29 > 0 )
    v30 = v29;
  v31 = 2 * v30;
  if ( a6 > 2 * v30 )
    v31 = a6;
  v32 = v31 >> 1;
  if ( v32 )
  {
    v33 = 8 * nDenominator / v32;
    v34 = 512;
    if ( v33 <= 0x200 )
    {
      v34 = v33;
      if ( !v33 )
        v34 = 1;
    }
  }
  else
  {
    v34 = 512;
  }
  nNumerator = (v34 + 3) & 0xFFFFFFFC;
  v35 = CDigitalAudio::PRELToPFRACT(a9);
  v37 = v36 << 8;
  v104 = (*((_DWORD *)this + 14) * v35) >> 12;
  v95 = MulDiv(v104 - *((_DWORD *)this + 15), v36 << 8, nDenominator);
  if ( a4 )
  {
    v38 = MulDiv(*a7 - *a8, v37, nDenominator);
    v39 = a7[1] - a8[1];
    v97 = v38;
    v40 = a8;
    v105 = v38;
    v96 = MulDiv(v39, v37, nDenominator);
    v106 = v96;
  }
  else
  {
    v41 = 0;
    if ( a3 )
    {
      do
      {
        v42 = 4 * v41;
        v43 = MulDiv(a7[v41] - a8[v41], v37, nDenominator);
        v41 = (unsigned int)(v41 + 1);
        *(int *)((char *)&v105 + v42) = v43;
      }
      while ( (unsigned int)v41 < a3 );
      v15 = a2;
      v40 = a8;
      v96 = v106;
      v97 = v105;
    }
    else
    {
      v40 = a8;
      v96 = v106;
      v97 = v105;
    }
  }
  v44 = a4 != 0 ? 0x40 : 0;
  if ( CDigitalAudio::m_sfMMXEnabled && nDenominator > 8 )
    v44 |= 0x10u;
  v45 = v44 | *((unsigned __int8 *)this + 32);
  v101 = 0;
  if ( a10 )
  {
    v45 |= 0x80u;
    v103 = MulDiv(a11 - *((_DWORD *)this + 32), nNumerator, nDenominator);
    v99 = MulDiv(a12 - *((_DWORD *)this + 33), nNumerator, nDenominator);
    v98 = MulDiv(a13 - *((_DWORD *)this + 34), nNumerator, nDenominator);
  }
  else
  {
    v103 = 0;
    v99 = 0;
    v98 = 0;
  }
  v46 = (_DWORD *)((char *)this + 68);
  while ( 1 )
  {
    while ( 1 )
    {
      v47 = v45 & 0xFFFFFFEF;
      if ( v14 > 8 )
        v47 = v45;
      v45 = v47;
      if ( *((_DWORD *)this + 21) )
      {
        v48 = (unsigned __int64 *)((char *)this + 96);
        v49 = *((_QWORD *)this + 11);
        if ( *((_DWORD *)this + 31) || (v50 = *v48, v46 = (_DWORD *)((char *)this + 68), v49 < *v48) )
          v50 = *((_QWORD *)this + 11);
        v51 = ((v50 >> 12) & 0xFFFFFFFE) << 12;
        *((_DWORD *)this + 30) = (v50 >> 12) & 0xFFFFFFFE;
        v52 = *((_QWORD *)this + 13);
        *v46 = v49 - v51;
        if ( (unsigned __int64)(v52 - v51) >= 0x7FFFFFFF )
        {
          v53 = 0x7FFFFFFF;
          v54 = 0;
        }
        else
        {
          v53 = v52 - v51;
          v54 = *(_DWORD *)v48 - v51;
        }
        *((_DWORD *)this + 18) = v54;
        *((_DWORD *)this + 19) = v53;
        v55 = *((_QWORD *)this + 14) - v51;
        v56 = v50 >> 12;
        if ( v55 > 0x7FFFFFFF )
          LODWORD(v55) = 0x7FFFFFFF;
        *((_DWORD *)this + 20) = v55;
        if ( (*((_BYTE *)this + 32) & 2) != 0 )
          LODWORD(v56) = (unsigned int)v56 >> 1;
        *((_QWORD *)this + 6) = *(_QWORD *)(*(_QWORD *)this + 32LL) + 2LL * (unsigned int)v56;
      }
      if ( *((_DWORD *)this + 31) )
      {
        v57 = (__int64 *)*((_QWORD *)this + 19);
        v58 = *((unsigned int *)this + 20);
        if ( v57 )
        {
          v59 = v57[1];
          if ( v59 )
          {
            v60 = *(_DWORD *)(v59 + 8);
            if ( (int)v58 >> 12 >= v60 - 1 )
            {
              v61 = *v57;
              if ( !*v57 && (v61 = *(_QWORD *)v57[2]) == 0 || (v62 = v60 - 1, !*(_BYTE *)(*(_QWORD *)(v61 + 8) + 51LL)) )
                v62 = v60 - 2;
              v58 = (unsigned int)(v62 << 12);
            }
          }
        }
        v63 = *((_DWORD *)this + 17);
        v64 = 0;
      }
      else
      {
        v58 = *((unsigned int *)this + 19);
        v64 = *((_DWORD *)this + 19) - *((_DWORD *)this + 18);
        if ( v64 <= v104 )
          return 0;
        v63 = 0;
        if ( v64 > *((_DWORD *)this + 20) )
          return 0;
      }
      switch ( v45 )
      {
        case 1:
        case 17:
          v65 = CDigitalAudio::MixMulti16(this, v15, a3, v14, nNumerator, &v105, v40, v95, v58, v64);
          break;
        case 2:
        case 18:
          v65 = CDigitalAudio::MixMulti8(this, v15, a3, v14, nNumerator, &v105, v40, v95, v58, v64);
          break;
        case 65:
          v65 = CDigitalAudio::Mix16(this, *v15, v14, nNumerator, v97, v96, (int *)v40, v95, v58, v64);
          break;
        case 66:
          v65 = CDigitalAudio::Mix8(this, *v15, v14, nNumerator, v97, v96, (int *)v40, v95, v58, v64);
          break;
        case 129:
        case 145:
          v65 = CDigitalAudio::MixMulti16Filter(
                  this,
                  v15,
                  a3,
                  v14,
                  nNumerator,
                  &v105,
                  v40,
                  v95,
                  v58,
                  v64,
                  v103,
                  v99,
                  v98);
          v96 = v106;
          goto LABEL_74;
        case 130:
        case 146:
          v65 = CDigitalAudio::MixMulti8Filter(
                  this,
                  v15,
                  a3,
                  v14,
                  nNumerator,
                  &v105,
                  v40,
                  v95,
                  v58,
                  v64,
                  v103,
                  v99,
                  v98);
          v96 = v106;
LABEL_74:
          v97 = v105;
          break;
        case 193:
        case 209:
          v65 = CDigitalAudio::Mix16Filter(
                  this,
                  (__int16 *)v58,
                  v14,
                  nNumerator,
                  v97,
                  v96,
                  (int *)v40,
                  v95,
                  v58,
                  v64,
                  v103,
                  v99,
                  v98);
          break;
        case 194:
        case 210:
          v65 = CDigitalAudio::Mix8Filter(
                  this,
                  (__int16 *)v58,
                  v14,
                  nNumerator,
                  v97,
                  v96,
                  (int *)v40,
                  v95,
                  v58,
                  v64,
                  v103,
                  v99,
                  v98);
          break;
        default:
          return 0;
      }
      if ( *((_DWORD *)this + 21) )
      {
        v66 = *((int *)this + 17);
        *((_QWORD *)this + 6) = *(_QWORD *)(*(_QWORD *)this + 32LL);
        v67 = (unsigned __int64)*((unsigned int *)this + 30) << 12;
        *((_DWORD *)this + 30) = 0;
        *((_QWORD *)this + 11) = v66 + v67;
      }
      if ( *((_DWORD *)this + 31) )
        break;
      if ( v65 >= v14 )
        goto LABEL_107;
      v46 = (_DWORD *)((char *)this + 68);
      v14 -= v65;
      v88 = (v65 << a4) + v101;
      *((_DWORD *)this + 17) += *((_DWORD *)this + 18) - *((_DWORD *)this + 19);
      v101 = v88;
      v89 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v88), 0);
      if ( a3 )
      {
        v90 = 0;
        if ( a3 >= 8 )
        {
          v91 = _mm_unpacklo_epi32(_mm_move_epi64(v89), (__m128i)0LL);
          v92 = _mm_add_epi64(v91, v91);
          do
          {
            *(__m128i *)&v15[v90] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v15[v90]), v92);
            *(__m128i *)&v15[(unsigned int)(v90 + 2)] = _mm_add_epi64(
                                                          v92,
                                                          _mm_loadu_si128((const __m128i *)&v15[(unsigned int)(v90 + 2)]));
            *(__m128i *)&v15[(unsigned int)(v90 + 4)] = _mm_add_epi64(
                                                          _mm_loadu_si128((const __m128i *)&v15[(unsigned int)(v90 + 4)]),
                                                          v92);
            v93 = (unsigned int)(v90 + 6);
            v90 = (unsigned int)(v90 + 8);
            *(__m128i *)&v15[v93] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v15[v93]), v92);
          }
          while ( (unsigned int)v90 < (a3 & 0xFFFFFFF8) );
        }
        for ( ; (unsigned int)v90 < a3; v90 = (unsigned int)(v90 + 1) )
          v15[v90] += v88;
      }
    }
    v68 = *((_QWORD *)this + 21);
    v69 = (*((_DWORD *)this + 17) - v63) >> 12;
    if ( v65 >= v14 )
      break;
    v70 = v69 - 1;
    v71 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 21) = v68 + v70;
    if ( !v71 || !*(_DWORD *)(v71 + 68) )
      return 0;
    *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 19) + 8LL) + 50LL) = 0;
    *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 19) + 8LL) + 51LL) = 0;
    *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 19) + 8LL) + 52LL) = 0;
    v72 = (__int64 *)*((_QWORD *)this + 19);
    v73 = *v72;
    if ( !*v72 )
      v73 = *(_QWORD *)v72[2];
    *((_QWORD *)this + 19) = v73;
    *((_QWORD *)this + 6) = *(_QWORD *)(*(_QWORD *)(v73 + 8) + 32LL);
    v74 = *(_QWORD *)(v73 + 8);
    if ( !*(_BYTE *)(v74 + 51) )
      goto LABEL_107;
    *(_BYTE *)(v74 + 50) = 1;
    v46 = (_DWORD *)((char *)this + 68);
    v75 = (__int64 *)*((_QWORD *)this + 19);
    v76 = *v75;
    if ( !*v75 )
      v76 = *(_QWORD *)v75[2];
    v77 = *(_QWORD *)(v76 + 8);
    if ( *(_BYTE *)(v77 + 51) )
    {
      v78 = v75[1];
      v79 = *(_BYTE **)(v77 + 32);
      v80 = *(_QWORD *)(v78 + 32);
      v81 = (unsigned int)(*(_DWORD *)(v78 + 8) - 1);
      if ( *((_BYTE *)this + 32) == 2 )
        *(_BYTE *)(v81 + v80) = *v79;
      else
        *(_WORD *)(v80 + 2 * v81) = *(_WORD *)v79;
      *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 19) + 8LL) + 52LL) = 1;
    }
    v14 -= v65;
    v82 = (v65 << a4) + v101;
    *((_DWORD *)this + 17) = 0;
    v101 = v82;
    v83 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v82), 0);
    if ( a3 )
    {
      v84 = 0;
      if ( a3 < 8 )
        goto LABEL_111;
      v85 = _mm_unpacklo_epi32(_mm_move_epi64(v83), (__m128i)0LL);
      v86 = _mm_add_epi64(v85, v85);
      do
      {
        *(__m128i *)&v15[v84] = _mm_add_epi64(v86, _mm_loadu_si128((const __m128i *)&v15[v84]));
        *(__m128i *)&v15[(unsigned int)(v84 + 2)] = _mm_add_epi64(
                                                      _mm_loadu_si128((const __m128i *)&v15[(unsigned int)(v84 + 2)]),
                                                      v86);
        *(__m128i *)&v15[(unsigned int)(v84 + 4)] = _mm_add_epi64(
                                                      _mm_loadu_si128((const __m128i *)&v15[(unsigned int)(v84 + 4)]),
                                                      v86);
        v87 = (unsigned int)(v84 + 6);
        v84 = (unsigned int)(v84 + 8);
        *(__m128i *)&v15[v87] = _mm_add_epi64(_mm_loadu_si128((const __m128i *)&v15[v87]), v86);
      }
      while ( (unsigned int)v84 < (a3 & 0xFFFFFFF8) );
      if ( (unsigned int)v84 < a3 )
      {
LABEL_111:
        do
        {
          v15[v84] += v82;
          v84 = (unsigned int)(v84 + 1);
        }
        while ( (unsigned int)v84 < a3 );
      }
    }
  }
  *((_QWORD *)this + 21) = v68 + v69;
LABEL_107:
  *((_DWORD *)this + 15) = v104;
  *((_DWORD *)this + 32) = a11;
  *((_DWORD *)this + 33) = a12;
  *((_DWORD *)this + 34) = a13;
  return 1;
}

```

## disassembly

```asm
0x18000bb20  push    rbx
0x18000bb22  push    rsi
0x18000bb23  push    rdi
0x18000bb24  push    r12
0x18000bb26  push    r13
0x18000bb28  push    r14
0x18000bb2a  sub     rsp, 148h
0x18000bb31  mov     rax, cs:__security_cookie
0x18000bb38  xor     rax, rsp
0x18000bb3b  mov     [rsp+178h+var_48], rax
0x18000bb43  mov     rdi, [rsp+178h+arg_38]
0x18000bb4b  mov     r14d, r8d
0x18000bb4e  mov     r13d, [rsp+178h+nDenominator]
0x18000bb56  mov     rsi, rdx
0x18000bb59  mov     r12, [rsp+178h+arg_30]
0x18000bb61  mov     rbx, rcx
0x18000bb64  mov     [rsp+178h+var_E8], rdi
0x18000bb6c  mov     [rsp+178h+var_F0], r9d
0x18000bb74  mov     qword ptr [rsp+178h+var_E0], rdx
0x18000bb7c  test    r13d, r13d
0x18000bb7f  jnz     short loc_18000BBD0
0x18000bb81  mov     r11d, [rsp+178h+arg_40]
0x18000bb89  mov     ecx, r11d; int
0x18000bb8c  call    ?PRELToPFRACT@CDigitalAudio@@SAJJ@Z; CDigitalAudio::PRELToPFRACT(long)
0x18000bb91  imul    eax, [rbx+38h]
0x18000bb95  mov     [rbx+40h], r11d
0x18000bb99  sar     eax, 0Ch
0x18000bb9c  mov     [rbx+3Ch], eax
0x18000bb9f  mov     eax, [rsp+178h+arg_50]
0x18000bba6  mov     [rbx+80h], eax
0x18000bbac  mov     eax, [rsp+178h+arg_58]
0x18000bbb3  mov     [rbx+84h], eax
0x18000bbb9  mov     eax, [rsp+178h+arg_60]
0x18000bbc0  mov     [rbx+88h], eax
0x18000bbc6  mov     eax, 1
0x18000bbcb  jmp     loc_18000C5E6
0x18000bbd0  mov     rax, [rcx+0A0h]
0x18000bbd7  test    rax, rax
0x18000bbda  jz      short loc_18000BC55
0x18000bbdc  cmp     dword ptr [rax+44h], 0
0x18000bbe0  jz      short loc_18000BC55
0x18000bbe2  mov     rax, [rcx+98h]
0x18000bbe9  mov     rcx, [rax+8]
0x18000bbed  cmp     byte ptr [rcx+33h], 0
0x18000bbf1  jz      short loc_18000BBC6
0x18000bbf3  mov     byte ptr [rcx+32h], 1
0x18000bbf7  mov     rax, [rbx+98h]
0x18000bbfe  mov     rdx, [rax+8]
0x18000bc02  cmp     byte ptr [rdx+34h], 0
0x18000bc06  jnz     short loc_18000BC55
0x18000bc08  mov     rcx, [rax]
0x18000bc0b  test    rcx, rcx
0x18000bc0e  jnz     short loc_18000BC17
0x18000bc10  mov     rax, [rax+10h]
0x18000bc14  mov     rcx, [rax]
0x18000bc17  mov     r8, [rcx+8]
0x18000bc1b  cmp     byte ptr [r8+33h], 0
0x18000bc20  jz      short loc_18000BC55
0x18000bc22  mov     ecx, [rdx+8]
0x18000bc25  mov     rax, [r8+20h]
0x18000bc29  dec     ecx
0x18000bc2b  cmp     byte ptr [rbx+20h], 2
0x18000bc2f  mov     r8, [rdx+20h]
0x18000bc33  jnz     short loc_18000BC3E
0x18000bc35  movzx   eax, byte ptr [rax]
0x18000bc38  mov     [rcx+r8], al
0x18000bc3c  jmp     short loc_18000BC46
0x18000bc3e  movzx   eax, word ptr [rax]
0x18000bc41  mov     [r8+rcx*2], ax
0x18000bc46  mov     rax, [rbx+98h]
0x18000bc4d  mov     rcx, [rax+8]
0x18000bc51  mov     byte ptr [rcx+34h], 1
0x18000bc55  mov     rax, [rbx]
0x18000bc58  mov     [rsp+178h+arg_18], rbp
0x18000bc60  mov     [rsp+178h+var_38], r15
0x18000bc68  test    rax, rax
0x18000bc6b  jz      def_18000BFFE; jumptable 000000018000BFFE default case, cases 3-16,19-64,67-128,131-144,147-192,195-208
0x18000bc71  cmp     qword ptr [rax+20h], 0
0x18000bc76  jz      def_18000BFFE; jumptable 000000018000BFFE default case, cases 3-16,19-64,67-128,131-144,147-192,195-208
0x18000bc7c  mov     r8d, [rsp+178h+arg_40]
0x18000bc84  mov     ecx, r8d
0x18000bc87  sub     ecx, [rbx+40h]
0x18000bc8a  mov     eax, ecx
0x18000bc8c  mov     [rbx+40h], r8d
0x18000bc90  neg     eax
0x18000bc92  cmovs   eax, ecx
0x18000bc95  lea     ecx, [rax+rax]
0x18000bc98  cmp     [rsp+178h+arg_28], ecx
0x18000bc9f  cmovg   ecx, [rsp+178h+arg_28]
0x18000bca7  shr     ecx, 1
0x18000bca9  jz      short loc_18000BCCE
0x18000bcab  xor     edx, edx
0x18000bcad  lea     eax, ds:0[r13*8]
0x18000bcb5  div     ecx
0x18000bcb7  mov     ecx, 200h
0x18000bcbc  cmp     eax, ecx
0x18000bcbe  ja      short loc_18000BCD3
0x18000bcc0  mov     ecx, eax
0x18000bcc2  cmp     eax, 1
0x18000bcc5  jnb     short loc_18000BCD3
0x18000bcc7  mov     ecx, 1
0x18000bccc  jmp     short loc_18000BCD3
0x18000bcce  mov     ecx, 200h
0x18000bcd3  lea     r11d, [rcx+3]
0x18000bcd7  mov     ecx, r8d; int
0x18000bcda  and     r11d, 0FFFFFFFCh
0x18000bcde  mov     [rsp+178h+nNumerator], r11d
0x18000bce3  call    ?PRELToPFRACT@CDigitalAudio@@SAJJ@Z; CDigitalAudio::PRELToPFRACT(long)
0x18000bce8  imul    eax, [rbx+38h]
0x18000bcec  mov     r15d, r11d
0x18000bcef  shl     r15d, 8
0x18000bcf3  mov     r8d, r13d; nDenominator
0x18000bcf6  mov     edx, r15d; nNumerator
0x18000bcf9  sar     eax, 0Ch
0x18000bcfc  mov     ecx, eax
0x18000bcfe  mov     [rsp+178h+var_D8], eax
0x18000bd05  sub     ecx, [rbx+3Ch]; nNumber
0x18000bd08  call    cs:__imp_MulDiv
0x18000bd0e  cmp     [rsp+178h+var_F0], 0
0x18000bd16  mov     [rsp+178h+var_104], eax
0x18000bd1a  jz      short loc_18000BD5D
0x18000bd1c  mov     ecx, [r12]
0x18000bd20  mov     r8d, r13d; nDenominator
0x18000bd23  sub     ecx, [rdi]; nNumber
0x18000bd25  mov     edx, r15d; nNumerator
0x18000bd28  call    cs:__imp_MulDiv
0x18000bd2e  mov     ecx, [r12+4]
0x18000bd33  mov     r8d, r13d; nDenominator
0x18000bd36  sub     ecx, [rdi+4]; nNumber
0x18000bd39  mov     edx, r15d; nNumerator
0x18000bd3c  mov     [rsp+178h+var_FC], eax
0x18000bd40  mov     r12, rdi
0x18000bd43  mov     [rsp+178h+var_C8], eax
0x18000bd4a  call    cs:__imp_MulDiv
0x18000bd50  mov     [rsp+178h+var_100], eax
0x18000bd54  mov     [rsp+178h+var_C4], eax
0x18000bd5b  jmp     short loc_18000BDDC
0x18000bd5d  xor     ebp, ebp
0x18000bd5f  test    r14d, r14d
0x18000bd62  jz      short loc_18000BDC3
0x18000bd64  mov     rsi, rdi
0x18000bd67  nop     word ptr [rax+rax+00000000h]
0x18000bd70  lea     rdi, ds:0[rbp*4]
0x18000bd78  mov     r8d, r13d; nDenominator
0x18000bd7b  mov     ecx, [rdi+r12]
0x18000bd7f  mov     edx, r15d; nNumerator
0x18000bd82  sub     ecx, [rdi+rsi]; nNumber
0x18000bd85  call    cs:__imp_MulDiv
0x18000bd8b  inc     ebp
0x18000bd8d  mov     [rsp+rdi+178h+var_C8], eax
0x18000bd94  cmp     ebp, r14d
0x18000bd97  jb      short loc_18000BD70
0x18000bd99  mov     r8d, [rsp+178h+var_C4]
0x18000bda1  mov     edx, [rsp+178h+var_C8]
0x18000bda8  mov     rsi, qword ptr [rsp+178h+var_E0]
0x18000bdb0  mov     r12, [rsp+178h+var_E8]
0x18000bdb8  mov     [rsp+178h+var_100], r8d
0x18000bdbd  mov     [rsp+178h+var_FC], edx
0x18000bdc1  jmp     short loc_18000BDDC
0x18000bdc3  mov     eax, [rsp+178h+var_C4]
0x18000bdca  mov     r12, rdi
0x18000bdcd  mov     [rsp+178h+var_100], eax
0x18000bdd1  mov     eax, [rsp+178h+var_C8]
0x18000bdd8  mov     [rsp+178h+var_FC], eax
0x18000bddc  mov     eax, [rsp+178h+var_F0]
0x18000bde3  neg     eax
0x18000bde5  sbb     ecx, ecx
0x18000bde7  and     ecx, 40h
0x18000bdea  cmp     cs:?m_sfMMXEnabled@CDigitalAudio@@0HA, 0; int CDigitalAudio::m_sfMMXEnabled
0x18000bdf1  jz      short loc_18000BDFC
0x18000bdf3  cmp     r13d, 8
0x18000bdf7  jbe     short loc_18000BDFC
0x18000bdf9  or      ecx, 10h
0x18000bdfc  movzx   ebp, byte ptr [rbx+20h]
0x18000be00  or      ebp, ecx
0x18000be02  mov     dword ptr [rsp+178h+var_E8], 0
0x18000be0d  cmp     [rsp+178h+arg_48], 0
0x18000be15  jz      short loc_18000BE7E
0x18000be17  mov     ecx, [rsp+178h+arg_50]
0x18000be1e  mov     r8d, r13d; nDenominator
0x18000be21  mov     edi, [rsp+178h+nNumerator]
0x18000be25  bts     ebp, 7
0x18000be29  sub     ecx, [rbx+80h]; nNumber
0x18000be2f  mov     edx, edi; nNumerator
0x18000be31  call    cs:__imp_MulDiv
0x18000be37  mov     ecx, [rsp+178h+arg_58]
0x18000be3e  mov     r8d, r13d; nDenominator
0x18000be41  sub     ecx, [rbx+84h]; nNumber
0x18000be47  mov     edx, edi; nNumerator
0x18000be49  mov     [rsp+178h+var_E0], eax
0x18000be50  call    cs:__imp_MulDiv
0x18000be56  mov     ecx, [rsp+178h+arg_60]
0x18000be5d  mov     r8d, r13d; nDenominator
0x18000be60  sub     ecx, [rbx+88h]; nNumber
0x18000be66  mov     edx, edi; nNumerator
0x18000be68  mov     [rsp+178h+var_F4], eax
0x18000be6f  call    cs:__imp_MulDiv
0x18000be75  mov     [rsp+178h+var_F8], eax
0x18000be7c  jmp     short loc_18000BE9F
0x18000be7e  mov     [rsp+178h+var_E0], 0
0x18000be89  mov     [rsp+178h+var_F4], 0
0x18000be94  mov     [rsp+178h+var_F8], 0
0x18000be9f  lea     r11, [rbx+44h]
0x18000bea3  mov     eax, ebp
0x18000bea5  lea     r10, cs:180000000h
0x18000beac  and     eax, 0FFFFFFEFh
0x18000beaf  mov     edi, 7FFFFFFFh
0x18000beb4  cmp     r13d, 8
0x18000beb8  cmova   eax, ebp
0x18000bebb  cmp     dword ptr [rbx+54h], 0
0x18000bebf  mov     ebp, eax
0x18000bec1  jz      loc_18000BF58
0x18000bec7  cmp     dword ptr [rbx+7Ch], 0
0x18000becb  lea     r10, [rbx+60h]
0x18000becf  mov     r8, [rbx+58h]
0x18000bed3  jnz     short loc_18000BEE1
0x18000bed5  mov     rdx, [r10]
0x18000bed8  lea     r11, [rbx+44h]
0x18000bedc  cmp     r8, rdx
0x18000bedf  jnb     short loc_18000BEE4
0x18000bee1  mov     rdx, r8
0x18000bee4  mov     rax, rdx
0x18000bee7  shr     rax, 0Ch
0x18000beeb  and     eax, 0FFFFFFFEh
0x18000beee  mov     ecx, eax
0x18000bef0  mov     r9d, eax
0x18000bef3  shl     r9, 0Ch
0x18000bef7  sub     r8d, r9d
0x18000befa  mov     [rbx+78h], ecx
0x18000befd  mov     rcx, [rbx+68h]
0x18000bf01  mov     rax, rcx
0x18000bf04  mov     [r11], r8d
0x18000bf07  sub     rax, r9
0x18000bf0a  cmp     rax, rdi
0x18000bf0d  jnb     short loc_18000BF1A
0x18000bf0f  mov     eax, [r10]
0x18000bf12  sub     ecx, r9d
0x18000bf15  sub     eax, r9d
0x18000bf18  jmp     short loc_18000BF1E
0x18000bf1a  mov     ecx, edi
0x18000bf1c  xor     eax, eax
0x18000bf1e  mov     [rbx+48h], eax
0x18000bf21  mov     [rbx+4Ch], ecx
0x18000bf24  mov     rax, [rbx+70h]
0x18000bf28  sub     rax, r9
0x18000bf2b  shr     rdx, 0Ch
0x18000bf2f  cmp     rax, rdi
0x18000bf32  cmova   eax, edi
0x18000bf35  mov     [rbx+50h], eax
0x18000bf38  test    byte ptr [rbx+20h], 2
0x18000bf3c  jz      short loc_18000BF40
0x18000bf3e  shr     edx, 1
0x18000bf40  mov     rax, [rbx]
0x18000bf43  lea     r10, cs:180000000h
0x18000bf4a  mov     edx, edx
0x18000bf4c  mov     rcx, [rax+20h]
0x18000bf50  lea     rax, [rcx+rdx*2]
0x18000bf54  mov     [rbx+30h], rax
0x18000bf58  cmp     dword ptr [rbx+7Ch], 0
0x18000bf5c  jz      short loc_18000BFB8
0x18000bf5e  mov     rcx, [rbx+98h]
0x18000bf65  mov     edx, [rbx+50h]
0x18000bf68  test    rcx, rcx
0x18000bf6b  jz      short loc_18000BFB0
0x18000bf6d  mov     rax, [rcx+8]
0x18000bf71  test    rax, rax
0x18000bf74  jz      short loc_18000BFB0
0x18000bf76  mov     r8d, [rax+8]
0x18000bf7a  mov     eax, edx
0x18000bf7c  sar     eax, 0Ch
0x18000bf7f  lea     r9d, [r8-1]
0x18000bf83  cmp     eax, r9d
0x18000bf86  jl      short loc_18000BFB0
0x18000bf88  mov     rax, [rcx]
0x18000bf8b  test    rax, rax
0x18000bf8e  jnz     short loc_18000BF9C
0x18000bf90  mov     rax, [rcx+10h]
0x18000bf94  mov     rax, [rax]
0x18000bf97  test    rax, rax
0x18000bf9a  jz      short loc_18000BFA9
0x18000bf9c  mov     rax, [rax+8]
0x18000bfa0  mov     edx, r9d
0x18000bfa3  cmp     byte ptr [rax+33h], 0
0x18000bfa7  jnz     short loc_18000BFAD
0x18000bfa9  lea     edx, [r8-2]
0x18000bfad  shl     edx, 0Ch
0x18000bfb0  mov     edi, [rbx+44h]
0x18000bfb3  xor     r8d, r8d
0x18000bfb6  jmp     short loc_18000BFDC
0x18000bfb8  mov     edx, [rbx+4Ch]; __int16 *
0x18000bfbb  mov     r8d, edx
0x18000bfbe  sub     r8d, [rbx+48h]
0x18000bfc2  cmp     r8d, [rsp+178h+var_D8]
0x18000bfca  jle     def_18000BFFE; jumptable 000000018000BFFE default case, cases 3-16,19-64,67-128,131-144,147-192,195-208
0x18000bfd0  xor     edi, edi
0x18000bfd2  cmp     r8d, [rbx+50h]
0x18000bfd6  jg      def_18000BFFE; jumptable 000000018000BFFE default case, cases 3-16,19-64,67-128,131-144,147-192,195-208
0x18000bfdc  lea     eax, [rbp-1]; switch 210 cases
0x18000bfdf  cmp     eax, 0D1h
0x18000bfe4  ja      def_18000BFFE; jumptable 000000018000BFFE default case, cases 3-16,19-64,67-128,131-144,147-192,195-208
  ... truncated ...
```
