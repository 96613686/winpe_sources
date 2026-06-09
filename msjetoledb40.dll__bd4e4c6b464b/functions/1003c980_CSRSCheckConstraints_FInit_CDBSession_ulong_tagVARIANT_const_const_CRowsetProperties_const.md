# CSRSCheckConstraints::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003c980`
- end: `0x1003d389`
- name: `?FInit@CSRSCheckConstraints@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `2569`
- prototype: `int __userpurge@<eax>(_DWORD *@<edx>, int@<ecx>, const struct _GUID *@<edi>, const struct _GUID *@<esi>, CSRSCheckConstraints *this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d4a0`
- `0x1000d570`
- `0x10013020`
- `0x10013100`
- `0x10017880`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035d90`
- `0x10035e60`
- `0x1003c980`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x1003d33c`
- `msjet40!__imp__JetCloseTable@8` at `0x1003d33c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003d31a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003d31a`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003cb12`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003cb12`
- `msjet40!__imp__JetMove@16` at `0x1003cb36`
- `msjet40!__imp__JetMove@16` at `0x1003d1d3`
- `msjet40!__imp__JetMove@16` at `0x1003cb36`
- `msjet40!__imp__JetMove@16` at `0x1003d1d3`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003cc42`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003cd73`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003d09d`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003cc42`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003cd73`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003d09d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003cb87`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003cb87`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cc87`
- `msjet40!__imp__JetSetColumn@28` at `0x1003ccbd`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cd9d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cdd4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d0eb`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d12b`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cc87`
- `msjet40!__imp__JetSetColumn@28` at `0x1003ccbd`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cd9d`
- `msjet40!__imp__JetSetColumn@28` at `0x1003cdd4`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d0eb`
- `msjet40!__imp__JetSetColumn@28` at `0x1003d12b`
- `msjet40!__imp__JetUpdate@20` at `0x1003ccd7`
- `msjet40!__imp__JetUpdate@20` at `0x1003ce18`
- `msjet40!__imp__JetUpdate@20` at `0x1003d19b`
- `msjet40!__imp__JetUpdate@20` at `0x1003ccd7`
- `msjet40!__imp__JetUpdate@20` at `0x1003ce18`
- `msjet40!__imp__JetUpdate@20` at `0x1003d19b`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cbe0`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cd29`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cf3e`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cbe0`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cd29`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1003cf3e`

## pseudocode

```c
int __userpurge CSRSCheckConstraints::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        const struct _GUID *a3@<edi>,
        const struct _GUID *a4@<esi>,
        CSRSCheckConstraints *this,
        struct CDBSession *a6,
        unsigned int a7,
        const struct tagVARIANT *const a8,
        const struct CRowsetProperties *a9)
{
  JET_SESID v10; // esi
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // edi
  int v15; // eax
  int v16; // ecx
  CSchemaRowset *v17; // eax
  int v18; // eax
  _DWORD *v19; // edi
  JET_ERR v20; // eax
  unsigned int v21; // eax
  unsigned __int16 *v22; // edi
  unsigned __int16 *v23; // eax
  unsigned int v25; // esi
  unsigned __int16 *v26; // edi
  char *v27; // esi
  __int16 v28; // ax
  unsigned int v29; // esi
  unsigned int v30; // eax
  CSchemaRowset *v31; // edi
  CSchemaRowset *v32; // ecx
  _DWORD *v33; // eax
  _DWORD *v34; // edi
  unsigned int v35; // eax
  int *v36; // ecx
  int v37; // ecx
  int v38; // edi
  int v39; // eax
  int v40; // eax
  unsigned int v41; // eax
  int v42; // edx
  _WORD *v43; // ecx
  int v44; // eax
  _WORD *v45; // edx
  int v47; // ecx
  const unsigned __int16 *v48; // eax
  int v49; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v50; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v51; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v52; // esi
  int v53; // ecx
  unsigned int v55; // [esp-2Ch] [ebp-102B4h]
  JET_TABLEID v56; // [esp-10h] [ebp-10298h]
  const struct _GUID *v57; // [esp-8h] [ebp-10290h]
  const unsigned __int16 *v58; // [esp-8h] [ebp-10290h]
  const unsigned __int16 *v59; // [esp-8h] [ebp-10290h]
  const unsigned __int16 *v60; // [esp-8h] [ebp-10290h]
  const unsigned __int16 *v61; // [esp-8h] [ebp-10290h]
  const unsigned __int16 *v62; // [esp-8h] [ebp-10290h]
  const struct _GUID *v63; // [esp-4h] [ebp-1028Ch]
  unsigned int v64; // [esp-4h] [ebp-1028Ch]
  unsigned int v65; // [esp-4h] [ebp-1028Ch]
  unsigned int v66; // [esp-4h] [ebp-1028Ch]
  unsigned int v67; // [esp-4h] [ebp-1028Ch]
  unsigned int v68; // [esp-4h] [ebp-1028Ch]
  unsigned int ObjectInfo; // [esp+Ch] [ebp-1027Ch] BYREF
  JET_TABLEID v70; // [esp+10h] [ebp-10278h] BYREF
  _DWORD *v71; // [esp+14h] [ebp-10274h]
  JET_SESID sesid; // [esp+18h] [ebp-10270h]
  CSchemaRowset *v73; // [esp+1Ch] [ebp-1026Ch]
  unsigned int v74; // [esp+20h] [ebp-10268h] BYREF
  _DWORD *v75; // [esp+24h] [ebp-10264h]
  int *v76; // [esp+28h] [ebp-10260h]
  unsigned int v77; // [esp+2Ch] [ebp-1025Ch]
  int v78; // [esp+30h] [ebp-10258h]
  unsigned int *v79; // [esp+34h] [ebp-10254h]
  ColumnDataWithFakeNamesAndDBTYPES *v80; // [esp+38h] [ebp-10250h] BYREF
  unsigned int pcbActual; // [esp+3Ch] [ebp-1024Ch] BYREF
  unsigned int v82; // [esp+40h] [ebp-10248h]
  int v83; // [esp+44h] [ebp-10244h]
  int v84; // [esp+48h] [ebp-10240h] BYREF
  JET_TABLEID tableid; // [esp+4Ch] [ebp-1023Ch]
  unsigned int v86; // [esp+50h] [ebp-10238h]
  JET_COLUMNID columnid; // [esp+58h] [ebp-10230h]
  __int128 v88; // [esp+78h] [ebp-10210h] BYREF
  __int64 v89; // [esp+88h] [ebp-10200h]
  int v90; // [esp+90h] [ebp-101F8h]
  wchar_t v91; // [esp+94h] [ebp-101F4h]
  _OWORD v92[2]; // [esp+98h] [ebp-101F0h] BYREF
  wchar_t v93; // [esp+B8h] [ebp-101D0h]
  unsigned __int16 pvData[68]; // [esp+C8h] [ebp-101C0h] BYREF
  unsigned __int16 v95[168]; // [esp+150h] [ebp-10138h] BYREF
  unsigned __int16 v96[32754]; // [esp+2A0h] [ebp-FFE8h] BYREF

  v63 = a4;
  v88 = *(_OWORD *)L"ValidationRule";
  v82 = a7;
  v89 = *(_QWORD *)L"onRule";
  v57 = a3;
  v90 = *(_DWORD *)L"le";
  v91 = aValidationrule[14];
  v10 = a1[4];
  v71 = a1;
  v83 = a2;
  v93 = aCheckconstrain[16];
  ObjectInfo = 0;
  sesid = v10;
  v73 = 0;
  tableid = -1;
  v92[0] = *(_OWORD *)L"CheckConstraints";
  v92[1] = *(_OWORD *)L"straints";
  if ( this )
  {
    if ( !a6
      || (unsigned int)this > 3
      || (v11 = *(unsigned __int16 *)a6, (_WORD)v11) && v11 != 1 && (v11 != 8 || *((_DWORD *)a6 + 2))
      || (unsigned int)this > 1
      && (v12 = *((unsigned __int16 *)a6 + 8), (_WORD)v12)
      && v12 != 1
      && (v12 != 8 || *((_DWORD *)a6 + 6))
      || (unsigned int)this > 2
      && (v13 = *((unsigned __int16 *)a6 + 16), (_WORD)v13)
      && v13 != 1
      && (v13 != 8 || *((_DWORD *)a6 + 10)) )
    {
      v14 = -2147024809;
      v15 = v71[5];
      v16 = v71[4];
LABEL_101:
      if ( !JetGetDatabaseInfo(v16, v15, &v80, 4, 3) )
        CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v57, (int)v63);
      goto LABEL_103;
    }
  }
  v17 = (CSchemaRowset *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                           *(_DWORD *)(*(_DWORD *)Sys + 12),
                           Sys,
                           20);
  v73 = v17;
  if ( !v17 )
    goto LABEL_95;
  v18 = SRSCreateTempTable(10, a1, &v70, (JET_COLUMNID *)v17, 0);
  v10 = sesid;
  v14 = v18;
  if ( v18 < 0 )
    goto LABEL_97;
  v19 = v71;
  ObjectInfo = JetGetObjectInfo(sesid, v71[5], 1, L"tables", 0, &v84, 48, 1);
  if ( ObjectInfo )
    goto LABEL_22;
  v20 = JetMove(v10, tableid, 0x80000000, 0);
  ObjectInfo = v20;
  if ( v20 != -1603 && v20 )
  {
    v14 = -2147467259;
    goto LABEL_97;
  }
  v78 = 0;
  if ( v86 )
  {
    while ( 1 )
    {
      ObjectInfo = JetRetrieveColumn(v10, tableid, columnid, pvData, 0x81u, &pcbActual, 0, 0);
      if ( ObjectInfo )
        break;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
        goto LABEL_109;
      *(unsigned __int16 *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      v21 = JetRetrieveProperty(v10, v19[5], L"tables", pvData, 0, v92, v96, 65504, &v74, 0, 0, 0);
      ObjectInfo = v21;
      if ( v21 != -3600 && v21 != -1907 )
      {
        if ( v21 )
          break;
        v22 = v96;
        if ( v96[0] )
        {
          while ( v22 - v96 < v74 >> 1 )
          {
            ObjectInfo = JetPrepareUpdate(v10, v70, 0);
            if ( ObjectInfo )
              goto LABEL_22;
            v23 = v22;
            while ( *v23++ )
              ;
            v25 = v23 - (v22 + 1);
            JetSetColumn(sesid, v70, *((_DWORD *)v73 + 2), v22, v25 * 2, 0, 0);
            v26 = &v22[v25 + 1];
            v27 = (char *)v26;
            do
            {
              v28 = *(_WORD *)v27;
              v27 += 2;
            }
            while ( v28 );
            v29 = (v27 - (char *)(v26 + 1)) >> 1;
            JetSetColumn(sesid, v70, *((_DWORD *)v73 + 3), v26, v29 * 2, 0, 0);
            v22 = &v26[v29 + 1];
            v10 = sesid;
            ObjectInfo = JetUpdate(sesid, v70, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_22;
            if ( !*v22 )
              break;
          }
        }
        v19 = v71;
      }
      v30 = JetRetrieveProperty(v10, v19[5], L"tables", pvData, 0, &v88, v96, 65504, &v74, 0, 0, 0);
      ObjectInfo = v30;
      if ( v30 != -3600 && v30 != -1907 )
      {
        if ( v30 )
          break;
        if ( (v74 & 0xFFFFFFFE) >= 0xFFE0 )
LABEL_109:
          __report_rangecheckfailure();
        v56 = v70;
        *(unsigned __int16 *)((char *)v96 + (v74 & 0xFFFFFFFE)) = 0;
        ObjectInfo = JetPrepareUpdate(v10, v56, 0);
        if ( ObjectInfo )
          break;
        v31 = v73;
        JetSetColumn(v10, v70, *((_DWORD *)v73 + 2), &v88, 0x1Eu, 0, 0);
        JetSetColumn(v10, v70, *((_DWORD *)v31 + 3), v96, wcslen(v96), 0, 0);
        v14 = CSchemaRowset::MapStringPropertyValueToColumn(
                v32,
                v10,
                v71[5],
                (const unsigned __int16 *)v32,
                pvData,
                0,
                L"ValidationText",
                v70,
                *((_DWORD *)v31 + 4),
                (int *)&ObjectInfo);
        if ( v14 < 0 )
          goto LABEL_97;
        ObjectInfo = JetUpdate(v10, v70, 0, 0, 0);
        if ( ObjectInfo )
          break;
        v19 = v71;
      }
      v33 = operator new(0x10u);
      v75 = v33;
      v79 = v33;
      if ( !v33 )
      {
        v14 = -2147024882;
        goto LABEL_97;
      }
      *v33 = &ColumnData::`vftable';
      v33[1] = 0;
      v33[2] = 0;
      v33[3] = 0;
      v14 = ColumnData::FInit((ColumnData *)v33, v10, v19[5], pvData, (int *)&ObjectInfo, 0);
      if ( v14 < 0 )
      {
        if ( (int)ObjectInfo > -1811 )
        {
          if ( ObjectInfo )
            goto LABEL_89;
        }
        else
        {
          if ( ObjectInfo != -1811 && ObjectInfo != -2001 && ObjectInfo != -1907 )
          {
LABEL_89:
            (*(void (__thiscall **)(_DWORD *, int))(*v75 + 4))(v75, 1);
            goto LABEL_96;
          }
          ObjectInfo = 0;
        }
      }
      v34 = v75;
      v35 = 0;
      v77 = 0;
      v79 = v75 + 1;
      if ( v75[1] )
      {
        v36 = v75 + 3;
        v76 = v75 + 3;
        do
        {
          v37 = *v36;
          v38 = 104 * v35;
          v39 = *(_DWORD *)(v37 + 104 * v35 + 4);
          if ( !v39 )
          {
            v40 = *(_DWORD *)(v37 + v38 + 24);
            if ( v40 && (unsigned int)(v40 - 2) >= 2 )
              v39 = 0;
            else
              v39 = *(_DWORD *)(v37 + v38 + 28);
          }
          v41 = JetRetrieveProperty(v10, v71[5], L"tables", pvData, v39, &v88, v96, 255, &v74, 0, 0, 0);
          ObjectInfo = v41;
          if ( v41 != -3600 && v41 != -1907 )
          {
            if ( v41 )
              goto LABEL_22;
            if ( (v74 & 0xFFFFFFFE) >= 0xFFE0 )
              goto LABEL_109;
            *(unsigned __int16 *)((char *)v96 + (v74 & 0xFFFFFFFE)) = 0;
            if ( wcslen(pvData) )
            {
              v42 = *v76;
              v43 = *(_WORD **)(*v76 + v38 + 4);
              if ( !v43 )
              {
                v44 = *(_DWORD *)(v42 + v38 + 24);
                if ( !v44 || (unsigned int)(v44 - 2) <= 1 )
                  v43 = *(_WORD **)(v42 + v38 + 28);
              }
              v45 = v43 + 1;
              while ( *v43++ )
                ;
              if ( v43 - v45 )
              {
                v95[0] = 0;
                WCSCPY((unsigned __int16 *)0xA6, (const unsigned __int16 *)v57, (unsigned int)v63);
                WCSCAT((unsigned __int16 *)0xA6, v58, v64);
                WCSCAT((unsigned __int16 *)0xA6, v59, v65);
                WCSCAT((unsigned __int16 *)0xA6, v60, v66);
                WCSCAT((unsigned __int16 *)0xA6, v61, v67);
                WCSCAT((unsigned __int16 *)0xA6, v62, v68);
                ObjectInfo = JetPrepareUpdate(v10, v70, 0);
                if ( ObjectInfo )
                  goto LABEL_22;
                JetSetColumn(v10, v70, *((_DWORD *)v73 + 2), v95, 2 * wcslen(v95), 0, 0);
                JetSetColumn(v10, v70, *((_DWORD *)v73 + 3), v96, 2 * wcslen(v96), 0, 0);
                v47 = *v76;
                v48 = *(const unsigned __int16 **)(*v76 + v38 + 4);
                if ( !v48 )
                {
                  v49 = *(_DWORD *)(v47 + v38 + 24);
                  if ( v49 && (unsigned int)(v49 - 2) >= 2 )
                    v48 = 0;
                  else
                    v48 = *(const unsigned __int16 **)(v47 + v38 + 28);
                }
                v14 = CSchemaRowset::MapStringPropertyValueToColumn(
                        v73,
                        v10,
                        v71[5],
                        (const unsigned __int16 *)v73,
                        pvData,
                        v48,
                        L"ValidationText",
                        v70,
                        *((_DWORD *)v73 + 4),
                        (int *)&ObjectInfo);
                if ( v14 < 0 )
                  goto LABEL_97;
                ObjectInfo = JetUpdate(v10, v70, 0, 0, 0);
                if ( ObjectInfo )
                  goto LABEL_22;
              }
            }
          }
          v35 = v77 + 1;
          v77 = v35;
          v36 = v76;
        }
        while ( v35 < *v79 );
        v34 = v75;
      }
      ObjectInfo = JetMove(v10, tableid, 1, 0);
      (*(void (__thiscall **)(_DWORD *, int))(*v34 + 4))(v34, 1);
      v19 = v71;
      if ( ++v78 >= v86 )
        goto LABEL_91;
      v10 = sesid;
    }
LABEL_22:
    v14 = -2147467259;
    goto LABEL_97;
  }
LABEL_91:
  v50 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
  v80 = v50;
  if ( v50 && (v51 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v50), (v52 = v51) != 0) )
  {
    *((_DWORD *)v51 + 4) = 0;
    *((_DWORD *)v51 + 5) = &SRSCheckConstraintsNames;
    *((_DWORD *)v51 + 7) = 0;
    v14 = ColumnData::FInit(v51, sesid, v19[5], v70, (int *)&ObjectInfo, 0, (int)&SRSCheckConstraintsNames);
    if ( v14 >= 0 )
    {
      v53 = v83;
      v55 = v82;
      *((_DWORD *)v52 + 1) = 5;
      v14 = CRowset::FInit(v53, 0, v71, 0, 0, 0, v70, v55, 1, 0, 0, v52, 1, 0, 0, &GUID_NULL);
    }
  }
  else
  {
LABEL_95:
    v14 = -2147024882;
  }
LABEL_96:
  v10 = sesid;
LABEL_97:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v57, v63);
    goto LABEL_103;
  }
  if ( v14 < 0 )
  {
    v10 = sesid;
    v15 = v71[5];
    v16 = v71[4];
    if ( v14 != -2147024882 )
      goto LABEL_101;
  }
LABEL_103:
  if ( tableid != -1 )
  {
    JetCloseTable(v10, tableid);
    tableid = -1;
  }
  if ( v73 && Sys )
    (*(void (__thiscall **)(_DWORD, int, CSchemaRowset *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v73);
  return v14;
}

```

## disassembly

```asm
0x1003c980  mov     edi, edi
0x1003c982  push    ebp
0x1003c983  mov     ebp, esp
0x1003c985  and     esp, 0FFFFFFF0h
0x1003c988  mov     eax, 10288h
0x1003c98d  call    __chkstk
0x1003c992  mov     eax, ___security_cookie
0x1003c997  xor     eax, esp
0x1003c999  mov     [esp+10288h+var_4], eax
0x1003c9a0  movups  xmm0, xmmword ptr ds:aValidationrule; "ValidationRule"
0x1003c9a7  mov     eax, [ebp+arg_8]
0x1003c9aa  push    esi; int
0x1003c9ab  movups  [esp+1028Ch+var_10210], xmm0
0x1003c9b0  mov     [esp+1028Ch+var_10248], eax
0x1003c9b4  movq    xmm0, qword ptr ds:aValidationrule+10h; "onRule"
0x1003c9bc  mov     eax, dword ptr ds:aValidationrule+18h; "le"
0x1003c9c1  movq    [esp+1028Ch+var_10200], xmm0
0x1003c9ca  movups  xmm0, xmmword ptr ds:aCheckconstrain; "CheckConstraints"
0x1003c9d1  push    edi; struct _GUID *
0x1003c9d2  mov     edi, edx
0x1003c9d4  mov     [esp+10290h+var_101F8], eax
0x1003c9db  movzx   eax, word ptr ds:aValidationrule+1Ch; ""
0x1003c9e2  mov     edx, [ebp+this]
0x1003c9e5  mov     [esp+10290h+var_101F4], ax
0x1003c9ed  movzx   eax, word ptr ds:aCheckconstrain+20h; ""
0x1003c9f4  mov     esi, [edi+10h]
0x1003c9f7  mov     [esp+10290h+var_10274], edi
0x1003c9fb  mov     [esp+10290h+var_10244], ecx
0x1003c9ff  mov     [esp+10290h+var_101D0], ax
0x1003ca07  mov     [esp+10290h+var_1027C], 0
0x1003ca0f  mov     [esp+10290h+sesid], esi
0x1003ca13  mov     [esp+10290h+var_1026C], 0
0x1003ca1b  mov     [esp+10290h+tableid], 0FFFFFFFFh
0x1003ca23  movups  [esp+10290h+var_101F0], xmm0
0x1003ca2b  movups  xmm0, xmmword ptr ds:aCheckconstrain+10h; "straints"
0x1003ca32  movups  [esp+10290h+var_101E0], xmm0
0x1003ca3a  test    edx, edx
0x1003ca3c  jz      short loc_1003CAB2
0x1003ca3e  mov     eax, [ebp+arg_4]
0x1003ca41  test    eax, eax
0x1003ca43  jz      short loc_1003CA9E
0x1003ca45  cmp     edx, 3
0x1003ca48  ja      short loc_1003CA9E
0x1003ca4a  movzx   ecx, word ptr [eax]
0x1003ca4d  test    cx, cx
0x1003ca50  jz      short loc_1003CA62
0x1003ca52  cmp     ecx, 1
0x1003ca55  jz      short loc_1003CA62
0x1003ca57  cmp     ecx, 8
0x1003ca5a  jnz     short loc_1003CA9E
0x1003ca5c  cmp     dword ptr [eax+8], 0
0x1003ca60  jnz     short loc_1003CA9E
0x1003ca62  cmp     edx, 1
0x1003ca65  jbe     short loc_1003CA80
0x1003ca67  movzx   ecx, word ptr [eax+10h]
0x1003ca6b  test    cx, cx
0x1003ca6e  jz      short loc_1003CA80
0x1003ca70  cmp     ecx, 1
0x1003ca73  jz      short loc_1003CA80
0x1003ca75  cmp     ecx, 8
0x1003ca78  jnz     short loc_1003CA9E
0x1003ca7a  cmp     dword ptr [eax+18h], 0
0x1003ca7e  jnz     short loc_1003CA9E
0x1003ca80  cmp     edx, 2
0x1003ca83  jbe     short loc_1003CAB2
0x1003ca85  movzx   ecx, word ptr [eax+20h]
0x1003ca89  test    cx, cx
0x1003ca8c  jz      short loc_1003CAB2
0x1003ca8e  cmp     ecx, 1
0x1003ca91  jz      short loc_1003CAB2
0x1003ca93  cmp     ecx, 8
0x1003ca96  jnz     short loc_1003CA9E
0x1003ca98  cmp     dword ptr [eax+28h], 0
0x1003ca9c  jz      short loc_1003CAB2
0x1003ca9e  mov     ecx, [esp+10290h+var_10274]
0x1003caa2  mov     edi, 80070057h
0x1003caa7  mov     eax, [ecx+14h]
0x1003caaa  mov     ecx, [ecx+10h]
0x1003caad  jmp     loc_1003D30F
0x1003cab2  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003cab8  push    14h
0x1003caba  push    ecx
0x1003cabb  mov     eax, [ecx]
0x1003cabd  mov     esi, [eax+0Ch]
0x1003cac0  mov     ecx, esi
0x1003cac2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003cac8  call    esi
0x1003caca  mov     [esp+10290h+var_1026C], eax
0x1003cace  test    eax, eax
0x1003cad0  jz      loc_1003D2C4
0x1003cad6  push    0
0x1003cad8  push    eax
0x1003cad9  lea     eax, [esp+10298h+var_10278]
0x1003cadd  mov     edx, edi
0x1003cadf  push    eax
0x1003cae0  mov     ecx, 0Ah
0x1003cae5  call    SRSCreateTempTable
0x1003caea  mov     esi, [esp+10290h+sesid]
0x1003caee  mov     edi, eax
0x1003caf0  test    edi, edi
0x1003caf2  js      loc_1003D2CD
0x1003caf8  mov     edi, [esp+10290h+var_10274]
0x1003cafc  lea     eax, [esp+10290h+var_10240]
0x1003cb00  push    1
0x1003cb02  push    30h ; '0'
0x1003cb04  push    eax
0x1003cb05  push    0
0x1003cb07  push    offset aTables_0; "tables"
0x1003cb0c  push    1
0x1003cb0e  push    dword ptr [edi+14h]
0x1003cb11  push    esi
0x1003cb12  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003cb18  mov     [esp+10290h+var_1027C], eax
0x1003cb1c  test    eax, eax
0x1003cb1e  jz      short loc_1003CB2A
0x1003cb20  mov     edi, 80004005h
0x1003cb25  jmp     loc_1003D2CD
0x1003cb2a  push    0; grbit
0x1003cb2c  push    80000000h; cRow
0x1003cb31  push    [esp+10298h+tableid]; tableid
0x1003cb35  push    esi; sesid
0x1003cb36  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003cb3c  mov     [esp+10290h+var_1027C], eax
0x1003cb40  cmp     eax, 0FFFFF9BDh
0x1003cb45  jz      short loc_1003CB55
0x1003cb47  test    eax, eax
0x1003cb49  jz      short loc_1003CB55
0x1003cb4b  mov     edi, 80004005h
0x1003cb50  jmp     loc_1003D2CD
0x1003cb55  cmp     [esp+10290h+var_10238], 0
0x1003cb5a  mov     [esp+10290h+var_10258], 0
0x1003cb62  jbe     loc_1003D234
0x1003cb68  push    0; pretinfo
0x1003cb6a  push    0; grbit
0x1003cb6c  lea     eax, [esp+10298h+pcbActual]
0x1003cb70  push    eax; pcbActual
0x1003cb71  push    81h; cbData
0x1003cb76  lea     eax, [esp+102A0h+pvData]
0x1003cb7d  push    eax; pvData
0x1003cb7e  push    [esp+102A4h+columnid]; columnid
0x1003cb82  push    [esp+102A8h+tableid]; tableid
0x1003cb86  push    esi; sesid
0x1003cb87  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1003cb8d  mov     [esp+10290h+var_1027C], eax
0x1003cb91  test    eax, eax
0x1003cb93  jnz     short loc_1003CB20
0x1003cb95  mov     eax, [esp+10290h+pcbActual]
0x1003cb99  and     eax, 0FFFFFFFEh
0x1003cb9c  cmp     eax, 82h
0x1003cba1  jnb     loc_1003D384
0x1003cba7  xor     ecx, ecx
0x1003cba9  push    ecx
0x1003cbaa  push    ecx
0x1003cbab  push    ecx
0x1003cbac  mov     [esp+eax+1029Ch+pvData], cx
0x1003cbb4  lea     eax, [esp+1029Ch+var_10268]
0x1003cbb8  push    eax
0x1003cbb9  push    0FFE0h
0x1003cbbe  lea     eax, [esp+102A4h+var_FFE8]
0x1003cbc5  push    eax
0x1003cbc6  lea     eax, [esp+102A8h+var_101F0]
0x1003cbcd  push    eax
0x1003cbce  push    ecx
0x1003cbcf  lea     eax, [esp+102B0h+pvData]
0x1003cbd6  push    eax
0x1003cbd7  push    offset aTables_0; "tables"
0x1003cbdc  push    dword ptr [edi+14h]
0x1003cbdf  push    esi
0x1003cbe0  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x1003cbe6  mov     [esp+10290h+var_1027C], eax
0x1003cbea  cmp     eax, 0FFFFF1F0h
0x1003cbef  jz      loc_1003CCF6
0x1003cbf5  cmp     eax, 0FFFFF88Dh
0x1003cbfa  jz      loc_1003CCF6
0x1003cc00  test    eax, eax
0x1003cc02  jnz     loc_1003CB20
0x1003cc08  lea     edi, [esp+10290h+var_FFE8]
0x1003cc0f  cmp     [esp+10290h+var_FFE8], ax
0x1003cc17  jz      loc_1003CCF2
0x1003cc1d  nop     dword ptr [eax]
0x1003cc20  lea     eax, [esp+10290h+var_FFE8]
0x1003cc27  mov     ecx, edi
0x1003cc29  sub     ecx, eax
0x1003cc2b  mov     eax, [esp+10290h+var_10268]
0x1003cc2f  sar     ecx, 1
0x1003cc31  shr     eax, 1
0x1003cc33  cmp     ecx, eax
0x1003cc35  jnb     loc_1003CCF2
0x1003cc3b  push    0; prep
0x1003cc3d  push    [esp+10294h+var_10278]; tableid
0x1003cc41  push    esi; sesid
0x1003cc42  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1003cc48  mov     [esp+10290h+var_1027C], eax
0x1003cc4c  test    eax, eax
0x1003cc4e  jnz     loc_1003CB20
0x1003cc54  mov     eax, edi
0x1003cc56  lea     edx, [eax+2]
0x1003cc59  nop     dword ptr [eax+00000000h]
0x1003cc60  mov     cx, [eax]
0x1003cc63  add     eax, 2
0x1003cc66  test    cx, cx
0x1003cc69  jnz     short loc_1003CC60
0x1003cc6b  sub     eax, edx
0x1003cc6d  push    0; psetinfo
0x1003cc6f  sar     eax, 1
0x1003cc71  push    0; grbit
0x1003cc73  lea     esi, [eax+eax]
0x1003cc76  mov     eax, [esp+10298h+var_1026C]
0x1003cc7a  push    esi; cbData
0x1003cc7b  push    edi; pvData
0x1003cc7c  push    dword ptr [eax+8]; columnid
0x1003cc7f  push    [esp+102A4h+var_10278]; tableid
0x1003cc83  push    [esp+102A8h+sesid]; sesid
0x1003cc87  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003cc8d  add     esi, 2
0x1003cc90  add     edi, esi
0x1003cc92  mov     esi, edi
0x1003cc94  lea     ecx, [esi+2]
0x1003cc97  mov     ax, [esi]
0x1003cc9a  add     esi, 2
0x1003cc9d  test    ax, ax
0x1003cca0  jnz     short loc_1003CC97
0x1003cca2  mov     eax, [esp+10290h+var_1026C]
0x1003cca6  sub     esi, ecx
0x1003cca8  push    0; psetinfo
0x1003ccaa  push    0; grbit
0x1003ccac  sar     esi, 1
0x1003ccae  add     esi, esi
0x1003ccb0  push    esi; cbData
0x1003ccb1  push    edi; pvData
0x1003ccb2  push    dword ptr [eax+0Ch]; columnid
0x1003ccb5  push    [esp+102A4h+var_10278]; tableid
0x1003ccb9  push    [esp+102A8h+sesid]; sesid
0x1003ccbd  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003ccc3  push    0; pcbActual
0x1003ccc5  push    0; cbBookmark
0x1003ccc7  push    0; pvBookmark
0x1003ccc9  push    [esp+1029Ch+var_10278]; tableid
0x1003cccd  add     esi, 2
0x1003ccd0  add     edi, esi
0x1003ccd2  mov     esi, [esp+102A0h+sesid]
0x1003ccd6  push    esi; sesid
0x1003ccd7  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1003ccdd  mov     [esp+10290h+var_1027C], eax
0x1003cce1  test    eax, eax
0x1003cce3  jnz     loc_1003CB20
0x1003cce9  cmp     [edi], ax
0x1003ccec  jnz     loc_1003CC20
0x1003ccf2  mov     edi, [esp+10290h+var_10274]
0x1003ccf6  push    0
0x1003ccf8  push    0
0x1003ccfa  push    0
0x1003ccfc  lea     eax, [esp+1029Ch+var_10268]
0x1003cd00  push    eax
0x1003cd01  push    0FFE0h
0x1003cd06  lea     eax, [esp+102A4h+var_FFE8]
0x1003cd0d  push    eax
0x1003cd0e  lea     eax, [esp+102A8h+var_10210]
0x1003cd15  push    eax
0x1003cd16  push    0
0x1003cd18  lea     eax, [esp+102B0h+pvData]
0x1003cd1f  push    eax
0x1003cd20  push    offset aTables_0; "tables"
0x1003cd25  push    dword ptr [edi+14h]
0x1003cd28  push    esi
0x1003cd29  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x1003cd2f  mov     [esp+10290h+var_1027C], eax
0x1003cd33  cmp     eax, 0FFFFF1F0h
0x1003cd38  jz      loc_1003CE2E
0x1003cd3e  cmp     eax, 0FFFFF88Dh
0x1003cd43  jz      loc_1003CE2E
0x1003cd49  test    eax, eax
0x1003cd4b  jnz     loc_1003CB20
0x1003cd51  mov     eax, [esp+10290h+var_10268]
0x1003cd55  and     eax, 0FFFFFFFEh
0x1003cd58  cmp     eax, 0FFE0h
0x1003cd5d  jnb     loc_1003D384
0x1003cd63  xor     ecx, ecx
0x1003cd65  push    ecx; prep
0x1003cd66  push    [esp+10294h+var_10278]; tableid
0x1003cd6a  mov     [esp+eax+10298h+var_FFE8], cx
0x1003cd72  push    esi; sesid
0x1003cd73  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1003cd79  mov     [esp+10290h+var_1027C], eax
0x1003cd7d  test    eax, eax
0x1003cd7f  jnz     loc_1003CB20
0x1003cd85  mov     edi, [esp+10290h+var_1026C]
0x1003cd89  push    eax; psetinfo
0x1003cd8a  push    eax; grbit
0x1003cd8b  push    1Eh; cbData
0x1003cd8d  lea     eax, [esp+1029Ch+var_10210]
0x1003cd94  push    eax; pvData
0x1003cd95  push    dword ptr [edi+8]; columnid
0x1003cd98  push    [esp+102A4h+var_10278]; tableid
0x1003cd9c  push    esi; sesid
0x1003cd9d  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003cda3  lea     ecx, [esp+10290h+var_FFE8]
0x1003cdaa  lea     edx, [ecx+2]
0x1003cdad  nop     dword ptr [eax]
0x1003cdb0  mov     ax, [ecx]
  ... truncated ...
```
