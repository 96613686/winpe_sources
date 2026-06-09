# Scanner::Scan(void)

- ea: `0x18001f400`
- end: `0x1800207bc`
- name: `?Scan@Scanner@@QEAA?AW4tokens@@XZ`
- size: `5052`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18001d590`
- `0x18001e880`
- `0x1800207c4`
- `0x1800209c0`
- `0x1800230f0`
- `0x180024f88`
- `0x1800255d0`
- `0x18002bf20`
- `0x18002bfe4`
- `0x18002c194`
- `0x18002c30c`
- `0x18002c400`
- `0x18002ce60`
- `0x18003fff8`
- `0x180068f2c`
- `0x18006db48`
- `0x18006e174`
- `0x180074520`
- `0x180087fd0`
- `0x1800880ac`
- `0x1800910d0`

## callees

- `0x180016498`
- `0x18001f400`
- `0x1800210b0`
- `0x18002d340`
- `0x18002d720`
- `0x18002f050`
- `0x18002f0f0`
- `0x18002f114`
- `0x180034f10`
- `0x1800352f0`
- `0x1800357cc`
- `0x180035dc0`
- `0x180035f90`
- `0x18003a0e0`
- `0x180052840`
- `0x180052b74`
- `0x180053044`
- `0x18007463c`
- `0x1800746b8`
- `0x180074be8`
- `0x180074d08`
- `0x180094282`
- `0x180096010`

## import_xrefs

- `msvcrt!malloc` at `0x18001ff53`
- `msvcrt!malloc` at `0x18001ff53`

## pseudocode

```c
__int64 __fastcall Scanner::Scan(__int64 a1, unsigned __int64 a2)
{
  __m128i v2; // xmm0
  int v4; // r15d
  __int16 v5; // r10
  __int64 v6; // r8
  unsigned __int16 *v7; // rax
  __int64 v8; // rsi
  unsigned __int8 BigCharType; // al
  __int64 result; // rax
  unsigned __int16 *v11; // rsi
  __int64 v12; // rax
  unsigned __int8 BigCharFlags; // al
  unsigned __int16 *v14; // r14
  __int64 v15; // rbp
  __int64 v16; // rcx
  _QWORD *v17; // rax
  unsigned __int16 *v18; // rsi
  __int64 v19; // rax
  unsigned __int8 v20; // al
  _DWORD *v21; // rcx
  _WORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int16 *v25; // rax
  const unsigned __int16 *v26; // r8
  int v27; // r10d
  __int16 v28; // ax
  unsigned __int16 *v29; // rdx
  int v30; // eax
  char v31; // r9
  __m128i v32; // xmm2
  __int16 v33; // ax
  __int16 *v34; // rcx
  __int16 v35; // ax
  bool v36; // zf
  _WORD *v37; // rax
  _WORD *v38; // rcx
  _WORD *v39; // rax
  _WORD *v40; // rax
  __int64 v41; // rdx
  unsigned __int16 *v42; // rcx
  Scanner *v43; // rcx
  double v44; // xmm1_8
  int v45; // eax
  int v46; // ecx
  _WORD *v47; // rax
  _WORD *v48; // rax
  unsigned __int16 *v49; // rax
  __int16 v50; // ax
  _WORD *v51; // rax
  _WORD *v52; // rax
  _WORD *v53; // rcx
  int v54; // ebp
  int v55; // ebp
  unsigned __int16 *v56; // rax
  _WORD *v57; // rax
  _WORD *v58; // rax
  int v59; // eax
  _WORD *v60; // rcx
  _DWORD *v61; // rcx
  _WORD *v62; // rax
  const unsigned __int16 *v63; // rax
  __int64 i; // rax
  size_t v65; // rsi
  char *v66; // rax
  _WORD *v67; // rcx
  _WORD *v68; // rax
  int v69; // eax
  __int64 v70; // rcx
  int v71; // eax
  __int64 v72; // r8
  __int64 v73; // rax
  _WORD *v74; // rax
  _WORD *v75; // rax
  unsigned __int16 v76; // cx
  int v77; // ecx
  Scanner *v78; // rcx
  int v79; // ecx
  int v80; // eax
  Scanner *v81; // rcx
  Scanner *v82; // rcx
  int v83; // r9d
  char v84; // bp
  int v85; // esi
  unsigned int v86; // r11d
  int v87; // r11d
  int v88; // r9d
  unsigned __int16 v89; // cx
  unsigned __int16 v90; // cx
  __int128 v91; // [rsp+30h] [rbp-58h] BYREF
  __int64 v92; // [rsp+40h] [rbp-48h]
  __int64 v93; // [rsp+90h] [rbp+8h] BYREF
  __int64 v94; // [rsp+98h] [rbp+10h]
  unsigned __int16 *v95; // [rsp+A0h] [rbp+18h] BYREF

  *(_DWORD *)(a1 + 96) &= ~8u;
  v4 = 1;
LABEL_2:
  v5 = 62;
LABEL_3:
  v6 = 45;
  while ( 1 )
  {
    if ( (*(_BYTE *)(a1 + 96) & 0x20) != 0
      && *(int *)(a1 + 100) <= (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 16)) >> 1 )
    {
      result = 127;
      **(_DWORD **)(a1 + 8) = 127;
      return result;
    }
    v7 = *(unsigned __int16 **)(a1 + 40);
    *(_QWORD *)(a1 + 32) = v7;
    v8 = *v7;
    *(_QWORD *)(a1 + 40) = v7 + 1;
    if ( (unsigned __int16)v8 >= 0x80u )
    {
      BigCharType = GetBigCharType(v8);
      v6 = 45;
      v5 = 62;
    }
    else
    {
      BigCharType = *((_BYTE *)&qword_1800A0550 + v8);
    }
    if ( BigCharType == 4 )
      goto LABEL_2;
    if ( BigCharType != 9 )
    {
      if ( BigCharType == 6 )
      {
LABEL_23:
        *(_QWORD *)(a1 + 40) -= 2LL;
        return Scanner::ScanIdentifier(a1, a2, v6);
      }
      a2 = (unsigned int)v8;
      switch ( BigCharType )
      {
        case 1u:
          *(_QWORD *)(a1 + 40) -= 2LL;
          if ( *(_DWORD *)(a1 + 80) )
            Scanner::Error((Scanner *)a1, 1029);
          **(_DWORD **)(a1 + 8) = 127;
          return 127;
        case 2u:
        case 0x1Fu:
          goto LABEL_23;
        case 3u:
          return Scanner::ScanNumericConstant(a1, (unsigned int)v8, 1);
        case 5u:
          if ( (_DWORD)v8 == 13 )
          {
            v22 = *(_WORD **)(a1 + 40);
            if ( *v22 == 10 )
              *(_QWORD *)(a1 + 40) = v22 + 1;
          }
          if ( (*(_BYTE *)(a1 + 96) & 0x10) == 0 )
          {
            if ( *(_QWORD *)(a1 + 384) )
            {
              a2 = *(_QWORD *)(a1 + 392);
            }
            else
            {
              v65 = *(int *)(a1 + 68);
              v66 = (char *)malloc(v65);
              *(_QWORD *)(a1 + 392) = v66;
              a2 = (unsigned __int64)v66;
              *(_QWORD *)(a1 + 384) = v66;
              if ( !v66 )
                Scanner::Error((Scanner *)a1, 1001);
              *(_QWORD *)(a1 + 400) = &v66[v65];
            }
            v23 = (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 24)) >> 1;
            if ( (v23 & 0xFFFFFF80) != 0 )
            {
              if ( (v23 & 0xFFFFC000) != 0 )
              {
                if ( (v23 & 0xFFE00000) != 0 )
                {
                  if ( (v23 & 0xF0000000) != 0 )
                  {
                    *(_BYTE *)a2 = ((int)v23 >> 28) & 0xF;
                    a2 = ++*(_QWORD *)(a1 + 392);
                  }
                  *(_BYTE *)a2 = ((int)v23 >> 21) & 0x7F;
                  a2 = ++*(_QWORD *)(a1 + 392);
                }
                *(_BYTE *)a2 = ((int)v23 >> 14) & 0x7F;
                a2 = ++*(_QWORD *)(a1 + 392);
              }
              *(_BYTE *)a2 = ((int)v23 >> 7) & 0x7F;
              a2 = ++*(_QWORD *)(a1 + 392);
            }
            *(_BYTE *)a2 = v23 | 0x80;
            v24 = *(_QWORD *)(a1 + 24);
            ++*(_QWORD *)(a1 + 392);
            ++*(_DWORD *)(a1 + 408);
            *(_QWORD *)(a1 + 48) = v24;
            *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 40);
          }
          *(_DWORD *)(a1 + 96) |= 8u;
          goto LABEL_2;
        case 7u:
          *(_QWORD *)(a1 + 40) -= 2LL;
          result = Scanner::ScanIdentifier(a1, (unsigned int)v8, v6);
          if ( (_DWORD)result == 126 )
          {
            if ( (*(_BYTE *)(a1 + 96) & 0x10) == 0 )
              Scanner::Error((Scanner *)a1, 1014);
            v61 = *(_DWORD **)(a1 + 8);
            *(_QWORD *)(a1 + 40) += 2LL;
            *v61 = 126;
          }
          return result;
        case 0xBu:
          **(_DWORD **)(a1 + 8) = 118;
          v39 = *(_WORD **)(a1 + 40);
          if ( *v39 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v39 + 1;
            **(_DWORD **)(a1 + 8) = 102;
            v40 = *(_WORD **)(a1 + 40);
            if ( *v40 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v40 + 1;
              **(_DWORD **)(a1 + 8) = 104;
            }
          }
          return **(unsigned int **)(a1 + 8);
        case 0xCu:
        case 0xDu:
          return Scanner::ScanStringConstant(a1, (unsigned int)v8, v6);
        case 0xEu:
          **(_DWORD **)(a1 + 8) = 116;
          v74 = *(_WORD **)(a1 + 40);
          if ( *v74 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v74 + 1;
            **(_DWORD **)(a1 + 8) = 87;
          }
          return **(unsigned int **)(a1 + 8);
        case 0xFu:
          **(_DWORD **)(a1 + 8) = 100;
          v52 = *(_WORD **)(a1 + 40);
          if ( *v52 == 38 )
          {
            *(_QWORD *)(a1 + 40) = v52 + 1;
            **(_DWORD **)(a1 + 8) = 97;
          }
          else if ( *v52 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v52 + 1;
            **(_DWORD **)(a1 + 8) = 88;
            return **(unsigned int **)(a1 + 8);
          }
          return **(unsigned int **)(a1 + 8);
        case 0x10u:
          result = 121;
          **(_DWORD **)(a1 + 8) = 121;
          return result;
        case 0x11u:
          result = 77;
          **(_DWORD **)(a1 + 8) = 77;
          return result;
        case 0x12u:
          **(_DWORD **)(a1 + 8) = 112;
          v38 = *(_WORD **)(a1 + 40);
          if ( *v38 == 43 )
          {
            *(_QWORD *)(a1 + 40) = v38 + 1;
            **(_DWORD **)(a1 + 8) = 119;
          }
          else if ( *v38 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v38 + 1;
            **(_DWORD **)(a1 + 8) = 83;
            return **(unsigned int **)(a1 + 8);
          }
          return **(unsigned int **)(a1 + 8);
        case 0x13u:
          **(_DWORD **)(a1 + 8) = 113;
          v51 = *(_WORD **)(a1 + 40);
          if ( *v51 == 45 )
          {
            *(_QWORD *)(a1 + 40) = v51 + 1;
            **(_DWORD **)(a1 + 8) = 120;
            if ( (*(_BYTE *)(a1 + 64) & 1) != 0 )
            {
              v53 = *(_WORD **)(a1 + 40);
              v54 = 0;
              if ( (_WORD)v6 == *v53 )
              {
                do
                  ++v54;
                while ( (_WORD)v6 == v53[v54] );
              }
              if ( v5 == v53[v54] )
              {
                v55 = v54 + 1;
                v56 = (unsigned __int16 *)PchSkipWhiteSpace(&v53[v55]);
                if ( GetCharType(*v56) == 1 )
                {
                  **(_DWORD **)(a1 + 8) = 127;
                  return **(unsigned int **)(a1 + 8);
                }
                if ( *PchSkipWhiteSpace((const unsigned __int16 *)(*(_QWORD *)(a1 + 40) + 2LL * v55)) == 125 )
                {
                  v63 = PchSkipWhiteSpace((const unsigned __int16 *)(*(_QWORD *)(a1 + 40) + 2LL * v55));
                  if ( GetCharType(v63[1]) == 5 )
                  {
                    for ( i = *(_QWORD *)(a1 + 40); v55 > 0; i += 2 )
                      --v55;
                    *(_QWORD *)(a1 + 40) = i;
                    goto LABEL_2;
                  }
                }
              }
            }
          }
          else if ( *v51 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v51 + 1;
            **(_DWORD **)(a1 + 8) = 84;
          }
          return **(unsigned int **)(a1 + 8);
        case 0x14u:
          **(_DWORD **)(a1 + 8) = 114;
          v62 = *(_WORD **)(a1 + 40);
          if ( *v62 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v62 + 1;
            **(_DWORD **)(a1 + 8) = 85;
          }
          return **(unsigned int **)(a1 + 8);
        case 0x15u:
          **(_DWORD **)(a1 + 8) = 115;
          a2 = *(_QWORD *)(a1 + 40);
          v33 = *(_WORD *)a2;
          if ( *(_WORD *)a2 != 47 )
          {
            if ( v33 != 42 )
            {
              if ( v33 == 61 )
              {
                *(_QWORD *)(a1 + 40) = a2 + 2;
                **(_DWORD **)(a1 + 8) = 86;
              }
              return **(unsigned int **)(a1 + 8);
            }
            *(_QWORD *)(a1 + 40) = a2 + 2;
            if ( *(_WORD *)(a2 + 2) != 64 || (*(_BYTE *)(a1 + 96) & 0x10) != 0 )
              goto LABEL_145;
            v69 = Scanner::FCcOn((Scanner *)a1);
            *(_QWORD *)(a1 + 40) = a2 + 4;
            v6 = *(unsigned __int16 *)(a2 + 4);
            if ( v69 )
            {
              if ( (unsigned __int16)v6 >= 0x80u || (*((_BYTE *)&qword_1800A0990 + v6) & 2) == 0 )
                goto LABEL_3;
              v6 = 45;
              goto LABEL_13;
            }
            if ( (_WORD)v6 == 99 )
            {
              *(_QWORD *)(a1 + 40) = a2 + 6;
              if ( *(_WORD *)(a2 + 6) == 99 )
              {
                *(_QWORD *)(a1 + 40) = a2 + 8;
                if ( *(_WORD *)(a2 + 8) == 95 )
                {
                  *(_QWORD *)(a1 + 40) = a2 + 10;
                  if ( *(_WORD *)(a2 + 10) == 111 )
                  {
                    *(_QWORD *)(a1 + 40) = a2 + 12;
                    if ( *(_WORD *)(a2 + 12) == 110 )
                    {
                      *(_QWORD *)(a1 + 40) = a2 + 14;
                      v70 = *(unsigned __int16 *)(a2 + 14);
                      if ( (unsigned __int16)v70 >= 0x80u || (*((_BYTE *)&qword_1800A0990 + v70) & 1) == 0 )
                        goto LABEL_22;
                    }
                  }
                }
              }
            }
LABEL_145:
            v59 = Scanner::SkipComment(a1, a2, v6);
            **(_DWORD **)(a1 + 8) = v59;
            if ( v59 )
              return **(unsigned int **)(a1 + 8);
            goto LABEL_2;
          }
          v34 = (__int16 *)(a2 + 2);
          *(_QWORD *)(a1 + 40) = a2 + 2;
          if ( *(_WORD *)(a2 + 2) != 64 || (*(_BYTE *)(a1 + 96) & 0x10) != 0 )
            goto LABEL_63;
          v71 = Scanner::FCcOn((Scanner *)a1);
          v34 = (__int16 *)(a2 + 4);
          *(_QWORD *)(a1 + 40) = a2 + 4;
          v72 = *(unsigned __int16 *)(a2 + 4);
          if ( !v71 )
          {
            if ( (_WORD)v72 == 99 )
            {
              v34 = (__int16 *)(a2 + 6);
              *(_QWORD *)(a1 + 40) = a2 + 6;
              if ( *(_WORD *)(a2 + 6) == 99 )
              {
                v34 = (__int16 *)(a2 + 8);
                *(_QWORD *)(a1 + 40) = a2 + 8;
                if ( *(_WORD *)(a2 + 8) == 95 )
                {
                  v34 = (__int16 *)(a2 + 10);
                  *(_QWORD *)(a1 + 40) = a2 + 10;
                  if ( *(_WORD *)(a2 + 10) == 111 )
                  {
                    v34 = (__int16 *)(a2 + 12);
                    *(_QWORD *)(a1 + 40) = a2 + 12;
                    if ( *(_WORD *)(a2 + 12) == 110 )
                    {
                      v34 = (__int16 *)(a2 + 14);
                      *(_QWORD *)(a1 + 40) = a2 + 14;
                      v73 = *(unsigned __int16 *)(a2 + 14);
                      if ( (unsigned __int16)v73 >= 0x80u || (*((_BYTE *)&qword_1800A0990 + v73) & 1) == 0 )
                        goto LABEL_22;
                    }
                  }
                }
              }
            }
            v6 = 45;
            do
            {
LABEL_63:
              v35 = *v34;
              a2 = (unsigned __int64)v34++;
              *(_QWORD *)(a1 + 40) = v34;
            }
            while ( v35 && v35 != 10 && v35 != 13 );
            v36 = (*(_BYTE *)(a1 + 96) & 0x10) == 0;
            *(_QWORD *)(a1 + 40) = a2;
            if ( !v36 )
            {
              result = 125;
              **(_DWORD **)(a1 + 8) = 125;
              return result;
            }
            continue;
          }
          if ( (unsigned __int16)v72 >= 0x80u )
            goto LABEL_3;
          v36 = (*((_BYTE *)&qword_1800A0990 + v72) & 2) == 0;
          v6 = 45;
          if ( !v36 )
            goto LABEL_13;
          continue;
        case 0x16u:
          **(_DWORD **)(a1 + 8) = 99;
          v75 = *(_WORD **)(a1 + 40);
          if ( *v75 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v75 + 1;
            **(_DWORD **)(a1 + 8) = 89;
          }
          return **(unsigned int **)(a1 + 8);
        case 0x17u:
          result = 81;
          **(_DWORD **)(a1 + 8) = 81;
          return result;
        case 0x18u:
          v25 = *(__int16 **)(a1 + 40);
          *(_DWORD *)(a1 + 96) &= ~4u;
          v26 = (const unsigned __int16 *)(v25 - 1);
          v27 = *(_DWORD *)(a1 + 96);
          *(_QWORD *)(a1 + 40) = v25 - 1;
          v95 = 0;
          if ( *(v25 - 1) != 48 )
            goto LABEL_107;
          v28 = *v25;
          switch ( v28 )
          {
            case 'X':
              goto LABEL_81;
            case 'E':
            case '.':
            case 'e':
              goto LABEL_107;
            case 'x':
LABEL_81:
              *(_DWORD *)(a1 + 96) = v27 | 4;
              *(double *)v2.m128i_i64 = DblFromHex(v26 + 2, (const unsigned __int16 **)&v95);
              v41 = *(_QWORD *)(a1 + 40);
              v32 = v2;
              v42 = v95;
              if ( v95 == (unsigned __int16 *)(v41 + 4) )
              {
                v32 = 0;
                v93 = 0;
                *(_QWORD *)(a1 + 40) = v41 + 2;
                goto LABEL_56;
              }
              v93 = v2.m128i_i64[0];
LABEL_122:
              *(_QWORD *)(a1 + 40) = v42;
LABEL_56:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = (int)*(double *)v32.m128i_i64;
              if ( COERCE__INT64((double)(int)*(double *)v32.m128i_i64) == __PAIR64__(
                                                                             HIDWORD(v93),
                                                                             _mm_cvtsi128_si32(v32)) )
              {
                **(_DWORD **)(a1 + 8) = 128;
              }
              else
              {
                **(_DWORD **)(a1 + 8) = 129;
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = v32.m128i_i64[0];
              }
              if ( **(_DWORD **)(a1 + 8) )
                return **(unsigned int **)(a1 + 8);
LABEL_59:
              **(_DWORD **)(a1 + 8) = 123;
              return **(unsigned int **)(a1 + 8);
          }
          v29 = (unsigned __int16 *)v26;
          do
          {
            v30 = v29[1];
            ++v29;
          }
          while ( v30 == 48 );
          v2 = 0;
          v31 = v30 - 48;
          v94 = 0;
          if ( (unsigned int)(v30 - 48) > 7 )
          {
            v95 = v29;
            v32 = 0;
LABEL_51:
            v93 = v32.m128i_i64[0];
            if ( *(double *)v32.m128i_i64 != 0.0 || v29 > v26 + 1 )
              *(_DWORD *)(a1 + 96) = v27 | 4;
            if ( *v29 != 56 && *v29 != 57 )
            {
              *(_QWORD *)(a1 + 40) = v29;
              goto LABEL_56;
            }
            *(_DWORD *)(a1 + 96) |= 4u;
LABEL_107:
            *(double *)v2.m128i_i64 = StrToDbl(v26, (const unsigned __int16 **)&v95);
            v49 = *(unsigned __int16 **)(a1 + 40);
            v32 = v2;
            v42 = v95;
            v93 = v2.m128i_i64[0];
            if ( v95 == v49 )
            {
              *(_QWORD *)(a1 + 40) = v49 + 1;
              goto LABEL_59;
            }
            goto LABEL_122;
          }
          ++v29;
          if ( (v31 & 4) != 0 )
          {
            v4 = 3;
            v83 = (v31 & 3) << 18;
          }
          else if ( (v31 & 2) != 0 )
          {
            v4 = 2;
            v83 = (v31 & 1) << 19;
          }
          else
          {
            v83 = HIDWORD(v94);
          }
          v84 = 0;
          v85 = v94;
          v86 = *v29 - 48;
          if ( v86 > 7 )
          {
LABEL_275:
            v95 = v29;
            if ( v4 + 1022 <= 2046 )
            {
              v88 = ((v4 + 1022) << 20) | v83;
              HIDWORD(v94) = v88;
              if ( v84 < 0 && ((v84 & 0x7F) != 0 || (v85 & 1) != 0) )
              {
                LODWORD(v94) = v85 + 1;
                if ( v85 == -1 )
                  HIDWORD(v94) = v88 + 1;
              }
            }
            else
            {
              v94 = 0x7FF0000000000000LL;
            }
            v32 = (__m128i)(unsigned __int64)v94;
            goto LABEL_51;
          }
          break;
        case 0x19u:
          **(_DWORD **)(a1 + 8) = 105;
          v34 = *(__int16 **)(a1 + 40);
          v50 = *v34;
          if ( *v34 == 60 )
          {
            *(_QWORD *)(a1 + 40) = v34 + 1;
            **(_DWORD **)(a1 + 8) = 109;
            v57 = *(_WORD **)(a1 + 40);
            if ( *v57 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v57 + 1;
              **(_DWORD **)(a1 + 8) = 91;
            }
            return **(unsigned int **)(a1 + 8);
          }
          if ( v50 != 33 )
          {
            if ( v50 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v34 + 1;
              **(_DWORD **)(a1 + 8) = 106;
            }
            return **(unsigned int **)(a1 + 8);
          }
          if ( (*(_BYTE *)(a1 + 64) & 1) == 0 || v34[1] != 45 || v34[2] != 45 )
            return **(unsigned int **)(a1 + 8);
          goto LABEL_63;
        case 0x1Au:
          **(_DWORD **)(a1 + 8) = 82;
          v37 = *(_WORD **)(a1 + 40);
          if ( *v37 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v37 + 1;
            **(_DWORD **)(a1 + 8) = 101;
            v47 = *(_WORD **)(a1 + 40);
            if ( *v47 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v47 + 1;
              **(_DWORD **)(a1 + 8) = 103;
            }
          }
          return **(unsigned int **)(a1 + 8);
        case 0x1Bu:
          **(_DWORD **)(a1 + 8) = 107;
          v60 = *(_WORD **)(a1 + 40);
          if ( *v60 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v60 + 1;
            **(_DWORD **)(a1 + 8) = 108;
          }
          else if ( *v60 == 62 )
          {
            *(_QWORD *)(a1 + 40) = v60 + 1;
            **(_DWORD **)(a1 + 8) = 110;
            v67 = *(_WORD **)(a1 + 40);
            if ( *v67 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v67 + 1;
              **(_DWORD **)(a1 + 8) = 92;
              return **(unsigned int **)(a1 + 8);
            }
            if ( *v67 == 62 )
            {
              *(_QWORD *)(a1 + 40) = v67 + 1;
              **(_DWORD **)(a1 + 8) = 111;
              v68 = *(_WORD **)(a1 + 40);
              if ( *v68 == 61 )
              {
                *(_QWORD *)(a1 + 40) = v68 + 1;
                **(_DWORD **)(a1 + 8) = 93;
                return **(unsigned int **)(a1 + 8);
              }
            }
          }
          return **(unsigned int **)(a1 + 8);
        case 0x1Cu:
          result = 94;
          **(_DWORD **)(a1 + 8) = 94;
          return result;
        case 0x1Du:
          result = 122;
          **(_DWORD **)(a1 + 8) = 122;
          return result;
        case 0x1Eu:
          result = 78;
          **(_DWORD **)(a1 + 8) = 78;
          return result;
        case 0x20u:
          result = 79;
          **(_DWORD **)(a1 + 8) = 79;
          return result;
        case 0x21u:
          result = 80;
          **(_DWORD **)(a1 + 8) = 80;
          return result;
        case 0x22u:
          **(_DWORD **)(a1 + 8) = 98;
          v58 = *(_WORD **)(a1 + 40);
          if ( *v58 == 61 )
          {
            *(_QWORD *)(a1 + 40) = v58 + 1;
            **(_DWORD **)(a1 + 8) = 90;
          }
          else if ( *v58 == 124 )
          {
            *(_QWORD *)(a1 + 40) = v58 + 1;
            **(_DWORD **)(a1 + 8) = 96;
          }
          return **(unsigned int **)(a1 + 8);
        case 0x23u:
          result = 117;
          **(_DWORD **)(a1 + 8) = 117;
          return result;
        case 0x24u:
          **(_DWORD **)(a1 + 8) = 95;
          v48 = *(_WORD **)(a1 + 40);
          if ( *v48 == 58 )
          {
            *(_QWORD *)(a1 + 40) = v48 + 1;
            **(_DWORD **)(a1 + 8) = 124;
          }
          return **(unsigned int **)(a1 + 8);
        case 0x25u:
          result = 76;
          **(_DWORD **)(a1 + 8) = 76;
          return result;
        default:
          if ( (*(_BYTE *)(a1 + 96) & 0x10) == 0 )
          {
            *(_QWORD *)(a1 + 40) -= 2LL;
            Scanner::Error((Scanner *)a1, 1014);
          }
          **(_DWORD **)(a1 + 8) = 126;
          return 126;
      }
      while ( 2 )
      {
        if ( v4 <= 18 )
        {
          v83 |= v86 << (18 - v4);
          goto LABEL_274;
        }
        if ( v4 < 21 )
        {
          v83 |= v86 >> (v4 - 18);
          goto LABEL_268;
        }
        if ( v4 <= 50 )
        {
LABEL_268:
          v85 |= v86 << (50 - v4);
          LODWORD(v94) = v85;
        }
        else if ( v4 > 53 )
        {
          if ( v86 )
            v84 |= 1u;
        }
        else
        {
          v85 |= v86 >> (v4 - 50);
          LODWORD(v94) = v85;
          v84 = (_BYTE)v86 << (58 - v4);
        }
LABEL_274:
        v87 = v29[1];
        ++v29;
        v86 = v87 - 48;
        v4 += 3;
        if ( v86 > 7 )
          goto LABEL_275;
        continue;
      }
    }
    if ( (*(_BYTE *)(a1 + 96) & 0x10) != 0 )
      break;
LABEL_13:
    v11 = *(unsigned __int16 **)(a1 + 40);
    v12 = *v11;
    if ( (unsigned __int16)v12 >= 0x80u )
    {
      BigCharFlags = GetBigCharFlags(v12);
      v6 = 45;
      v5 = 62;
    }
    else
    {
      BigCharFlags = *((_BYTE *)&qword_1800A0990 + v12);
    }
    if ( (BigCharFlags & 2) != 0 )
    {
      v14 = v11 + 1;
      if ( (GetCharFlags(v11[1]) & 1) != 0 )
      {
        do
        {
          v76 = v14[1];
          ++v14;
        }
        while ( (GetCharFlags(v76) & 1) != 0 );
      }
      v6 = 45;
      v5 = 62;
    }
    else
    {
      v14 = v11;
    }
    *(_QWORD *)(a1 + 40) = v14;
    v15 = v14 - v11;
    if ( v15 == 5 )
    {
      v16 = 0x6F005F00630063LL - *(_QWORD *)v11;
      if ( *(_QWORD *)v11 == 0x6F005F00630063LL )
        v16 = 110LL - v11[4];
      if ( v16 )
        goto LABEL_87;
      v17 = *(_QWORD **)(a1 + 88);
      if ( !v17 || !*v17 )
LABEL_22:
        Scanner::InitCc((Scanner *)a1);
      goto LABEL_2;
    }
    if ( v15 )
    {
      if ( v15 == 2 )
      {
        if ( *(_DWORD *)v11 == 6684777 )
        {
          if ( !(unsigned int)Scanner::FCcOn((Scanner *)a1) )
            Scanner::InitCc(v81);
          ++*(_DWORD *)(a1 + 80);
          if ( !(unsigned int)Scanner::FScanCond((Scanner *)a1) )
            Scanner::ScanForEnd((Scanner *)a1, 1);
          goto LABEL_2;
        }
LABEL_87:
        if ( !(unsigned int)Scanner::FCcOn((Scanner *)a1) )
          Scanner::Error(v43, 1030);
        v92 = 0;
        v93 = 0;
        v91 = 0;
        if ( (int)v15 > 0 )
        {
          *(_DWORD *)(a1 + 116) = 0;
          while ( (int)v15 >= *(_DWORD *)(a1 + 112) )
            Scanner::GrowBuf((Scanner *)a1);
          memcpy_0(*(void **)(a1 + 120), v11, 2LL * (int)v15);
          *(_WORD *)(2LL * (int)v15 + *(_QWORD *)(a1 + 120)) = 0;
          v11 = *(unsigned __int16 **)(a1 + 120);
        }
        SYM::InitFromPsz((SYM *)&v91, v11);
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int128 *, __int64 *, _QWORD))(***(_QWORD ***)(a1 + 88) + 8LL))(
               **(_QWORD **)(a1 + 88),
               &v91,
               &v93,
               0) )
        {
          v44 = *(double *)(v93 + 8);
          if ( *(_WORD *)v93 != 5 )
          {
            if ( *(_WORD *)v93 != 139 )
LABEL_292:
              Scanner::Error((Scanner *)a1, 1002);
            v45 = BoolFromDbl();
            v46 = 63;
            if ( !v45 )
              v46 = 24;
            **(_DWORD **)(a1 + 8) = v46;
            return **(unsigned int **)(a1 + 8);
          }
        }
        else
        {
          v44 = cdblNan;
        }
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = (int)v44;
        if ( COERCE__INT64((double)(int)v44) == *(_QWORD *)&v44 )
        {
          **(_DWORD **)(a1 + 8) = 128;
          return **(unsigned int **)(a1 + 8);
        }
        *(double *)(*(_QWORD *)(a1 + 8) + 8LL) = v44;
        **(_DWORD **)(a1 + 8) = 129;
        return **(unsigned int **)(a1 + 8);
      }
      if ( v15 != 3 )
      {
        if ( v15 != 4 )
          goto LABEL_87;
        if ( *(_QWORD *)v11 == 0x660069006C0065LL )
        {
          if ( *(int *)(a1 + 80) <= 0 )
            goto LABEL_292;
        }
        else
        {
          if ( *(_QWORD *)v11 != 0x650073006C0065LL )
            goto LABEL_87;
          if ( *(int *)(a1 + 80) <= 0 )
            goto LABEL_292;
        }
        Scanner::ScanForEnd((Scanner *)a1, 0);
        goto LABEL_2;
      }
      v77 = 6619251 - *(_DWORD *)v11;
      if ( *(_DWORD *)v11 == 6619251 )
        v77 = 116 - v11[2];
      if ( !v77 )
      {
        if ( !(unsigned int)Scanner::FCcOn((Scanner *)a1) )
          Scanner::InitCc(v78);
        Scanner::ScanSet((Scanner *)a1);
        goto LABEL_2;
      }
      v79 = 7209061 - *(_DWORD *)v11;
      if ( *(_DWORD *)v11 == 7209061 )
        v79 = 100 - v11[2];
      if ( v79 )
        goto LABEL_87;
      v80 = *(_DWORD *)(a1 + 80);
      if ( v80 <= 0 )
        goto LABEL_292;
      *(_DWORD *)(a1 + 80) = v80 - 1;
    }
    else
    {
      if ( !(unsigned int)Scanner::FCcOn((Scanner *)a1) || *v14 != 42 || v14[1] != 47 )
      {
        *(_QWORD *)(a1 + 40) = v14 - 1;
        Scanner::Error(v82, 1014);
      }
      *(_QWORD *)(a1 + 40) = v14 + 2;
    }
  }
  v18 = *(unsigned __int16 **)(a1 + 40);
  v19 = *v18;
  if ( (unsigned __int16)v19 >= 0x80u )
    v20 = GetBigCharFlags(v19);
  else
    v20 = *((_BYTE *)&qword_1800A0990 + v19);
  if ( (v20 & 2) != 0 )
  {
    v89 = v18[1];
    ++v18;
    if ( (GetCharFlags(v89) & 1) != 0 )
    {
      do
      {
        v90 = v18[1];
        ++v18;
      }
      while ( (GetCharFlags(v90) & 1) != 0 );
    }
  }
  v21 = *(_DWORD **)(a1 + 8);
  result = 75;
  *(_QWORD *)(a1 + 40) = v18;
  *v21 = 75;
  return result;
}

```

## disassembly

```asm
0x18001f400  mov     [rsp+arg_18], rbx
0x18001f405  push    rbp
0x18001f406  push    rsi
0x18001f407  push    rdi
0x18001f408  push    r12
0x18001f40a  push    r13
0x18001f40c  push    r14
0x18001f40e  push    r15
0x18001f410  sub     rsp, 50h
0x18001f414  and     dword ptr [rcx+60h], 0FFFFFFF7h
0x18001f418  lea     r12, __ImageBase
0x18001f41f  mov     rdi, rcx
0x18001f422  mov     r13d, 80h
0x18001f428  mov     r15d, 1
0x18001f42e  mov     r14d, 7Dh ; '}'
0x18001f434  mov     r10d, 3Eh ; '>'
0x18001f43a  mov     r8d, 2Dh ; '-'
0x18001f440  test    byte ptr [rdi+60h], 20h
0x18001f444  jnz     loc_18001FB88
0x18001f44a  mov     rax, [rdi+28h]
0x18001f44e  mov     [rdi+20h], rax
0x18001f452  movzx   esi, word ptr [rax]
0x18001f455  add     rax, 2
0x18001f459  mov     [rdi+28h], rax
0x18001f45d  cmp     si, r13w
0x18001f461  jnb     loc_18001FBB4
0x18001f467  movzx   eax, byte ptr [rsi+r12+0A0550h]
0x18001f470  cmp     al, 4
0x18001f472  jz      short loc_18001F434
0x18001f474  cmp     al, 9
0x18001f476  jz      short loc_18001F4B3
0x18001f478  cmp     al, 6
0x18001f47a  jz      loc_18001F53A; jumptable 000000018001F49D cases 2,31
0x18001f480  movzx   eax, al
0x18001f483  dec     eax; switch 37 cases
0x18001f485  cmp     eax, 24h
0x18001f488  ja      def_18001F49D; jumptable 000000018001F49D default case, cases 4,6,8-10
0x18001f48e  cdqe
0x18001f490  mov     edx, esi
0x18001f492  mov     ecx, ds:(jpt_18001F49D - 180000000h)[r12+rax*4]
0x18001f49a  add     rcx, r12
0x18001f49d  jmp     rcx; switch jump
0x18001f49f  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 23
0x18001f4a3  mov     eax, 51h ; 'Q'
0x18001f4a8  mov     dword ptr [rcx], 51h ; 'Q'
0x18001f4ae  jmp     loc_18001F547
0x18001f4b3  test    byte ptr [rdi+60h], 10h
0x18001f4b7  jnz     loc_18001F55F
0x18001f4bd  mov     rsi, [rdi+28h]
0x18001f4c1  movzx   eax, word ptr [rsi]
0x18001f4c4  cmp     ax, r13w
0x18001f4c8  jnb     loc_18002031F
0x18001f4ce  movzx   eax, byte ptr [rax+r12+0A0990h]
0x18001f4d7  test    al, 2
0x18001f4d9  jnz     loc_180020338
0x18001f4df  mov     r14, rsi
0x18001f4e2  mov     rbp, r14
0x18001f4e5  mov     [rdi+28h], r14
0x18001f4e9  sub     rbp, rsi
0x18001f4ec  sar     rbp, 1
0x18001f4ef  cmp     rbp, 5
0x18001f4f3  jnz     loc_18001F911
0x18001f4f9  mov     rcx, 6F005F00630063h
0x18001f503  sub     rcx, [rsi]
0x18001f506  jnz     short loc_18001F517
0x18001f508  mov     eax, 6Eh ; 'n'
0x18001f50d  movzx   ecx, ax
0x18001f510  movzx   eax, word ptr [rsi+8]
0x18001f514  sub     rcx, rax
0x18001f517  test    rcx, rcx
0x18001f51a  jnz     loc_18001F939
0x18001f520  mov     rax, [rdi+58h]
0x18001f524  test    rax, rax
0x18001f527  jnz     loc_1800204B2
0x18001f52d  mov     rcx, rdi; this
0x18001f530  call    ?InitCc@Scanner@@AEAAXXZ; Scanner::InitCc(void)
0x18001f535  jmp     loc_18001F42E
0x18001f53a  add     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFEh; jumptable 000000018001F49D cases 2,31
0x18001f53f  mov     rcx, rdi
0x18001f542  call    ?ScanIdentifier@Scanner@@AEAA?AW4tokens@@XZ; Scanner::ScanIdentifier(void)
0x18001f547  mov     rbx, [rsp+88h+arg_18]
0x18001f54f  add     rsp, 50h
0x18001f553  pop     r15
0x18001f555  pop     r14
0x18001f557  pop     r13
0x18001f559  pop     r12
0x18001f55b  pop     rdi
0x18001f55c  pop     rsi
0x18001f55d  pop     rbp
0x18001f55e  retn
0x18001f55f  mov     rsi, [rdi+28h]
0x18001f563  movzx   eax, word ptr [rsi]
0x18001f566  cmp     ax, r13w
0x18001f56a  jnb     loc_1800206EB
0x18001f570  movzx   eax, byte ptr [rax+r12+0A0990h]
0x18001f579  test    al, 2
0x18001f57b  jnz     loc_1800206F8
0x18001f581  mov     rcx, [rdi+8]
0x18001f585  mov     eax, 4Bh ; 'K'
0x18001f58a  mov     [rdi+28h], rsi
0x18001f58e  mov     dword ptr [rcx], 4Bh ; 'K'
0x18001f594  jmp     short loc_18001F547
0x18001f596  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 16
0x18001f59a  mov     eax, 79h ; 'y'
0x18001f59f  mov     dword ptr [rcx], 79h ; 'y'
0x18001f5a5  jmp     short loc_18001F547
0x18001f5a7  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 17
0x18001f5ab  mov     eax, 4Dh ; 'M'
0x18001f5b0  mov     dword ptr [rcx], 4Dh ; 'M'
0x18001f5b6  jmp     short loc_18001F547
0x18001f5b8  cmp     edx, 0Dh; jumptable 000000018001F49D case 5
0x18001f5bb  jnz     short loc_18001F5CF
0x18001f5bd  mov     rax, [rdi+28h]
0x18001f5c1  cmp     word ptr [rax], 0Ah
0x18001f5c5  jnz     short loc_18001F5CF
0x18001f5c7  add     rax, 2
0x18001f5cb  mov     [rdi+28h], rax
0x18001f5cf  test    byte ptr [rdi+60h], 10h
0x18001f5d3  jnz     short loc_18001F623
0x18001f5d5  cmp     qword ptr [rdi+180h], 0
0x18001f5dd  jz      loc_18001FF4C
0x18001f5e3  mov     rdx, [rdi+188h]
0x18001f5ea  mov     rcx, [rdi+28h]
0x18001f5ee  sub     rcx, [rdi+18h]
0x18001f5f2  sar     rcx, 1
0x18001f5f5  test    ecx, 0FFFFFF80h
0x18001f5fb  jnz     loc_18001FDF2
0x18001f601  or      cl, r13b
0x18001f604  mov     [rdx], cl
0x18001f606  mov     rax, [rdi+18h]
0x18001f60a  inc     qword ptr [rdi+188h]
0x18001f611  inc     dword ptr [rdi+198h]
0x18001f617  mov     [rdi+30h], rax
0x18001f61b  mov     rax, [rdi+28h]
0x18001f61f  mov     [rdi+18h], rax
0x18001f623  or      dword ptr [rdi+60h], 8
0x18001f627  jmp     loc_18001F434
0x18001f62c  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 37
0x18001f630  mov     eax, 4Ch ; 'L'
0x18001f635  mov     dword ptr [rcx], 4Ch ; 'L'
0x18001f63b  jmp     loc_18001F547
0x18001f640  mov     rax, [rdi+28h]; jumptable 000000018001F49D case 24
0x18001f644  mov     ecx, 30h ; '0'
0x18001f649  and     dword ptr [rdi+60h], 0FFFFFFFBh
0x18001f64d  lea     r8, [rax-2]
0x18001f651  mov     r10d, [rdi+60h]
0x18001f655  mov     [rdi+28h], r8
0x18001f659  mov     [rsp+88h+arg_10], 0
0x18001f665  cmp     cx, [r8]
0x18001f669  jnz     loc_18001FAC4
0x18001f66f  movzx   eax, word ptr [rax]
0x18001f672  cmp     ax, 58h ; 'X'
0x18001f676  jz      loc_18001F8C3
0x18001f67c  cmp     ax, 45h ; 'E'
0x18001f680  jz      loc_18001FAC4
0x18001f686  cmp     ax, 2Eh ; '.'
0x18001f68a  jz      loc_18001FAC4
0x18001f690  cmp     ax, 65h ; 'e'
0x18001f694  jz      loc_18001FAC4
0x18001f69a  cmp     ax, 78h ; 'x'
0x18001f69e  jz      loc_18001F8C3
0x18001f6a4  mov     rdx, r8
0x18001f6a7  movzx   eax, word ptr [rdx+2]
0x18001f6ab  add     rdx, 2
0x18001f6af  cmp     eax, ecx
0x18001f6b1  jz      short loc_18001F6A7
0x18001f6b3  mov     r9d, eax
0x18001f6b6  xorps   xmm0, xmm0
0x18001f6b9  add     r9d, 0FFFFFFD0h
0x18001f6bd  movsd   [rsp+88h+arg_8], xmm0
0x18001f6c6  cmp     r9d, 7
0x18001f6ca  jbe     loc_1800204DD
0x18001f6d0  mov     [rsp+88h+arg_10], rdx
0x18001f6d8  xorps   xmm2, xmm2
0x18001f6db  ucomisd xmm2, xmm0
0x18001f6df  movsd   [rsp+88h+arg_0], xmm2
0x18001f6e8  jp      loc_180020639
0x18001f6ee  jnz     loc_180020639
0x18001f6f4  lea     rax, [r8+2]
0x18001f6f8  cmp     rdx, rax
0x18001f6fb  ja      loc_180020639
0x18001f701  movzx   ecx, word ptr [rdx]
0x18001f704  sub     ecx, 38h ; '8'
0x18001f707  jz      loc_18001FAC0
0x18001f70d  cmp     ecx, 1
0x18001f710  jz      loc_18001FAC0
0x18001f716  mov     [rdi+28h], rdx
0x18001f71a  mov     rax, [rdi+8]
0x18001f71e  cvttsd2si ecx, xmm2
0x18001f722  mov     [rax+8], ecx
0x18001f725  movd    xmm1, ecx
0x18001f729  cvtdq2pd xmm1, xmm1
0x18001f72d  movq    rcx, xmm1
0x18001f732  mov     rax, rcx
0x18001f735  shr     rax, 20h
0x18001f739  cmp     eax, dword ptr [rsp+88h+arg_0+4]
0x18001f740  jnz     loc_18001FD0C
0x18001f746  movd    eax, xmm2
0x18001f74a  cmp     ecx, eax
0x18001f74c  jnz     loc_18001FD0C
0x18001f752  mov     rax, [rdi+8]
0x18001f756  mov     [rax], r13d
0x18001f759  mov     rax, [rdi+8]
0x18001f75d  cmp     dword ptr [rax], 0
0x18001f760  jnz     short loc_18001F76C
0x18001f762  mov     rax, [rdi+8]
0x18001f766  mov     dword ptr [rax], 7Bh ; '{'
0x18001f76c  mov     rax, [rdi+8]
0x18001f770  mov     eax, [rax]
0x18001f772  jmp     loc_18001F547
0x18001f777  mov     rax, [rdi+8]; jumptable 000000018001F49D case 21
0x18001f77b  mov     dword ptr [rax], 73h ; 's'
0x18001f781  mov     rdx, [rdi+28h]
0x18001f785  movzx   eax, word ptr [rdx]
0x18001f788  cmp     ax, 2Fh ; '/'
0x18001f78c  jnz     loc_18001FBDF
0x18001f792  lea     rcx, [rdx+2]
0x18001f796  mov     eax, 40h ; '@'
0x18001f79b  mov     [rdi+28h], rcx
0x18001f79f  cmp     ax, [rcx]
0x18001f7a2  jz      loc_1800200D9
0x18001f7a8  nop     dword ptr [rax+rax+00000000h]
0x18001f7b0  movzx   eax, word ptr [rcx]
0x18001f7b3  mov     rdx, rcx
0x18001f7b6  add     rcx, 2
0x18001f7ba  mov     [rdi+28h], rcx
0x18001f7be  test    ax, ax
0x18001f7c1  jz      short loc_18001F7CF
0x18001f7c3  cmp     ax, 0Ah
0x18001f7c7  jz      short loc_18001F7CF
0x18001f7c9  cmp     ax, 0Dh
0x18001f7cd  jnz     short loc_18001F7B0
0x18001f7cf  test    byte ptr [rdi+60h], 10h
0x18001f7d3  mov     [rdi+28h], rdx
0x18001f7d7  jz      loc_18001F440
0x18001f7dd  mov     rcx, [rdi+8]
0x18001f7e1  mov     eax, r14d
0x18001f7e4  mov     [rcx], r14d
0x18001f7e7  jmp     loc_18001F547
0x18001f7ec  mov     rax, [rdi+8]; jumptable 000000018001F49D case 26
0x18001f7f0  mov     dword ptr [rax], 52h ; 'R'
0x18001f7f6  mov     rax, [rdi+28h]
0x18001f7fa  cmp     word ptr [rax], 3Dh ; '='
0x18001f7fe  jz      loc_18001FA66
0x18001f804  mov     rax, [rdi+8]
0x18001f808  mov     eax, [rax]
0x18001f80a  jmp     loc_18001F547
0x18001f80f  mov     r8d, r15d; jumptable 000000018001F49D case 3
0x18001f812  mov     rcx, rdi
0x18001f815  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18001f81a  jmp     loc_18001F547
0x18001f81f  mov     rcx, rdi; jumptable 000000018001F49D cases 12,13
0x18001f822  call    ?ScanStringConstant@Scanner@@AEAA?AW4tokens@@I@Z; Scanner::ScanStringConstant(uint)
0x18001f827  jmp     loc_18001F547
0x18001f82c  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 33
0x18001f830  mov     eax, 50h ; 'P'
0x18001f835  mov     dword ptr [rcx], 50h ; 'P'
0x18001f83b  jmp     loc_18001F547
0x18001f840  mov     rcx, [rdi+8]; jumptable 000000018001F49D case 32
0x18001f844  mov     eax, 4Fh ; 'O'
0x18001f849  mov     dword ptr [rcx], 4Fh ; 'O'
0x18001f84f  jmp     loc_18001F547
0x18001f854  mov     rax, [rdi+8]; jumptable 000000018001F49D case 18
0x18001f858  mov     dword ptr [rax], 70h ; 'p'
0x18001f85e  mov     rcx, [rdi+28h]
0x18001f862  movzx   eax, word ptr [rcx]
0x18001f865  cmp     ax, 2Bh ; '+'
0x18001f869  jz      loc_18001FD99
0x18001f86f  cmp     ax, 3Dh ; '='
0x18001f873  jz      loc_18001FE76
0x18001f879  mov     rax, [rdi+8]
0x18001f87d  mov     eax, [rax]
0x18001f87f  jmp     loc_18001F547
0x18001f884  mov     rax, [rdi+8]; jumptable 000000018001F49D case 11
0x18001f888  mov     dword ptr [rax], 76h ; 'v'
0x18001f88e  mov     rax, [rdi+28h]
0x18001f892  cmp     word ptr [rax], 3Dh ; '='
0x18001f896  jnz     short loc_18001F8B8
0x18001f898  add     rax, 2
0x18001f89c  mov     [rdi+28h], rax
0x18001f8a0  mov     rax, [rdi+8]
0x18001f8a4  mov     dword ptr [rax], 66h ; 'f'
0x18001f8aa  mov     rax, [rdi+28h]
0x18001f8ae  cmp     word ptr [rax], 3Dh ; '='
0x18001f8b2  jz      loc_18001FE93
0x18001f8b8  mov     rax, [rdi+8]
0x18001f8bc  mov     eax, [rax]
0x18001f8be  jmp     loc_18001F547
0x18001f8c3  or      r10d, 4
0x18001f8c7  lea     rcx, [r8+4]; unsigned __int16 *
0x18001f8cb  lea     rdx, [rsp+88h+arg_10]; unsigned __int16 **
0x18001f8d3  mov     [rdi+60h], r10d
0x18001f8d7  call    ?DblFromHex@@YANPEBGPEAPEBG@Z; DblFromHex(ushort const *,ushort const * *)
0x18001f8dc  mov     rdx, [rdi+28h]
0x18001f8e0  movaps  xmm2, xmm0
0x18001f8e3  mov     rcx, [rsp+88h+arg_10]
0x18001f8eb  lea     rax, [rdx+4]
0x18001f8ef  cmp     rcx, rax
0x18001f8f2  jnz     loc_18001FBCD
0x18001f8f8  xorps   xmm2, xmm2
  ... truncated ...
```
