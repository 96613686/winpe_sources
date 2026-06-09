# ErrREPOpenDatabase(x,x,x,x,x)

- ea: `0x10117340`
- end: `0x10117a0c`
- name: `_ErrREPOpenDatabase@20`
- size: `1740`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x10017150`
- `0x100179a0`
- `0x1001a570`
- `0x1001ab50`

## callees

- `0x1002ed50`
- `0x10043060`
- `0x10043220`
- `0x100437f0`
- `0x10043890`
- `0x100439d0`
- `0x10044240`
- `0x100445e0`
- `0x10044a70`
- `0x10044ca0`
- `0x10044d10`
- `0x10044d80`
- `0x10044f80`
- `0x10117340`
- `0x1011aa70`
- `0x1011b3e8`
- `0x1011b5c0`
- `0x1011bb70`
- `0x1011ce1d`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011736b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1011736b`

## string_xrefs

- `0x1011773f`: `ReadOnly`

## pseudocode

```c
int __stdcall ErrREPOpenDatabase(Session *a1, int a2, int a3, int a4, int a5)
{
  _DWORD *v5; // esi
  int result; // eax
  unsigned int *v7; // edi
  int v8; // eax
  int v9; // eax
  __int16 v10; // ax
  _DWORD *v11; // esi
  int v12; // ecx
  __int16 v13; // ax
  int v14; // edi
  int v15; // eax
  int v16; // eax
  __int16 v17; // ax
  int *v18; // edi
  int v19; // eax
  unsigned int v20; // edx
  int v21; // eax
  int v22; // edx
  _DWORD *v23; // edi
  unsigned int v24; // eax
  int v25; // eax
  int v26; // [esp-4h] [ebp-9Ch]
  int v27; // [esp+Ch] [ebp-8Ch] BYREF
  __int16 v28; // [esp+10h] [ebp-88h] BYREF
  int TableColumnInfo; // [esp+14h] [ebp-84h] BYREF
  int v30; // [esp+18h] [ebp-80h]
  int v31; // [esp+1Ch] [ebp-7Ch] BYREF
  int v32; // [esp+20h] [ebp-78h] BYREF
  __int16 v33; // [esp+24h] [ebp-74h] BYREF
  int v34; // [esp+28h] [ebp-70h] BYREF
  unsigned int *v35; // [esp+2Ch] [ebp-6Ch]
  unsigned int v36; // [esp+30h] [ebp-68h] BYREF
  unsigned int v37; // [esp+34h] [ebp-64h] BYREF
  _DWORD *v38; // [esp+38h] [ebp-60h]
  char v39[4]; // [esp+3Ch] [ebp-5Ch] BYREF
  int v40; // [esp+40h] [ebp-58h] BYREF
  char v41[4]; // [esp+44h] [ebp-54h] BYREF
  int v42; // [esp+48h] [ebp-50h]
  int v43[4]; // [esp+5Ch] [ebp-3Ch] BYREF
  _DWORD v44[4]; // [esp+6Ch] [ebp-2Ch] BYREF
  char v45[4]; // [esp+7Ch] [ebp-1Ch] BYREF
  int v46; // [esp+80h] [ebp-18h]

  v30 = a2;
  v5 = _malloc(0x140u);
  v38 = v5;
  if ( !v5 )
    return -1011;
  memset(v5 + 7, 0, 0x124u);
  v7 = v5 + 57;
  *v5 = -1;
  v5[1] = -1;
  v5[2] = -1;
  v5[3] = -1;
  v5[4] = -1;
  v5[6] = -1;
  v5[5] = -1;
  *(&rgrepdbinfo + a2) = v5;
  v35 = v5 + 57;
  if ( a5 )
    *v7 |= 0x4000u;
  else
    v35 = v5 + 57;
  if ( a4 != 0xFFFF )
    *v7 |= 0x20u;
  result = ErrDispGetDatabaseInfo(a1, a2, &v36, 4, 8);
  if ( result == -1001 )
    return 0;
  if ( result < 0 )
    return result;
  if ( v36 < 0x30000 )
    return 0;
  if ( v36 < 0x40000 )
    *v7 = *v7 & 0xFFF7FFDF | 0x80000;
  result = ErrFObjectReplicable2((int)L"Databases", L"MSysDb", (int)&v32, (int)&TableColumnInfo);
  if ( result < 0 )
    return result;
  if ( !v32 )
  {
    if ( TableColumnInfo )
    {
      v26 = v30;
      v5[57] |= 0x8000u;
      v25 = ErrREPOpenRepTables(a1, v26);
      v12 = 0;
      if ( v25 < 0 )
        return v25;
      return v12;
    }
    return 0;
  }
  *v7 |= 1u;
  result = ErrFColumnLevelTracking((int)a1, v30, (int)L"Databases", L"MSysDb", (int)&v32);
  if ( result < 0 )
    return result;
  if ( v32 )
    *v7 |= 0x20000u;
  result = ErrREPOpenRepTables(a1, v30);
  if ( result < 0 )
    return result;
  result = ErrDispOpenTable(a1, v30, &v27, L"MSysRepInfo", -2143289344);
  if ( result < 0 )
    return result;
  TableColumnInfo = ErrDispGetTableColumnInfo(a1, v27, L"SchemaMaster", v41, 24, 0);
  if ( TableColumnInfo < 0 )
    goto LABEL_32;
  TableColumnInfo = ErrDispMove2(a1, v27, 0x80000000, 0);
  if ( TableColumnInfo < 0 )
    goto LABEL_32;
  v8 = ErrDispRetrieveColumn(a1, v27, v42, v44, 16, &v31, 0, 0);
  TableColumnInfo = v8;
  if ( v8 == 1004 )
  {
    memset(v44, 0, sizeof(v44));
    v7 = v35;
  }
  else if ( v8 < 0 )
  {
    goto LABEL_32;
  }
  TableColumnInfo = ErrDispGetTableColumnInfo(a1, v27, L"SingleMaster", v41, 24, 0);
  if ( TableColumnInfo >= 0 )
  {
    v9 = ErrDispRetrieveColumn(a1, v27, v42, &v33, 2, &v31, 0, 0);
    TableColumnInfo = v9;
    if ( v9 == 1004 )
    {
      v10 = 0;
      v33 = 0;
      goto LABEL_30;
    }
    if ( v9 >= 0 )
    {
      v10 = v33;
LABEL_30:
      if ( v10 == 84 )
        *v7 |= 0x1080u;
    }
  }
LABEL_32:
  ErrDispCloseTable(a1, v27);
  result = TableColumnInfo;
  if ( TableColumnInfo >= 0 )
  {
    result = JetIRetrieveProperty(
               (int)a1,
               v30,
               (int)L"Databases",
               L"MSysDb",
               0,
               (int)L"ReplicaId",
               (int)v43,
               16,
               (int)&v31,
               (int)&v40,
               0,
               0);
    if ( result >= 0 )
    {
      v5[53] = v43[0];
      v5[54] = v43[1];
      v5[55] = v43[2];
      v5[56] = v43[3];
      v11 = v38;
      v27 = v38[3];
      result = ErrDispSetCurrentIndex(a1, v27, L"s_GUID");
      if ( result >= 0 )
      {
        result = ErrDispMakeKey(a1, v27, v43, 16, 1);
        if ( result >= 0 )
        {
          result = ErrDispSeek(a1, v27, 1);
          if ( result >= 0 )
          {
            result = ErrDispGetTableColumnInfo(a1, v27, L"Nickname", v41, 24, 0);
            if ( result >= 0 )
            {
              v12 = ErrDispRetrieveColumn(a1, v27, v42, &v34, 4, &v31, 0, 0);
              if ( v12 == 1004 )
              {
                v13 = 0;
                v34 = 0;
              }
              else
              {
                v13 = v34;
              }
              if ( v31 == 2 )
                v34 = v13;
              if ( v12 < 0 )
                return v12;
              v14 = v30;
              result = ErrDispGetDatabaseInfo(a1, v30, v39, 4, 6);
              if ( result >= 0 )
              {
                v15 = 0;
                TableColumnInfo = 0;
                v32 = 0;
                if ( (v39[0] & 1) == 0 )
                {
                  if ( ErrREPDetectMoveCopy(a1, v14, v27, &v32) < 0 )
                    goto LABEL_51;
                  v15 = v32;
                  TableColumnInfo = v32;
                }
                if ( !v15 )
                {
                  v16 = v34;
LABEL_52:
                  v11[58] = v16;
                  result = ErrDispGetTableColumnInfo(a1, v27, L"ReadOnly", v45, 24, 0);
                  if ( result < 0 )
                    return result;
                  result = ErrDispRetrieveColumn(a1, v27, v46, &v28, 2, &v31, 0, 0);
                  if ( result == 1004 )
                  {
                    v17 = 0;
                    v28 = 0;
                  }
                  else
                  {
                    if ( result < 0 )
                      return result;
                    v17 = v28;
                  }
                  v18 = (int *)v35;
                  if ( v17 == 84 )
                    *v35 |= 0x80u;
                  if ( v36 < 0x40000 )
                    goto LABEL_64;
                  result = ErrDispGetTableColumnInfo(a1, v27, L"Attributes", v41, 24, 0);
                  if ( result < 0 )
                    return result;
                  result = ErrDispRetrieveColumn(a1, v27, v42, v11 + 51, 4, &v31, 0, 0);
                  if ( result == 1004 )
                  {
LABEL_64:
                    v11[51] = 4096;
                  }
                  else if ( result < 0 )
                  {
                    return result;
                  }
                  result = ErrDispGetTableColumnInfo(a1, v27, L"ReplicaType", v41, 24, 0);
                  if ( result < 0 )
                    return result;
                  v19 = ErrDispRetrieveColumn(a1, v27, v42, &v37, 4, &v31, 0, 0);
                  v12 = v19;
                  if ( v19 == 1004 )
                  {
                    v20 = 0;
                    v37 = 0;
                  }
                  else
                  {
                    if ( v19 < 0 )
                      return v12;
                    v20 = v37;
                  }
                  if ( v20 )
                  {
                    v21 = *v18;
                    if ( v20 == 11 )
                    {
                      *v18 = v21 | 0x40;
                    }
                    else
                    {
                      *v18 = v21 | 0x80;
                      if ( v37 > 0xF )
                        return -1907;
                    }
                  }
                  v22 = 0;
                  while ( v43[v22] == v44[v22] )
                  {
                    if ( ++v22 == 4 )
                    {
                      if ( (*v18 & 0x80000) != 0 )
                        return v12;
                      if ( v28 == 84 || (v23 = v11 + 51, (v11[51] & 4) != 0) )
                      {
                        v28 = 70;
                        result = ErrDispPrepareUpdate2(a1, v27, 2);
                        if ( result < 0 )
                          return result;
                        result = ErrDispSetColumn(a1, v27, v46, &v28, 2, 0, 0);
                        if ( result < 0 )
                          return result;
                        v23 = v11 + 51;
                        v11[51] &= ~4u;
                        result = ErrDispGetTableColumnInfo(a1, v27, L"Attributes", v41, 24, 0);
                        if ( result < 0 )
                          return result;
                        result = ErrDispSetColumn(a1, v27, v42, v11 + 51, 4, 0, 0);
                        if ( result < 0 )
                          return result;
                        v12 = ErrDispUpdate(a1, v27, 0, 0, 0);
                        if ( v12 < 0 )
                          return v12;
                      }
                      if ( TableColumnInfo )
                      {
                        if ( (*((_DWORD *)*(&rgrepdbinfo + v30) + 51) & 0x10000) != 0 && (a3 & 0x10000000) == 0 )
                          return ErrNullHostInfo(a1);
                      }
                      else
                      {
                        v24 = v11[57] & 0xFFFFFF7D | 2;
                        *v23 &= ~4u;
                        v11[57] = v24;
                      }
                      return v12;
                    }
                  }
                  return v12;
                }
LABEL_51:
                TableColumnInfo = 1;
                v16 = (a3 & 0x10000000) != 0 ? v34 : 0;
                goto LABEL_52;
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
0x10117340  mov     edi, edi
0x10117342  push    ebp
0x10117343  mov     ebp, esp
0x10117345  and     esp, 0FFFFFFF8h
0x10117348  sub     esp, 8Ch
0x1011734e  mov     eax, ___security_cookie
0x10117353  xor     eax, esp
0x10117355  mov     [esp+8Ch+var_4], eax
0x1011735c  push    ebx
0x1011735d  mov     ebx, [ebp+arg_4]
0x10117360  push    esi
0x10117361  push    edi
0x10117362  push    140h; Size
0x10117367  mov     [esp+9Ch+var_80], ebx
0x1011736b  call    ds:__imp__malloc
0x10117371  mov     esi, eax
0x10117373  mov     [esp+9Ch+var_60], esi
0x10117377  pop     ecx
0x10117378  test    esi, esi
0x1011737a  jnz     short loc_10117386
0x1011737c  mov     eax, 0FFFFFC0Dh
0x10117381  jmp     loc_101179F5
0x10117386  push    124h; Size
0x1011738b  lea     eax, [esi+1Ch]
0x1011738e  push    0; Val
0x10117390  push    eax; void *
0x10117391  call    _memset
0x10117396  or      eax, 0FFFFFFFFh
0x10117399  lea     edi, [esi+0E4h]
0x1011739f  add     esp, 0Ch
0x101173a2  mov     [esi], eax
0x101173a4  cmp     [ebp+arg_10], 0
0x101173a8  mov     [esi+4], eax
0x101173ab  mov     [esi+8], eax
0x101173ae  mov     [esi+0Ch], eax
0x101173b1  mov     [esi+10h], eax
0x101173b4  mov     [esi+18h], eax
0x101173b7  mov     [esi+14h], eax
0x101173ba  mov     _rgrepdbinfo[ebx*4], esi
0x101173c1  mov     [esp+98h+var_6C], edi
0x101173c5  jz      short loc_101173CF
0x101173c7  or      dword ptr [edi], 4000h
0x101173cd  jmp     short loc_101173D3
0x101173cf  mov     [esp+98h+var_6C], edi
0x101173d3  cmp     [ebp+arg_C], 0FFFFh
0x101173da  jz      short loc_101173DF
0x101173dc  or      dword ptr [edi], 20h
0x101173df  push    8
0x101173e1  push    4
0x101173e3  lea     eax, [esp+0A0h+var_68]
0x101173e7  push    eax
0x101173e8  push    ebx
0x101173e9  mov     ebx, [ebp+arg_0]
0x101173ec  push    ebx
0x101173ed  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x101173f2  cmp     eax, 0FFFFFC17h
0x101173f7  jz      loc_101179F3
0x101173fd  test    eax, eax
0x101173ff  js      loc_101179F5
0x10117405  cmp     [esp+98h+var_68], 30000h
0x1011740d  jb      loc_101179F3
0x10117413  cmp     [esp+98h+var_68], 40000h
0x1011741b  jnb     short loc_10117429
0x1011741d  mov     eax, [edi]
0x1011741f  or      eax, 80000h
0x10117424  and     eax, 0FFFFFFDFh
0x10117427  mov     [edi], eax
0x10117429  mov     edx, [esp+98h+var_80]
0x1011742d  lea     eax, [esp+98h+var_84]
0x10117431  push    eax; int
0x10117432  lea     eax, [esp+9Ch+var_78]
0x10117436  mov     ecx, ebx
0x10117438  push    eax; int
0x10117439  push    offset _wszDbObject; "MSysDb"
0x1011743e  push    offset _wszDcObject; "Databases"
0x10117443  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10117448  test    eax, eax
0x1011744a  js      loc_101179F5
0x10117450  cmp     [esp+98h+var_78], 0
0x10117455  jz      loc_101179CC
0x1011745b  or      dword ptr [edi], 1
0x1011745e  lea     eax, [esp+98h+var_78]
0x10117462  push    eax; int
0x10117463  push    offset _wszDbObject; "MSysDb"
0x10117468  push    offset _wszDcObject; "Databases"
0x1011746d  push    [esp+0A4h+var_80]; int
0x10117471  push    ebx; int
0x10117472  call    _ErrFColumnLevelTracking@20; ErrFColumnLevelTracking(x,x,x,x,x)
0x10117477  test    eax, eax
0x10117479  js      loc_101179F5
0x1011747f  cmp     [esp+98h+var_78], 0
0x10117484  jz      short loc_1011748C
0x10117486  or      dword ptr [edi], 20000h
0x1011748c  push    [esp+98h+var_80]
0x10117490  push    ebx
0x10117491  call    _ErrREPOpenRepTables@8; ErrREPOpenRepTables(x,x)
0x10117496  test    eax, eax
0x10117498  js      loc_101179F5
0x1011749e  push    80400000h
0x101174a3  push    offset _WZMSysRepInfo; "MSysRepInfo"
0x101174a8  lea     eax, [esp+0A0h+var_8C]
0x101174ac  push    eax
0x101174ad  push    [esp+0A4h+var_80]
0x101174b1  push    ebx
0x101174b2  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x101174b7  test    eax, eax
0x101174b9  js      loc_101179F5
0x101174bf  push    0
0x101174c1  push    18h
0x101174c3  lea     eax, [esp+0A0h+var_54]
0x101174c7  push    eax
0x101174c8  push    offset _WZSchemaMaster; "SchemaMaster"
0x101174cd  push    [esp+0A8h+var_8C]
0x101174d1  push    ebx
0x101174d2  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x101174d7  mov     [esp+98h+var_84], eax
0x101174db  test    eax, eax
0x101174dd  js      loc_101175AE
0x101174e3  push    0
0x101174e5  push    80000000h
0x101174ea  push    [esp+0A0h+var_8C]
0x101174ee  push    ebx
0x101174ef  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x101174f4  mov     [esp+98h+var_84], eax
0x101174f8  test    eax, eax
0x101174fa  js      loc_101175AE
0x10117500  push    0
0x10117502  push    0
0x10117504  lea     eax, [esp+0A0h+var_7C]
0x10117508  push    eax
0x10117509  push    10h
0x1011750b  lea     eax, [esp+0A8h+var_2C]
0x1011750f  push    eax
0x10117510  push    [esp+0ACh+var_50]
0x10117514  push    [esp+0B0h+var_8C]
0x10117518  push    ebx
0x10117519  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011751e  mov     [esp+98h+var_84], eax
0x10117522  cmp     eax, 3ECh
0x10117527  jnz     short loc_10117539
0x10117529  xor     eax, eax
0x1011752b  lea     edi, [esp+98h+var_2C]
0x1011752f  stosd
0x10117530  stosd
0x10117531  stosd
0x10117532  stosd
0x10117533  mov     edi, [esp+98h+var_6C]
0x10117537  jmp     short loc_1011753D
0x10117539  test    eax, eax
0x1011753b  js      short loc_101175AE
0x1011753d  push    0
0x1011753f  push    18h
0x10117541  lea     eax, [esp+0A0h+var_54]
0x10117545  push    eax
0x10117546  push    offset _WZSingleMaster; "SingleMaster"
0x1011754b  push    [esp+0A8h+var_8C]
0x1011754f  push    ebx
0x10117550  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117555  mov     [esp+98h+var_84], eax
0x10117559  test    eax, eax
0x1011755b  js      short loc_101175AE
0x1011755d  push    0
0x1011755f  push    0
0x10117561  lea     eax, [esp+0A0h+var_7C]
0x10117565  push    eax
0x10117566  push    2
0x10117568  lea     eax, [esp+0A8h+var_74]
0x1011756c  push    eax
0x1011756d  push    [esp+0ACh+var_50]
0x10117571  push    [esp+0B0h+var_8C]
0x10117575  push    ebx
0x10117576  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011757b  mov     [esp+98h+var_84], eax
0x1011757f  cmp     eax, 3ECh
0x10117584  jnz     short loc_1011758F
0x10117586  xor     eax, eax
0x10117588  mov     [esp+98h+var_74], ax
0x1011758d  jmp     short loc_10117598
0x1011758f  test    eax, eax
0x10117591  js      short loc_101175AE
0x10117593  mov     ax, [esp+98h+var_74]
0x10117598  push    54h ; 'T'
0x1011759a  pop     ecx
0x1011759b  cmp     ax, cx
0x1011759e  jnz     short loc_101175AE
0x101175a0  mov     eax, [edi]
0x101175a2  or      eax, 1000h
0x101175a7  or      eax, 80h
0x101175ac  mov     [edi], eax
0x101175ae  push    [esp+98h+var_8C]
0x101175b2  push    ebx
0x101175b3  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x101175b8  mov     eax, [esp+98h+var_84]
0x101175bc  test    eax, eax
0x101175be  js      loc_101179F5
0x101175c4  xor     ecx, ecx
0x101175c6  lea     eax, [esp+98h+var_58]
0x101175ca  push    ecx; int
0x101175cb  push    ecx; int
0x101175cc  push    eax; int
0x101175cd  lea     eax, [esp+0A4h+var_7C]
0x101175d1  push    eax; int
0x101175d2  push    10h; int
0x101175d4  lea     eax, [esp+0ACh+var_3C]
0x101175d8  push    eax; int
0x101175d9  push    offset _WZReplicaID; "ReplicaId"
0x101175de  push    ecx; int
0x101175df  push    offset _wszDbObject; "MSysDb"
0x101175e4  push    offset _wszDcObject; "Databases"
0x101175e9  push    [esp+0C0h+var_80]; int
0x101175ed  push    ebx; int
0x101175ee  call    _JetIRetrieveProperty@48; JetIRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x101175f3  test    eax, eax
0x101175f5  js      loc_101179F5
0x101175fb  lea     edi, [esi+0D4h]
0x10117601  lea     esi, [esp+98h+var_3C]
0x10117605  movsd
0x10117606  push    offset _WZGUID; "s_GUID"
0x1011760b  movsd
0x1011760c  movsd
0x1011760d  movsd
0x1011760e  mov     esi, [esp+9Ch+var_60]
0x10117612  mov     eax, [esi+0Ch]
0x10117615  push    eax
0x10117616  push    ebx
0x10117617  mov     [esp+0A4h+var_8C], eax
0x1011761b  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10117620  test    eax, eax
0x10117622  js      loc_101179F5
0x10117628  push    1
0x1011762a  push    10h
0x1011762c  lea     eax, [esp+0A0h+var_3C]
0x10117630  push    eax
0x10117631  push    [esp+0A4h+var_8C]
0x10117635  push    ebx
0x10117636  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x1011763b  test    eax, eax
0x1011763d  js      loc_101179F5
0x10117643  push    1
0x10117645  push    [esp+9Ch+var_8C]
0x10117649  push    ebx
0x1011764a  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x1011764f  test    eax, eax
0x10117651  js      loc_101179F5
0x10117657  xor     edi, edi
0x10117659  lea     eax, [esp+98h+var_54]
0x1011765d  push    edi
0x1011765e  push    18h
0x10117660  push    eax
0x10117661  push    offset _WZNickname; "Nickname"
0x10117666  push    [esp+0A8h+var_8C]
0x1011766a  push    ebx
0x1011766b  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117670  test    eax, eax
0x10117672  js      loc_101179F5
0x10117678  push    edi
0x10117679  push    edi
0x1011767a  lea     eax, [esp+0A0h+var_7C]
0x1011767e  push    eax
0x1011767f  push    4
0x10117681  lea     eax, [esp+0A8h+var_70]
0x10117685  push    eax
0x10117686  push    [esp+0ACh+var_50]
0x1011768a  push    [esp+0B0h+var_8C]
0x1011768e  push    ebx
0x1011768f  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x10117694  mov     ecx, eax
0x10117696  cmp     ecx, 3ECh
0x1011769c  jnz     short loc_101176A6
0x1011769e  mov     eax, edi
0x101176a0  mov     [esp+98h+var_70], eax
0x101176a4  jmp     short loc_101176AA
0x101176a6  mov     eax, [esp+98h+var_70]
0x101176aa  cmp     [esp+98h+var_7C], 2
0x101176af  jnz     short loc_101176B6
0x101176b1  cwde
0x101176b2  mov     [esp+98h+var_70], eax
0x101176b6  test    ecx, ecx
0x101176b8  jns     short loc_101176C1
0x101176ba  mov     eax, ecx
0x101176bc  jmp     loc_101179F5
0x101176c1  mov     edi, [esp+98h+var_80]
0x101176c5  lea     eax, [esp+98h+var_5C]
0x101176c9  push    6
0x101176cb  push    4
0x101176cd  push    eax
0x101176ce  push    edi
0x101176cf  push    ebx
0x101176d0  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x101176d5  test    eax, eax
0x101176d7  js      loc_101179F5
0x101176dd  xor     eax, eax
0x101176df  test    [esp+98h+var_5C], 1
0x101176e4  mov     [esp+98h+var_84], eax
0x101176e8  mov     [esp+98h+var_78], eax
0x101176ec  jnz     short loc_1011770A
0x101176ee  lea     eax, [esp+98h+var_78]
0x101176f2  push    eax; int
0x101176f3  push    [esp+9Ch+var_8C]; int
0x101176f7  push    edi; int
  ... truncated ...
```
