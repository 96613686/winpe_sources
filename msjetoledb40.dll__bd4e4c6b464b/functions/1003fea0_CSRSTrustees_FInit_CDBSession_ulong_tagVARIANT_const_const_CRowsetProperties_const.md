# CSRSTrustees::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003fea0`
- end: `0x10040605`
- name: `?FInit@CSRSTrustees@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1893`
- prototype: `int(CSRSTrustees *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10034e00`

## callees

- `0x1000d4a0`
- `0x1000d570`
- `0x10013100`
- `0x10017880`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10034d50`
- `0x10035e60`
- `0x1003fea0`
- `0x10043840`
- `0x100438f0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x1004059a`
- `msjet40!__imp__JetCloseTable@8` at `0x100405bc`
- `msjet40!__imp__JetCloseTable@8` at `0x1004059a`
- `msjet40!__imp__JetCloseTable@8` at `0x100405bc`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10040568`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10040568`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x100402d8`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10040308`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x100402d8`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10040308`
- `msjet40!__imp__JetMove@16` at `0x1004032e`
- `msjet40!__imp__JetMove@16` at `0x10040465`
- `msjet40!__imp__JetMove@16` at `0x1004032e`
- `msjet40!__imp__JetMove@16` at `0x10040465`
- `msjet40!__imp__JetOpenTable@28` at `0x100402b0`
- `msjet40!__imp__JetOpenTable@28` at `0x100402b0`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100403ce`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100403ce`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004035f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100403a4`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004035f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100403a4`
- `msjet40!__imp__JetSetColumn@28` at `0x100403fe`
- `msjet40!__imp__JetSetColumn@28` at `0x1004042a`
- `msjet40!__imp__JetSetColumn@28` at `0x100403fe`
- `msjet40!__imp__JetSetColumn@28` at `0x1004042a`
- `msjet40!__imp__JetUpdate@20` at `0x1004044a`
- `msjet40!__imp__JetUpdate@20` at `0x1004044a`

## pseudocode

```c
int __userpurge CSRSTrustees::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSTrustees *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  _DWORD *v7; // edi
  unsigned __int16 *v8; // esi
  int v9; // edx
  int v10; // edx
  JET_SESID v11; // eax
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  int v16; // eax
  const unsigned __int16 *v17; // eax
  int v18; // eax
  bool v19; // zf
  int v20; // edi
  JET_COLUMNID *v21; // eax
  unsigned __int16 *v22; // eax
  int v23; // edi
  const wchar_t *v24; // eax
  JET_SESID v25; // esi
  JET_ERR v26; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v27; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v28; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v29; // esi
  _DWORD *v30; // eax
  int v31; // ecx
  unsigned int v33; // [esp-24h] [ebp-374h]
  const struct _GUID *v34; // [esp+0h] [ebp-350h]
  const unsigned __int16 *v35; // [esp+0h] [ebp-350h]
  const unsigned __int16 *v36; // [esp+0h] [ebp-350h]
  const struct _GUID *v37; // [esp+4h] [ebp-34Ch]
  unsigned int v38; // [esp+4h] [ebp-34Ch]
  unsigned int v39; // [esp+4h] [ebp-34Ch]
  unsigned int TableColumnInfo; // [esp+14h] [ebp-33Ch] BYREF
  unsigned __int16 *v41; // [esp+18h] [ebp-338h]
  int v42; // [esp+1Ch] [ebp-334h] BYREF
  _DWORD *v43; // [esp+20h] [ebp-330h]
  JET_TABLEID tableid; // [esp+24h] [ebp-32Ch] BYREF
  JET_TABLEID v45; // [esp+28h] [ebp-328h] BYREF
  JET_SESID sesid; // [esp+2Ch] [ebp-324h]
  JET_COLUMNID columnid; // [esp+30h] [ebp-320h] BYREF
  JET_COLUMNID *v48; // [esp+34h] [ebp-31Ch]
  JET_COLUMNID v49; // [esp+38h] [ebp-318h]
  int v50; // [esp+3Ch] [ebp-314h]
  int v51; // [esp+40h] [ebp-310h]
  const unsigned __int16 *v52; // [esp+44h] [ebp-30Ch]
  CSecuritySession *v53; // [esp+48h] [ebp-308h]
  int v54; // [esp+4Ch] [ebp-304h]
  unsigned int pcbActual; // [esp+50h] [ebp-300h] BYREF
  JET_SESID v56; // [esp+54h] [ebp-2FCh]
  int v57; // [esp+58h] [ebp-2F8h] BYREF
  int v58; // [esp+5Ch] [ebp-2F4h] BYREF
  unsigned int v59; // [esp+60h] [ebp-2F0h]
  int v60; // [esp+64h] [ebp-2ECh]
  unsigned int v61; // [esp+68h] [ebp-2E8h] BYREF
  char v62[4]; // [esp+6Ch] [ebp-2E4h] BYREF
  JET_COLUMNID v63; // [esp+70h] [ebp-2E0h]
  __int64 v64; // [esp+84h] [ebp-2CCh] BYREF
  wchar_t v65; // [esp+8Ch] [ebp-2C4h]
  __int64 v66; // [esp+90h] [ebp-2C0h] BYREF
  int v67; // [esp+98h] [ebp-2B8h]
  wchar_t v68; // [esp+9Ch] [ebp-2B4h]
  __int128 v69; // [esp+A0h] [ebp-2B0h] BYREF
  wchar_t v70; // [esp+B0h] [ebp-2A0h]
  _OWORD v71[4]; // [esp+C0h] [ebp-290h] BYREF
  __int64 v72; // [esp+100h] [ebp-250h]
  int v73; // [esp+108h] [ebp-248h]
  _OWORD v74[3]; // [esp+110h] [ebp-240h] BYREF
  _WORD pvData[258]; // [esp+148h] [ebp-208h] BYREF

  v7 = a1;
  v43 = a1;
  v57 = a2;
  v59 = a5;
  v71[0] = *(_OWORD *)L"SELECT NAME, FGROUP FROM MsysAccounts";
  v73 = *(_DWORD *)L"s";
  v71[1] = *(_OWORD *)L"AME, FGROUP FROM MsysAccounts";
  v65 = aName_0[4];
  v8 = 0;
  v71[2] = *(_OWORD *)L"OUP FROM MsysAccounts";
  v70 = aWhere[8];
  v71[3] = *(_OWORD *)L" MsysAccounts";
  v67 = *(_DWORD *)L"up";
  v9 = a1[5];
  v72 = *(_QWORD *)L"ounts";
  v64 = *(_QWORD *)L"NAME";
  v60 = v9;
  v10 = v43[21];
  v69 = *(_OWORD *)L" WHERE (";
  v68 = aFgroup_0[6];
  v66 = *(_QWORD *)L"FGroup";
  v53 = (CSecuritySession *)(v10 + 64);
  v50 = 0;
  v52 = 0;
  v49 = 0;
  columnid = 0;
  TableColumnInfo = 0;
  v11 = v43[4];
  v51 = 0;
  v54 = 1;
  sesid = v11;
  v48 = 0;
  v45 = 0;
  v41 = 0;
  v56 = -1;
  tableid = -1;
  HIBYTE(v42) = 0;
  v74[0] = *(_OWORD *)L" ORDER BY NAME, FGROUP;";
  v74[1] = *(_OWORD *)L"Y NAME, FGROUP;";
  v74[2] = *(_OWORD *)L"FGROUP;";
  if ( this )
  {
    if ( !a4
      || (unsigned int)this > 4
      || (v12 = *(unsigned __int16 *)a4, (_WORD)v12) && v12 != 1 && v12 != 8
      || (unsigned int)this > 1 && (v13 = *((unsigned __int16 *)a4 + 8), (_WORD)v13) && v13 != 1
      || (unsigned int)this > 2 && (v14 = *((unsigned __int16 *)a4 + 16), (_WORD)v14) && v14 != 1
      || (unsigned int)this > 3 && (v15 = *((unsigned __int16 *)a4 + 24), (_WORD)v15) && v15 != 1 && v15 != 19 )
    {
      v20 = -2147024809;
      goto LABEL_76;
    }
    v16 = *(unsigned __int16 *)a4;
    if ( (_WORD)v16 )
    {
      if ( v16 != 1 )
      {
        v17 = (const unsigned __int16 *)*((_DWORD *)a4 + 2);
        if ( v17 )
        {
          v51 = 1;
          v52 = v17;
        }
      }
    }
    if ( (unsigned int)this <= 3 || (v18 = *((unsigned __int16 *)a4 + 24), !(_WORD)v18) || v18 == 1 )
    {
      v7 = v43;
    }
    else
    {
      v19 = *((_DWORD *)a4 + 14) == 0;
      v49 = *((_DWORD *)a4 + 14);
      v7 = v43;
      v50 = 1;
      if ( v19 )
        v54 = 0;
    }
  }
  v21 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          16);
  v48 = v21;
  if ( !v21 )
  {
    v20 = -2147024882;
LABEL_30:
    v8 = 0;
LABEL_71:
    if ( TableColumnInfo )
    {
      CExtError::SendJetErrortoOLEAuto(TableColumnInfo, (int)&IID_IDBSchemaRowset, (int)v34, v37);
      goto LABEL_78;
    }
    if ( v20 >= 0 || v20 == -2147024882 )
      goto LABEL_80;
    v11 = sesid;
LABEL_76:
    if ( !JetGetDatabaseInfo(v11, v60, &v57, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v34, (int)v37);
    goto LABEL_78;
  }
  v20 = SRSCreateTempTable(19, v7, &v45, v21, 0);
  if ( v20 < 0 )
    goto LABEL_30;
  if ( v52 && wcslen(v52) > 0x14 || v54 != 1 )
    goto LABEL_65;
  v22 = (unsigned __int16 *)operator new(0xEEu);
  v8 = v22;
  v41 = v22;
  if ( !v22 )
  {
    v20 = -2147024882;
    goto LABEL_71;
  }
  WCSCPY((unsigned __int16 *)v71, v22, (unsigned __int16 *)0x77, (const unsigned __int16 *)v34, (unsigned int)v37);
  v23 = v50;
  if ( v51 != 1 && v50 != 1 )
    goto LABEL_47;
  WCSCAT((unsigned __int16 *)&v69, v8, (unsigned __int16 *)0x77, v35, v38);
  if ( v51 == 1 )
  {
    StringCchPrintfW(v8, 0x77u, (wchar_t *)L"%s [%s] = '%s'", v8, &v64, v52);
    if ( v23 == 1 )
    {
      WCSCAT(L" AND ", v8, (unsigned __int16 *)0x77, v36, v39);
LABEL_43:
      v24 = L"FALSE";
      if ( v49 != 1 )
        v24 = L"TRUE";
      StringCchPrintfW(v8, 0x77u, (wchar_t *)L"%s [%s] = %s", v8, &v66, v24);
    }
  }
  else if ( v23 == 1 )
  {
    goto LABEL_43;
  }
  WCSCAT(L")", v8, (unsigned __int16 *)0x77, v36, v39);
LABEL_47:
  WCSCAT((unsigned __int16 *)v74, v8, (unsigned __int16 *)0x77, v35, v38);
  v20 = CSecuritySession::CheckForSecuritySesid(v53, (int *)&TableColumnInfo);
  if ( v20 < 0 )
    goto LABEL_71;
  v20 = CSecuritySession::CheckForSecurityDbid(v53, (int *)&TableColumnInfo, (int *)&columnid);
  if ( v20 >= 0 )
  {
    v25 = *((_DWORD *)v53 + 1);
    v56 = v25;
    TableColumnInfo = JetOpenTable(v25, *((_DWORD *)v53 + 2), v41, 0, 0, 96, &tableid);
    if ( (TableColumnInfo & 0x80000000) != 0
      || (TableColumnInfo = JetGetTableColumnInfo(v25, tableid, &v64, v62, 24, 0), (TableColumnInfo & 0x80000000) != 0)
      || (columnid = v63,
          TableColumnInfo = JetGetTableColumnInfo(v25, tableid, &v66, v62, 24, 0),
          (TableColumnInfo & 0x80000000) != 0) )
    {
LABEL_70:
      v8 = v41;
      goto LABEL_71;
    }
    v49 = v63;
    v26 = JetMove(v25, tableid, 0x80000000, 0);
    for ( TableColumnInfo = v26; !v26; TableColumnInfo = v26 )
    {
      TableColumnInfo = JetRetrieveColumn(v25, tableid, columnid, pvData, 0x200u, &pcbActual, 0, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
        __report_rangecheckfailure();
      *(_WORD *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      TableColumnInfo = JetRetrieveColumn(v25, tableid, v49, (char *)&v42 + 3, 1u, &v61, 0, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      v58 = (HIBYTE(v42) != 0) + 1;
      TableColumnInfo = JetPrepareUpdate(sesid, v45, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      TableColumnInfo = JetSetColumn(sesid, v45, *v48, pvData, pcbActual, 0, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      TableColumnInfo = JetSetColumn(sesid, v45, v48[3], &v58, 4u, 0, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      TableColumnInfo = JetUpdate(sesid, v45, 0, 0, 0);
      if ( (TableColumnInfo & 0x80000000) != 0 )
        goto LABEL_70;
      v26 = JetMove(v25, tableid, 1, 0);
    }
    if ( v26 == -1603 )
      TableColumnInfo = 0;
LABEL_65:
    v27 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
    columnid = (JET_COLUMNID)v27;
    if ( v27 && (v28 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v27), (v29 = v28) != 0) )
    {
      *((_DWORD *)v28 + 4) = dword_100087C8;
      v30 = v43;
      *((_DWORD *)v29 + 5) = &SRSTrusteesNames;
      *((_DWORD *)v29 + 7) = 0;
      v20 = ColumnData::FInit(v29, sesid, v30[5], v45, (int *)&TableColumnInfo, 0, (int)&SRSTrusteesNames);
      if ( v20 >= 0 )
      {
        v31 = v57;
        v33 = v59;
        *((_DWORD *)v29 + 1) = 4;
        v20 = CRowset::FInit(v31, 0, v43, 0, 0, 0, v45, v33, 1, 0, 0, v29, 1, 0, 0, &GUID_NULL);
      }
    }
    else
    {
      v20 = -2147024882;
    }
    goto LABEL_70;
  }
  if ( columnid != 1 )
    goto LABEL_71;
LABEL_78:
  if ( (TableColumnInfo & 0x80000000) != 0 )
    v20 = -2147467259;
LABEL_80:
  if ( tableid != -1 )
    JetCloseTable(v56, tableid);
  if ( v8 )
    operator delete(v8);
  if ( v20 < 0 )
    TableColumnInfo = JetCloseTable(v43[4], v45);
  if ( v48 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v48);
  return v20;
}

```

## disassembly

```asm
0x1003fea0  mov     edi, edi
0x1003fea2  push    ebp
0x1003fea3  mov     ebp, esp
0x1003fea5  and     esp, 0FFFFFFF0h
0x1003fea8  sub     esp, 348h
0x1003feae  mov     eax, ___security_cookie
0x1003feb3  xor     eax, esp
0x1003feb5  mov     [esp+348h+var_4], eax
0x1003febc  push    esi; int
0x1003febd  push    edi; struct _GUID *
0x1003febe  mov     edi, edx
0x1003fec0  mov     [esp+350h+var_330], edi
0x1003fec4  mov     [esp+350h+var_2F8], ecx
0x1003fec8  movups  xmm0, xmmword ptr ds:aSelectNameFgro; "SELECT NAME, FGROUP FROM MsysAccounts"
0x1003fecf  mov     eax, [ebp+arg_8]
0x1003fed2  mov     [esp+350h+var_2F0], eax
0x1003fed6  movups  [esp+350h+var_290], xmm0
0x1003fede  mov     eax, dword ptr ds:aSelectNameFgro+48h; "s"
0x1003fee3  movups  xmm0, xmmword ptr ds:aSelectNameFgro+10h; "AME, FGROUP FROM MsysAccounts"
0x1003feea  mov     [esp+350h+var_248], eax
0x1003fef1  movzx   eax, word ptr ds:aName_0+8; ""
0x1003fef8  movups  [esp+350h+var_280], xmm0
0x1003ff00  movups  xmm0, xmmword ptr ds:aSelectNameFgro+20h; "OUP FROM MsysAccounts"
0x1003ff07  mov     [esp+350h+var_2C4], ax
0x1003ff0f  xor     esi, esi
0x1003ff11  movzx   eax, word ptr ds:aWhere+10h; ""
0x1003ff18  movups  [esp+350h+var_270], xmm0
0x1003ff20  movups  xmm0, xmmword ptr ds:aSelectNameFgro+30h; " MsysAccounts"
0x1003ff27  mov     [esp+350h+var_2A0], ax
0x1003ff2f  mov     eax, dword ptr ds:aFgroup_0+8; "up"
0x1003ff34  movups  [esp+350h+var_260], xmm0
0x1003ff3c  mov     [esp+350h+var_2B8], eax
0x1003ff43  movq    xmm0, qword ptr ds:aSelectNameFgro+40h; "ounts"
0x1003ff4b  mov     edx, [edi+14h]
0x1003ff4e  movzx   eax, word ptr ds:aFgroup_0+0Ch; ""
0x1003ff55  movq    [esp+350h+var_250], xmm0
0x1003ff5e  movq    xmm0, qword ptr ds:aName_0; "NAME"
0x1003ff66  movq    [esp+350h+var_2CC], xmm0
0x1003ff6f  movups  xmm0, xmmword ptr ds:aWhere; " WHERE ("
0x1003ff76  mov     [esp+350h+var_2EC], edx
0x1003ff7a  mov     edx, [edi+54h]
0x1003ff7d  movups  [esp+350h+var_2B0], xmm0
0x1003ff85  add     edx, 40h ; '@'
0x1003ff88  mov     [esp+350h+var_2B4], ax
0x1003ff90  movq    xmm0, qword ptr ds:aFgroup_0; "FGroup"
0x1003ff98  xor     eax, eax
0x1003ff9a  movq    [esp+350h+var_2C0], xmm0
0x1003ffa3  movups  xmm0, xmmword ptr ds:aOrderByNameFgr; " ORDER BY NAME, FGROUP;"
0x1003ffaa  mov     [esp+350h+var_308], edx
0x1003ffae  mov     edx, [ebp+this]
0x1003ffb1  mov     [esp+350h+var_314], eax
0x1003ffb5  mov     [esp+350h+var_30C], eax
0x1003ffb9  mov     [esp+350h+var_318], eax
0x1003ffbd  mov     [esp+350h+columnid], eax
0x1003ffc1  mov     [esp+350h+var_33C], eax
0x1003ffc5  mov     eax, [edi+10h]
0x1003ffc8  mov     ecx, [ebp+arg_4]
0x1003ffcb  mov     [esp+350h+var_310], 0
0x1003ffd3  mov     [esp+350h+var_304], 1
0x1003ffdb  mov     [esp+350h+sesid], eax
0x1003ffdf  mov     [esp+350h+var_31C], 0
0x1003ffe7  mov     [esp+350h+var_328], 0
0x1003ffef  mov     [esp+350h+var_338], esi
0x1003fff3  mov     [esp+350h+var_2FC], 0FFFFFFFFh
0x1003fffb  mov     [esp+350h+tableid], 0FFFFFFFFh
0x10040003  mov     byte ptr [esp+350h+var_334+3], 0
0x10040008  movups  [esp+350h+var_240], xmm0
0x10040010  movups  xmm0, xmmword ptr ds:aOrderByNameFgr+10h; "Y NAME, FGROUP;"
0x10040017  movups  [esp+350h+var_230], xmm0
0x1004001f  movups  xmm0, xmmword ptr ds:aOrderByNameFgr+20h; "FGROUP;"
0x10040026  movups  [esp+350h+var_220], xmm0
0x1004002e  test    edx, edx
0x10040030  jz      loc_100400F9
0x10040036  test    ecx, ecx
0x10040038  jz      loc_100400EB
0x1004003e  cmp     edx, 4
0x10040041  ja      loc_100400EB
0x10040047  movzx   edi, word ptr [ecx]
0x1004004a  test    di, di
0x1004004d  jz      short loc_1004005D
0x1004004f  cmp     edi, 1
0x10040052  jz      short loc_1004005D
0x10040054  cmp     edi, 8
0x10040057  jnz     loc_100400EB
0x1004005d  cmp     edx, 1
0x10040060  jbe     short loc_10040070
0x10040062  movzx   edi, word ptr [ecx+10h]
0x10040066  test    di, di
0x10040069  jz      short loc_10040070
0x1004006b  cmp     edi, 1
0x1004006e  jnz     short loc_100400EB
0x10040070  cmp     edx, 2
0x10040073  jbe     short loc_10040083
0x10040075  movzx   edi, word ptr [ecx+20h]
0x10040079  test    di, di
0x1004007c  jz      short loc_10040083
0x1004007e  cmp     edi, 1
0x10040081  jnz     short loc_100400EB
0x10040083  cmp     edx, 3
0x10040086  jbe     short loc_1004009B
0x10040088  movzx   edi, word ptr [ecx+30h]
0x1004008c  test    di, di
0x1004008f  jz      short loc_1004009B
0x10040091  cmp     edi, 1
0x10040094  jz      short loc_1004009B
0x10040096  cmp     edi, 13h
0x10040099  jnz     short loc_100400EB
0x1004009b  movzx   eax, word ptr [ecx]
0x1004009e  test    ax, ax
0x100400a1  jz      short loc_100400BB
0x100400a3  cmp     eax, 1
0x100400a6  jz      short loc_100400BB
0x100400a8  mov     eax, [ecx+8]
0x100400ab  test    eax, eax
0x100400ad  jz      short loc_100400BB
0x100400af  mov     [esp+350h+var_310], 1
0x100400b7  mov     [esp+350h+var_30C], eax
0x100400bb  cmp     edx, 3
0x100400be  jbe     short loc_100400F5
0x100400c0  movzx   eax, word ptr [ecx+30h]
0x100400c4  test    ax, ax
0x100400c7  jz      short loc_100400F5
0x100400c9  cmp     eax, 1
0x100400cc  jz      short loc_100400F5
0x100400ce  mov     edi, [ecx+38h]
0x100400d1  test    edi, edi
0x100400d3  mov     [esp+350h+var_318], edi
0x100400d7  mov     edi, [esp+350h+var_330]
0x100400db  mov     [esp+350h+var_314], 1
0x100400e3  jnz     short loc_100400F9
0x100400e5  mov     [esp+350h+var_304], esi
0x100400e9  jmp     short loc_100400F9
0x100400eb  mov     edi, 80070057h
0x100400f0  jmp     loc_1004055A
0x100400f5  mov     edi, [esp+350h+var_330]
0x100400f9  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100400ff  push    10h
0x10040101  push    ecx
0x10040102  mov     eax, [ecx]
0x10040104  mov     esi, [eax+0Ch]
0x10040107  mov     ecx, esi
0x10040109  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004010f  call    esi
0x10040111  mov     [esp+350h+var_31C], eax
0x10040115  test    eax, eax
0x10040117  jnz     short loc_10040125
0x10040119  mov     edi, 8007000Eh
0x1004011e  xor     esi, esi
0x10040120  jmp     loc_1004052C
0x10040125  push    0
0x10040127  push    eax
0x10040128  lea     eax, [esp+358h+var_328]
0x1004012c  mov     edx, edi
0x1004012e  push    eax
0x1004012f  mov     ecx, 13h
0x10040134  call    SRSCreateTempTable
0x10040139  mov     edi, eax
0x1004013b  test    edi, edi
0x1004013d  js      short loc_1004011E
0x1004013f  mov     eax, [esp+350h+var_30C]
0x10040143  test    eax, eax
0x10040145  jz      short loc_10040168
0x10040147  mov     ecx, eax
0x10040149  lea     edx, [ecx+2]
0x1004014c  nop     dword ptr [eax+00h]
0x10040150  mov     ax, [ecx]
0x10040153  add     ecx, 2
0x10040156  test    ax, ax
0x10040159  jnz     short loc_10040150
0x1004015b  sub     ecx, edx
0x1004015d  sar     ecx, 1
0x1004015f  cmp     ecx, 14h
0x10040162  ja      loc_10040486
0x10040168  cmp     [esp+350h+var_304], 1
0x1004016d  jnz     loc_10040486
0x10040173  push    0EEh; Size
0x10040178  call    ??2@YAPAXI@Z; operator new(uint)
0x1004017d  mov     esi, eax
0x1004017f  add     esp, 4
0x10040182  mov     [esp+350h+var_338], esi
0x10040186  test    esi, esi
0x10040188  jnz     short loc_10040194
0x1004018a  mov     edi, 8007000Eh
0x1004018f  jmp     loc_1004052C
0x10040194  push    77h ; 'w'; unsigned __int16 *
0x10040196  lea     edx, [esp+354h+var_290]
0x1004019d  mov     ecx, esi
0x1004019f  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x100401a4  cmp     [esp+350h+var_310], 1
0x100401a9  mov     edi, [esp+350h+var_314]
0x100401ad  jz      short loc_100401B8
0x100401af  cmp     edi, 1
0x100401b2  jnz     loc_10040241
0x100401b8  push    77h ; 'w'; unsigned __int16 *
0x100401ba  lea     edx, [esp+354h+var_2B0]
0x100401c1  mov     ecx, esi
0x100401c3  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x100401c8  cmp     [esp+350h+var_310], 1
0x100401cd  jnz     short loc_10040202
0x100401cf  mov     eax, [esp+350h+var_30C]
0x100401d3  push    eax
0x100401d4  lea     eax, [esp+354h+var_2CC]
0x100401db  push    eax
0x100401dc  push    esi
0x100401dd  push    offset aSSS; "%s [%s] = '%s'"
0x100401e2  push    77h ; 'w'; unsigned int
0x100401e4  push    esi; Buffer
0x100401e5  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x100401ea  add     esp, 18h
0x100401ed  cmp     edi, 1
0x100401f0  jnz     short loc_10040233
0x100401f2  push    77h ; 'w'; unsigned __int16 *
0x100401f4  mov     edx, offset aAnd; " AND "
0x100401f9  mov     ecx, esi
0x100401fb  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x10040200  jmp     short loc_10040207
0x10040202  cmp     edi, 1
0x10040205  jnz     short loc_10040233
0x10040207  cmp     [esp+350h+var_318], 1
0x1004020c  mov     ecx, offset aTrue; "TRUE"
0x10040211  mov     eax, offset aFalse; "FALSE"
0x10040216  cmovnz  eax, ecx
0x10040219  push    eax
0x1004021a  lea     eax, [esp+354h+var_2C0]
0x10040221  push    eax
0x10040222  push    esi
0x10040223  push    offset aSSS_0; "%s [%s] = %s"
0x10040228  push    77h ; 'w'; unsigned int
0x1004022a  push    esi; Buffer
0x1004022b  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x10040230  add     esp, 18h
0x10040233  push    77h ; 'w'; unsigned __int16 *
0x10040235  mov     edx, offset asc_100076A4; ")"
0x1004023a  mov     ecx, esi
0x1004023c  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x10040241  push    77h ; 'w'; unsigned __int16 *
0x10040243  lea     edx, [esp+354h+var_240]
0x1004024a  mov     ecx, esi
0x1004024c  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x10040251  mov     ecx, [esp+350h+var_308]; this
0x10040255  lea     eax, [esp+350h+var_33C]
0x10040259  push    eax; int *
0x1004025a  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x1004025f  mov     edi, eax
0x10040261  test    edi, edi
0x10040263  js      loc_1004052C
0x10040269  mov     ecx, [esp+350h+var_308]; this
0x1004026d  lea     eax, [esp+350h+columnid]
0x10040271  push    eax; int *
0x10040272  lea     eax, [esp+354h+var_33C]
0x10040276  push    eax; int *
0x10040277  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x1004027c  mov     edi, eax
0x1004027e  test    edi, edi
0x10040280  jns     short loc_10040292
0x10040282  cmp     [esp+350h+columnid], 1
0x10040287  jnz     loc_1004052C
0x1004028d  jmp     loc_1004057F
0x10040292  mov     eax, [esp+350h+var_308]
0x10040296  lea     ecx, [esp+350h+tableid]
0x1004029a  push    ecx
0x1004029b  push    60h ; '`'
0x1004029d  push    0
0x1004029f  mov     esi, [eax+4]
0x100402a2  push    0
0x100402a4  push    [esp+360h+var_338]
0x100402a8  mov     [esp+364h+var_2FC], esi
0x100402ac  push    dword ptr [eax+8]
0x100402af  push    esi
0x100402b0  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x100402b6  mov     [esp+350h+var_33C], eax
0x100402ba  test    eax, eax
0x100402bc  js      loc_10040528
0x100402c2  push    0
0x100402c4  push    18h
0x100402c6  lea     eax, [esp+358h+var_2E4]
0x100402ca  push    eax
0x100402cb  lea     eax, [esp+35Ch+var_2CC]
0x100402d2  push    eax
0x100402d3  push    [esp+360h+tableid]
0x100402d7  push    esi
0x100402d8  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x100402de  mov     [esp+350h+var_33C], eax
0x100402e2  test    eax, eax
0x100402e4  js      loc_10040528
0x100402ea  mov     eax, [esp+350h+var_2E0]
0x100402ee  push    0
0x100402f0  push    18h
0x100402f2  mov     [esp+358h+columnid], eax
0x100402f6  lea     eax, [esp+358h+var_2E4]
0x100402fa  push    eax
0x100402fb  lea     eax, [esp+35Ch+var_2C0]
0x10040302  push    eax
0x10040303  push    [esp+360h+tableid]
0x10040307  push    esi
0x10040308  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x1004030e  mov     [esp+350h+var_33C], eax
0x10040312  test    eax, eax
0x10040314  js      loc_10040528
0x1004031a  mov     eax, [esp+350h+var_2E0]
  ... truncated ...
```
