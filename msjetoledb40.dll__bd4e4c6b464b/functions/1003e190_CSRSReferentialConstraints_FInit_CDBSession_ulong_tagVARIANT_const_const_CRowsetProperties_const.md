# CSRSReferentialConstraints::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003e190`
- end: `0x1003e7be`
- name: `?FInit@CSRSReferentialConstraints@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1582`
- prototype: `int(CSRSReferentialConstraints *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
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
- `0x1003e190`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003e461`
- `msvcrt!_wcsicmp` at `0x1003e461`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e635`
- `msjet40!__imp__JetCloseTable@8` at `0x1003e635`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003e76f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003e76f`
- `msjet40!__imp__JetMove@16` at `0x1003e60a`
- `msjet40!__imp__JetMove@16` at `0x1003e60a`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003e4af`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003e4af`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003e41b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003e493`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003e41b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003e493`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e4dc`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e4fd`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e517`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e578`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e5d8`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e4dc`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e4fd`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e517`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e578`
- `msjet40!__imp__JetSetColumn@28` at `0x1003e5d8`
- `msjet40!__imp__JetUpdate@20` at `0x1003e5eb`
- `msjet40!__imp__JetUpdate@20` at `0x1003e5eb`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003e393`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x1003e393`

## pseudocode

```c
int __userpurge CSRSReferentialConstraints::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSReferentialConstraints *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  struct CDBSession *v7; // edx
  JET_COLUMNID *v8; // esi
  JET_SESID v9; // eax
  int v10; // edi
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  bool v16; // zf
  int v17; // eax
  int v18; // edi
  int v19; // eax
  int v20; // ecx
  JET_SESID v21; // edi
  unsigned int RelationshipInfo; // eax
  JET_TABLEID v23; // eax
  unsigned int v24; // ecx
  __int128 *v25; // edx
  __int128 *v26; // edx
  JET_ERR v27; // eax
  ColumnData *v28; // eax
  int v29; // ecx
  _DWORD *v30; // ebx
  ColumnData *v31; // esi
  int v32; // ecx
  unsigned int v34; // [esp-24h] [ebp-174h]
  const struct _GUID *v35; // [esp+0h] [ebp-150h]
  const struct _GUID *v36; // [esp+4h] [ebp-14Ch]
  unsigned int v37; // [esp+Ch] [ebp-144h] BYREF
  unsigned int v38; // [esp+10h] [ebp-140h]
  int v39; // [esp+14h] [ebp-13Ch] BYREF
  JET_SESID sesid; // [esp+18h] [ebp-138h]
  int v41; // [esp+1Ch] [ebp-134h] BYREF
  struct CDBSession *v42; // [esp+20h] [ebp-130h]
  int v43; // [esp+24h] [ebp-12Ch]
  unsigned int pcbActual; // [esp+28h] [ebp-128h] BYREF
  int v45; // [esp+2Ch] [ebp-124h]
  JET_COLUMNID *v46; // [esp+30h] [ebp-120h]
  unsigned int v47; // [esp+34h] [ebp-11Ch] BYREF
  JET_TABLEID v48; // [esp+38h] [ebp-118h] BYREF
  _DWORD *v49; // [esp+3Ch] [ebp-114h]
  _BYTE v50[4]; // [esp+40h] [ebp-110h] BYREF
  JET_TABLEID tableid; // [esp+44h] [ebp-10Ch]
  unsigned int v52; // [esp+48h] [ebp-108h]
  JET_COLUMNID columnid; // [esp+4Ch] [ebp-104h]
  JET_COLUMNID v54; // [esp+50h] [ebp-100h]
  wchar_t pvData[66]; // [esp+6Ch] [ebp-E4h] BYREF
  __int128 v56; // [esp+F0h] [ebp-60h] BYREF
  __int64 v57; // [esp+100h] [ebp-50h]
  __int128 v58; // [esp+108h] [ebp-48h] BYREF
  __int128 v59; // [esp+118h] [ebp-38h] BYREF
  int v60; // [esp+128h] [ebp-28h]
  __int128 v61; // [esp+12Ch] [ebp-24h] BYREF
  wchar_t v62; // [esp+13Ch] [ebp-14h]
  __int64 v63; // [esp+140h] [ebp-10h] BYREF
  wchar_t v64; // [esp+148h] [ebp-8h]

  v49 = a1;
  v39 = a2;
  v38 = a5;
  v58 = *(_OWORD *)L"CASCADE";
  v62 = aSetNull[8];
  v7 = a4;
  v61 = *(_OWORD *)L"SET NULL";
  v60 = *(_DWORD *)L"N";
  v56 = *(_OWORD *)L"SET DEFAULT";
  v8 = 0;
  v64 = aFull[4];
  v9 = v49[4];
  v57 = *(_QWORD *)L"ULT";
  v10 = 1;
  v11 = 0;
  v42 = a4;
  v47 = 0;
  sesid = v9;
  v43 = 1;
  v45 = 0;
  v59 = *(_OWORD *)L"NO ACTION";
  v63 = *(_QWORD *)L"FULL";
  if ( this )
  {
    if ( !a4
      || (unsigned int)this > 3
      || (v12 = *(unsigned __int16 *)a4, (_WORD)v12) && v12 != 1 && (v12 != 8 || *((_DWORD *)a4 + 2))
      || (unsigned int)this > 1
      && (v13 = *((unsigned __int16 *)a4 + 8), (_WORD)v13)
      && v13 != 1
      && (v13 != 8 || *((_DWORD *)a4 + 6))
      || (unsigned int)this > 2 && (v14 = *((unsigned __int16 *)a4 + 16), (_WORD)v14) && v14 != 1 && v14 != 8 )
    {
      v18 = -2147024809;
      v19 = v49[5];
      v20 = v49[4];
LABEL_69:
      if ( !JetGetDatabaseInfo(v20, v19, &v39, 4, 3) )
        CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v35, (int)v36);
      goto LABEL_71;
    }
    if ( (unsigned int)this >= 3 )
    {
      v15 = *((unsigned __int16 *)a4 + 16);
      if ( (_WORD)v15 )
      {
        if ( v15 != 1 )
        {
          v16 = *((_DWORD *)a4 + 10) == 0;
          v45 = *((_DWORD *)a4 + 10);
          v7 = v42;
          v11 = 1;
          if ( v16 )
            v10 = 0;
        }
      }
      v17 = 0;
      if ( *((_WORD *)v7 + 16) != 1 )
        v17 = v10;
      v43 = v17;
    }
  }
  v8 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                         *(_DWORD *)(*(_DWORD *)Sys + 12),
                         Sys,
                         40);
  v46 = v8;
  if ( !v8 )
  {
    v18 = -2147024882;
LABEL_64:
    v30 = v49;
    goto LABEL_65;
  }
  v18 = SRSCreateTempTable(12, v49, &v48, v8, 2u);
  if ( v18 < 0 )
    goto LABEL_64;
  v21 = sesid;
  RelationshipInfo = JetGetRelationshipInfo(sesid, v49[5], 0, v45, v50, 44);
  v47 = RelationshipInfo;
  if ( RelationshipInfo == -1907 || RelationshipInfo == -1305 )
  {
    v23 = -1;
    v52 = 0;
    tableid = -1;
  }
  else
  {
    if ( RelationshipInfo )
    {
LABEL_63:
      v18 = -2147467259;
      goto LABEL_64;
    }
    v23 = tableid;
  }
  v24 = 0;
  v45 = 0;
  if ( v43 == 1 )
  {
    while ( v24 < v52 )
    {
      v47 = JetRetrieveColumn(v21, v23, columnid, pvData, 0x81u, &pcbActual, 0, 0);
      if ( v47 )
        goto LABEL_63;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
        __report_rangecheckfailure();
      *(wchar_t *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      if ( !v11 || !__wcsicmp(pvData, *((const wchar_t **)v42 + 10)) )
      {
        v47 = JetRetrieveColumn(v21, tableid, v54, &v41, 4u, &v37, 0, 0);
        if ( v47 )
          goto LABEL_63;
        v47 = JetPrepareUpdate(v21, v48, 0);
        if ( v47 )
          goto LABEL_63;
        JetSetColumn(v21, v48, v8[2], pvData, pcbActual, 0, 0);
        JetSetColumn(v21, v48, v8[5], pvData, pcbActual, 0, 0);
        JetSetColumn(v21, v48, v8[6], &v63, 8u, 0, 0);
        if ( (v41 & 0x100) != 0 )
        {
          v25 = &v58;
        }
        else if ( (v41 & 0x200) != 0 )
        {
          v25 = &v61;
        }
        else
        {
          v25 = &v56;
          if ( (v41 & 0x300) == 0 )
            v25 = &v59;
        }
        JetSetColumn(v21, v48, v46[7], v25, 2 * wcslen((const unsigned __int16 *)v25), 0, 0);
        if ( (v41 & 0x1000) != 0 )
        {
          v26 = &v58;
        }
        else if ( (v41 & 0x2000) != 0 )
        {
          v26 = &v61;
        }
        else
        {
          v26 = &v56;
          if ( (v41 & 0x3000) == 0 )
            v26 = &v59;
        }
        v8 = v46;
        JetSetColumn(v21, v48, v46[8], v26, 2 * wcslen((const unsigned __int16 *)v26), 0, 0);
        v47 = JetUpdate(v21, v48, 0, 0, 0);
        if ( v47 )
          goto LABEL_63;
      }
      v27 = JetMove(v21, tableid, 1, 0);
      v24 = v45 + 1;
      v47 = v27;
      v23 = tableid;
      ++v45;
    }
  }
  if ( v23 != -1 )
  {
    v47 = JetCloseTable(v21, v23);
    if ( v47 )
      goto LABEL_63;
  }
  v28 = (ColumnData *)operator new(0x20u);
  v30 = v49;
  v31 = v28;
  sesid = (JET_SESID)v28;
  if ( v28 )
  {
    *((_DWORD *)v28 + 1) = 0;
    *((_DWORD *)v28 + 2) = 0;
    *((_DWORD *)v28 + 3) = 0;
    *(_DWORD *)v28 = &ColumnDataWithFakeNamesAndDBTYPES::`vftable';
    *((_DWORD *)v28 + 4) = 0;
    *((_DWORD *)v28 + 5) = 0;
    *((_DWORD *)v28 + 6) = 0;
    *((_DWORD *)v28 + 7) = 0;
    *((_DWORD *)v28 + 4) = 0;
    *((_DWORD *)v28 + 5) = &SRSReferentialConstraintsNames;
    *((_DWORD *)v28 + 7) = 0;
    v18 = ColumnData::FInit(v28, v21, v30[5], v48, (int *)&v47, 0, v29);
    if ( v18 >= 0 )
    {
      v32 = v39;
      v34 = v38;
      *((_DWORD *)v31 + 1) = 10;
      v18 = CRowset::FInit(v32, 0, v30, 0, 0, 0, v48, v34, 1, 0, 0, v31, 1, 0, 0, &GUID_NULL);
    }
    v8 = v46;
  }
  else
  {
    v8 = v46;
    v18 = -2147024882;
  }
LABEL_65:
  if ( v47 )
  {
    CExtError::SendJetErrortoOLEAuto(v47, (int)&IID_IDBSchemaRowset, (int)v35, v36);
    goto LABEL_71;
  }
  if ( v18 < 0 )
  {
    v19 = v30[5];
    v20 = v30[4];
    if ( v18 != -2147024882 )
      goto LABEL_69;
  }
LABEL_71:
  if ( v8 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v8);
  return v18;
}

```

## disassembly

```asm
0x1003e190  mov     edi, edi
0x1003e192  push    ebp
0x1003e193  mov     ebp, esp
0x1003e195  sub     esp, 144h
0x1003e19b  mov     eax, ___security_cookie
0x1003e1a0  xor     eax, ebp
0x1003e1a2  mov     [ebp+var_4], eax
0x1003e1a5  push    ebx
0x1003e1a6  push    esi; int
0x1003e1a7  push    edi; struct _GUID *
0x1003e1a8  mov     ebx, edx
0x1003e1aa  mov     [ebp+var_114], ebx
0x1003e1b0  mov     [ebp+var_13C], ecx
0x1003e1b6  movups  xmm0, xmmword ptr ds:aCascade; "CASCADE"
0x1003e1bd  mov     eax, [ebp+arg_8]
0x1003e1c0  mov     [ebp+var_140], eax
0x1003e1c6  movzx   eax, word ptr ds:aSetNull+10h; ""
0x1003e1cd  movups  [ebp+var_48], xmm0
0x1003e1d1  movups  xmm0, xmmword ptr ds:aSetNull; "SET NULL"
0x1003e1d8  mov     [ebp+var_14], ax
0x1003e1dc  mov     eax, dword ptr ds:aNoAction+10h; "N"
0x1003e1e1  mov     edx, [ebp+arg_4]
0x1003e1e4  movups  [ebp+var_24], xmm0
0x1003e1e8  mov     [ebp+var_28], eax
0x1003e1eb  movups  xmm0, xmmword ptr ds:aSetDefault; "SET DEFAULT"
0x1003e1f2  movzx   eax, word ptr ds:aFull+8; ""
0x1003e1f9  movups  [ebp+var_60], xmm0
0x1003e1fd  xor     esi, esi
0x1003e1ff  mov     [ebp+var_8], ax
0x1003e203  movq    xmm0, qword ptr ds:aSetDefault+10h; "ULT"
0x1003e20b  mov     eax, [ebx+10h]
0x1003e20e  movq    [ebp+var_50], xmm0
0x1003e213  movups  xmm0, xmmword ptr ds:aNoAction; "NO ACTION"
0x1003e21a  mov     edi, 1
0x1003e21f  xor     ebx, ebx
0x1003e221  mov     ecx, [ebp+this]
0x1003e224  mov     [ebp+var_130], edx
0x1003e22a  mov     [ebp+var_11C], 0
0x1003e234  mov     [ebp+sesid], eax
0x1003e23a  mov     [ebp+var_12C], edi
0x1003e240  mov     [ebp+var_124], ebx
0x1003e246  movups  [ebp+var_38], xmm0
0x1003e24a  movq    xmm0, qword ptr ds:aFull; "FULL"
0x1003e252  movq    [ebp+var_10], xmm0
0x1003e257  test    ecx, ecx
0x1003e259  jz      loc_1003E30A
0x1003e25f  test    edx, edx
0x1003e261  jz      loc_1003E338
0x1003e267  cmp     ecx, 3
0x1003e26a  ja      loc_1003E338
0x1003e270  movzx   eax, word ptr [edx]
0x1003e273  test    ax, ax
0x1003e276  jz      short loc_1003E28E
0x1003e278  cmp     eax, edi
0x1003e27a  jz      short loc_1003E28E
0x1003e27c  cmp     eax, 8
0x1003e27f  jnz     loc_1003E338
0x1003e285  cmp     [edx+8], ebx
0x1003e288  jnz     loc_1003E338
0x1003e28e  cmp     ecx, 1
0x1003e291  jbe     short loc_1003E2B3
0x1003e293  movzx   eax, word ptr [edx+10h]
0x1003e297  test    ax, ax
0x1003e29a  jz      short loc_1003E2B3
0x1003e29c  cmp     eax, 1
0x1003e29f  jz      short loc_1003E2B3
0x1003e2a1  cmp     eax, 8
0x1003e2a4  jnz     loc_1003E338
0x1003e2aa  cmp     [edx+18h], ebx
0x1003e2ad  jnz     loc_1003E338
0x1003e2b3  cmp     ecx, 2
0x1003e2b6  jbe     short loc_1003E2CB
0x1003e2b8  movzx   eax, word ptr [edx+20h]
0x1003e2bc  test    ax, ax
0x1003e2bf  jz      short loc_1003E2CB
0x1003e2c1  cmp     eax, 1
0x1003e2c4  jz      short loc_1003E2CB
0x1003e2c6  cmp     eax, 8
0x1003e2c9  jnz     short loc_1003E338
0x1003e2cb  cmp     ecx, 3
0x1003e2ce  jb      short loc_1003E30A
0x1003e2d0  movzx   eax, word ptr [edx+20h]
0x1003e2d4  test    ax, ax
0x1003e2d7  jz      short loc_1003E2F6
0x1003e2d9  cmp     eax, 1
0x1003e2dc  jz      short loc_1003E2F6
0x1003e2de  mov     edx, [edx+28h]
0x1003e2e1  xor     eax, eax
0x1003e2e3  test    edx, edx
0x1003e2e5  mov     [ebp+var_124], edx
0x1003e2eb  mov     edx, [ebp+var_130]
0x1003e2f1  mov     ebx, edi
0x1003e2f3  cmovz   edi, eax
0x1003e2f6  mov     ecx, 1
0x1003e2fb  xor     eax, eax
0x1003e2fd  cmp     cx, [edx+20h]
0x1003e301  cmovnz  eax, edi
0x1003e304  mov     [ebp+var_12C], eax
0x1003e30a  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003e310  push    28h ; '('
0x1003e312  push    ecx
0x1003e313  mov     eax, [ecx]
0x1003e315  mov     esi, [eax+0Ch]
0x1003e318  mov     ecx, esi
0x1003e31a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003e320  call    esi
0x1003e322  mov     esi, eax
0x1003e324  mov     [ebp+var_120], esi
0x1003e32a  test    esi, esi
0x1003e32c  jnz     short loc_1003E34E
0x1003e32e  mov     edi, 8007000Eh
0x1003e333  jmp     loc_1003E72C
0x1003e338  mov     ecx, [ebp+var_114]
0x1003e33e  mov     edi, 80070057h
0x1003e343  mov     eax, [ecx+14h]
0x1003e346  mov     ecx, [ecx+10h]
0x1003e349  jmp     loc_1003E762
0x1003e34e  mov     edx, [ebp+var_114]
0x1003e354  lea     eax, [ebp+var_118]
0x1003e35a  push    2
0x1003e35c  push    esi
0x1003e35d  push    eax
0x1003e35e  mov     ecx, 0Ch
0x1003e363  call    SRSCreateTempTable
0x1003e368  mov     edi, eax
0x1003e36a  test    edi, edi
0x1003e36c  js      loc_1003E72C
0x1003e372  mov     edi, [ebp+sesid]
0x1003e378  lea     eax, [ebp+var_110]
0x1003e37e  push    2Ch ; ','
0x1003e380  push    eax
0x1003e381  push    [ebp+var_124]
0x1003e387  mov     eax, [ebp+var_114]
0x1003e38d  push    0
0x1003e38f  push    dword ptr [eax+14h]
0x1003e392  push    edi
0x1003e393  call    ds:__imp__JetGetRelationshipInfo@24; JetGetRelationshipInfo(x,x,x,x,x,x)
0x1003e399  mov     [ebp+var_11C], eax
0x1003e39f  cmp     eax, 0FFFFF88Dh
0x1003e3a4  jz      short loc_1003E3BD
0x1003e3a6  cmp     eax, 0FFFFFAE7h
0x1003e3ab  jz      short loc_1003E3BD
0x1003e3ad  test    eax, eax
0x1003e3af  jnz     loc_1003E727
0x1003e3b5  mov     eax, [ebp+tableid]
0x1003e3bb  jmp     short loc_1003E3D0
0x1003e3bd  or      eax, 0FFFFFFFFh
0x1003e3c0  mov     [ebp+var_108], 0
0x1003e3ca  mov     [ebp+tableid], eax
0x1003e3d0  xor     ecx, ecx
0x1003e3d2  cmp     [ebp+var_12C], 1
0x1003e3d9  mov     [ebp+var_124], ecx
0x1003e3df  jnz     loc_1003E62E
0x1003e3e5  nop     word ptr [eax+eax+00000000h]
0x1003e3f0  cmp     ecx, [ebp+var_108]
0x1003e3f6  jnb     loc_1003E62E
0x1003e3fc  push    0; pretinfo
0x1003e3fe  push    0; grbit
0x1003e400  lea     ecx, [ebp+pcbActual]
0x1003e406  push    ecx; pcbActual
0x1003e407  push    81h; cbData
0x1003e40c  lea     ecx, [ebp+pvData]
0x1003e412  push    ecx; pvData
0x1003e413  push    [ebp+columnid]; columnid
0x1003e419  push    eax; tableid
0x1003e41a  push    edi; sesid
0x1003e41b  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003e421  mov     [ebp+var_11C], eax
0x1003e427  test    eax, eax
0x1003e429  jnz     loc_1003E727
0x1003e42f  mov     eax, [ebp+pcbActual]
0x1003e435  and     eax, 0FFFFFFFEh
0x1003e438  cmp     eax, 82h
0x1003e43d  jnb     loc_1003E7B9
0x1003e443  xor     ecx, ecx
0x1003e445  mov     [ebp+eax+pvData], cx
0x1003e44d  test    ebx, ebx
0x1003e44f  jz      short loc_1003E472
0x1003e451  mov     eax, [ebp+var_130]
0x1003e457  push    dword ptr [eax+28h]; String2
0x1003e45a  lea     eax, [ebp+pvData]
0x1003e460  push    eax; String1
0x1003e461  call    ds:__imp___wcsicmp
0x1003e467  add     esp, 8
0x1003e46a  test    eax, eax
0x1003e46c  jnz     loc_1003E5FF
0x1003e472  push    0; pretinfo
0x1003e474  push    0; grbit
0x1003e476  lea     eax, [ebp+var_144]
0x1003e47c  push    eax; pcbActual
0x1003e47d  push    4; cbData
0x1003e47f  lea     eax, [ebp+var_134]
0x1003e485  push    eax; pvData
0x1003e486  push    [ebp+var_100]; columnid
0x1003e48c  push    [ebp+tableid]; tableid
0x1003e492  push    edi; sesid
0x1003e493  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003e499  mov     [ebp+var_11C], eax
0x1003e49f  test    eax, eax
0x1003e4a1  jnz     loc_1003E727
0x1003e4a7  push    eax; prep
0x1003e4a8  push    [ebp+var_118]; tableid
0x1003e4ae  push    edi; sesid
0x1003e4af  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1003e4b5  mov     [ebp+var_11C], eax
0x1003e4bb  test    eax, eax
0x1003e4bd  jnz     loc_1003E727
0x1003e4c3  push    eax; psetinfo
0x1003e4c4  push    eax; grbit
0x1003e4c5  push    [ebp+pcbActual]; cbData
0x1003e4cb  lea     eax, [ebp+pvData]
0x1003e4d1  push    eax; pvData
0x1003e4d2  push    dword ptr [esi+8]; columnid
0x1003e4d5  push    [ebp+var_118]; tableid
0x1003e4db  push    edi; sesid
0x1003e4dc  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003e4e2  push    0; psetinfo
0x1003e4e4  push    0; grbit
0x1003e4e6  push    [ebp+pcbActual]; cbData
0x1003e4ec  lea     eax, [ebp+pvData]
0x1003e4f2  push    eax; pvData
0x1003e4f3  push    dword ptr [esi+14h]; columnid
0x1003e4f6  push    [ebp+var_118]; tableid
0x1003e4fc  push    edi; sesid
0x1003e4fd  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003e503  push    0; psetinfo
0x1003e505  push    0; grbit
0x1003e507  push    8; cbData
0x1003e509  lea     eax, [ebp+var_10]
0x1003e50c  push    eax; pvData
0x1003e50d  push    dword ptr [esi+18h]; columnid
0x1003e510  push    [ebp+var_118]; tableid
0x1003e516  push    edi; sesid
0x1003e517  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003e51d  mov     eax, [ebp+var_134]
0x1003e523  test    eax, 100h
0x1003e528  jz      short loc_1003E52F
0x1003e52a  lea     edx, [ebp+var_48]
0x1003e52d  jmp     short loc_1003E549
0x1003e52f  test    eax, 200h
0x1003e534  jz      short loc_1003E53B
0x1003e536  lea     edx, [ebp+var_24]
0x1003e539  jmp     short loc_1003E549
0x1003e53b  test    eax, 300h
0x1003e540  lea     edx, [ebp+var_60]
0x1003e543  lea     eax, [ebp+var_38]
0x1003e546  cmovz   edx, eax
0x1003e549  mov     ecx, edx
0x1003e54b  lea     esi, [ecx+2]
0x1003e54e  mov     edi, edi
0x1003e550  mov     ax, [ecx]
0x1003e553  add     ecx, 2
0x1003e556  test    ax, ax
0x1003e559  jnz     short loc_1003E550
0x1003e55b  sub     ecx, esi
0x1003e55d  push    0; psetinfo
0x1003e55f  sar     ecx, 1
0x1003e561  push    0; grbit
0x1003e563  lea     eax, [ecx+ecx]
0x1003e566  push    eax; cbData
0x1003e567  mov     eax, [ebp+var_120]
0x1003e56d  push    edx; pvData
0x1003e56e  push    dword ptr [eax+1Ch]; columnid
0x1003e571  push    [ebp+var_118]; tableid
0x1003e577  push    edi; sesid
0x1003e578  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003e57e  mov     eax, [ebp+var_134]
0x1003e584  test    eax, 1000h
0x1003e589  jz      short loc_1003E590
0x1003e58b  lea     edx, [ebp+var_48]
0x1003e58e  jmp     short loc_1003E5A9
0x1003e590  test    eax, 2000h
0x1003e595  jz      short loc_1003E59C
0x1003e597  lea     edx, [ebp+var_24]
0x1003e59a  jmp     short loc_1003E5A9
0x1003e59c  lea     edx, [ebp+var_60]
0x1003e59f  test    eax, 3000h
0x1003e5a4  jnz     short loc_1003E5A9
0x1003e5a6  lea     edx, [ebp+var_38]
0x1003e5a9  mov     ecx, edx
0x1003e5ab  lea     esi, [ecx+2]
0x1003e5ae  mov     edi, edi
0x1003e5b0  mov     ax, [ecx]
0x1003e5b3  add     ecx, 2
0x1003e5b6  test    ax, ax
0x1003e5b9  jnz     short loc_1003E5B0
0x1003e5bb  sub     ecx, esi
0x1003e5bd  mov     esi, [ebp+var_120]
0x1003e5c3  push    0; psetinfo
0x1003e5c5  sar     ecx, 1
0x1003e5c7  push    0; grbit
0x1003e5c9  lea     eax, [ecx+ecx]
0x1003e5cc  push    eax; cbData
0x1003e5cd  push    edx; pvData
0x1003e5ce  push    dword ptr [esi+20h]; columnid
0x1003e5d1  push    [ebp+var_118]; tableid
0x1003e5d7  push    edi; sesid
0x1003e5d8  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003e5de  push    0; pcbActual
0x1003e5e0  push    0; cbBookmark
  ... truncated ...
```
