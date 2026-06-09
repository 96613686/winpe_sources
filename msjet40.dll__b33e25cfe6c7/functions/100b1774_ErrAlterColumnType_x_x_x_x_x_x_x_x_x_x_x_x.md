# ErrAlterColumnType(x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x100b1774`
- end: `0x100b1c76`
- name: `_ErrAlterColumnType@48`
- size: `1282`
- prototype: `int __fastcall(Session *, int, void *, int, int, _DWORD *, char, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x100cf9f4`

## callees

- `0x10015340`
- `0x10016ed0`
- `0x1001ea70`
- `0x10042f40`
- `0x10043660`
- `0x10043700`
- `0x100437d0`
- `0x10043840`
- `0x10043c10`
- `0x100440c0`
- `0x100441e0`
- `0x100447a0`
- `0x100448f0`
- `0x10044c00`
- `0x10044e00`
- `0x100a7c2e`
- `0x100b118b`
- `0x100b149d`
- `0x100b1546`
- `0x100b1774`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100b1c5c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100b1c5c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100b1b73`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100b1b73`

## string_xrefs

- `0x100b1a50`: ` tableid; UPDATE `

## pseudocode

```c
int __fastcall ErrAlterColumnType(
        Session *a1,
        int a2,
        void *a3,
        int a4,
        int a5,
        _DWORD *a6,
        char a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12)
{
  int result; // eax
  int v14; // eax
  int v15; // ecx
  int v16; // edx
  int v17; // eax
  int v18; // ecx
  int TableIndexes; // esi
  int v20; // eax
  int v21; // esi
  _BYTE v22[4]; // [esp+Ch] [ebp-454h] BYREF
  _DWORD *v23; // [esp+10h] [ebp-450h]
  int v24; // [esp+14h] [ebp-44Ch] BYREF
  int v25; // [esp+1Ch] [ebp-444h] BYREF
  void *Block; // [esp+20h] [ebp-440h] BYREF
  int v27; // [esp+24h] [ebp-43Ch] BYREF
  _BYTE v28[4]; // [esp+28h] [ebp-438h] BYREF
  int v29; // [esp+2Ch] [ebp-434h]
  int v30; // [esp+30h] [ebp-430h] BYREF
  int v31; // [esp+34h] [ebp-42Ch] BYREF
  _DWORD v32[15]; // [esp+38h] [ebp-428h] BYREF
  _DWORD v33[15]; // [esp+74h] [ebp-3ECh] BYREF
  _BYTE v34[4]; // [esp+B0h] [ebp-3B0h] BYREF
  int v35; // [esp+B4h] [ebp-3ACh]
  _BYTE v36[8]; // [esp+C8h] [ebp-398h] BYREF
  int v37; // [esp+D0h] [ebp-390h]
  int v38; // [esp+D4h] [ebp-38Ch]
  int v39; // [esp+D8h] [ebp-388h]
  int v40; // [esp+DCh] [ebp-384h]
  _DWORD v41[6]; // [esp+E0h] [ebp-380h] BYREF
  _BYTE v42[592]; // [esp+F8h] [ebp-368h] BYREF
  _BYTE v43[136]; // [esp+348h] [ebp-118h] BYREF
  _BYTE v44[140]; // [esp+3D0h] [ebp-90h] BYREF

  v30 = a2;
  v29 = a4;
  qmemcpy(v41, &a7, sizeof(v41));
  v23 = a6;
  v31 = -1;
  Block = 0;
  *a6 = 0;
  result = ErrDispGetTableColumnInfo(a1, a3, a4, v36, 24, 0);
  if ( result >= 0 )
  {
    v14 = v41[2];
    if ( v41[2] == 16 )
    {
      v15 = v41[3];
    }
    else
    {
      result = ErrSetLangInfo(v41, &v27);
      if ( result < 0 )
        return result;
      v15 = v41[3];
      if ( v27 )
        v15 = 1033;
      v14 = v41[2];
      v41[3] = v15;
    }
    v16 = v41[5] | 0x20;
    v41[5] |= 0x20u;
    if ( v37 == v14 && v39 == v41[4] && v38 == v15 && v40 == v16 )
    {
      *v23 = 1;
      return 0;
    }
    else if ( (v16 & 0x10) != 0
           && ((v40 & 0x10) != 0
            || (v17 = ErrDispMove2(a1, a3, 0x80000000, 0), v15 = v17 == -1603, Block = (void *)v15, v17 != -1603)) )
    {
      return -1511;
    }
    else
    {
      result = ErrUniqueName(v44, v15, 0);
      if ( result >= 0 )
      {
        result = ErrDispAddColumn((int)a1, (unsigned int)a3, (int)v44, (int)v41, 0, 0, (int)v22);
        if ( result >= 0 )
        {
          if ( (int)ErrDispGetTableColumnInfo(a1, a3, v29, &v31, 4, 3) >= 0 )
          {
            if ( (int)ErrDispGetTableColumnInfo(a1, v31, L"PresentationOrder", v34, 24, 0) >= 0 )
              ErrDispRetrieveColumn(a1, v31, v35, v28, 2, 0, 0, 0);
            ErrDispCloseTable(a1, v31);
          }
          if ( (int)ErrDispGetTableColumnInfo(a1, a3, v44, &v31, 4, 3) >= 0 )
          {
            if ( (int)ErrDispGetTableColumnInfo(a1, v31, L"PresentationOrder", v34, 24, 0) >= 0 )
            {
              ErrDispPrepareUpdate2(a1, v31, 2);
              ErrDispSetColumn(a1, v31, v35, v28, 2, 0, 0);
              ErrDispUpdate(a1, v31, 0, 0, 0);
            }
            ErrDispCloseTable(a1, v31);
          }
          if ( Block )
            goto LABEL_33;
          v27 = -1;
          result = ErrUniqueName(v43, v18, 0);
          if ( result >= 0 )
          {
            WCSCPY2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            WCSCAT2(295);
            v25 = 255;
            Block = a3;
            result = ErrTrySQLString(a1, v30, v42, &v25, 8, a5, 0, &v27);
            if ( result >= 0 )
            {
LABEL_33:
              v33[1] = -1;
              if ( a3 == (void *)-1 )
              {
                Block = v33;
                v24 = 60;
                result = ErrDispGetIndexInfo(a1, 0, 0, 0, &v24, 0);
              }
              else
              {
                result = ErrDispGetTableIndexInfo(a1, a3, 0, v33, 60, 0);
              }
              if ( result >= 0 )
              {
                v30 = 0;
                Block = _malloc(0);
                if ( Block )
                {
                  qmemcpy(v32, v33, sizeof(v32));
                  v20 = ErrDispMove2(a1, v32[1], 0x80000000, 0);
                  if ( v20 >= 0 )
                  {
                    v21 = v29;
                    do
                      v20 = ErrExamineOneIndex(v21, v32, &v30, &Block);
                    while ( v20 >= 0 );
                  }
                  TableIndexes = 0;
                  if ( v20 != -1603 )
                    TableIndexes = v20;
                  if ( TableIndexes >= 0 )
                  {
                    TableIndexes = ErrDispDeleteColumn(a1, a3, v29);
                    if ( TableIndexes >= 0 )
                    {
                      TableIndexes = ErrDispRenameColumn(a1, a3, v44, v29);
                      if ( TableIndexes >= 0 )
                      {
                        *v23 = 1;
                        if ( v30 )
                          TableIndexes = ErrReCreateTableIndexes(v30, Block);
                      }
                    }
                  }
                }
                else
                {
                  TableIndexes = -1011;
                }
                ErrDispCloseTable(a1, v33[1]);
                if ( Block )
                  _free(Block);
                return TableIndexes;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x100b1774  mov     edi, edi
0x100b1776  push    ebp
0x100b1777  mov     ebp, esp
0x100b1779  sub     esp, 454h
0x100b177f  mov     eax, ___security_cookie
0x100b1784  xor     eax, ebp
0x100b1786  mov     [ebp+var_4], eax
0x100b1789  mov     eax, [ebp+arg_4]
0x100b178c  push    ebx
0x100b178d  push    esi
0x100b178e  push    edi
0x100b178f  push    6
0x100b1791  mov     ebx, ecx
0x100b1793  mov     [ebp+var_430], edx
0x100b1799  mov     edx, [ebp+arg_C]
0x100b179c  lea     esi, [ebp+arg_10]
0x100b179f  pop     ecx
0x100b17a0  lea     edi, [ebp+var_380]
0x100b17a6  mov     [ebp+var_434], eax
0x100b17ac  rep movsd
0x100b17ae  mov     esi, [ebp+arg_0]
0x100b17b1  lea     ecx, [ebp+var_398]
0x100b17b7  xor     edi, edi
0x100b17b9  mov     [ebp+var_450], edx
0x100b17bf  push    edi
0x100b17c0  push    18h
0x100b17c2  push    ecx
0x100b17c3  push    eax
0x100b17c4  push    esi
0x100b17c5  push    ebx
0x100b17c6  mov     [ebp+var_42C], 0FFFFFFFFh
0x100b17d0  mov     [ebp+Block], edi
0x100b17d6  mov     [edx], edi
0x100b17d8  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b17dd  test    eax, eax
0x100b17df  js      loc_100B1C65
0x100b17e5  mov     eax, [ebp+var_378]
0x100b17eb  cmp     eax, 10h
0x100b17ee  jz      short loc_100B1835
0x100b17f0  mov     edx, [ebp+var_430]
0x100b17f6  lea     eax, [ebp+var_43C]
0x100b17fc  push    eax
0x100b17fd  lea     eax, [ebp+var_380]
0x100b1803  mov     ecx, ebx
0x100b1805  push    eax
0x100b1806  call    _ErrSetLangInfo@16; ErrSetLangInfo(x,x,x,x)
0x100b180b  test    eax, eax
0x100b180d  js      loc_100B1C65
0x100b1813  mov     ecx, [ebp+var_374]
0x100b1819  mov     eax, 409h
0x100b181e  cmp     [ebp+var_43C], edi
0x100b1824  cmovnz  ecx, eax
0x100b1827  mov     eax, [ebp+var_378]
0x100b182d  mov     [ebp+var_374], ecx
0x100b1833  jmp     short loc_100B183B
0x100b1835  mov     ecx, [ebp+var_374]
0x100b183b  mov     edx, [ebp+var_36C]
0x100b1841  or      edx, 20h
0x100b1844  mov     [ebp+var_36C], edx
0x100b184a  cmp     [ebp+var_390], eax
0x100b1850  jnz     short loc_100B1883
0x100b1852  mov     eax, [ebp+var_388]
0x100b1858  cmp     eax, [ebp+var_370]
0x100b185e  jnz     short loc_100B1883
0x100b1860  cmp     [ebp+var_38C], ecx
0x100b1866  jnz     short loc_100B1883
0x100b1868  cmp     [ebp+var_384], edx
0x100b186e  jnz     short loc_100B1883
0x100b1870  mov     eax, [ebp+var_450]
0x100b1876  mov     dword ptr [eax], 1
0x100b187c  xor     eax, eax
0x100b187e  jmp     loc_100B1C65
0x100b1883  test    dl, 10h
0x100b1886  jz      short loc_100B18BC
0x100b1888  test    byte ptr [ebp+var_384], 10h
0x100b188f  jnz     short loc_100B18B2
0x100b1891  push    edi
0x100b1892  push    80000000h
0x100b1897  push    esi
0x100b1898  push    ebx
0x100b1899  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100b189e  xor     ecx, ecx
0x100b18a0  mov     edx, 0FFFFF9BDh
0x100b18a5  cmp     eax, edx
0x100b18a7  setz    cl
0x100b18aa  mov     [ebp+Block], ecx
0x100b18b0  jz      short loc_100B18BC
0x100b18b2  mov     eax, 0FFFFFA19h
0x100b18b7  jmp     loc_100B1C65
0x100b18bc  push    edi
0x100b18bd  push    ecx
0x100b18be  lea     eax, [ebp+var_90]
0x100b18c4  mov     edx, offset aTmpcol; "TmpCol"
0x100b18c9  push    eax
0x100b18ca  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x100b18cf  test    eax, eax
0x100b18d1  js      loc_100B1C65
0x100b18d7  lea     eax, [ebp+var_454]
0x100b18dd  push    eax
0x100b18de  push    edi
0x100b18df  push    edi
0x100b18e0  lea     eax, [ebp+var_380]
0x100b18e6  push    eax
0x100b18e7  lea     eax, [ebp+var_90]
0x100b18ed  push    eax
0x100b18ee  push    esi
0x100b18ef  push    ebx
0x100b18f0  call    _ErrDispAddColumn@28; ErrDispAddColumn(x,x,x,x,x,x,x)
0x100b18f5  test    eax, eax
0x100b18f7  js      loc_100B1C65
0x100b18fd  mov     edi, [ebp+var_434]
0x100b1903  lea     eax, [ebp+var_42C]
0x100b1909  push    3
0x100b190b  push    4
0x100b190d  push    eax
0x100b190e  push    edi
0x100b190f  push    esi
0x100b1910  push    ebx
0x100b1911  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1916  test    eax, eax
0x100b1918  js      short loc_100B1966
0x100b191a  push    0
0x100b191c  push    18h
0x100b191e  lea     eax, [ebp+var_3B0]
0x100b1924  push    eax
0x100b1925  push    offset _wszSoPresentationOrder; "PresentationOrder"
0x100b192a  push    [ebp+var_42C]
0x100b1930  push    ebx
0x100b1931  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1936  test    eax, eax
0x100b1938  js      short loc_100B195A
0x100b193a  xor     eax, eax
0x100b193c  push    eax
0x100b193d  push    eax
0x100b193e  push    eax
0x100b193f  push    2
0x100b1941  lea     eax, [ebp+var_438]
0x100b1947  push    eax
0x100b1948  push    [ebp+var_3AC]
0x100b194e  push    [ebp+var_42C]
0x100b1954  push    ebx
0x100b1955  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100b195a  push    [ebp+var_42C]
0x100b1960  push    ebx
0x100b1961  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100b1966  push    3
0x100b1968  push    4
0x100b196a  lea     eax, [ebp+var_42C]
0x100b1970  push    eax
0x100b1971  lea     eax, [ebp+var_90]
0x100b1977  push    eax
0x100b1978  push    esi
0x100b1979  push    ebx
0x100b197a  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b197f  test    eax, eax
0x100b1981  js      short loc_100B19ED
0x100b1983  push    0
0x100b1985  push    18h
0x100b1987  lea     eax, [ebp+var_3B0]
0x100b198d  push    eax
0x100b198e  push    offset _wszSoPresentationOrder; "PresentationOrder"
0x100b1993  push    [ebp+var_42C]
0x100b1999  push    ebx
0x100b199a  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b199f  test    eax, eax
0x100b19a1  js      short loc_100B19E1
0x100b19a3  push    2
0x100b19a5  push    [ebp+var_42C]
0x100b19ab  push    ebx
0x100b19ac  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100b19b1  push    0
0x100b19b3  push    0
0x100b19b5  push    2
0x100b19b7  lea     eax, [ebp+var_438]
0x100b19bd  push    eax
0x100b19be  push    [ebp+var_3AC]
0x100b19c4  push    [ebp+var_42C]
0x100b19ca  push    ebx
0x100b19cb  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100b19d0  xor     eax, eax
0x100b19d2  push    eax
0x100b19d3  push    eax
0x100b19d4  push    eax
0x100b19d5  push    [ebp+var_42C]
0x100b19db  push    ebx
0x100b19dc  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100b19e1  push    [ebp+var_42C]
0x100b19e7  push    ebx
0x100b19e8  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100b19ed  cmp     [ebp+Block], 0
0x100b19f4  jnz     loc_100B1B1F
0x100b19fa  push    0
0x100b19fc  push    ecx
0x100b19fd  lea     eax, [ebp+var_118]
0x100b1a03  mov     [ebp+var_43C], 0FFFFFFFFh
0x100b1a0d  push    eax
0x100b1a0e  mov     edx, offset aTmptableidparm; "TmpTableIdParm"
0x100b1a13  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x100b1a18  test    eax, eax
0x100b1a1a  js      loc_100B1C65
0x100b1a20  push    127h
0x100b1a25  mov     edx, offset aParameters; "PARAMETERS "
0x100b1a2a  lea     ecx, [ebp+var_368]
0x100b1a30  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100b1a35  push    127h
0x100b1a3a  lea     edx, [ebp+var_118]
0x100b1a40  lea     ecx, [ebp+var_368]
0x100b1a46  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1a4b  push    127h
0x100b1a50  mov     edx, offset aTableidUpdate; " tableid; UPDATE "
0x100b1a55  lea     ecx, [ebp+var_368]
0x100b1a5b  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1a60  push    127h
0x100b1a65  lea     edx, [ebp+var_118]
0x100b1a6b  lea     ecx, [ebp+var_368]
0x100b1a71  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1a76  push    127h
0x100b1a7b  mov     edx, offset aSet; " SET "
0x100b1a80  lea     ecx, [ebp+var_368]
0x100b1a86  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1a8b  push    127h
0x100b1a90  lea     edx, [ebp+var_90]
0x100b1a96  lea     ecx, [ebp+var_368]
0x100b1a9c  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1aa1  push    127h
0x100b1aa6  mov     edx, offset asc_1000D160; " = ["
0x100b1aab  lea     ecx, [ebp+var_368]
0x100b1ab1  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1ab6  push    127h
0x100b1abb  mov     edx, edi
0x100b1abd  lea     ecx, [ebp+var_368]
0x100b1ac3  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1ac8  push    127h
0x100b1acd  mov     edx, offset asc_1000D16C; "]"
0x100b1ad2  lea     ecx, [ebp+var_368]
0x100b1ad8  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1add  lea     eax, [ebp+var_43C]
0x100b1ae3  mov     [ebp+var_444], 0FFh
0x100b1aed  push    eax
0x100b1aee  xor     edi, edi
0x100b1af0  mov     [ebp+Block], esi
0x100b1af6  push    edi
0x100b1af7  push    [ebp+arg_8]
0x100b1afa  lea     eax, [ebp+var_444]
0x100b1b00  push    8
0x100b1b02  push    eax
0x100b1b03  lea     eax, [ebp+var_368]
0x100b1b09  push    eax
0x100b1b0a  push    [ebp+var_430]
0x100b1b10  push    ebx
0x100b1b11  call    _ErrTrySQLString@32; ErrTrySQLString(x,x,x,x,x,x,x,x)
0x100b1b16  test    eax, eax
0x100b1b18  jns     short loc_100B1B21
0x100b1b1a  jmp     loc_100B1C65
0x100b1b1f  xor     edi, edi
0x100b1b21  mov     [ebp+var_3E8], 0FFFFFFFFh
0x100b1b2b  lea     eax, [ebp+var_3EC]
0x100b1b31  push    edi
0x100b1b32  cmp     esi, 0FFFFFFFFh
0x100b1b35  jz      short loc_100B1B44
0x100b1b37  push    3Ch ; '<'
0x100b1b39  push    eax
0x100b1b3a  push    edi
0x100b1b3b  push    esi
0x100b1b3c  push    ebx
0x100b1b3d  call    _ErrDispGetTableIndexInfo@24; ErrDispGetTableIndexInfo(x,x,x,x,x,x)
0x100b1b42  jmp     short loc_100B1B64
0x100b1b44  mov     [ebp+Block], eax
0x100b1b4a  lea     eax, [ebp+var_44C]
0x100b1b50  push    eax
0x100b1b51  push    edi
0x100b1b52  push    edi
0x100b1b53  push    edi
0x100b1b54  push    ebx
0x100b1b55  mov     [ebp+var_44C], 3Ch ; '<'
0x100b1b5f  call    _ErrDispGetIndexInfo@24; ErrDispGetIndexInfo(x,x,x,x,x,x)
0x100b1b64  test    eax, eax
0x100b1b66  js      loc_100B1C65
0x100b1b6c  push    edi; Size
0x100b1b6d  mov     [ebp+var_430], edi
0x100b1b73  call    ds:__imp__malloc
0x100b1b79  mov     [ebp+Block], eax
0x100b1b7f  pop     ecx
0x100b1b80  test    eax, eax
0x100b1b82  jnz     short loc_100B1B8E
0x100b1b84  mov     esi, 0FFFFFC0Dh
0x100b1b89  jmp     loc_100B1C45
0x100b1b8e  push    0Fh
0x100b1b90  pop     ecx
0x100b1b91  push    0
0x100b1b93  push    80000000h
0x100b1b98  lea     esi, [ebp+var_3EC]
0x100b1b9e  lea     edi, [ebp+var_428]
0x100b1ba4  rep movsd
0x100b1ba6  push    [ebp+var_424]
0x100b1bac  push    ebx
0x100b1bad  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100b1bb2  mov     edi, [ebp+arg_0]
0x100b1bb5  test    eax, eax
0x100b1bb7  js      short loc_100B1BE2
  ... truncated ...
```
