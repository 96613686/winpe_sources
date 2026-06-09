# ErrREPOpenDatabase(x,x,x,x,x)

- ea: `0x10117190`
- end: `0x1011785c`
- name: `_ErrREPOpenDatabase@20`
- size: `1740`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x10017010`
- `0x10017860`
- `0x1001a430`
- `0x1001aa00`

## callees

- `0x1002ebb0`
- `0x10042ed0`
- `0x10043090`
- `0x10043660`
- `0x10043700`
- `0x10043840`
- `0x100440c0`
- `0x10044460`
- `0x100448f0`
- `0x10044b20`
- `0x10044b90`
- `0x10044c00`
- `0x10044e00`
- `0x10117190`
- `0x1011a8c0`
- `0x1011b238`
- `0x1011b410`
- `0x1011b9c0`
- `0x1011cc6d`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x101171bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x101171bb`

## string_xrefs

- `0x1011758f`: `ReadOnly`

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
                        v12 = ErrDispUpdate((int)a1, v27, 0, 0, 0);
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
0x10117190  mov     edi, edi
0x10117192  push    ebp
0x10117193  mov     ebp, esp
0x10117195  and     esp, 0FFFFFFF8h
0x10117198  sub     esp, 8Ch
0x1011719e  mov     eax, ___security_cookie
0x101171a3  xor     eax, esp
0x101171a5  mov     [esp+8Ch+var_4], eax
0x101171ac  push    ebx
0x101171ad  mov     ebx, [ebp+arg_4]
0x101171b0  push    esi
0x101171b1  push    edi
0x101171b2  push    140h; Size
0x101171b7  mov     [esp+9Ch+var_80], ebx
0x101171bb  call    ds:__imp__malloc
0x101171c1  mov     esi, eax
0x101171c3  mov     [esp+9Ch+var_60], esi
0x101171c7  pop     ecx
0x101171c8  test    esi, esi
0x101171ca  jnz     short loc_101171D6
0x101171cc  mov     eax, 0FFFFFC0Dh
0x101171d1  jmp     loc_10117845
0x101171d6  push    124h; Size
0x101171db  lea     eax, [esi+1Ch]
0x101171de  push    0; Val
0x101171e0  push    eax; void *
0x101171e1  call    _memset
0x101171e6  or      eax, 0FFFFFFFFh
0x101171e9  lea     edi, [esi+0E4h]
0x101171ef  add     esp, 0Ch
0x101171f2  mov     [esi], eax
0x101171f4  cmp     [ebp+arg_10], 0
0x101171f8  mov     [esi+4], eax
0x101171fb  mov     [esi+8], eax
0x101171fe  mov     [esi+0Ch], eax
0x10117201  mov     [esi+10h], eax
0x10117204  mov     [esi+18h], eax
0x10117207  mov     [esi+14h], eax
0x1011720a  mov     _rgrepdbinfo[ebx*4], esi
0x10117211  mov     [esp+98h+var_6C], edi
0x10117215  jz      short loc_1011721F
0x10117217  or      dword ptr [edi], 4000h
0x1011721d  jmp     short loc_10117223
0x1011721f  mov     [esp+98h+var_6C], edi
0x10117223  cmp     [ebp+arg_C], 0FFFFh
0x1011722a  jz      short loc_1011722F
0x1011722c  or      dword ptr [edi], 20h
0x1011722f  push    8
0x10117231  push    4
0x10117233  lea     eax, [esp+0A0h+var_68]
0x10117237  push    eax
0x10117238  push    ebx
0x10117239  mov     ebx, [ebp+arg_0]
0x1011723c  push    ebx
0x1011723d  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117242  cmp     eax, 0FFFFFC17h
0x10117247  jz      loc_10117843
0x1011724d  test    eax, eax
0x1011724f  js      loc_10117845
0x10117255  cmp     [esp+98h+var_68], 30000h
0x1011725d  jb      loc_10117843
0x10117263  cmp     [esp+98h+var_68], 40000h
0x1011726b  jnb     short loc_10117279
0x1011726d  mov     eax, [edi]
0x1011726f  or      eax, 80000h
0x10117274  and     eax, 0FFFFFFDFh
0x10117277  mov     [edi], eax
0x10117279  mov     edx, [esp+98h+var_80]
0x1011727d  lea     eax, [esp+98h+var_84]
0x10117281  push    eax; int
0x10117282  lea     eax, [esp+9Ch+var_78]
0x10117286  mov     ecx, ebx
0x10117288  push    eax; int
0x10117289  push    offset _wszDbObject; "MSysDb"
0x1011728e  push    offset _wszDcObject; "Databases"
0x10117293  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10117298  test    eax, eax
0x1011729a  js      loc_10117845
0x101172a0  cmp     [esp+98h+var_78], 0
0x101172a5  jz      loc_1011781C
0x101172ab  or      dword ptr [edi], 1
0x101172ae  lea     eax, [esp+98h+var_78]
0x101172b2  push    eax; int
0x101172b3  push    offset _wszDbObject; "MSysDb"
0x101172b8  push    offset _wszDcObject; "Databases"
0x101172bd  push    [esp+0A4h+var_80]; int
0x101172c1  push    ebx; int
0x101172c2  call    _ErrFColumnLevelTracking@20; ErrFColumnLevelTracking(x,x,x,x,x)
0x101172c7  test    eax, eax
0x101172c9  js      loc_10117845
0x101172cf  cmp     [esp+98h+var_78], 0
0x101172d4  jz      short loc_101172DC
0x101172d6  or      dword ptr [edi], 20000h
0x101172dc  push    [esp+98h+var_80]
0x101172e0  push    ebx
0x101172e1  call    _ErrREPOpenRepTables@8; ErrREPOpenRepTables(x,x)
0x101172e6  test    eax, eax
0x101172e8  js      loc_10117845
0x101172ee  push    80400000h
0x101172f3  push    offset _WZMSysRepInfo; "MSysRepInfo"
0x101172f8  lea     eax, [esp+0A0h+var_8C]
0x101172fc  push    eax
0x101172fd  push    [esp+0A4h+var_80]
0x10117301  push    ebx
0x10117302  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10117307  test    eax, eax
0x10117309  js      loc_10117845
0x1011730f  push    0
0x10117311  push    18h
0x10117313  lea     eax, [esp+0A0h+var_54]
0x10117317  push    eax
0x10117318  push    offset _WZSchemaMaster; "SchemaMaster"
0x1011731d  push    [esp+0A8h+var_8C]
0x10117321  push    ebx
0x10117322  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x10117327  mov     [esp+98h+var_84], eax
0x1011732b  test    eax, eax
0x1011732d  js      loc_101173FE
0x10117333  push    0
0x10117335  push    80000000h
0x1011733a  push    [esp+0A0h+var_8C]
0x1011733e  push    ebx
0x1011733f  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x10117344  mov     [esp+98h+var_84], eax
0x10117348  test    eax, eax
0x1011734a  js      loc_101173FE
0x10117350  push    0
0x10117352  push    0
0x10117354  lea     eax, [esp+0A0h+var_7C]
0x10117358  push    eax
0x10117359  push    10h
0x1011735b  lea     eax, [esp+0A8h+var_2C]
0x1011735f  push    eax
0x10117360  push    [esp+0ACh+var_50]
0x10117364  push    [esp+0B0h+var_8C]
0x10117368  push    ebx
0x10117369  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1011736e  mov     [esp+98h+var_84], eax
0x10117372  cmp     eax, 3ECh
0x10117377  jnz     short loc_10117389
0x10117379  xor     eax, eax
0x1011737b  lea     edi, [esp+98h+var_2C]
0x1011737f  stosd
0x10117380  stosd
0x10117381  stosd
0x10117382  stosd
0x10117383  mov     edi, [esp+98h+var_6C]
0x10117387  jmp     short loc_1011738D
0x10117389  test    eax, eax
0x1011738b  js      short loc_101173FE
0x1011738d  push    0
0x1011738f  push    18h
0x10117391  lea     eax, [esp+0A0h+var_54]
0x10117395  push    eax
0x10117396  push    offset _WZSingleMaster; "SingleMaster"
0x1011739b  push    [esp+0A8h+var_8C]
0x1011739f  push    ebx
0x101173a0  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x101173a5  mov     [esp+98h+var_84], eax
0x101173a9  test    eax, eax
0x101173ab  js      short loc_101173FE
0x101173ad  push    0
0x101173af  push    0
0x101173b1  lea     eax, [esp+0A0h+var_7C]
0x101173b5  push    eax
0x101173b6  push    2
0x101173b8  lea     eax, [esp+0A8h+var_74]
0x101173bc  push    eax
0x101173bd  push    [esp+0ACh+var_50]
0x101173c1  push    [esp+0B0h+var_8C]
0x101173c5  push    ebx
0x101173c6  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x101173cb  mov     [esp+98h+var_84], eax
0x101173cf  cmp     eax, 3ECh
0x101173d4  jnz     short loc_101173DF
0x101173d6  xor     eax, eax
0x101173d8  mov     [esp+98h+var_74], ax
0x101173dd  jmp     short loc_101173E8
0x101173df  test    eax, eax
0x101173e1  js      short loc_101173FE
0x101173e3  mov     ax, [esp+98h+var_74]
0x101173e8  push    54h ; 'T'
0x101173ea  pop     ecx
0x101173eb  cmp     ax, cx
0x101173ee  jnz     short loc_101173FE
0x101173f0  mov     eax, [edi]
0x101173f2  or      eax, 1000h
0x101173f7  or      eax, 80h
0x101173fc  mov     [edi], eax
0x101173fe  push    [esp+98h+var_8C]
0x10117402  push    ebx
0x10117403  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10117408  mov     eax, [esp+98h+var_84]
0x1011740c  test    eax, eax
0x1011740e  js      loc_10117845
0x10117414  xor     ecx, ecx
0x10117416  lea     eax, [esp+98h+var_58]
0x1011741a  push    ecx; int
0x1011741b  push    ecx; int
0x1011741c  push    eax; int
0x1011741d  lea     eax, [esp+0A4h+var_7C]
0x10117421  push    eax; int
0x10117422  push    10h; int
0x10117424  lea     eax, [esp+0ACh+var_3C]
0x10117428  push    eax; int
0x10117429  push    offset _WZReplicaID; "ReplicaId"
0x1011742e  push    ecx; int
0x1011742f  push    offset _wszDbObject; "MSysDb"
0x10117434  push    offset _wszDcObject; "Databases"
0x10117439  push    [esp+0C0h+var_80]; int
0x1011743d  push    ebx; int
0x1011743e  call    _JetIRetrieveProperty@48; JetIRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x10117443  test    eax, eax
0x10117445  js      loc_10117845
0x1011744b  lea     edi, [esi+0D4h]
0x10117451  lea     esi, [esp+98h+var_3C]
0x10117455  movsd
0x10117456  push    offset _WZGUID; "s_GUID"
0x1011745b  movsd
0x1011745c  movsd
0x1011745d  movsd
0x1011745e  mov     esi, [esp+9Ch+var_60]
0x10117462  mov     eax, [esi+0Ch]
0x10117465  push    eax
0x10117466  push    ebx
0x10117467  mov     [esp+0A4h+var_8C], eax
0x1011746b  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10117470  test    eax, eax
0x10117472  js      loc_10117845
0x10117478  push    1
0x1011747a  push    10h
0x1011747c  lea     eax, [esp+0A0h+var_3C]
0x10117480  push    eax
0x10117481  push    [esp+0A4h+var_8C]
0x10117485  push    ebx
0x10117486  call    _ErrDispMakeKey@20; ErrDispMakeKey(x,x,x,x,x)
0x1011748b  test    eax, eax
0x1011748d  js      loc_10117845
0x10117493  push    1
0x10117495  push    [esp+9Ch+var_8C]
0x10117499  push    ebx
0x1011749a  call    _ErrDispSeek@12; ErrDispSeek(x,x,x)
0x1011749f  test    eax, eax
0x101174a1  js      loc_10117845
0x101174a7  xor     edi, edi
0x101174a9  lea     eax, [esp+98h+var_54]
0x101174ad  push    edi
0x101174ae  push    18h
0x101174b0  push    eax
0x101174b1  push    offset _WZNickname; "Nickname"
0x101174b6  push    [esp+0A8h+var_8C]
0x101174ba  push    ebx
0x101174bb  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x101174c0  test    eax, eax
0x101174c2  js      loc_10117845
0x101174c8  push    edi
0x101174c9  push    edi
0x101174ca  lea     eax, [esp+0A0h+var_7C]
0x101174ce  push    eax
0x101174cf  push    4
0x101174d1  lea     eax, [esp+0A8h+var_70]
0x101174d5  push    eax
0x101174d6  push    [esp+0ACh+var_50]
0x101174da  push    [esp+0B0h+var_8C]
0x101174de  push    ebx
0x101174df  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x101174e4  mov     ecx, eax
0x101174e6  cmp     ecx, 3ECh
0x101174ec  jnz     short loc_101174F6
0x101174ee  mov     eax, edi
0x101174f0  mov     [esp+98h+var_70], eax
0x101174f4  jmp     short loc_101174FA
0x101174f6  mov     eax, [esp+98h+var_70]
0x101174fa  cmp     [esp+98h+var_7C], 2
0x101174ff  jnz     short loc_10117506
0x10117501  cwde
0x10117502  mov     [esp+98h+var_70], eax
0x10117506  test    ecx, ecx
0x10117508  jns     short loc_10117511
0x1011750a  mov     eax, ecx
0x1011750c  jmp     loc_10117845
0x10117511  mov     edi, [esp+98h+var_80]
0x10117515  lea     eax, [esp+98h+var_5C]
0x10117519  push    6
0x1011751b  push    4
0x1011751d  push    eax
0x1011751e  push    edi
0x1011751f  push    ebx
0x10117520  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x10117525  test    eax, eax
0x10117527  js      loc_10117845
0x1011752d  xor     eax, eax
0x1011752f  test    [esp+98h+var_5C], 1
0x10117534  mov     [esp+98h+var_84], eax
0x10117538  mov     [esp+98h+var_78], eax
0x1011753c  jnz     short loc_1011755A
0x1011753e  lea     eax, [esp+98h+var_78]
0x10117542  push    eax; int
0x10117543  push    [esp+9Ch+var_8C]; int
0x10117547  push    edi; int
  ... truncated ...
```
