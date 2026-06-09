# WBDBDeleteTable(x,x,x)

- ea: `0x10029b60`
- end: `0x10029f41`
- name: `_WBDBDeleteTable@12`
- size: `993`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x10006400`
- `0x100168a0`
- `0x10018b80`
- `0x1001a630`
- `0x1001b770`
- `0x1001bbd0`
- `0x1001bc20`
- `0x1001bc60`
- `0x1001c2b0`
- `0x1001d870`
- `0x10024505`
- `0x100246ef`
- `0x1002476e`
- `0x100255d7`
- `0x10025ab7`
- `0x100268a0`
- `0x10027e33`
- `0x1002838d`
- `0x10028701`
- `0x10028ffc`
- `0x10029648`
- `0x10029a27`
- `0x10029aad`
- `0x10029b60`
- `0x1002aaa4`
- `0x1002ab35`
- `0x1002ab9e`
- `0x1002abcc`
- `0x1002ac5e`
- `0x10032ea8`
- `0x10034bca`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10029c51`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10029c51`

## pseudocode

```c
int __stdcall WBDBDeleteTable(int a1, int a2, WCHAR *a3)
{
  int v3; // eax
  int v4; // edi
  int result; // eax
  int v6; // ebx
  int v7; // ecx
  UINT v8; // esi
  int v9; // ecx
  int v10; // eax
  _WORD *v11; // edx
  int v12; // ebx
  int v13; // ecx
  __int16 v14; // dx
  _DWORD *v15; // ecx
  _DWORD *v16; // ecx
  int v17; // [esp-14h] [ebp-65Ch]
  int v18; // [esp-10h] [ebp-658h]
  int v19; // [esp-Ch] [ebp-654h]
  int v20; // [esp-8h] [ebp-650h]
  int v21; // [esp+10h] [ebp-638h]
  UINT CodePage; // [esp+14h] [ebp-634h] BYREF
  int v23; // [esp+18h] [ebp-630h]
  _WORD *v24; // [esp+1Ch] [ebp-62Ch]
  WCHAR *v25; // [esp+20h] [ebp-628h] BYREF
  int v26; // [esp+24h] [ebp-624h]
  int v27; // [esp+28h] [ebp-620h] BYREF
  int v28; // [esp+2Ch] [ebp-61Ch]
  wchar_t FullPath[256]; // [esp+30h] [ebp-618h] BYREF
  WCHAR FileName[264]; // [esp+230h] [ebp-418h] BYREF
  wchar_t Ext[258]; // [esp+440h] [ebp-208h] BYREF

  v25 = a3;
  v3 = ISAMDBFindDatabaseUser(a1, a2);
  v4 = v3;
  v24 = (_WORD *)v3;
  if ( !v3 )
    return -1010;
  v6 = *(_DWORD *)(v3 + 4);
  v28 = v6;
  WorkbookCodePage(*(_DWORD *)(v6 + 12), &CodePage);
  if ( (*((_BYTE *)&ISAMLimits + 2 * *(_DWORD *)(v6 + 16)) & 2) == 0 )
    return -1001;
  if ( (*(_BYTE *)(v4 + 20) & 1) != 0 )
    return -1809;
  if ( *(_DWORD *)(v6 + 8) == 1 )
  {
    if ( !MakeIntoValidFilename(v17, v18, v19, v20, CodePage) )
    {
      ErrorSetExtendedInfoSz1(1);
      return -1002;
    }
    if ( ISAMDBLocateTable(v6, FullPath) )
      goto LABEL_10;
    __wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
    if ( !Ext[0] )
      WCSCAT2(FullPath, (_WORD *)dword_1003C328 + 5 * *(_DWORD *)(v6 + 16), 0x100u);
    WCSCPY2(FileName, (_WORD *)(v6 + 72), 0x105u);
    WCSCAT2(FileName, FullPath, 0x105u);
    if ( IsAcceptableFileName(FileName) )
    {
      if ( DOSFileExists(FileName) )
      {
        ErrorSetExtendedInfoSz1(1);
        return -1305;
      }
      else
      {
        JetDeleteFileW(FileName);
        return 0;
      }
    }
    return -1809;
  }
  result = LocateTableInDatabase(v4, a3, (int *)&CodePage, &v27, 2);
  if ( !result )
  {
    v8 = CodePage;
    if ( *(int *)(CodePage + 36) > 0 || *(_DWORD *)(CodePage + 56) == 1 || AnyOverlappedTables(CodePage) )
    {
LABEL_10:
      ErrorSetExtendedInfoSz2(v7);
      return -1304;
    }
    v23 = EngineOpenTable((int)v24, v8);
    if ( !v23 )
    {
      v21 = ISAMDBAddCursor(v24, v8);
      if ( v21 )
      {
        v26 = WorkbookRangeRowCount(*(_DWORD *)(v8 + 12), *(_DWORD *)(v8 + 16));
        LOWORD(v9) = 0;
        v10 = v21;
        v27 = 0;
        v11 = (_WORD *)(v21 + 30);
        v24 = (_WORD *)(v21 + 30);
        if ( v26 <= 0 )
        {
          v24 = (_WORD *)(v21 + 30);
LABEL_32:
          v23 = 0;
          v25 = (WCHAR *)(v26 - 1);
          if ( v26 - 1 >= 0 )
          {
            v12 = v26 - 1;
            do
            {
              *v11 = v12;
              *(_WORD *)(v10 + 32) = 0;
              v23 = ClearRecord(v10);
              if ( v23 )
                break;
              --v12;
              v10 = v21;
              v11 = v24;
            }
            while ( v12 >= 0 );
            v8 = CodePage;
            v6 = v28;
          }
          ISAMDBDeleteCursor(v8, v21);
          WorkbookRangeRange(v8 + 96);
          if ( !*(_DWORD *)(v8 + 48) && !*(_DWORD *)(v8 + 52) )
          {
            if ( (*((_BYTE *)&ISAMLimits + 2 * *(_DWORD *)(v6 + 16)) & 0x10) != 0 )
              WorkbookNameUpdate(v13, 2, *(_DWORD *)(v8 + 96), *(_DWORD *)(v8 + 100));
            else
              AddToDeletedTableList(v6, v8);
          }
          TableCacheRemove(v6, v8);
          if ( *(_DWORD *)(v6 + 32) == 1 && *(_DWORD *)(v8 + 84) <= 1u )
            ExceptionsTableClose(*(JET_SESID **)(v8 + 88));
          v14 = *(_WORD *)(v8 + 98);
          if ( *(_DWORD *)(*(_DWORD *)(v8 + 12) + 12) )
          {
            TranslateEXErrorToJETError(0);
          }
          else
          {
            LOWORD(CodePage) = *(_WORD *)(v8 + 96);
            HIWORD(CodePage) = v14;
            ExcelDeleteNote(CodePage);
          }
        }
        else
        {
          while ( 1 )
          {
            *v11 = v9;
            *(_WORD *)(v10 + 32) = 0;
            v23 = CheckRecord(&v25);
            if ( v23 )
              break;
            if ( !v25 )
            {
              ISAMDBDeleteCursor(v8, v21);
              v23 = -5035;
              goto LABEL_48;
            }
            v10 = v21;
            v9 = v27 + 1;
            v27 = v9;
            v11 = (_WORD *)(v21 + 30);
            if ( v9 >= v26 )
            {
              v11 = v24;
              goto LABEL_32;
            }
          }
          ISAMDBDeleteCursor(v8, v21);
        }
      }
      else
      {
        v23 = -1011;
      }
    }
LABEL_48:
    v15 = *(_DWORD **)(v8 + 92);
    if ( v15 )
      MemFree(v15);
    WorkbookRangeDelete(*(_DWORD *)(v8 + 12), *(_DWORD *)(v8 + 16));
    *(_DWORD *)(v8 + 16) = 0;
    v16 = *(_DWORD **)(v8 + 12);
    if ( v16 && v16 != *(_DWORD **)(v6 + 12) )
      WorkbookSheetClose(v16);
    ISAMDBDeleteTable(v6, v8);
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x10029b60  mov     edi, edi
0x10029b62  push    ebp
0x10029b63  mov     ebp, esp
0x10029b65  and     esp, 0FFFFFFF8h
0x10029b68  sub     esp, 63Ch
0x10029b6e  mov     eax, ___security_cookie
0x10029b73  xor     eax, esp
0x10029b75  mov     [esp+63Ch+var_4], eax
0x10029b7c  mov     ecx, [ebp+arg_0]
0x10029b7f  mov     edx, [ebp+arg_4]
0x10029b82  push    ebx
0x10029b83  push    esi
0x10029b84  mov     esi, [ebp+arg_8]
0x10029b87  push    edi
0x10029b88  mov     [esp+648h+var_628], esi
0x10029b8c  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10029b91  mov     edi, eax
0x10029b93  mov     [esp+648h+var_62C], edi
0x10029b97  test    edi, edi
0x10029b99  jnz     short loc_10029BA5
0x10029b9b  mov     eax, 0FFFFFC0Eh
0x10029ba0  jmp     loc_10029F2A
0x10029ba5  mov     ebx, [edi+4]
0x10029ba8  lea     edx, [esp+648h+CodePage]
0x10029bac  mov     [esp+648h+var_61C], ebx
0x10029bb0  mov     ecx, [ebx+0Ch]
0x10029bb3  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x10029bb8  mov     eax, [ebx+10h]
0x10029bbb  test    byte ptr _ISAMLimits[eax*2], 2
0x10029bc3  jnz     short loc_10029BCF
0x10029bc5  mov     eax, 0FFFFFC17h
0x10029bca  jmp     loc_10029F2A
0x10029bcf  test    byte ptr [edi+14h], 1
0x10029bd3  jnz     loc_10029F25
0x10029bd9  cmp     dword ptr [ebx+8], 1
0x10029bdd  jnz     loc_10029CF2
0x10029be3  push    [esp+648h+CodePage]; CodePage
0x10029be7  lea     edx, [esp+64Ch+FullPath]
0x10029beb  mov     ecx, esi
0x10029bed  sub     esp, 10h
0x10029bf0  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x10029bf5  test    eax, eax
0x10029bf7  jnz     short loc_10029C11
0x10029bf9  push    1
0x10029bfb  mov     edx, esi
0x10029bfd  mov     ecx, 0FFFFDFFAh
0x10029c02  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10029c07  mov     eax, 0FFFFFC16h
0x10029c0c  jmp     loc_10029F2A
0x10029c11  lea     edx, [esp+648h+FullPath]
0x10029c15  mov     ecx, ebx
0x10029c17  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x10029c1c  test    eax, eax
0x10029c1e  jz      short loc_10029C37
0x10029c20  mov     edx, esi
0x10029c22  push    ecx
0x10029c23  mov     ecx, 0FFFFE026h
0x10029c28  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x10029c2d  mov     eax, 0FFFFFAE8h
0x10029c32  jmp     loc_10029F2A
0x10029c37  push    0FFh; ExtCount
0x10029c3c  xor     edi, edi
0x10029c3e  lea     eax, [esp+64Ch+Ext]
0x10029c45  push    eax; Ext
0x10029c46  push    edi; FilenameCount
0x10029c47  push    edi; Filename
0x10029c48  push    edi; DirCount
0x10029c49  push    edi; Dir
0x10029c4a  push    edi; DriveCount
0x10029c4b  lea     eax, [esp+664h+FullPath]
0x10029c4f  push    edi; Drive
0x10029c50  push    eax; FullPath
0x10029c51  call    ds:__imp___wsplitpath_s
0x10029c57  add     esp, 24h
0x10029c5a  cmp     [esp+648h+Ext], di
0x10029c62  jnz     short loc_10029C7C
0x10029c64  imul    edx, [ebx+10h], 0Ah
0x10029c68  lea     ecx, [esp+648h+FullPath]
0x10029c6c  push    100h
0x10029c71  add     edx, offset dword_1003C328
0x10029c77  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029c7c  mov     edi, 105h
0x10029c81  lea     edx, [ebx+48h]
0x10029c84  push    edi
0x10029c85  lea     ecx, [esp+64Ch+FileName]
0x10029c8c  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10029c91  push    edi
0x10029c92  lea     edx, [esp+64Ch+FullPath]
0x10029c96  lea     ecx, [esp+64Ch+FileName]
0x10029c9d  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029ca2  lea     ecx, [esp+648h+FileName]
0x10029ca9  call    _IsAcceptableFileName@4; IsAcceptableFileName(x)
0x10029cae  test    eax, eax
0x10029cb0  jz      loc_10029F25
0x10029cb6  lea     ecx, [esp+648h+FileName]; lpWideCharStr
0x10029cbd  call    _DOSFileExists@4; DOSFileExists(x)
0x10029cc2  test    eax, eax
0x10029cc4  jz      short loc_10029CDE
0x10029cc6  push    1
0x10029cc8  mov     edx, esi
0x10029cca  mov     ecx, 0FFFFDF94h
0x10029ccf  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10029cd4  mov     eax, 0FFFFFAE7h
0x10029cd9  jmp     loc_10029F2A
0x10029cde  lea     eax, [esp+648h+FileName]
0x10029ce5  push    eax; lpFileName
0x10029ce6  call    _JetDeleteFileW@4; JetDeleteFileW(x)
0x10029ceb  xor     eax, eax
0x10029ced  jmp     loc_10029F2A
0x10029cf2  push    2
0x10029cf4  lea     eax, [esp+64Ch+var_620]
0x10029cf8  mov     edx, esi
0x10029cfa  push    eax
0x10029cfb  lea     eax, [esp+650h+CodePage]
0x10029cff  mov     ecx, edi
0x10029d01  push    eax
0x10029d02  call    _LocateTableInDatabase@20; LocateTableInDatabase(x,x,x,x,x)
0x10029d07  test    eax, eax
0x10029d09  jnz     loc_10029F2A
0x10029d0f  mov     esi, [esp+648h+CodePage]
0x10029d13  xor     edi, edi
0x10029d15  cmp     [esi+24h], edi
0x10029d18  jg      loc_10029F1C
0x10029d1e  cmp     dword ptr [esi+38h], 1
0x10029d22  jz      loc_10029F1C
0x10029d28  mov     ecx, esi
0x10029d2a  call    AnyOverlappedTables
0x10029d2f  test    eax, eax
0x10029d31  jnz     loc_10029F1C
0x10029d37  mov     ecx, [esp+648h+var_62C]
0x10029d3b  mov     edx, esi
0x10029d3d  call    EngineOpenTable
0x10029d42  mov     [esp+648h+var_630], eax
0x10029d46  test    eax, eax
0x10029d48  jnz     loc_10029EE2
0x10029d4e  mov     ecx, [esp+648h+var_62C]
0x10029d52  mov     edx, esi
0x10029d54  call    _ISAMDBAddCursor@8; ISAMDBAddCursor(x,x)
0x10029d59  mov     [esp+648h+var_638], eax
0x10029d5d  test    eax, eax
0x10029d5f  jnz     short loc_10029D6E
0x10029d61  mov     [esp+648h+var_630], 0FFFFFC0Dh
0x10029d69  jmp     loc_10029EE2
0x10029d6e  mov     edx, [esi+10h]
0x10029d71  mov     ecx, [esi+0Ch]
0x10029d74  call    _WorkbookRangeRowCount@8; WorkbookRangeRowCount(x,x)
0x10029d79  mov     [esp+648h+var_624], eax
0x10029d7d  mov     ecx, edi
0x10029d7f  mov     eax, [esp+648h+var_638]
0x10029d83  mov     [esp+648h+var_620], ecx
0x10029d87  lea     edx, [eax+1Eh]
0x10029d8a  mov     [esp+648h+var_62C], edx
0x10029d8e  cmp     [esp+648h+var_624], ecx
0x10029d92  jle     short loc_10029DFB
0x10029d94  mov     [edx], cx
0x10029d97  xor     ecx, ecx
0x10029d99  mov     [eax+20h], cx
0x10029d9d  mov     edx, eax
0x10029d9f  lea     ecx, [esp+648h+var_628]
0x10029da3  push    ecx
0x10029da4  call    CheckRecord
0x10029da9  mov     [esp+648h+var_630], eax
0x10029dad  test    eax, eax
0x10029daf  jnz     short loc_10029DEB
0x10029db1  cmp     [esp+648h+var_628], edi
0x10029db5  jz      short loc_10029DD3
0x10029db7  mov     ecx, [esp+648h+var_620]
0x10029dbb  mov     eax, [esp+648h+var_638]
0x10029dbf  inc     ecx
0x10029dc0  mov     [esp+648h+var_620], ecx
0x10029dc4  lea     edx, [eax+1Eh]
0x10029dc7  cmp     ecx, [esp+648h+var_624]
0x10029dcb  jl      short loc_10029D94
0x10029dcd  mov     edx, [esp+648h+var_62C]
0x10029dd1  jmp     short loc_10029DFF
0x10029dd3  mov     edx, [esp+648h+var_638]
0x10029dd7  mov     ecx, esi
0x10029dd9  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x10029dde  mov     [esp+648h+var_630], 0FFFFEC55h
0x10029de6  jmp     loc_10029EE2
0x10029deb  mov     edx, [esp+648h+var_638]
0x10029def  mov     ecx, esi
0x10029df1  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x10029df6  jmp     loc_10029EE2
0x10029dfb  mov     [esp+648h+var_62C], edx
0x10029dff  mov     ecx, [esp+648h+var_624]
0x10029e03  sub     ecx, 1
0x10029e06  mov     [esp+648h+var_630], edi
0x10029e0a  mov     [esp+648h+var_628], ecx
0x10029e0e  js      short loc_10029E41
0x10029e10  mov     ebx, ecx
0x10029e12  xor     ecx, ecx
0x10029e14  mov     [edx], bx
0x10029e17  mov     [eax+20h], cx
0x10029e1b  mov     ecx, eax
0x10029e1d  call    ClearRecord
0x10029e22  mov     esi, eax
0x10029e24  mov     [esp+648h+var_630], esi
0x10029e28  test    esi, esi
0x10029e2a  jnz     short loc_10029E39
0x10029e2c  sub     ebx, 1
0x10029e2f  mov     eax, [esp+648h+var_638]
0x10029e33  mov     edx, [esp+648h+var_62C]
0x10029e37  jns     short loc_10029E12
0x10029e39  mov     esi, [esp+648h+CodePage]
0x10029e3d  mov     ebx, [esp+648h+var_61C]
0x10029e41  mov     edx, [esp+648h+var_638]
0x10029e45  mov     ecx, esi
0x10029e47  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x10029e4c  mov     edx, [esi+10h]
0x10029e4f  lea     eax, [esi+60h]
0x10029e52  mov     ecx, [esi+0Ch]
0x10029e55  push    eax
0x10029e56  call    _WorkbookRangeRange@12; WorkbookRangeRange(x,x,x)
0x10029e5b  cmp     [esi+30h], edi
0x10029e5e  jnz     short loc_10029E91
0x10029e60  cmp     [esi+34h], edi
0x10029e63  jnz     short loc_10029E91
0x10029e65  mov     eax, [ebx+10h]
0x10029e68  test    byte ptr _ISAMLimits[eax*2], 10h
0x10029e70  jz      short loc_10029E88
0x10029e72  push    dword ptr [esi+64h]
0x10029e75  lea     edx, [esi+68h]
0x10029e78  push    dword ptr [esi+60h]
0x10029e7b  push    2
0x10029e7d  push    ecx
0x10029e7e  mov     ecx, [esi+0Ch]
0x10029e81  call    _WorkbookNameUpdate@24; WorkbookNameUpdate(x,x,x,x,x,x)
0x10029e86  jmp     short loc_10029E91
0x10029e88  mov     edx, esi
0x10029e8a  mov     ecx, ebx
0x10029e8c  call    AddToDeletedTableList
0x10029e91  mov     edx, esi
0x10029e93  mov     ecx, ebx
0x10029e95  call    _TableCacheRemove@8; TableCacheRemove(x,x)
0x10029e9a  cmp     dword ptr [ebx+20h], 1
0x10029e9e  jnz     short loc_10029EB3
0x10029ea0  cmp     dword ptr [esi+54h], 1
0x10029ea4  jz      short loc_10029EAB
0x10029ea6  cmp     [esi+54h], edi
0x10029ea9  jnz     short loc_10029EB3
0x10029eab  mov     ecx, [esi+58h]
0x10029eae  call    _ExceptionsTableClose@4; ExceptionsTableClose(x)
0x10029eb3  mov     ecx, [esi+0Ch]
0x10029eb6  movzx   eax, word ptr [esi+60h]
0x10029eba  movzx   edx, word ptr [esi+62h]
0x10029ebe  cmp     [ecx+0Ch], edi
0x10029ec1  jz      short loc_10029ECC
0x10029ec3  xor     ecx, ecx
0x10029ec5  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x10029eca  jmp     short loc_10029EE2
0x10029ecc  mov     ecx, [ecx+8]
0x10029ecf  mov     word ptr [esp+648h+CodePage], ax
0x10029ed4  mov     word ptr [esp+648h+CodePage+2], dx
0x10029ed9  push    [esp+648h+CodePage]
0x10029edd  call    _ExcelDeleteNote@8; ExcelDeleteNote(x,x)
0x10029ee2  mov     ecx, [esi+5Ch]
0x10029ee5  test    ecx, ecx
0x10029ee7  jz      short loc_10029EEE
0x10029ee9  call    _MemFree@4; MemFree(x)
0x10029eee  mov     edx, [esi+10h]
0x10029ef1  mov     ecx, [esi+0Ch]
0x10029ef4  call    _WorkbookRangeDelete@8; WorkbookRangeDelete(x,x)
0x10029ef9  mov     [esi+10h], edi
0x10029efc  mov     ecx, [esi+0Ch]
0x10029eff  test    ecx, ecx
0x10029f01  jz      short loc_10029F0D
0x10029f03  cmp     ecx, [ebx+0Ch]
0x10029f06  jz      short loc_10029F0D
0x10029f08  call    _WorkbookSheetClose@4; WorkbookSheetClose(x)
0x10029f0d  mov     edx, esi
0x10029f0f  mov     ecx, ebx
0x10029f11  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x10029f16  mov     eax, [esp+648h+var_630]
0x10029f1a  jmp     short loc_10029F2A
0x10029f1c  mov     edx, [esp+648h+var_628]
0x10029f20  jmp     loc_10029C22
0x10029f25  mov     eax, 0FFFFF8EFh
0x10029f2a  mov     ecx, [esp+648h+var_4]
0x10029f31  pop     edi
0x10029f32  pop     esi
0x10029f33  pop     ebx
0x10029f34  xor     ecx, esp; StackCookie
0x10029f36  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10029f3b  mov     esp, ebp
0x10029f3d  pop     ebp
0x10029f3e  retn    0Ch
```
