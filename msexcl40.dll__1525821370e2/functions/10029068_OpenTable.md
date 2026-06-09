# OpenTable

- ea: `0x10029068`
- end: `0x10029547`
- name: `OpenTable`
- size: `1247`
- prototype: `int __fastcall(int, int, _DWORD *, int, int, int)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, service_task`

## callers

- `0x10029550`
- `0x10029590`

## callees

- `0x10006400`
- `0x10018b80`
- `0x1001a630`
- `0x1001b770`
- `0x1001bc60`
- `0x100243dc`
- `0x10024505`
- `0x100246ef`
- `0x1002476e`
- `0x100268a0`
- `0x10026c60`
- `0x100279f0`
- `0x10027e33`
- `0x10028701`
- `0x10028ee0`
- `0x10028f6e`
- `0x10028ffc`
- `0x10029068`
- `0x1002a7de`
- `0x1002ab35`
- `0x1002ab9e`
- `0x1002abcc`
- `0x1002ac5e`
- `0x10034bca`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100291d9`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100291d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002946d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002946d`

## pseudocode

```c
int __fastcall OpenTable(int a1, int a2, _DWORD *a3, int a4, int a5, int a6)
{
  int v6; // esi
  _DWORD *v7; // ebx
  __int16 *v8; // ecx
  int v9; // eax
  __int16 v10; // ax
  int result; // eax
  _DWORD *v12; // edi
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  UINT v16; // eax
  int v17; // edx
  _DWORD *v18; // ecx
  int v19; // ebx
  int v20; // ecx
  int v21; // ebx
  int v22; // ebx
  unsigned int v23; // eax
  DWORD CurrentProcessId; // eax
  int v25; // eax
  _DWORD *v26; // esi
  int v27; // [esp-10h] [ebp-8ECh]
  int v28; // [esp-Ch] [ebp-8E8h]
  int v29; // [esp-8h] [ebp-8E4h]
  int v30; // [esp-4h] [ebp-8E0h]
  int v31; // [esp+0h] [ebp-8DCh]
  _DWORD *v32; // [esp+10h] [ebp-8CCh]
  UINT CodePage; // [esp+14h] [ebp-8C8h] BYREF
  int v34[2]; // [esp+18h] [ebp-8C4h] BYREF
  int v35; // [esp+20h] [ebp-8BCh]
  _DWORD *v36; // [esp+24h] [ebp-8B8h]
  int v37; // [esp+28h] [ebp-8B4h]
  int v38; // [esp+2Ch] [ebp-8B0h]
  _DWORD *v39; // [esp+30h] [ebp-8ACh]
  int v40; // [esp+34h] [ebp-8A8h] BYREF
  int v41; // [esp+38h] [ebp-8A4h] BYREF
  WCHAR v42[68]; // [esp+3Ch] [ebp-8A0h] BYREF
  wchar_t FullPath[264]; // [esp+C4h] [ebp-818h] BYREF
  char v44[512]; // [esp+2D4h] [ebp-608h] BYREF
  unsigned __int16 v45[256]; // [esp+4D4h] [ebp-408h] BYREF
  wchar_t Ext[258]; // [esp+6D4h] [ebp-208h] BYREF

  v6 = a2;
  v38 = a1;
  CodePage = 0;
  v36 = 0;
  v7 = *(_DWORD **)(a2 + 4);
  v40 = 0;
  v34[0] = 0;
  v8 = (__int16 *)a4;
  v39 = a3;
  v9 = v7[2];
  v35 = a2;
  v34[1] = a4;
  v32 = v7;
  v37 = v9;
  do
    v10 = *v8++;
  while ( v10 != (_WORD)CodePage );
  if ( (unsigned int)(((int)v8 - a4 - 2) >> 1) > 0x40 )
    return -1002;
  WCSCPY2(65);
  WorkbookCodePage(v7[3], &CodePage);
  if ( v7[2] != 1 )
    goto LABEL_28;
  v36 = v7;
  if ( !MakeIntoValidFilename(v27, v28, v29, v30, CodePage) )
  {
    ErrorSetExtendedInfoSz1(1);
    return -1002;
  }
  v12 = (_DWORD *)ISAMDBLocateTable(v7, v44);
  v34[0] = (int)v12;
  if ( v12 )
  {
    v17 = v37;
    goto LABEL_32;
  }
  WCSCPY2(261);
  WCSCAT2(261);
  WCSCPY2(256);
  v13 = DOSFileExists(FullPath);
  if ( v13 )
  {
    if ( v13 == -3 )
    {
LABEL_18:
      ErrorSetExtendedInfoSz1(0);
      return -1023;
    }
    if ( v13 == -5 )
    {
LABEL_17:
      ErrorSetExtendedInfoSz1(0);
      return -1032;
    }
    __wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, Ext, 0xFFu);
    if ( Ext[0] )
    {
LABEL_16:
      ErrorSetExtendedInfoSz1(0);
      return -1305;
    }
    WCSCAT2(261);
    WCSCAT2(256);
    v14 = DOSFileExists(FullPath);
    if ( v14 )
    {
      if ( v14 != -3 )
      {
        if ( v14 != -5 )
          goto LABEL_16;
        goto LABEL_17;
      }
      goto LABEL_18;
    }
  }
  v31 = v7[16];
  v15 = v38;
  result = WBISAMOpenDatabase(*(_DWORD *)(v38 + 12), FullPath, v6 + 64, &v41, v31);
  if ( !result )
  {
    v7 = *(_DWORD **)(*(_DWORD *)(v15 + 4) + 8);
    v32 = v7;
    if ( v7 )
    {
      while ( 1 )
      {
        v6 = v7[11];
        v35 = v6;
        if ( v6 )
          break;
LABEL_25:
        v7 = (_DWORD *)*v7;
        if ( !v7 )
          goto LABEL_26;
      }
      while ( *(_DWORD *)(v6 + 16) != v41 )
      {
        v6 = *(_DWORD *)v6;
        v35 = v6;
        if ( !v6 )
        {
          v35 = 0;
          goto LABEL_25;
        }
      }
LABEL_26:
      v32 = v7;
    }
    MakeValidJetName(v45, v42, 65, CodePage);
LABEL_28:
    v16 = LocateTableInDatabase(v6, v42, v34, &v40, 2);
    v12 = (_DWORD *)v34[0];
    CodePage = v16;
    if ( v16 )
    {
      v21 = CodePage;
      goto LABEL_64;
    }
    v17 = v37;
    if ( v37 == 1 )
    {
      v18 = v36;
      *(_DWORD *)v34[0] = v36[12];
      v18[12] = v12;
      v7[12] = 0;
    }
LABEL_32:
    v19 = a5 | 4;
    v12[19] = v17;
    if ( (*(_BYTE *)(v6 + 20) & 1) == 0 )
      v19 = a5;
    v36 = (_DWORD *)v19;
    if ( !a6 )
    {
      if ( AnyCursorHasOption(v12, 2) == 1 )
      {
LABEL_36:
        ErrorSetExtendedInfoSz2(v20);
        v21 = -1302;
        goto LABEL_64;
      }
      if ( AnyCursorHasOption(v12, 1) == 1 )
      {
        if ( v19 != 4 )
          goto LABEL_36;
      }
      else if ( (v12[5] || AnyOverlappedTables(v12) == 1)
             && ((v19 & 2) != 0 || (v19 & 1) != 0 && !AllCursorsHaveOption(v12)) )
      {
        ErrorSetExtendedInfoSz2(v20);
        v21 = -1304;
        goto LABEL_64;
      }
    }
    if ( v12[9] || (v21 = EngineOpenTable(v6, (int)v12), v21 >= 0) )
    {
      v22 = ISAMDBAddCursor(v6, v12);
      if ( v22 )
      {
        v23 = (unsigned int)v36;
        *(_DWORD *)(v22 + 20) = v36;
        *(_BYTE *)(v22 + 28) = 0;
        if ( (v23 & 0x80000) != 0 )
          *(_DWORD *)(v22 + 24) = 1;
        if ( (v23 & 4) != 0 )
          *(_BYTE *)(v22 + 28) = 1;
        *(_BYTE *)(v22 + 29) = 2;
        *(_DWORD *)(v22 + 30) = 0;
        if ( v12[11] == 1 )
        {
          if ( WorkbookRangeRowCount(v12[3], v12[4]) == 1 )
            *(_BYTE *)(v22 + 29) = 0;
          else
            ++*(_WORD *)(v22 + 30);
        }
        CurrentProcessId = GetCurrentProcessId();
        v25 = ISAMDBFindTask(CurrentProcessId);
        CodePage = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD *, _DWORD, int *))(*(_DWORD *)(v25 + 28) + 36))(
                     *(_DWORD *)(*(_DWORD *)(v25 + 28) + 36),
                     *(_DWORD *)(v38 + 12),
                     v39,
                     *(_DWORD *)(v22 + 12),
                     TableEntryPoints);
        if ( !CodePage )
        {
          *(_DWORD *)(v22 + 16) = *v39;
          return 0;
        }
        ISAMDBDeleteCursor(v12, v22);
        v26 = v32;
        if ( !v12[5] )
          ISAMDBDeleteTable(v32, v12);
        v21 = CodePage;
        goto LABEL_65;
      }
      v21 = -1011;
    }
LABEL_64:
    v26 = v32;
LABEL_65:
    if ( v40 == 1 && v26 )
    {
      if ( v26[8] == 1 && v12[21] <= 1u )
        ExceptionsTableClose(v12[22]);
      WorkbookSheetClose(v12[3]);
      ISAMDBDeleteTable(v26, v12);
    }
    if ( v37 )
      WBDBCloseDatabase(*(_DWORD *)(v38 + 12), *(_DWORD *)(v35 + 12), 0);
    return v21;
  }
  return result;
}

```

## disassembly

```asm
0x10029068  mov     edi, edi
0x1002906a  push    ebp
0x1002906b  mov     ebp, esp
0x1002906d  and     esp, 0FFFFFFF8h
0x10029070  sub     esp, 8CCh
0x10029076  mov     eax, ___security_cookie
0x1002907b  xor     eax, esp
0x1002907d  mov     [esp+8CCh+var_4], eax
0x10029084  mov     eax, [ebp+arg_0]
0x10029087  push    ebx
0x10029088  push    esi
0x10029089  mov     esi, edx
0x1002908b  mov     [esp+8D4h+var_8B0], ecx
0x1002908f  mov     edx, [ebp+arg_4]
0x10029092  xor     ecx, ecx
0x10029094  mov     [esp+8D4h+CodePage], ecx
0x10029098  mov     [esp+8D4h+var_8B8], ecx
0x1002909c  mov     ebx, [esi+4]
0x1002909f  mov     [esp+8D4h+var_8A8], ecx
0x100290a3  mov     [esp+8D4h+var_8C4], ecx
0x100290a7  mov     ecx, edx
0x100290a9  mov     [esp+8D4h+var_8AC], eax
0x100290ad  mov     eax, [ebx+8]
0x100290b0  push    edi
0x100290b1  mov     [esp+8D8h+var_8BC], esi
0x100290b5  lea     edi, [ecx+2]
0x100290b8  mov     [esp+8D8h+var_8C0], edx
0x100290bc  mov     [esp+8D8h+var_8CC], ebx
0x100290c0  mov     [esp+8D8h+var_8B4], eax
0x100290c4  mov     ax, [ecx]
0x100290c7  add     ecx, 2
0x100290ca  cmp     ax, word ptr [esp+8D8h+CodePage]
0x100290cf  jnz     short loc_100290C4
0x100290d1  sub     ecx, edi
0x100290d3  sar     ecx, 1
0x100290d5  cmp     ecx, 40h ; '@'
0x100290d8  jbe     short loc_100290E4
0x100290da  mov     eax, 0FFFFFC16h
0x100290df  jmp     loc_10029530
0x100290e4  push    41h ; 'A'
0x100290e6  lea     ecx, [esp+8DCh+var_8A0]
0x100290ea  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100290ef  mov     ecx, [ebx+0Ch]
0x100290f2  lea     edx, [esp+8D8h+CodePage]
0x100290f6  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x100290fb  cmp     dword ptr [ebx+8], 1
0x100290ff  jnz     loc_1002930F
0x10029105  push    [esp+8D8h+CodePage]; CodePage
0x10029109  lea     edx, [esp+8DCh+var_608]
0x10029110  mov     [esp+8DCh+var_8B8], ebx
0x10029114  sub     esp, 10h
0x10029117  lea     ecx, [esp+8ECh+var_8A0]
0x1002911b  call    _MakeIntoValidFilename@28; MakeIntoValidFilename(x,x,x,x,x,x,x)
0x10029120  test    eax, eax
0x10029122  jnz     short loc_10029136
0x10029124  push    1
0x10029126  lea     edx, [esp+8DCh+var_8A0]
0x1002912a  mov     ecx, 0FFFFDFFAh
0x1002912f  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10029134  jmp     short loc_100290DA
0x10029136  lea     edx, [esp+8D8h+var_608]
0x1002913d  mov     ecx, ebx
0x1002913f  call    _ISAMDBLocateTable@8; ISAMDBLocateTable(x,x)
0x10029144  mov     edi, eax
0x10029146  mov     [esp+8D8h+var_8C4], edi
0x1002914a  test    edi, edi
0x1002914c  jnz     loc_10029354
0x10029152  push    105h
0x10029157  lea     edx, [ebx+48h]
0x1002915a  lea     ecx, [esp+8DCh+FullPath]
0x10029161  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10029166  push    105h
0x1002916b  lea     edx, [esp+8DCh+var_608]
0x10029172  lea     ecx, [esp+8DCh+FullPath]
0x10029179  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002917e  push    100h
0x10029183  lea     edx, [esp+8DCh+var_608]
0x1002918a  lea     ecx, [esp+8DCh+var_408]
0x10029191  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10029196  lea     ecx, [esp+8D8h+FullPath]; lpWideCharStr
0x1002919d  call    _DOSFileExists@4; DOSFileExists(x)
0x100291a2  test    eax, eax
0x100291a4  jz      loc_10029293
0x100291aa  cmp     eax, 0FFFFFFFDh
0x100291ad  jz      loc_10029276
0x100291b3  cmp     eax, 0FFFFFFFBh
0x100291b6  jz      loc_10029259
0x100291bc  push    0FFh; ExtCount
0x100291c1  lea     eax, [esp+8DCh+Ext]
0x100291c8  push    eax; Ext
0x100291c9  xor     eax, eax
0x100291cb  push    eax; FilenameCount
0x100291cc  push    eax; Filename
0x100291cd  push    eax; DirCount
0x100291ce  push    eax; Dir
0x100291cf  push    eax; DriveCount
0x100291d0  push    eax; Drive
0x100291d1  lea     eax, [esp+8F8h+FullPath]
0x100291d8  push    eax; FullPath
0x100291d9  call    ds:__imp___wsplitpath_s
0x100291df  add     esp, 24h
0x100291e2  cmp     [esp+8D8h+Ext], di
0x100291ea  jnz     short loc_1002923C
0x100291ec  imul    edx, [ebx+10h], 0Ah
0x100291f0  lea     ecx, [esp+8D8h+FullPath]
0x100291f7  push    105h
0x100291fc  add     edx, offset dword_1003C328
0x10029202  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029207  imul    edx, [ebx+10h], 0Ah
0x1002920b  lea     ecx, [esp+8D8h+var_408]
0x10029212  push    100h
0x10029217  add     edx, offset dword_1003C328
0x1002921d  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029222  lea     ecx, [esp+8D8h+FullPath]; lpWideCharStr
0x10029229  call    _DOSFileExists@4; DOSFileExists(x)
0x1002922e  test    eax, eax
0x10029230  jz      short loc_10029293
0x10029232  cmp     eax, 0FFFFFFFDh
0x10029235  jz      short loc_10029276
0x10029237  cmp     eax, 0FFFFFFFBh
0x1002923a  jz      short loc_10029259
0x1002923c  push    0
0x1002923e  lea     edx, [esp+8DCh+FullPath]
0x10029245  mov     ecx, 0FFFFDF94h
0x1002924a  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1002924f  mov     eax, 0FFFFFAE7h
0x10029254  jmp     loc_10029530
0x10029259  push    0
0x1002925b  lea     edx, [esp+8DCh+FullPath]
0x10029262  mov     ecx, 0FFFFE020h
0x10029267  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1002926c  mov     eax, 0FFFFFBF8h
0x10029271  jmp     loc_10029530
0x10029276  push    0
0x10029278  lea     edx, [esp+8DCh+FullPath]
0x1002927f  mov     ecx, 0FFFFE01Fh
0x10029284  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10029289  mov     eax, 0FFFFFC01h
0x1002928e  jmp     loc_10029530
0x10029293  push    dword ptr [ebx+40h]
0x10029296  mov     ebx, [esp+8DCh+var_8B0]
0x1002929a  lea     eax, [esp+8DCh+var_8A4]
0x1002929e  push    eax
0x1002929f  lea     eax, [esi+40h]
0x100292a2  push    eax
0x100292a3  lea     eax, [esp+8E4h+FullPath]
0x100292aa  push    eax
0x100292ab  push    dword ptr [ebx+0Ch]
0x100292ae  call    _WBISAMOpenDatabase@20; WBISAMOpenDatabase(x,x,x,x,x)
0x100292b3  test    eax, eax
0x100292b5  jnz     loc_10029530
0x100292bb  mov     eax, [ebx+4]
0x100292be  mov     ebx, [eax+8]
0x100292c1  mov     [esp+8D8h+var_8CC], ebx
0x100292c5  test    ebx, ebx
0x100292c7  jz      short loc_100292F5
0x100292c9  mov     eax, [esp+8D8h+var_8A4]
0x100292cd  mov     esi, [ebx+2Ch]
0x100292d0  mov     [esp+8D8h+var_8BC], esi
0x100292d4  test    esi, esi
0x100292d6  jz      short loc_100292EB
0x100292d8  cmp     [esi+10h], eax
0x100292db  jz      short loc_100292F1
0x100292dd  mov     esi, [esi]
0x100292df  mov     [esp+8D8h+var_8BC], esi
0x100292e3  test    esi, esi
0x100292e5  jnz     short loc_100292D8
0x100292e7  mov     [esp+8D8h+var_8BC], esi
0x100292eb  mov     ebx, [ebx]
0x100292ed  test    ebx, ebx
0x100292ef  jnz     short loc_100292CD
0x100292f1  mov     [esp+8D8h+var_8CC], ebx
0x100292f5  push    [esp+8D8h+CodePage]
0x100292f9  lea     edx, [esp+8DCh+var_8A0]
0x100292fd  push    41h ; 'A'
0x100292ff  lea     ecx, [esp+8E0h+var_408]
0x10029306  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1002930b  test    edi, edi
0x1002930d  jnz     short loc_10029354
0x1002930f  push    2
0x10029311  lea     eax, [esp+8DCh+var_8A8]
0x10029315  mov     ecx, esi
0x10029317  push    eax
0x10029318  lea     eax, [esp+8E0h+var_8C4]
0x1002931c  push    eax
0x1002931d  lea     edx, [esp+8E4h+var_8A0]
0x10029321  call    _LocateTableInDatabase@20; LocateTableInDatabase(x,x,x,x,x)
0x10029326  mov     edi, [esp+8D8h+var_8C4]
0x1002932a  mov     [esp+8D8h+CodePage], eax
0x1002932e  test    eax, eax
0x10029330  jnz     loc_100294D4
0x10029336  mov     edx, [esp+8D8h+var_8B4]
0x1002933a  cmp     edx, 1
0x1002933d  jnz     short loc_10029358
0x1002933f  mov     ecx, [esp+8D8h+var_8B8]
0x10029343  mov     eax, [ecx+30h]
0x10029346  mov     [edi], eax
0x10029348  mov     [ecx+30h], edi
0x1002934b  mov     dword ptr [ebx+30h], 0
0x10029352  jmp     short loc_10029358
0x10029354  mov     edx, [esp+8D8h+var_8B4]
0x10029358  mov     ebx, [ebp+arg_8]
0x1002935b  or      ebx, 4
0x1002935e  mov     [edi+4Ch], edx
0x10029361  test    byte ptr [esi+14h], 1
0x10029365  cmovz   ebx, [ebp+arg_8]
0x10029369  cmp     [ebp+arg_C], 0
0x1002936d  mov     [esp+8D8h+var_8B8], ebx
0x10029371  jnz     short loc_100293F1
0x10029373  push    2
0x10029375  pop     edx
0x10029376  mov     ecx, edi
0x10029378  call    AnyCursorHasOption
0x1002937d  cmp     eax, 1
0x10029380  jnz     short loc_1002939B
0x10029382  mov     edx, [esp+8D8h+var_8C0]
0x10029386  push    ecx
0x10029387  mov     ecx, 0FFFFE027h
0x1002938c  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x10029391  mov     ebx, 0FFFFFAEAh
0x10029396  jmp     loc_100294D8
0x1002939b  xor     edx, edx
0x1002939d  mov     ecx, edi
0x1002939f  inc     edx
0x100293a0  call    AnyCursorHasOption
0x100293a5  cmp     eax, 1
0x100293a8  jnz     short loc_100293B1
0x100293aa  cmp     ebx, 4
0x100293ad  jz      short loc_100293F1
0x100293af  jmp     short loc_10029382
0x100293b1  cmp     dword ptr [edi+14h], 0
0x100293b5  jnz     short loc_100293C3
0x100293b7  mov     ecx, edi
0x100293b9  call    AnyOverlappedTables
0x100293be  cmp     eax, 1
0x100293c1  jnz     short loc_100293F1
0x100293c3  test    bl, 2
0x100293c6  jz      short loc_100293E1
0x100293c8  mov     edx, [esp+8D8h+var_8C0]
0x100293cc  push    ecx
0x100293cd  mov     ecx, 0FFFFE026h
0x100293d2  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x100293d7  mov     ebx, 0FFFFFAE8h
0x100293dc  jmp     loc_100294D8
0x100293e1  test    bl, 1
0x100293e4  jz      short loc_100293F1
0x100293e6  mov     ecx, edi
0x100293e8  call    AllCursorsHaveOption
0x100293ed  test    eax, eax
0x100293ef  jz      short loc_100293C8
0x100293f1  cmp     dword ptr [edi+24h], 0
0x100293f5  jnz     short loc_1002940A
0x100293f7  mov     edx, edi
0x100293f9  mov     ecx, esi
0x100293fb  call    EngineOpenTable
0x10029400  mov     ebx, eax
0x10029402  test    ebx, ebx
0x10029404  js      loc_100294D8
0x1002940a  mov     edx, edi
0x1002940c  mov     ecx, esi
0x1002940e  call    _ISAMDBAddCursor@8; ISAMDBAddCursor(x,x)
0x10029413  mov     ebx, eax
0x10029415  test    ebx, ebx
0x10029417  jnz     short loc_10029423
0x10029419  mov     ebx, 0FFFFFC0Dh
0x1002941e  jmp     loc_100294D8
0x10029423  mov     eax, [esp+8D8h+var_8B8]
0x10029427  mov     [ebx+14h], eax
0x1002942a  mov     byte ptr [ebx+1Ch], 0
0x1002942e  test    eax, 80000h
0x10029433  jz      short loc_1002943C
0x10029435  mov     dword ptr [ebx+18h], 1
0x1002943c  test    al, 4
0x1002943e  jz      short loc_10029444
0x10029440  mov     byte ptr [ebx+1Ch], 1
0x10029444  xor     eax, eax
0x10029446  mov     byte ptr [ebx+1Dh], 2
0x1002944a  mov     [ebx+1Eh], eax
0x1002944d  cmp     dword ptr [edi+2Ch], 1
0x10029451  jnz     short loc_1002946D
0x10029453  mov     edx, [edi+10h]
0x10029456  mov     ecx, [edi+0Ch]
0x10029459  call    _WorkbookRangeRowCount@8; WorkbookRangeRowCount(x,x)
0x1002945e  cmp     eax, 1
0x10029461  jnz     short loc_10029469
0x10029463  mov     byte ptr [ebx+1Dh], 0
0x10029467  jmp     short loc_1002946D
0x10029469  inc     word ptr [ebx+1Eh]
0x1002946d  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10029473  mov     ecx, eax
0x10029475  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002947a  push    offset _TableEntryPoints
0x1002947f  push    dword ptr [ebx+0Ch]
0x10029482  mov     esi, [eax+1Ch]
0x10029485  mov     eax, [esp+8E0h+var_8B0]
0x10029489  push    [esp+8E0h+var_8AC]
0x1002948d  mov     esi, [esi+24h]
0x10029490  mov     ecx, esi
0x10029492  push    dword ptr [eax+0Ch]
0x10029495  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
  ... truncated ...
```
