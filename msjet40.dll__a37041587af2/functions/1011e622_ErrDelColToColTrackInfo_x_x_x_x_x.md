# ErrDelColToColTrackInfo(x,x,x,x,x)

- ea: `0x1011e622`
- end: `0x1011eb9f`
- name: `_ErrDelColToColTrackInfo@20`
- size: `1405`
- prototype: `int __thiscall(int, int, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x10114c50`

## callees

- `0x10012a80`
- `0x10012af0`
- `0x1002d380`
- `0x1002ed50`
- `0x10043890`
- `0x10044240`
- `0x10044a70`
- `0x10044d10`
- `0x1011ca40`
- `0x1011e432`
- `0x1011e622`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1011eb85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1011eb85`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011ea82`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011ea82`

## string_xrefs

- `0x1011e992`: `TempField*`

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
  TableColumnInfo = ErrGetColLinPosInfo(v21, v27, dword_101315EC[v25 / 4], &v23);
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
    v13 = (unsigned int)(dword_101315EC[v25 / 4] + 7) >> 3;
    v14 = _malloc(v13);
    v15 = v14;
    Block = v14;
    if ( !v14 )
      return -1011;
    memset(v14, 0, v13);
    memset(v15, 0, v13);
    if ( dword_101315F0[v25 / 4] )
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
      v17 = &dword_101315F0[v25 / 4];
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
  TableColumnInfo = ErrGetColLinPosInfo(v21, v27, dword_101315EC[v25 / 4], &Block);
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
0x1011e622  mov     edi, edi
0x1011e624  push    ebp
0x1011e625  mov     ebp, esp
0x1011e627  sub     esp, 340h
0x1011e62d  mov     eax, ___security_cookie
0x1011e632  xor     eax, ebp
0x1011e634  mov     [ebp+var_8], eax
0x1011e637  mov     eax, [ebp+arg_4]
0x1011e63a  push    ebx
0x1011e63b  push    esi
0x1011e63c  push    edi
0x1011e63d  mov     edi, ecx
0x1011e63f  mov     [ebp+var_33C], edx
0x1011e645  mov     ecx, [ebp+arg_0]
0x1011e648  imul    ebx, ecx, 64h ; 'd'
0x1011e64b  push    0Ch
0x1011e64d  push    4
0x1011e64f  mov     [ebp+Src], eax
0x1011e655  mov     eax, [ebp+arg_8]
0x1011e658  mov     [ebp+var_330], ebx
0x1011e65e  mov     ebx, _rgrepdbinfo[edx*4]
0x1011e665  lea     edx, [ebp+var_328]
0x1011e66b  push    edx
0x1011e66c  push    eax
0x1011e66d  push    ecx
0x1011e66e  push    edi
0x1011e66f  mov     [ebp+var_340], ecx
0x1011e675  mov     [ebp+var_338], 0
0x1011e67f  mov     [ebp+Block], 0
0x1011e689  mov     [ebp+var_328], 0FFFFFFFFh
0x1011e693  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011e698  mov     esi, eax
0x1011e69a  test    esi, esi
0x1011e69c  js      loc_1011EB8C
0x1011e6a2  cmp     [ebp+var_328], 0FFFFFFFFh
0x1011e6a9  jnz     short loc_1011E6B5
0x1011e6ab  mov     esi, 0FFFFFC15h
0x1011e6b0  jmp     loc_1011EB8C
0x1011e6b5  mov     ecx, [ebp+var_330]
0x1011e6bb  lea     eax, [ebp+var_338]
0x1011e6c1  push    eax
0x1011e6c2  push    dword_101315EC[ecx]
0x1011e6c8  push    [ebp+var_328]
0x1011e6ce  push    [ebp+var_340]
0x1011e6d4  call    _ErrGetColLinPosInfo@24; ErrGetColLinPosInfo(x,x,x,x,x,x)
0x1011e6d9  mov     esi, eax
0x1011e6db  test    esi, esi
0x1011e6dd  js      loc_1011EB8C
0x1011e6e3  push    offset _WZSchVersion; "SchemaVersion"
0x1011e6e8  push    dword ptr [ebx+4]
0x1011e6eb  push    edi
0x1011e6ec  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x1011e6f1  test    eax, eax
0x1011e6f3  js      loc_1011EB8E
0x1011e6f9  xor     esi, esi
0x1011e6fb  push    esi
0x1011e6fc  push    7FFFFFFFh
0x1011e701  push    dword ptr [ebx+4]
0x1011e704  push    edi
0x1011e705  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e70a  test    eax, eax
0x1011e70c  js      loc_1011EB8E
0x1011e712  push    esi
0x1011e713  push    esi
0x1011e714  lea     eax, [ebp+var_324]
0x1011e71a  push    eax
0x1011e71b  push    4
0x1011e71d  lea     eax, [ebp+var_320]
0x1011e723  push    eax
0x1011e724  push    dword ptr [ebx+40h]
0x1011e727  push    dword ptr [ebx+4]
0x1011e72a  push    edi
0x1011e72b  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e730  cmp     eax, 3ECh
0x1011e735  jnz     short loc_1011E741
0x1011e737  mov     eax, esi
0x1011e739  mov     [ebp+var_320], eax
0x1011e73f  jmp     short loc_1011E74F
0x1011e741  test    eax, eax
0x1011e743  js      loc_1011EB8E
0x1011e749  mov     eax, [ebp+var_320]
0x1011e74f  cmp     eax, 0Ch
0x1011e752  jnz     loc_1011E8AE
0x1011e758  push    esi
0x1011e759  push    esi
0x1011e75a  lea     eax, [ebp+var_324]
0x1011e760  push    eax
0x1011e761  push    81h
0x1011e766  lea     eax, [ebp+var_11C]
0x1011e76c  push    eax
0x1011e76d  push    dword ptr [ebx+50h]
0x1011e770  push    dword ptr [ebx+4]
0x1011e773  push    edi
0x1011e774  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e779  test    eax, eax
0x1011e77b  js      loc_1011EB8E
0x1011e781  mov     eax, [ebp+var_324]
0x1011e787  xor     ecx, ecx
0x1011e789  mov     edx, offset _WZColGeneration; "ColGeneration"
0x1011e78e  mov     [ebp+eax+var_11C], cx
0x1011e796  lea     ecx, [ebp+var_11C]
0x1011e79c  call    _WCSICMP@8; WCSICMP(x,x)
0x1011e7a1  test    eax, eax
0x1011e7a3  jnz     loc_1011EA6F
0x1011e7a9  push    esi
0x1011e7aa  push    0FFFFFFFFh
0x1011e7ac  push    dword ptr [ebx+4]
0x1011e7af  push    edi
0x1011e7b0  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e7b5  test    eax, eax
0x1011e7b7  js      loc_1011EB8E
0x1011e7bd  push    esi
0x1011e7be  push    esi
0x1011e7bf  lea     eax, [ebp+var_324]
0x1011e7c5  push    eax
0x1011e7c6  push    4
0x1011e7c8  lea     eax, [ebp+var_320]
0x1011e7ce  push    eax
0x1011e7cf  push    dword ptr [ebx+40h]
0x1011e7d2  push    dword ptr [ebx+4]
0x1011e7d5  push    edi
0x1011e7d6  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e7db  cmp     eax, 3ECh
0x1011e7e0  jnz     short loc_1011E7EC
0x1011e7e2  mov     eax, esi
0x1011e7e4  mov     [ebp+var_320], eax
0x1011e7ea  jmp     short loc_1011E7FA
0x1011e7ec  test    eax, eax
0x1011e7ee  js      loc_1011EB8E
0x1011e7f4  mov     eax, [ebp+var_320]
0x1011e7fa  cmp     eax, 5
0x1011e7fd  jnz     loc_1011EA6F
0x1011e803  push    esi
0x1011e804  push    0FFFFFFFFh
0x1011e806  push    dword ptr [ebx+4]
0x1011e809  push    edi
0x1011e80a  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e80f  test    eax, eax
0x1011e811  js      loc_1011EB8E
0x1011e817  push    esi
0x1011e818  push    esi
0x1011e819  lea     eax, [ebp+var_324]
0x1011e81f  push    eax
0x1011e820  push    4
0x1011e822  lea     eax, [ebp+var_320]
0x1011e828  push    eax
0x1011e829  push    dword ptr [ebx+40h]
0x1011e82c  push    dword ptr [ebx+4]
0x1011e82f  push    edi
0x1011e830  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e835  cmp     eax, 3ECh
0x1011e83a  jnz     short loc_1011E846
0x1011e83c  mov     eax, esi
0x1011e83e  mov     [ebp+var_320], eax
0x1011e844  jmp     short loc_1011E854
0x1011e846  test    eax, eax
0x1011e848  js      loc_1011EB8E
0x1011e84e  mov     eax, [ebp+var_320]
0x1011e854  cmp     eax, 4
0x1011e857  jnz     loc_1011EA6F
0x1011e85d  push    esi
0x1011e85e  push    0FFFFFFFFh
0x1011e860  push    dword ptr [ebx+4]
0x1011e863  push    edi
0x1011e864  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e869  test    eax, eax
0x1011e86b  js      loc_1011EB8E
0x1011e871  push    esi
0x1011e872  push    esi
0x1011e873  lea     eax, [ebp+var_324]
0x1011e879  push    eax
0x1011e87a  push    4
0x1011e87c  lea     eax, [ebp+var_320]
0x1011e882  push    eax
0x1011e883  push    dword ptr [ebx+40h]
0x1011e886  push    dword ptr [ebx+4]
0x1011e889  push    edi
0x1011e88a  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e88f  cmp     eax, 3ECh
0x1011e894  jnz     short loc_1011E8A0
0x1011e896  mov     eax, esi
0x1011e898  mov     [ebp+var_320], eax
0x1011e89e  jmp     short loc_1011E8AE
0x1011e8a0  test    eax, eax
0x1011e8a2  js      loc_1011EB8E
0x1011e8a8  mov     eax, [ebp+var_320]
0x1011e8ae  cmp     eax, 1Ch
0x1011e8b1  jnz     short loc_1011E904
0x1011e8b3  push    esi
0x1011e8b4  push    0FFFFFFFFh
0x1011e8b6  push    dword ptr [ebx+4]
0x1011e8b9  push    edi
0x1011e8ba  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x1011e8bf  test    eax, eax
0x1011e8c1  js      loc_1011EB8E
0x1011e8c7  push    esi
0x1011e8c8  push    esi
0x1011e8c9  lea     eax, [ebp+var_324]
0x1011e8cf  push    eax
0x1011e8d0  push    4
0x1011e8d2  lea     eax, [ebp+var_320]
0x1011e8d8  push    eax
0x1011e8d9  push    dword ptr [ebx+40h]
0x1011e8dc  push    dword ptr [ebx+4]
0x1011e8df  push    edi
0x1011e8e0  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e8e5  cmp     eax, 3ECh
0x1011e8ea  jnz     short loc_1011E8F6
0x1011e8ec  mov     eax, esi
0x1011e8ee  mov     [ebp+var_320], eax
0x1011e8f4  jmp     short loc_1011E904
0x1011e8f6  test    eax, eax
0x1011e8f8  js      loc_1011EB8E
0x1011e8fe  mov     eax, [ebp+var_320]
0x1011e904  cmp     eax, 4
0x1011e907  jnz     loc_1011EA6F
0x1011e90d  push    esi
0x1011e90e  push    esi
0x1011e90f  lea     eax, [ebp+var_324]
0x1011e915  push    eax
0x1011e916  push    1FFh
0x1011e91b  lea     eax, [ebp+var_31C]
0x1011e921  push    eax
0x1011e922  push    dword ptr [ebx+44h]
0x1011e925  push    dword ptr [ebx+4]
0x1011e928  push    edi
0x1011e929  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e92e  test    eax, eax
0x1011e930  js      loc_1011EB8E
0x1011e936  mov     eax, [ebp+var_324]
0x1011e93c  xor     ecx, ecx
0x1011e93e  mov     edx, [ebp+Src]
0x1011e944  mov     [ebp+eax+var_31C], cx
0x1011e94c  lea     ecx, [ebp+var_31C]
0x1011e952  call    _WCSICMP@8; WCSICMP(x,x)
0x1011e957  test    eax, eax
0x1011e959  jnz     loc_1011EA6F
0x1011e95f  push    esi
0x1011e960  push    esi
0x1011e961  lea     eax, [ebp+var_324]
0x1011e967  push    eax
0x1011e968  push    81h
0x1011e96d  lea     eax, [ebp+var_94]
0x1011e973  push    eax
0x1011e974  push    dword ptr [ebx+48h]
0x1011e977  push    dword ptr [ebx+4]
0x1011e97a  push    edi
0x1011e97b  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011e980  test    eax, eax
0x1011e982  js      loc_1011EB8E
0x1011e988  mov     eax, [ebp+var_324]
0x1011e98e  xor     ecx, ecx
0x1011e990  push    0Ah
0x1011e992  mov     edx, offset aTempfield; "TempField*"
0x1011e997  mov     [ebp+eax+var_94], cx
0x1011e99f  lea     ecx, [ebp+var_94]
0x1011e9a5  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1011e9aa  test    eax, eax
0x1011e9ac  jnz     loc_1011EA6F
0x1011e9b2  mov     ebx, [ebp+var_340]
0x1011e9b8  lea     eax, [ebp+var_328]
0x1011e9be  push    0Ch
0x1011e9c0  push    4
0x1011e9c2  push    eax
0x1011e9c3  lea     eax, [ebp+var_94]
0x1011e9c9  push    eax
0x1011e9ca  push    ebx
0x1011e9cb  push    edi
0x1011e9cc  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1011e9d1  mov     esi, eax
0x1011e9d3  test    esi, esi
0x1011e9d5  js      loc_1011EB8C
0x1011e9db  cmp     [ebp+var_328], 0FFFFFFFFh
0x1011e9e2  jz      loc_1011E6AB
0x1011e9e8  lea     eax, [ebp+Block]
0x1011e9ee  push    eax
0x1011e9ef  mov     eax, [ebp+var_330]
0x1011e9f5  push    dword_101315EC[eax]
0x1011e9fb  push    [ebp+var_328]
0x1011ea01  push    ebx
0x1011ea02  call    _ErrGetColLinPosInfo@24; ErrGetColLinPosInfo(x,x,x,x,x,x)
0x1011ea07  mov     esi, eax
0x1011ea09  test    esi, esi
0x1011ea0b  js      loc_1011EB8C
0x1011ea11  mov     esi, [ebp+var_33C]
0x1011ea17  lea     eax, [ebp+var_338]
0x1011ea1d  push    80h; int
0x1011ea22  push    4; int
0x1011ea24  push    4; Size
0x1011ea26  push    eax; void *
0x1011ea27  push    offset _WZColLinPosition; "ColLinPosition"
0x1011ea2c  lea     eax, [ebp+var_94]
0x1011ea32  push    eax; void *
0x1011ea33  push    [ebp+Src]; int
0x1011ea39  push    offset _wszTcObject; "Tables"
0x1011ea3e  push    esi; unsigned int
0x1011ea3f  push    edi; Session *
0x1011ea40  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x1011ea45  test    eax, eax
0x1011ea47  js      loc_1011EB8E
  ... truncated ...
```
