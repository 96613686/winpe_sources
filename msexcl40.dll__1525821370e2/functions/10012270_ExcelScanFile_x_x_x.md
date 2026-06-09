# ExcelScanFile(x,x,x)

- ea: `0x10012270`
- end: `0x10013231`
- name: `_ExcelScanFile@12`
- size: `4033`
- prototype: `int __fastcall(int *, _DWORD *, int)`
- caller_count: `7`
- callee_count: `23`
- tags: `file_ops`

## callers

- `0x10014710`
- `0x10016240`
- `0x100168a0`
- `0x1001abf0`
- `0x1001b4b0`
- `0x1001d6c0`
- `0x1001e5c0`

## callees

- `0x10007510`
- `0x1000dcc0`
- `0x1000dd90`
- `0x1000df70`
- `0x1000e440`
- `0x1000eec0`
- `0x1000f270`
- `0x1000f470`
- `0x1000f530`
- `0x1000fb30`
- `0x1000fbf0`
- `0x10010700`
- `0x10011e70`
- `0x10011f60`
- `0x10012270`
- `0x1002580a`
- `0x10025986`
- `0x10025ab7`
- `0x10025ed1`
- `0x10025f86`
- `0x10033c94`
- `0x10035510`
- `0x10035b40`

## pseudocode

```c
int __fastcall ExcelScanFile(int *a1, _DWORD *a2, int a3)
{
  bool v4; // zf
  int *v5; // ebx
  int v7; // esi
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  int *v11; // ecx
  int *v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // edi
  int String; // ebx
  unsigned __int16 *v17; // esi
  int v18; // ecx
  _DWORD *v19; // ecx
  size_t v20; // esi
  int v21; // ebx
  void *v22; // eax
  int v23; // eax
  int v24; // edx
  int (__thiscall *v25)(_DWORD, WCHAR *, int, int); // esi
  int v26; // eax
  int v27; // ecx
  __int16 v28; // bx
  const CHAR *v29; // esi
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // ebx
  __int64 v34; // rax
  double v35; // xmm0_8
  int (__thiscall *v36)(_DWORD, int, _DWORD); // ebx
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int *v40; // ebx
  int v41; // esi
  int v42; // eax
  int (__thiscall *v43)(_DWORD, int, int, LPCCH, _BYTE *); // ecx
  int v44; // ebx
  int v45; // eax
  WCHAR *v46; // edx
  int (__thiscall *v47)(_DWORD); // esi
  int v48; // ebx
  int v49; // ecx
  int *v50; // eax
  __int16 *v51; // ecx
  int v52; // edx
  int v53; // ebx
  __int16 *v54; // esi
  int (__thiscall *v55)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD); // ebx
  __int64 v56; // rax
  double v57; // xmm0_8
  const CHAR *v58; // ebx
  int *v59; // ecx
  int v60; // esi
  int v61; // eax
  int v62; // edx
  const CHAR *v63; // eax
  unsigned __int16 *v64; // edx
  __int16 *v65; // esi
  int v66; // eax
  int *v67; // ecx
  int v68; // eax
  int v69; // esi
  int v70; // edx
  __int16 *v71; // ecx
  int v72; // edx
  const CHAR *v73; // esi
  int (__thiscall *v74)(_DWORD, int, int, _DWORD); // ebx
  unsigned __int16 *v75; // eax
  int v76; // edx
  int v77; // ecx
  int v78; // eax
  _DWORD *v79; // eax
  int v80; // ebx
  int *v81; // [esp+28h] [ebp-1E0h]
  int cbMultiByte; // [esp+2Ch] [ebp-1DCh] BYREF
  LPCCH lpMultiByteStr; // [esp+30h] [ebp-1D8h] BYREF
  int v84; // [esp+34h] [ebp-1D4h] BYREF
  int v85; // [esp+38h] [ebp-1D0h] BYREF
  int *v86; // [esp+3Ch] [ebp-1CCh]
  int (__thiscall *v87)(_DWORD, int, int, LPCCH, _BYTE *); // [esp+40h] [ebp-1C8h] BYREF
  int v88; // [esp+44h] [ebp-1C4h]
  int *v89; // [esp+48h] [ebp-1C0h]
  _DWORD *v90; // [esp+4Ch] [ebp-1BCh]
  int v91; // [esp+50h] [ebp-1B8h]
  int v92; // [esp+54h] [ebp-1B4h]
  int *v93; // [esp+58h] [ebp-1B0h]
  WCHAR *v94; // [esp+5Ch] [ebp-1ACh]
  int v95; // [esp+60h] [ebp-1A8h] BYREF
  WCHAR *v96; // [esp+64h] [ebp-1A4h] BYREF
  int v97; // [esp+68h] [ebp-1A0h]
  int v98; // [esp+6Ch] [ebp-19Ch]
  unsigned __int64 v99; // [esp+70h] [ebp-198h]
  unsigned __int64 v100; // [esp+78h] [ebp-190h]
  int v101; // [esp+80h] [ebp-188h] BYREF
  int v102; // [esp+84h] [ebp-184h] BYREF
  _DWORD v103[2]; // [esp+88h] [ebp-180h] BYREF
  int v104; // [esp+90h] [ebp-178h] BYREF
  _DWORD v105[2]; // [esp+94h] [ebp-174h] BYREF
  int v106; // [esp+9Ch] [ebp-16Ch] BYREF
  int v107; // [esp+A0h] [ebp-168h] BYREF
  int v108; // [esp+A4h] [ebp-164h] BYREF
  int v109; // [esp+A8h] [ebp-160h]
  int v110; // [esp+ACh] [ebp-15Ch]
  int v111; // [esp+B0h] [ebp-158h] BYREF
  _BYTE v112[12]; // [esp+B4h] [ebp-154h] BYREF
  int v113; // [esp+C0h] [ebp-148h]
  char v114[4]; // [esp+C8h] [ebp-140h] BYREF
  char v115[4]; // [esp+CCh] [ebp-13Ch] BYREF
  _WORD v116[24]; // [esp+D0h] [ebp-138h] BYREF
  _BYTE v117[260]; // [esp+100h] [ebp-108h] BYREF

  v90 = a2;
  v4 = *a2 == 10;
  v5 = a1;
  v86 = a1;
  v81 = a1;
  if ( !v4 )
    return -14;
  v7 = *a1;
  if ( *a1 == 1 )
  {
    v5 = (int *)a1[11];
    v81 = v5;
  }
  NeedToReadRecords(v5, v117, a1, a2);
  v8 = v5[10];
  v9 = a3;
  if ( v8 )
  {
    if ( a3 )
    {
      *(_DWORD *)(v8 + 8) = a3;
      v11 = v81;
      v12 = v81;
      v89 = v81;
    }
    else
    {
      if ( !v7 || (v10 = ExcelWorksheetBOFPos(a1), v8 = v5[10], !v10) )
        v10 = *(_DWORD *)(v8 + 4);
      *(_DWORD *)(v8 + 8) = v10;
      v11 = v81;
      v12 = v81;
      v89 = v81;
      v81[21] = 0;
    }
  }
  else if ( a3 )
  {
    BFSetFilePosition(a3);
    v11 = v81;
    v12 = v81;
    v89 = v81;
  }
  else
  {
    if ( v7 )
      v9 = ExcelWorksheetBOFPos(a1);
    BFSetFilePosition(v9);
    v11 = v81;
    v12 = v81;
    v89 = v81;
    v81[21] = 0;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v13 = v11[10];
        if ( v13 )
          v14 = *(_DWORD *)(v13 + 8);
        else
          v14 = *(_DWORD *)(v12[5] + 8) + *(_DWORD *)(v12[5] + 84) - *(_DWORD *)(v12[5] + 4);
        v81[22] = v14;
        if ( ExcelReadRecordHeader(v81, &v85) )
          return -10;
        v15 = v85;
        String = 0;
        v17 = 0;
        v84 = (__int16)v85;
        cbMultiByte = 0;
        if ( v117[(unsigned __int8)v85]
          || (_WORD)v85 == 10
          || (_WORD)v85 == 9
          || (_WORD)v85 == 521
          || (_WORD)v85 == 1033
          || (_WORD)v85 == 2057 )
        {
          break;
        }
        v18 = v81[10];
        if ( v18 )
          *(_DWORD *)(v18 + 8) = **(_DWORD **)(v18 + 8);
        else
          BFSetFilePosition(SHIWORD(v85));
        v11 = v81;
        v12 = v89;
      }
      v19 = v90;
      if ( !v90[1] )
        break;
      v20 = SHIWORD(v85);
      v21 = v89[5];
      if ( SHIWORD(v85) <= g_cbCurrentSize )
      {
        v22 = pExcelRecordBuffer;
      }
      else
      {
        v22 = (void *)MemReAllocate(pExcelRecordBuffer);
        pExcelRecordBuffer = v22;
        if ( !v22 )
        {
          v23 = -2;
LABEL_215:
          v80 = dword_10001970[abs32(v23)];
          if ( v80 == -10 )
            return -10;
          return v80;
        }
        g_cbCurrentSize = v20;
      }
      v23 = BFReadFile(v21, v22, v20, v115);
      if ( v23 )
        goto LABEL_215;
      String = ((int (__thiscall *)(_DWORD, int, size_t, int, void *))v90[1])(
                 v90[1],
                 v84,
                 v20,
                 v81[22],
                 pExcelRecordBuffer);
      if ( String || (_WORD)v15 == 10 )
        return String;
      v11 = v81;
      v12 = v89;
    }
    if ( (_WORD)v85 != 127 )
    {
      String = ExcelReadTotalRecord(&cbMultiByte);
      if ( String )
        return String;
      v15 = v85;
      v17 = (unsigned __int16 *)cbMultiByte;
      v19 = v90;
    }
    v24 = (__int16)v15;
    v91 = (__int16)v15;
    if ( (__int16)v15 <= 421 )
    {
      if ( (__int16)v15 != 421 )
      {
        switch ( (__int16)v15 )
        {
          case 6:
            goto LABEL_171;
          case 9:
            goto LABEL_200;
          case 10:
            v11 = v81;
            v4 = v81[21]-- == 1;
            if ( !v4 )
              goto LABEL_210;
            v47 = (int (__thiscall *)(_DWORD))v90[50];
            if ( !v47 )
              goto LABEL_210;
            v26 = v47(v90[50]);
            goto LABEL_208;
          case 18:
          case 19:
          case 25:
          case 91:
          case 99:
          case 134:
            goto LABEL_113;
          case 24:
            goto LABEL_130;
          case 28:
          case 52:
            v84 = v19[45];
            v40 = v86;
            v93 = v86;
            v92 = 5;
            if ( *v86 == 1 )
            {
              v40 = (int *)v86[11];
              v93 = v40;
            }
            v88 = v40[1];
            if ( v88 >= 8 && (__int16)v15 == 28 )
              goto LABEL_92;
            v41 = *(_DWORD *)v17;
            v42 = *(__int16 *)(cbMultiByte + 4) + dword_1003A77C;
            lpMultiByteStr = (LPCCH)(cbMultiByte + 6);
            cbMultiByte = v42;
            if ( v42 )
            {
              if ( v91 == 52 )
              {
                v92 = v88;
                v40[1] = 4;
                v88 = 4;
              }
              v43 = (int (__thiscall *)(_DWORD, int, int, LPCCH, _BYTE *))v40[6];
              v44 = v42 + 1;
              v87 = v43;
              if ( v42 + 1 <= 512 )
              {
                v46 = &ExcelRecordTextBuffer;
                v44 = 512;
                v94 = &ExcelRecordTextBuffer;
              }
              else
              {
                v45 = MemAllocate(2 * v44);
                if ( !v45 )
                {
                  String = -2;
LABEL_104:
                  if ( v91 == 52 )
                    v93[1] = v92;
                  if ( String >= 0 )
                  {
                    String = ((int (__thiscall *)(int, int, WCHAR *, int, _DWORD))v84)(v84, v41, v94, String, 0);
                    if ( v94 != &ExcelRecordTextBuffer )
                      MemFree(v94);
                  }
                  goto LABEL_209;
                }
                v46 = (WCHAR *)v45;
                v94 = (WCHAR *)v45;
                v42 = cbMultiByte;
              }
              String = ExcelExtractString(v46, v44, lpMultiByteStr, v42);
              goto LABEL_104;
            }
            String = ExcelPeekRecordHeader(v40, &v111);
            if ( String )
              goto LABEL_209;
            v26 = ((int (__thiscall *)(int, int, _DWORD, _DWORD, bool))v84)(v84, v41, 0, 0, (_WORD)v111 == 150);
            goto LABEL_208;
          case 30:
            goto LABEL_183;
          case 34:
            v26 = ((int (__thiscall *)(_DWORD, _DWORD))v19[14])(v19[14], *(__int16 *)cbMultiByte);
            goto LABEL_208;
          case 47:
            return -12;
          case 66:
            v26 = ((int (__thiscall *)(_DWORD, _DWORD))v19[15])(v19[15], *(__int16 *)cbMultiByte);
            goto LABEL_208;
          case 92:
            v28 = HIWORD(v85);
            v84 = v19[25];
            cbMultiByte = 0;
            if ( v86[1] >= 8 )
            {
              if ( SHIWORD(v85) >= 2 )
              {
                v88 = *v17;
                if ( (v88 & 0x8000u) == 0
                  && FSafeSumU(&cbMultiByte)
                  && (unsigned int)cbMultiByte <= 0x7FFF
                  && v28 >= 0
                  && v28 >= (unsigned int)cbMultiByte )
                {
                  v29 = (const CHAR *)(v17 + 1);
                  goto LABEL_71;
                }
              }
            }
            else if ( SHIWORD(v85) > 0 )
            {
              v88 = *(unsigned __int8 *)v17;
              if ( FSafeSumU(&cbMultiByte) )
              {
                if ( (unsigned int)cbMultiByte <= 0x7FFF && v28 >= 0 && v28 >= (unsigned int)cbMultiByte )
                {
                  v29 = (char *)v17 + 1;
LABEL_71:
                  ExcelExtractString(&ExcelRecordTextBuffer, 512, v29, (__int16)v88);
                  v26 = ((int (__thiscall *)(int, WCHAR *))v84)(v84, &ExcelRecordTextBuffer);
                  goto LABEL_208;
                }
              }
            }
            break;
          case 133:
            v11 = v81;
            if ( v81[1] >= 5 )
            {
              v25 = (int (__thiscall *)(_DWORD, WCHAR *, int, int))v90[6];
              LOBYTE(v109) = *(_BYTE *)(cbMultiByte + 4);
              LOBYTE(v110) = *(_BYTE *)(cbMultiByte + 5);
              ExcelExtractString(
                &ExcelRecordTextBuffer,
                512,
                (LPCCH)(cbMultiByte + 7),
                *(unsigned __int8 *)(cbMultiByte + 6));
              v26 = v25(v25, &ExcelRecordTextBuffer, v110, v109);
              goto LABEL_208;
            }
            String = 0;
            goto LABEL_211;
          case 140:
            v26 = ((int (__thiscall *)(_DWORD, _DWORD))v19[51])(v19[51], *(__int16 *)cbMultiByte);
            goto LABEL_208;
          case 143:
            if ( v19[3] )
            {
              v26 = ExcelReadTotalRecord(&cbMultiByte);
              LOWORD(v15) = v85;
              goto LABEL_208;
            }
            v27 = v81[10];
            if ( v27 )
              *(_DWORD *)(v27 + 8) = **(_DWORD **)(v27 + 8);
            else
              BFSetFilePosition(SHIWORD(v85));
            goto LABEL_209;
          case 189:
            v30 = v19[37];
            v31 = *(_DWORD *)v17;
            v88 = v30;
            cbMultiByte = v31;
            v32 = 0;
            v91 = 0;
            v84 = (SHIWORD(v15) - 6) / 6;
            if ( v84 <= 0 )
              goto LABEL_92;
            while ( 2 )
            {
              LODWORD(v34) = 3 * v32;
              v33 = (__int16)v17[(_DWORD)v34 + 2];
              HIDWORD(v34) = *(_DWORD *)&v17[v34 + 3];
              if ( (BYTE4(v34) & 3) == 2 )
              {
                v35 = (double)(SHIDWORD(v34) >> 2);
              }
              else
              {
                if ( (v34 & 0x200000000LL) != 0 )
                {
                  v35 = (double)(SHIDWORD(v34) >> 2);
                  *(double *)&v99 = v35;
                }
                else
                {
                  v99 = v34 & 0xFFFFFFFC00000000uLL;
                  *(_QWORD *)&v35 = v34 & 0xFFFFFFFC00000000uLL;
                }
                if ( (v34 & 0x100000000LL) != 0 )
                {
                  v35 = v35 / 100.0;
                  *(double *)&v99 = v35;
                }
              }
              String = ((int (__thiscall *)(int, int, int, _DWORD, _DWORD))v88)(
                         v88,
                         v31,
                         v33,
                         LODWORD(v35),
                         HIDWORD(v35));
              if ( String )
                goto LABEL_209;
              ++HIWORD(cbMultiByte);
              v32 = v91 + 1;
              v91 = v32;
              if ( v32 < v84 )
              {
                v31 = cbMultiByte;
                continue;
              }
              goto LABEL_92;
            }
          case 190:
            v36 = (int (__thiscall *)(_DWORD, int, _DWORD))v19[38];
            v37 = *(_DWORD *)v17;
            v92 = (int)v36;
            cbMultiByte = v37;
            v84 = (SHIWORD(v15) - 6) / 2;
            v91 = 0;
            if ( v84 <= 0 )
              goto LABEL_92;
            v38 = v36(v36, v37, (__int16)v17[2]);
            while ( 2 )
            {
              String = v38;
              if ( v38 )
                goto LABEL_209;
              ++HIWORD(cbMultiByte);
              v39 = v91 + 1;
              v91 = v39;
              if ( v39 < v84 )
              {
                v38 = ((int (__thiscall *)(int, int, _DWORD))v92)(v92, cbMultiByte, (__int16)v17[v39 + 2]);
                continue;
              }
              goto LABEL_92;
            }
          case 214:
          case 253:
            goto LABEL_147;
          case 224:
            goto LABEL_195;
          default:
            goto LABEL_209;
        }
        goto LABEL_189;
      }
LABEL_113:
      v48 = 0;
      lpMultiByteStr = (LPCCH)v19[16];
      v49 = 1;
      if ( (__int16)v15 > 99 )
      {
        switch ( (__int16)v15 )
        {
          case 134:
            goto LABEL_124;
          case 221:
            v26 = ((int (__thiscall *)(LPCCH, int, _DWORD))lpMultiByteStr)(lpMultiByteStr, 6, (__int16)*v17);
            goto LABEL_208;
          case 421:
LABEL_124:
            v48 = 1;
            v49 = 4;
            break;
        }
LABEL_125:
        v26 = ((int (__thiscall *)(LPCCH, int, int))lpMultiByteStr)(lpMultiByteStr, v49, v48);
        goto LABEL_208;
      }
      if ( (__int16)v15 == 99 )
      {
        v26 = ((int (__thiscall *)(LPCCH, int, _DWORD))lpMultiByteStr)(lpMultiByteStr, 2, (__int16)*v17);
      }
      else
      {
        switch ( (__int16)v15 )
        {
          case 18:
            v26 = ((int (__thiscall *)(LPCCH, _DWORD, _DWORD))lpMultiByteStr)(lpMultiByteStr, 0, (__int16)*v17);
            break;
          case 19:
            v26 = ((int (__thiscall *)(LPCCH, int, _DWORD))lpMultiByteStr)(lpMultiByteStr, 5, (__int16)*v17);
            break;
          case 25:
            goto LABEL_117;
          case 91:
            v49 = 3;
LABEL_117:
            v26 = ((int (__thiscall *)(LPCCH, int, _DWORD))lpMultiByteStr)(lpMultiByteStr, v49, (__int16)*v17);
            break;
          default:
            goto LABEL_125;
        }
      }
LABEL_208:
      String = v26;
      goto LABEL_209;
    }
    if ( (__int16)v15 <= 1030 )
    {
      if ( (__int16)v15 == 1030 )
      {
LABEL_171:
        v93 = (int *)v19[41];
        v67 = v86;
        v4 = *v86 == 1;
        lpMultiByteStr = (LPCCH)(unsigned __int16)v15;
        if ( v4 )
          v67 = (int *)v86[11];
        v87 = (int (__thiscall *)(_DWORD, int, int, LPCCH, _BYTE *))(unsigned __int16)v15;
        v68 = cbMultiByte;
        v67[9] = 1;
        v69 = *(_DWORD *)v17;
        v92 = *(__int16 *)(v68 + 4);
        v84 = *(unsigned __int16 *)(v68 + 14);
        v116[0] = 0;
        String = FormulaCurrentValue(v116, 0);
        if ( !String )
        {
          if ( (_WORD)lpMultiByteStr == 6 )
          {
            v70 = cbMultiByte + 22;
            v71 = (__int16 *)(cbMultiByte + 20);
          }
          else
          {
            v70 = cbMultiByte + 18;
            v71 = (__int16 *)(cbMultiByte + 16);
          }
          String = BreakoutFormulaParts(v70, *v71, v112);
          if ( !String )
          {
            v66 = ((int (__thiscall *)(int *, int, int, int, _BYTE *, _WORD *))v93)(v93, v69, v92, v84, v112, v116);
LABEL_169:
            String = v66;
            if ( v113 )
              FreeArrayConstantList();
          }
        }
      }
      else
      {
        switch ( (__int16)v15 )
        {
          case 512:
            lpMultiByteStr = (LPCCH)v19[35];
            v50 = v86;
            if ( *v86 == 1 )
              v50 = (int *)v86[11];
            v51 = (__int16 *)(v17 + 2);
            if ( v50[1] >= 8 )
            {
              v53 = *(_DWORD *)v51;
              v51 = (__int16 *)(v17 + 4);
              v52 = *(_DWORD *)v17;
              v54 = (__int16 *)(v17 + 5);
            }
            else
            {
              v52 = (__int16)*v17;
              v53 = (__int16)v17[1];
              v54 = (__int16 *)(v17 + 3);
            }
            v26 = ((int (__thiscall *)(LPCCH, int, int, _DWORD, _DWORD))lpMultiByteStr)(
                    lpMultiByteStr,
                    v52,
                    v53,
                    *v51,
                    *v54);
            goto LABEL_208;
          case 513:
            v26 = ((int (__thiscall *)(_DWORD, _DWORD, _DWORD))v19[38])(
                    v19[38],
                    *(_DWORD *)cbMultiByte,
                    *(__int16 *)(cbMultiByte + 4));
            goto LABEL_208;
          case 515:
            v26 = ((int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))v19[37])(
                    v19[37],
                    *(_DWORD *)cbMultiByte,
                    *(__int16 *)(cbMultiByte + 4),
                    *(_DWORD *)(cbMultiByte + 6),
                    *(_DWORD *)(cbMultiByte + 10));
            goto LABEL_208;
          case 516:
LABEL_147:
            v58 = (const CHAR *)v19[36];
            v59 = v86;
            lpMultiByteStr = v58;
            v84 = 0;
            if ( *v86 == 1 )
              v59 = (int *)v86[11];
            v60 = *(_DWORD *)v17;
            v87 = (int (__thiscall *)(_DWORD, int, int, LPCCH, _BYTE *))*(__int16 *)(cbMultiByte + 4);
            LOWORD(v15) = v85;
            if ( v24 != 253 )
            {
              v62 = *(__int16 *)(cbMultiByte + 6);
              v63 = (const CHAR *)(cbMultiByte + 8);
              v95 = v62;
              if ( !v62 || !*v63 )
              {
LABEL_92:
                String = 0;
                goto LABEL_209;
              }
              v95 = ExcelExtractString(&ExcelRecordTextBuffer, 512, v63, v62);
              v96 = &ExcelRecordTextBuffer;
              v61 = ((int (__thiscall *)(const CHAR *, int, _DWORD, WCHAR *, int))v58)(
                      v58,
                      v60,
                      v87,
                      &ExcelRecordTextBuffer,
                      v95);
              goto LABEL_156;
            }
            if ( !v59[18] )
              goto LABEL_92;
            String = GetStringPoolEntry(&v96, &v95, &v84);
            if ( !String )
            {
              v61 = ((int (__thiscall *)(LPCCH, int, _DWORD, WCHAR *, int))lpMultiByteStr)(
                      lpMultiByteStr,
                      v60,
                      v87,
                      v96,
                      v95);
LABEL_156:
              String = v61;
              if ( v84 )
                MemFree(v96);
              goto LABEL_209;
            }
            break;
          case 517:
            ParseBoolerrRecord(&v87, &lpMultiByteStr, &v101);
            if ( v101 == 1 )
            {
              lpMultiByteStr = (LPCCH)v90[40];
              if ( !lpMultiByteStr )
                goto LABEL_209;
              ParseBoolerrRecord(v103, &v102, &v87);
              v26 = ((int (__thiscall *)(LPCCH, _DWORD, _DWORD, int))lpMultiByteStr)(
                      lpMultiByteStr,
                      v103[1],
                      v103[0],
                      v102);
              goto LABEL_208;
            }
            if ( !v101 )
            {
              lpMultiByteStr = (LPCCH)v90[39];
              if ( lpMultiByteStr )
              {
                ParseBoolerrRecord(v105, &v104, &v87);
                v26 = ((int (__thiscall *)(LPCCH, _DWORD, _DWORD, int))lpMultiByteStr)(
                        lpMultiByteStr,
                        v105[1],
                        v105[0],
                        v104);
                goto LABEL_208;
              }
            }
            goto LABEL_209;
          case 518:
            goto LABEL_171;
          case 521:
            goto LABEL_200;
          case 536:
LABEL_130:
            v26 = ProcessNameRecord(v17, v15);
            goto LABEL_208;
          case 545:
            v87 = (int (__thiscall *)(_DWORD, int, int, LPCCH, _BYTE *))v19[42];
            LOWORD(v97) = *v17;
            LOWORD(v98) = v17[1];
            HIWORD(v97) = *((unsigned __int8 *)v17 + 4);
            HIWORD(v98) = *((unsigned __int8 *)v17 + 5);
            lpMultiByteStr = (LPCCH)v17[3];
            if ( v86[1] < 5 )
            {
              v64 = v17 + 5;
              v65 = (__int16 *)(v17 + 4);
            }
            else
            {
              v64 = v17 + 7;
              v65 = (__int16 *)(v17 + 6);
            }
            String = BreakoutFormulaParts(v64, *v65, v112);
            if ( String )
              goto LABEL_209;
            v66 = v87(v87, v97, v98, lpMultiByteStr, v112);
            goto LABEL_169;
          case 579:
            goto LABEL_195;
          case 638:
            v55 = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))v19[37];
            HIDWORD(v56) = *(_DWORD *)(v17 + 3);
            LODWORD(v56) = *(_DWORD *)v17;
            if ( (BYTE4(v56) & 3) == 2 )
            {
              v57 = (double)(SHIDWORD(v56) >> 2);
            }
            else
            {
              if ( (v56 & 0x200000000LL) != 0 )
              {
                v57 = (double)(SHIDWORD(v56) >> 2);
                *(double *)&v100 = v57;
              }
              else
              {
                v100 = v56 & 0xFFFFFFFC00000000uLL;
                *(_QWORD *)&v57 = v56 & 0xFFFFFFFC00000000uLL;
              }
              if ( (v56 & 0x100000000LL) != 0 )
              {
                v57 = v57 / 100.0;
                *(double *)&v100 = v57;
              }
            }
            v26 = v55(v55, v56, (__int16)v17[2], LODWORD(v57), HIDWORD(v57));
            goto LABEL_208;
          default:
            goto LABEL_209;
        }
      }
      goto LABEL_209;
    }
    if ( (__int16)v15 > 1091 )
    {
      if ( (__int16)v15 != 2057 )
        goto LABEL_209;
    }
    else
    {
      if ( (__int16)v15 == 1091 )
      {
LABEL_195:
        v74 = (int (__thiscall *)(_DWORD, int, int, _DWORD))v19[24];
        v75 = v17 + 1;
        if ( (_WORD)v15 == 224 )
        {
          v76 = (__int16)*v75;
          v75 = v17 + 2;
          v77 = (__int16)*v17;
        }
        else
        {
          v77 = *(unsigned __int8 *)v17;
          v76 = *((unsigned __int8 *)v17 + 1);
        }
        v26 = v74(v74, v77, v76, *v75);
        goto LABEL_208;
      }
      if ( (__int16)v15 != 1033 )
      {
        if ( (__int16)v15 != 1054 )
        {
LABEL_209:
          v11 = v81;
          goto LABEL_210;
        }
LABEL_183:
        lpMultiByteStr = (LPCCH)v19[23];
        if ( (_WORD)v15 == 30 && v86[1] < 5 )
        {
          v72 = *(unsigned __int8 *)v17;
          v73 = (char *)v17 + 1;
          v84 = 0;
LABEL_194:
          ExcelExtractString(&ExcelRecordTextBuffer, 512, v73, v72);
          v26 = ((int (__thiscall *)(LPCCH, WCHAR *, int, int))lpMultiByteStr)(
                  lpMultiByteStr,
                  &ExcelRecordTextBuffer,
                  512,
                  v84);
          goto LABEL_208;
        }
        v84 = (__int16)*v17;
        if ( v86[1] > 5 )
        {
          v72 = (__int16)v17[1];
          v73 = (const CHAR *)(v17 + 2);
          if ( (unsigned int)(v72 + 4) > 0x7FFF || v85 < 0 || SHIWORD(v85) < (unsigned int)(v72 + 4) )
            goto LABEL_189;
        }
        else
        {
          v72 = *((unsigned __int8 *)v17 + 2);
          v73 = (char *)v17 + 3;
          if ( v85 < 0 || SHIWORD(v85) < (unsigned int)(v72 + 3) )
            goto LABEL_189;
        }
        if ( v72 >= 0 )
          goto LABEL_194;
LABEL_189:
        String = -10;
        goto LABEL_209;
      }
    }
LABEL_200:
    ParseBOFRecord(v17, v114, &v106, &v87, &lpMultiByteStr);
    v11 = v81;
    v78 = v81[21];
    if ( v78 > 0 )
      break;
    v79 = v90;
    v81[21] = 1;
    lpMultiByteStr = (LPCCH)v79[2];
    if ( lpMultiByteStr )
    {
      ParseBOFRecord(v17, &v108, &v107, &v84, &v87);
      v26 = ((int (__thiscall *)(LPCCH, int, int))lpMultiByteStr)(lpMultiByteStr, v108, v107);
      goto LABEL_208;
    }
LABEL_210:
    if ( String )
      return String;
LABEL_211:
    v12 = v11;
    if ( (_WORD)v15 == 10 && v11[21] <= 0 )
      return String;
  }
  if ( (v81[14] & 0x400) != 0 )
  {
    v81[21] = v78 + 1;
    goto LABEL_210;
  }
  if ( v106 == 32 || v106 == 256 )
  {
    v26 = SkipEmbeddedRegion();
    goto LABEL_208;
  }
  return -10;
}

```

## disassembly

```asm
0x10012270  mov     edi, edi
0x10012272  push    ebp
0x10012273  mov     ebp, esp
0x10012275  and     esp, 0FFFFFFC0h
0x10012278  sub     esp, 1F4h
0x1001227e  mov     eax, ___security_cookie
0x10012283  xor     eax, esp
0x10012285  mov     [esp+1F4h+var_4], eax
0x1001228c  push    ebx
0x1001228d  mov     eax, edx
0x1001228f  push    esi
0x10012290  push    edi
0x10012291  mov     edi, ecx
0x10012293  mov     [esp+200h+var_1BC], eax
0x10012297  cmp     dword ptr [eax], 0Ah
0x1001229a  mov     ebx, edi
0x1001229c  mov     [esp+200h+var_1CC], edi
0x100122a0  mov     [esp+200h+var_1E0], edi
0x100122a4  jz      short loc_100122C2
0x100122a6  mov     eax, 0FFFFFFF2h
0x100122ab  pop     edi
0x100122ac  pop     esi
0x100122ad  pop     ebx
0x100122ae  mov     ecx, [esp+1F4h+var_4]
0x100122b5  xor     ecx, esp; StackCookie
0x100122b7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100122bc  mov     esp, ebp
0x100122be  pop     ebp
0x100122bf  retn    4
0x100122c2  mov     esi, [edi]
0x100122c4  cmp     esi, 1
0x100122c7  jnz     short loc_100122D0
0x100122c9  mov     ebx, [edi+2Ch]
0x100122cc  mov     [esp+200h+var_1E0], ebx
0x100122d0  push    eax
0x100122d1  push    ecx
0x100122d2  lea     edx, [esp+208h+var_108]
0x100122d9  mov     ecx, ebx
0x100122db  call    NeedToReadRecords
0x100122e0  mov     ecx, [ebx+28h]
0x100122e3  mov     eax, [ebp+arg_0]
0x100122e6  test    ecx, ecx
0x100122e8  jz      short loc_10012328
0x100122ea  test    eax, eax
0x100122ec  jnz     short loc_10012319
0x100122ee  test    esi, esi
0x100122f0  jz      short loc_10012300
0x100122f2  mov     ecx, edi
0x100122f4  call    _ExcelWorksheetBOFPos@4; ExcelWorksheetBOFPos(x)
0x100122f9  mov     ecx, [ebx+28h]
0x100122fc  test    eax, eax
0x100122fe  jnz     short loc_10012303
0x10012300  mov     eax, [ecx+4]
0x10012303  mov     [ecx+8], eax
0x10012306  mov     ecx, [esp+200h+var_1E0]
0x1001230a  mov     eax, ecx
0x1001230c  mov     [esp+200h+var_1C0], eax
0x10012310  mov     dword ptr [ecx+54h], 0
0x10012317  jmp     short loc_1001236A
0x10012319  mov     [ecx+8], eax
0x1001231c  mov     ecx, [esp+200h+var_1E0]
0x10012320  mov     eax, ecx
0x10012322  mov     [esp+200h+var_1C0], eax
0x10012326  jmp     short loc_1001236A
0x10012328  test    eax, eax
0x1001232a  jnz     short loc_10012355
0x1001232c  test    esi, esi
0x1001232e  jz      short loc_10012337
0x10012330  mov     ecx, edi
0x10012332  call    _ExcelWorksheetBOFPos@4; ExcelWorksheetBOFPos(x)
0x10012337  mov     ecx, [ebx+14h]
0x1001233a  xor     edx, edx
0x1001233c  push    eax
0x1001233d  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10012342  mov     ecx, [esp+200h+var_1E0]
0x10012346  mov     eax, ecx
0x10012348  mov     [esp+200h+var_1C0], eax
0x1001234c  mov     dword ptr [ecx+54h], 0
0x10012353  jmp     short loc_1001236A
0x10012355  mov     ecx, [ebx+14h]
0x10012358  xor     edx, edx
0x1001235a  push    eax
0x1001235b  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10012360  mov     ecx, [esp+200h+var_1E0]
0x10012364  mov     eax, ecx
0x10012366  mov     [esp+200h+var_1C0], ecx
0x1001236a  mov     edx, 14h
0x1001236f  nop
0x10012370  mov     ecx, [ecx+28h]
0x10012373  test    ecx, ecx
0x10012375  jz      short loc_1001237C
0x10012377  mov     ecx, [ecx+8]
0x1001237a  jmp     short loc_10012388
0x1001237c  mov     eax, [eax+edx]
0x1001237f  mov     ecx, [eax+54h]
0x10012382  sub     ecx, [eax+4]
0x10012385  add     ecx, [eax+8]
0x10012388  mov     eax, [esp+200h+var_1E0]
0x1001238c  lea     edx, [esp+200h+var_1D0]
0x10012390  mov     [eax+58h], ecx
0x10012393  mov     ecx, eax
0x10012395  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x1001239a  test    eax, eax
0x1001239c  jnz     loc_10013215
0x100123a2  mov     edi, [esp+200h+var_1D0]
0x100123a6  xor     ebx, ebx
0x100123a8  movsx   eax, di
0x100123ab  xor     esi, esi
0x100123ad  mov     [esp+200h+var_1D4], eax
0x100123b1  movzx   eax, al
0x100123b4  mov     [esp+200h+cbMultiByte], esi
0x100123b8  cmp     [esp+eax+200h+var_108], bl
0x100123bf  jnz     short loc_10012434
0x100123c1  cmp     di, 0Ah
0x100123c5  jz      short loc_10012434
0x100123c7  cmp     di, 9
0x100123cb  jz      short loc_10012434
0x100123cd  mov     eax, 209h
0x100123d2  cmp     di, ax
0x100123d5  jz      short loc_10012434
0x100123d7  mov     eax, 409h
0x100123dc  cmp     di, ax
0x100123df  jz      short loc_10012434
0x100123e1  mov     eax, 809h
0x100123e6  cmp     di, ax
0x100123e9  jz      short loc_10012434
0x100123eb  mov     ecx, [esp+200h+var_1E0]
0x100123ef  mov     ecx, [ecx+28h]
0x100123f2  test    ecx, ecx
0x100123f4  jz      short loc_1001240B
0x100123f6  mov     eax, [ecx+8]
0x100123f9  mov     eax, [eax]
0x100123fb  mov     [ecx+8], eax
0x100123fe  mov     ecx, [esp+200h+var_1E0]
0x10012402  mov     eax, [esp+200h+var_1C0]
0x10012406  jmp     loc_1001236A
0x1001240b  movsx   eax, word ptr [esp+200h+var_1D0+2]
0x10012410  mov     edx, 1
0x10012415  mov     ecx, [esp+200h+var_1C0]
0x10012419  push    eax
0x1001241a  mov     eax, 14h
0x1001241f  mov     ecx, [ecx+eax]
0x10012422  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10012427  mov     ecx, [esp+200h+var_1E0]
0x1001242b  mov     eax, [esp+200h+var_1C0]
0x1001242f  jmp     loc_1001236A
0x10012434  mov     ecx, [esp+200h+var_1BC]
0x10012438  cmp     [ecx+4], ebx
0x1001243b  jz      loc_100124DF
0x10012441  mov     ecx, [esp+200h+var_1C0]
0x10012445  mov     eax, 14h
0x1001244a  movsx   esi, word ptr [esp+200h+var_1D0+2]
0x1001244f  mov     ebx, [ecx+eax]
0x10012452  cmp     esi, _g_cbCurrentSize
0x10012458  jbe     short loc_1001247C
0x1001245a  mov     ecx, _pExcelRecordBuffer; Src
0x10012460  mov     edx, esi
0x10012462  call    _MemReAllocate@8; MemReAllocate(x,x)
0x10012467  mov     _pExcelRecordBuffer, eax
0x1001246c  test    eax, eax
0x1001246e  jz      loc_100131A5
0x10012474  mov     _g_cbCurrentSize, esi
0x1001247a  jmp     short loc_10012481
0x1001247c  mov     eax, _pExcelRecordBuffer
0x10012481  lea     ecx, [esp+200h+var_13C]
0x10012488  mov     edx, eax
0x1001248a  push    ecx
0x1001248b  push    esi
0x1001248c  mov     ecx, ebx
0x1001248e  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x10012493  test    eax, eax
0x10012495  jnz     loc_100131AA
0x1001249b  push    _pExcelRecordBuffer
0x100124a1  mov     ecx, [esp+204h+var_1E0]
0x100124a5  mov     eax, [esp+204h+var_1BC]
0x100124a9  push    dword ptr [ecx+58h]
0x100124ac  push    esi
0x100124ad  mov     esi, [eax+4]
0x100124b0  mov     ecx, esi
0x100124b2  push    [esp+20Ch+var_1D4]
0x100124b6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100124bc  call    esi
0x100124be  mov     ebx, eax
0x100124c0  test    ebx, ebx
0x100124c2  jnz     loc_100131FC
0x100124c8  cmp     di, 0Ah
0x100124cc  jz      loc_100131FC
0x100124d2  mov     ecx, [esp+200h+var_1E0]
0x100124d6  mov     eax, [esp+200h+var_1C0]
0x100124da  jmp     loc_1001236A
0x100124df  cmp     di, 7Fh
0x100124e3  jz      short loc_1001250D
0x100124e5  mov     ecx, [esp+200h+var_1E0]
0x100124e9  lea     eax, [esp+200h+cbMultiByte]
0x100124ed  push    eax
0x100124ee  lea     edx, [esp+204h+var_1D0]
0x100124f2  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100124f7  mov     ebx, eax
0x100124f9  test    ebx, ebx
0x100124fb  jnz     loc_100131FC
0x10012501  mov     edi, [esp+200h+var_1D0]
0x10012505  mov     esi, [esp+200h+cbMultiByte]
0x10012509  mov     ecx, [esp+200h+var_1BC]
0x1001250d  movsx   edx, di
0x10012510  mov     eax, edx
0x10012512  mov     [esp+200h+var_1B8], edx
0x10012516  cmp     eax, 1A5h
0x1001251b  jg      loc_10012ADE
0x10012521  jz      loc_10012A2D; jumptable 1001253C cases 18,19,25,91,99,134
0x10012527  sub     eax, 6; switch 248 cases
0x1001252a  cmp     eax, 0F7h
0x1001252f  ja      def_1001253C; jumptable 1001253C default case, cases 7,8,11-17,20-23,26,27,29,31-33,35-46,48-51,53-65,67-90,93-98,100-132,135-139,141,142,144-188,191-213,215-223,225-252
0x10012535  movzx   eax, ds:byte_10013280[eax]
0x1001253c  jmp     ds:jpt_1001253C[eax*4]; switch jump
0x10012543  mov     ecx, [esp+200h+var_1E0]; jumptable 1001253C case 133
0x10012547  cmp     dword ptr [ecx+4], 5
0x1001254b  jl      short loc_100125B2
0x1001254d  mov     ecx, [esp+200h+cbMultiByte]
0x10012551  mov     eax, [esp+200h+var_1BC]
0x10012555  mov     esi, [eax+18h]
0x10012558  movzx   eax, byte ptr [ecx+4]
0x1001255c  mov     byte ptr [esp+200h+var_160], al
0x10012563  movzx   eax, byte ptr [ecx+5]
0x10012567  mov     byte ptr [esp+200h+var_15C], al
0x1001256e  movzx   eax, byte ptr [ecx+6]
0x10012572  push    eax; cbMultiByte
0x10012573  lea     eax, [ecx+7]
0x10012576  push    eax; lpMultiByteStr
0x10012577  mov     eax, [esp+208h+var_1CC]
0x1001257b  push    200h; cchWideChar
0x10012580  push    offset _ExcelRecordTextBuffer; lpWideCharStr
0x10012585  mov     edx, [eax+18h]
0x10012588  mov     ecx, [eax+4]
0x1001258b  call    _ExcelExtractString@24; ExcelExtractString(x,x,x,x,x,x)
0x10012590  push    [esp+200h+var_160]
0x10012597  mov     ecx, esi
0x10012599  push    [esp+204h+var_15C]
0x100125a0  push    offset _ExcelRecordTextBuffer
0x100125a5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100125ab  call    esi
0x100125ad  jmp     loc_1001317F
0x100125b2  xor     ebx, ebx
0x100125b4  jmp     loc_10013189
0x100125b9  cmp     dword ptr [ecx+0Ch], 0; jumptable 1001253C case 143
0x100125bd  jnz     short loc_100125F8
0x100125bf  mov     eax, [esp+200h+var_1E0]
0x100125c3  mov     ecx, [eax+28h]
0x100125c6  test    ecx, ecx
0x100125c8  jz      short loc_100125D7
0x100125ca  mov     eax, [ecx+8]
0x100125cd  mov     eax, [eax]
0x100125cf  mov     [ecx+8], eax
0x100125d2  jmp     def_1001253C; jumptable 1001253C default case, cases 7,8,11-17,20-23,26,27,29,31-33,35-46,48-51,53-65,67-90,93-98,100-132,135-139,141,142,144-188,191-213,215-223,225-252
0x100125d7  movsx   eax, word ptr [esp+200h+var_1D0+2]
0x100125dc  mov     edx, 1
0x100125e1  mov     ecx, [esp+200h+var_1C0]
0x100125e5  push    eax
0x100125e6  mov     eax, 14h
0x100125eb  mov     ecx, [ecx+eax]
0x100125ee  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x100125f3  jmp     def_1001253C; jumptable 1001253C default case, cases 7,8,11-17,20-23,26,27,29,31-33,35-46,48-51,53-65,67-90,93-98,100-132,135-139,141,142,144-188,191-213,215-223,225-252
0x100125f8  mov     ecx, [esp+200h+var_1E0]
0x100125fc  lea     eax, [esp+200h+cbMultiByte]
0x10012600  push    eax
0x10012601  lea     edx, [esp+204h+var_1D0]
0x10012605  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x1001260a  mov     edi, [esp+200h+var_1D0]
0x1001260e  jmp     loc_1001317F
0x10012613  mov     esi, [ecx+38h]; jumptable 1001253C case 34
0x10012616  mov     ecx, [esp+200h+cbMultiByte]
0x1001261a  movsx   eax, word ptr [ecx]
0x1001261d  mov     ecx, esi
0x1001261f  push    eax
0x10012620  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10012626  call    esi
0x10012628  jmp     loc_1001317F
0x1001262d  mov     esi, [ecx+3Ch]; jumptable 1001253C case 66
0x10012630  jmp     short loc_10012616
0x10012632  mov     eax, [ecx+64h]; jumptable 1001253C case 92
0x10012635  mov     bx, word ptr [esp+200h+var_1D0+2]
0x1001263a  mov     [esp+200h+var_1D4], eax
0x1001263e  mov     eax, [esp+200h+var_1CC]
0x10012642  mov     [esp+200h+cbMultiByte], 0
0x1001264a  cmp     dword ptr [eax+4], 8
0x1001264e  jge     short loc_100126AB
0x10012650  test    bx, bx
0x10012653  js      loc_10013025
0x10012659  cmp     bx, 1
0x1001265d  jb      loc_10013025
0x10012663  movzx   eax, byte ptr [esi]
0x10012666  lea     ecx, [esp+200h+cbMultiByte]
0x1001266a  push    ecx
0x1001266b  movsx   edx, ax
0x1001266e  mov     ecx, 1
0x10012673  mov     [esp+204h+var_1C4], eax
0x10012677  call    _FSafeSumU@12; FSafeSumU(x,x,x)
0x1001267c  test    eax, eax
0x1001267e  jz      loc_10013025
0x10012684  mov     ecx, [esp+200h+cbMultiByte]
0x10012688  cmp     ecx, 7FFFh
  ... truncated ...
```
