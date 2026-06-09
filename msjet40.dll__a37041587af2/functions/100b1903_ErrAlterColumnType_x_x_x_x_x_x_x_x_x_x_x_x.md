# ErrAlterColumnType(x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x100b1903`
- end: `0x100b1e05`
- name: `_ErrAlterColumnType@48`
- size: `1282`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x100cfb84`

## callees

- `0x10015480`
- `0x10017010`
- `0x1001ebc0`
- `0x100430d0`
- `0x100437f0`
- `0x10043890`
- `0x10043960`
- `0x100439d0`
- `0x10043da0`
- `0x10044240`
- `0x10044360`
- `0x10044920`
- `0x10044a70`
- `0x10044d80`
- `0x10044f80`
- `0x100a7dbe`
- `0x100b131a`
- `0x100b162c`
- `0x100b16d5`
- `0x100b1903`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100b1deb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100b1deb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100b1d02`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100b1d02`

## string_xrefs

- `0x100b1bdf`: ` tableid; UPDATE `

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
  unsigned __int16 v43[68]; // [esp+348h] [ebp-118h] BYREF
  unsigned __int16 v44[70]; // [esp+3D0h] [ebp-90h] BYREF

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
      result = ErrUniqueName(v15, (int)L"TmpCol", v44, v15, 0);
      if ( result >= 0 )
      {
        result = ErrDispAddColumn(a1, a3, v44, v41, 0, 0, v22);
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
          result = ErrUniqueName(v18, (int)L"TmpTableIdParm", v43, v18, 0);
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
0x100b1903  mov     edi, edi
0x100b1905  push    ebp
0x100b1906  mov     ebp, esp
0x100b1908  sub     esp, 454h
0x100b190e  mov     eax, ___security_cookie
0x100b1913  xor     eax, ebp
0x100b1915  mov     [ebp+var_4], eax
0x100b1918  mov     eax, [ebp+arg_4]
0x100b191b  push    ebx
0x100b191c  push    esi
0x100b191d  push    edi
0x100b191e  push    6
0x100b1920  mov     ebx, ecx
0x100b1922  mov     [ebp+var_430], edx
0x100b1928  mov     edx, [ebp+arg_C]
0x100b192b  lea     esi, [ebp+arg_10]
0x100b192e  pop     ecx
0x100b192f  lea     edi, [ebp+var_380]
0x100b1935  mov     [ebp+var_434], eax
0x100b193b  rep movsd
0x100b193d  mov     esi, [ebp+arg_0]
0x100b1940  lea     ecx, [ebp+var_398]
0x100b1946  xor     edi, edi
0x100b1948  mov     [ebp+var_450], edx
0x100b194e  push    edi
0x100b194f  push    18h
0x100b1951  push    ecx
0x100b1952  push    eax
0x100b1953  push    esi
0x100b1954  push    ebx
0x100b1955  mov     [ebp+var_42C], 0FFFFFFFFh
0x100b195f  mov     [ebp+Block], edi
0x100b1965  mov     [edx], edi
0x100b1967  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b196c  test    eax, eax
0x100b196e  js      loc_100B1DF4
0x100b1974  mov     eax, [ebp+var_378]
0x100b197a  cmp     eax, 10h
0x100b197d  jz      short loc_100B19C4
0x100b197f  mov     edx, [ebp+var_430]
0x100b1985  lea     eax, [ebp+var_43C]
0x100b198b  push    eax
0x100b198c  lea     eax, [ebp+var_380]
0x100b1992  mov     ecx, ebx
0x100b1994  push    eax
0x100b1995  call    _ErrSetLangInfo@16; ErrSetLangInfo(x,x,x,x)
0x100b199a  test    eax, eax
0x100b199c  js      loc_100B1DF4
0x100b19a2  mov     ecx, [ebp+var_374]
0x100b19a8  mov     eax, 409h
0x100b19ad  cmp     [ebp+var_43C], edi
0x100b19b3  cmovnz  ecx, eax
0x100b19b6  mov     eax, [ebp+var_378]
0x100b19bc  mov     [ebp+var_374], ecx
0x100b19c2  jmp     short loc_100B19CA
0x100b19c4  mov     ecx, [ebp+var_374]
0x100b19ca  mov     edx, [ebp+var_36C]
0x100b19d0  or      edx, 20h
0x100b19d3  mov     [ebp+var_36C], edx
0x100b19d9  cmp     [ebp+var_390], eax
0x100b19df  jnz     short loc_100B1A12
0x100b19e1  mov     eax, [ebp+var_388]
0x100b19e7  cmp     eax, [ebp+var_370]
0x100b19ed  jnz     short loc_100B1A12
0x100b19ef  cmp     [ebp+var_38C], ecx
0x100b19f5  jnz     short loc_100B1A12
0x100b19f7  cmp     [ebp+var_384], edx
0x100b19fd  jnz     short loc_100B1A12
0x100b19ff  mov     eax, [ebp+var_450]
0x100b1a05  mov     dword ptr [eax], 1
0x100b1a0b  xor     eax, eax
0x100b1a0d  jmp     loc_100B1DF4
0x100b1a12  test    dl, 10h
0x100b1a15  jz      short loc_100B1A4B
0x100b1a17  test    byte ptr [ebp+var_384], 10h
0x100b1a1e  jnz     short loc_100B1A41
0x100b1a20  push    edi
0x100b1a21  push    80000000h
0x100b1a26  push    esi
0x100b1a27  push    ebx
0x100b1a28  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100b1a2d  xor     ecx, ecx
0x100b1a2f  mov     edx, 0FFFFF9BDh
0x100b1a34  cmp     eax, edx
0x100b1a36  setz    cl
0x100b1a39  mov     [ebp+Block], ecx
0x100b1a3f  jz      short loc_100B1A4B
0x100b1a41  mov     eax, 0FFFFFA19h
0x100b1a46  jmp     loc_100B1DF4
0x100b1a4b  push    edi
0x100b1a4c  push    ecx
0x100b1a4d  lea     eax, [ebp+var_90]
0x100b1a53  mov     edx, offset aTmpcol; "TmpCol"
0x100b1a58  push    eax
0x100b1a59  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x100b1a5e  test    eax, eax
0x100b1a60  js      loc_100B1DF4
0x100b1a66  lea     eax, [ebp+var_454]
0x100b1a6c  push    eax
0x100b1a6d  push    edi
0x100b1a6e  push    edi
0x100b1a6f  lea     eax, [ebp+var_380]
0x100b1a75  push    eax
0x100b1a76  lea     eax, [ebp+var_90]
0x100b1a7c  push    eax
0x100b1a7d  push    esi
0x100b1a7e  push    ebx
0x100b1a7f  call    _ErrDispAddColumn@28; ErrDispAddColumn(x,x,x,x,x,x,x)
0x100b1a84  test    eax, eax
0x100b1a86  js      loc_100B1DF4
0x100b1a8c  mov     edi, [ebp+var_434]
0x100b1a92  lea     eax, [ebp+var_42C]
0x100b1a98  push    3
0x100b1a9a  push    4
0x100b1a9c  push    eax
0x100b1a9d  push    edi
0x100b1a9e  push    esi
0x100b1a9f  push    ebx
0x100b1aa0  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1aa5  test    eax, eax
0x100b1aa7  js      short loc_100B1AF5
0x100b1aa9  push    0
0x100b1aab  push    18h
0x100b1aad  lea     eax, [ebp+var_3B0]
0x100b1ab3  push    eax
0x100b1ab4  push    offset _wszSoPresentationOrder; "PresentationOrder"
0x100b1ab9  push    [ebp+var_42C]
0x100b1abf  push    ebx
0x100b1ac0  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1ac5  test    eax, eax
0x100b1ac7  js      short loc_100B1AE9
0x100b1ac9  xor     eax, eax
0x100b1acb  push    eax
0x100b1acc  push    eax
0x100b1acd  push    eax
0x100b1ace  push    2
0x100b1ad0  lea     eax, [ebp+var_438]
0x100b1ad6  push    eax
0x100b1ad7  push    [ebp+var_3AC]
0x100b1add  push    [ebp+var_42C]
0x100b1ae3  push    ebx
0x100b1ae4  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x100b1ae9  push    [ebp+var_42C]
0x100b1aef  push    ebx
0x100b1af0  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100b1af5  push    3
0x100b1af7  push    4
0x100b1af9  lea     eax, [ebp+var_42C]
0x100b1aff  push    eax
0x100b1b00  lea     eax, [ebp+var_90]
0x100b1b06  push    eax
0x100b1b07  push    esi
0x100b1b08  push    ebx
0x100b1b09  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1b0e  test    eax, eax
0x100b1b10  js      short loc_100B1B7C
0x100b1b12  push    0
0x100b1b14  push    18h
0x100b1b16  lea     eax, [ebp+var_3B0]
0x100b1b1c  push    eax
0x100b1b1d  push    offset _wszSoPresentationOrder; "PresentationOrder"
0x100b1b22  push    [ebp+var_42C]
0x100b1b28  push    ebx
0x100b1b29  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x100b1b2e  test    eax, eax
0x100b1b30  js      short loc_100B1B70
0x100b1b32  push    2
0x100b1b34  push    [ebp+var_42C]
0x100b1b3a  push    ebx
0x100b1b3b  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100b1b40  push    0
0x100b1b42  push    0
0x100b1b44  push    2
0x100b1b46  lea     eax, [ebp+var_438]
0x100b1b4c  push    eax
0x100b1b4d  push    [ebp+var_3AC]
0x100b1b53  push    [ebp+var_42C]
0x100b1b59  push    ebx
0x100b1b5a  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100b1b5f  xor     eax, eax
0x100b1b61  push    eax
0x100b1b62  push    eax
0x100b1b63  push    eax
0x100b1b64  push    [ebp+var_42C]
0x100b1b6a  push    ebx
0x100b1b6b  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100b1b70  push    [ebp+var_42C]
0x100b1b76  push    ebx
0x100b1b77  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100b1b7c  cmp     [ebp+Block], 0
0x100b1b83  jnz     loc_100B1CAE
0x100b1b89  push    0
0x100b1b8b  push    ecx
0x100b1b8c  lea     eax, [ebp+var_118]
0x100b1b92  mov     [ebp+var_43C], 0FFFFFFFFh
0x100b1b9c  push    eax
0x100b1b9d  mov     edx, offset aTmptableidparm; "TmpTableIdParm"
0x100b1ba2  call    _ErrUniqueName@20; ErrUniqueName(x,x,x,x,x)
0x100b1ba7  test    eax, eax
0x100b1ba9  js      loc_100B1DF4
0x100b1baf  push    127h
0x100b1bb4  mov     edx, offset aParameters; "PARAMETERS "
0x100b1bb9  lea     ecx, [ebp+var_368]
0x100b1bbf  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100b1bc4  push    127h
0x100b1bc9  lea     edx, [ebp+var_118]
0x100b1bcf  lea     ecx, [ebp+var_368]
0x100b1bd5  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1bda  push    127h
0x100b1bdf  mov     edx, offset aTableidUpdate; " tableid; UPDATE "
0x100b1be4  lea     ecx, [ebp+var_368]
0x100b1bea  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1bef  push    127h
0x100b1bf4  lea     edx, [ebp+var_118]
0x100b1bfa  lea     ecx, [ebp+var_368]
0x100b1c00  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c05  push    127h
0x100b1c0a  mov     edx, offset aSet; " SET "
0x100b1c0f  lea     ecx, [ebp+var_368]
0x100b1c15  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c1a  push    127h
0x100b1c1f  lea     edx, [ebp+var_90]
0x100b1c25  lea     ecx, [ebp+var_368]
0x100b1c2b  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c30  push    127h
0x100b1c35  mov     edx, offset asc_1000D248; " = ["
0x100b1c3a  lea     ecx, [ebp+var_368]
0x100b1c40  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c45  push    127h
0x100b1c4a  mov     edx, edi
0x100b1c4c  lea     ecx, [ebp+var_368]
0x100b1c52  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c57  push    127h
0x100b1c5c  mov     edx, offset asc_1000D254; "]"
0x100b1c61  lea     ecx, [ebp+var_368]
0x100b1c67  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1c6c  lea     eax, [ebp+var_43C]
0x100b1c72  mov     [ebp+var_444], 0FFh
0x100b1c7c  push    eax
0x100b1c7d  xor     edi, edi
0x100b1c7f  mov     [ebp+Block], esi
0x100b1c85  push    edi
0x100b1c86  push    [ebp+arg_8]
0x100b1c89  lea     eax, [ebp+var_444]
0x100b1c8f  push    8
0x100b1c91  push    eax
0x100b1c92  lea     eax, [ebp+var_368]
0x100b1c98  push    eax
0x100b1c99  push    [ebp+var_430]
0x100b1c9f  push    ebx
0x100b1ca0  call    _ErrTrySQLString@32; ErrTrySQLString(x,x,x,x,x,x,x,x)
0x100b1ca5  test    eax, eax
0x100b1ca7  jns     short loc_100B1CB0
0x100b1ca9  jmp     loc_100B1DF4
0x100b1cae  xor     edi, edi
0x100b1cb0  mov     [ebp+var_3E8], 0FFFFFFFFh
0x100b1cba  lea     eax, [ebp+var_3EC]
0x100b1cc0  push    edi
0x100b1cc1  cmp     esi, 0FFFFFFFFh
0x100b1cc4  jz      short loc_100B1CD3
0x100b1cc6  push    3Ch ; '<'
0x100b1cc8  push    eax
0x100b1cc9  push    edi
0x100b1cca  push    esi
0x100b1ccb  push    ebx
0x100b1ccc  call    _ErrDispGetTableIndexInfo@24; ErrDispGetTableIndexInfo(x,x,x,x,x,x)
0x100b1cd1  jmp     short loc_100B1CF3
0x100b1cd3  mov     [ebp+Block], eax
0x100b1cd9  lea     eax, [ebp+var_44C]
0x100b1cdf  push    eax
0x100b1ce0  push    edi
0x100b1ce1  push    edi
0x100b1ce2  push    edi
0x100b1ce3  push    ebx
0x100b1ce4  mov     [ebp+var_44C], 3Ch ; '<'
0x100b1cee  call    _ErrDispGetIndexInfo@24; ErrDispGetIndexInfo(x,x,x,x,x,x)
0x100b1cf3  test    eax, eax
0x100b1cf5  js      loc_100B1DF4
0x100b1cfb  push    edi; Size
0x100b1cfc  mov     [ebp+var_430], edi
0x100b1d02  call    ds:__imp__malloc
0x100b1d08  mov     [ebp+Block], eax
0x100b1d0e  pop     ecx
0x100b1d0f  test    eax, eax
0x100b1d11  jnz     short loc_100B1D1D
0x100b1d13  mov     esi, 0FFFFFC0Dh
0x100b1d18  jmp     loc_100B1DD4
0x100b1d1d  push    0Fh
0x100b1d1f  pop     ecx
0x100b1d20  push    0
0x100b1d22  push    80000000h
0x100b1d27  lea     esi, [ebp+var_3EC]
0x100b1d2d  lea     edi, [ebp+var_428]
0x100b1d33  rep movsd
0x100b1d35  push    [ebp+var_424]
0x100b1d3b  push    ebx
0x100b1d3c  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100b1d41  mov     edi, [ebp+arg_0]
0x100b1d44  test    eax, eax
0x100b1d46  js      short loc_100B1D71
  ... truncated ...
```
