# ErrSecRefreshLink(x,x,x,x,x)

- ea: `0x1002bfa0`
- end: `0x1002c5e4`
- name: `_ErrSecRefreshLink@20`
- size: `1604`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1002cf90`
- `0x100d7d33`

## callees

- `0x100129b0`
- `0x10014240`
- `0x10016ed0`
- `0x10017010`
- `0x1001ea70`
- `0x1002a600`
- `0x1002b0d0`
- `0x1002b760`
- `0x1002bfa0`
- `0x1003a2a0`
- `0x1003a3f0`
- `0x1003d9f0`
- `0x1003e820`
- `0x1003e870`
- `0x100429d0`
- `0x10042cf0`
- `0x10043260`
- `0x10043840`
- `0x100440c0`
- `0x100448f0`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x10050000`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c598`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c5a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c598`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002c5a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c1a2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c1e1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c1a2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1002c1e1`

## pseudocode

```c
int __fastcall ErrSecRefreshLink(Session *a1, unsigned int a2, void *a3, unsigned __int16 *a4, int a5)
{
  unsigned __int16 *v5; // ebx
  int (__thiscall *v6)(_DWORD, _DWORD, _DWORD, _DWORD, const wchar_t *, void *, _DWORD *, int); // ecx
  int result; // eax
  Session *v8; // edi
  int TableColumnInfo; // esi
  int v10; // eax
  _WORD *v11; // esi
  unsigned __int16 *v12; // eax
  int v13; // esi
  int v14; // edx
  unsigned __int16 *v15; // ecx
  unsigned __int16 *v16; // eax
  int v17; // eax
  char *v18; // ecx
  unsigned __int16 *v19; // esi
  int v20; // edx
  char *v21; // eax
  bool v22; // zf
  const wchar_t *v23; // esi
  int v24; // edx
  int v25; // eax
  unsigned __int16 *v26; // ecx
  unsigned __int16 *v27; // eax
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
  char v44[4]; // [esp+6Ch] [ebp-388h] BYREF
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
                    v5 = (unsigned __int16 *)_malloc(0x25Cu);
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
                        v5 = (unsigned __int16 *)v41;
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
                      v28 = ErrOpenDatabase((int)v8, (wchar_t *)Block, v5, (int)&v37, 0);
                      TableColumnInfo = v28;
                      if ( v28 < 0 )
                      {
                        if ( v32 || v28 != -1032 && v28 != -1031 && v28 != -1033 && v28 != -1024 )
                          goto LABEL_74;
                        ClearErrorInfo(v8);
                        TableColumnInfo = ErrOpenDatabase((int)v8, (wchar_t *)Block, v5, (int)&v37, 3);
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
0x1002bfa0  mov     edi, edi
0x1002bfa2  push    ebp
0x1002bfa3  mov     ebp, esp
0x1002bfa5  and     esp, 0FFFFFFF8h
0x1002bfa8  sub     esp, 3CCh
0x1002bfae  mov     eax, ___security_cookie
0x1002bfb3  xor     eax, esp
0x1002bfb5  mov     [esp+3CCh+var_4], eax
0x1002bfbc  mov     eax, [ebp+arg_8]
0x1002bfbf  push    ebx
0x1002bfc0  xor     ebx, ebx
0x1002bfc2  mov     [esp+3D0h+var_3A0], eax
0x1002bfc6  mov     [esp+3D0h+var_3C4], ecx
0x1002bfca  lea     eax, [esp+3D0h+var_3BC]
0x1002bfce  mov     ecx, [ebp+arg_0]
0x1002bfd1  mov     [esp+3D0h+var_3C0], edx
0x1002bfd5  mov     [esp+3D0h+Src], ecx
0x1002bfd9  mov     [esp+3D0h+var_3B0], 0FFFFFFFFh
0x1002bfe1  mov     [esp+3D0h+var_3BC], 0FFFFFFFFh
0x1002bfe9  mov     [esp+3D0h+var_3C8], 0
0x1002bff1  mov     [esp+3D0h+Block], ebx
0x1002bff5  mov     [esp+3D0h+var_3AC], ebx
0x1002bff9  mov     [esp+3D0h+var_38C], eax
0x1002bffd  mov     [esp+3D0h+var_398], 4
0x1002c005  push    esi
0x1002c006  push    edi
0x1002c007  cmp     edx, 100h
0x1002c00d  jnb     loc_1002C5C8
0x1002c013  cmp     edx, _dbidInit
0x1002c019  jb      loc_1002C5C8
0x1002c01f  push    3
0x1002c021  lfence
0x1002c024  mov     eax, _mpdbidiiscb[edx*4]
0x1002c02b  lea     edi, [esp+3DCh+var_398]
0x1002c02f  mov     esi, _mpdbidpvdbfndef[edx*4]
0x1002c036  push    edi
0x1002c037  push    ecx
0x1002c038  push    offset _wszTcObject; "Tables"
0x1002c03d  mov     esi, [esi+34h]
0x1002c040  lea     eax, [eax+eax*4]
0x1002c043  push    ebx
0x1002c044  push    _mpdbiddbid[edx*4]; unsigned int
0x1002c04b  mov     ecx, esi
0x1002c04d  push    dword ptr _rgiscb[eax*4]; void *
0x1002c054  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002c05a  call    esi
0x1002c05c  mov     edi, [esp+3D8h+var_3C4]
0x1002c060  test    eax, eax
0x1002c062  js      loc_1002C5CD
0x1002c068  mov     eax, [esp+3D8h+var_3BC]
0x1002c06c  lea     ecx, [esp+3D8h+var_388]
0x1002c070  push    ebx
0x1002c071  push    18h
0x1002c073  push    ecx
0x1002c074  push    offset _wszSoObjectTypeColumn; "Type"
0x1002c079  push    eax
0x1002c07a  push    edi
0x1002c07b  mov     [esp+3F0h+var_3C8], 2
0x1002c083  mov     [esp+3F0h+var_3A8], eax
0x1002c087  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c08c  mov     esi, eax
0x1002c08e  test    esi, esi
0x1002c090  js      loc_1002C55D
0x1002c096  push    ebx
0x1002c097  push    ebx
0x1002c098  lea     eax, [esp+3E0h+var_3C8]
0x1002c09c  push    eax
0x1002c09d  push    [esp+3E4h+var_3C8]
0x1002c0a1  lea     eax, [esp+3E8h+var_3B4]
0x1002c0a5  push    eax
0x1002c0a6  push    [esp+3ECh+var_384]
0x1002c0aa  push    [esp+3F0h+var_3A8]
0x1002c0ae  push    edi
0x1002c0af  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c0b4  mov     esi, eax
0x1002c0b6  test    esi, esi
0x1002c0b8  js      loc_1002C55D
0x1002c0be  mov     eax, [esp+3D8h+var_3BC]
0x1002c0c2  lea     ecx, [esp+3D8h+var_388]
0x1002c0c6  push    ebx
0x1002c0c7  push    18h
0x1002c0c9  push    ecx
0x1002c0ca  push    offset _wszSoIdColumn; "Id"
0x1002c0cf  push    eax
0x1002c0d0  push    edi
0x1002c0d1  mov     [esp+3F0h+var_3C8], 4
0x1002c0d9  mov     [esp+3F0h+var_3A8], eax
0x1002c0dd  call    _ErrDispGetTableColumnInfo@24; ErrDispGetTableColumnInfo(x,x,x,x,x,x)
0x1002c0e2  mov     esi, eax
0x1002c0e4  test    esi, esi
0x1002c0e6  js      loc_1002C55D
0x1002c0ec  push    ebx
0x1002c0ed  push    ebx
0x1002c0ee  lea     eax, [esp+3E0h+var_3C8]
0x1002c0f2  push    eax
0x1002c0f3  push    [esp+3E4h+var_3C8]
0x1002c0f7  lea     eax, [esp+3E8h+var_39C]
0x1002c0fb  push    eax
0x1002c0fc  push    [esp+3ECh+var_384]
0x1002c100  push    [esp+3F0h+var_3A8]
0x1002c104  push    edi
0x1002c105  call    _ErrDispRetrieveColumn@32; ErrDispRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002c10a  mov     esi, eax
0x1002c10c  test    esi, esi
0x1002c10e  js      loc_1002C55D
0x1002c114  mov     ecx, [esp+3D8h+var_3C0]
0x1002c118  mov     eax, _mpdbidiiscb[ecx*4]
0x1002c11f  lea     eax, [eax+eax*4]
0x1002c122  mov     eax, Src[eax*4]
0x1002c129  test    eax, eax
0x1002c12b  jnz     short loc_1002C137
0x1002c12d  mov     esi, 0FFFFFC17h
0x1002c132  jmp     loc_1002C55D
0x1002c137  push    0
0x1002c139  lea     edx, [esp+3DCh+var_3A8]
0x1002c13d  push    edx
0x1002c13e  push    0
0x1002c140  push    eax
0x1002c141  push    [esp+3E8h+var_39C]
0x1002c145  mov     edx, ecx
0x1002c147  mov     ecx, edi
0x1002c149  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1002c14e  mov     esi, eax
0x1002c150  test    esi, esi
0x1002c152  js      loc_1002C55D
0x1002c158  test    byte ptr [esp+3D8h+var_3A8], 8
0x1002c15d  jnz     short loc_1002C182
0x1002c15f  push    0; int
0x1002c161  push    0; int
0x1002c163  push    0; int
0x1002c165  push    0FFFFE016h; int
0x1002c16a  push    0; void *
0x1002c16c  push    0; void *
0x1002c16e  push    [esp+3F0h+Src]; Src
0x1002c172  push    edi; int
0x1002c173  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1002c178  mov     esi, 0FFFFF88Dh
0x1002c17d  jmp     loc_1002C55D
0x1002c182  mov     ax, [esp+3D8h+var_3B4]
0x1002c187  cmp     ax, 6
0x1002c18b  jz      short loc_1002C19D
0x1002c18d  cmp     ax, 4
0x1002c191  jz      short loc_1002C19D
0x1002c193  mov     esi, 0FFFFFADCh
0x1002c198  jmp     loc_1002C55D
0x1002c19d  push    20Ah; Size
0x1002c1a2  call    ds:__imp__malloc
0x1002c1a8  mov     esi, eax
0x1002c1aa  add     esp, 4
0x1002c1ad  mov     [esp+3D8h+Block], esi
0x1002c1b1  test    esi, esi
0x1002c1b3  jnz     short loc_1002C1BF
0x1002c1b5  mov     esi, 0FFFFFC0Dh
0x1002c1ba  jmp     loc_1002C55D
0x1002c1bf  mov     eax, [esp+3D8h+var_3A0]
0x1002c1c3  test    eax, eax
0x1002c1c5  jz      short loc_1002C1D7
0x1002c1c7  push    105h
0x1002c1cc  mov     edx, eax
0x1002c1ce  mov     ecx, esi
0x1002c1d0  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002c1d5  jmp     short loc_1002C1DC
0x1002c1d7  xor     eax, eax
0x1002c1d9  mov     [esi], ax
0x1002c1dc  push    25Ch; Size
0x1002c1e1  call    ds:__imp__malloc
0x1002c1e7  mov     ebx, eax
0x1002c1e9  add     esp, 4
0x1002c1ec  mov     [esp+3D8h+var_3A0], ebx
0x1002c1f0  test    ebx, ebx
0x1002c1f2  jnz     short loc_1002C1FE
0x1002c1f4  mov     esi, 0FFFFFC0Dh
0x1002c1f9  jmp     loc_1002C55D
0x1002c1fe  mov     eax, [ebp+arg_4]
0x1002c201  test    eax, eax
0x1002c203  jz      short loc_1002C243
0x1002c205  mov     esi, 7FFFFFFEh
0x1002c20a  mov     edx, 12Eh
0x1002c20f  mov     ecx, ebx
0x1002c211  test    esi, esi
0x1002c213  jz      short loc_1002C22C
0x1002c215  movzx   edi, word ptr [eax]
0x1002c218  test    di, di
0x1002c21b  jz      short loc_1002C22C
0x1002c21d  mov     [ecx], di
0x1002c220  add     eax, 2
0x1002c223  add     ecx, 2
0x1002c226  dec     esi
0x1002c227  sub     edx, 1
0x1002c22a  jnz     short loc_1002C211
0x1002c22c  mov     edi, [esp+3D8h+var_3C4]
0x1002c230  lea     eax, [ecx-2]
0x1002c233  mov     esi, [esp+3D8h+Block]
0x1002c237  test    edx, edx
0x1002c239  cmovnz  eax, ecx
0x1002c23c  xor     ecx, ecx
0x1002c23e  mov     [eax], cx
0x1002c241  jmp     short loc_1002C248
0x1002c243  xor     eax, eax
0x1002c245  mov     [ebx], ax
0x1002c248  cmp     word ptr [esi], 0
0x1002c24c  jnz     short loc_1002C2C0
0x1002c24e  cmp     word ptr [ebx], 0
0x1002c252  jnz     short loc_1002C2C0
0x1002c254  mov     edx, [esp+3D8h+var_3BC]
0x1002c258  lea     eax, [esp+3D8h+var_3C8]
0x1002c25c  push    eax
0x1002c25d  push    esi
0x1002c25e  push    offset _wszSoDatabaseColumn; "Database"
0x1002c263  mov     ecx, edi
0x1002c265  mov     [esp+3E4h+var_3C8], 209h
0x1002c26d  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002c272  mov     esi, eax
0x1002c274  test    esi, esi
0x1002c276  js      loc_1002C55D
0x1002c27c  mov     eax, [esp+3D8h+var_3C8]
0x1002c280  xor     edx, edx
0x1002c282  mov     ecx, [esp+3D8h+Block]
0x1002c286  shr     eax, 1
0x1002c288  mov     [ecx+eax*2], dx
0x1002c28c  lea     eax, [esp+3D8h+var_3C8]
0x1002c290  mov     edx, [esp+3D8h+var_3BC]
0x1002c294  mov     ecx, edi
0x1002c296  push    eax
0x1002c297  push    ebx
0x1002c298  push    offset _wszSoConnectColumn; "Connect"
0x1002c29d  mov     [esp+3E4h+var_3C8], 25Ch
0x1002c2a5  call    _ErrGetSysField@20; ErrGetSysField(x,x,x,x,x)
0x1002c2aa  mov     esi, eax
0x1002c2ac  test    esi, esi
0x1002c2ae  js      loc_1002C55D
0x1002c2b4  mov     eax, [esp+3D8h+var_3C8]
0x1002c2b8  shr     eax, 1
0x1002c2ba  xor     ecx, ecx
0x1002c2bc  mov     [ebx+eax*2], cx
0x1002c2c0  cmp     [esp+3D8h+var_3B4], 4
0x1002c2c6  jnz     loc_1002C37B
0x1002c2cc  push    5
0x1002c2ce  mov     edx, ebx
0x1002c2d0  mov     ecx, offset _wszODBC; "ODBC;"
0x1002c2d5  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1002c2da  test    eax, eax
0x1002c2dc  jz      loc_1002C37B
0x1002c2e2  mov     eax, 7FFFFFFEh
0x1002c2e7  lea     ecx, [esp+3D8h+var_268]
0x1002c2ee  mov     esi, ebx
0x1002c2f0  mov     edx, 12Eh
0x1002c2f5  test    eax, eax
0x1002c2f7  jz      short loc_1002C310
0x1002c2f9  movzx   edi, word ptr [esi]
0x1002c2fc  test    di, di
0x1002c2ff  jz      short loc_1002C310
0x1002c301  mov     [ecx], di
0x1002c304  add     esi, 2
0x1002c307  add     ecx, 2
0x1002c30a  dec     eax
0x1002c30b  sub     edx, 1
0x1002c30e  jnz     short loc_1002C2F5
0x1002c310  mov     edi, [esp+3D8h+var_3C4]
0x1002c314  lea     eax, [ecx-2]
0x1002c317  test    edx, edx
0x1002c319  mov     esi, offset _wszODBC; "ODBC;"
0x1002c31e  mov     edx, 12Eh
0x1002c323  cmovnz  eax, ecx
0x1002c326  xor     ecx, ecx
0x1002c328  mov     [eax], cx
0x1002c32b  mov     eax, 7FFFFFFEh
0x1002c330  mov     ecx, ebx
0x1002c332  test    eax, eax
0x1002c334  jz      short loc_1002C34D
0x1002c336  movzx   ebx, word ptr [esi]
0x1002c339  test    bx, bx
0x1002c33c  jz      short loc_1002C34D
0x1002c33e  mov     [ecx], bx
0x1002c341  add     esi, 2
0x1002c344  add     ecx, 2
0x1002c347  dec     eax
0x1002c348  sub     edx, 1
0x1002c34b  jnz     short loc_1002C332
0x1002c34d  mov     ebx, [esp+3D8h+var_3A0]
0x1002c351  lea     eax, [ecx-2]
0x1002c354  test    edx, edx
0x1002c356  lea     edx, [esp+3D8h+var_268]
0x1002c35d  push    12Eh
0x1002c362  cmovnz  eax, ecx
0x1002c365  xor     ecx, ecx
0x1002c367  mov     [eax], cx
0x1002c36a  mov     ecx, ebx
0x1002c36c  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002c371  mov     [esp+3D8h+var_3C4], 1
0x1002c379  jmp     short loc_1002C383
0x1002c37b  mov     [esp+3D8h+var_3C4], 0
0x1002c383  push    0
0x1002c385  lea     eax, [esp+3DCh+var_3B0]
0x1002c389  push    eax
0x1002c38a  push    ebx
0x1002c38b  push    [esp+3E4h+Block]
0x1002c38f  push    edi
0x1002c390  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x1002c395  mov     esi, eax
  ... truncated ...
```
