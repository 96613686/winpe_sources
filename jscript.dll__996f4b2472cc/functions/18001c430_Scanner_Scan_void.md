# Scanner::Scan(void)

- ea: `0x18001c430`
- end: `0x18001d7f0`
- name: `?Scan@Scanner@@QEAA?AW4tokens@@XZ`
- size: `5056`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18001a510`
- `0x18001b870`
- `0x18001d7f8`
- `0x18001da00`
- `0x180020170`
- `0x180022170`
- `0x1800227c8`
- `0x180029160`
- `0x180029228`
- `0x1800293d8`
- `0x180029550`
- `0x180029648`
- `0x18002a0dc`
- `0x18003f238`
- `0x18006a26c`
- `0x18006eee0`
- `0x18006f530`
- `0x180075a20`
- `0x180089e40`
- `0x180089f1c`
- `0x1800932d8`

## callees

- `0x1800132f8`
- `0x18001c430`
- `0x18001e114`
- `0x18002a5d0`
- `0x18002a9c0`
- `0x18002c310`
- `0x18002c3c0`
- `0x18002c3e8`
- `0x180037bb0`
- `0x180037fa0`
- `0x180038d24`
- `0x180039324`
- `0x1800394f0`
- `0x18003b368`
- `0x1800535e8`
- `0x180053938`
- `0x180053958`
- `0x180075b44`
- `0x180075bc0`
- `0x1800760f4`
- `0x180076218`
- `0x180096692`
- `0x180098010`

## import_xrefs

- `msvcrt!malloc` at `0x18001cf83`
- `msvcrt!malloc` at `0x18001cf83`

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
      BigCharType = *((_BYTE *)&qword_1800A2400 + v8);
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
              if ( (unsigned __int16)v6 >= 0x80u || (*((_BYTE *)&qword_1800A2780 + v6) & 2) == 0 )
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
                      if ( (unsigned __int16)v70 >= 0x80u || (*((_BYTE *)&qword_1800A2780 + v70) & 1) == 0 )
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
                      if ( (unsigned __int16)v73 >= 0x80u || (*((_BYTE *)&qword_1800A2780 + v73) & 1) == 0 )
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
          v36 = (*((_BYTE *)&qword_1800A2780 + v72) & 2) == 0;
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
      BigCharFlags = *((_BYTE *)&qword_1800A2780 + v12);
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
    v20 = *((_BYTE *)&qword_1800A2780 + v19);
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
0x18001c430  mov     [rsp+arg_18], rbx
0x18001c435  push    rbp
0x18001c436  push    rsi
0x18001c437  push    rdi
0x18001c438  push    r12
0x18001c43a  push    r13
0x18001c43c  push    r14
0x18001c43e  push    r15
0x18001c440  sub     rsp, 50h
0x18001c444  and     dword ptr [rcx+60h], 0FFFFFFF7h
0x18001c448  lea     r12, __ImageBase
0x18001c44f  mov     rdi, rcx
0x18001c452  mov     r13d, 80h
0x18001c458  mov     r15d, 1
0x18001c45e  mov     r14d, 7Dh ; '}'
0x18001c464  mov     r10d, 3Eh ; '>'
0x18001c46a  mov     r8d, 2Dh ; '-'
0x18001c470  test    byte ptr [rdi+60h], 20h
0x18001c474  jnz     loc_18001CBB8
0x18001c47a  mov     rax, [rdi+28h]
0x18001c47e  mov     [rdi+20h], rax
0x18001c482  movzx   esi, word ptr [rax]
0x18001c485  add     rax, 2
0x18001c489  mov     [rdi+28h], rax
0x18001c48d  cmp     si, r13w
0x18001c491  jnb     loc_18001CBE4
0x18001c497  movzx   eax, byte ptr [rsi+r12+0A2400h]
0x18001c4a0  cmp     al, 4
0x18001c4a2  jz      short loc_18001C464
0x18001c4a4  cmp     al, 9
0x18001c4a6  jz      short loc_18001C4E7
0x18001c4a8  cmp     al, 6
0x18001c4aa  jz      loc_18001C56E; jumptable 000000018001C4CD cases 2,31
0x18001c4b0  movzx   eax, al
0x18001c4b3  dec     eax; switch 37 cases
0x18001c4b5  cmp     eax, 24h
0x18001c4b8  ja      def_18001C4CD; jumptable 000000018001C4CD default case, cases 4,6,8-10
0x18001c4be  cdqe
0x18001c4c0  mov     edx, esi
0x18001c4c2  mov     ecx, ds:(jpt_18001C4CD - 180000000h)[r12+rax*4]
0x18001c4ca  add     rcx, r12
0x18001c4cd  jmp     rcx; switch jump
0x18001c4d3  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 23
0x18001c4d7  mov     eax, 51h ; 'Q'
0x18001c4dc  mov     dword ptr [rcx], 51h ; 'Q'
0x18001c4e2  jmp     loc_18001C57B
0x18001c4e7  test    byte ptr [rdi+60h], 10h
0x18001c4eb  jnz     loc_18001C594
0x18001c4f1  mov     rsi, [rdi+28h]
0x18001c4f5  movzx   eax, word ptr [rsi]
0x18001c4f8  cmp     ax, r13w
0x18001c4fc  jnb     loc_18001D355
0x18001c502  movzx   eax, byte ptr [rax+r12+0A2780h]
0x18001c50b  test    al, 2
0x18001c50d  jnz     loc_18001D36E
0x18001c513  mov     r14, rsi
0x18001c516  mov     rbp, r14
0x18001c519  mov     [rdi+28h], r14
0x18001c51d  sub     rbp, rsi
0x18001c520  sar     rbp, 1
0x18001c523  cmp     rbp, 5
0x18001c527  jnz     loc_18001C941
0x18001c52d  mov     rcx, 6F005F00630063h
0x18001c537  sub     rcx, [rsi]
0x18001c53a  jnz     short loc_18001C54B
0x18001c53c  mov     eax, 6Eh ; 'n'
0x18001c541  movzx   ecx, ax
0x18001c544  movzx   eax, word ptr [rsi+8]
0x18001c548  sub     rcx, rax
0x18001c54b  test    rcx, rcx
0x18001c54e  jnz     loc_18001C969
0x18001c554  mov     rax, [rdi+58h]
0x18001c558  test    rax, rax
0x18001c55b  jnz     loc_18001D4E8
0x18001c561  mov     rcx, rdi; this
0x18001c564  call    ?InitCc@Scanner@@AEAAXXZ; Scanner::InitCc(void)
0x18001c569  jmp     loc_18001C45E
0x18001c56e  add     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFEh; jumptable 000000018001C4CD cases 2,31
0x18001c573  mov     rcx, rdi
0x18001c576  call    ?ScanIdentifier@Scanner@@AEAA?AW4tokens@@XZ; Scanner::ScanIdentifier(void)
0x18001c57b  mov     rbx, [rsp+88h+arg_18]
0x18001c583  add     rsp, 50h
0x18001c587  pop     r15
0x18001c589  pop     r14
0x18001c58b  pop     r13
0x18001c58d  pop     r12
0x18001c58f  pop     rdi
0x18001c590  pop     rsi
0x18001c591  pop     rbp
0x18001c592  retn
0x18001c594  mov     rsi, [rdi+28h]
0x18001c598  movzx   eax, word ptr [rsi]
0x18001c59b  cmp     ax, r13w
0x18001c59f  jnb     loc_18001D721
0x18001c5a5  movzx   eax, byte ptr [rax+r12+0A2780h]
0x18001c5ae  test    al, 2
0x18001c5b0  jnz     loc_18001D72E
0x18001c5b6  mov     rcx, [rdi+8]
0x18001c5ba  mov     eax, 4Bh ; 'K'
0x18001c5bf  mov     [rdi+28h], rsi
0x18001c5c3  mov     dword ptr [rcx], 4Bh ; 'K'
0x18001c5c9  jmp     short loc_18001C57B
0x18001c5cb  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 16
0x18001c5cf  mov     eax, 79h ; 'y'
0x18001c5d4  mov     dword ptr [rcx], 79h ; 'y'
0x18001c5da  jmp     short loc_18001C57B
0x18001c5dc  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 17
0x18001c5e0  mov     eax, 4Dh ; 'M'
0x18001c5e5  mov     dword ptr [rcx], 4Dh ; 'M'
0x18001c5eb  jmp     short loc_18001C57B
0x18001c5ed  cmp     edx, 0Dh; jumptable 000000018001C4CD case 5
0x18001c5f0  jnz     short loc_18001C604
0x18001c5f2  mov     rax, [rdi+28h]
0x18001c5f6  cmp     word ptr [rax], 0Ah
0x18001c5fa  jnz     short loc_18001C604
0x18001c5fc  add     rax, 2
0x18001c600  mov     [rdi+28h], rax
0x18001c604  test    byte ptr [rdi+60h], 10h
0x18001c608  jnz     short loc_18001C658
0x18001c60a  cmp     qword ptr [rdi+180h], 0
0x18001c612  jz      loc_18001CF7C
0x18001c618  mov     rdx, [rdi+188h]
0x18001c61f  mov     rcx, [rdi+28h]
0x18001c623  sub     rcx, [rdi+18h]
0x18001c627  sar     rcx, 1
0x18001c62a  test    ecx, 0FFFFFF80h
0x18001c630  jnz     loc_18001CE22
0x18001c636  or      cl, r13b
0x18001c639  mov     [rdx], cl
0x18001c63b  mov     rax, [rdi+18h]
0x18001c63f  inc     qword ptr [rdi+188h]
0x18001c646  inc     dword ptr [rdi+198h]
0x18001c64c  mov     [rdi+30h], rax
0x18001c650  mov     rax, [rdi+28h]
0x18001c654  mov     [rdi+18h], rax
0x18001c658  or      dword ptr [rdi+60h], 8
0x18001c65c  jmp     loc_18001C464
0x18001c661  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 37
0x18001c665  mov     eax, 4Ch ; 'L'
0x18001c66a  mov     dword ptr [rcx], 4Ch ; 'L'
0x18001c670  jmp     loc_18001C57B
0x18001c675  mov     rax, [rdi+28h]; jumptable 000000018001C4CD case 24
0x18001c679  mov     ecx, 30h ; '0'
0x18001c67e  and     dword ptr [rdi+60h], 0FFFFFFFBh
0x18001c682  lea     r8, [rax-2]
0x18001c686  mov     r10d, [rdi+60h]
0x18001c68a  mov     [rdi+28h], r8
0x18001c68e  mov     [rsp+88h+arg_10], 0
0x18001c69a  cmp     cx, [r8]
0x18001c69e  jnz     loc_18001CAF4
0x18001c6a4  movzx   eax, word ptr [rax]
0x18001c6a7  cmp     ax, 58h ; 'X'
0x18001c6ab  jz      loc_18001C8F3
0x18001c6b1  cmp     ax, 45h ; 'E'
0x18001c6b5  jz      loc_18001CAF4
0x18001c6bb  cmp     ax, 2Eh ; '.'
0x18001c6bf  jz      loc_18001CAF4
0x18001c6c5  cmp     ax, 65h ; 'e'
0x18001c6c9  jz      loc_18001CAF4
0x18001c6cf  cmp     ax, 78h ; 'x'
0x18001c6d3  jz      loc_18001C8F3
0x18001c6d9  mov     rdx, r8
0x18001c6dc  movzx   eax, word ptr [rdx+2]
0x18001c6e0  add     rdx, 2
0x18001c6e4  cmp     eax, ecx
0x18001c6e6  jz      short loc_18001C6DC
0x18001c6e8  mov     r9d, eax
0x18001c6eb  xorps   xmm0, xmm0
0x18001c6ee  add     r9d, 0FFFFFFD0h
0x18001c6f2  movsd   [rsp+88h+arg_8], xmm0
0x18001c6fb  cmp     r9d, 7
0x18001c6ff  jbe     loc_18001D513
0x18001c705  mov     [rsp+88h+arg_10], rdx
0x18001c70d  xorps   xmm2, xmm2
0x18001c710  ucomisd xmm2, xmm0
0x18001c714  movsd   [rsp+88h+arg_0], xmm2
0x18001c71d  jp      loc_18001D66F
0x18001c723  jnz     loc_18001D66F
0x18001c729  lea     rax, [r8+2]
0x18001c72d  cmp     rdx, rax
0x18001c730  ja      loc_18001D66F
0x18001c736  movzx   ecx, word ptr [rdx]
0x18001c739  sub     ecx, 38h ; '8'
0x18001c73c  jz      loc_18001CAF0
0x18001c742  cmp     ecx, 1
0x18001c745  jz      loc_18001CAF0
0x18001c74b  mov     [rdi+28h], rdx
0x18001c74f  mov     rax, [rdi+8]
0x18001c753  cvttsd2si ecx, xmm2
0x18001c757  mov     [rax+8], ecx
0x18001c75a  movd    xmm1, ecx
0x18001c75e  cvtdq2pd xmm1, xmm1
0x18001c762  movq    rcx, xmm1
0x18001c767  mov     rax, rcx
0x18001c76a  shr     rax, 20h
0x18001c76e  cmp     eax, dword ptr [rsp+88h+arg_0+4]
0x18001c775  jnz     loc_18001CD3C
0x18001c77b  movd    eax, xmm2
0x18001c77f  cmp     ecx, eax
0x18001c781  jnz     loc_18001CD3C
0x18001c787  mov     rax, [rdi+8]
0x18001c78b  mov     [rax], r13d
0x18001c78e  mov     rax, [rdi+8]
0x18001c792  cmp     dword ptr [rax], 0
0x18001c795  jnz     short loc_18001C7A1
0x18001c797  mov     rax, [rdi+8]
0x18001c79b  mov     dword ptr [rax], 7Bh ; '{'
0x18001c7a1  mov     rax, [rdi+8]
0x18001c7a5  mov     eax, [rax]
0x18001c7a7  jmp     loc_18001C57B
0x18001c7ac  mov     rax, [rdi+8]; jumptable 000000018001C4CD case 21
0x18001c7b0  mov     dword ptr [rax], 73h ; 's'
0x18001c7b6  mov     rdx, [rdi+28h]
0x18001c7ba  movzx   eax, word ptr [rdx]
0x18001c7bd  cmp     ax, 2Fh ; '/'
0x18001c7c1  jnz     loc_18001CC0F
0x18001c7c7  lea     rcx, [rdx+2]
0x18001c7cb  mov     eax, 40h ; '@'
0x18001c7d0  mov     [rdi+28h], rcx
0x18001c7d4  cmp     ax, [rcx]
0x18001c7d7  jz      loc_18001D10F
0x18001c7dd  nop     dword ptr [rax]
0x18001c7e0  movzx   eax, word ptr [rcx]
0x18001c7e3  mov     rdx, rcx
0x18001c7e6  add     rcx, 2
0x18001c7ea  mov     [rdi+28h], rcx
0x18001c7ee  test    ax, ax
0x18001c7f1  jz      short loc_18001C7FF
0x18001c7f3  cmp     ax, 0Ah
0x18001c7f7  jz      short loc_18001C7FF
0x18001c7f9  cmp     ax, 0Dh
0x18001c7fd  jnz     short loc_18001C7E0
0x18001c7ff  test    byte ptr [rdi+60h], 10h
0x18001c803  mov     [rdi+28h], rdx
0x18001c807  jz      loc_18001C470
0x18001c80d  mov     rcx, [rdi+8]
0x18001c811  mov     eax, r14d
0x18001c814  mov     [rcx], r14d
0x18001c817  jmp     loc_18001C57B
0x18001c81c  mov     rax, [rdi+8]; jumptable 000000018001C4CD case 26
0x18001c820  mov     dword ptr [rax], 52h ; 'R'
0x18001c826  mov     rax, [rdi+28h]
0x18001c82a  cmp     word ptr [rax], 3Dh ; '='
0x18001c82e  jz      loc_18001CA96
0x18001c834  mov     rax, [rdi+8]
0x18001c838  mov     eax, [rax]
0x18001c83a  jmp     loc_18001C57B
0x18001c83f  mov     r8d, r15d; jumptable 000000018001C4CD case 3
0x18001c842  mov     rcx, rdi
0x18001c845  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18001c84a  jmp     loc_18001C57B
0x18001c84f  mov     rcx, rdi; jumptable 000000018001C4CD cases 12,13
0x18001c852  call    ?ScanStringConstant@Scanner@@AEAA?AW4tokens@@I@Z; Scanner::ScanStringConstant(uint)
0x18001c857  jmp     loc_18001C57B
0x18001c85c  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 33
0x18001c860  mov     eax, 50h ; 'P'
0x18001c865  mov     dword ptr [rcx], 50h ; 'P'
0x18001c86b  jmp     loc_18001C57B
0x18001c870  mov     rcx, [rdi+8]; jumptable 000000018001C4CD case 32
0x18001c874  mov     eax, 4Fh ; 'O'
0x18001c879  mov     dword ptr [rcx], 4Fh ; 'O'
0x18001c87f  jmp     loc_18001C57B
0x18001c884  mov     rax, [rdi+8]; jumptable 000000018001C4CD case 18
0x18001c888  mov     dword ptr [rax], 70h ; 'p'
0x18001c88e  mov     rcx, [rdi+28h]
0x18001c892  movzx   eax, word ptr [rcx]
0x18001c895  cmp     ax, 2Bh ; '+'
0x18001c899  jz      loc_18001CDC9
0x18001c89f  cmp     ax, 3Dh ; '='
0x18001c8a3  jz      loc_18001CEA6
0x18001c8a9  mov     rax, [rdi+8]
0x18001c8ad  mov     eax, [rax]
0x18001c8af  jmp     loc_18001C57B
0x18001c8b4  mov     rax, [rdi+8]; jumptable 000000018001C4CD case 11
0x18001c8b8  mov     dword ptr [rax], 76h ; 'v'
0x18001c8be  mov     rax, [rdi+28h]
0x18001c8c2  cmp     word ptr [rax], 3Dh ; '='
0x18001c8c6  jnz     short loc_18001C8E8
0x18001c8c8  add     rax, 2
0x18001c8cc  mov     [rdi+28h], rax
0x18001c8d0  mov     rax, [rdi+8]
0x18001c8d4  mov     dword ptr [rax], 66h ; 'f'
0x18001c8da  mov     rax, [rdi+28h]
0x18001c8de  cmp     word ptr [rax], 3Dh ; '='
0x18001c8e2  jz      loc_18001CEC3
0x18001c8e8  mov     rax, [rdi+8]
0x18001c8ec  mov     eax, [rax]
0x18001c8ee  jmp     loc_18001C57B
0x18001c8f3  or      r10d, 4
0x18001c8f7  lea     rcx, [r8+4]; unsigned __int16 *
0x18001c8fb  lea     rdx, [rsp+88h+arg_10]; unsigned __int16 **
0x18001c903  mov     [rdi+60h], r10d
0x18001c907  call    ?DblFromHex@@YANPEBGPEAPEBG@Z; DblFromHex(ushort const *,ushort const * *)
0x18001c90c  mov     rdx, [rdi+28h]
0x18001c910  movaps  xmm2, xmm0
0x18001c913  mov     rcx, [rsp+88h+arg_10]
0x18001c91b  lea     rax, [rdx+4]
0x18001c91f  cmp     rcx, rax
0x18001c922  jnz     loc_18001CBFD
0x18001c928  xorps   xmm2, xmm2
  ... truncated ...
```
