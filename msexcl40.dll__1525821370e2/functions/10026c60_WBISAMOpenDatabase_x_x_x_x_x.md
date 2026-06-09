# WBISAMOpenDatabase(x,x,x,x,x)

- ea: `0x10026c60`
- end: `0x100278cd`
- name: `_WBISAMOpenDatabase@20`
- size: `3181`
- prototype: `int __stdcall(int, _WORD *, const wchar_t *, _DWORD *, int)`
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x10029068`
- `0x1002df60`

## callees

- `0x10006390`
- `0x10006400`
- `0x100073e0`
- `0x1000da30`
- `0x10018b80`
- `0x1001abf0`
- `0x1001b1e0`
- `0x1001b2f0`
- `0x1001b8e0`
- `0x1001b900`
- `0x10022838`
- `0x10022871`
- `0x10022890`
- `0x100234fb`
- `0x100246ef`
- `0x100255d7`
- `0x10025710`
- `0x1002580a`
- `0x10026676`
- `0x100268a0`
- `0x10026b2c`
- `0x10026bc4`
- `0x10026c60`
- `0x1002a7de`
- `0x1002a869`
- `0x1002a89a`
- `0x1002a907`
- `0x1002a9c3`
- `0x1002a9f4`
- `0x1002aa6e`
- `0x1002af75`
- `0x10033a09`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100271ba`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10027459`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002773a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100271ba`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10027459`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002773a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10026d30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10027025`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10026d30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10027025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10026cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002785f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10026cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002785f`

## pseudocode

```c
int __stdcall WBISAMOpenDatabase(int a1, _WORD *a2, const wchar_t *a3, _DWORD *a4, int a5)
{
  DWORD CurrentProcessId; // eax
  int result; // eax
  unsigned int v7; // ebx
  wchar_t *v8; // eax
  wchar_t *v9; // eax
  int v10; // eax
  int v11; // ebx
  BOOL v12; // esi
  int v13; // eax
  int v14; // ecx
  int v15; // esi
  int v16; // ecx
  WCHAR *v17; // ecx
  WCHAR v18; // dx
  int v19; // eax
  int v20; // eax
  int v21; // ebx
  _DWORD *v22; // esi
  _DWORD *v23; // eax
  int v24; // eax
  int **i; // eax
  int v26; // eax
  int v27; // eax
  int v28; // esi
  int v29; // edi
  int v30; // eax
  bool v31; // zf
  int v32; // eax
  _DWORD *v33; // ebx
  int v34; // ecx
  int v35; // eax
  int v36; // esi
  int v37; // ecx
  int v38; // eax
  int v39; // esi
  BOOL v40; // edx
  int v41; // eax
  unsigned int v42; // esi
  int v43; // eax
  int v44; // eax
  _DWORD *v45; // edx
  _DWORD *v46; // eax
  int *v47; // ecx
  int v48; // eax
  int v49; // ebx
  _DWORD *v50; // ecx
  int v51; // eax
  int j; // edx
  int v53; // eax
  int v54; // ebx
  int v55; // eax
  DWORD v56; // eax
  int v57; // eax
  int v58; // [esp-4h] [ebp-AF0h]
  int *v59; // [esp+18h] [ebp-AD4h]
  int v60; // [esp+20h] [ebp-ACCh]
  char v61; // [esp+20h] [ebp-ACCh]
  int v62; // [esp+24h] [ebp-AC8h]
  int v63; // [esp+28h] [ebp-AC4h]
  BOOL v64; // [esp+30h] [ebp-ABCh]
  int v65; // [esp+34h] [ebp-AB8h]
  int v66; // [esp+38h] [ebp-AB4h] BYREF
  int v67; // [esp+3Ch] [ebp-AB0h]
  int v68; // [esp+40h] [ebp-AACh]
  _DWORD v69[3]; // [esp+44h] [ebp-AA8h] BYREF
  wchar_t Filename[256]; // [esp+50h] [ebp-A9Ch] BYREF
  wchar_t Ext[256]; // [esp+250h] [ebp-89Ch] BYREF
  WCHAR WideCharStr[264]; // [esp+450h] [ebp-69Ch] BYREF
  WCHAR v73[32]; // [esp+660h] [ebp-48Ch] BYREF
  WCHAR PathName[264]; // [esp+6A0h] [ebp-44Ch] BYREF
  wchar_t FullPath[266]; // [esp+8B0h] [ebp-23Ch] BYREF
  _WORD v76[16]; // [esp+AC4h] [ebp-28h] BYREF

  v59 = 0;
  v66 = 0;
  v64 = 0;
  if ( !a2 )
    return -1003;
  CurrentProcessId = GetCurrentProcessId();
  v68 = ISAMDBFindTask(CurrentProcessId);
  if ( !v68 )
    return -1029;
  if ( !ISAMDBFindSession(a1) )
    return -1104;
  v76[0] = 0;
  v63 = dword_1003C2D4;
  v67 = -1;
  v7 = 2;
  v65 = 2;
  if ( !a3 || !*a3 )
    goto LABEL_34;
  v8 = _wcschr(a3, 0x3Bu);
  if ( v8 )
  {
    v9 = v8 - 3;
    v7 = 0;
  }
  else
  {
    v7 = 0;
    v9 = (wchar_t *)&a3[wcslen(a3) - 3];
  }
  v10 = *v9;
  if ( v10 != 51 )
  {
    v11 = 0;
    if ( v10 == 52 )
    {
      v7 = 1;
    }
    else
    {
      LOBYTE(v11) = v10 != 53;
      v7 = v11 + 2;
    }
  }
  v65 = v7;
  ExtractConnectStringKey(PathName, 261);
  v12 = WCSICMP(PathName, L"1") == 0;
  v64 = v12;
  if ( ExtractConnectStringKey(PathName, 261) == 1 && !PathName[0] )
    return -1003;
  if ( WCSICMP(PathName, L"Yes") )
    v63 = WCSICMP(PathName, L"No") != 0 ? v63 : 0;
  else
    v63 = 1;
  if ( ExtractConnectStringKey(PathName, 261) == 1 )
  {
    if ( !PathName[0] )
      return -1003;
  }
  else if ( !PathName[0] )
  {
    goto LABEL_32;
  }
  if ( WCSCMP(PathName, L"0") )
  {
    if ( WCSCMP(PathName, L"1") )
    {
      v13 = WCSCMP(PathName, L"2");
      v14 = v67;
      if ( !v13 )
        v14 = 2;
      v67 = v14;
    }
    else
    {
      v67 = 1;
    }
  }
  else
  {
    v67 = 0;
    v63 = 1;
  }
LABEL_32:
  if ( ExtractConnectStringKey(v76, 16) == 1 )
  {
    v64 = v12;
    if ( !v76[0] )
      return -1003;
  }
LABEL_34:
  v15 = 0;
  v60 = 0;
  WCSNCPY2(PathName, 0x105u, a2, 0x105u);
  PathName[259] = 0;
  if ( !NetProtocolType(PathName) )
  {
    Jetwfullpath(v16);
    FullPath[259] = 0;
    v19 = DOSLocatesDirectory(FullPath, (int)&v66);
    if ( v7 > 1 )
    {
      if ( v19 )
        goto LABEL_78;
    }
    else
    {
      if ( v19 )
      {
        v20 = PathName[wcslen(FullPath) + 263];
        if ( v20 != 92 && v20 != 58 )
          WCSCAT2(FullPath, L"\\", 0x105u);
        v15 = 1;
      }
      v60 = v15;
      if ( v15 )
        goto LABEL_56;
    }
LABEL_69:
    if ( !NetProtocolType(FullPath) && !v64 )
    {
      v26 = DOSFileExists(FullPath);
      if ( v26 )
      {
        if ( v26 == -3 )
          goto LABEL_46;
        if ( v26 == -5 )
          goto LABEL_78;
        __wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
        if ( !Ext[0] )
        {
          WCSCAT2(FullPath, (_WORD *)dword_1003C328 + 5 * v7, 0x105u);
          v27 = DOSFileExists(FullPath);
          if ( v27 )
          {
            if ( v27 == -3 )
              goto LABEL_46;
            if ( v27 == -5 )
            {
LABEL_78:
              ErrorSetExtendedInfoSz1(0);
              return -1032;
            }
          }
        }
      }
    }
LABEL_56:
    v21 = a5;
    if ( (a5 & 8) != 0 )
    {
      if ( ISAMDBFindDatabase(v68, FullPath) )
        return -1202;
      v21 = a5 | 2;
    }
    v22 = (_DWORD *)dword_1003AE68;
    if ( dword_1003AE68 )
    {
      v23 = (_DWORD *)v68;
      do
      {
        if ( v22 != v23 )
        {
          v24 = ISAMDBFindDatabase(v22, FullPath);
          if ( v24 )
          {
            if ( (v21 & 2) != 0 )
              return -1202;
            for ( i = *(int ***)(v24 + 44); i; i = (int **)*i )
            {
              if ( ((_BYTE)i[5] & 2) != 0 )
                return -1207;
            }
          }
          v23 = (_DWORD *)v68;
        }
        v22 = (_DWORD *)*v22;
      }
      while ( v22 );
    }
    v28 = 0;
    v62 = 0;
    v66 = 0;
    if ( v60 == 1 )
    {
      v29 = ISAMDBFindDatabase(v68, FullPath);
      if ( v29 )
      {
LABEL_86:
        if ( !*(_DWORD *)(v29 + 44) )
        {
          v31 = v67 == -1;
          *(_DWORD *)(v29 + 32) = 0;
          *(_DWORD *)(v29 + 36) = -1;
          *(_DWORD *)(v29 + 40) = -1;
          if ( !v31 && GetImexInfo(v68, v69) == 1 )
          {
            *(_DWORD *)(v29 + 32) = 1;
            *(_DWORD *)(v29 + 36) = v69[0];
            *(_DWORD *)(v29 + 40) = v69[1];
          }
        }
        v32 = ISAMDBAddDatabaseUser(a3);
        v33 = (_DWORD *)v32;
        if ( !v32 )
        {
          if ( !*(_DWORD *)(v29 + 44) )
          {
            if ( v28 )
              WorkbookClose(v28, 0);
            ISAMDBDeleteDatabase(v68, v29);
          }
          return -1011;
        }
        WCSCPY2((_WORD *)(v32 + 24), v76, 0x10u);
        v33[5] = *(_DWORD *)(v29 + 64);
        v55 = v67;
        if ( v67 == -1 )
          v55 = 2;
        v36 = 0;
        v33[14] = v55;
        v33[15] = v63;
        if ( !a4 )
          return v36;
        v56 = GetCurrentProcessId();
        v57 = ISAMDBFindTask(v56);
        v36 = (*(int (__thiscall **)(_DWORD, _DWORD *, _DWORD, int *))(*(_DWORD *)(v57 + 28) + 40))(
                *(_DWORD *)(*(_DWORD *)(v57 + 28) + 40),
                a4,
                v33[3],
                DatabaseEntryPoints);
        if ( !v36 )
        {
          v33[4] = *a4;
          return v36;
        }
        ISAMDBDeleteDatabaseUser(v29, v33);
        if ( *(_DWORD *)(v29 + 44) )
          return v36;
        if ( v62 )
          WorkbookClose(v62, 0);
LABEL_107:
        ISAMDBDeleteDatabase(v68, v29);
        return v36;
      }
      v30 = ISAMDBAddDatabase(v68, FullPath);
      v29 = v30;
      if ( v30 )
      {
        WCSCPY2((_WORD *)(v30 + 72), FullPath, 0x105u);
        *(_DWORD *)(v29 + 64) = v21;
        *(_DWORD *)(v29 + 16) = v65;
        *(_DWORD *)(v29 + 8) = 1;
        goto LABEL_86;
      }
      return -1011;
    }
    v29 = ISAMDBFindDatabase(v68, FullPath);
    if ( v29 )
      goto LABEL_86;
    v29 = ISAMDBAddDatabase(v68, FullPath);
    if ( !v29 )
      return -1011;
    if ( !NetProtocolType(FullPath) )
    {
      WCSCPY2(WideCharStr, FullPath, 0x105u);
      goto LABEL_116;
    }
    NetCreateLocalDirectory(PathName);
    v35 = NetDownloadToLocal(FullPath, (int)PathName, (int)WideCharStr, v34);
    v36 = v35;
    if ( !v35 )
    {
LABEL_102:
      ISAMDBAddNetFile(WideCharStr, 0);
      v21 |= 1u;
LABEL_116:
      v39 = v67;
      goto LABEL_117;
    }
    if ( v35 == -1305 )
    {
      __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0xFFu, Ext, 0xFFu);
      if ( Ext[0] )
        goto LABEL_112;
      WCSCAT2(FullPath, (_WORD *)dword_1003C328 + 5 * v65, 0x105u);
      v38 = NetDownloadToLocal(FullPath, (int)PathName, (int)WideCharStr, v37);
      v36 = v38;
      if ( !v38 )
        goto LABEL_102;
      if ( v38 == -1305 )
      {
LABEL_112:
        v39 = v67;
        if ( v67 == 1 )
          goto LABEL_113;
        WCSCPY2(WideCharStr, PathName, 0x105u);
        WCSCAT2(WideCharStr, Filename, 0x105u);
        WCSCAT2(WideCharStr, Ext, 0x105u);
LABEL_117:
        v40 = v64;
        if ( v64 )
        {
          v42 = v65;
LABEL_134:
          if ( (v21 & 1) != 0 || v67 == 1 )
            v58 = 32;
          else
            v58 = 18;
          v44 = v58 | 0x100;
          if ( v42 < 2 )
            v44 = v58;
          if ( (v44 & 3) == 0 )
            v21 |= 1u;
          if ( v40 )
            v44 |= 0x200u;
          v43 = WorkbookOpen(WideCharStr, v44, &v66);
          if ( !v43 )
          {
            v28 = v66;
            *(_DWORD *)(v29 + 64) = v21;
            *(_DWORD *)(v29 + 8) = 0;
            v62 = v28;
            *(_DWORD *)(v29 + 12) = v28;
            WCSCPY2((_WORD *)(v29 + 72), WideCharStr, 0x105u);
            v45 = *(_DWORD **)(v29 + 12);
            v46 = v45;
            if ( *v45 )
              v46 = (_DWORD *)v45[201];
            if ( v46[5] )
              *(_DWORD *)(v29 + 64) |= 1u;
            switch ( v45[1] )
            {
              case 3:
                *(_DWORD *)(v29 + 16) = 0;
                v47 = &ISAMLimits;
                break;
              case 4:
                *(_DWORD *)(v29 + 16) = 1;
                v47 = (int *)((char *)&ISAMLimits + 2);
                break;
              case 5:
                *(_DWORD *)(v29 + 16) = 2;
                v47 = &dword_1003C2E4;
                break;
              default:
                *(_DWORD *)(v29 + 16) = 3;
                v47 = (int *)((char *)&dword_1003C2E4 + 2);
                break;
            }
            *(_DWORD *)(v29 + 68) = v45[10];
            if ( (*(_BYTE *)v47 & 1) == 0 )
              *(_DWORD *)(v29 + 64) |= 1u;
            if ( WorkbookOneSheetPerFile(v45) )
            {
              __wsplitpath_s((const wchar_t *)(v29 + 72), 0, 0, 0, 0, Filename, 0xFFu, Ext, 0xFFu);
              v48 = MemAllocate(528);
              v49 = v48;
              if ( !v48 )
              {
LABEL_170:
                WorkbookClose(*(_DWORD *)(v29 + 12), 0);
                v36 = -1011;
                goto LABEL_107;
              }
              *(_BYTE *)(v48 + 12) = 1;
              WCSCPY2((_WORD *)(v48 + 14), Filename, 0x100u);
              WorkbookCurrentDimensions(*(_DWORD *)(v29 + 12), v49 + 4);
              v50 = *(_DWORD **)(v29 + 12);
              v51 = 12;
              if ( *v50 )
                v51 = 200;
              *(_DWORD *)(v29 + 24) = v50[v51];
              *(_DWORD *)(v29 + 28) = v49;
            }
            else
            {
              for ( j = *(_DWORD *)(v28 + 80); ; j = **(_DWORD **)(v28 + 84) )
              {
                *(_DWORD *)(v28 + 84) = j;
                if ( !j )
                  break;
                strcpyn(32);
                v61 = *(_BYTE *)(*(_DWORD *)(v28 + 84) + 12);
                v53 = MemAllocate(528);
                v54 = v53;
                if ( !v53 )
                  goto LABEL_170;
                WCSCPY2((_WORD *)(v53 + 14), v73, 0x100u);
                *(_BYTE *)(v54 + 12) = v61;
                if ( *(_DWORD *)(v29 + 28) )
                  *v59 = v54;
                else
                  *(_DWORD *)(v29 + 28) = v54;
                v59 = (int *)v54;
              }
            }
            goto LABEL_86;
          }
LABEL_127:
          v36 = v43;
          goto LABEL_107;
        }
        v41 = DOSFileExists(WideCharStr);
        if ( v41 == -3 )
        {
          ErrorSetExtendedInfoSz1(0);
          v36 = -1023;
          goto LABEL_107;
        }
        if ( !v41 )
        {
          v42 = v65;
LABEL_133:
          v40 = 0;
          goto LABEL_134;
        }
        if ( v39 != 1 )
        {
          v42 = v65;
          if ( (*((_BYTE *)&ISAMLimits + 2 * v65) & 1) == 0 )
          {
            v36 = -1001;
            goto LABEL_107;
          }
          if ( !IsAcceptableFileName(WideCharStr) )
          {
            v36 = -1809;
            goto LABEL_107;
          }
          v43 = WorkbookCreate(&v66);
          if ( v43 )
            goto LABEL_127;
          v43 = WorkbookClose(v66, 0);
          if ( v43 )
            goto LABEL_127;
          if ( NetProtocolType(FullPath) )
            ISAMDBAddNetFile(WideCharStr, 1);
          goto LABEL_133;
        }
LABEL_113:
        ErrorSetExtendedInfoSz1(0);
        v36 = -1305;
        goto LABEL_107;
      }
    }
    if ( v36 == -1023 || v36 == -1032 )
      ErrorSetExtendedInfoSz1(0);
    goto LABEL_107;
  }
  if ( ProtocolPrefix(PathName) != 1 )
    return -20158;
  if ( v7 > 1 && DOSLocatesDirectory(PathName, (int)&v66) )
    goto LABEL_78;
  v17 = &v73[wcslen(PathName) + 31];
  if ( *v17 != 92 )
  {
    v18 = *v17;
    do
    {
      if ( v18 == 47 )
        break;
      v18 = *--v17;
    }
    while ( *v17 != 92 );
    v7 = v65;
  }
  v17[1] = 0;
  if ( DOSLocatesDirectory(PathName, (int)&v66) )
  {
    WCSNCPY2(FullPath, 0x105u, a2, 0x105u);
    if ( !_wcschr(FullPath, 0x2Eu) )
      WCSCAT2(FullPath, (_WORD *)dword_1003C328 + 5 * v7, 0x105u);
    goto LABEL_69;
  }
  result = v66;
  if ( !v66 )
  {
LABEL_46:
    ErrorSetExtendedInfoSz1(0);
    return -1023;
  }
  return result;
}

```

## disassembly

```asm
0x10026c60  mov     edi, edi
0x10026c62  push    ebp
0x10026c63  mov     ebp, esp
0x10026c65  sub     esp, 0AE0h
0x10026c6b  mov     eax, ___security_cookie
0x10026c70  xor     eax, ebp
0x10026c72  mov     [ebp+var_8], eax
0x10026c75  mov     ecx, [ebp+arg_8]
0x10026c78  mov     eax, [ebp+arg_4]
0x10026c7b  push    ebx
0x10026c7c  mov     [ebp+Str], ecx
0x10026c82  mov     ecx, [ebp+arg_C]
0x10026c85  push    esi
0x10026c86  mov     esi, [ebp+arg_0]
0x10026c89  mov     [ebp+var_AD0], ecx
0x10026c8f  xor     ecx, ecx
0x10026c91  mov     [ebp+var_AC8], eax
0x10026c97  mov     [ebp+var_AD4], ecx
0x10026c9d  mov     [ebp+var_AB4], ecx
0x10026ca3  mov     [ebp+var_ABC], ecx
0x10026ca9  push    edi
0x10026caa  mov     edi, ecx
0x10026cac  test    eax, eax
0x10026cae  jz      loc_10026E41
0x10026cb4  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10026cba  mov     ecx, eax
0x10026cbc  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x10026cc1  mov     [ebp+var_AAC], eax
0x10026cc7  test    eax, eax
0x10026cc9  jnz     short loc_10026CD5
0x10026ccb  mov     eax, 0FFFFFBFBh
0x10026cd0  jmp     loc_10026E46
0x10026cd5  mov     ecx, esi
0x10026cd7  call    _ISAMDBFindSession@4; ISAMDBFindSession(x)
0x10026cdc  mov     [ebp+var_ADC], eax
0x10026ce2  test    eax, eax
0x10026ce4  jnz     short loc_10026CF0
0x10026ce6  mov     eax, 0FFFFFBB0h
0x10026ceb  jmp     loc_10026E46
0x10026cf0  mov     esi, [ebp+Str]
0x10026cf6  xor     eax, eax
0x10026cf8  mov     [ebp+var_28], ax
0x10026cfc  mov     eax, dword_1003C2D4
0x10026d01  mov     [ebp+var_AC4], eax
0x10026d07  mov     [ebp+var_AB0], 0FFFFFFFFh
0x10026d11  push    2
0x10026d13  pop     ebx
0x10026d14  mov     [ebp+var_AB8], ebx
0x10026d1a  test    esi, esi
0x10026d1c  jz      loc_10026EF5
0x10026d22  xor     eax, eax
0x10026d24  cmp     [esi], ax
0x10026d27  jz      loc_10026EF5
0x10026d2d  push    3Bh ; ';'; Ch
0x10026d2f  push    esi; Str
0x10026d30  call    ds:__imp__wcschr
0x10026d36  pop     ecx
0x10026d37  pop     ecx
0x10026d38  test    eax, eax
0x10026d3a  jz      short loc_10026D43
0x10026d3c  sub     eax, 6
0x10026d3f  xor     ebx, ebx
0x10026d41  jmp     short loc_10026D5F
0x10026d43  mov     ecx, esi
0x10026d45  xor     ebx, ebx
0x10026d47  lea     edx, [ecx+2]
0x10026d4a  mov     ax, [ecx]
0x10026d4d  add     ecx, 2
0x10026d50  cmp     ax, bx
0x10026d53  jnz     short loc_10026D4A
0x10026d55  sub     ecx, edx
0x10026d57  lea     eax, [esi-6]
0x10026d5a  sar     ecx, 1
0x10026d5c  lea     eax, [eax+ecx*2]
0x10026d5f  movzx   eax, word ptr [eax]
0x10026d62  cmp     eax, 33h ; '3'
0x10026d65  jz      short loc_10026D7A
0x10026d67  xor     ebx, ebx
0x10026d69  cmp     eax, 34h ; '4'
0x10026d6c  jnz     short loc_10026D71
0x10026d6e  inc     ebx
0x10026d6f  jmp     short loc_10026D7A
0x10026d71  cmp     eax, 35h ; '5'
0x10026d74  setnz   bl
0x10026d77  add     ebx, 2
0x10026d7a  push    105h
0x10026d7f  lea     eax, [ebp+PathName]
0x10026d85  mov     [ebp+var_AB8], ebx
0x10026d8b  push    eax
0x10026d8c  mov     edx, offset aXlole; "XLOLE="
0x10026d91  mov     ecx, esi
0x10026d93  call    ExtractConnectStringKey
0x10026d98  mov     edx, offset a1; "1"
0x10026d9d  lea     ecx, [ebp+PathName]
0x10026da3  call    _WCSICMP@8; WCSICMP(x,x)
0x10026da8  mov     ecx, [ebp+Str]
0x10026dae  neg     eax
0x10026db0  push    105h
0x10026db5  sbb     esi, esi
0x10026db7  mov     edx, offset aHdr; "HDR="
0x10026dbc  lea     eax, [ebp+PathName]
0x10026dc2  inc     esi
0x10026dc3  push    eax
0x10026dc4  mov     [ebp+var_ABC], esi
0x10026dca  call    ExtractConnectStringKey
0x10026dcf  cmp     eax, 1
0x10026dd2  jnz     short loc_10026DDD
0x10026dd4  cmp     [ebp+PathName], di
0x10026ddb  jz      short loc_10026E41
0x10026ddd  mov     edx, offset aYes; "Yes"
0x10026de2  lea     ecx, [ebp+PathName]
0x10026de8  call    _WCSICMP@8; WCSICMP(x,x)
0x10026ded  test    eax, eax
0x10026def  jnz     short loc_10026DFD
0x10026df1  mov     [ebp+var_AC4], 1
0x10026dfb  jmp     short loc_10026E17
0x10026dfd  mov     edx, offset aNo; "No"
0x10026e02  lea     ecx, [ebp+PathName]
0x10026e08  call    _WCSICMP@8; WCSICMP(x,x)
0x10026e0d  neg     eax
0x10026e0f  sbb     eax, eax
0x10026e11  and     [ebp+var_AC4], eax
0x10026e17  mov     ecx, [ebp+Str]
0x10026e1d  lea     eax, [ebp+PathName]
0x10026e23  push    105h
0x10026e28  push    eax
0x10026e29  mov     edx, offset aImex; "IMEX="
0x10026e2e  call    ExtractConnectStringKey
0x10026e33  cmp     eax, 1
0x10026e36  jnz     short loc_10026E57
0x10026e38  cmp     [ebp+PathName], di
0x10026e3f  jnz     short loc_10026E60
0x10026e41  mov     eax, 0FFFFFC15h
0x10026e46  mov     ecx, [ebp+var_8]
0x10026e49  pop     edi
0x10026e4a  pop     esi
0x10026e4b  xor     ecx, ebp; StackCookie
0x10026e4d  pop     ebx
0x10026e4e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026e53  leave
0x10026e54  retn    14h
0x10026e57  cmp     [ebp+PathName], di
0x10026e5e  jz      short loc_10026ECA
0x10026e60  mov     edx, offset a0_0; "0"
0x10026e65  lea     ecx, [ebp+PathName]
0x10026e6b  call    _WCSCMP@8; WCSCMP(x,x)
0x10026e70  test    eax, eax
0x10026e72  jnz     short loc_10026E86
0x10026e74  mov     [ebp+var_AB0], edi
0x10026e7a  mov     [ebp+var_AC4], 1
0x10026e84  jmp     short loc_10026ECA
0x10026e86  mov     edx, offset a1; "1"
0x10026e8b  lea     ecx, [ebp+PathName]
0x10026e91  call    _WCSCMP@8; WCSCMP(x,x)
0x10026e96  test    eax, eax
0x10026e98  jnz     short loc_10026EA6
0x10026e9a  mov     [ebp+var_AB0], 1
0x10026ea4  jmp     short loc_10026ECA
0x10026ea6  mov     edx, offset a2; "2"
0x10026eab  lea     ecx, [ebp+PathName]
0x10026eb1  call    _WCSCMP@8; WCSCMP(x,x)
0x10026eb6  mov     ecx, [ebp+var_AB0]
0x10026ebc  test    eax, eax
0x10026ebe  push    2
0x10026ec0  pop     eax
0x10026ec1  cmovz   ecx, eax
0x10026ec4  mov     [ebp+var_AB0], ecx
0x10026eca  mov     ecx, [ebp+Str]
0x10026ed0  lea     eax, [ebp+var_28]
0x10026ed3  push    10h
0x10026ed5  push    eax
0x10026ed6  mov     edx, offset aPwd; "PWD="
0x10026edb  call    ExtractConnectStringKey
0x10026ee0  cmp     eax, 1
0x10026ee3  jnz     short loc_10026EF5
0x10026ee5  mov     [ebp+var_ABC], esi
0x10026eeb  cmp     [ebp+var_28], di
0x10026eef  jz      loc_10026E41
0x10026ef5  push    105h
0x10026efa  push    [ebp+var_AC8]
0x10026f00  xor     esi, esi
0x10026f02  lea     ecx, [ebp+PathName]
0x10026f08  mov     edx, 105h
0x10026f0d  mov     [ebp+var_ACC], esi
0x10026f13  call    _WCSNCPY2@16; WCSNCPY2(x,x,x,x)
0x10026f18  xor     eax, eax
0x10026f1a  lea     ecx, [ebp+PathName]
0x10026f20  mov     [ebp+var_246], ax
0x10026f27  call    _NetProtocolType@4; NetProtocolType(x)
0x10026f2c  test    eax, eax
0x10026f2e  jz      loc_10027053
0x10026f34  lea     ecx, [ebp+PathName]
0x10026f3a  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10026f3f  cmp     eax, 1
0x10026f42  jz      short loc_10026F4E
0x10026f44  mov     eax, 0FFFFB142h
0x10026f49  jmp     loc_10026E46
0x10026f4e  cmp     ebx, 1
0x10026f51  jbe     short loc_10026F6D
0x10026f53  lea     eax, [ebp+var_AB4]
0x10026f59  push    eax; int
0x10026f5a  lea     ecx, [ebp+PathName]; lpPathName
0x10026f60  call    _DOSLocatesDirectory@12; DOSLocatesDirectory(x,x,x)
0x10026f65  test    eax, eax
0x10026f67  jnz     loc_1002720A
0x10026f6d  lea     ecx, [ebp+PathName]
0x10026f73  xor     esi, esi
0x10026f75  lea     edx, [ecx+2]
0x10026f78  mov     ax, [ecx]
0x10026f7b  add     ecx, 2
0x10026f7e  cmp     ax, si
0x10026f81  jnz     short loc_10026F78
0x10026f83  sub     ecx, edx
0x10026f85  sar     ecx, 1
0x10026f87  push    5Ch ; '\'
0x10026f89  pop     edx
0x10026f8a  mov     [ebp+var_AD8], edx
0x10026f90  lea     ecx, [ebp+ecx*2+var_44E]
0x10026f97  movzx   eax, word ptr [ecx]
0x10026f9a  cmp     ax, dx
0x10026f9d  jz      short loc_10026FBE
0x10026f9f  mov     edx, eax
0x10026fa1  cmp     dx, 2Fh ; '/'
0x10026fa5  jz      short loc_10026FB8
0x10026fa7  sub     ecx, 2
0x10026faa  movzx   eax, word ptr [ecx]
0x10026fad  mov     edx, eax
0x10026faf  cmp     ax, word ptr [ebp+var_AD8]
0x10026fb6  jnz     short loc_10026FA1
0x10026fb8  mov     ebx, [ebp+var_AB8]
0x10026fbe  xor     eax, eax
0x10026fc0  mov     [ecx+2], ax
0x10026fc4  lea     eax, [ebp+var_AB4]
0x10026fca  push    eax; int
0x10026fcb  lea     ecx, [ebp+PathName]; lpPathName
0x10026fd1  call    _DOSLocatesDirectory@12; DOSLocatesDirectory(x,x,x)
0x10026fd6  test    eax, eax
0x10026fd8  jnz     short loc_10027003
0x10026fda  mov     eax, [ebp+var_AB4]
0x10026fe0  test    eax, eax
0x10026fe2  jnz     loc_10026E46
0x10026fe8  lea     edx, [ebp+PathName]
0x10026fee  push    esi
0x10026fef  mov     ecx, 0FFFFE01Fh
0x10026ff4  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10026ff9  mov     eax, 0FFFFFC01h
0x10026ffe  jmp     loc_10026E46
0x10027003  mov     eax, 105h
0x10027008  lea     ecx, [ebp+FullPath]
0x1002700e  push    eax
0x1002700f  push    [ebp+var_AC8]
0x10027015  mov     edx, eax
0x10027017  call    _WCSNCPY2@16; WCSNCPY2(x,x,x,x)
0x1002701c  lea     eax, [ebp+FullPath]
0x10027022  push    2Eh ; '.'; Ch
0x10027024  push    eax; Str
0x10027025  call    ds:__imp__wcschr
0x1002702b  pop     ecx
0x1002702c  pop     ecx
0x1002702d  test    eax, eax
0x1002702f  jnz     loc_10027161
0x10027035  imul    edx, ebx, 0Ah
0x10027038  lea     ecx, [ebp+FullPath]
0x1002703e  push    105h
0x10027043  add     edx, offset dword_1003C328
0x10027049  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002704e  jmp     loc_10027161
0x10027053  push    ecx
0x10027054  lea     edx, [ebp+PathName]
0x1002705a  lea     ecx, [ebp+FullPath]
0x10027060  call    _Jetwfullpath@12; Jetwfullpath(x,x,x)
0x10027065  xor     eax, eax
0x10027067  lea     ecx, [ebp+FullPath]; lpPathName
0x1002706d  mov     [ebp+var_36], ax
0x10027071  lea     eax, [ebp+var_AB4]
0x10027077  push    eax; int
0x10027078  call    _DOSLocatesDirectory@12; DOSLocatesDirectory(x,x,x)
0x1002707d  cmp     ebx, 1
0x10027080  ja      loc_10027157
0x10027086  test    eax, eax
0x10027088  jz      short loc_100270CE
0x1002708a  lea     ecx, [ebp+FullPath]
0x10027090  xor     esi, esi
0x10027092  lea     edx, [ecx+2]
0x10027095  mov     ax, [ecx]
0x10027098  add     ecx, 2
0x1002709b  cmp     ax, si
0x1002709e  jnz     short loc_10027095
0x100270a0  sub     ecx, edx
0x100270a2  sar     ecx, 1
0x100270a4  movzx   eax, [ebp+ecx*2+var_23E]
0x100270ac  cmp     eax, 5Ch ; '\'
0x100270af  jz      short loc_100270CB
0x100270b1  cmp     eax, 3Ah ; ':'
0x100270b4  jz      short loc_100270CB
0x100270b6  push    105h
0x100270bb  mov     edx, offset asc_1000539C; "\\"
0x100270c0  lea     ecx, [ebp+FullPath]
0x100270c6  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100270cb  xor     esi, esi
  ... truncated ...
```
