# ErrSecRefreshLink(x,x,x,x,x)

- ea: `0x1002c160`
- end: `0x1002c7a4`
- name: `_ErrSecRefreshLink@20`
- size: `1604`
- prototype: `int __fastcall(Session *, unsigned int, void *, _WORD *, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1002d140`
- `0x100d7ec3`

## callees

- `0x10012af0`
- `0x10014380`
- `0x10017010`
- `0x10017150`
- `0x1001ebc0`
- `0x1002a7d0`
- `0x1002b290`
- `0x1002b920`
- `0x1002c160`
- `0x1003a420`
- `0x1003a570`
- `0x1003db70`
- `0x1003e9b0`
- `0x1003ea00`
- `0x10042b60`
- `0x10042e80`
- `0x100433f0`
- `0x100439d0`
- `0x10044240`
- `0x10044a70`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x10050190`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c758`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c766`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c758`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c766`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c362`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c3a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c362`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c3a1`

## pseudocode

```c
int __fastcall ErrSecRefreshLink(Session *a1, unsigned int a2, void *a3, _WORD *a4, int a5)
{
  _WORD *v5; // ebx
  int (__thiscall *v6)(_DWORD, _DWORD, _DWORD, _DWORD, const wchar_t *, void *, _DWORD *, int); // ecx
  int result; // eax
  Session *v8; // edi
  int TableColumnInfo; // esi
  int v10; // eax
  _WORD *v11; // esi
  _WORD *v12; // eax
  int v13; // esi
  int v14; // edx
  _WORD *v15; // ecx
  _WORD *v16; // eax
  int v17; // eax
  char *v18; // ecx
  _WORD *v19; // esi
  int v20; // edx
  char *v21; // eax
  bool v22; // zf
  const wchar_t *v23; // esi
  int v24; // edx
  int v25; // eax
  _WORD *v26; // ecx
  _WORD *v27; // eax
  int v28; // eax
  int (__thiscall *v29)(_DWORD, _DWORD, _DWORD, const wchar_t *, void *, Session **); // ecx
  int v30; // [esp+18h] [ebp-3DCh]
  unsigned int v31; // [esp+2Ch] [ebp-3C8h] BYREF
  Session *v32; // [esp+30h] [ebp-3C4h] BYREF
  unsigned int v33; // [esp+34h] [ebp-3C0h]
  int v34; // [esp+38h] [ebp-3BCh] BYREF
  void *Block; // [esp+3Ch] [ebp-3B8h]
  __int16 v36; // [esp+40h] [ebp-3B4h] BYREF
  int v37; // [esp+44h] [ebp-3B0h] BYREF
  int v38; // [esp+48h] [ebp-3ACh] BYREF
  int v39; // [esp+4Ch] [ebp-3A8h] BYREF
  void *Src; // [esp+50h] [ebp-3A4h]
  int v41; // [esp+54h] [ebp-3A0h]
  int v42; // [esp+58h] [ebp-39Ch] BYREF
  _DWORD v43[4]; // [esp+5Ch] [ebp-398h] BYREF
  _BYTE v44[4]; // [esp+6Ch] [ebp-388h] BYREF
  int v45; // [esp+70h] [ebp-384h]
  int v46[34]; // [esp+84h] [ebp-370h] BYREF
  _BYTE v47[128]; // [esp+10Ch] [ebp-2E8h] BYREF
  char v48; // [esp+18Ch] [ebp-268h] BYREF

  v5 = 0;
  v41 = a5;
  v32 = a1;
  v33 = a2;
  Src = a3;
  v37 = -1;
  v34 = -1;
  v31 = 0;
  Block = 0;
  v38 = 0;
  v43[3] = &v34;
  v43[0] = 4;
  if ( a2 >= 0x100 || a2 < dbidInit )
    return -1010;
  v30 = 3;
  _mm_lfence();
  v6 = *(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD, const wchar_t *, void *, _DWORD *, int))(mpdbidpvdbfndef[a2] + 52);
  result = v6(v6, *(&rgiscb + 5 * mpdbidiiscb[a2]), *(&mpdbiddbid + a2), 0, L"Tables", a3, v43, v30);
  v8 = v32;
  if ( result < 0 )
    return result;
  v31 = 2;
  v39 = v34;
  TableColumnInfo = ErrDispGetTableColumnInfo(v32, v34, L"Type", v44, 24, 0);
  if ( TableColumnInfo >= 0 )
  {
    TableColumnInfo = ErrDispRetrieveColumn(v32, v39, v45, &v36, v31, &v31, 0, 0);
    if ( TableColumnInfo >= 0 )
    {
      v31 = 4;
      v39 = v34;
      TableColumnInfo = ErrDispGetTableColumnInfo(v8, v34, L"Id", v44, 24, 0);
      if ( TableColumnInfo >= 0 )
      {
        TableColumnInfo = ErrDispRetrieveColumn(v8, v39, v45, &v42, v31, &v31, 0, 0);
        if ( TableColumnInfo >= 0 )
        {
          v10 = (int)*(&::Src + 5 * mpdbidiiscb[v33]);
          if ( v10 )
          {
            TableColumnInfo = ErrSecCollectAccess(v42, v10, 0, &v39, 0);
            if ( TableColumnInfo >= 0 )
            {
              if ( (v39 & 8) != 0 )
              {
                if ( v36 == 6 || v36 == 4 )
                {
                  v11 = _malloc(0x20Au);
                  Block = v11;
                  if ( v11 )
                  {
                    if ( v41 )
                      WCSCPY2(261);
                    else
                      *v11 = 0;
                    v5 = _malloc(0x25Cu);
                    v41 = (int)v5;
                    if ( v5 )
                    {
                      v12 = a4;
                      if ( a4 )
                      {
                        v13 = 2147483646;
                        v14 = 302;
                        v15 = v5;
                        do
                        {
                          if ( !v13 )
                            break;
                          if ( !*v12 )
                            break;
                          *v15++ = *v12++;
                          --v13;
                          --v14;
                        }
                        while ( v14 );
                        v8 = v32;
                        v16 = v15 - 1;
                        v11 = Block;
                        if ( v14 )
                          v16 = v15;
                        *v16 = 0;
                      }
                      else
                      {
                        *v5 = 0;
                      }
                      if ( !*v11 && !*v5 )
                      {
                        v31 = 521;
                        TableColumnInfo = ErrGetSysField(L"Database", v11, &v31);
                        if ( TableColumnInfo < 0 )
                          goto LABEL_74;
                        *((_WORD *)Block + (v31 >> 1)) = 0;
                        v31 = 604;
                        TableColumnInfo = ErrGetSysField(L"Connect", v5, &v31);
                        if ( TableColumnInfo < 0 )
                          goto LABEL_74;
                        v5[v31 >> 1] = 0;
                      }
                      if ( v36 == 4 && WCSNICMP(5) )
                      {
                        v17 = 2147483646;
                        v18 = &v48;
                        v19 = v5;
                        v20 = 302;
                        do
                        {
                          if ( !v17 )
                            break;
                          if ( !*v19 )
                            break;
                          *(_WORD *)v18 = *v19++;
                          v18 += 2;
                          --v17;
                          --v20;
                        }
                        while ( v20 );
                        v8 = v32;
                        v21 = v18 - 2;
                        v22 = v20 == 0;
                        v23 = L"ODBC;";
                        v24 = 302;
                        if ( !v22 )
                          v21 = v18;
                        *(_WORD *)v21 = 0;
                        v25 = 2147483646;
                        v26 = v5;
                        do
                        {
                          if ( !v25 )
                            break;
                          if ( !*v23 )
                            break;
                          *v26++ = *v23++;
                          --v25;
                          --v24;
                        }
                        while ( v24 );
                        v5 = (_WORD *)v41;
                        v27 = v26 - 1;
                        if ( v24 )
                          v27 = v26;
                        *v27 = 0;
                        WCSCAT2(302);
                        v32 = (Session *)1;
                      }
                      else
                      {
                        v32 = 0;
                      }
                      v28 = ErrOpenDatabase(v8, Block, v5, &v37, 0);
                      TableColumnInfo = v28;
                      if ( v28 < 0 )
                      {
                        if ( v32 || v28 != -1032 && v28 != -1031 && v28 != -1033 && v28 != -1024 )
                          goto LABEL_74;
                        ClearErrorInfo(v8);
                        TableColumnInfo = ErrOpenDatabase(v8, Block, v5, &v37, 3);
                        if ( TableColumnInfo < 0 )
                          goto LABEL_74;
                      }
                      TableColumnInfo = ErrIsamBeginTransaction(v8);
                      if ( TableColumnInfo < 0 )
                        goto LABEL_74;
                      TableColumnInfo = ErrCreateTmpLink(v8, v37, v34, (int)v46, (int)v5, (int)&v38);
                      if ( TableColumnInfo >= 0 )
                      {
                        TableColumnInfo = ErrRefreshLinkProperties(v8, v33, Src, v46, v38);
                        if ( TableColumnInfo >= 0 )
                        {
                          v38 = 0;
                          if ( v33 < dbidInit )
                          {
                            TableColumnInfo = -1010;
                          }
                          else
                          {
                            _mm_lfence();
                            v29 = *(int (__thiscall **)(_DWORD, _DWORD, _DWORD, const wchar_t *, void *, Session **))(mpdbidpvdbfndef[v33] + 72);
                            TableColumnInfo = v29(
                                                v29,
                                                *(&rgiscb + 5 * mpdbidiiscb[v33]),
                                                *(&mpdbiddbid + v33),
                                                L"Tables",
                                                Src,
                                                &v32);
                            if ( TableColumnInfo >= 0 )
                            {
                              TableColumnInfo = ErrSecGetOwner(v8, v33, v32, v47, 128, &v38);
                              if ( TableColumnInfo >= 0 )
                              {
                                TableColumnInfo = ErrDispGetObjidFromName(v8, v33, L"Tables", v46, &v32);
                                if ( TableColumnInfo >= 0 )
                                {
                                  TableColumnInfo = ErrSecSetOwner(v8, v33, (char)v32, v47, v38);
                                  if ( TableColumnInfo >= 0 )
                                  {
                                    TableColumnInfo = ErrDeleteObject(v8, v33, v42);
                                    if ( TableColumnInfo >= 0 )
                                    {
                                      TableColumnInfo = ErrDispRenameObject(v8, v33, L"Tables", v46, Src);
                                      if ( TableColumnInfo >= 0 )
                                      {
                                        TableColumnInfo = ErrIsamCommitTransaction(v8, 0);
                                        if ( TableColumnInfo >= 0 )
                                          goto LABEL_74;
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                      ErrIsamRollback(v8, 0);
                    }
                    else
                    {
                      TableColumnInfo = -1011;
                    }
                  }
                  else
                  {
                    TableColumnInfo = -1011;
                  }
                }
                else
                {
                  TableColumnInfo = -1316;
                }
              }
              else
              {
                UtilSetErrorInfoReal((int)v8, Src, 0, 0, -8170, 0, 0, 0);
                TableColumnInfo = -1907;
              }
            }
          }
          else
          {
            TableColumnInfo = -1001;
          }
        }
      }
    }
  }
LABEL_74:
  if ( v34 != -1 )
  {
    ErrDispCloseTable(v8, v34);
    v34 = -1;
  }
  if ( v37 != -1 )
  {
    ErrDispCloseDatabase(v8, v37, 0);
    v37 = -1;
  }
  if ( Block )
    _free(Block);
  if ( v5 )
    _free(v5);
  return TableColumnInfo;
}

```

## disassembly

```asm
0x1002c160  mov     edi, edi
0x1002c162  push    ebp
0x1002c163  mov     ebp, esp
0x1002c165  and     esp, 0FFFFFFF8h
0x1002c168  sub     esp, 3CCh
0x1002c16e  mov     eax, ___security_cookie
0x1002c173  xor     eax, esp
0x1002c175  mov     [esp+3CCh+var_4], eax
0x1002c17c  mov     eax, [ebp+arg_8]
0x1002c17f  push    ebx
0x1002c180  xor     ebx, ebx
0x1002c182  mov     [esp+3D0h+var_3A0], eax
0x1002c186  mov     [esp+3D0h+var_3C4], ecx
0x1002c18a  lea     eax, [esp+3D0h+var_3BC]
0x1002c18e  mov     ecx, [ebp+arg_0]
0x1002c191  mov     [esp+3D0h+var_3C0], edx
0x1002c195  mov     [esp+3D0h+Src], ecx
0x1002c199  mov     [esp+3D0h+var_3B0], 0FFFFFFFFh
0x1002c1a1  mov     [esp+3D0h+var_3BC], 0FFFFFFFFh
0x1002c1a9  mov     [esp+3D0h+var_3C8], 0
0x1002c1b1  mov     [esp+3D0h+Block], ebx
0x1002c1b5  mov     [esp+3D0h+var_3AC], ebx
0x1002c1b9  mov     [esp+3D0h+var_38C], eax
0x1002c1bd  mov     [esp+3D0h+var_398], 4
0x1002c1c5  push    esi
0x1002c1c6  push    edi
0x1002c1c7  cmp     edx, 100h
0x1002c1cd  jnb     loc_1002C788
0x1002c1d3  cmp     edx, _dbidInit
0x1002c1d9  jb      loc_1002C788
0x1002c1df  push    3
0x1002c1e1  lfence
0x1002c1e4  mov     eax, _mpdbidiiscb[edx*4]
0x1002c1eb  lea     edi, [esp+3DCh+var_398]
0x1002c1ef  mov     esi, _mpdbidpvdbfndef[edx*4]
0x1002c1f6  push    edi
0x1002c1f7  push    ecx
0x1002c1f8  push    offset _wszTcObject; "Tables"
0x1002c1fd  mov     esi, [esi+34h]
0x1002c200  lea     eax, [eax+eax*4]
0x1002c203  push    ebx
0x1002c204  push    _mpdbiddbid[edx*4]; unsigned int
0x1002c20b  mov     ecx, esi
0x1002c20d  push    dword ptr _rgiscb[eax*4]; void *
0x1002c214  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002c21a  call    esi
0x1002c21c  mov     edi, [esp+3D8h+var_3C4]
0x1002c220  test    eax, eax
0x1002c222  js      loc_1002C78D
0x1002c228  mov     eax, [esp+3D8h+var_3BC]
0x1002c22c  lea     ecx, [esp+3D8h+var_388]
0x1002c230  push    ebx
0x1002c231  push    18h
0x1002c233  push    ecx
0x1002c234  push    offset _wszSoObjectTypeColumn; "Type"
0x1002c239  push    eax
0x1002c23a  push    edi
0x1002c23b  mov     [esp+3F0h+var_3C8], 2
0x1002c243  mov     [esp+3F0h+var_3A8], eax
0x1002c247  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c24c  mov     esi, eax
0x1002c24e  test    esi, esi
0x1002c250  js      loc_1002C71D
0x1002c256  push    ebx
0x1002c257  push    ebx
0x1002c258  lea     eax, [esp+3E0h+var_3C8]
0x1002c25c  push    eax
0x1002c25d  push    [esp+3E4h+var_3C8]
0x1002c261  lea     eax, [esp+3E8h+var_3B4]
0x1002c265  push    eax
0x1002c266  push    [esp+3ECh+var_384]
0x1002c26a  push    [esp+3F0h+var_3A8]
0x1002c26e  push    edi
0x1002c26f  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c274  mov     esi, eax
0x1002c276  test    esi, esi
0x1002c278  js      loc_1002C71D
0x1002c27e  mov     eax, [esp+3D8h+var_3BC]
0x1002c282  lea     ecx, [esp+3D8h+var_388]
0x1002c286  push    ebx
0x1002c287  push    18h
0x1002c289  push    ecx
0x1002c28a  push    offset _wszSoIdColumn; "Id"
0x1002c28f  push    eax
0x1002c290  push    edi
0x1002c291  mov     [esp+3F0h+var_3C8], 4
0x1002c299  mov     [esp+3F0h+var_3A8], eax
0x1002c29d  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c2a2  mov     esi, eax
0x1002c2a4  test    esi, esi
0x1002c2a6  js      loc_1002C71D
0x1002c2ac  push    ebx
0x1002c2ad  push    ebx
0x1002c2ae  lea     eax, [esp+3E0h+var_3C8]
0x1002c2b2  push    eax
0x1002c2b3  push    [esp+3E4h+var_3C8]
0x1002c2b7  lea     eax, [esp+3E8h+var_39C]
0x1002c2bb  push    eax
0x1002c2bc  push    [esp+3ECh+var_384]
0x1002c2c0  push    [esp+3F0h+var_3A8]
0x1002c2c4  push    edi
0x1002c2c5  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c2ca  mov     esi, eax
0x1002c2cc  test    esi, esi
0x1002c2ce  js      loc_1002C71D
0x1002c2d4  mov     ecx, [esp+3D8h+var_3C0]
0x1002c2d8  mov     eax, _mpdbidiiscb[ecx*4]
0x1002c2df  lea     eax, [eax+eax*4]
0x1002c2e2  mov     eax, Src[eax*4]
0x1002c2e9  test    eax, eax
0x1002c2eb  jnz     short loc_1002C2F7
0x1002c2ed  mov     esi, 0FFFFFC17h
0x1002c2f2  jmp     loc_1002C71D
0x1002c2f7  push    0
0x1002c2f9  lea     edx, [esp+3DCh+var_3A8]
0x1002c2fd  push    edx
0x1002c2fe  push    0
0x1002c300  push    eax
0x1002c301  push    [esp+3E8h+var_39C]
0x1002c305  mov     edx, ecx
0x1002c307  mov     ecx, edi
0x1002c309  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1002c30e  mov     esi, eax
0x1002c310  test    esi, esi
0x1002c312  js      loc_1002C71D
0x1002c318  test    byte ptr [esp+3D8h+var_3A8], 8
0x1002c31d  jnz     short loc_1002C342
0x1002c31f  push    0; int
0x1002c321  push    0; int
0x1002c323  push    0; int
0x1002c325  push    0FFFFE016h; int
0x1002c32a  push    0; void *
0x1002c32c  push    0; void *
0x1002c32e  push    [esp+3F0h+Src]; Src
0x1002c332  push    edi; int
0x1002c333  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002c338  mov     esi, 0FFFFF88Dh
0x1002c33d  jmp     loc_1002C71D
0x1002c342  mov     ax, [esp+3D8h+var_3B4]
0x1002c347  cmp     ax, 6
0x1002c34b  jz      short loc_1002C35D
0x1002c34d  cmp     ax, 4
0x1002c351  jz      short loc_1002C35D
0x1002c353  mov     esi, 0FFFFFADCh
0x1002c358  jmp     loc_1002C71D
0x1002c35d  push    20Ah; Size
0x1002c362  call    ds:__imp__malloc
0x1002c368  mov     esi, eax
0x1002c36a  add     esp, 4
0x1002c36d  mov     [esp+3D8h+Block], esi
0x1002c371  test    esi, esi
0x1002c373  jnz     short loc_1002C37F
0x1002c375  mov     esi, 0FFFFFC0Dh
0x1002c37a  jmp     loc_1002C71D
0x1002c37f  mov     eax, [esp+3D8h+var_3A0]
0x1002c383  test    eax, eax
0x1002c385  jz      short loc_1002C397
0x1002c387  push    105h
0x1002c38c  mov     edx, eax
0x1002c38e  mov     ecx, esi
0x1002c390  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002c395  jmp     short loc_1002C39C
0x1002c397  xor     eax, eax
0x1002c399  mov     [esi], ax
0x1002c39c  push    25Ch; Size
0x1002c3a1  call    ds:__imp__malloc
0x1002c3a7  mov     ebx, eax
0x1002c3a9  add     esp, 4
0x1002c3ac  mov     [esp+3D8h+var_3A0], ebx
0x1002c3b0  test    ebx, ebx
0x1002c3b2  jnz     short loc_1002C3BE
0x1002c3b4  mov     esi, 0FFFFFC0Dh
0x1002c3b9  jmp     loc_1002C71D
0x1002c3be  mov     eax, [ebp+arg_4]
0x1002c3c1  test    eax, eax
0x1002c3c3  jz      short loc_1002C403
0x1002c3c5  mov     esi, 7FFFFFFEh
0x1002c3ca  mov     edx, 12Eh
0x1002c3cf  mov     ecx, ebx
0x1002c3d1  test    esi, esi
0x1002c3d3  jz      short loc_1002C3EC
0x1002c3d5  movzx   edi, word ptr [eax]
0x1002c3d8  test    di, di
0x1002c3db  jz      short loc_1002C3EC
0x1002c3dd  mov     [ecx], di
0x1002c3e0  add     eax, 2
0x1002c3e3  add     ecx, 2
0x1002c3e6  dec     esi
0x1002c3e7  sub     edx, 1
0x1002c3ea  jnz     short loc_1002C3D1
0x1002c3ec  mov     edi, [esp+3D8h+var_3C4]
0x1002c3f0  lea     eax, [ecx-2]
0x1002c3f3  mov     esi, [esp+3D8h+Block]
0x1002c3f7  test    edx, edx
0x1002c3f9  cmovnz  eax, ecx
0x1002c3fc  xor     ecx, ecx
0x1002c3fe  mov     [eax], cx
0x1002c401  jmp     short loc_1002C408
0x1002c403  xor     eax, eax
0x1002c405  mov     [ebx], ax
0x1002c408  cmp     word ptr [esi], 0
0x1002c40c  jnz     short loc_1002C480
0x1002c40e  cmp     word ptr [ebx], 0
0x1002c412  jnz     short loc_1002C480
0x1002c414  mov     edx, [esp+3D8h+var_3BC]
0x1002c418  lea     eax, [esp+3D8h+var_3C8]
0x1002c41c  push    eax
0x1002c41d  push    esi
0x1002c41e  push    offset _wszSoDatabaseColumn; "Database"
0x1002c423  mov     ecx, edi
0x1002c425  mov     [esp+3E4h+var_3C8], 209h
0x1002c42d  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002c432  mov     esi, eax
0x1002c434  test    esi, esi
0x1002c436  js      loc_1002C71D
0x1002c43c  mov     eax, [esp+3D8h+var_3C8]
0x1002c440  xor     edx, edx
0x1002c442  mov     ecx, [esp+3D8h+Block]
0x1002c446  shr     eax, 1
0x1002c448  mov     [ecx+eax*2], dx
0x1002c44c  lea     eax, [esp+3D8h+var_3C8]
0x1002c450  mov     edx, [esp+3D8h+var_3BC]
0x1002c454  mov     ecx, edi
0x1002c456  push    eax
0x1002c457  push    ebx
0x1002c458  push    offset _wszSoConnectColumn; "Connect"
0x1002c45d  mov     [esp+3E4h+var_3C8], 25Ch
0x1002c465  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002c46a  mov     esi, eax
0x1002c46c  test    esi, esi
0x1002c46e  js      loc_1002C71D
0x1002c474  mov     eax, [esp+3D8h+var_3C8]
0x1002c478  shr     eax, 1
0x1002c47a  xor     ecx, ecx
0x1002c47c  mov     [ebx+eax*2], cx
0x1002c480  cmp     [esp+3D8h+var_3B4], 4
0x1002c486  jnz     loc_1002C53B
0x1002c48c  push    5
0x1002c48e  mov     edx, ebx
0x1002c490  mov     ecx, offset _wszODBC; "ODBC;"
0x1002c495  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1002c49a  test    eax, eax
0x1002c49c  jz      loc_1002C53B
0x1002c4a2  mov     eax, 7FFFFFFEh
0x1002c4a7  lea     ecx, [esp+3D8h+var_268]
0x1002c4ae  mov     esi, ebx
0x1002c4b0  mov     edx, 12Eh
0x1002c4b5  test    eax, eax
0x1002c4b7  jz      short loc_1002C4D0
0x1002c4b9  movzx   edi, word ptr [esi]
0x1002c4bc  test    di, di
0x1002c4bf  jz      short loc_1002C4D0
0x1002c4c1  mov     [ecx], di
0x1002c4c4  add     esi, 2
0x1002c4c7  add     ecx, 2
0x1002c4ca  dec     eax
0x1002c4cb  sub     edx, 1
0x1002c4ce  jnz     short loc_1002C4B5
0x1002c4d0  mov     edi, [esp+3D8h+var_3C4]
0x1002c4d4  lea     eax, [ecx-2]
0x1002c4d7  test    edx, edx
0x1002c4d9  mov     esi, offset _wszODBC; "ODBC;"
0x1002c4de  mov     edx, 12Eh
0x1002c4e3  cmovnz  eax, ecx
0x1002c4e6  xor     ecx, ecx
0x1002c4e8  mov     [eax], cx
0x1002c4eb  mov     eax, 7FFFFFFEh
0x1002c4f0  mov     ecx, ebx
0x1002c4f2  test    eax, eax
0x1002c4f4  jz      short loc_1002C50D
0x1002c4f6  movzx   ebx, word ptr [esi]
0x1002c4f9  test    bx, bx
0x1002c4fc  jz      short loc_1002C50D
0x1002c4fe  mov     [ecx], bx
0x1002c501  add     esi, 2
0x1002c504  add     ecx, 2
0x1002c507  dec     eax
0x1002c508  sub     edx, 1
0x1002c50b  jnz     short loc_1002C4F2
0x1002c50d  mov     ebx, [esp+3D8h+var_3A0]
0x1002c511  lea     eax, [ecx-2]
0x1002c514  test    edx, edx
0x1002c516  lea     edx, [esp+3D8h+var_268]
0x1002c51d  push    12Eh
0x1002c522  cmovnz  eax, ecx
0x1002c525  xor     ecx, ecx
0x1002c527  mov     [eax], cx
0x1002c52a  mov     ecx, ebx
0x1002c52c  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002c531  mov     [esp+3D8h+var_3C4], 1
0x1002c539  jmp     short loc_1002C543
0x1002c53b  mov     [esp+3D8h+var_3C4], 0
0x1002c543  push    0
0x1002c545  lea     eax, [esp+3DCh+var_3B0]
0x1002c549  push    eax
0x1002c54a  push    ebx
0x1002c54b  push    [esp+3E4h+Block]
0x1002c54f  push    edi
0x1002c550  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x1002c555  mov     esi, eax
  ... truncated ...
```
