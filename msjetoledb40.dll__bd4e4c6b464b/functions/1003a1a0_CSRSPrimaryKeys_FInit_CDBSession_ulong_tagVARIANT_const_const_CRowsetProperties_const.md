# CSRSPrimaryKeys::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003a1a0`
- end: `0x1003a8a9`
- name: `?FInit@CSRSPrimaryKeys@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1801`
- prototype: `int(CSRSPrimaryKeys *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035e60`
- `0x1003a1a0`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003a429`
- `msvcrt!_wcsicmp` at `0x1003a429`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a6e3`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a857`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a867`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a6e3`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a857`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a867`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003a835`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003a835`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003a458`
- `msjet40!__imp__JetGetIndexInfo@28` at `0x1003a458`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003a2df`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003a2df`
- `msjet40!__imp__JetMove@16` at `0x1003a303`
- `msjet40!__imp__JetMove@16` at `0x1003a6c1`
- `msjet40!__imp__JetMove@16` at `0x1003a6fa`
- `msjet40!__imp__JetMove@16` at `0x1003a303`
- `msjet40!__imp__JetMove@16` at `0x1003a6c1`
- `msjet40!__imp__JetMove@16` at `0x1003a6fa`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003a5b4`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003a5b4`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a391`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a3d9`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a4c0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a500`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a551`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a59c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a69a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a391`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a3d9`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a4c0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a500`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a551`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a59c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003a69a`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a5e0`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a5fe`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a61b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a65a`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a5e0`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a5fe`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a61b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003a65a`
- `msjet40!__imp__JetUpdate@20` at `0x1003a66b`
- `msjet40!__imp__JetUpdate@20` at `0x1003a66b`

## pseudocode

```c
int __userpurge CSRSPrimaryKeys::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSPrimaryKeys *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_COLUMNID *v7; // esi
  JET_SESID v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // ecx
  JET_ERR v15; // eax
  struct CDBSession *v16; // esi
  BOOL v17; // eax
  signed int IndexInfo; // eax
  unsigned int v19; // esi
  ColumnData *v20; // eax
  int v21; // ecx
  ColumnData *v22; // esi
  int v23; // ecx
  JET_TABLEID v24; // eax
  unsigned int v26; // [esp-24h] [ebp-27Ch]
  const struct _GUID *v27; // [esp+0h] [ebp-258h]
  const struct _GUID *v28; // [esp+4h] [ebp-254h]
  unsigned int ObjectInfo; // [esp+Ch] [ebp-24Ch] BYREF
  JET_COLUMNID *v30; // [esp+10h] [ebp-248h]
  JET_TABLEID v31; // [esp+14h] [ebp-244h] BYREF
  _DWORD *v32; // [esp+18h] [ebp-240h]
  ColumnData *v33; // [esp+1Ch] [ebp-23Ch] BYREF
  BOOL v34; // [esp+20h] [ebp-238h]
  unsigned int v35; // [esp+24h] [ebp-234h] BYREF
  struct CDBSession *v36; // [esp+28h] [ebp-230h]
  unsigned int pcbActual; // [esp+2Ch] [ebp-22Ch] BYREF
  unsigned int cbData; // [esp+30h] [ebp-228h] BYREF
  int v39; // [esp+34h] [ebp-224h]
  ColumnData *v40; // [esp+38h] [ebp-220h] BYREF
  int v41; // [esp+3Ch] [ebp-21Ch] BYREF
  int pvData; // [esp+40h] [ebp-218h] BYREF
  char v43[4]; // [esp+44h] [ebp-214h] BYREF
  unsigned int v44; // [esp+48h] [ebp-210h]
  int v45; // [esp+4Ch] [ebp-20Ch] BYREF
  JET_TABLEID tableid; // [esp+50h] [ebp-208h]
  unsigned int v47; // [esp+54h] [ebp-204h]
  JET_COLUMNID v48; // [esp+5Ch] [ebp-1FCh]
  JET_COLUMNID columnid; // [esp+60h] [ebp-1F8h]
  int v50; // [esp+7Ch] [ebp-1DCh] BYREF
  JET_TABLEID v51; // [esp+80h] [ebp-1D8h]
  unsigned int v52; // [esp+84h] [ebp-1D4h]
  JET_COLUMNID v53; // [esp+88h] [ebp-1D0h]
  JET_COLUMNID v54; // [esp+8Ch] [ebp-1CCh]
  JET_COLUMNID v55; // [esp+9Ch] [ebp-1BCh]
  JET_COLUMNID v56; // [esp+A0h] [ebp-1B8h]
  JET_COLUMNID v57; // [esp+B4h] [ebp-1A4h]
  wchar_t String1[68]; // [esp+B8h] [ebp-1A0h] BYREF
  _WORD v59[68]; // [esp+140h] [ebp-118h] BYREF
  unsigned __int16 v60[70]; // [esp+1C8h] [ebp-90h] BYREF

  v41 = a2;
  v7 = 0;
  v32 = a1;
  v36 = a4;
  v44 = a5;
  ObjectInfo = 0;
  v34 = 1;
  tableid = -1;
  v8 = a1[4];
  if ( this )
  {
    if ( !a4
      || (unsigned int)this > 3
      || (v9 = *(unsigned __int16 *)a4, (_WORD)v9) && v9 != 1 && (v9 != 8 || *((_DWORD *)a4 + 2))
      || (unsigned int)this > 1
      && (v10 = *((unsigned __int16 *)a4 + 8), (_WORD)v10)
      && v10 != 1
      && (v10 != 8 || *((_DWORD *)a4 + 6))
      || (unsigned int)this > 2 && (v11 = *((unsigned __int16 *)a4 + 16), (_WORD)v11) && v11 != 1 && v11 != 8 )
    {
      v12 = a1[5];
      v13 = -2147024809;
      v14 = a1[4];
LABEL_78:
      if ( !JetGetDatabaseInfo(v14, v12, &v41, 4, 3) )
        CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v27, (int)v28);
      goto LABEL_80;
    }
  }
  v7 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                         *(_DWORD *)(*(_DWORD *)Sys + 12),
                         Sys,
                         32);
  v30 = v7;
  if ( v7 )
  {
    v13 = SRSCreateTempTable(7, v32, &v31, v7, 0);
    if ( v13 >= 0 )
    {
      if ( (unsigned int)this >= 3 )
        v34 = *((_WORD *)v36 + 16) != 1;
      ObjectInfo = JetGetObjectInfo(v8, v32[5], 0, L"tables", 0, &v45, 48, 1);
      if ( ObjectInfo )
      {
        v13 = -2147467259;
      }
      else
      {
        v15 = JetMove(v8, tableid, 0x80000000, 0);
        ObjectInfo = v15;
        if ( v15 == -1603 || !v15 )
        {
          v16 = v36;
          if ( (unsigned int)this < 3 )
          {
            v17 = v34;
          }
          else
          {
            v17 = v34;
            if ( *((_WORD *)v36 + 16) == 8 )
            {
              if ( !*((_DWORD *)v36 + 10) )
                v17 = 0;
              v34 = v17;
            }
          }
          v39 = 0;
          if ( v47 )
          {
            while ( v17 )
            {
              v59[0] = 0;
              String1[0] = 0;
              ObjectInfo = JetRetrieveColumn(v8, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
              if ( ObjectInfo )
                goto LABEL_73;
              if ( pvData == 1 || pvData == 4 || pvData == 6 )
              {
                ObjectInfo = JetRetrieveColumn(v8, tableid, v48, String1, 0x81u, &pcbActual, 0, 0);
                if ( ObjectInfo )
                  goto LABEL_68;
                if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
LABEL_88:
                  __report_rangecheckfailure();
                *(wchar_t *)((char *)String1 + (pcbActual & 0xFFFFFFFE)) = 0;
                if ( this != (CSRSPrimaryKeys *)3
                  || !*((_WORD *)v16 + 16)
                  || *((_DWORD *)v16 + 10) && !__wcsicmp(String1, *((const wchar_t **)v16 + 10)) )
                {
                  IndexInfo = JetGetIndexInfo(v8, v32[5], String1, 0, &v50, 60, 1);
                  ObjectInfo = IndexInfo;
                  if ( IndexInfo > -1404 )
                  {
                    if ( IndexInfo )
                      goto LABEL_68;
                    v13 = 0;
                    v19 = 0;
                    if ( v52 )
                    {
                      while ( 1 )
                      {
                        ObjectInfo = JetRetrieveColumn(v8, v51, v54, v43, 4u, &v35, 0, 0);
                        if ( ObjectInfo )
                          break;
                        if ( (v43[0] & 2) != 0 )
                        {
                          ObjectInfo = JetRetrieveColumn(v8, v51, v57, v59, 0x81u, &cbData, 0, 0);
                          if ( ObjectInfo )
                            break;
                          if ( (cbData & 0xFFFFFFFE) >= 0x82 )
                            goto LABEL_88;
                          *(_WORD *)((char *)v59 + (cbData & 0xFFFFFFFE)) = 0;
                          ObjectInfo = JetRetrieveColumn(v8, v51, v53, v60, 0x80u, &v35, 0, 0);
                          if ( ObjectInfo )
                            break;
                          if ( (v35 & 0xFFFFFFFE) >= 0x82 )
                            goto LABEL_88;
                          *(unsigned __int16 *)((char *)v60 + (v35 & 0xFFFFFFFE)) = 0;
                          ObjectInfo = JetRetrieveColumn(v8, v51, v56, &v33, 4u, &v35, 0, 0);
                          if ( ObjectInfo )
                            break;
                          ObjectInfo = JetPrepareUpdate(v8, v31, 0);
                          if ( ObjectInfo )
                            break;
                          JetSetColumn(v8, v31, v30[2], String1, pcbActual, 0, 0);
                          JetSetColumn(v8, v31, v30[3], v59, cbData, 0, 0);
                          v33 = (ColumnData *)((char *)v33 + 1);
                          JetSetColumn(v8, v31, v30[6], &v33, 4u, 0, 0);
                          v33 = (ColumnData *)((char *)v33 - 1);
                          v35 = 2 * wcslen(v60);
                          JetSetColumn(v8, v31, v30[7], v60, v35, 0, 0);
                          ObjectInfo = JetUpdate(v8, v31, 0, 0, 0);
                          if ( ObjectInfo )
                            break;
                          ObjectInfo = JetRetrieveColumn(v8, v51, v55, &v40, 4u, &v35, 0, 0);
                          if ( ObjectInfo )
                            break;
                          v13 = 0;
                          if ( (ColumnData *)((char *)v40 - 1) == v33 )
                            goto LABEL_65;
                        }
                        ++v19;
                        ObjectInfo = JetMove(v8, v51, 1, 0);
                        v13 = 0;
                        if ( v19 >= v52 )
                          goto LABEL_65;
                      }
LABEL_68:
                      v13 = -2147467259;
                      goto LABEL_73;
                    }
LABEL_65:
                    ObjectInfo = JetCloseTable(v8, v51);
                    if ( ObjectInfo )
                      goto LABEL_68;
                  }
                  else
                  {
                    if ( IndexInfo != -1404 && IndexInfo != -1907 && IndexInfo != -1811 )
                      goto LABEL_68;
                    v13 = 0;
                    ObjectInfo = 0;
                  }
                }
              }
              ObjectInfo = JetMove(v8, tableid, 1, 0);
              if ( ++v39 >= v47 )
                break;
              v16 = v36;
              v17 = v34;
            }
          }
          v20 = (ColumnData *)operator new(0x20u);
          v22 = v20;
          v40 = v20;
          if ( v20 )
          {
            *((_DWORD *)v20 + 1) = 0;
            *((_DWORD *)v20 + 2) = 0;
            *((_DWORD *)v20 + 3) = 0;
            *(_DWORD *)v20 = &ColumnDataWithFakeNamesAndDBTYPES::`vftable';
            *((_DWORD *)v20 + 4) = 0;
            *((_DWORD *)v20 + 5) = 0;
            *((_DWORD *)v20 + 6) = 0;
            *((_DWORD *)v20 + 7) = 0;
            *((_DWORD *)v20 + 4) = dword_10008640;
            *((_DWORD *)v20 + 5) = &SRSPrimaryKeysNames;
            *((_DWORD *)v20 + 7) = 0;
            v13 = ColumnData::FInit(v20, v8, v32[5], v31, (int *)&ObjectInfo, 0, v21);
            if ( v13 >= 0 )
            {
              v23 = v41;
              v26 = v44;
              *((_DWORD *)v22 + 1) = 8;
              v13 = CRowset::FInit(v23, 0, v32, 0, 0, 0, v31, v26, 1, 0, 0, v22, 1, 0, 0, &GUID_NULL);
            }
          }
          else
          {
            v13 = -2147024882;
          }
LABEL_73:
          v7 = v30;
        }
        else
        {
          v13 = -2147467259;
        }
      }
    }
  }
  else
  {
    v13 = -2147024882;
  }
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v27, v28);
    goto LABEL_80;
  }
  if ( v13 < 0 )
  {
    v12 = v32[5];
    v14 = v32[4];
    if ( v13 != -2147024882 )
      goto LABEL_78;
  }
LABEL_80:
  v24 = tableid;
  if ( tableid != -1 )
  {
    JetCloseTable(v8, tableid);
    v24 = tableid;
  }
  if ( v13 < 0 )
    JetCloseTable(v8, v24);
  if ( v7 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v7);
  return v13;
}

```

## disassembly

```asm
0x1003a1a0  mov     edi, edi
0x1003a1a2  push    ebp
0x1003a1a3  mov     ebp, esp
0x1003a1a5  and     esp, 0FFFFFFF8h
0x1003a1a8  sub     esp, 24Ch
0x1003a1ae  mov     eax, ___security_cookie
0x1003a1b3  xor     eax, esp
0x1003a1b5  mov     [esp+24Ch+var_4], eax
0x1003a1bc  mov     eax, [ebp+arg_8]
0x1003a1bf  push    ebx
0x1003a1c0  mov     ebx, [ebp+this]
0x1003a1c3  push    esi; int
0x1003a1c4  mov     [esp+254h+var_21C], ecx
0x1003a1c8  xor     esi, esi
0x1003a1ca  mov     ecx, [ebp+arg_4]
0x1003a1cd  mov     [esp+254h+var_240], edx
0x1003a1d1  mov     [esp+254h+var_230], ecx
0x1003a1d5  mov     [esp+254h+var_210], eax
0x1003a1d9  mov     [esp+254h+var_24C], 0
0x1003a1e1  mov     [esp+254h+var_238], 1
0x1003a1e9  mov     [esp+254h+tableid], 0FFFFFFFFh
0x1003a1f1  push    edi; struct _GUID *
0x1003a1f2  mov     edi, [edx+10h]
0x1003a1f5  test    ebx, ebx
0x1003a1f7  jz      short loc_1003A25D
0x1003a1f9  test    ecx, ecx
0x1003a1fb  jz      short loc_1003A24E
0x1003a1fd  cmp     ebx, 3
0x1003a200  ja      short loc_1003A24E
0x1003a202  movzx   eax, word ptr [ecx]
0x1003a205  test    ax, ax
0x1003a208  jz      short loc_1003A219
0x1003a20a  cmp     eax, 1
0x1003a20d  jz      short loc_1003A219
0x1003a20f  cmp     eax, 8
0x1003a212  jnz     short loc_1003A24E
0x1003a214  cmp     [ecx+8], esi
0x1003a217  jnz     short loc_1003A24E
0x1003a219  cmp     ebx, 1
0x1003a21c  jbe     short loc_1003A236
0x1003a21e  movzx   eax, word ptr [ecx+10h]
0x1003a222  test    ax, ax
0x1003a225  jz      short loc_1003A236
0x1003a227  cmp     eax, 1
0x1003a22a  jz      short loc_1003A236
0x1003a22c  cmp     eax, 8
0x1003a22f  jnz     short loc_1003A24E
0x1003a231  cmp     [ecx+18h], esi
0x1003a234  jnz     short loc_1003A24E
0x1003a236  cmp     ebx, 2
0x1003a239  jbe     short loc_1003A25D
0x1003a23b  movzx   eax, word ptr [ecx+20h]
0x1003a23f  test    ax, ax
0x1003a242  jz      short loc_1003A25D
0x1003a244  cmp     eax, 1
0x1003a247  jz      short loc_1003A25D
0x1003a249  cmp     eax, 8
0x1003a24c  jz      short loc_1003A25D
0x1003a24e  mov     eax, [edx+14h]
0x1003a251  mov     ebx, 80070057h
0x1003a256  mov     ecx, edi
0x1003a258  jmp     loc_1003A82A
0x1003a25d  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003a263  push    20h ; ' '
0x1003a265  push    ecx
0x1003a266  mov     eax, [ecx]
0x1003a268  mov     esi, [eax+0Ch]
0x1003a26b  mov     ecx, esi
0x1003a26d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003a273  call    esi
0x1003a275  mov     esi, eax
0x1003a277  mov     [esp+258h+var_248], esi
0x1003a27b  test    esi, esi
0x1003a27d  jnz     short loc_1003A289
0x1003a27f  mov     ebx, 8007000Eh
0x1003a284  jmp     loc_1003A7F4
0x1003a289  mov     edx, [esp+258h+var_240]
0x1003a28d  lea     eax, [esp+258h+var_244]
0x1003a291  push    0
0x1003a293  push    esi
0x1003a294  push    eax
0x1003a295  mov     ecx, 7
0x1003a29a  call    SRSCreateTempTable
0x1003a29f  mov     ebx, eax
0x1003a2a1  test    ebx, ebx
0x1003a2a3  js      loc_1003A7F4
0x1003a2a9  cmp     [ebp+this], 3
0x1003a2ad  jb      short loc_1003A2C5
0x1003a2af  mov     eax, [esp+258h+var_230]
0x1003a2b3  xor     ecx, ecx
0x1003a2b5  mov     edx, 1
0x1003a2ba  cmp     dx, [eax+20h]
0x1003a2be  setnz   cl
0x1003a2c1  mov     [esp+258h+var_238], ecx
0x1003a2c5  push    1
0x1003a2c7  push    30h ; '0'
0x1003a2c9  lea     eax, [esp+260h+var_20C]
0x1003a2cd  push    eax
0x1003a2ce  mov     eax, [esp+264h+var_240]
0x1003a2d2  push    0
0x1003a2d4  push    offset aTables_0; "tables"
0x1003a2d9  push    0
0x1003a2db  push    dword ptr [eax+14h]
0x1003a2de  push    edi
0x1003a2df  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003a2e5  mov     [esp+258h+var_24C], eax
0x1003a2e9  test    eax, eax
0x1003a2eb  jz      short loc_1003A2F7
0x1003a2ed  mov     ebx, 80004005h
0x1003a2f2  jmp     loc_1003A7F4
0x1003a2f7  push    0; grbit
0x1003a2f9  push    80000000h; cRow
0x1003a2fe  push    [esp+260h+tableid]; tableid
0x1003a302  push    edi; sesid
0x1003a303  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003a309  mov     [esp+258h+var_24C], eax
0x1003a30d  cmp     eax, 0FFFFF9BDh
0x1003a312  jz      short loc_1003A322
0x1003a314  test    eax, eax
0x1003a316  jz      short loc_1003A322
0x1003a318  mov     ebx, 80004005h
0x1003a31d  jmp     loc_1003A7F4
0x1003a322  cmp     [ebp+this], 3
0x1003a326  mov     esi, [esp+258h+var_230]
0x1003a32a  jb      short loc_1003A349
0x1003a32c  mov     eax, 8
0x1003a331  cmp     ax, [esi+20h]
0x1003a335  mov     eax, [esp+258h+var_238]
0x1003a339  jnz     short loc_1003A34D
0x1003a33b  xor     ecx, ecx
0x1003a33d  cmp     [esi+28h], ecx
0x1003a340  cmovz   eax, ecx
0x1003a343  mov     [esp+258h+var_238], eax
0x1003a347  jmp     short loc_1003A34D
0x1003a349  mov     eax, [esp+258h+var_238]
0x1003a34d  cmp     [esp+258h+var_204], 0
0x1003a352  mov     [esp+258h+var_224], 0
0x1003a35a  jbe     loc_1003A72A
0x1003a360  test    eax, eax
0x1003a362  jz      loc_1003A72A
0x1003a368  xor     eax, eax
0x1003a36a  push    eax; pretinfo
0x1003a36b  push    eax; grbit
0x1003a36c  mov     [esp+260h+var_118], ax
0x1003a374  mov     [esp+260h+String1], ax
0x1003a37c  lea     eax, [esp+260h+pcbActual]
0x1003a380  push    eax; pcbActual
0x1003a381  push    4; cbData
0x1003a383  lea     eax, [esp+268h+pvData]
0x1003a387  push    eax; pvData
0x1003a388  push    [esp+26Ch+columnid]; columnid
0x1003a38c  push    [esp+270h+tableid]; tableid
0x1003a390  push    edi; sesid
0x1003a391  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a397  mov     [esp+258h+var_24C], eax
0x1003a39b  test    eax, eax
0x1003a39d  jnz     loc_1003A7F0
0x1003a3a3  mov     eax, [esp+258h+pvData]
0x1003a3a7  sub     eax, 1
0x1003a3aa  jz      short loc_1003A3BA
0x1003a3ac  sub     eax, 3
0x1003a3af  jz      short loc_1003A3BA
0x1003a3b1  sub     eax, 2
0x1003a3b4  jnz     loc_1003A6F1
0x1003a3ba  push    0; pretinfo
0x1003a3bc  push    0; grbit
0x1003a3be  lea     eax, [esp+260h+pcbActual]
0x1003a3c2  push    eax; pcbActual
0x1003a3c3  push    81h; cbData
0x1003a3c8  lea     eax, [esp+268h+String1]
0x1003a3cf  push    eax; pvData
0x1003a3d0  push    [esp+26Ch+var_1FC]; columnid
0x1003a3d4  push    [esp+270h+tableid]; tableid
0x1003a3d8  push    edi; sesid
0x1003a3d9  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a3df  mov     [esp+258h+var_24C], eax
0x1003a3e3  test    eax, eax
0x1003a3e5  jnz     loc_1003A720
0x1003a3eb  mov     eax, [esp+258h+pcbActual]
0x1003a3ef  and     eax, 0FFFFFFFEh
0x1003a3f2  cmp     eax, 82h
0x1003a3f7  jnb     loc_1003A8A4
0x1003a3fd  xor     ecx, ecx
0x1003a3ff  cmp     [ebp+this], 3
0x1003a403  mov     [esp+eax+258h+String1], cx
0x1003a40b  jnz     short loc_1003A43A
0x1003a40d  xor     eax, eax
0x1003a40f  cmp     ax, [esi+20h]
0x1003a413  jz      short loc_1003A43A
0x1003a415  mov     eax, [esi+28h]
0x1003a418  test    eax, eax
0x1003a41a  jz      loc_1003A6F1
0x1003a420  push    eax; String2
0x1003a421  lea     eax, [esp+25Ch+String1]
0x1003a428  push    eax; String1
0x1003a429  call    ds:__imp___wcsicmp
0x1003a42f  add     esp, 8
0x1003a432  test    eax, eax
0x1003a434  jnz     loc_1003A6F1
0x1003a43a  push    1
0x1003a43c  push    3Ch ; '<'
0x1003a43e  lea     eax, [esp+260h+var_1DC]
0x1003a445  push    eax
0x1003a446  push    0
0x1003a448  lea     eax, [esp+268h+String1]
0x1003a44f  push    eax
0x1003a450  mov     eax, [esp+26Ch+var_240]
0x1003a454  push    dword ptr [eax+14h]
0x1003a457  push    edi
0x1003a458  call    ds:__imp__JetGetIndexInfo@28; JetGetIndexInfo(x,x,x,x,x,x,x)
0x1003a45e  mov     [esp+258h+var_24C], eax
0x1003a462  cmp     eax, 0FFFFFA84h
0x1003a467  jg      short loc_1003A488
0x1003a469  jz      short loc_1003A47D
0x1003a46b  cmp     eax, 0FFFFF88Dh
0x1003a470  jz      short loc_1003A47D
0x1003a472  cmp     eax, 0FFFFF8EDh
0x1003a477  jnz     loc_1003A720
0x1003a47d  xor     ebx, ebx
0x1003a47f  mov     [esp+258h+var_24C], ebx
0x1003a483  jmp     loc_1003A6F1
0x1003a488  test    eax, eax
0x1003a48a  jnz     loc_1003A720
0x1003a490  xor     ebx, ebx
0x1003a492  xor     esi, esi
0x1003a494  cmp     [esp+258h+var_1D4], ebx
0x1003a49b  jbe     loc_1003A6DB
0x1003a4a1  push    0; pretinfo
0x1003a4a3  push    0; grbit
0x1003a4a5  lea     eax, [esp+260h+var_234]
0x1003a4a9  push    eax; pcbActual
0x1003a4aa  push    4; cbData
0x1003a4ac  lea     eax, [esp+268h+var_214]
0x1003a4b0  push    eax; pvData
0x1003a4b1  push    [esp+26Ch+var_1CC]; columnid
0x1003a4b8  push    [esp+270h+var_1D8]; tableid
0x1003a4bf  push    edi; sesid
0x1003a4c0  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a4c6  mov     [esp+258h+var_24C], eax
0x1003a4ca  test    eax, eax
0x1003a4cc  jnz     loc_1003A720
0x1003a4d2  test    [esp+258h+var_214], 2
0x1003a4d7  jz      loc_1003A6B5
0x1003a4dd  push    eax; pretinfo
0x1003a4de  push    eax; grbit
0x1003a4df  lea     eax, [esp+260h+cbData]
0x1003a4e3  push    eax; pcbActual
0x1003a4e4  push    81h; cbData
0x1003a4e9  lea     eax, [esp+268h+var_118]
0x1003a4f0  push    eax; pvData
0x1003a4f1  push    [esp+26Ch+var_1A4]; columnid
0x1003a4f8  push    [esp+270h+var_1D8]; tableid
0x1003a4ff  push    edi; sesid
0x1003a500  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a506  mov     [esp+258h+var_24C], eax
0x1003a50a  test    eax, eax
0x1003a50c  jnz     loc_1003A720
0x1003a512  mov     eax, [esp+258h+cbData]
0x1003a516  and     eax, 0FFFFFFFEh
0x1003a519  cmp     eax, 82h
0x1003a51e  jnb     loc_1003A8A4
0x1003a524  xor     ecx, ecx
0x1003a526  push    ecx; pretinfo
0x1003a527  push    ecx; grbit
0x1003a528  mov     [esp+eax+260h+var_118], cx
0x1003a530  lea     eax, [esp+260h+var_234]
0x1003a534  push    eax; pcbActual
0x1003a535  push    80h; cbData
0x1003a53a  lea     eax, [esp+268h+var_90]
0x1003a541  push    eax; pvData
0x1003a542  push    [esp+26Ch+var_1D0]; columnid
0x1003a549  push    [esp+270h+var_1D8]; tableid
0x1003a550  push    edi; sesid
0x1003a551  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a557  mov     [esp+258h+var_24C], eax
0x1003a55b  test    eax, eax
0x1003a55d  jnz     loc_1003A720
0x1003a563  mov     eax, [esp+258h+var_234]
0x1003a567  and     eax, 0FFFFFFFEh
0x1003a56a  cmp     eax, 82h
0x1003a56f  jnb     loc_1003A8A4
0x1003a575  xor     ecx, ecx
0x1003a577  push    ecx; pretinfo
0x1003a578  push    ecx; grbit
0x1003a579  mov     [esp+eax+260h+var_90], cx
0x1003a581  lea     eax, [esp+260h+var_234]
0x1003a585  push    eax; pcbActual
0x1003a586  push    4; cbData
0x1003a588  lea     eax, [esp+268h+var_23C]
0x1003a58c  push    eax; pvData
0x1003a58d  push    [esp+26Ch+var_1B8]; columnid
0x1003a594  push    [esp+270h+var_1D8]; tableid
0x1003a59b  push    edi; sesid
0x1003a59c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003a5a2  mov     [esp+258h+var_24C], eax
0x1003a5a6  test    eax, eax
0x1003a5a8  jnz     loc_1003A720
0x1003a5ae  push    eax; prep
0x1003a5af  push    [esp+25Ch+var_244]; tableid
0x1003a5b3  push    edi; sesid
  ... truncated ...
```
