# TXISAMOpenDatabase(x,x,x,x,x)

- ea: `0x10011d90`
- end: `0x10012e69`
- name: `_TXISAMOpenDatabase@20`
- size: `4313`
- prototype: `int __stdcall(int, wchar_t *Source, int, int, int)`
- caller_count: `0`
- callee_count: `49`
- tags: `service_task, broker_com_uri`

## callees

- `0x10009010`
- `0x1000a1f0`
- `0x1000a470`
- `0x1000a740`
- `0x1000ad60`
- `0x1000b070`
- `0x1000b200`
- `0x1000b600`
- `0x1000b790`
- `0x1000b860`
- `0x1000bab0`
- `0x1000bf60`
- `0x1000c2f0`
- `0x1000d130`
- `0x1000d2b0`
- `0x1000d720`
- `0x1000e350`
- `0x10010370`
- `0x10010870`
- `0x10011d90`
- `0x10013cd0`
- `0x10013d50`
- `0x10013de0`
- `0x10014100`
- `0x100141b0`
- `0x10014560`
- `0x10014650`
- `0x10014690`
- `0x100147c0`
- `0x100198d0`
- `0x1001c060`
- `0x1001c1e0`
- `0x1001c210`
- `0x1001c250`
- `0x1001eaf0`
- `0x1001fbb0`
- `0x10025df0`
- `0x10025e40`
- `0x100260f0`
- `0x10026150`
- `0x10026190`
- `0x10029870`
- `0x1002b500`
- `0x1002b81a`
- `0x1002c490`
- `0x1002c9ad`
- `0x1002c9f6`
- `0x1002cad2`
- `0x1002cce0`

## pseudocode

```c
int __stdcall TXISAMOpenDatabase(int a1, wchar_t *Source, const wchar_t *a3, int a4, int a5)
{
  int v5; // ebp
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int result; // eax
  wchar_t *v11; // ecx
  int v12; // edx
  wchar_t v13; // ax
  wchar_t *v14; // ecx
  int v15; // edx
  wchar_t v16; // ax
  wchar_t v17; // ax
  int v18; // eax
  wchar_t *v19; // eax
  wchar_t *v20; // ecx
  int v21; // edx
  wchar_t v22; // ax
  int v23; // edx
  wchar_t *v24; // ecx
  wchar_t v25; // ax
  int v26; // eax
  wchar_t *v27; // ecx
  int v28; // edx
  wchar_t v29; // ax
  int v30; // eax
  unsigned int v31; // kr08_4
  int v32; // eax
  DWORD v33; // eax
  int v34; // edi
  int v35; // ebx
  _DWORD *v36; // esi
  int v37; // eax
  int **v38; // eax
  int v39; // ebx
  STRSAFE_LPCWSTR v40; // eax
  int v41; // esi
  __int16 v42; // ax
  int v43; // esi
  int v44; // eax
  int v45; // edi
  unsigned int v46; // ecx
  _DWORD *v47; // eax
  int *v48; // ebp
  char *v49; // eax
  char *v50; // edi
  _WORD *v51; // ecx
  int v52; // edx
  __int16 v53; // ax
  _WORD *v54; // ecx
  int v55; // edx
  __int16 v56; // ax
  int v57; // edx
  __int16 v58; // ax
  STRSAFE_LPCWSTR v59; // esi
  _DWORD *v60; // eax
  int v61; // ebp
  int ConnectStringKey; // eax
  int v63; // eax
  bool v64; // zf
  wchar_t *v65; // ecx
  int v66; // edx
  wchar_t v67; // ax
  int v68; // esi
  int v69; // edi
  int v70; // eax
  DWORD v71; // eax
  int v72; // eax
  _DWORD *v73; // edi
  int v74; // [esp-10h] [ebp-1544h]
  int v75; // [esp+Ch] [ebp-1528h]
  int v76; // [esp+10h] [ebp-1524h] BYREF
  int v77; // [esp+14h] [ebp-1520h]
  int v78; // [esp+18h] [ebp-151Ch] BYREF
  int v79; // [esp+1Ch] [ebp-1518h]
  int v80; // [esp+20h] [ebp-1514h]
  STRSAFE_LPCWSTR v81; // [esp+24h] [ebp-1510h]
  int v82; // [esp+28h] [ebp-150Ch]
  int v83; // [esp+2Ch] [ebp-1508h] BYREF
  int v84; // [esp+30h] [ebp-1504h] BYREF
  int v85; // [esp+34h] [ebp-1500h] BYREF
  int v86; // [esp+38h] [ebp-14FCh]
  int v87; // [esp+3Ch] [ebp-14F8h] BYREF
  int v88; // [esp+40h] [ebp-14F4h] BYREF
  int v89; // [esp+44h] [ebp-14F0h] BYREF
  int v90; // [esp+48h] [ebp-14ECh]
  int v91; // [esp+4Ch] [ebp-14E8h]
  int v92; // [esp+50h] [ebp-14E4h] BYREF
  int v93; // [esp+54h] [ebp-14E0h]
  wchar_t Drive[10]; // [esp+5Ch] [ebp-14D8h] BYREF
  wchar_t Destination[262]; // [esp+70h] [ebp-14C4h] BYREF
  wchar_t FullPath[262]; // [esp+27Ch] [ebp-12B8h] BYREF
  wchar_t FileName[262]; // [esp+488h] [ebp-10ACh] BYREF
  wchar_t Src[66]; // [esp+694h] [ebp-EA0h] BYREF
  wchar_t v99[262]; // [esp+718h] [ebp-E1Ch] BYREF
  wchar_t Buffer[262]; // [esp+924h] [ebp-C10h] BYREF
  wchar_t pszDest[256]; // [esp+B30h] [ebp-A04h] BYREF
  wchar_t Dir[256]; // [esp+D30h] [ebp-804h] BYREF
  wchar_t Filename[256]; // [esp+F30h] [ebp-604h] BYREF
  wchar_t v104[256]; // [esp+1130h] [ebp-404h] BYREF
  wchar_t pszSrc[256]; // [esp+1330h] [ebp-204h] BYREF

  v5 = 0;
  v90 = a4;
  v85 = 0;
  v77 = 0;
  v86 = 0;
  v87 = 0;
  v80 = 0;
  v78 = 0;
  v83 = 0;
  v82 = 1;
  v88 = 0;
  v84 = 0;
  v81 = a3;
  if ( !Source )
    return -1003;
  if ( a3 )
  {
    v6 = *a3;
    if ( (_WORD)v6 )
    {
      if ( (v6 == 72 || v6 == 104) && ((v7 = a3[5], v7 == 73) || v7 == 105) )
      {
        v77 = 1;
      }
      else if ( (v6 == 72 || v6 == 104) && ((v8 = a3[5], v8 == 69) || v8 == 101) )
      {
        v77 = 2;
      }
      else
      {
        v77 = 0;
      }
    }
  }
  wcsncpy(Destination, Source, 0x105u);
  Destination[259] = 0;
  if ( ExtractConnectStringKey(a3, L"CharacterSet=", Buffer, 261) == 1 )
  {
    if ( !Buffer[0] )
      return -1003;
    v5 = 1;
    if ( ascii_wcsicmp(Buffer, L"Detect") )
    {
      v80 = 0;
      if ( !DecodeCharacterSet(Buffer, (int)&v78, 1) )
        return -1003;
    }
    else
    {
      v80 = 1;
    }
  }
  v9 = v78;
  if ( !v78 )
    v9 = dword_10046A24;
  v78 = v9;
  if ( ExtractConnectStringKey(a3, L"Locale=", Buffer, 261) == 1 )
  {
    if ( !Buffer[0] )
      return -1003;
    if ( ascii_wcsicmp(Buffer, L"All") && swscanf(Buffer, L"%i", &v83) >= 0 )
    {
      v82 = 0;
    }
    else
    {
      v82 = 1;
      v83 = 0;
    }
  }
  if ( !v77 || v77 == 2 )
  {
    v26 = NetProtocolType(Destination);
    if ( v26 )
    {
      if ( v77 == 2 && v26 == 1 )
      {
LABEL_74:
        v19 = Destination;
        goto LABEL_75;
      }
      if ( !DOSLocatesDirectory(Destination, 261, (int)&v84) )
      {
LABEL_73:
        result = v84;
        if ( v84 )
          return result;
        goto LABEL_74;
      }
      wcsncpy(FullPath, Destination, wcslen(Destination) + 1);
    }
    else
    {
      if ( !DOSLocatesDirectory(Destination, 261, (int)&v84) )
        goto LABEL_73;
      Jetwfullpath(FullPath, Destination, 0x105u);
      v27 = FileName;
      v28 = 261;
      while ( v28 != -2147483385 )
      {
        v29 = *(wchar_t *)((char *)v27 + (char *)FullPath - (char *)FileName);
        if ( !v29 )
          break;
        *v27++ = v29;
        if ( !--v28 )
        {
          --v27;
          break;
        }
      }
      *v27 = 0;
      v30 = FullPath[wcslen(FileName) + 261];
      if ( v30 != 92 && v30 != 58 )
        StringCchCatW(FileName, 0x105u, L"\\");
    }
    v31 = wcslen(FullPath);
    v32 = Destination[v31 + 261];
    if ( v32 != 92 && v32 != 58 && !NetProtocolType(FullPath)
      || NetProtocolType(FullPath) && Destination[v31 + 261] != 47 )
    {
      StringCchCatW(FullPath, 0x105u, L"\\");
    }
    v79 = a5;
    goto LABEL_93;
  }
  v79 = a5 | 1;
  if ( !NetProtocolType(Destination) )
  {
    SplitPath(Source, Drive, 8u, Dir, 0xFFu, Filename, 0xFFu, pszSrc, 0xFFu);
    v11 = pszDest;
    v12 = 256;
    while ( v12 != -2147483390 )
    {
      v13 = *(wchar_t *)((char *)v11 + (char *)Filename - (char *)pszDest);
      if ( !v13 )
        break;
      *v11++ = v13;
      if ( !--v12 )
      {
        --v11;
        break;
      }
    }
    *v11 = 0;
    StringCchCatW(pszDest, 0x100u, pszSrc);
    MakeIntoValidFilename(pszDest, (int)v104, 256, 255, 255, 1, 0x4B0u);
    v14 = FullPath;
    v15 = 261;
    if ( Drive[0] )
    {
      while ( v15 != -2147483385 )
      {
        v16 = *(wchar_t *)((char *)v14 + (char *)Drive - (char *)FullPath);
        if ( !v16 )
          break;
        *v14++ = v16;
        if ( !--v15 )
        {
          --v14;
          break;
        }
      }
      *v14 = 0;
      StringCchCatW(FullPath, 0x105u, Dir);
    }
    else
    {
      while ( v15 != -2147483385 )
      {
        v17 = *(wchar_t *)((char *)v14 + (char *)Dir - (char *)FullPath);
        if ( !v17 )
          break;
        *v14++ = v17;
        if ( !--v15 )
        {
          --v14;
          break;
        }
      }
      *v14 = 0;
    }
    StringCchCatW(FullPath, 0x105u, v104);
    v18 = DOSFileExists(FullPath);
    if ( !v18 )
    {
      SplitPath(FullPath, Drive, 8u, Destination, 0xFFu, 0, 0, 0, 0);
      v20 = FileName;
      v21 = 261;
      while ( v21 != -2147483385 )
      {
        v22 = *(wchar_t *)((char *)v20 + (char *)FullPath - (char *)FileName);
        if ( !v22 )
          break;
        *v20++ = v22;
        if ( !--v21 )
        {
          --v20;
          break;
        }
      }
      *v20 = 0;
      v23 = 261;
      v24 = v99;
      while ( v23 != -2147483385 )
      {
        v25 = *(wchar_t *)((char *)v24 + (char *)Drive - (char *)v99);
        if ( !v25 )
          break;
        *v24++ = v25;
        if ( !--v23 )
        {
          --v24;
          break;
        }
      }
      *v24 = 0;
      StringCchCatW(v99, 0x105u, Destination);
      goto LABEL_93;
    }
    if ( v18 != -3 )
    {
      if ( v18 == -5 )
      {
        ErrorSetExtendedInfoSz1(-8160, FullPath, 0);
        return -1032;
      }
      else if ( v18 == -21 )
      {
        return -1021;
      }
      else
      {
        ErrorSetExtendedInfoSz1(-8300, FullPath, 0);
        return -1305;
      }
    }
    v19 = FullPath;
LABEL_75:
    ErrorSetExtendedInfoSz1(-8161, v19, 0);
    return -1023;
  }
  if ( !IsAcceptableFileName(Destination) )
    return -1809;
  wcsncpy(FullPath, Destination, 0x105u);
LABEL_93:
  v33 = CurrentTaskHandle();
  v34 = ISAMDBFindTask(v33);
  v75 = v34;
  if ( !v34 )
    return -1029;
  v91 = ISAMDBFindSession(a1);
  if ( !v91 )
    return -1104;
  v35 = v79;
  if ( (v79 & 8) != 0 )
  {
    if ( ISAMDBFindDatabase(v34, FullPath) )
      return -1202;
    v35 |= 2u;
    v79 = v35;
  }
  v36 = (_DWORD *)ISAMDBTaskList();
  if ( !v36 )
  {
LABEL_109:
    v39 = ISAMDBFindDatabase(v34, FullPath);
    if ( !v39 )
    {
      v39 = ISAMDBAddDatabase(v34, FullPath);
      if ( !v39 )
        return -1011;
      v40 = v81;
      v41 = 0;
      *(_DWORD *)(v39 + 32) = 0;
      if ( v40 && ExtractConnectStringKey(v40, L"IMEX=", Destination, 261) == 1 )
      {
        if ( !Destination[0] )
        {
LABEL_188:
          ISAMDBDeleteDatabase(v34, v39);
          return -1003;
        }
        v41 = 1;
      }
      *(_DWORD *)(v39 + 40) = -1;
      *(_DWORD *)(v39 + 44) = -1;
      if ( v41 == 1 && GetImexInfo(v34, &v92) == 1 )
      {
        if ( ExtractConnectStringKey(v81, L"DSN=", Destination, 261) && Destination[0] )
        {
          v42 = 1;
        }
        else
        {
          *(_DWORD *)(v39 + 32) = 1;
          v42 = 0;
        }
        *(_WORD *)(v39 + 36) = v42;
        *(_DWORD *)(v39 + 40) = v92;
        *(_DWORD *)(v39 + 44) = v93;
      }
      else
      {
        *(_WORD *)(v39 + 36) = 0;
      }
      if ( !v77 || v77 == 2 )
      {
        if ( NetProtocolType(FullPath) )
          NetCreateLocalDirectory(FileName, 0x105u);
        v43 = TextOpenDirectory(FileName, &v85);
        if ( v43 )
        {
          ISAMDBDeleteDatabase(v34, v39);
          return v43;
        }
        v54 = (_WORD *)(v39 + 56);
        v57 = 261;
        while ( v57 != -2147483385 )
        {
          v58 = *(wchar_t *)((char *)&FileName[-28] + (_DWORD)v54 - v39);
          if ( !v58 )
            break;
          *v54++ = v58;
          if ( !--v57 )
          {
            --v54;
            break;
          }
        }
      }
      else
      {
        if ( NetProtocolType(FullPath) )
        {
          NetCreateLocalDirectory(v99, 0x105u);
          v43 = NetDownloadToLocal(FullPath, 0, v99, FileName, 0x105u);
          if ( v43 )
          {
            ISAMDBDeleteDatabase(v34, v39);
            NetDestroyLocalDirectory(v99);
            return v43;
          }
          ISAMDBAddNetFile(v39, FullPath, FileName, 0);
          v86 = 1;
        }
        v44 = dword_10046A24;
        v76 = dword_10046A24;
        if ( !v80 )
        {
          if ( v5 )
            v44 = v78;
          v76 = v44;
        }
        v45 = TextDetectCodePageInfo(FileName, 1, (int)&v76, 0, 0, (int)&v87, (int)&v89, (int)&v76, 3);
        if ( !v45 )
        {
          v46 = 0;
          if ( v89 )
          {
            v47 = (_DWORD *)(v87 + 516);
            while ( *v47 != 1 )
            {
              ++v46;
              v47 += 258;
              if ( v46 >= v89 )
                goto LABEL_141;
            }
            v78 = *(_DWORD *)(1032 * v46 + v87 + 512);
            v76 = v78;
          }
        }
LABEL_141:
        if ( v87 )
          MemFree(v87);
        if ( v45 )
        {
          ISAMDBDeleteDatabase(v75, v39);
          NetDestroyLocalDirectory(v99);
          return v45;
        }
        v48 = (int *)(v39 + 12);
        v43 = HTMLOpenFile(FileName, v86, FullPath, v76, v39 + 12);
        if ( v43 )
        {
LABEL_168:
          ISAMDBDeleteDatabase(v75, v39);
          NetDestroyLocalDirectory(v99);
          return v43;
        }
        if ( v77 == 1 )
          DOSFindLocalDirectory(FileName, 0x104u);
        v43 = TextOpenDirectory(FileName, &v85);
        if ( v43 )
        {
          HTMLCloseFile(*v48);
          ISAMDBDeleteDatabase(v75, v39);
          NetDestroyLocalDirectory(FileName);
          return v43;
        }
        result = HTMLFirstTable(*v48, Src, 0x41u);
        if ( result == -1002 )
          return result;
        *(_DWORD *)(v39 + 16) = 0;
        if ( !result )
        {
          while ( 1 )
          {
            DOSUniquePathname(Destination, 0x105u, FileName, (int)L"HTML", L".TMP");
            v43 = HTMLExtractTable(*v48, Src, Destination, (int)&v88);
            if ( v43 )
              break;
            v49 = (char *)MemAllocate(0xA4u);
            v50 = v49;
            if ( !v49 )
            {
              HTMLCloseFile(*v48);
              ISAMDBDeleteDatabase(v75, v39);
              NetDestroyLocalDirectory(v99);
              return -1011;
            }
            memset(v49, 0, 0xA4u);
            v51 = v50 + 4;
            v52 = 65;
            while ( v52 != -2147483581 )
            {
              v53 = *(_WORD *)((char *)v51 + (char *)Src - (v50 + 4));
              if ( !v53 )
                break;
              *v51++ = v53;
              if ( !--v52 )
              {
                --v51;
                break;
              }
            }
            *v51 = 0;
            *((_DWORD *)v50 + 40) = v88;
            SplitPath(Destination, 0, 0, 0, 0, (wchar_t *)v50 + 67, 0xDu, 0, 0);
            StringCchCatW((STRSAFE_LPWSTR)v50 + 67, 0xDu, L".tmp");
            *(_DWORD *)v50 = *(_DWORD *)(v39 + 16);
            v74 = *v48;
            *(_DWORD *)(v39 + 16) = v50;
            if ( HTMLNextTable(v74, Src, 0x40u) )
              goto LABEL_160;
          }
          HTMLCloseFile(*v48);
          goto LABEL_168;
        }
LABEL_160:
        HTMLCloseFile(*v48);
        v54 = (_WORD *)(v39 + 56);
        v55 = 261;
        while ( v55 != -2147483385 )
        {
          v56 = *(wchar_t *)((char *)&FileName[-28] + (_DWORD)v54 - v39);
          if ( !v56 )
            break;
          *v54++ = v56;
          if ( !--v55 )
          {
            v34 = v75;
            --v54;
            goto LABEL_179;
          }
        }
        v34 = v75;
      }
LABEL_179:
      *v54 = 0;
      *(_DWORD *)(v39 + 8) = v77;
      *(_DWORD *)(v39 + 28) = v85;
      *(_DWORD *)(v39 + 24) = v79;
    }
    v59 = v81;
    v60 = (_DWORD *)ISAMDBAddDatabaseUser(v91, v39, v81);
    v61 = (int)v60;
    if ( !v60 )
    {
      if ( !*(_DWORD *)(v39 + 48) )
      {
        TextCloseDirectory(*(_DWORD *)(v39 + 28));
        ISAMDBDeleteDatabase(v34, v39);
        return -1011;
      }
      return -1011;
    }
    v60[217] = v80;
    v60[216] = v78;
    v60[218] = v83;
    v60[219] = v82;
    if ( !v59 )
    {
LABEL_234:
      *(_DWORD *)(v61 + 892) = *(_DWORD *)(v39 + 24);
      v71 = CurrentTaskHandle();
      v72 = ISAMDBFindTask(v71);
      v73 = (_DWORD *)v90;
      v43 = (*(int (__stdcall **)(int, _DWORD, int *))(*(_DWORD *)(v72 + 28) + 40))(
              v90,
              *(_DWORD *)(v61 + 884),
              &DatabaseEntryPoints);
      if ( v43 )
      {
        ISAMDBDeleteDatabaseUser(v39, v61);
        if ( !*(_DWORD *)(v39 + 48) )
        {
          TextCloseDirectory(*(_DWORD *)(v39 + 28));
          ISAMDBDeleteDatabase(v75, v39);
        }
      }
      else
      {
        *(_DWORD *)(v61 + 888) = *v73;
      }
      return v43;
    }
    if ( ExtractConnectStringKey(v59, L"HDR=", Destination, 261) != 1 || Destination[0] )
    {
      ExtractConnectStringKey(v59, L"DSN=", v61 + 896, 65);
      if ( ascii_wcsicmp(Destination, L"Yes") )
        *(_DWORD *)(v61 + 852) = ascii_wcsicmp(Destination, L"No") ? dword_10046A1C : 0;
      else
        *(_DWORD *)(v61 + 852) = 1;
      if ( ExtractConnectStringKey(v59, L"FMT=", Destination, 261) != 1 || Destination[0] )
      {
        if ( ascii_wcsicmp(Destination, L"Fixed") )
        {
          if ( ascii_wcsicmp(Destination, L"WordMerge") )
            *(_BYTE *)(v61 + 856) = 0;
          else
            *(_BYTE *)(v61 + 856) = 2;
        }
        else
        {
          *(_BYTE *)(v61 + 856) = 1;
        }
        ConnectStringKey = ExtractConnectStringKey(v59, L"FixedFormat=", Destination, 261);
        *(_DWORD *)(v61 + 860) = 0;
        if ( ConnectStringKey != 1 )
          goto LABEL_205;
        if ( Destination[0] )
        {
          *(_DWORD *)(v61 + 860) = 1;
          *(_BYTE *)(v61 + 857) = ascii_wcsicmp(Destination, L"RaggedEdge") != 0;
LABEL_205:
          v63 = *(_DWORD *)(v61 + 852);
          qmemcpy((void *)(v61 + 12), &DefaultFileSpec, 0x348u);
          *(_DWORD *)(v61 + 40) = v63;
          v64 = v77 == 2;
          *(_DWORD *)(v61 + 32) = *(_BYTE *)(v61 + 857) == 0;
          *(_DWORD *)(v61 + 48) = *(_DWORD *)(v61 + 864);
          if ( v64 )
          {
            *(_BYTE *)(v61 + 856) = 3;
            *(_DWORD *)(v61 + 64) = 3;
          }
          else
          {
            *(_DWORD *)(v61 + 64) = *(unsigned __int8 *)(v61 + 856);
          }
          if ( *(_BYTE *)(v61 + 856) == 2 )
          {
            TextSpecForWordMerge(v61 + 12);
          }
          else if ( *(_DWORD *)(v39 + 8) == 1 )
          {
            TextSpecForHTML(v61 + 12);
            *(_DWORD *)(v61 + 48) = *(_DWORD *)(v61 + 864);
          }
          if ( *(_WORD *)(v61 + 896) )
          {
            v65 = Destination;
            v66 = 261;
            while ( v66 != -2147483385 )
            {
              v67 = *(wchar_t *)((char *)v65 + v39 + 56 - (_DWORD)Destination);
              if ( !v67 )
                break;
              *v65++ = v67;
              if ( !--v66 )
              {
                --v65;
                break;
              }
            }
            *v65 = 0;
            StringCchCatW(Destination, 0x105u, L"schema.ini");
            if ( *(_WORD *)(v39 + 36) == 1 && (*(_DWORD *)(v39 + 40) == -1 || *(_DWORD *)(v39 + 44) == -1) )
            {
              v68 = v75;
              if ( GetImexInfo(v75, &v92) == 1 )
              {
                *(_DWORD *)(v39 + 40) = v92;
                *(_DWORD *)(v39 + 44) = v93;
              }
            }
            else
            {
              v68 = v75;
            }
            if ( !TextSpecAvailable(v61, (JET_TABLEID)Destination, (void *)(v61 + 896), *(__int16 *)(v39 + 36)) )
            {
              ErrorSetExtendedInfoSz1(-8244, (STRSAFE_LPCWSTR)(v61 + 896), 0);
              ISAMDBDeleteDatabaseUser(v39, v61);
              if ( !*(_DWORD *)(v39 + 48) )
              {
                TextCloseDirectory(*(_DWORD *)(v39 + 28));
                ISAMDBDeleteDatabase(v68, v39);
              }
              return -5411;
            }
            v76 = *(_DWORD *)(v61 + 864);
            v69 = TextSpecRead(v61, (JET_TABLEID)Destination, v61 + 896, v61 + 12, *(__int16 *)(v39 + 36));
            if ( v69 )
            {
              ISAMDBDeleteDatabaseUser(v39, v61);
              if ( !*(_DWORD *)(v39 + 48) )
              {
                TextCloseDirectory(*(_DWORD *)(v39 + 28));
                ISAMDBDeleteDatabase(v75, v39);
              }
              return v69;
            }
            *(_DWORD *)(v61 + 12) = 1;
            if ( *(_DWORD *)(v39 + 8) == 1 )
            {
              TextSpecForHTML(v61 + 12);
              *(_DWORD *)(v61 + 864) = v76;
              *(_DWORD *)(v61 + 48) = v76;
            }
          }
          if ( ExtractConnectStringKey(v81, L"ORIENT=", Destination, 261) == 1 && Destination[0] )
          {
            v70 = _wtol(Destination);
            *(_DWORD *)(v61 + 880) = v70;
            *(_DWORD *)(v61 + 836) = v70;
          }
          goto LABEL_234;
        }
        goto LABEL_188;
      }
    }
    ISAMDBDeleteDatabaseUser(v39, v61);
    if ( !*(_DWORD *)(v39 + 48) )
    {
      TextCloseDirectory(*(_DWORD *)(v39 + 28));
      goto LABEL_188;
    }
    return -1003;
  }
  while ( 1 )
  {
    if ( v36 != (_DWORD *)v34 )
    {
      v37 = ISAMDBFindDatabase(v36, FullPath);
      if ( v37 )
      {
        if ( (v35 & 2) != 0 )
          return -1202;
        v38 = *(int ***)(v37 + 48);
        if ( v38 )
          break;
      }
    }
LABEL_108:
    v36 = (_DWORD *)*v36;
    if ( !v36 )
      goto LABEL_109;
  }
  while ( ((_BYTE)v38[223] & 2) == 0 )
  {
    v38 = (int **)*v38;
    if ( !v38 )
      goto LABEL_108;
  }
  return -1207;
}

```

## disassembly

```asm
0x10011d90  mov     eax, 1528h
0x10011d95  call    __chkstk
0x10011d9a  mov     eax, ___security_cookie
0x10011d9f  xor     eax, esp
0x10011da1  mov     [esp+1528h+var_4], eax
0x10011da8  mov     eax, [esp+1528h+arg_C]
0x10011daf  push    ebx
0x10011db0  mov     ebx, [esp+152Ch+arg_0]
0x10011db7  push    ebp
0x10011db8  xor     ebp, ebp
0x10011dba  mov     [esp+1530h+var_14EC], eax
0x10011dbe  push    esi
0x10011dbf  mov     esi, [esp+1534h+Source]
0x10011dc6  mov     [esp+1534h+var_1500], 0
0x10011dce  mov     [esp+1534h+var_1520], 0
0x10011dd6  mov     [esp+1534h+var_14FC], 0
0x10011dde  mov     [esp+1534h+var_14F8], ebp
0x10011de2  mov     [esp+1534h+var_1514], ebp
0x10011de6  mov     [esp+1534h+var_151C], ebp
0x10011dea  mov     [esp+1534h+var_1508], ebp
0x10011dee  mov     [esp+1534h+var_150C], 1
0x10011df6  mov     [esp+1534h+var_14F4], ebp
0x10011dfa  mov     [esp+1534h+var_1504], ebp
0x10011dfe  push    edi
0x10011dff  mov     edi, [esp+1538h+arg_8]
0x10011e06  mov     [esp+1538h+var_1510], edi
0x10011e0a  test    esi, esi
0x10011e0c  jz      loc_10012AB4
0x10011e12  test    edi, edi
0x10011e14  jz      short loc_10011E66
0x10011e16  movzx   eax, word ptr [edi]
0x10011e19  test    ax, ax
0x10011e1c  jz      short loc_10011E66
0x10011e1e  cmp     eax, 48h ; 'H'
0x10011e21  jz      short loc_10011E28
0x10011e23  cmp     eax, 68h ; 'h'
0x10011e26  jnz     short loc_10011E36
0x10011e28  movzx   ecx, word ptr [edi+0Ah]
0x10011e2c  cmp     ecx, 49h ; 'I'
0x10011e2f  jz      short loc_10011E5E
0x10011e31  cmp     ecx, 69h ; 'i'
0x10011e34  jz      short loc_10011E5E
0x10011e36  cmp     eax, 48h ; 'H'
0x10011e39  jz      short loc_10011E40
0x10011e3b  cmp     eax, 68h ; 'h'
0x10011e3e  jnz     short loc_10011E4E
0x10011e40  movzx   eax, word ptr [edi+0Ah]
0x10011e44  cmp     eax, 45h ; 'E'
0x10011e47  jz      short loc_10011E54
0x10011e49  cmp     eax, 65h ; 'e'
0x10011e4c  jz      short loc_10011E54
0x10011e4e  mov     [esp+1538h+var_1520], ebp
0x10011e52  jmp     short loc_10011E66
0x10011e54  mov     [esp+1538h+var_1520], 2
0x10011e5c  jmp     short loc_10011E66
0x10011e5e  mov     [esp+1538h+var_1520], 1
0x10011e66  push    105h; Count
0x10011e6b  lea     eax, [esp+153Ch+Destination]
0x10011e6f  push    esi; Source
0x10011e70  push    eax; Destination
0x10011e71  call    _wcsncpy
0x10011e76  add     esp, 0Ch
0x10011e79  xor     eax, eax
0x10011e7b  mov     [esp+1538h+var_12BE], ax
0x10011e83  lea     eax, [esp+1538h+Buffer]
0x10011e8a  push    105h
0x10011e8f  push    eax
0x10011e90  push    offset aCharacterset_0; "CharacterSet="
0x10011e95  push    edi
0x10011e96  call    ExtractConnectStringKey
0x10011e9b  cmp     eax, 1
0x10011e9e  jnz     short loc_10011EF3
0x10011ea0  cmp     [esp+1538h+Buffer], bp
0x10011ea8  jz      loc_10012AB4
0x10011eae  mov     ebp, eax
0x10011eb0  lea     eax, [esp+1538h+Buffer]
0x10011eb7  push    offset aDetect; "Detect"
0x10011ebc  push    eax
0x10011ebd  call    _ascii_wcsicmp
0x10011ec2  add     esp, 8
0x10011ec5  test    eax, eax
0x10011ec7  jnz     short loc_10011ECF
0x10011ec9  mov     [esp+1538h+var_1514], ebp
0x10011ecd  jmp     short loc_10011EF3
0x10011ecf  push    1; int
0x10011ed1  lea     eax, [esp+153Ch+var_151C]
0x10011ed5  mov     [esp+153Ch+var_1514], 0
0x10011edd  push    eax; int
0x10011ede  lea     eax, [esp+1540h+Buffer]
0x10011ee5  push    eax; String
0x10011ee6  call    _DecodeCharacterSet@12; DecodeCharacterSet(x,x,x)
0x10011eeb  test    eax, eax
0x10011eed  jz      loc_10012AB4
0x10011ef3  mov     eax, [esp+1538h+var_151C]
0x10011ef7  test    eax, eax
0x10011ef9  push    105h
0x10011efe  cmovz   eax, dword_10046A24
0x10011f05  mov     [esp+153Ch+var_151C], eax
0x10011f09  lea     eax, [esp+153Ch+Buffer]
0x10011f10  push    eax
0x10011f11  push    offset aLocale; "Locale="
0x10011f16  push    edi
0x10011f17  call    ExtractConnectStringKey
0x10011f1c  cmp     eax, 1
0x10011f1f  jnz     short loc_10011F81
0x10011f21  cmp     [esp+1538h+Buffer], 0
0x10011f2a  jz      loc_10012AB4
0x10011f30  lea     eax, [esp+1538h+Buffer]
0x10011f37  push    offset aAll; "All"
0x10011f3c  push    eax
0x10011f3d  call    _ascii_wcsicmp
0x10011f42  add     esp, 8
0x10011f45  test    eax, eax
0x10011f47  jz      short loc_10011F71
0x10011f49  lea     eax, [esp+1538h+var_1508]
0x10011f4d  push    eax
0x10011f4e  lea     eax, [esp+153Ch+Buffer]
0x10011f55  push    offset aI; "%i"
0x10011f5a  push    eax; Buffer
0x10011f5b  call    _swscanf
0x10011f60  add     esp, 0Ch
0x10011f63  test    eax, eax
0x10011f65  js      short loc_10011F71
0x10011f67  mov     [esp+1538h+var_150C], 0
0x10011f6f  jmp     short loc_10011F81
0x10011f71  mov     [esp+1538h+var_150C], 1
0x10011f79  mov     [esp+1538h+var_1508], 0
0x10011f81  mov     edi, [esp+1538h+var_1520]
0x10011f85  test    edi, edi
0x10011f87  jz      loc_1001228A
0x10011f8d  cmp     edi, 2
0x10011f90  jz      loc_1001228A
0x10011f96  mov     eax, [esp+1538h+arg_10]
0x10011f9d  or      eax, 1
0x10011fa0  mov     [esp+1538h+var_1518], eax
0x10011fa4  lea     eax, [esp+1538h+Destination]
0x10011fa8  push    eax
0x10011fa9  call    _NetProtocolType@4; NetProtocolType(x)
0x10011fae  test    eax, eax
0x10011fb0  jz      short loc_10011FE9
0x10011fb2  lea     eax, [esp+1538h+Destination]
0x10011fb6  push    eax; pszSrc
0x10011fb7  call    _IsAcceptableFileName@4; IsAcceptableFileName(x)
0x10011fbc  test    eax, eax
0x10011fbe  jnz     short loc_10011FCA
0x10011fc0  mov     eax, 0FFFFF8EFh
0x10011fc5  jmp     loc_10012E4E
0x10011fca  push    105h; Count
0x10011fcf  lea     eax, [esp+153Ch+Destination]
0x10011fd3  push    eax; Source
0x10011fd4  lea     eax, [esp+1540h+FullPath]
0x10011fdb  push    eax; Destination
0x10011fdc  call    _wcsncpy
0x10011fe1  add     esp, 0Ch
0x10011fe4  jmp     loc_10012452
0x10011fe9  push    0FFh; ExtCount
0x10011fee  lea     eax, [esp+153Ch+pszSrc]
0x10011ff5  push    eax; Ext
0x10011ff6  push    0FFh; FilenameCount
0x10011ffb  lea     eax, [esp+1544h+Filename]
0x10012002  push    eax; Filename
0x10012003  push    0FFh; DirCount
0x10012008  lea     eax, [esp+154Ch+Dir]
0x1001200f  push    eax; Dir
0x10012010  push    8; DriveCount
0x10012012  lea     eax, [esp+1554h+Drive]
0x10012016  push    eax; Drive
0x10012017  push    esi; FullPath
0x10012018  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1001201d  lea     ecx, [esp+1538h+pszDest]
0x10012024  mov     edx, 100h
0x10012029  lea     esi, [esp+1538h+Filename]
0x10012030  mov     eax, ecx
0x10012032  sub     esi, eax
0x10012034  lea     eax, [edx+7FFFFEFEh]
0x1001203a  test    eax, eax
0x1001203c  jz      short loc_10012052
0x1001203e  movzx   eax, word ptr [esi+ecx]
0x10012042  test    ax, ax
0x10012045  jz      short loc_10012052
0x10012047  mov     [ecx], ax
0x1001204a  add     ecx, 2
0x1001204d  dec     edx
0x1001204e  jnz     short loc_10012034
0x10012050  jmp     short loc_10012056
0x10012052  test    edx, edx
0x10012054  jnz     short loc_10012059
0x10012056  sub     ecx, 2
0x10012059  xor     eax, eax
0x1001205b  mov     [ecx], ax
0x1001205e  lea     eax, [esp+1538h+pszSrc]
0x10012065  push    eax; pszSrc
0x10012066  push    100h; cchDest
0x1001206b  lea     eax, [esp+1540h+pszDest]
0x10012072  push    eax; pszDest
0x10012073  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10012078  push    4B0h; CodePage
0x1001207d  push    1; int
0x1001207f  push    0FFh; int
0x10012084  push    0FFh; int
0x10012089  push    100h; int
0x1001208e  lea     eax, [esp+154Ch+var_404]
0x10012095  push    eax; int
0x10012096  lea     eax, [esp+1550h+pszDest]
0x1001209d  push    eax; lpWideCharStr
0x1001209e  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x100120a3  cmp     [esp+1538h+Drive], 0
0x100120a9  lea     ecx, [esp+1538h+FullPath]
0x100120b0  mov     edx, 105h
0x100120b5  mov     eax, ecx
0x100120b7  jz      short loc_10012106
0x100120b9  lea     esi, [esp+1538h+Drive]
0x100120bd  sub     esi, eax
0x100120bf  nop
0x100120c0  lea     eax, [edx+7FFFFEF9h]
0x100120c6  test    eax, eax
0x100120c8  jz      short loc_100120DE
0x100120ca  movzx   eax, word ptr [ecx+esi]
0x100120ce  test    ax, ax
0x100120d1  jz      short loc_100120DE
0x100120d3  mov     [ecx], ax
0x100120d6  add     ecx, 2
0x100120d9  dec     edx
0x100120da  jnz     short loc_100120C0
0x100120dc  jmp     short loc_100120E2
0x100120de  test    edx, edx
0x100120e0  jnz     short loc_100120E5
0x100120e2  sub     ecx, 2
0x100120e5  xor     eax, eax
0x100120e7  mov     [ecx], ax
0x100120ea  lea     eax, [esp+1538h+Dir]
0x100120f1  push    eax; pszSrc
0x100120f2  push    105h; cchDest
0x100120f7  lea     eax, [esp+1540h+FullPath]
0x100120fe  push    eax; pszDest
0x100120ff  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10012104  jmp     short loc_1001213A
0x10012106  lea     esi, [esp+1538h+Dir]
0x1001210d  sub     esi, eax
0x1001210f  nop
0x10012110  lea     eax, [edx+7FFFFEF9h]
0x10012116  test    eax, eax
0x10012118  jz      short loc_1001212E
0x1001211a  movzx   eax, word ptr [ecx+esi]
0x1001211e  test    ax, ax
0x10012121  jz      short loc_1001212E
0x10012123  mov     [ecx], ax
0x10012126  add     ecx, 2
0x10012129  dec     edx
0x1001212a  jnz     short loc_10012110
0x1001212c  jmp     short loc_10012132
0x1001212e  test    edx, edx
0x10012130  jnz     short loc_10012135
0x10012132  sub     ecx, 2
0x10012135  xor     eax, eax
0x10012137  mov     [ecx], ax
0x1001213a  lea     eax, [esp+1538h+var_404]
0x10012141  push    eax; pszSrc
0x10012142  push    105h; cchDest
0x10012147  lea     eax, [esp+1540h+FullPath]
0x1001214e  push    eax; pszDest
0x1001214f  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10012154  lea     eax, [esp+1538h+FullPath]
0x1001215b  push    eax; lpFileName
0x1001215c  call    _DOSFileExists@4; DOSFileExists(x)
0x10012161  test    eax, eax
0x10012163  jz      short loc_100121C6
0x10012165  cmp     eax, 0FFFFFFFDh
0x10012168  jnz     short loc_10012176
0x1001216a  lea     eax, [esp+1538h+FullPath]
0x10012171  jmp     loc_100122CE
0x10012176  cmp     eax, 0FFFFFFFBh
0x10012179  jnz     short loc_10012199
0x1001217b  push    0; int
0x1001217d  lea     eax, [esp+153Ch+FullPath]
0x10012184  push    eax; pszSrc
0x10012185  push    0FFFFE020h; int
0x1001218a  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1001218f  mov     eax, 0FFFFFBF8h
0x10012194  jmp     loc_10012E4E
0x10012199  cmp     eax, 0FFFFFFEBh
0x1001219c  jnz     short loc_100121A8
0x1001219e  mov     eax, 0FFFFFC03h
0x100121a3  jmp     loc_10012E4E
0x100121a8  push    0; int
0x100121aa  lea     eax, [esp+153Ch+FullPath]
0x100121b1  push    eax; pszSrc
0x100121b2  push    0FFFFDF94h; int
0x100121b7  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x100121bc  mov     eax, 0FFFFFAE7h
0x100121c1  jmp     loc_10012E4E
0x100121c6  push    0; ExtCount
0x100121c8  push    0; Ext
0x100121ca  push    0; FilenameCount
0x100121cc  push    0; Filename
0x100121ce  push    0FFh; DirCount
0x100121d3  lea     eax, [esp+154Ch+Destination]
0x100121da  push    eax; Dir
0x100121db  push    8; DriveCount
0x100121dd  lea     eax, [esp+1554h+Drive]
  ... truncated ...
```
