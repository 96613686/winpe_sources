# ErrDelColToColTrackInfo(x,x,x,x,x)

- ea: `0x1011e474`
- end: `0x1011e9f1`
- name: `_ErrDelColToColTrackInfo@20`
- size: `1405`
- prototype: `int __thiscall(int, int, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x10114aa0`

## callees

- `0x10012940`
- `0x100129b0`
- `0x1002d1d0`
- `0x1002ebb0`
- `0x10043700`
- `0x100440c0`
- `0x100448f0`
- `0x10044b90`
- `0x1011c890`
- `0x1011e284`
- `0x1011e474`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1011e9d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1011e9d7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011e8d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011e8d4`

## string_xrefs

- `0x1011e7e4`: `TempField*`

## pseudocode

```c
int __fastcall ErrDelColToColTrackInfo(Session *a1, unsigned int a2, int a3, void *a4, int a5)
{
  _DWORD *v6; // ebx
  int TableColumnInfo; // esi
  int result; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  void *v12; // edx
  unsigned int v13; // ebx
  void *v14; // eax
  void *v15; // esi
  unsigned int v16; // ebx
  int *v17; // eax
  unsigned int v18; // [esp-24h] [ebp-370h]
  void *v19; // [esp-1Ch] [ebp-368h]
  size_t v20; // [esp-Ch] [ebp-358h]
  int v21; // [esp+Ch] [ebp-340h] BYREF
  unsigned int v22; // [esp+10h] [ebp-33Ch]
  unsigned int v23; // [esp+14h] [ebp-338h] BYREF
  void *Block; // [esp+18h] [ebp-334h] BYREF
  unsigned int v25; // [esp+1Ch] [ebp-330h]
  void *Src; // [esp+20h] [ebp-32Ch]
  int v27; // [esp+24h] [ebp-328h] BYREF
  int v28; // [esp+28h] [ebp-324h] BYREF
  int v29; // [esp+2Ch] [ebp-320h] BYREF
  _WORD v30[256]; // [esp+30h] [ebp-31Ch] BYREF
  _WORD v31[68]; // [esp+230h] [ebp-11Ch] BYREF
  _WORD v32[70]; // [esp+2B8h] [ebp-94h] BYREF

  v22 = a2;
  Src = a4;
  v25 = 100 * a3;
  v6 = *(&rgrepdbinfo + a2);
  v21 = a3;
  v23 = 0;
  Block = 0;
  v27 = -1;
  TableColumnInfo = ErrDispGetTableColumnInfo(a1, a3, a5, &v27, 4, 12);
  if ( TableColumnInfo < 0 )
    return TableColumnInfo;
  if ( v27 == -1 )
    return -1003;
  TableColumnInfo = ErrGetColLinPosInfo(v21, v27, dword_1013154C[v25 / 4], &v23);
  if ( TableColumnInfo < 0 )
    return TableColumnInfo;
  result = ErrDispSetCurrentIndex(a1, v6[1], L"SchemaVersion");
  if ( result < 0 )
    return result;
  result = ErrDispMove2(a1, v6[1], 0x7FFFFFFF, 0);
  if ( result < 0 )
    return result;
  result = ErrDispRetrieveColumn(a1, v6[1], v6[16], &v29, 4, &v28, 0, 0);
  if ( result == 1004 )
  {
    v9 = 0;
    v29 = 0;
  }
  else
  {
    if ( result < 0 )
      return result;
    v9 = v29;
  }
  if ( v9 == 12 )
  {
    result = ErrDispRetrieveColumn(a1, v6[1], v6[20], v31, 129, &v28, 0, 0);
    if ( result < 0 )
      return result;
    *(_WORD *)((char *)v31 + v28) = 0;
    if ( WCSICMP(v31, L"ColGeneration") )
      goto LABEL_48;
    result = ErrDispMove2(a1, v6[1], -1, 0);
    if ( result < 0 )
      return result;
    result = ErrDispRetrieveColumn(a1, v6[1], v6[16], &v29, 4, &v28, 0, 0);
    if ( result == 1004 )
    {
      v10 = 0;
      v29 = 0;
    }
    else
    {
      if ( result < 0 )
        return result;
      v10 = v29;
    }
    if ( v10 != 5 )
      goto LABEL_48;
    result = ErrDispMove2(a1, v6[1], -1, 0);
    if ( result < 0 )
      return result;
    result = ErrDispRetrieveColumn(a1, v6[1], v6[16], &v29, 4, &v28, 0, 0);
    if ( result == 1004 )
    {
      v11 = 0;
      v29 = 0;
    }
    else
    {
      if ( result < 0 )
        return result;
      v11 = v29;
    }
    if ( v11 != 4 )
      goto LABEL_48;
    result = ErrDispMove2(a1, v6[1], -1, 0);
    if ( result < 0 )
      return result;
    result = ErrDispRetrieveColumn(a1, v6[1], v6[16], &v29, 4, &v28, 0, 0);
    if ( result == 1004 )
    {
      v9 = 0;
      v29 = 0;
    }
    else
    {
      if ( result < 0 )
        return result;
      v9 = v29;
    }
  }
  if ( v9 == 28 )
  {
    result = ErrDispMove2(a1, v6[1], -1, 0);
    if ( result < 0 )
      return result;
    result = ErrDispRetrieveColumn(a1, v6[1], v6[16], &v29, 4, &v28, 0, 0);
    if ( result == 1004 )
    {
      v9 = 0;
      v29 = 0;
    }
    else
    {
      if ( result < 0 )
        return result;
      v9 = v29;
    }
  }
  if ( v9 != 4 )
    goto LABEL_48;
  result = ErrDispRetrieveColumn(a1, v6[1], v6[17], v30, 511, &v28, 0, 0);
  if ( result < 0 )
    return result;
  v12 = Src;
  *(_WORD *)((char *)v30 + v28) = 0;
  if ( WCSICMP(v30, v12) )
    goto LABEL_48;
  result = ErrDispRetrieveColumn(a1, v6[1], v6[18], v32, 129, &v28, 0, 0);
  if ( result < 0 )
    return result;
  *(_WORD *)((char *)v32 + v28) = 0;
  if ( WCSNICMP(10) )
  {
LABEL_48:
    v13 = (unsigned int)(dword_1013154C[v25 / 4] + 7) >> 3;
    v14 = _malloc(v13);
    v15 = v14;
    Block = v14;
    if ( !v14 )
      return -1011;
    memset(v14, 0, v13);
    memset(v15, 0, v13);
    if ( dword_10131550[v25 / 4] )
    {
      TableColumnInfo = JetIRetrieveProperty(
                          (int)a1,
                          v22,
                          (int)L"Tables",
                          Src,
                          0,
                          (int)L"MissingColumnsBitmap",
                          (int)v15,
                          v13,
                          (int)&v28,
                          (int)&v21,
                          128,
                          0);
      if ( TableColumnInfo < 0 )
      {
LABEL_55:
        _free(Block);
        return TableColumnInfo;
      }
      v15 = Block;
    }
    v20 = v13;
    v16 = v22;
    v19 = Src;
    v18 = v22;
    *((_BYTE *)v15 + (v23 >> 3)) |= 128 >> (v23 & 7);
    TableColumnInfo = JetISetProperty(a1, v18, (int)L"Tables", (int)v19, 0, L"MissingColumnsBitmap", v15, v20, 11, 128);
    if ( TableColumnInfo >= 0 )
    {
      v17 = &dword_10131550[v25 / 4];
      ++*v17;
      TableColumnInfo = JetISetProperty(a1, v16, (int)L"Tables", (int)Src, 0, L"CColumnsMissing", v17, 4u, 4, 128);
    }
    goto LABEL_55;
  }
  TableColumnInfo = ErrDispGetTableColumnInfo(a1, v21, v32, &v27, 4, 12);
  if ( TableColumnInfo < 0 )
    return TableColumnInfo;
  if ( v27 == -1 )
    return -1003;
  TableColumnInfo = ErrGetColLinPosInfo(v21, v27, dword_1013154C[v25 / 4], &Block);
  if ( TableColumnInfo < 0 )
    return TableColumnInfo;
  result = JetISetProperty(a1, v22, (int)L"Tables", (int)Src, v32, L"ColLinPosition", &v23, 4u, 4, 128);
  if ( result >= 0 )
  {
    result = ErrBldColidPosList(a1, v22, v21, Src);
    if ( result >= 0 )
    {
      v23 = (unsigned int)Block;
      goto LABEL_48;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1011e474  mov     edi, edi
0x1011e476  push    ebp
0x1011e477  mov     ebp, esp
0x1011e479  sub     esp, 340h
0x1011e47f  mov     eax, ___security_cookie
0x1011e484  xor     eax, ebp
0x1011e486  mov     [ebp+var_8], eax
0x1011e489  mov     eax, [ebp+arg_4]
0x1011e48c  push    ebx
0x1011e48d  push    esi
0x1011e48e  push    edi
0x1011e48f  mov     edi, ecx
0x1011e491  mov     [ebp+var_33C], edx
0x1011e497  mov     ecx, [ebp+arg_0]
0x1011e49a  imul    ebx, ecx, 64h ; 'd'
0x1011e49d  push    0Ch
0x1011e49f  push    4
0x1011e4a1  mov     [ebp+Src], eax
0x1011e4a7  mov     eax, [ebp+arg_8]
0x1011e4aa  mov     [ebp+var_330], ebx
0x1011e4b0  mov     ebx, _rgrepdbinfo[edx*4]
0x1011e4b7  lea     edx, [ebp+var_328]
0x1011e4bd  push    edx
0x1011e4be  push    eax
0x1011e4bf  push    ecx
0x1011e4c0  push    edi
0x1011e4c1  mov     [ebp+var_340], ecx
0x1011e4c7  mov     [ebp+var_338], 0
0x1011e4d1  mov     [ebp+Block], 0
0x1011e4db  mov     [ebp+var_328], 0FFFFFFFFh
0x1011e4e5  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011e4ea  mov     esi, eax
0x1011e4ec  test    esi, esi
0x1011e4ee  js      loc_1011E9DE
0x1011e4f4  cmp     [ebp+var_328], 0FFFFFFFFh
0x1011e4fb  jnz     short loc_1011E507
0x1011e4fd  mov     esi, 0FFFFFC15h
0x1011e502  jmp     loc_1011E9DE
0x1011e507  mov     ecx, [ebp+var_330]
0x1011e50d  lea     eax, [ebp+var_338]
0x1011e513  push    eax
0x1011e514  push    dword_1013154C[ecx]
0x1011e51a  push    [ebp+var_328]
0x1011e520  push    [ebp+var_340]
0x1011e526  call    _ErrGetColLinPosInfo@24; ErrGetColLinPosInfo(x,x,x,x,x,x)
0x1011e52b  mov     esi, eax
0x1011e52d  test    esi, esi
0x1011e52f  js      loc_1011E9DE
0x1011e535  push    offset _WZSchVersion; "SchemaVersion"
0x1011e53a  push    dword ptr [ebx+4]
0x1011e53d  push    edi
0x1011e53e  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1011e543  test    eax, eax
0x1011e545  js      loc_1011E9E0
0x1011e54b  xor     esi, esi
0x1011e54d  push    esi
0x1011e54e  push    7FFFFFFFh
0x1011e553  push    dword ptr [ebx+4]
0x1011e556  push    edi
0x1011e557  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e55c  test    eax, eax
0x1011e55e  js      loc_1011E9E0
0x1011e564  push    esi
0x1011e565  push    esi
0x1011e566  lea     eax, [ebp+var_324]
0x1011e56c  push    eax
0x1011e56d  push    4
0x1011e56f  lea     eax, [ebp+var_320]
0x1011e575  push    eax
0x1011e576  push    dword ptr [ebx+40h]
0x1011e579  push    dword ptr [ebx+4]
0x1011e57c  push    edi
0x1011e57d  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e582  cmp     eax, 3ECh
0x1011e587  jnz     short loc_1011E593
0x1011e589  mov     eax, esi
0x1011e58b  mov     [ebp+var_320], eax
0x1011e591  jmp     short loc_1011E5A1
0x1011e593  test    eax, eax
0x1011e595  js      loc_1011E9E0
0x1011e59b  mov     eax, [ebp+var_320]
0x1011e5a1  cmp     eax, 0Ch
0x1011e5a4  jnz     loc_1011E700
0x1011e5aa  push    esi
0x1011e5ab  push    esi
0x1011e5ac  lea     eax, [ebp+var_324]
0x1011e5b2  push    eax
0x1011e5b3  push    81h
0x1011e5b8  lea     eax, [ebp+var_11C]
0x1011e5be  push    eax
0x1011e5bf  push    dword ptr [ebx+50h]
0x1011e5c2  push    dword ptr [ebx+4]
0x1011e5c5  push    edi
0x1011e5c6  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e5cb  test    eax, eax
0x1011e5cd  js      loc_1011E9E0
0x1011e5d3  mov     eax, [ebp+var_324]
0x1011e5d9  xor     ecx, ecx
0x1011e5db  mov     edx, offset _WZColGeneration; "ColGeneration"
0x1011e5e0  mov     [ebp+eax+var_11C], cx
0x1011e5e8  lea     ecx, [ebp+var_11C]
0x1011e5ee  call    _WCSICMP@8; WCSICMP(x,x)
0x1011e5f3  test    eax, eax
0x1011e5f5  jnz     loc_1011E8C1
0x1011e5fb  push    esi
0x1011e5fc  push    0FFFFFFFFh
0x1011e5fe  push    dword ptr [ebx+4]
0x1011e601  push    edi
0x1011e602  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e607  test    eax, eax
0x1011e609  js      loc_1011E9E0
0x1011e60f  push    esi
0x1011e610  push    esi
0x1011e611  lea     eax, [ebp+var_324]
0x1011e617  push    eax
0x1011e618  push    4
0x1011e61a  lea     eax, [ebp+var_320]
0x1011e620  push    eax
0x1011e621  push    dword ptr [ebx+40h]
0x1011e624  push    dword ptr [ebx+4]
0x1011e627  push    edi
0x1011e628  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e62d  cmp     eax, 3ECh
0x1011e632  jnz     short loc_1011E63E
0x1011e634  mov     eax, esi
0x1011e636  mov     [ebp+var_320], eax
0x1011e63c  jmp     short loc_1011E64C
0x1011e63e  test    eax, eax
0x1011e640  js      loc_1011E9E0
0x1011e646  mov     eax, [ebp+var_320]
0x1011e64c  cmp     eax, 5
0x1011e64f  jnz     loc_1011E8C1
0x1011e655  push    esi
0x1011e656  push    0FFFFFFFFh
0x1011e658  push    dword ptr [ebx+4]
0x1011e65b  push    edi
0x1011e65c  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e661  test    eax, eax
0x1011e663  js      loc_1011E9E0
0x1011e669  push    esi
0x1011e66a  push    esi
0x1011e66b  lea     eax, [ebp+var_324]
0x1011e671  push    eax
0x1011e672  push    4
0x1011e674  lea     eax, [ebp+var_320]
0x1011e67a  push    eax
0x1011e67b  push    dword ptr [ebx+40h]
0x1011e67e  push    dword ptr [ebx+4]
0x1011e681  push    edi
0x1011e682  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e687  cmp     eax, 3ECh
0x1011e68c  jnz     short loc_1011E698
0x1011e68e  mov     eax, esi
0x1011e690  mov     [ebp+var_320], eax
0x1011e696  jmp     short loc_1011E6A6
0x1011e698  test    eax, eax
0x1011e69a  js      loc_1011E9E0
0x1011e6a0  mov     eax, [ebp+var_320]
0x1011e6a6  cmp     eax, 4
0x1011e6a9  jnz     loc_1011E8C1
0x1011e6af  push    esi
0x1011e6b0  push    0FFFFFFFFh
0x1011e6b2  push    dword ptr [ebx+4]
0x1011e6b5  push    edi
0x1011e6b6  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e6bb  test    eax, eax
0x1011e6bd  js      loc_1011E9E0
0x1011e6c3  push    esi
0x1011e6c4  push    esi
0x1011e6c5  lea     eax, [ebp+var_324]
0x1011e6cb  push    eax
0x1011e6cc  push    4
0x1011e6ce  lea     eax, [ebp+var_320]
0x1011e6d4  push    eax
0x1011e6d5  push    dword ptr [ebx+40h]
0x1011e6d8  push    dword ptr [ebx+4]
0x1011e6db  push    edi
0x1011e6dc  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e6e1  cmp     eax, 3ECh
0x1011e6e6  jnz     short loc_1011E6F2
0x1011e6e8  mov     eax, esi
0x1011e6ea  mov     [ebp+var_320], eax
0x1011e6f0  jmp     short loc_1011E700
0x1011e6f2  test    eax, eax
0x1011e6f4  js      loc_1011E9E0
0x1011e6fa  mov     eax, [ebp+var_320]
0x1011e700  cmp     eax, 1Ch
0x1011e703  jnz     short loc_1011E756
0x1011e705  push    esi
0x1011e706  push    0FFFFFFFFh
0x1011e708  push    dword ptr [ebx+4]
0x1011e70b  push    edi
0x1011e70c  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e711  test    eax, eax
0x1011e713  js      loc_1011E9E0
0x1011e719  push    esi
0x1011e71a  push    esi
0x1011e71b  lea     eax, [ebp+var_324]
0x1011e721  push    eax
0x1011e722  push    4
0x1011e724  lea     eax, [ebp+var_320]
0x1011e72a  push    eax
0x1011e72b  push    dword ptr [ebx+40h]
0x1011e72e  push    dword ptr [ebx+4]
0x1011e731  push    edi
0x1011e732  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e737  cmp     eax, 3ECh
0x1011e73c  jnz     short loc_1011E748
0x1011e73e  mov     eax, esi
0x1011e740  mov     [ebp+var_320], eax
0x1011e746  jmp     short loc_1011E756
0x1011e748  test    eax, eax
0x1011e74a  js      loc_1011E9E0
0x1011e750  mov     eax, [ebp+var_320]
0x1011e756  cmp     eax, 4
0x1011e759  jnz     loc_1011E8C1
0x1011e75f  push    esi
0x1011e760  push    esi
0x1011e761  lea     eax, [ebp+var_324]
0x1011e767  push    eax
0x1011e768  push    1FFh
0x1011e76d  lea     eax, [ebp+var_31C]
0x1011e773  push    eax
0x1011e774  push    dword ptr [ebx+44h]
0x1011e777  push    dword ptr [ebx+4]
0x1011e77a  push    edi
0x1011e77b  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e780  test    eax, eax
0x1011e782  js      loc_1011E9E0
0x1011e788  mov     eax, [ebp+var_324]
0x1011e78e  xor     ecx, ecx
0x1011e790  mov     edx, [ebp+Src]
0x1011e796  mov     [ebp+eax+var_31C], cx
0x1011e79e  lea     ecx, [ebp+var_31C]
0x1011e7a4  call    _WCSICMP@8; WCSICMP(x,x)
0x1011e7a9  test    eax, eax
0x1011e7ab  jnz     loc_1011E8C1
0x1011e7b1  push    esi
0x1011e7b2  push    esi
0x1011e7b3  lea     eax, [ebp+var_324]
0x1011e7b9  push    eax
0x1011e7ba  push    81h
0x1011e7bf  lea     eax, [ebp+var_94]
0x1011e7c5  push    eax
0x1011e7c6  push    dword ptr [ebx+48h]
0x1011e7c9  push    dword ptr [ebx+4]
0x1011e7cc  push    edi
0x1011e7cd  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e7d2  test    eax, eax
0x1011e7d4  js      loc_1011E9E0
0x1011e7da  mov     eax, [ebp+var_324]
0x1011e7e0  xor     ecx, ecx
0x1011e7e2  push    0Ah
0x1011e7e4  mov     edx, offset aTempfield; "TempField*"
0x1011e7e9  mov     [ebp+eax+var_94], cx
0x1011e7f1  lea     ecx, [ebp+var_94]
0x1011e7f7  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1011e7fc  test    eax, eax
0x1011e7fe  jnz     loc_1011E8C1
0x1011e804  mov     ebx, [ebp+var_340]
0x1011e80a  lea     eax, [ebp+var_328]
0x1011e810  push    0Ch
0x1011e812  push    4
0x1011e814  push    eax
0x1011e815  lea     eax, [ebp+var_94]
0x1011e81b  push    eax
0x1011e81c  push    ebx
0x1011e81d  push    edi
0x1011e81e  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011e823  mov     esi, eax
0x1011e825  test    esi, esi
0x1011e827  js      loc_1011E9DE
0x1011e82d  cmp     [ebp+var_328], 0FFFFFFFFh
0x1011e834  jz      loc_1011E4FD
0x1011e83a  lea     eax, [ebp+Block]
0x1011e840  push    eax
0x1011e841  mov     eax, [ebp+var_330]
0x1011e847  push    dword_1013154C[eax]
0x1011e84d  push    [ebp+var_328]
0x1011e853  push    ebx
0x1011e854  call    _ErrGetColLinPosInfo@24; ErrGetColLinPosInfo(x,x,x,x,x,x)
0x1011e859  mov     esi, eax
0x1011e85b  test    esi, esi
0x1011e85d  js      loc_1011E9DE
0x1011e863  mov     esi, [ebp+var_33C]
0x1011e869  lea     eax, [ebp+var_338]
0x1011e86f  push    80h; int
0x1011e874  push    4; int
0x1011e876  push    4; Size
0x1011e878  push    eax; void *
0x1011e879  push    offset _WZColLinPosition; "ColLinPosition"
0x1011e87e  lea     eax, [ebp+var_94]
0x1011e884  push    eax; void *
0x1011e885  push    [ebp+Src]; int
0x1011e88b  push    offset _wszTcObject; "Tables"
0x1011e890  push    esi; unsigned int
0x1011e891  push    edi; Session *
0x1011e892  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x1011e897  test    eax, eax
0x1011e899  js      loc_1011E9E0
  ... truncated ...
```
