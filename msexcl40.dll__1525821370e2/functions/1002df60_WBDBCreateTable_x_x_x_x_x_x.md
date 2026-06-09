# WBDBCreateTable(x,x,x,x,x,x)

- ea: `0x1002df60`
- end: `0x1002e567`
- name: `_WBDBCreateTable@24`
- size: `1543`
- prototype: `int __stdcall(int, int, wchar_t *Source, int, int, int)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, service_task`

## callees

- `0x10006400`
- `0x10018b80`
- `0x1001a630`
- `0x1001b5e0`
- `0x1001b770`
- `0x1001b8e0`
- `0x1001e0f0`
- `0x1001e4b0`
- `0x10024505`
- `0x100246ef`
- `0x1002580a`
- `0x10025ab7`
- `0x100268a0`
- `0x10026c60`
- `0x100279f0`
- `0x10027bfb`
- `0x10027d68`
- `0x10027e33`
- `0x1002a7de`
- `0x1002aaa4`
- `0x1002aaf6`
- `0x1002ab35`
- `0x1002ab9e`
- `0x1002abcc`
- `0x1002df60`
- `0x10035510`
- `0x10035b40`
- `0x10036678`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002e0c4`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002e0c4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1002e38d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1002e38d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002e4b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002e4b6`

## pseudocode

```c
UINT __stdcall WBDBCreateTable(int a1, int a2, wchar_t *Source, int a4, int a5, _DWORD *a6)
{
  int v6; // eax
  int v7; // esi
  UINT result; // eax
  UINT v9; // edi
  int v10; // ecx
  int IntoValidFilename; // eax
  int v12; // ecx
  UINT v13; // ebx
  _DWORD *v14; // esi
  int v15; // esi
  int v16; // ebx
  bool v17; // zf
  int v18; // ecx
  int v19; // ebx
  int v20; // eax
  _WORD *v21; // eax
  _DWORD *v22; // eax
  _DWORD *v23; // ecx
  int v24; // edx
  _DWORD *v25; // esi
  int v26; // eax
  DWORD CurrentProcessId; // eax
  int v28; // eax
  int v29; // [esp-18h] [ebp-868h]
  int v30; // [esp-14h] [ebp-864h]
  int v31; // [esp-10h] [ebp-860h]
  int v32; // [esp-Ch] [ebp-85Ch]
  int v33; // [esp-8h] [ebp-858h]
  int v34; // [esp-8h] [ebp-858h]
  _DWORD v35[2]; // [esp+8h] [ebp-848h] BYREF
  int v36; // [esp+10h] [ebp-840h] BYREF
  int v37; // [esp+14h] [ebp-83Ch] BYREF
  _DWORD *v38; // [esp+18h] [ebp-838h]
  int v39; // [esp+1Ch] [ebp-834h]
  int v40; // [esp+20h] [ebp-830h]
  int v41; // [esp+24h] [ebp-82Ch]
  wchar_t *v42; // [esp+28h] [ebp-828h]
  int ValidRangeName; // [esp+2Ch] [ebp-824h]
  int v44; // [esp+30h] [ebp-820h]
  _DWORD *v45; // [esp+34h] [ebp-81Ch]
  _DWORD *v46; // [esp+38h] [ebp-818h]
  UINT CodePage; // [esp+3Ch] [ebp-814h] BYREF
  wchar_t Ext[256]; // [esp+40h] [ebp-810h] BYREF
  wchar_t v49[256]; // [esp+240h] [ebp-610h] BYREF
  WCHAR WideCharStr[262]; // [esp+440h] [ebp-410h] BYREF
  wchar_t FullPath[256]; // [esp+64Ch] [ebp-204h] BYREF

  v38 = a6;
  *a6 = -1;
  v40 = a1;
  v42 = Source;
  v45 = 0;
  ValidRangeName = 1;
  v39 = 0;
  v44 = 0;
  v6 = ISAMDBFindDatabaseUser(a1, a2);
  v7 = v6;
  v46 = (_DWORD *)v6;
  if ( !v6 )
    return -1010;
  v9 = *(_DWORD *)(v6 + 4);
  if ( (*((_BYTE *)&ISAMLimits + 2 * *(_DWORD *)(v9 + 16)) & 4) == 0 )
    return -1001;
  if ( (*(_BYTE *)(v6 + 20) & 1) != 0 )
    return -1809;
  v10 = *(_DWORD *)(v9 + 12);
  v41 = *(_DWORD *)(v9 + 8);
  WorkbookCodePage(v10, &CodePage);
  if ( v41 == 1 )
  {
    v45 = (_DWORD *)v9;
    IntoValidFilename = MakeIntoValidFilename(v29, v30, v31, v32, CodePage);
    ValidRangeName = IntoValidFilename;
    if ( IntoValidFilename )
    {
      v33 = *(_DWORD *)(v9 + 16);
      if ( IntoValidFilename == 1 )
        ValidRangeName = WorkbookMakeValidRangeName(FullPath, v49, v12, CodePage, v33);
      else
        WorkbookMakeValidRangeName(FullPath, v49, v12, CodePage, v33);
      WCSCPY2(FullPath, v49, 0x100u);
      v13 = ISAMDBLocateTable(v9, FullPath);
      if ( !v13 )
      {
        __wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
        if ( !Ext[0] )
          WCSCAT2(FullPath, (_WORD *)dword_1003C328 + 5 * *(_DWORD *)(v9 + 16), 0x100u);
        WCSCPY2(WideCharStr, (_WORD *)(v9 + 72), 0x105u);
        WCSCAT2(WideCharStr, FullPath, 0x105u);
        if ( DOSFileExists(WideCharStr) )
        {
          result = WBISAMOpenDatabase(v40, WideCharStr, (const wchar_t *)(v7 + 64), &v36, *(_DWORD *)(v9 + 64));
          if ( result )
            return result;
          v9 = *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(v7 + 8) + 4) + 8);
          if ( v9 )
          {
            while ( 1 )
            {
              v14 = *(_DWORD **)(v9 + 44);
              v46 = v14;
              if ( v14 )
                break;
LABEL_22:
              v9 = *(_DWORD *)v9;
              if ( !v9 )
                goto LABEL_23;
            }
            while ( v14[4] != v36 )
            {
              v14 = (_DWORD *)*v14;
              v46 = v14;
              if ( !v14 )
              {
                v46 = 0;
                goto LABEL_22;
              }
            }
          }
          goto LABEL_23;
        }
      }
LABEL_57:
      ErrorSetExtendedInfoSz1(1);
      return -1303;
    }
LABEL_74:
    ErrorSetExtendedInfoSz1(1);
    return -1002;
  }
  FullPath[255] = 0;
  wcsncpy(FullPath, Source, 0xFFu);
  if ( !WorkbookMakeValidColumnName(FullPath, FullPath, 256, CodePage) )
    goto LABEL_74;
  if ( IsTableA1Reference((_DWORD *)v9, &v37, v35) != 1 )
  {
    if ( IsTableWholeSheet(v9, (int)FullPath, &v37, v35) == 1 )
    {
      v39 = 1;
    }
    else
    {
      if ( _wcschr(FullPath, dword_1003C35A) )
        goto LABEL_74;
      ValidRangeName = WorkbookMakeValidRangeName(Source, FullPath, v34, CodePage, *(_DWORD *)(v9 + 16));
      if ( !ValidRangeName )
        goto LABEL_74;
      CodePage = ISAMDBLocateTable(v9, FullPath);
      if ( CodePage )
        goto LABEL_57;
    }
    goto LABEL_35;
  }
  v16 = 1;
  v17 = *(_DWORD *)(v9 + 28) == 0;
  v44 = 1;
  if ( v17 )
  {
    v19 = MemAllocate(528);
    if ( !v19 )
      return -1011;
    CodePage = WorkbookSheetAppend(*(_DWORD **)(v9 + 12), L"1", v18);
    if ( CodePage )
    {
      MemFree((_DWORD *)v19);
      return CodePage;
    }
    *(_DWORD *)(v9 + 28) = v19;
    *(_BYTE *)(v19 + 12) = 1;
    WCSCPY2((_WORD *)(v19 + 14), L"1", 0x100u);
LABEL_35:
    v16 = v44;
  }
  v20 = LocateTableInDatabase(v7, FullPath, (int *)&CodePage, &v37, 16388);
  v15 = v20;
  if ( v20 && v20 != -1305 )
  {
LABEL_68:
    if ( v41 )
      WBDBCloseDatabase(v40, v46[3], 0);
    return v15;
  }
  v17 = v16 == 1;
  v13 = CodePage;
  if ( v17 || v39 == 1 )
    *(_DWORD *)(CodePage + 68) = 1;
  if ( !v20 )
  {
    if ( *(_DWORD *)(v13 + 68) != 1 )
    {
      WorkbookSheetClose(*(_DWORD **)(v13 + 12));
      ISAMDBDeleteTable(v9, v13);
      ErrorSetExtendedInfoSz1(1);
      v15 = -1303;
      goto LABEL_68;
    }
    *(_DWORD *)(v13 + 32) = *(unsigned __int16 *)(v13 + 102) - *(unsigned __int16 *)(v13 + 98) + 1;
  }
  if ( WorkbookOneSheetPerFile(*(_DWORD *)(v9 + 12)) )
  {
    if ( !v13 )
    {
      v21 = *(_WORD **)(v9 + 28);
      if ( (v21[2] || v21[4] || v21[3] || v21[5])
        && dword_1003C2D8 + 1 + (unsigned __int16)v21[4] > *((unsigned __int16 *)&dword_1003C2FA + *(_DWORD *)(v9 + 16)) )
      {
        v15 = -5037;
        goto LABEL_68;
      }
      goto LABEL_24;
    }
LABEL_64:
    v23 = v46;
    goto LABEL_65;
  }
LABEL_23:
  if ( v13 )
    goto LABEL_64;
LABEL_24:
  if ( v9 && *(_DWORD *)(v9 + 24) == 1 )
  {
    v15 = -1809;
    goto LABEL_68;
  }
  v22 = (_DWORD *)ISAMDBAddTable(v9, FullPath);
  v13 = (UINT)v22;
  if ( !v22 )
  {
LABEL_60:
    v15 = -1011;
    goto LABEL_68;
  }
  v23 = v46;
  v24 = v41;
  v22[8] = (__int16)dword_1003C2EE;
  v22[15] = 1;
  v22[21] = v23[14];
  if ( v24 == 1 )
  {
    v25 = v45;
    *v22 = v45[12];
    v25[12] = v22;
    *(_DWORD *)(v9 + 48) = 0;
  }
  v22[19] = v24;
LABEL_65:
  v26 = ISAMDBAddCursor(v23, v13);
  v45 = (_DWORD *)v26;
  if ( !v26 )
    goto LABEL_60;
  *(_DWORD *)(v26 + 20) = 3;
  *(_BYTE *)(v26 + 28) = 0;
  *(_DWORD *)(v13 + 56) = 1;
  *(_DWORD *)(v13 + 36) = 0;
  CurrentProcessId = GetCurrentProcessId();
  v28 = ISAMDBFindTask(CurrentProcessId);
  v15 = (*(int (__thiscall **)(_DWORD, int, _DWORD *, _DWORD, int *))(*(_DWORD *)(v28 + 28) + 36))(
          *(_DWORD *)(*(_DWORD *)(v28 + 28) + 36),
          v40,
          v38,
          v45[3],
          TableEntryPoints);
  if ( v15 )
  {
    ISAMDBDeleteTable(v9, v13);
    goto LABEL_68;
  }
  v45[4] = *v38;
  result = 0;
  if ( ValidRangeName == 2 )
    return 5011;
  return result;
}

```

## disassembly

```asm
0x1002df60  mov     edi, edi
0x1002df62  push    ebp
0x1002df63  mov     ebp, esp
0x1002df65  sub     esp, 848h
0x1002df6b  mov     eax, ___security_cookie
0x1002df70  xor     eax, ebp
0x1002df72  mov     [ebp+var_4], eax
0x1002df75  mov     ecx, [ebp+arg_14]
0x1002df78  mov     eax, [ebp+arg_0]
0x1002df7b  mov     edx, [ebp+arg_4]
0x1002df7e  push    ebx
0x1002df7f  mov     ebx, [ebp+Source]
0x1002df82  push    esi
0x1002df83  xor     esi, esi
0x1002df85  mov     [ebp+var_838], ecx
0x1002df8b  mov     dword ptr [ecx], 0FFFFFFFFh
0x1002df91  mov     ecx, eax
0x1002df93  mov     [ebp+var_830], eax
0x1002df99  mov     [ebp+var_828], ebx
0x1002df9f  mov     [ebp+var_81C], esi
0x1002dfa5  mov     [ebp+var_824], 1
0x1002dfaf  mov     [ebp+var_834], esi
0x1002dfb5  mov     [ebp+var_820], esi
0x1002dfbb  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x1002dfc0  mov     esi, eax
0x1002dfc2  mov     [ebp+var_818], esi
0x1002dfc8  test    esi, esi
0x1002dfca  jnz     short loc_1002DFD6
0x1002dfcc  mov     eax, 0FFFFFC0Eh
0x1002dfd1  jmp     loc_1002E557
0x1002dfd6  push    edi
0x1002dfd7  mov     edi, [esi+4]
0x1002dfda  mov     eax, [edi+10h]
0x1002dfdd  test    byte ptr _ISAMLimits[eax*2], 4
0x1002dfe5  jnz     short loc_1002DFF1
0x1002dfe7  mov     eax, 0FFFFFC17h
0x1002dfec  jmp     loc_1002E556
0x1002dff1  test    byte ptr [esi+14h], 1
0x1002dff5  jz      short loc_1002E001
0x1002dff7  mov     eax, 0FFFFF8EFh
0x1002dffc  jmp     loc_1002E556
0x1002e001  mov     eax, [edi+8]
0x1002e004  lea     edx, [ebp+CodePage]
0x1002e00a  mov     ecx, [edi+0Ch]
0x1002e00d  mov     [ebp+var_82C], eax
0x1002e013  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x1002e018  cmp     [ebp+var_82C], 1
0x1002e01f  jnz     loc_1002E1B5
0x1002e025  push    [ebp+CodePage]; CodePage
0x1002e02b  lea     edx, [ebp+FullPath]
0x1002e031  mov     [ebp+var_81C], edi
0x1002e037  sub     esp, 10h
0x1002e03a  mov     ecx, ebx
0x1002e03c  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x1002e041  mov     [ebp+var_824], eax
0x1002e047  test    eax, eax
0x1002e049  jz      loc_1002E543
0x1002e04f  lea     edx, [ebp+var_610]
0x1002e055  push    dword ptr [edi+10h]; int
0x1002e058  push    [ebp+CodePage]; CodePage
0x1002e05e  push    ecx; int
0x1002e05f  lea     ecx, [ebp+FullPath]; lpWideCharStr
0x1002e065  cmp     eax, 1
0x1002e068  jnz     short loc_1002E077
0x1002e06a  call    _WorkbookMakeValidRangeName@20; WorkbookMakeValidRangeName(x,x,x,x,x)
0x1002e06f  mov     [ebp+var_824], eax
0x1002e075  jmp     short loc_1002E07C
0x1002e077  call    _WorkbookMakeValidRangeName@20; WorkbookMakeValidRangeName(x,x,x,x,x)
0x1002e07c  push    100h
0x1002e081  lea     edx, [ebp+var_610]
0x1002e087  lea     ecx, [ebp+FullPath]
0x1002e08d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002e092  lea     edx, [ebp+FullPath]
0x1002e098  mov     ecx, edi
0x1002e09a  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x1002e09f  mov     ebx, eax
0x1002e0a1  test    ebx, ebx
0x1002e0a3  jnz     loc_1002E3DF
0x1002e0a9  push    0FFh; ExtCount
0x1002e0ae  lea     eax, [ebp+Ext]
0x1002e0b4  push    eax; Ext
0x1002e0b5  xor     eax, eax
0x1002e0b7  push    eax; FilenameCount
0x1002e0b8  push    eax; Filename
0x1002e0b9  push    eax; DirCount
0x1002e0ba  push    eax; Dir
0x1002e0bb  push    eax; DriveCount
0x1002e0bc  push    eax; Drive
0x1002e0bd  lea     eax, [ebp+FullPath]
0x1002e0c3  push    eax; FullPath
0x1002e0c4  call    ds:__imp___wsplitpath_s
0x1002e0ca  add     esp, 24h
0x1002e0cd  cmp     [ebp+Ext], bx
0x1002e0d4  jnz     short loc_1002E0F0
0x1002e0d6  imul    edx, [edi+10h], 0Ah
0x1002e0da  lea     ecx, [ebp+FullPath]
0x1002e0e0  push    100h
0x1002e0e5  add     edx, offset dword_1003C328
0x1002e0eb  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002e0f0  push    105h
0x1002e0f5  lea     edx, [edi+48h]
0x1002e0f8  lea     ecx, [ebp+WideCharStr]
0x1002e0fe  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002e103  push    105h
0x1002e108  lea     edx, [ebp+FullPath]
0x1002e10e  lea     ecx, [ebp+WideCharStr]
0x1002e114  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002e119  lea     ecx, [ebp+WideCharStr]; lpWideCharStr
0x1002e11f  call    _DOSFileExists@4; DOSFileExists(x)
0x1002e124  test    eax, eax
0x1002e126  jz      loc_1002E3DF
0x1002e12c  push    dword ptr [edi+40h]
0x1002e12f  lea     eax, [ebp+var_840]
0x1002e135  push    eax
0x1002e136  lea     eax, [esi+40h]
0x1002e139  push    eax
0x1002e13a  lea     eax, [ebp+WideCharStr]
0x1002e140  push    eax
0x1002e141  push    [ebp+var_830]
0x1002e147  call    _WBISAMOpenDatabase@20; WBISAMOpenDatabase(x,x,x,x,x)
0x1002e14c  test    eax, eax
0x1002e14e  jnz     loc_1002E556
0x1002e154  mov     eax, [esi+8]
0x1002e157  mov     eax, [eax+4]
0x1002e15a  mov     edi, [eax+8]
0x1002e15d  test    edi, edi
0x1002e15f  jz      short loc_1002E191
0x1002e161  mov     eax, [ebp+var_840]
0x1002e167  mov     esi, [edi+2Ch]
0x1002e16a  mov     [ebp+var_818], esi
0x1002e170  test    esi, esi
0x1002e172  jz      short loc_1002E18B
0x1002e174  cmp     [esi+10h], eax
0x1002e177  jz      short loc_1002E191
0x1002e179  mov     esi, [esi]
0x1002e17b  mov     [ebp+var_818], esi
0x1002e181  test    esi, esi
0x1002e183  jnz     short loc_1002E174
0x1002e185  mov     [ebp+var_818], esi
0x1002e18b  mov     edi, [edi]
0x1002e18d  test    edi, edi
0x1002e18f  jnz     short loc_1002E167
0x1002e191  test    ebx, ebx
0x1002e193  jnz     loc_1002E489
0x1002e199  test    edi, edi
0x1002e19b  jz      loc_1002E42A
0x1002e1a1  cmp     dword ptr [edi+18h], 1
0x1002e1a5  jnz     loc_1002E42A
0x1002e1ab  mov     esi, 0FFFFF8EFh
0x1002e1b0  jmp     loc_1002E4FC
0x1002e1b5  xor     eax, eax
0x1002e1b7  push    0FFh; Count
0x1002e1bc  mov     [ebp+var_6], ax
0x1002e1c0  lea     eax, [ebp+FullPath]
0x1002e1c6  push    ebx; Source
0x1002e1c7  push    eax; Destination
0x1002e1c8  call    _wcsncpy
0x1002e1cd  add     esp, 0Ch
0x1002e1d0  lea     edx, [ebp+FullPath]; String1
0x1002e1d6  mov     ecx, edx; String2
0x1002e1d8  push    [ebp+CodePage]; CodePage
0x1002e1de  push    100h; int
0x1002e1e3  call    _WorkbookMakeValidColumnName@16; WorkbookMakeValidColumnName(x,x,x,x)
0x1002e1e8  test    eax, eax
0x1002e1ea  jz      loc_1002E543
0x1002e1f0  lea     eax, [ebp+var_848]
0x1002e1f6  mov     ecx, edi
0x1002e1f8  push    eax
0x1002e1f9  lea     eax, [ebp+var_83C]
0x1002e1ff  push    eax
0x1002e200  lea     edx, [ebp+FullPath]
0x1002e206  call    _IsTableA1Reference@16; IsTableA1Reference(x,x,x,x)
0x1002e20b  cmp     eax, 1
0x1002e20e  jnz     loc_1002E351
0x1002e214  xor     ebx, ebx
0x1002e216  inc     ebx
0x1002e217  cmp     dword ptr [edi+1Ch], 0
0x1002e21b  mov     [ebp+var_820], ebx
0x1002e221  jnz     short loc_1002E286
0x1002e223  mov     ecx, 210h
0x1002e228  call    _MemAllocate@4; MemAllocate(x)
0x1002e22d  mov     ebx, eax
0x1002e22f  test    ebx, ebx
0x1002e231  jnz     short loc_1002E23D
0x1002e233  mov     eax, 0FFFFFC0Dh
0x1002e238  jmp     loc_1002E556
0x1002e23d  push    ecx
0x1002e23e  mov     ecx, [edi+0Ch]
0x1002e241  mov     edx, offset a1; "1"
0x1002e246  call    _WorkbookSheetAppend@12; WorkbookSheetAppend(x,x,x)
0x1002e24b  mov     [ebp+CodePage], eax
0x1002e251  test    eax, eax
0x1002e253  jz      short loc_1002E267
0x1002e255  mov     ecx, ebx
0x1002e257  call    _MemFree@4; MemFree(x)
0x1002e25c  mov     eax, [ebp+CodePage]
0x1002e262  jmp     loc_1002E556
0x1002e267  mov     [edi+1Ch], ebx
0x1002e26a  lea     ecx, [ebx+0Eh]
0x1002e26d  push    100h
0x1002e272  mov     edx, offset a1; "1"
0x1002e277  mov     byte ptr [ebx+0Ch], 1
0x1002e27b  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002e280  mov     ebx, [ebp+var_820]
0x1002e286  push    4004h
0x1002e28b  lea     eax, [ebp+var_83C]
0x1002e291  mov     ecx, esi
0x1002e293  push    eax
0x1002e294  lea     eax, [ebp+CodePage]
0x1002e29a  push    eax
0x1002e29b  lea     edx, [ebp+FullPath]
0x1002e2a1  call    _LocateTableInDatabase@20; LocateTableInDatabase(x,x,x,x,x)
0x1002e2a6  mov     esi, eax
0x1002e2a8  test    esi, esi
0x1002e2aa  jz      short loc_1002E2B8
0x1002e2ac  cmp     esi, 0FFFFFAE7h
0x1002e2b2  jnz     loc_1002E4FC
0x1002e2b8  cmp     ebx, 1
0x1002e2bb  mov     ebx, [ebp+CodePage]
0x1002e2c1  jz      short loc_1002E2CC
0x1002e2c3  cmp     [ebp+var_834], 1
0x1002e2ca  jnz     short loc_1002E2D3
0x1002e2cc  mov     dword ptr [ebx+44h], 1
0x1002e2d3  test    esi, esi
0x1002e2d5  jnz     short loc_1002E2EF
0x1002e2d7  cmp     dword ptr [ebx+44h], 1
0x1002e2db  jnz     loc_1002E3FD
0x1002e2e1  movzx   ecx, word ptr [ebx+66h]
0x1002e2e5  movzx   eax, word ptr [ebx+62h]
0x1002e2e9  sub     ecx, eax
0x1002e2eb  inc     ecx
0x1002e2ec  mov     [ebx+20h], ecx
0x1002e2ef  mov     ecx, [edi+0Ch]
0x1002e2f2  call    _WorkbookOneSheetPerFile@4; WorkbookOneSheetPerFile(x)
0x1002e2f7  test    eax, eax
0x1002e2f9  jz      loc_1002E191
0x1002e2ff  test    ebx, ebx
0x1002e301  jnz     loc_1002E489
0x1002e307  mov     eax, [edi+1Ch]
0x1002e30a  xor     ecx, ecx
0x1002e30c  cmp     [eax+4], cx
0x1002e310  jnz     short loc_1002E328
0x1002e312  cmp     [eax+8], cx
0x1002e316  jnz     short loc_1002E328
0x1002e318  cmp     [eax+6], cx
0x1002e31c  jnz     short loc_1002E328
0x1002e31e  cmp     [eax+0Ah], cx
0x1002e322  jz      loc_1002E199
0x1002e328  movzx   ecx, word ptr [eax+8]
0x1002e32c  mov     eax, dword_1003C2D8
0x1002e331  inc     eax
0x1002e332  add     ecx, eax
0x1002e334  mov     eax, [edi+10h]
0x1002e337  movzx   eax, word ptr dword_1003C2FA[eax*2]
0x1002e33f  cmp     ecx, eax
0x1002e341  jle     loc_1002E199
0x1002e347  mov     esi, 0FFFFEC53h
0x1002e34c  jmp     loc_1002E4FC
0x1002e351  lea     eax, [ebp+var_848]
0x1002e357  mov     ecx, edi
0x1002e359  push    eax
0x1002e35a  lea     eax, [ebp+var_83C]
0x1002e360  push    eax
0x1002e361  lea     edx, [ebp+FullPath]
0x1002e367  call    _IsTableWholeSheet@16; IsTableWholeSheet(x,x,x,x)
0x1002e36c  xor     ecx, ecx
0x1002e36e  inc     ecx
0x1002e36f  cmp     eax, ecx
0x1002e371  jnz     short loc_1002E37E
0x1002e373  mov     [ebp+var_834], ecx
0x1002e379  jmp     loc_1002E280
0x1002e37e  movzx   eax, word ptr dword_1003C35A
0x1002e385  push    eax; Ch
0x1002e386  lea     eax, [ebp+FullPath]
0x1002e38c  push    eax; Str
0x1002e38d  call    ds:__imp__wcschr
0x1002e393  pop     ecx
0x1002e394  pop     ecx
0x1002e395  test    eax, eax
0x1002e397  jnz     loc_1002E543
0x1002e39d  push    dword ptr [edi+10h]; int
0x1002e3a0  lea     edx, [ebp+FullPath]
0x1002e3a6  push    [ebp+CodePage]; CodePage
0x1002e3ac  push    ecx; int
0x1002e3ad  mov     ecx, ebx; lpWideCharStr
0x1002e3af  call    _WorkbookMakeValidRangeName@20; WorkbookMakeValidRangeName(x,x,x,x,x)
0x1002e3b4  mov     [ebp+var_824], eax
0x1002e3ba  test    eax, eax
0x1002e3bc  jz      loc_1002E543
0x1002e3c2  lea     edx, [ebp+FullPath]
0x1002e3c8  mov     ecx, edi
0x1002e3ca  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x1002e3cf  mov     [ebp+CodePage], eax
0x1002e3d5  test    eax, eax
0x1002e3d7  jz      loc_1002E280
0x1002e3dd  jmp     short loc_1002E3E5
0x1002e3df  mov     ebx, [ebp+var_828]
0x1002e3e5  push    1
0x1002e3e7  mov     edx, ebx
0x1002e3e9  mov     ecx, 0FFFFE01Eh
  ... truncated ...
```
