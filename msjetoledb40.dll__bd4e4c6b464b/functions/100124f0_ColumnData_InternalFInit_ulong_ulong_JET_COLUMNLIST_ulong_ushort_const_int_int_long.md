# ColumnData::InternalFInit(ulong,ulong,JET_COLUMNLIST &,ulong,ushort const *,int,int,long &)

- ea: `0x100124f0`
- end: `0x10012de6`
- name: `?InternalFInit@ColumnData@@MAEJKKAAUJET_COLUMNLIST@@KPBGHHAAJ@Z`
- size: `2294`
- prototype: `int __thiscall(ColumnData *this, JET_SESID sesid, unsigned int, struct JET_COLUMNLIST *, unsigned int, const unsigned __int16 *, int, int, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x100131d0`

## callees

- `0x1000d4a0`
- `0x100124f0`
- `0x10012e10`
- `0x1001c6d0`
- `0x100258b0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`
- `0x1004dc81`

## import_xrefs

- `msjet40!__imp__JetMove@16` at `0x10012556`
- `msjet40!__imp__JetMove@16` at `0x10012d73`
- `msjet40!__imp__JetMove@16` at `0x10012556`
- `msjet40!__imp__JetMove@16` at `0x10012d73`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012620`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001266c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001274b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012798`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100127fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001283d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100128cf`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001297b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012a34`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012620`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001266c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001274b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012798`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100127fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001283d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100128cf`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001297b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10012a34`
- `msjet40!__imp__JetGetPropertyBlob@28` at `0x1001258d`
- `msjet40!__imp__JetGetPropertyBlob@28` at `0x1001258d`
- `msjet40!__imp__JetFreePropertyBlob@4` at `0x10012dbf`
- `msjet40!__imp__JetFreePropertyBlob@4` at `0x10012dbf`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10012afa`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10012c0f`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10012afa`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10012c0f`
- `msjet40!__imp__JetGetTablePropertyBlob@20` at `0x100125a3`
- `msjet40!__imp__JetGetTablePropertyBlob@20` at `0x100125a3`

## pseudocode

```c
int __thiscall ColumnData::InternalFInit(
        ColumnData *this,
        JET_SESID sesid,
        unsigned int a3,
        struct JET_COLUMNLIST *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        int a7,
        int a8,
        int *a9)
{
  struct JET_COLUMNLIST *v9; // ebx
  int v10; // edi
  JET_ERR v11; // eax
  int TablePropertyBlob; // ecx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  int *v15; // edi
  int v16; // esi
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  unsigned int v19; // kr00_4
  int v20; // ecx
  int v21; // eax
  int v22; // eax
  unsigned __int16 *v23; // eax
  JET_ERR v24; // eax
  int *v25; // edi
  JET_ERR v26; // eax
  unsigned int v27; // eax
  __int16 v28; // ax
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  JET_ERR v34; // eax
  unsigned int v35; // kr04_4
  size_t v36; // eax
  JET_ERR v37; // eax
  unsigned int v38; // kr08_4
  int v39; // ecx
  int v40; // eax
  JET_ERR v41; // eax
  int v42; // ecx
  int PropertyBlobValue; // eax
  int v44; // eax
  int v45; // edx
  bool v46; // zf
  int v47; // eax
  unsigned int v48; // ebx
  size_t v49; // eax
  unsigned int v50; // kr0C_4
  size_t v51; // eax
  JET_ERR v52; // eax
  unsigned int v53; // ecx
  unsigned int cRecord; // [esp-4h] [ebp-20408h]
  struct tagDBID *v56; // [esp+0h] [ebp-20404h]
  const unsigned __int16 *v57; // [esp+0h] [ebp-20404h]
  const unsigned __int16 *v58; // [esp+0h] [ebp-20404h]
  struct tagDBID *v59; // [esp+0h] [ebp-20404h]
  const unsigned __int16 *v60; // [esp+0h] [ebp-20404h]
  unsigned int v61; // [esp+4h] [ebp-20400h]
  unsigned int v62; // [esp+4h] [ebp-20400h]
  unsigned int v63; // [esp+4h] [ebp-20400h]
  char v64[4]; // [esp+Ch] [ebp-203F8h] BYREF
  char v65[4]; // [esp+10h] [ebp-203F4h] BYREF
  struct JET_COLUMNLIST *v66; // [esp+14h] [ebp-203F0h]
  unsigned __int16 *v67; // [esp+18h] [ebp-203ECh]
  ColumnData *v68; // [esp+1Ch] [ebp-203E8h]
  int v69; // [esp+20h] [ebp-203E4h]
  unsigned int v70; // [esp+24h] [ebp-203E0h]
  int v71; // [esp+28h] [ebp-203DCh] BYREF
  int v72; // [esp+2Ch] [ebp-203D8h] BYREF
  int v73; // [esp+30h] [ebp-203D4h] BYREF
  unsigned __int16 *v74; // [esp+34h] [ebp-203D0h]
  int *v75; // [esp+38h] [ebp-203CCh]
  unsigned int pcbActual; // [esp+3Ch] [ebp-203C8h] BYREF
  unsigned int v77; // [esp+40h] [ebp-203C4h] BYREF
  unsigned __int16 Src[32752]; // [esp+44h] [ebp-203C0h] BYREF
  _BYTE v79[65500]; // [esp+10024h] [ebp-103E0h] BYREF
  _WORD pvData[256]; // [esp+20000h] [ebp-404h] BYREF
  unsigned __int16 v81[256]; // [esp+20200h] [ebp-204h] BYREF

  v9 = a4;
  *a9 = 0;
  cRecord = a4->cRecord;
  v68 = this;
  v66 = a4;
  v75 = a9;
  v73 = 0;
  v10 = ColumnData::GrowColumnInfoArray(this, cRecord);
  if ( v10 >= 0 )
  {
    v11 = JetMove(sesid, a4->tableid, 0x80000000, 0);
    *v75 = v11;
    if ( v11 >= 0
      && (!a6
        ? (TablePropertyBlob = JetGetTablePropertyBlob(sesid, a5, 0, &v73, 0))
        : (TablePropertyBlob = JetGetPropertyBlob(sesid, a3, L"tables", a6, 0, &v73, 0)),
          (v69 = TablePropertyBlob, *v75 = TablePropertyBlob, TablePropertyBlob == -1906) || TablePropertyBlob >= 0) )
    {
      v13 = a4->cRecord;
      v14 = 0;
      v70 = 0;
      if ( v13 )
      {
        v15 = v75;
        while ( 1 )
        {
          v71 = 0;
          v72 = 0;
          v16 = *((_DWORD *)v68 + 3) + 104 * v14;
          v17 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidDefault, pvData, 0x1FEu, &pcbActual, 0, 0);
          *v15 = v17;
          if ( v17 < 0 )
            return -2147467259;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
            goto LABEL_121;
          *(_WORD *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
          v18 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidcolumnname, v81, 0x1FEu, &pcbActual, 0, 0);
          *v15 = v18;
          if ( v18 < 0 )
            return -2147467259;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
            goto LABEL_121;
          *(unsigned __int16 *)((char *)v81 + (pcbActual & 0xFFFFFFFE)) = 0;
          FreeDBIDs(v56);
          *(_DWORD *)(v16 + 24) = 2;
          v19 = wcslen(v81);
          v20 = *(_DWORD *)Sys;
          v74 = (unsigned __int16 *)(2 * v19 + 2);
          v21 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(v20 + 12))(*(_DWORD *)(v20 + 12), Sys, v74);
          *(_DWORD *)(v16 + 28) = v21;
          if ( !v21 )
            return -2147024882;
          WCSCPY(v74, v57, v61);
          v74 = *(unsigned __int16 **)(v16 + 4);
          if ( !v74 )
          {
            v22 = *(_DWORD *)(v16 + 24);
            if ( v22 && (unsigned int)(v22 - 2) >= 2 )
              v23 = 0;
            else
              v23 = *(unsigned __int16 **)(v16 + 28);
            v74 = v23;
          }
          v24 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidcolumnid, &v77, 4u, &pcbActual, 0, 0);
          v25 = v75;
          *v75 = v24;
          if ( v24 )
          {
            if ( v24 != 1004 )
              return -2147467259;
            *(_DWORD *)(v16 + 32) = v70 + 1;
          }
          *(_DWORD *)(v16 + 32) = v77;
          v26 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidcoltyp, &v77, 4u, &pcbActual, 0, 0);
          *v25 = v26;
          if ( v26 )
          {
            if ( v26 != 1004 )
              return -2147467259;
            v27 = 0;
            v77 = 0;
          }
          else
          {
            v27 = v77;
          }
          *(_DWORD *)(v16 + 36) = v27;
          v28 = word_100510F0[4 * v77];
          *(_WORD *)(v16 + 40) = v28;
          if ( v28 == 131 )
          {
            v29 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidCountry, &v77, 4u, &pcbActual, 0, 0);
            *v25 = v29;
            if ( v29 )
              return -2147467259;
            *(_BYTE *)(v16 + 48) = v77;
            *(_BYTE *)(v16 + 49) = BYTE2(v77);
          }
          v30 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidLangid, &v77, 4u, &pcbActual, 0, 0);
          *v25 = v30;
          if ( v30 )
            return -2147467259;
          v31 = *(_DWORD *)(v16 + 36);
          if ( v31 == 1 )
            break;
          v32 = v77;
          if ( !v77 && (v31 == 10 || v31 == 9) )
          {
            v32 = 510;
            goto LABEL_39;
          }
LABEL_40:
          *(_DWORD *)(v16 + 44) = v32;
          switch ( *(_DWORD *)(v16 + 36) )
          {
            case 0xA:
              v33 = v77 >> 1;
              break;
            case 0xB:
              v33 = 0x3FFFFFFF;
              break;
            case 0xC:
              v33 = 536870910;
              break;
            default:
              v33 = v77;
              break;
          }
          *(_DWORD *)(v16 + 60) = v33;
          v34 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidcbMax, v81, 0x1FEu, &pcbActual, 0, 0);
          *v25 = v34;
          if ( v34 < 0 )
            return -2147467259;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
            goto LABEL_121;
          *(unsigned __int16 *)((char *)v81 + (pcbActual & 0xFFFFFFFE)) = 0;
          if ( *(_DWORD *)(v16 + 100) )
          {
            operator delete(*(void **)(v16 + 100));
            *(_DWORD *)(v16 + 100) = 0;
          }
          v35 = wcslen(v81);
          v36 = 2 * (v35 + 1);
          if ( !is_mul_ok(2u, v35 + 1) )
            v36 = -1;
          *(_DWORD *)(v16 + 100) = operator new(v36);
          WCSCPY((unsigned __int16 *)(v35 + 1), v58, v62);
          v37 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidgrbit, v81, 0x1FEu, &pcbActual, 0, 0);
          *v75 = v37;
          if ( v37 < 0 )
            return -2147467259;
          if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
            goto LABEL_121;
          *(unsigned __int16 *)((char *)v81 + (pcbActual & 0xFFFFFFFE)) = 0;
          FreeDBIDs(v59);
          *(_DWORD *)(v16 + 92) = 2;
          v38 = wcslen(v81);
          v39 = *(_DWORD *)Sys;
          v67 = (unsigned __int16 *)(2 * v38 + 2);
          v40 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(v39 + 12))(*(_DWORD *)(v39 + 12), Sys, v67);
          *(_DWORD *)(v16 + 96) = v40;
          if ( !v40 )
            return -2147024882;
          WCSCPY(v67, v60, v63);
          v41 = JetRetrieveColumn(sesid, v9->tableid, v9->columnidCp, &v77, 4u, &pcbActual, 0, 0);
          v15 = v75;
          *v75 = v41;
          if ( v41 )
            return -2147467259;
          v42 = 66;
          *(_DWORD *)(v16 + 52) = v77;
          v77 = 66;
          if ( *(_DWORD *)(v16 + 36) == 11 || *(_DWORD *)(v16 + 36) == 12 )
          {
            v42 = 194;
            v77 = 194;
          }
          if ( (*(_BYTE *)(v16 + 52) & 1) != 0 && *(_DWORD *)(v16 + 36) == 10 )
          {
            v42 |= 0x10u;
            v77 = v42;
          }
          switch ( *(_DWORD *)(v16 + 36) )
          {
            case 1:
            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 0xF:
            case 0x10:
              v42 |= 0x10u;
              v77 = v42;
              break;
            default:
              break;
          }
          if ( !v74 || !*v74 )
            goto LABEL_78;
          if ( v69 == -1906 )
          {
            *v15 = -1906;
LABEL_77:
            v42 = v77;
LABEL_78:
            v71 = 0;
            goto LABEL_79;
          }
          PropertyBlobValue = JetGetPropertyBlobValue(v73, pvData, L"Required", &v71, 4, &pcbActual, v65, 0);
          *v15 = PropertyBlobValue;
          if ( PropertyBlobValue > -1906 )
          {
            if ( PropertyBlobValue )
              return -2147467259;
            v42 = v77;
          }
          else
          {
            if ( PropertyBlobValue == -1906 )
              goto LABEL_77;
            if ( PropertyBlobValue != -3602 )
            {
              if ( PropertyBlobValue != -3600 )
                return -2147467259;
              goto LABEL_77;
            }
            v42 = v77;
            v72 = 1;
          }
LABEL_79:
          if ( !v71 )
          {
            v44 = *(_DWORD *)(v16 + 52);
            if ( (v44 & 4) == 0 && *(_DWORD *)(v16 + 36) != 1 && (v44 & 0x10) == 0 )
            {
              v42 |= 0x20u;
              v77 = v42;
            }
          }
          if ( (*(_BYTE *)(v16 + 52) & 8) != 0 )
          {
            v42 |= 0x200u;
            v77 = v42;
          }
          v45 = *(_DWORD *)(v16 + 52);
          if ( (v45 & 0x30) == 0x20 )
          {
            v42 |= 4u;
          }
          else
          {
            if ( (v45 & 0x400000) != 0 )
              goto LABEL_91;
            v42 |= 8u;
          }
          v77 = v42;
LABEL_91:
          v46 = v72 == 0;
          *(_DWORD *)(v16 + 56) = v42;
          if ( v46 && a8 == 1 )
          {
            v72 = 0;
            if ( v69 == -1906 )
            {
              *v15 = -1906;
            }
            else
            {
              v47 = JetGetPropertyBlobValue(v73, v74, L"DefaultValue", Src, 65502, &pcbActual, &v72, 0);
              *v15 = v47;
              if ( v47 > -1906 )
              {
                if ( v47 < 0 )
                  return -2147467259;
                if ( v72 == 9 || v72 == 11 )
                {
                  v48 = pcbActual;
                  v49 = 65500;
                  if ( pcbActual < 0xFFDC )
                    v49 = pcbActual;
                  memcpy(v79, Src, v49);
                  v10 = (*(int (__thiscall **)(_DWORD, LPVOID, int, int, unsigned int, unsigned int *, _BYTE *, unsigned __int16 *, int, _DWORD, char *, _DWORD, _DWORD, _DWORD))(*(_DWORD *)g_pIDataConvert + 12))(
                          *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 12),
                          g_pIDataConvert,
                          128,
                          130,
                          v48,
                          &pcbActual,
                          v79,
                          Src,
                          65500,
                          0,
                          v64,
                          0,
                          0,
                          0);
                  if ( v10 < 0 )
                    return v10;
                  v9 = v66;
                }
                if ( (pcbActual & 0xFFFFFFFE) >= 0xFFDE )
LABEL_121:
                  __report_rangecheckfailure();
                *(unsigned __int16 *)((char *)Src + (pcbActual & 0xFFFFFFFE)) = 0;
                if ( *(_DWORD *)(v16 + 64) )
                {
                  operator delete(*(void **)(v16 + 64));
                  *(_DWORD *)(v16 + 64) = 0;
                }
                v50 = wcslen(Src);
                v51 = 2 * (v50 + 1);
                if ( !is_mul_ok(2u, v50 + 1) )
                  v51 = -1;
                *(_DWORD *)(v16 + 64) = operator new(v51);
                WCSCPY((unsigned __int16 *)(v50 + 1), (const unsigned __int16 *)v56, v61);
                v15 = v75;
              }
              else if ( v47 != -1906 && v47 != -3602 && v47 != -3600 )
              {
                return -2147467259;
              }
            }
          }
          v52 = JetMove(sesid, v9->tableid, 1, 0);
          v53 = v70;
          *v15 = v52;
          if ( v52 < 0 && v53 != v9->cRecord - 1 )
            return -2147467259;
          v14 = v53 + 1;
          *v15 = 0;
          v13 = v9->cRecord;
          v70 = v14;
          if ( v14 >= v13 )
          {
            v10 = 0;
            goto LABEL_117;
          }
        }
        v32 = 2;
LABEL_39:
        v77 = v32;
        goto LABEL_40;
      }
LABEL_117:
      *((_DWORD *)v68 + 1) += v13;
      if ( v73 )
        JetFreePropertyBlob(v73);
    }
    else
    {
      return -2147467259;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x100124f0  mov     edi, edi
0x100124f2  push    ebp
0x100124f3  mov     ebp, esp
0x100124f5  mov     eax, 203F8h
0x100124fa  call    __chkstk
0x100124ff  mov     eax, ___security_cookie
0x10012504  xor     eax, ebp
0x10012506  mov     [ebp+var_4], eax
0x10012509  mov     eax, [ebp+arg_1C]
0x1001250c  push    ebx
0x1001250d  mov     ebx, [ebp+arg_8]
0x10012510  push    esi; unsigned int
0x10012511  mov     esi, [ebp+arg_10]
0x10012514  push    edi; unsigned __int16 *
0x10012515  mov     dword ptr [eax], 0
0x1001251b  push    dword ptr [ebx+8]; unsigned int
0x1001251e  mov     [ebp+var_203E8], ecx
0x10012524  mov     [ebp+var_203F0], ebx
0x1001252a  mov     [ebp+var_203CC], eax
0x10012530  mov     [ebp+var_203D4], 0
0x1001253a  call    ?GrowColumnInfoArray@ColumnData@@IAEJK@Z; ColumnData::GrowColumnInfoArray(ulong)
0x1001253f  mov     edi, eax
0x10012541  test    edi, edi
0x10012543  js      loc_10012DC5
0x10012549  push    0; grbit
0x1001254b  push    80000000h; cRow
0x10012550  push    dword ptr [ebx+4]; tableid
0x10012553  push    [ebp+sesid]; sesid
0x10012556  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1001255c  mov     ecx, [ebp+var_203CC]
0x10012562  mov     [ecx], eax
0x10012564  test    eax, eax
0x10012566  jns     short loc_10012572
0x10012568  mov     edi, 80004005h
0x1001256d  jmp     loc_10012DC5
0x10012572  lea     eax, [ebp+var_203D4]
0x10012578  push    0
0x1001257a  push    eax
0x1001257b  push    0
0x1001257d  test    esi, esi
0x1001257f  jz      short loc_1001259D
0x10012581  push    esi
0x10012582  push    offset aTables_0; "tables"
0x10012587  push    [ebp+arg_4]
0x1001258a  push    [ebp+sesid]
0x1001258d  call    ds:__imp__JetGetPropertyBlob@28; JetGetPropertyBlob(x,x,x,x,x,x,x)
0x10012593  mov     ecx, eax
0x10012595  mov     [ebp+var_203E4], ecx
0x1001259b  jmp     short loc_100125B1
0x1001259d  push    [ebp+arg_C]
0x100125a0  push    [ebp+sesid]
0x100125a3  call    ds:__imp__JetGetTablePropertyBlob@20; JetGetTablePropertyBlob(x,x,x,x,x)
0x100125a9  mov     ecx, eax
0x100125ab  mov     [ebp+var_203E4], eax
0x100125b1  mov     eax, [ebp+var_203CC]
0x100125b7  mov     [eax], ecx
0x100125b9  cmp     ecx, 0FFFFF88Eh
0x100125bf  jz      short loc_100125C5
0x100125c1  test    ecx, ecx
0x100125c3  js      short loc_10012568
0x100125c5  mov     eax, [ebx+8]
0x100125c8  xor     ecx, ecx
0x100125ca  mov     [ebp+var_203E0], ecx
0x100125d0  test    eax, eax
0x100125d2  jz      loc_10012DAB
0x100125d8  mov     edi, [ebp+var_203CC]
0x100125de  mov     edi, edi
0x100125e0  mov     eax, [ebp+var_203E8]
0x100125e6  push    0; pretinfo
0x100125e8  imul    esi, ecx, 68h ; 'h'
0x100125eb  push    0; grbit
0x100125ed  mov     [ebp+var_203DC], 0
0x100125f7  mov     [ebp+var_203D8], 0
0x10012601  add     esi, [eax+0Ch]
0x10012604  lea     eax, [ebp+pcbActual]
0x1001260a  push    eax; pcbActual
0x1001260b  push    1FEh; cbData
0x10012610  lea     eax, [ebp+pvData]
0x10012616  push    eax; pvData
0x10012617  push    dword ptr [ebx+34h]; columnid
0x1001261a  push    dword ptr [ebx+4]; tableid
0x1001261d  push    [ebp+sesid]; sesid
0x10012620  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10012626  mov     [edi], eax
0x10012628  test    eax, eax
0x1001262a  js      loc_10012568
0x10012630  mov     eax, [ebp+pcbActual]
0x10012636  and     eax, 0FFFFFFFEh
0x10012639  cmp     eax, 200h
0x1001263e  jnb     loc_10012DE1
0x10012644  xor     ecx, ecx
0x10012646  push    ecx; pretinfo
0x10012647  push    ecx; grbit
0x10012648  mov     [ebp+eax+pvData], cx
0x10012650  lea     eax, [ebp+pcbActual]
0x10012656  push    eax; pcbActual
0x10012657  push    1FEh; cbData
0x1001265c  lea     eax, [ebp+var_204]
0x10012662  push    eax; pvData
0x10012663  push    dword ptr [ebx+10h]; columnid
0x10012666  push    dword ptr [ebx+4]; tableid
0x10012669  push    [ebp+sesid]; sesid
0x1001266c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10012672  mov     [edi], eax
0x10012674  test    eax, eax
0x10012676  js      loc_10012568
0x1001267c  mov     eax, [ebp+pcbActual]
0x10012682  and     eax, 0FFFFFFFEh
0x10012685  cmp     eax, 200h
0x1001268a  jnb     loc_10012DE1
0x10012690  xor     ecx, ecx
0x10012692  mov     [ebp+eax+var_204], cx
0x1001269a  lea     ecx, [esi+8]
0x1001269d  call    ?FreeDBIDs@@YGXPAUtagDBID@@@Z; FreeDBIDs(tagDBID *)
0x100126a2  lea     ecx, [ebp+var_204]
0x100126a8  mov     dword ptr [esi+18h], 2
0x100126af  lea     edx, [ecx+2]
0x100126b2  mov     ax, [ecx]
0x100126b5  add     ecx, 2
0x100126b8  test    ax, ax
0x100126bb  jnz     short loc_100126B2
0x100126bd  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100126c2  sub     ecx, edx
0x100126c4  sar     ecx, 1
0x100126c6  lea     edx, ds:2[ecx*2]
0x100126cd  mov     ecx, [eax]
0x100126cf  push    edx
0x100126d0  push    eax
0x100126d1  mov     [ebp+var_203D0], edx
0x100126d7  mov     edi, [ecx+0Ch]
0x100126da  mov     ecx, edi
0x100126dc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100126e2  call    edi
0x100126e4  mov     [esi+1Ch], eax
0x100126e7  test    eax, eax
0x100126e9  jz      loc_10012DDA
0x100126ef  push    [ebp+var_203D0]; unsigned __int16 *
0x100126f5  lea     edx, [ebp+var_204]
0x100126fb  mov     ecx, eax
0x100126fd  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x10012702  mov     eax, [esi+4]
0x10012705  mov     [ebp+var_203D0], eax
0x1001270b  test    eax, eax
0x1001270d  jnz     short loc_1001272E
0x1001270f  mov     eax, [esi+18h]
0x10012712  sub     eax, 0
0x10012715  jz      short loc_10012725
0x10012717  sub     eax, 2
0x1001271a  jz      short loc_10012725
0x1001271c  sub     eax, 1
0x1001271f  jz      short loc_10012725
0x10012721  xor     eax, eax
0x10012723  jmp     short loc_10012728
0x10012725  mov     eax, [esi+1Ch]
0x10012728  mov     [ebp+var_203D0], eax
0x1001272e  push    0; pretinfo
0x10012730  push    0; grbit
0x10012732  lea     eax, [ebp+pcbActual]
0x10012738  push    eax; pcbActual
0x10012739  push    4; cbData
0x1001273b  lea     eax, [ebp+var_203C4]
0x10012741  push    eax; pvData
0x10012742  push    dword ptr [ebx+14h]; columnid
0x10012745  push    dword ptr [ebx+4]; tableid
0x10012748  push    [ebp+sesid]; sesid
0x1001274b  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10012751  mov     edi, [ebp+var_203CC]
0x10012757  mov     [edi], eax
0x10012759  test    eax, eax
0x1001275b  jz      short loc_10012772
0x1001275d  cmp     eax, 3ECh
0x10012762  jnz     loc_10012568
0x10012768  mov     eax, [ebp+var_203E0]
0x1001276e  inc     eax
0x1001276f  mov     [esi+20h], eax
0x10012772  mov     eax, [ebp+var_203C4]
0x10012778  push    0; pretinfo
0x1001277a  push    0; grbit
0x1001277c  mov     [esi+20h], eax
0x1001277f  lea     eax, [ebp+pcbActual]
0x10012785  push    eax; pcbActual
0x10012786  push    4; cbData
0x10012788  lea     eax, [ebp+var_203C4]
0x1001278e  push    eax; pvData
0x1001278f  push    dword ptr [ebx+18h]; columnid
0x10012792  push    dword ptr [ebx+4]; tableid
0x10012795  push    [ebp+sesid]; sesid
0x10012798  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1001279e  mov     [edi], eax
0x100127a0  test    eax, eax
0x100127a2  jz      short loc_100127B9
0x100127a4  cmp     eax, 3ECh
0x100127a9  jnz     loc_10012568
0x100127af  xor     eax, eax
0x100127b1  mov     [ebp+var_203C4], eax
0x100127b7  jmp     short loc_100127BF
0x100127b9  mov     eax, [ebp+var_203C4]
0x100127bf  mov     [esi+24h], eax
0x100127c2  mov     ecx, 83h
0x100127c7  mov     eax, [ebp+var_203C4]
0x100127cd  movzx   eax, word_100510F0[eax*8]
0x100127d5  mov     [esi+28h], ax
0x100127d9  cmp     cx, ax
0x100127dc  jnz     short loc_10012820
0x100127de  push    0; pretinfo
0x100127e0  push    0; grbit
0x100127e2  lea     eax, [ebp+pcbActual]
0x100127e8  push    eax; pcbActual
0x100127e9  push    4; cbData
0x100127eb  lea     eax, [ebp+var_203C4]
0x100127f1  push    eax; pvData
0x100127f2  push    dword ptr [ebx+1Ch]; columnid
0x100127f5  push    dword ptr [ebx+4]; tableid
0x100127f8  push    [ebp+sesid]; sesid
0x100127fb  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10012801  mov     [edi], eax
0x10012803  test    eax, eax
0x10012805  jnz     loc_10012568
0x1001280b  mov     al, byte ptr [ebp+var_203C4]
0x10012811  mov     [esi+30h], al
0x10012814  mov     eax, [ebp+var_203C4]
0x1001281a  shr     eax, 10h
0x1001281d  mov     [esi+31h], al
0x10012820  push    0; pretinfo
0x10012822  push    0; grbit
0x10012824  lea     eax, [ebp+pcbActual]
0x1001282a  push    eax; pcbActual
0x1001282b  push    4; cbData
0x1001282d  lea     eax, [ebp+var_203C4]
0x10012833  push    eax; pvData
0x10012834  push    dword ptr [ebx+20h]; columnid
0x10012837  push    dword ptr [ebx+4]; tableid
0x1001283a  push    [ebp+sesid]; sesid
0x1001283d  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10012843  mov     [edi], eax
0x10012845  test    eax, eax
0x10012847  jnz     loc_10012568
0x1001284d  mov     ecx, [esi+24h]
0x10012850  cmp     ecx, 1
0x10012853  jnz     short loc_1001285A
0x10012855  lea     eax, [ecx+1]
0x10012858  jmp     short loc_10012873
0x1001285a  mov     eax, [ebp+var_203C4]
0x10012860  test    eax, eax
0x10012862  jnz     short loc_10012879
0x10012864  cmp     ecx, 0Ah
0x10012867  jz      short loc_1001286E
0x10012869  cmp     ecx, 9
0x1001286c  jnz     short loc_10012879
0x1001286e  mov     eax, 1FEh
0x10012873  mov     [ebp+var_203C4], eax
0x10012879  mov     [esi+2Ch], eax
0x1001287c  mov     eax, [esi+24h]
0x1001287f  sub     eax, 0Ah
0x10012882  jz      short loc_100128A4
0x10012884  sub     eax, 1
0x10012887  jz      short loc_1001289D
0x10012889  sub     eax, 1
0x1001288c  jz      short loc_10012896
0x1001288e  mov     eax, [ebp+var_203C4]
0x10012894  jmp     short loc_100128AC
0x10012896  mov     eax, 1FFFFFFEh
0x1001289b  jmp     short loc_100128AC
0x1001289d  mov     eax, 3FFFFFFFh
0x100128a2  jmp     short loc_100128AC
0x100128a4  mov     eax, [ebp+var_203C4]
0x100128aa  shr     eax, 1
0x100128ac  push    0; pretinfo
0x100128ae  push    0; grbit
0x100128b0  mov     [esi+3Ch], eax
0x100128b3  lea     eax, [ebp+pcbActual]
0x100128b9  push    eax; pcbActual
0x100128ba  push    1FEh; cbData
0x100128bf  lea     eax, [ebp+var_204]
0x100128c5  push    eax; pvData
0x100128c6  push    dword ptr [ebx+2Ch]; columnid
0x100128c9  push    dword ptr [ebx+4]; tableid
0x100128cc  push    [ebp+sesid]; sesid
0x100128cf  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100128d5  mov     [edi], eax
0x100128d7  test    eax, eax
0x100128d9  js      loc_10012568
0x100128df  mov     eax, [ebp+pcbActual]
0x100128e5  and     eax, 0FFFFFFFEh
0x100128e8  cmp     eax, 200h
0x100128ed  jnb     loc_10012DE1
0x100128f3  xor     ecx, ecx
0x100128f5  mov     [ebp+eax+var_204], cx
0x100128fd  mov     eax, [esi+64h]
0x10012900  test    eax, eax
0x10012902  jz      short loc_10012914
0x10012904  push    eax; Block
0x10012905  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001290a  add     esp, 4
0x1001290d  mov     dword ptr [esi+64h], 0
0x10012914  lea     edi, [ebp+var_204]
0x1001291a  lea     ecx, [edi+2]
0x1001291d  nop     dword ptr [eax]
0x10012920  mov     ax, [edi]
0x10012923  add     edi, 2
  ... truncated ...
```
