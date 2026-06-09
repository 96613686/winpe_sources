# ConvertToDateTime(tagDBC *,void *,short,long,void *,short,long,long *,short,XLATDIR,ColMetaDataCache *)

- ea: `0x1004dbcc8`
- end: `0x1004dd4fc`
- name: `?ConvertToDateTime@@YAGPEAUtagDBC@@PEAXFJ1FJPEAJFW4XLATDIR@@PEAUColMetaDataCache@@@Z`
- size: `6196`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1004d7cf0`

## callees

- `0x100412efc`
- `0x1004d8d30`
- `0x1004d9694`
- `0x1004d9850`
- `0x1004dbcc8`
- `0x1004ded08`
- `0x1004e1ac8`
- `0x1004e2840`
- `0x1004e2ab8`
- `0x1004e2ba0`
- `0x10052b000`
- `0x100538f74`
- `0x1005407d0`
- `0x100540a7c`
- `0x100540d5c`
- `0x100540da4`
- `0x100540e18`
- `0x100540fd8`
- `0x100541158`
- `0x1005411d4`
- `0x100548210`
- `0x100548a18`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dbf61`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dd450`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dd4bd`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dbf61`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dd450`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004dd4bd`

## pseudocode

```c
unsigned __int16 __fastcall ConvertToDateTime(
        __int64 a1,
        _OWORD *a2,
        __int16 a3,
        int a4,
        struct tagTIMESTAMP_STRUCT *Destination,
        __int16 a6,
        int a7,
        int *a8,
        __int16 a9,
        int a10,
        __int64 a11)
{
  struct tagTIMESTAMP_STRUCT *v11; // r13
  int *v12; // r12
  WCHAR *v13; // rsi
  unsigned __int64 v14; // rdi
  int v15; // r9d
  __int64 v16; // r8
  unsigned __int16 v17; // bx
  int v18; // r11d
  USHORT hour; // di
  USHORT minute; // r11
  USHORT second; // r10
  unsigned int fraction; // r9d
  unsigned __int16 day; // r8
  int v24; // eax
  unsigned __int16 result; // ax
  __int64 v26; // rdx
  int v27; // eax
  struct tagTIMESTAMP_STRUCT v28; // xmm6
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rsi
  __int16 v32; // ax
  __int16 epi16; // dx
  __int16 v34; // bx
  BOOL v35; // eax
  USHORT month; // bx
  SHORT year; // dx
  int v38; // eax
  int v39; // eax
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdi
  WCHAR *v42; // r12
  __int64 v43; // rbx
  unsigned int ECode; // eax
  __int64 v45; // rdx
  BOOL v46; // eax
  unsigned int v47; // r15d
  const unsigned __int16 *v48; // rbx
  unsigned __int16 v49; // di
  unsigned __int8 near **v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rdx
  unsigned __int16 v53; // r10
  __int64 v54; // r8
  signed __int64 v55; // rdx
  _BYTE *v56; // rcx
  char v57; // al
  bool v58; // zf
  __int64 v59; // r8
  char v60; // al
  char v61; // al
  char v62; // al
  _BYTE *v63; // rax
  __int64 v64; // rsi
  _BYTE *v65; // rcx
  __int64 v66; // rax
  unsigned __int64 v67; // rax
  char v68; // al
  _BYTE *v69; // rax
  unsigned __int64 v70; // rsi
  __int16 v71; // r15
  int v72; // esi
  __int64 v73; // rdi
  __int64 v74; // rax
  __int64 v75; // rax
  unsigned __int64 v77; // rcx
  int v78; // eax
  __int64 v79; // rax
  rsize_t v80; // rcx
  int v81; // eax
  rsize_t v82; // rcx
  int v83; // ecx
  int v84; // [rsp+28h] [rbp-E0h]
  bool v85[4]; // [rsp+38h] [rbp-D0h]
  bool v86[4]; // [rsp+38h] [rbp-D0h]
  int v88; // [rsp+64h] [rbp-A4h]
  __int16 v89; // [rsp+68h] [rbp-A0h]
  unsigned __int16 v90[2]; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned int v91[2]; // [rsp+70h] [rbp-98h] BYREF
  int *v92; // [rsp+78h] [rbp-90h]
  unsigned int v93; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v94; // [rsp+84h] [rbp-84h] BYREF
  int v95[2]; // [rsp+88h] [rbp-80h] BYREF
  struct tagTIMESTAMP_STRUCT v96; // [rsp+90h] [rbp-78h] BYREF
  struct tagTIMESTAMP_STRUCT v97; // [rsp+A0h] [rbp-68h] BYREF
  struct tagTIMESTAMP_STRUCT v98; // [rsp+B0h] [rbp-58h] BYREF
  int v99; // [rsp+C0h] [rbp-48h]
  USHORT v100; // [rsp+C8h] [rbp-40h] BYREF
  USHORT v101; // [rsp+CAh] [rbp-3Eh]
  USHORT v102; // [rsp+CCh] [rbp-3Ch]
  ULONG v103; // [rsp+D0h] [rbp-38h]
  _WORD v104[4]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned int v105; // [rsp+E0h] [rbp-28h]
  char v106; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v107[2]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v108[62]; // [rsp+10Ah] [rbp+2h] BYREF
  WCHAR WideCharStr[104]; // [rsp+148h] [rbp+40h] BYREF

  v11 = (struct tagTIMESTAMP_STRUCT *)&v106;
  v12 = a8;
  v13 = (WCHAR *)a2;
  v14 = a4;
  v15 = a3;
  v16 = a1;
  *a8 = 0;
  v17 = 0;
  LOWORD(v91[0]) = v15;
  if ( Destination )
    v11 = Destination;
  v92 = a8;
  v18 = 20;
  if ( Destination )
    v18 = a7;
  v88 = v18;
  v99 = 0;
  *(_QWORD *)v95 = v11;
  v98 = 0;
  if ( v15 <= -8 )
  {
    if ( v15 != -8 )
    {
      if ( v15 != -32 )
      {
        if ( v15 == -29 )
        {
          if ( (unsigned __int16)(a6 + 30) <= 0x2Fu )
          {
            v26 = 0x810000000003LL;
            if ( _bittest64(&v26, (unsigned int)(unsigned __int16)a6 + 30) )
              return -25421;
          }
          if ( a6 == 0x4000 )
            return -25421;
          OledbDateFromSqlDate((const unsigned __int8 *)v13, v14, (struct tagDBDATE *)&v98);
          if ( (unsigned __int16)(v98.year - 1) > 0x270Eu || (unsigned __int16)(v98.month - 1) > 0xBu )
            return -25410;
          day = v98.day;
          if ( v98.month == 2 )
          {
            if ( !(v98.year % 4) && v98.year != 100 * (v98.year / 100) || (v27 = 0, v98.year == 400 * (v98.year / 400)) )
              v27 = 1;
            if ( v98.day > (unsigned __int16)((v27 != 0) + 28) )
              return -25410;
          }
          if ( v98.day > (unsigned __int16)((((1 << (16 - LOBYTE(v98.month))) & 0xAB50) != 0) + 30) || !v98.day )
            return -25410;
          v17 = 0;
          goto LABEL_290;
        }
        if ( (unsigned int)(v15 + 24) <= 1 )
          goto LABEL_31;
        if ( v15 == -22 )
        {
          if ( a6 != -24 )
          {
            if ( a6 == 11 && a11 )
            {
              *(_DWORD *)(a11 + 4) = 1;
              *(_QWORD *)(a11 + 8) = ConvertDateTimeToTimestampStruct;
              *(_WORD *)(a11 + 20) = 0;
            }
LABEL_31:
            v17 = ConvertDateTimeToTimestampStruct(a2, v14, (unsigned __int8 *)&v98);
            if ( v17 )
              return v17;
            goto LABEL_289;
          }
        }
        else
        {
          if ( v15 != -21 )
          {
            if ( (unsigned int)(v15 + 20) > 1 )
            {
              if ( v15 == -13 )
              {
                TimestampFromDateTime2((const unsigned __int8 *)a2, v14, a9, (struct tagDBTIMESTAMP *)&v98);
                hour = v98.hour;
                if ( v98.hour <= 0x17u )
                {
                  minute = v98.minute;
                  if ( v98.minute <= 0x3Bu )
                  {
                    second = v98.second;
                    if ( v98.second <= 0x3Bu )
                    {
                      fraction = v98.fraction;
                      if ( v98.fraction <= 0x3B9AC9FF )
                      {
                        if ( (unsigned __int16)(v98.year - 1) <= 0x270Eu && (unsigned __int16)(v98.month - 1) <= 0xBu )
                        {
                          day = v98.day;
                          if ( v98.month != 2 )
                            goto LABEL_27;
                          if ( !(v98.year % 4) && v98.year != 100 * (v98.year / 100)
                            || (v24 = 0, v98.year == 400 * (v98.year / 400)) )
                          {
                            v24 = 1;
                          }
                          if ( v98.day <= (unsigned __int16)((v24 != 0) + 28) )
                          {
LABEL_27:
                            if ( v98.day <= (unsigned __int16)((((1 << (16 - LOBYTE(v98.month))) & 0xAB50) != 0) + 30)
                              && v98.day )
                            {
                              v17 = 0;
LABEL_292:
                              v28 = v98;
                              goto LABEL_293;
                            }
                          }
                        }
                        return -25410;
                      }
                    }
                  }
                }
                return -25409;
              }
              return -25421;
            }
LABEL_104:
            v28 = (struct tagTIMESTAMP_STRUCT)*a2;
            v32 = a6;
            v98 = (struct tagTIMESTAMP_STRUCT)*a2;
            if ( *(_QWORD *)(a1 + 120) )
            {
LABEL_109:
              if ( v32 == -29 )
              {
                *(_DWORD *)&v98.hour = 0;
                hour = 0;
                v98.second = 0;
                minute = 0;
                v98.fraction = 0;
                second = 0;
                v28 = (struct tagTIMESTAMP_STRUCT)*(unsigned __int64 *)&v98.year;
                fraction = 0;
                goto LABEL_112;
              }
LABEL_111:
              fraction = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v28, 12));
              second = _mm_extract_epi16((__m128i)v28, 5);
              minute = _mm_extract_epi16((__m128i)v28, 4);
              hour = _mm_extract_epi16((__m128i)v28, 3);
LABEL_112:
              if ( !(fraction % dword_1005A08D8[a9]) )
              {
                if ( hour > 0x17u || minute > 0x3Bu || second > 0x3Bu || fraction > 0x3B9AC9FF )
                  return -25409;
                epi16 = _mm_extract_epi16((__m128i)v28, 1);
                v34 = _mm_cvtsi128_si32((__m128i)v28);
                if ( (unsigned __int16)(v34 - 1) > 0x270Eu || (unsigned __int16)(epi16 - 1) > 0xBu )
                  return -25410;
                day = _mm_extract_epi16((__m128i)v28, 2);
                if ( epi16 == 2 )
                {
                  v35 = !(v34 % 4) && v34 != 100 * (v34 / 100) || v34 == 400 * (v34 / 400);
                  if ( day > (unsigned __int16)(v35 + 28) )
                    return -25410;
                }
                if ( day > (unsigned __int16)((((1 << (16 - epi16)) & 0xAB50) != 0) + 30) || !day )
                  return -25410;
                v17 = 0;
LABEL_56:
                *(_DWORD *)&v98.year = _mm_cvtsi128_si32((__m128i)v28);
LABEL_293:
                v31 = a1;
                goto LABEL_294;
              }
              return -25045;
            }
            if ( a6 != 18 )
            {
LABEL_108:
              if ( !*(_QWORD *)(v16 + 120) )
                goto LABEL_111;
              goto LABEL_109;
            }
            result = PopulateTimeZoneValues((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
            if ( !result )
            {
              v28 = v98;
              v32 = a6;
              v16 = a1;
              goto LABEL_108;
            }
            return result;
          }
          if ( a6 != -23 )
            goto LABEL_31;
        }
        memcpy_s(v11, v18, a2, v14);
        *a8 = v14;
        return 0;
      }
      v28 = (struct tagTIMESTAMP_STRUCT)*a2;
      v99 = *((_DWORD *)a2 + 4);
      v29 = HIDWORD(*((_QWORD *)a2 + 1));
      v98 = v28;
      if ( (unsigned int)v29 % dword_1005A08D8[a9] )
        return -25045;
LABEL_55:
      fraction = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v28, 12));
      second = _mm_extract_epi16((__m128i)v28, 5);
      minute = _mm_extract_epi16((__m128i)v28, 4);
      hour = _mm_extract_epi16((__m128i)v28, 3);
      day = _mm_extract_epi16((__m128i)v28, 2);
      goto LABEL_56;
    }
    goto LABEL_176;
  }
  switch ( v15 )
  {
    case -2:
      if ( !*(_QWORD *)(a1 + 64)
        || (v74 = *(_QWORD *)(a1 + 64), *(_BYTE *)(v74 + 3878) < 0xAu)
        || (*(_BYTE *)(v74 + 416) & 2) != 0 )
      {
        if ( a6 == 11 )
        {
          *a8 = 16;
        }
        else if ( (unsigned __int16)(a6 - 9) <= 1u )
        {
          *a8 = 6;
        }
        else if ( a6 == -13 )
        {
          *a8 = 8;
        }
        if ( *a8 > v18 )
          return -25412;
        _mm_lfence();
        memcpy_s(v11, v18, a2, *a8);
        return 0;
      }
      if ( (unsigned __int16)(a6 - 9) <= 1u || (unsigned __int16)(a6 + 30) <= 1u )
        return -25421;
      if ( a6 == 17 )
      {
        if ( (_DWORD)v14 != 12 )
          return -25412;
        fraction = *((_DWORD *)a2 + 2);
        if ( !(fraction % dword_1005A08D8[a9]) )
        {
          if ( *(_WORD *)a2 <= 0x17u
            && *((_WORD *)a2 + 1) <= 0x3Bu
            && *((_WORD *)a2 + 2) <= 0x3Bu
            && fraction <= 0x3B9AC9FF )
          {
            hour = *(_WORD *)a2;
            day = 1;
            minute = *((_WORD *)a2 + 1);
            second = *((_WORD *)a2 + 2);
            v98.hour = *(_WORD *)a2;
            v98.minute = minute;
            v98.second = second;
            v98.fraction = fraction;
            *(_DWORD *)&v98.year = 67436;
            v98.day = 1;
            goto LABEL_292;
          }
          return -25409;
        }
        return -25045;
      }
      if ( a6 != 18 )
      {
        if ( a6 == 11 )
        {
          v83 = 16;
        }
        else
        {
          if ( a6 != -13 )
            goto LABEL_289;
          v83 = 8;
        }
        *a8 = v83;
        if ( v83 <= v18 )
        {
          _mm_lfence();
          memcpy_s(v11, v18, a2, *a8);
          return 0;
        }
        return -25412;
      }
      if ( (_DWORD)v14 != 20 )
        return -25412;
      v28 = (struct tagTIMESTAMP_STRUCT)*a2;
      v99 = *((_DWORD *)a2 + 4);
      v75 = HIDWORD(*((_QWORD *)a2 + 1));
      v98 = v28;
      if ( (unsigned int)v75 % dword_1005A08D8[a9] )
        return -25045;
LABEL_72:
      result = ValidateDateTimeOffsetStruct((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
      v17 = result;
      if ( result )
        return result;
      goto LABEL_55;
    case 1:
      if ( (_DWORD)v14 )
      {
        v40 = v14;
        do
        {
          if ( *((_BYTE *)a2 + v40 - 1) != 32 )
            break;
          LODWORD(v14) = v14 - 1;
          --v40;
        }
        while ( v40 );
        LODWORD(v14) = 2 * SystemLocale::FastAsciiMultiByteToWideChar(0, (LPCCH)a2, (int)v14, WideCharStr, 0x64u, 0, 0);
        if ( !(_DWORD)v14 )
          return -25411;
        v13 = WideCharStr;
      }
LABEL_176:
      v41 = (unsigned __int64)(int)v14 >> 1;
      v42 = v13;
      if ( !(_DWORD)v41 )
        goto LABEL_214;
      do
      {
        if ( *v42 != 32 && (unsigned __int16)(*v42 - 9) > 4u )
          break;
        ++v42;
        LODWORD(v41) = v41 - 1;
      }
      while ( (_DWORD)v41 );
      v11 = *(struct tagTIMESTAMP_STRUCT **)v95;
      if ( !(_DWORD)v41 )
      {
LABEL_214:
        v43 = a1;
        goto LABEL_215;
      }
      v43 = a1;
      if ( (unsigned __int16)(*v42 - 48) <= 9u )
        goto LABEL_215;
      _mm_lfence();
      ECode = FindECode((struct tagDBC *)a1, v42, v41, &v94, v90, v95);
      v45 = ECode;
      v91[1] = ECode;
      if ( ECode >= (unsigned int)v41 )
        goto LABEL_185;
      if ( v90[0] )
      {
        if ( ECode != 4 )
          goto LABEL_185;
      }
      else if ( ECode != 1 )
      {
LABEL_185:
        v46 = 0;
        goto LABEL_186;
      }
      v51 = 2 * ECode + v94;
      if ( (unsigned int)v41 < (unsigned int)v51 )
        return -25411;
      v42 += v51;
      LODWORD(v41) = v41 - (2 * v45 + v94);
      if ( (_DWORD)v41 )
      {
        do
        {
          if ( *v42 != 32 && (unsigned __int16)(*v42 - 9) > 4u )
            break;
          ++v42;
          LODWORD(v41) = v41 - 1;
        }
        while ( (_DWORD)v41 );
        v43 = a1;
      }
      v46 = v41 == 0;
LABEL_186:
      if ( v46 )
      {
        v47 = v94 - v90[0];
        v48 = &v13[v45 + v90[0]];
        v31 = a1;
        if ( GetLexToken((struct tagDBC *)a1, v48, v47, &v91[1], &v93) == 1 && v93 == 2 )
        {
          if ( (v48[v91[1]] & 0x5F) != 0x54 )
            goto LABEL_211;
          if ( (v48[v91[1] + 1] & 0x5F) == 0x53 )
            goto LABEL_203;
        }
        if ( v93 == 1 && (((v48[v91[1]] & 0x5F) - 68) & 0xFFEF) == 0 )
        {
          if ( (v48[v91[1]] & 0x5F) == 0x44 )
          {
            v49 = 1;
            v50 = &rgbECODE_DATE;
            goto LABEL_206;
          }
LABEL_203:
          if ( v93 == 2 )
          {
            v49 = 3;
            v50 = &rgbECODE_TIMESTAMP;
          }
          else
          {
            v49 = 2;
            v50 = &rgbECODE_TIME;
          }
LABEL_206:
          if ( v47 >= v93 + v91[1] )
          {
            _mm_lfence();
            *(_WORD *)v85 = a6;
            v17 = ParseDateTime(a1, v50, v49, &v48[v93 + v91[1]], v47 - (v93 + v91[1]), &v98, *(_DWORD *)v85, 0, a10);
            if ( v17 && v17 != 0x9E0D )
            {
              _mm_lfence();
              return v17;
            }
            day = v98.day;
            v12 = v92;
            goto LABEL_169;
          }
          return -25411;
        }
LABEL_211:
        result = -25400;
        if ( a6 == -13 )
          return -25408;
        return result;
      }
LABEL_215:
      if ( (unsigned int)v41 >= 8 )
      {
        do
        {
          v52 = (unsigned int)(v41 - 1);
          if ( v42[v52] != 32 )
            break;
          LODWORD(v41) = v41 - 1;
        }
        while ( (unsigned int)v52 >= 8 );
      }
      if ( (_DWORD)v41 == 10 )
      {
        if ( v42[5] != 58 )
        {
          v53 = 1;
          v89 = 1;
          v54 = 64;
          v55 = (char *)&rgbECODE_DATE - v107;
          v56 = v107;
          do
          {
            if ( v54 == -2147483582 )
              break;
            v57 = v56[v55];
            if ( !v57 )
              break;
            *v56++ = v57;
            --v54;
          }
          while ( v54 );
          v58 = v54 == 0;
          goto LABEL_243;
        }
      }
      else
      {
        if ( (_DWORD)v41 == 8 )
        {
          v89 = 2;
          v53 = 2;
          v56 = v107;
          v55 = (char *)&rgbECODE_TIME - v107;
          v59 = 64;
          do
          {
            if ( v59 == -2147483582 )
              break;
            v60 = v56[v55];
            if ( !v60 )
              break;
            *v56++ = v60;
            --v59;
          }
          while ( v59 );
          v58 = v59 == 0;
LABEL_243:
          v63 = v56 - 1;
          if ( !v58 )
            v63 = v56;
          v64 = -1;
          v65 = v107;
          *v63 = 0;
          v66 = -1;
          do
            ++v66;
          while ( v107[v66] );
          v67 = v66 - 2;
          if ( v67 < 0x40 )
          {
            v107[v67] = 0;
            *(_WORD *)v85 = a6;
            v17 = ParseDateTime(v43, v108, v53, v42, v41, &v98, *(_DWORD *)v85, 1, a10);
            if ( v17 != 0x9CBD )
            {
              v72 = a10;
              v71 = a6;
              v73 = a1;
              goto LABEL_261;
            }
            if ( v89 != 1 )
              return v17;
            v55 = 64;
            v65 = v107;
            do
            {
              if ( v55 == -2147483582 )
                break;
              v68 = v65[(char *)&rgbECODE_DATE_SLASH - v107];
              if ( !v68 )
                break;
              *v65++ = v68;
              --v55;
            }
            while ( v55 );
            v69 = v65 - 1;
            if ( v55 )
              v69 = v65;
            *v69 = 0;
            do
              ++v64;
            while ( v107[v64] );
            v70 = v64 - 2;
            if ( v70 < 0x40 )
            {
              v71 = a6;
              v107[v70] = 0;
              v72 = a10;
              *(_WORD *)v86 = a6;
              v84 = v41;
              v73 = a1;
              v17 = ParseDateTime(a1, v108, 1, v42, v84, &v98, *(_DWORD *)v86, 1, a10);
LABEL_261:
              if ( v17 && v17 != 0x9E0D )
                return v17;
              if ( !*(_QWORD *)(v73 + 120) || v71 != -29 && v71 != 9 )
              {
                fraction = v98.fraction;
                if ( v98.fraction % dword_1005A08D8[a9] && !v72 )
                  return -25045;
                day = v98.day;
                v12 = v92;
LABEL_291:
                second = v98.second;
                minute = v98.minute;
                hour = v98.hour;
                goto LABEL_292;
              }
              goto LABEL_84;
            }
          }
          _report_rangecheckfailure(v65, v55);
        }
        if ( (unsigned int)(v41 - 8) > 0xA )
        {
          if ( (unsigned int)(v41 - 19) > 0x11 )
            return -25411;
          v53 = 13;
          v89 = 13;
          v55 = 64;
          v56 = v107;
          do
          {
            if ( v55 == -2147483582 )
              break;
            v62 = v56[(char *)&rgbECODE_TIMESTAMPOFFSET - v107];
            if ( !v62 )
              break;
            *v56++ = v62;
            --v55;
          }
          while ( v55 );
          goto LABEL_242;
        }
      }
      v53 = 12;
      v89 = 12;
      v56 = v107;
      v55 = 64;
      do
      {
        if ( v55 == -2147483582 )
          break;
        v61 = v56[(char *)&rgbECODE_TIME2 - v107];
        if ( !v61 )
          break;
        *v56++ = v61;
        --v55;
      }
      while ( v55 );
LABEL_242:
      v58 = v55 == 0;
      goto LABEL_243;
    case 9:
      if ( a6 == 10 || a6 == 17 || a6 == 0x4000 )
        return -25421;
      day = *((_WORD *)a2 + 2);
      v31 = a1;
      *(_DWORD *)&v98.year = *(_DWORD *)a2;
      v98.day = day;
      if ( !*(_QWORD *)(a1 + 120) && a6 == 18 )
      {
        result = PopulateTimeZoneValues((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
        if ( result )
          return result;
        day = v98.day;
      }
      if ( (unsigned __int16)(v98.year - 1) > 0x270Eu || (unsigned __int16)(v98.month - 1) > 0xBu )
        return -25410;
      if ( v98.month == 2 )
      {
        if ( !(v98.year % 4) && v98.year != 100 * (v98.year / 100) || (v39 = 0, v98.year == 400 * (v98.year / 400)) )
          v39 = 1;
        if ( day > (unsigned __int16)((v39 != 0) + 28) )
          return -25410;
      }
      if ( day > (unsigned __int16)((((1 << (16 - LOBYTE(v98.month))) & 0xAB50) != 0) + 30) || !day )
        return -25410;
      v17 = 0;
LABEL_169:
      v28 = v98;
      hour = v98.hour;
      minute = v98.minute;
      second = v98.second;
      fraction = v98.fraction;
      goto LABEL_294;
    case 10:
      if ( a6 == 9 )
        return -25421;
      second = *((_WORD *)a2 + 2);
      *(_DWORD *)&v98.hour = *(_DWORD *)a2;
      v98.second = second;
      if ( *(_QWORD *)(a1 + 120) )
      {
        year = 1900;
        v98.day = 1;
        month = 1;
        v98.year = 1900;
        v98.month = 1;
        day = 1;
      }
      else
      {
        SetCurrentDate((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
        if ( a6 == 18 )
        {
          result = PopulateTimeZoneValues((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
          if ( result )
            return result;
        }
        second = v98.second;
        day = v98.day;
        month = v98.month;
        year = v98.year;
      }
      hour = v98.hour;
      if ( v98.hour <= 0x17u )
      {
        minute = v98.minute;
        if ( v98.minute <= 0x3Bu && second <= 0x3Bu )
        {
          fraction = v98.fraction;
          if ( v98.fraction <= 0x3B9AC9FF )
          {
            if ( (unsigned __int16)(year - 1) <= 0x270Eu && (unsigned __int16)(month - 1) <= 0xBu )
            {
              if ( month != 2
                || (!(year % 4) && year != 100 * (year / 100) || year == 400 * (year / 400) ? (v38 = 1) : (v38 = 0),
                    day <= (unsigned __int16)((v38 != 0) + 28)) )
              {
                if ( day <= (unsigned __int16)((((1 << (16 - month)) & 0xAB50) != 0) + 30) && day )
                {
                  v17 = 0;
                  goto LABEL_292;
                }
              }
            }
            return -25410;
          }
        }
      }
      return -25409;
    case 11:
      goto LABEL_104;
    case 17:
      if ( a6 != 9 && a6 != -29 )
      {
        OledbTime2FromSqlTime((const unsigned __int8 *)a2, v14, a9, (struct tagSS_TIME2_STRUCT *)&v100);
        hour = v100;
        if ( v100 <= 0x17u )
        {
          minute = v101;
          if ( v101 <= 0x3Bu )
          {
            second = v102;
            if ( v102 <= 0x3Bu )
            {
              fraction = v103;
              if ( v103 <= 0x3B9AC9FF )
              {
                v31 = a1;
                v98.hour = v100;
                v98.minute = v101;
                v98.second = v102;
                v98.fraction = v103;
                if ( *(_QWORD *)(a1 + 120) )
                {
                  *(_DWORD *)&v98.year = 67436;
                  day = 1;
                  v98.day = 1;
                }
                else
                {
                  SetCurrentDate((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
                  fraction = v98.fraction;
                  second = v98.second;
                  minute = v98.minute;
                  day = v98.day;
                  hour = v98.hour;
                }
                v28 = v98;
LABEL_294:
                if ( a6 <= -13 )
                {
                  if ( a6 != -13 )
                  {
                    if ( a6 == -32 )
                    {
                      *v12 = 20;
                      if ( v88 >= 20 )
                      {
                        v78 = v99;
                        *v11 = v28;
                        *(_DWORD *)&v11[1].year = v78;
                        return v17;
                      }
                      return -25412;
                    }
                    if ( a6 == -31 )
                    {
                      *v12 = 12;
                      if ( v88 >= 12 )
                      {
                        v11->year = hour;
                        v11->month = minute;
                        v11->day = second;
                        v11->hour = 0;
                        *(_DWORD *)&v11->minute = fraction;
                        return v17;
                      }
                      return -25412;
                    }
                    if ( a6 != -30 )
                    {
                      if ( a6 != -29 )
                      {
                        if ( (unsigned int)(a6 + 24) <= 3 )
                        {
LABEL_301:
                          _mm_lfence();
                          return ConvertToLegacyDateTime((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98, v11, v88, v12, a6);
                        }
                        return v17;
                      }
                      if ( !*(_QWORD *)(v31 + 120) && (hour || minute || second || fraction) )
                        return -25305;
                      *v12 = 3;
                      if ( v88 >= 3 )
                      {
                        _mm_lfence();
                        return SqlDateFromOledbDate((struct tagDBDATE *)&v98, (unsigned __int8 *)v11, 3u);
                      }
                      return -25412;
                    }
                    if ( (LOWORD(v91[0]) == 0xFFF3
                       || LOWORD(v91[0]) == 11
                       || (unsigned __int16)(LOWORD(v91[0]) - 0x4000) <= 1u)
                      && fraction )
                    {
                      return -25305;
                    }
                    goto LABEL_316;
                  }
                  if ( !*(_QWORD *)(v31 + 64) )
                    goto LABEL_301;
                  v79 = *(_QWORD *)(v31 + 64);
                  if ( *(_BYTE *)(v79 + 3878) < 0xAu || (*(_BYTE *)(v79 + 416) & 2) != 0 )
                    goto LABEL_301;
                  if ( a9 <= 7 )
                  {
                    v80 = dword_1005A0898[a9];
                    *v12 = v80;
                    if ( v88 >= (int)v80 )
                    {
                      _mm_lfence();
                      return DateTime2FromTimestamp((struct tagDBTIMESTAMP *)&v98, a9, (unsigned __int8 *)v11, v80);
                    }
                    return -25412;
                  }
                  return -25412;
                }
                if ( a6 == 9 )
                {
                  if ( hour || minute || second || fraction )
                    v17 = -25075;
                  *(_DWORD *)&v11->year = *(_DWORD *)&v98.year;
                  v11->day = day;
                }
                else
                {
                  if ( a6 != 10 )
                  {
                    if ( a6 == 11 )
                    {
                      *v11 = v28;
                      *v12 = 16;
                      return v17;
                    }
                    if ( a6 == 17 )
                    {
LABEL_316:
                      if ( a9 <= 7 )
                      {
                        v104[0] = hour;
                        v77 = dword_1005A0878[a9];
                        *v12 = v77;
                        v104[1] = minute;
                        v104[2] = second;
                        v105 = fraction;
                        if ( v88 >= (int)v77 )
                        {
                          _mm_lfence();
                          return SqlTimeFromOledbTime2(
                                   (struct tagSS_TIME2_STRUCT *)v104,
                                   a9,
                                   (unsigned __int8 *)v11,
                                   v77);
                        }
                        return -25412;
                      }
                      return -25412;
                    }
                    if ( a6 != 18 )
                    {
                      if ( a6 == 0x4000 )
                      {
                        v11->year = hour;
                        v11->month = minute;
                        v11->day = second;
                        v11->hour = 0;
                        *(_DWORD *)&v11->minute = fraction;
                        *v12 = 12;
                      }
                      else if ( a6 == 16385 )
                      {
                        v81 = v99;
                        *v11 = v28;
                        *(_DWORD *)&v11[1].year = v81;
                        *v12 = 20;
                      }
                      return v17;
                    }
                    if ( a9 <= 7 )
                    {
                      v82 = dword_1005A08B8[a9];
                      *v12 = v82;
                      if ( v88 >= (int)v82 )
                      {
                        _mm_lfence();
                        return DateTimeOffsetFromTimestampOffset(
                                 (struct tagDBTIMESTAMP *)&v98,
                                 a9,
                                 (unsigned __int8 *)v11,
                                 v82);
                      }
                      return -25412;
                    }
                    return -25412;
                  }
                  if ( fraction )
                    v17 = -25075;
                  *(_DWORD *)&v11->year = *(_DWORD *)&v98.hour;
                  v11->day = second;
                }
                *v12 = 6;
                return v17;
              }
            }
          }
        }
        return -25409;
      }
      return -25421;
  }
  if ( v15 != 18 )
  {
    if ( v15 == 0x4000 )
    {
      if ( a6 == 9 )
        return -25421;
      fraction = *((_DWORD *)a2 + 2);
      if ( !(fraction % dword_1005A08D8[a9]) )
      {
        hour = *(_WORD *)a2;
        if ( *(_WORD *)a2 > 0x17u )
          return -25409;
        minute = *((_WORD *)a2 + 1);
        if ( minute > 0x3Bu )
          return -25409;
        second = *((_WORD *)a2 + 2);
        if ( second > 0x3Bu || fraction > 0x3B9AC9FF )
          return -25409;
        v98.hour = *(_WORD *)a2;
        v98.minute = minute;
        v98.second = second;
        v98.fraction = fraction;
        if ( *(_QWORD *)(a1 + 120) )
        {
          v12 = v92;
          day = 1;
          *(_DWORD *)&v98.year = 67436;
          v98.day = 1;
          goto LABEL_292;
        }
        SetCurrentDate((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
        if ( a6 == 18 )
        {
          v17 = PopulateTimeZoneValues((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
          if ( v17 )
            return v17;
        }
LABEL_84:
        v12 = v92;
LABEL_289:
        day = v98.day;
LABEL_290:
        fraction = v98.fraction;
        goto LABEL_291;
      }
    }
    else
    {
      if ( v15 != 16385 )
        return -25421;
      v28 = (struct tagTIMESTAMP_STRUCT)*a2;
      v99 = *((_DWORD *)a2 + 4);
      v30 = HIDWORD(*((_QWORD *)a2 + 1));
      v98 = v28;
      if ( !((unsigned int)v30 % dword_1005A08D8[a9]) )
      {
        if ( !*(_QWORD *)(a1 + 120) && ((unsigned __int16)(a6 - 91) <= 2u || a6 == -154) )
        {
          result = ConvertOffsetToUTC((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98, &v96);
          if ( result )
            return result;
          v28 = v96;
          v98 = v96;
        }
        goto LABEL_72;
      }
    }
    return -25305;
  }
  TimestampOffsetFromDateTimeOffset((const unsigned __int8 *)a2, v14, a9, (struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
  v31 = a1;
  if ( *(_QWORD *)(a1 + 120) || (unsigned __int16)(a6 - 9) > 2u && a6 != 0x4000 )
  {
    v28 = v98;
  }
  else
  {
    result = ConvertOffsetToLocal((const struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98, &v97);
    if ( result )
      return result;
    v28 = v97;
    v99 = 0;
    v98 = v97;
  }
  result = ValidateDateTimeOffsetStruct((struct tagSS_TIMESTAMPOFFSET_STRUCT *)&v98);
  v17 = result;
  if ( !result )
  {
    *(_DWORD *)&v98.year = _mm_cvtsi128_si32((__m128i)v28);
    fraction = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v28, 12));
    second = _mm_extract_epi16((__m128i)v28, 5);
    minute = _mm_extract_epi16((__m128i)v28, 4);
    hour = _mm_extract_epi16((__m128i)v28, 3);
    day = _mm_extract_epi16((__m128i)v28, 2);
    goto LABEL_294;
  }
  return result;
}

```

## disassembly

```asm
0x1004dbcc8  mov     rax, rsp
0x1004dbccb  mov     [rax+18h], rbx
0x1004dbccf  push    rbp
0x1004dbcd0  push    rsi
0x1004dbcd1  push    rdi
0x1004dbcd2  push    r12
0x1004dbcd4  push    r13
0x1004dbcd6  push    r14
0x1004dbcd8  push    r15
0x1004dbcda  lea     rbp, [rax-168h]
0x1004dbce1  sub     rsp, 230h
0x1004dbce8  movaps  xmmword ptr [rax-48h], xmm6
0x1004dbcec  mov     rax, cs:__security_cookie
0x1004dbcf3  xor     rax, rsp
0x1004dbcf6  mov     [rbp+160h+var_50], rax
0x1004dbcfd  mov     rax, [rbp+160h+Destination]
0x1004dbd04  lea     r13, [rbp+160h+var_180]
0x1004dbd08  mov     r12, [rbp+160h+arg_38]
0x1004dbd0f  xorps   xmm0, xmm0
0x1004dbd12  movzx   r10d, [rbp+160h+arg_40]
0x1004dbd1a  mov     rsi, rdx
0x1004dbd1d  mov     rdx, [rbp+160h+arg_50]
0x1004dbd24  movsxd  rdi, r9d
0x1004dbd27  movsx   r9d, r8w
0x1004dbd2b  mov     r8, rcx
0x1004dbd2e  mov     [rsp+260h+var_210], rcx
0x1004dbd33  xor     ecx, ecx
0x1004dbd35  test    rax, rax
0x1004dbd38  mov     [r12], ecx
0x1004dbd3c  movzx   ebx, cx
0x1004dbd3f  mov     word ptr [rsp+260h+var_1F8], r9w
0x1004dbd45  cmovnz  r13, rax
0x1004dbd49  mov     [rsp+260h+var_1F0], r12
0x1004dbd4e  lea     r11d, [rcx+14h]
0x1004dbd52  mov     word ptr [rsp+260h+var_208], r10w
0x1004dbd58  cmovnz  r11d, [rbp+160h+arg_30]
0x1004dbd60  mov     ecx, r9d
0x1004dbd63  xor     eax, eax
0x1004dbd65  mov     [rsp+260h+var_204], r11d
0x1004dbd6a  mov     [rbp+160h+var_1A8], eax
0x1004dbd6d  mov     eax, 0Ah
0x1004dbd72  mov     qword ptr [rbp+160h+var_1E0], r13
0x1004dbd76  movups  [rbp+160h+var_1B8], xmm0
0x1004dbd7a  lea     r15d, [rax+1]
0x1004dbd7e  lea     r9d, [rax-1]
0x1004dbd82  lea     r14d, [rax-9]
0x1004dbd86  cmp     ecx, 0FFFFFFF8h
0x1004dbd89  jg      loc_1004DC13C
0x1004dbd8f  jz      loc_1004DC9B8
0x1004dbd95  cmp     ecx, 0FFFFFFE0h
0x1004dbd98  jz      loc_1004DC0D3
0x1004dbd9e  lea     ebx, [rax-27h]
0x1004dbda1  cmp     ecx, ebx
0x1004dbda3  jz      loc_1004DBFA4
0x1004dbda9  lea     eax, [rcx+18h]
0x1004dbdac  cmp     eax, r14d
0x1004dbdaf  jbe     loc_1004DBF2A
0x1004dbdb5  cmp     ecx, 0FFFFFFEAh
0x1004dbdb8  jz      loc_1004DBF48
0x1004dbdbe  cmp     ecx, 0FFFFFFEBh
0x1004dbdc1  jz      loc_1004DBF20
0x1004dbdc7  lea     eax, [rcx+14h]
0x1004dbdca  cmp     eax, r14d
0x1004dbdcd  jbe     loc_1004DC4AC
0x1004dbdd3  cmp     ecx, 0FFFFFFF3h
0x1004dbdd6  jnz     loc_1004DD45A
0x1004dbddc  mov     rdx, rdi; unsigned __int64
0x1004dbddf  lea     r9, [rbp+160h+var_1B8]; struct tagDBTIMESTAMP *
0x1004dbde3  mov     r8b, r10b; unsigned __int8
0x1004dbde6  mov     rcx, rsi; Source
0x1004dbde9  call    ?TimestampFromDateTime2@@YAXPEBE_KEPEAUtagDBTIMESTAMP@@@Z; TimestampFromDateTime2(uchar const *,unsigned __int64,uchar,tagDBTIMESTAMP *)
0x1004dbdee  movzx   edi, word ptr [rbp+160h+var_1B8+6]
0x1004dbdf2  cmp     di, 17h
0x1004dbdf6  ja      loc_1004DBF16
0x1004dbdfc  movzx   r11d, word ptr [rbp+160h+var_1B8+8]
0x1004dbe01  cmp     r11w, 3Bh ; ';'
0x1004dbe06  ja      loc_1004DBF16
0x1004dbe0c  movzx   r10d, word ptr [rbp+160h+var_1B8+0Ah]
0x1004dbe11  cmp     r10w, 3Bh ; ';'
0x1004dbe16  ja      loc_1004DBF16
0x1004dbe1c  mov     r9d, dword ptr [rbp+160h+var_1B8+0Ch]
0x1004dbe20  cmp     r9d, 3B9AC9FFh
0x1004dbe27  ja      loc_1004DBF16
0x1004dbe2d  movzx   edx, word ptr [rbp+160h+var_1B8+2]
0x1004dbe31  lea     ecx, [rbx+2Dh]
0x1004dbe34  movzx   eax, word ptr [rbp+160h+var_1B8]
0x1004dbe38  sub     ecx, edx
0x1004dbe3a  mov     r15d, r14d
0x1004dbe3d  sub     ax, r14w
0x1004dbe41  shl     r15d, cl
0x1004dbe44  mov     ecx, 270Eh
0x1004dbe49  and     r15d, 0AB50h
0x1004dbe50  cmp     ax, cx
0x1004dbe53  ja      loc_1004DC09C
0x1004dbe59  movzx   eax, dx
0x1004dbe5c  lea     ecx, [rbx+28h]
0x1004dbe5f  sub     ax, r14w
0x1004dbe63  cmp     ax, cx
0x1004dbe66  ja      loc_1004DC09C
0x1004dbe6c  movzx   r8d, word ptr [rbp+160h+var_1B8+4]
0x1004dbe71  lea     eax, [rbx+1Fh]
0x1004dbe74  cmp     dx, ax
0x1004dbe77  jnz     short loc_1004DBEE4
0x1004dbe79  movsx   esi, word ptr [rbp+160h+var_1B8]
0x1004dbe7d  mov     eax, esi
0x1004dbe7f  and     eax, 80000003h
0x1004dbe84  jge     short loc_1004DBE8F
0x1004dbe86  sub     eax, r14d
0x1004dbe89  or      eax, 0FFFFFFFCh
0x1004dbe8c  add     eax, r14d
0x1004dbe8f  xor     ecx, ecx
0x1004dbe91  mov     ebx, 51EB851Fh
0x1004dbe96  test    eax, eax
0x1004dbe98  jnz     short loc_1004DBEB1
0x1004dbe9a  mov     eax, ebx
0x1004dbe9c  imul    esi
0x1004dbe9e  sar     edx, 5
0x1004dbea1  mov     eax, edx
0x1004dbea3  shr     eax, 1Fh
0x1004dbea6  add     edx, eax
0x1004dbea8  imul    ecx, edx, 64h ; 'd'
0x1004dbeab  cmp     esi, ecx
0x1004dbead  jnz     short loc_1004DBECB
0x1004dbeaf  xor     ecx, ecx
0x1004dbeb1  mov     eax, ebx
0x1004dbeb3  imul    esi
0x1004dbeb5  sar     edx, 7
0x1004dbeb8  mov     eax, edx
0x1004dbeba  shr     eax, 1Fh
0x1004dbebd  add     edx, eax
0x1004dbebf  imul    eax, edx, 190h
0x1004dbec5  cmp     esi, eax
0x1004dbec7  mov     eax, ecx
0x1004dbec9  jnz     short loc_1004DBECE
0x1004dbecb  mov     eax, r14d
0x1004dbece  neg     eax
0x1004dbed0  sbb     ax, ax
0x1004dbed3  neg     ax
0x1004dbed6  add     ax, 1Ch
0x1004dbeda  cmp     r8w, ax
0x1004dbede  ja      loc_1004DC09C
0x1004dbee4  neg     r15d
0x1004dbee7  sbb     ax, ax
0x1004dbeea  neg     ax
0x1004dbeed  add     ax, 1Eh
0x1004dbef1  cmp     r8w, ax
0x1004dbef5  ja      loc_1004DC09C
0x1004dbefb  xor     eax, eax
0x1004dbefd  test    r8w, r8w
0x1004dbf01  jz      loc_1004DC09C
0x1004dbf07  mov     ebx, eax
0x1004dbf09  mov     eax, 0Bh
0x1004dbf0e  lea     edx, [rax-18h]
0x1004dbf11  jmp     loc_1004DD0FB
0x1004dbf16  mov     eax, 9CBFh
0x1004dbf1b  jmp     loc_1004DD4C7
0x1004dbf20  cmp     [rbp+160h+arg_28], 0FFE9h
0x1004dbf28  jz      short loc_1004DBF55
0x1004dbf2a  lea     r8, [rbp+160h+var_1B8]; unsigned __int8 *
0x1004dbf2e  mov     edx, edi; int
0x1004dbf30  mov     rcx, rsi; void *
0x1004dbf33  call    ?ConvertDateTimeToTimestampStruct@@YAGPEAXJPEAE@Z; ConvertDateTimeToTimestampStruct(void *,long,uchar *)
0x1004dbf38  movzx   ebx, ax
0x1004dbf3b  test    ax, ax
0x1004dbf3e  jz      short loc_1004DBF97
0x1004dbf40  movzx   eax, bx
0x1004dbf43  jmp     loc_1004DD4C7
0x1004dbf48  movzx   eax, [rbp+160h+arg_28]
0x1004dbf4f  cmp     ax, 0FFE8h
0x1004dbf53  jnz     short loc_1004DBF75
0x1004dbf55  mov     r9, rdi; SourceSize
0x1004dbf58  movsxd  rdx, r11d; DestinationSize
0x1004dbf5b  mov     r8, rsi; Source
0x1004dbf5e  mov     rcx, r13; Destination
0x1004dbf61  call    cs:__imp_memcpy_s
0x1004dbf67  xor     ecx, ecx
0x1004dbf69  mov     [r12], edi
0x1004dbf6d  movzx   eax, cx
0x1004dbf70  jmp     loc_1004DD4C7
0x1004dbf75  cmp     ax, r15w
0x1004dbf79  jnz     short loc_1004DBF2A
0x1004dbf7b  xor     ecx, ecx
0x1004dbf7d  test    rdx, rdx
0x1004dbf80  jz      short loc_1004DBF2A
0x1004dbf82  lea     rax, ?ConvertDateTimeToTimestampStruct@@YAGPEAXJPEAE@Z; ConvertDateTimeToTimestampStruct(void *,long,uchar *)
0x1004dbf89  mov     [rdx+4], r14d
0x1004dbf8d  mov     [rdx+8], rax
0x1004dbf91  mov     [rdx+14h], cx
0x1004dbf95  jmp     short loc_1004DBF2A
0x1004dbf97  mov     eax, r15d
0x1004dbf9a  mov     edx, 0FFFFFFF3h
0x1004dbf9f  jmp     loc_1004DD0E4
0x1004dbfa4  movzx   ecx, [rbp+160h+arg_28]
0x1004dbfab  lea     eax, [rcx+1Eh]
0x1004dbfae  cmp     ax, 2Fh ; '/'
0x1004dbfb2  ja      short loc_1004DBFC8
0x1004dbfb4  mov     rdx, 810000000003h
0x1004dbfbe  bt      rdx, rax
0x1004dbfc2  jb      loc_1004DD45A
0x1004dbfc8  mov     eax, 4000h
0x1004dbfcd  cmp     cx, ax
0x1004dbfd0  jz      loc_1004DD45A
0x1004dbfd6  mov     rdx, rdi; unsigned __int64
0x1004dbfd9  lea     r8, [rbp+160h+var_1B8]; struct tagDBDATE *
0x1004dbfdd  mov     rcx, rsi; Source
0x1004dbfe0  call    ?OledbDateFromSqlDate@@YAXPEBE_KPEAUtagDBDATE@@@Z; OledbDateFromSqlDate(uchar const *,unsigned __int64,tagDBDATE *)
0x1004dbfe5  movzx   edx, word ptr [rbp+160h+var_1B8+2]
0x1004dbfe9  mov     ecx, 10h
0x1004dbfee  movzx   eax, word ptr [rbp+160h+var_1B8]
0x1004dbff2  sub     ecx, edx
0x1004dbff4  mov     r10d, r14d
0x1004dbff7  sub     ax, r14w
0x1004dbffb  shl     r10d, cl
0x1004dbffe  mov     ecx, 270Eh
0x1004dc003  and     r10d, 0AB50h
0x1004dc00a  cmp     ax, cx
0x1004dc00d  ja      loc_1004DC09C
0x1004dc013  movzx   eax, dx
0x1004dc016  sub     ax, r14w
0x1004dc01a  cmp     ax, r15w
0x1004dc01e  ja      short loc_1004DC09C
0x1004dc020  movzx   r8d, word ptr [rbp+160h+var_1B8+4]
0x1004dc025  mov     eax, 2
0x1004dc02a  cmp     dx, ax
0x1004dc02d  jnz     short loc_1004DC0A6
0x1004dc02f  movsx   r9d, word ptr [rbp+160h+var_1B8]
0x1004dc034  mov     eax, r9d
0x1004dc037  and     eax, 80000003h
0x1004dc03c  jge     short loc_1004DC047
0x1004dc03e  sub     eax, r14d
0x1004dc041  or      eax, 0FFFFFFFCh
0x1004dc044  add     eax, r14d
0x1004dc047  xor     r11d, r11d
0x1004dc04a  mov     ebx, 51EB851Fh
0x1004dc04f  test    eax, eax
0x1004dc051  jnz     short loc_1004DC06A
0x1004dc053  mov     eax, ebx
0x1004dc055  imul    r9d
0x1004dc058  sar     edx, 5
0x1004dc05b  mov     eax, edx
0x1004dc05d  shr     eax, 1Fh
0x1004dc060  add     edx, eax
0x1004dc062  imul    ecx, edx, 64h ; 'd'
0x1004dc065  cmp     r9d, ecx
0x1004dc068  jnz     short loc_1004DC087
0x1004dc06a  mov     eax, ebx
0x1004dc06c  imul    r9d
0x1004dc06f  sar     edx, 7
0x1004dc072  mov     eax, edx
0x1004dc074  shr     eax, 1Fh
0x1004dc077  add     edx, eax
0x1004dc079  imul    eax, edx, 190h
0x1004dc07f  cmp     r9d, eax
0x1004dc082  mov     eax, r11d
0x1004dc085  jnz     short loc_1004DC08A
0x1004dc087  mov     eax, r14d
0x1004dc08a  neg     eax
0x1004dc08c  sbb     ax, ax
0x1004dc08f  neg     ax
0x1004dc092  add     ax, 1Ch
0x1004dc096  cmp     r8w, ax
0x1004dc09a  jbe     short loc_1004DC0A9
0x1004dc09c  mov     eax, 9CBEh
0x1004dc0a1  jmp     loc_1004DD4C7
0x1004dc0a6  xor     r11d, r11d
0x1004dc0a9  neg     r10d
0x1004dc0ac  sbb     ax, ax
0x1004dc0af  neg     ax
0x1004dc0b2  add     ax, 1Eh
0x1004dc0b6  cmp     r8w, ax
0x1004dc0ba  ja      short loc_1004DC09C
0x1004dc0bc  test    r8w, r8w
0x1004dc0c0  jz      short loc_1004DC09C
0x1004dc0c2  movzx   ebx, r11w
0x1004dc0c6  mov     eax, r15d
0x1004dc0c9  mov     edx, 0FFFFFFF3h
0x1004dc0ce  jmp     loc_1004DD0E9
0x1004dc0d3  mov     eax, [rsi+10h]
0x1004dc0d6  xor     edx, edx
0x1004dc0d8  movups  xmm6, xmmword ptr [rsi]
0x1004dc0db  mov     [rbp+160h+var_1A8], eax
0x1004dc0de  mov     rax, [rsi+8]
0x1004dc0e2  movsx   rcx, r10w
0x1004dc0e6  lea     r10, __ImageBase
0x1004dc0ed  shr     rax, 20h
0x1004dc0f1  movups  [rbp+160h+var_1B8], xmm6
0x1004dc0f5  div     ds:rva dword_1005A08D8[r10+rcx*4]
0x1004dc0fd  test    edx, edx
0x1004dc0ff  jnz     loc_1004DD0BE
0x1004dc105  movdqa  xmm0, xmm6
0x1004dc109  mov     eax, r15d
0x1004dc10c  psrldq  xmm0, 0Ch
0x1004dc111  movd    r9d, xmm0
0x1004dc116  pextrw  r10d, xmm6, 5
0x1004dc11c  pextrw  r11d, xmm6, 4
0x1004dc122  pextrw  edi, xmm6, 3
0x1004dc127  pextrw  r8d, xmm6, 2
0x1004dc12d  movd    dword ptr [rbp+160h+var_1B8], xmm6
0x1004dc132  mov     edx, 0FFFFFFF3h
0x1004dc137  jmp     loc_1004DD0FF
  ... truncated ...
```
