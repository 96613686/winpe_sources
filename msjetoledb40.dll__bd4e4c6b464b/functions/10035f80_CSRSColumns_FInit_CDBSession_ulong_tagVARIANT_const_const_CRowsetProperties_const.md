# CSRSColumns::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x10035f80`
- end: `0x10036a95`
- name: `?FInit@CSRSColumns@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `2837`
- prototype: `int __userpurge@<eax>(_DWORD *@<edx>, int@<ecx>, CSRSColumns *this, wchar_t **, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d570`
- `0x10013020`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035cc0`
- `0x10035e60`
- `0x10035f80`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003633d`
- `msvcrt!_wcsicmp` at `0x10036470`
- `msvcrt!_wcsicmp` at `0x1003633d`
- `msvcrt!_wcsicmp` at `0x10036470`
- `msjet40!__imp__JetCloseTable@8` at `0x1003630d`
- `msjet40!__imp__JetCloseTable@8` at `0x100368e6`
- `msjet40!__imp__JetCloseTable@8` at `0x10036a57`
- `msjet40!__imp__JetCloseTable@8` at `0x10036a71`
- `msjet40!__imp__JetCloseTable@8` at `0x1003630d`
- `msjet40!__imp__JetCloseTable@8` at `0x100368e6`
- `msjet40!__imp__JetCloseTable@8` at `0x10036a57`
- `msjet40!__imp__JetCloseTable@8` at `0x10036a71`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100369fa`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100369fa`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10036176`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10036176`
- `msjet40!__imp__JetMove@16` at `0x10036199`
- `msjet40!__imp__JetMove@16` at `0x100368ba`
- `msjet40!__imp__JetMove@16` at `0x10036199`
- `msjet40!__imp__JetMove@16` at `0x100368ba`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003648a`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003648a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100361fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003624e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100362b2`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100361fb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003624e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100362b2`
- `msjet40!__imp__JetSetColumn@28` at `0x100364d3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003656f`
- `msjet40!__imp__JetSetColumn@28` at `0x1003658e`
- `msjet40!__imp__JetSetColumn@28` at `0x100365c9`
- `msjet40!__imp__JetSetColumn@28` at `0x10036608`
- `msjet40!__imp__JetSetColumn@28` at `0x10036643`
- `msjet40!__imp__JetSetColumn@28` at `0x1003665e`
- `msjet40!__imp__JetSetColumn@28` at `0x1003668a`
- `msjet40!__imp__JetSetColumn@28` at `0x100366e3`
- `msjet40!__imp__JetSetColumn@28` at `0x10036709`
- `msjet40!__imp__JetSetColumn@28` at `0x10036776`
- `msjet40!__imp__JetSetColumn@28` at `0x100367bd`
- `msjet40!__imp__JetSetColumn@28` at `0x100367e7`
- `msjet40!__imp__JetSetColumn@28` at `0x100364d3`
- `msjet40!__imp__JetSetColumn@28` at `0x1003656f`
- `msjet40!__imp__JetSetColumn@28` at `0x1003658e`
- `msjet40!__imp__JetSetColumn@28` at `0x100365c9`
- `msjet40!__imp__JetSetColumn@28` at `0x10036608`
- `msjet40!__imp__JetSetColumn@28` at `0x10036643`
- `msjet40!__imp__JetSetColumn@28` at `0x1003665e`
- `msjet40!__imp__JetSetColumn@28` at `0x1003668a`
- `msjet40!__imp__JetSetColumn@28` at `0x100366e3`
- `msjet40!__imp__JetSetColumn@28` at `0x10036709`
- `msjet40!__imp__JetSetColumn@28` at `0x10036776`
- `msjet40!__imp__JetSetColumn@28` at `0x100367bd`
- `msjet40!__imp__JetSetColumn@28` at `0x100367e7`
- `msjet40!__imp__JetUpdate@20` at `0x10036848`
- `msjet40!__imp__JetUpdate@20` at `0x10036848`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100362f3`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100362f3`
- `msjet40!__imp__JetGetPropertyBlob@28` at `0x10036404`
- `msjet40!__imp__JetGetPropertyBlob@28` at `0x10036404`
- `msjet40!__imp__JetFreePropertyBlob@4` at `0x1003687f`
- `msjet40!__imp__JetFreePropertyBlob@4` at `0x1003687f`

## pseudocode

```c
int __userpurge CSRSColumns::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSColumns *this,
        wchar_t **a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_COLUMNID *v8; // esi
  JET_SESID v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  _DWORD *v14; // ebx
  int PropertyBlob; // edi
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  wchar_t *v19; // eax
  int v20; // eax
  JET_COLUMNID *v21; // eax
  int v22; // eax
  int v23; // esi
  int v24; // eax
  JET_ERR v25; // eax
  JET_SESID v26; // esi
  bool v27; // zf
  _DWORD *v28; // eax
  _DWORD *v29; // esi
  _DWORD *v30; // edx
  unsigned int v31; // eax
  _DWORD *v32; // ecx
  const wchar_t *v33; // eax
  int v34; // eax
  JET_COLUMNID *v35; // edi
  _DWORD *v36; // edx
  _BYTE *v37; // esi
  char *v38; // eax
  __int16 v39; // cx
  int v40; // eax
  int v41; // eax
  _WORD *v42; // eax
  _WORD *v43; // esi
  int v45; // ecx
  _DWORD *v46; // esi
  int v47; // ecx
  unsigned int v48; // edx
  int v49; // eax
  const void *v50; // esi
  char *v51; // ecx
  __int16 v52; // ax
  int v53; // eax
  __int16 v54; // cx
  unsigned __int8 v55; // al
  int v56; // eax
  int v57; // eax
  unsigned __int8 v58; // al
  _DWORD *v59; // ecx
  const unsigned __int16 *v60; // eax
  int v61; // eax
  JET_SESID v62; // edi
  ColumnDataWithFakeNamesAndDBTYPES *v63; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v64; // esi
  int v65; // ecx
  unsigned int v67; // [esp-20h] [ebp-19Ch]
  JET_COLUMNID v68; // [esp-10h] [ebp-18Ch]
  const struct _GUID *v69; // [esp+4h] [ebp-178h]
  const struct _GUID *v70; // [esp+8h] [ebp-174h]
  JET_TABLEID v71; // [esp+14h] [ebp-168h] BYREF
  unsigned __int16 v72[2]; // [esp+18h] [ebp-164h] BYREF
  JET_COLUMNID *v73; // [esp+1Ch] [ebp-160h]
  unsigned int v74; // [esp+20h] [ebp-15Ch] BYREF
  _DWORD *v75; // [esp+24h] [ebp-158h]
  int v76; // [esp+28h] [ebp-154h] BYREF
  JET_SESID sesid; // [esp+2Ch] [ebp-150h]
  unsigned int v78; // [esp+30h] [ebp-14Ch] BYREF
  _DWORD *v79; // [esp+34h] [ebp-148h]
  int v80; // [esp+38h] [ebp-144h] BYREF
  BOOL v81; // [esp+3Ch] [ebp-140h]
  _DWORD *v82; // [esp+40h] [ebp-13Ch]
  int v83; // [esp+44h] [ebp-138h]
  void *v84; // [esp+48h] [ebp-134h] BYREF
  int v85; // [esp+4Ch] [ebp-130h]
  int v86; // [esp+50h] [ebp-12Ch] BYREF
  int pvData; // [esp+54h] [ebp-128h] BYREF
  struct CDBSession *v88; // [esp+58h] [ebp-124h]
  _DWORD *v89; // [esp+5Ch] [ebp-120h]
  unsigned int pcbActual; // [esp+60h] [ebp-11Ch] BYREF
  wchar_t *String2; // [esp+64h] [ebp-118h]
  ColumnDataWithFakeNamesAndDBTYPES *v92; // [esp+68h] [ebp-114h] BYREF
  int v93; // [esp+6Ch] [ebp-110h] BYREF
  unsigned int v94; // [esp+70h] [ebp-10Ch] BYREF
  int v95; // [esp+74h] [ebp-108h] BYREF
  unsigned int v96; // [esp+78h] [ebp-104h]
  int v97; // [esp+7Ch] [ebp-100h]
  unsigned int v98; // [esp+80h] [ebp-FCh] BYREF
  int v99; // [esp+84h] [ebp-F8h] BYREF
  JET_TABLEID tableid; // [esp+88h] [ebp-F4h]
  unsigned int v101; // [esp+8Ch] [ebp-F0h]
  JET_COLUMNID v102; // [esp+94h] [ebp-E8h]
  JET_COLUMNID columnid; // [esp+98h] [ebp-E4h]
  JET_COLUMNID v104; // [esp+A8h] [ebp-D4h]
  int v105; // [esp+B4h] [ebp-C8h] BYREF
  JET_TABLEID v106; // [esp+B8h] [ebp-C4h]
  int v107; // [esp+BCh] [ebp-C0h]
  wchar_t String1[70]; // [esp+ECh] [ebp-90h] BYREF

  v97 = a2;
  v8 = 0;
  v96 = a5;
  v82 = a1;
  v9 = a1[4];
  v88 = (struct CDBSession *)a4;
  sesid = v9;
  *(_DWORD *)v72 = 0;
  v75 = 0;
  v84 = 0;
  v80 = 0;
  v81 = 0;
  String2 = 0;
  tableid = -1;
  v71 = -1;
  if ( this )
  {
    if ( !a4 )
      goto LABEL_21;
    if ( (unsigned int)this > 4 )
      goto LABEL_21;
    v10 = *(unsigned __int16 *)a4;
    if ( (_WORD)v10 )
    {
      if ( v10 != 1 && (v10 != 8 || a4[2]) )
        goto LABEL_21;
    }
    if ( (unsigned int)this > 1 )
    {
      v11 = *((unsigned __int16 *)a4 + 8);
      if ( (_WORD)v11 )
      {
        if ( v11 != 1 && (v11 != 8 || a4[6]) )
          goto LABEL_21;
      }
    }
    if ( (unsigned int)this > 2 )
    {
      v12 = *((unsigned __int16 *)a4 + 16);
      if ( (_WORD)v12 )
      {
        if ( v12 != 1 && v12 != 8 )
          goto LABEL_21;
      }
    }
    if ( (unsigned int)this <= 3 )
    {
      if ( (unsigned int)this < 3 )
        goto LABEL_30;
    }
    else
    {
      v13 = *((unsigned __int16 *)a4 + 24);
      if ( (_WORD)v13 && v13 != 1 && v13 != 8 )
      {
LABEL_21:
        v14 = a1;
        PropertyBlob = -2147024809;
        v16 = a1[5];
        v17 = a1[4];
LABEL_156:
        if ( !JetGetDatabaseInfo(v17, v16, &v92, 4, 3) )
          CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v69, (int)v70);
        goto LABEL_158;
      }
    }
    v18 = *((unsigned __int16 *)a4 + 16);
    if ( (_WORD)v18 && v18 != 1 )
    {
      v19 = a4[10];
      v80 = 1;
      String2 = v19;
    }
    if ( (unsigned int)this >= 4 )
    {
      v20 = *((unsigned __int16 *)a4 + 24);
      v81 = (_WORD)v20 && v20 != 1;
    }
  }
LABEL_30:
  v21 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          112);
  v8 = v21;
  v73 = v21;
  if ( !v21 )
  {
    PropertyBlob = -2147024882;
LABEL_32:
    v14 = v82;
    goto LABEL_152;
  }
  PropertyBlob = SRSCreateTempTable(0, a1, &v71, v21, 0);
  if ( PropertyBlob )
    goto LABEL_32;
  v22 = 1;
  if ( (unsigned int)this >= 3 && *((_WORD *)v88 + 16) == 1 || (unsigned int)this >= 4 && *((_WORD *)v88 + 24) == 1 )
    v22 = 0;
  if ( v81 && *((_WORD *)v88 + 24) == 8 && !*((_DWORD *)v88 + 14) )
    v22 = 0;
  if ( v80 )
  {
    v23 = 0;
    if ( *((_DWORD *)v88 + 10) )
      v23 = v22;
    if ( v80 == 1 )
    {
      v24 = *((_DWORD *)v88 + 10);
      goto LABEL_51;
    }
  }
  else
  {
    v23 = v22;
  }
  v24 = 0;
LABEL_51:
  v14 = v82;
  *(_DWORD *)v72 = JetGetObjectInfo(sesid, v82[5], 0, L"tables", v24, &v99, 48, 1);
  if ( *(_DWORD *)v72 )
    goto LABEL_150;
  v25 = JetMove(sesid, tableid, 0x80000000, 0);
  *(_DWORD *)v72 = v25;
  if ( v25 != -1603 )
  {
    if ( v25 )
      goto LABEL_150;
  }
  if ( v101 )
  {
    v75 = 0;
    v85 = 0;
    if ( v23 )
    {
      v26 = sesid;
      while ( 2 )
      {
        *(_DWORD *)v72 = JetRetrieveColumn(v26, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
        if ( !*(_DWORD *)v72 )
        {
          switch ( pvData )
          {
            case 1:
            case 4:
            case 5:
            case 6:
              *(_DWORD *)v72 = JetRetrieveColumn(v26, tableid, v102, String1, 0x81u, &pcbActual, 0, 0);
              if ( *(_DWORD *)v72 )
                goto LABEL_150;
              if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
                __report_rangecheckfailure();
              v27 = pvData == 5;
              *(wchar_t *)((char *)String1 + (pcbActual & 0xFFFFFFFE)) = 0;
              if ( v27 )
              {
                v106 = -1;
                *(_DWORD *)v72 = JetRetrieveColumn(v26, tableid, v104, &v93, 4u, &v98, 0, 0);
                if ( *(_DWORD *)v72 )
                  goto LABEL_150;
                if ( pvData == 5 && (_WORD)v93 )
                  goto LABEL_142;
                *(_DWORD *)v72 = JetGetQueryParameterInfo(v26, v14[5], String1, &v105, 56, &v92);
                if ( *(_DWORD *)v72 )
                  goto LABEL_142;
                *(_DWORD *)v72 = JetCloseTable(v26, v106);
                if ( *(_DWORD *)v72 )
                  goto LABEL_150;
                if ( v107 )
                  goto LABEL_142;
              }
              if ( String2 && __wcsicmp(String1, String2) )
                goto LABEL_142;
              if ( v75 )
                (*(void (__thiscall **)(_DWORD *, int))(*v75 + 4))(v75, 1);
              v28 = operator new(0x10u);
              v29 = v28;
              v75 = v28;
              v89 = v28;
              if ( !v28 )
              {
                v75 = 0;
                goto LABEL_149;
              }
              *v28 = &ColumnData::`vftable';
              v28[1] = 0;
              v28[2] = 0;
              v28[3] = 0;
              PropertyBlob = ColumnData::FInit((ColumnData *)v28, sesid, v14[5], String1, (int *)v72, 1);
              if ( PropertyBlob >= 0 )
                goto LABEL_78;
              if ( *(_DWORD *)v72 != -2001 && *(_DWORD *)v72 != -1907 && *(_DWORD *)v72 != -1811 )
                goto LABEL_151;
              *(_DWORD *)v72 = 0;
LABEL_78:
              PropertyBlob = JetGetPropertyBlob(v14[4], v14[5], L"Tables", String1, 0, &v84, 0);
              v74 = 0;
              v79 = v29;
              if ( !v75[1] )
                goto LABEL_139;
              v30 = v75 + 3;
              v29 = v75;
              v89 = v75 + 3;
              v31 = 0;
              v79 = v75;
              break;
            default:
LABEL_142:
              *(_DWORD *)v72 = JetMove(v26, tableid, 1, 0);
              if ( ++v85 >= v101 )
                goto LABEL_143;
              continue;
          }
          while ( 1 )
          {
            v32 = (_DWORD *)(*v30 + 104 * v31);
            v83 = v32[9];
            if ( !v81 )
              goto LABEL_87;
            v33 = (const wchar_t *)v32[1];
            if ( !v33 )
            {
              v34 = v32[6];
              if ( v34 && (unsigned int)(v34 - 2) >= 2 )
                v33 = 0;
              else
                v33 = (const wchar_t *)v32[7];
            }
            if ( !__wcsicmp(*((const wchar_t **)v88 + 14), v33) )
            {
LABEL_87:
              *(_DWORD *)v72 = JetPrepareUpdate(v14[4], v71, 0);
              if ( *(_DWORD *)v72 )
                goto LABEL_150;
              v35 = v73;
              JetSetColumn(v14[4], v71, v73[2], String1, 2 * wcslen(String1), 0, 0);
              v36 = (_DWORD *)(*v89 + 104 * v74);
              v37 = (_BYTE *)v36[1];
              if ( v37 )
              {
                v38 = (char *)v36[1];
                do
                {
                  v39 = *(_WORD *)v38;
                  v38 += 2;
                }
                while ( v39 );
                v40 = (v38 - (v37 + 2)) >> 1;
              }
              else
              {
                v41 = v36[6];
                if ( v41 && (unsigned int)(v41 - 2) >= 2 )
                  v42 = 0;
                else
                  v42 = (_WORD *)v36[7];
                v43 = v42 + 1;
                while ( *v42++ )
                  ;
                v45 = v36[6];
                v40 = v42 - v43;
                if ( v45 && (unsigned int)(v45 - 2) >= 2 )
                  v37 = 0;
                else
                  v37 = (_BYTE *)v36[7];
              }
              JetSetColumn(v14[4], v71, v35[3], v37, 2 * v40, 0, 0);
              ++v74;
              JetSetColumn(v14[4], v71, v35[6], &v74, 4u, 0, 0);
              v46 = v79;
              v47 = 104 * --v74;
              v68 = v35[7];
              v80 = *(_DWORD *)(v47 + v79[3] + 64) != 0;
              JetSetColumn(v14[4], v71, v68, &v80, 4u, 0, 0);
              v48 = v74;
              v49 = v46[3];
              v50 = *(const void **)(104 * v74 + v49 + 64);
              if ( v50 )
              {
                v51 = *(char **)(104 * v74 + v49 + 64);
                do
                {
                  v52 = *(_WORD *)v51;
                  v51 += 2;
                }
                while ( v52 );
                JetSetColumn(v14[4], v71, v35[8], v50, 2 * ((v51 - ((_BYTE *)v50 + 2)) >> 1), 0, 0);
                v48 = v74;
              }
              v29 = v79;
              v94 = *(_DWORD *)(104 * v48 + v79[3] + 56);
              v80 = (v94 >> 5) & 1;
              JetSetColumn(v14[4], v71, v35[10], &v80, 4u, 0, 0);
              JetSetColumn(v14[4], v71, v35[9], &v94, 4u, 0, 0);
              LOWORD(v86) = word_100510F0[4 * v83];
              JetSetColumn(v14[4], v71, v35[11], &v86, 2u, 0, 0);
              switch ( v83 )
              {
                case 1:
                case 9:
                case 10:
                case 17:
                  v78 = *(_DWORD *)(104 * v74 + v29[3] + 44);
                  if ( v78 != -1 )
                    goto LABEL_110;
                  break;
                case 11:
                case 12:
                  v78 = 0;
LABEL_110:
                  if ( v83 != 1 )
                  {
                    JetSetColumn(v14[4], v71, v35[14], &v78, 4u, 0, 0);
                    if ( v83 == 10 )
                      v78 >>= 1;
                  }
                  JetSetColumn(v14[4], v71, v35[13], &v78, 4u, 0, 0);
                  break;
                default:
                  break;
              }
              v78 = 0;
              v53 = v29[3] + 104 * v74;
              v54 = *(_WORD *)(v53 + 40);
              if ( v54 == 131 )
              {
                v55 = *(_BYTE *)(v53 + 48);
              }
              else
              {
                v56 = 0;
                while ( word_10004700[2 * v56] != v54 )
                {
                  if ( (unsigned int)++v56 >= 8 )
                  {
                    v55 = -1;
                    goto LABEL_121;
                  }
                }
                v55 = byte_10004702[4 * v56];
              }
LABEL_121:
              LOWORD(v76) = v55;
              if ( v55 != 255 )
                JetSetColumn(v14[4], v71, v35[15], &v76, 2u, 0, 0);
              v57 = v29[3] + 104 * v74;
              if ( *(_WORD *)(v57 + 40) == 131 )
                v58 = *(_BYTE *)(v57 + 49);
              else
                v58 = -1;
              LOWORD(v76) = v58;
              if ( v58 != 255 )
                JetSetColumn(v14[4], v71, v35[16], &v76, 2u, 0, 0);
              if ( v83 == 8 )
              {
                v95 = 0;
                JetSetColumn(v14[4], v71, v35[17], &v95, 4u, 0, 0);
              }
              v59 = (_DWORD *)(v29[3] + 104 * v74);
              v60 = (const unsigned __int16 *)v59[1];
              if ( !v60 )
              {
                v61 = v59[6];
                if ( v61 && (unsigned int)(v61 - 2) >= 2 )
                  v60 = 0;
                else
                  v60 = (const unsigned __int16 *)v59[7];
              }
              PropertyBlob = (int)CSchemaRowset::MapStringPropertyBlobValueToColumn(
                                    (CSchemaRowset *)v72,
                                    v84,
                                    sesid,
                                    (unsigned int)v72,
                                    v60,
                                    v72,
                                    v71,
                                    v35[27],
                                    (int *)v72);
              if ( PropertyBlob < 0 )
                goto LABEL_151;
              *(_DWORD *)v72 = JetUpdate(v14[4], v71, 0, 0, 0);
              if ( *(_DWORD *)v72 )
                goto LABEL_150;
              if ( v81 )
              {
LABEL_139:
                if ( v84 )
                {
                  JetFreePropertyBlob(v84);
                  v84 = 0;
                }
                (*(void (__thiscall **)(_DWORD *, int))(*v29 + 4))(v79, 1);
                v26 = sesid;
                v75 = 0;
                goto LABEL_142;
              }
            }
            v30 = v89;
            v31 = v74 + 1;
            v74 = v31;
            if ( v31 >= v29[1] )
              goto LABEL_139;
          }
        }
        goto LABEL_151;
      }
    }
  }
LABEL_143:
  v62 = sesid;
  *(_DWORD *)v72 = JetCloseTable(sesid, tableid);
  tableid = -1;
  if ( *(_DWORD *)v72 )
  {
LABEL_150:
    PropertyBlob = -2147467259;
  }
  else
  {
    v63 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
    v92 = v63;
    if ( v63 && (v64 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v63)) != 0 )
    {
      *((_DWORD *)v64 + 4) = dword_10008720;
      *((_DWORD *)v64 + 5) = &SRSColumnsDefNames;
      *((_DWORD *)v64 + 7) = 0;
      PropertyBlob = ColumnData::FInit(v64, v62, v14[5], v71, (int *)v72, 0, (int)&SRSColumnsDefNames);
      if ( PropertyBlob >= 0 )
      {
        v65 = v97;
        v67 = v96;
        *((_DWORD *)v64 + 1) = 28;
        PropertyBlob = CRowset::FInit(v65, 0, v14, 0, 0, 0, v71, v67, 1, 0, 0, v64, 1, 0, 0, &GUID_NULL);
      }
    }
    else
    {
LABEL_149:
      PropertyBlob = -2147024882;
    }
  }
LABEL_151:
  v8 = v73;
LABEL_152:
  if ( *(_DWORD *)v72 )
  {
    CExtError::SendJetErrortoOLEAuto(*(unsigned int *)v72, (int)&IID_IDBSchemaRowset, (int)v69, v70);
    goto LABEL_158;
  }
  if ( PropertyBlob < 0 )
  {
    v16 = v14[5];
    v17 = v14[4];
    v14 = v82;
    if ( PropertyBlob != -2147024882 )
      goto LABEL_156;
  }
LABEL_158:
  if ( v8 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v8);
  if ( v75 )
    (*(void (__thiscall **)(_DWORD *, int))(*v75 + 4))(v75, 1);
  if ( PropertyBlob < 0 )
    *(_DWORD *)v72 = JetCloseTable(v14[4], v71);
  if ( tableid != -1 )
    JetCloseTable(v14[4], tableid);
  return PropertyBlob;
}

```

## disassembly

```asm
0x10035f80  mov     edi, edi
0x10035f82  push    ebp
0x10035f83  mov     ebp, esp
0x10035f85  and     esp, 0FFFFFFF8h
0x10035f88  sub     esp, 16Ch
0x10035f8e  mov     eax, ___security_cookie
0x10035f93  xor     eax, esp
0x10035f95  mov     [esp+16Ch+var_4], eax
0x10035f9c  mov     eax, [ebp+arg_8]
0x10035f9f  push    ebx
0x10035fa0  mov     ebx, [ebp+this]
0x10035fa3  push    esi; int
0x10035fa4  push    edi; struct _GUID *
0x10035fa5  mov     edi, edx
0x10035fa7  mov     [esp+178h+var_100], ecx
0x10035fab  mov     ecx, [ebp+arg_4]
0x10035fae  xor     esi, esi
0x10035fb0  mov     [esp+178h+var_104], eax
0x10035fb4  mov     [esp+178h+var_13C], edi
0x10035fb8  mov     eax, [edi+10h]
0x10035fbb  mov     [esp+178h+var_124], ecx
0x10035fbf  mov     [esp+178h+sesid], eax
0x10035fc3  mov     dword ptr [esp+178h+var_164], 0
0x10035fcb  mov     [esp+178h+var_158], esi
0x10035fcf  mov     [esp+178h+var_134], esi
0x10035fd3  mov     [esp+178h+var_144], esi
0x10035fd7  mov     [esp+178h+var_140], esi
0x10035fdb  mov     [esp+178h+String2], esi
0x10035fdf  mov     [esp+178h+tableid], 0FFFFFFFFh
0x10035fea  mov     [esp+178h+var_168], 0FFFFFFFFh
0x10035ff2  test    ebx, ebx
0x10035ff4  jz      loc_100360B3
0x10035ffa  test    ecx, ecx
0x10035ffc  jz      short loc_10036067
0x10035ffe  cmp     ebx, 4
0x10036001  ja      short loc_10036067
0x10036003  movzx   eax, word ptr [ecx]
0x10036006  test    ax, ax
0x10036009  jz      short loc_1003601A
0x1003600b  cmp     eax, 1
0x1003600e  jz      short loc_1003601A
0x10036010  cmp     eax, 8
0x10036013  jnz     short loc_10036067
0x10036015  cmp     [ecx+8], esi
0x10036018  jnz     short loc_10036067
0x1003601a  cmp     ebx, 1
0x1003601d  jbe     short loc_10036037
0x1003601f  movzx   eax, word ptr [ecx+10h]
0x10036023  test    ax, ax
0x10036026  jz      short loc_10036037
0x10036028  cmp     eax, 1
0x1003602b  jz      short loc_10036037
0x1003602d  cmp     eax, 8
0x10036030  jnz     short loc_10036067
0x10036032  cmp     [ecx+18h], esi
0x10036035  jnz     short loc_10036067
0x10036037  cmp     ebx, 2
0x1003603a  jbe     short loc_1003604F
0x1003603c  movzx   eax, word ptr [ecx+20h]
0x10036040  test    ax, ax
0x10036043  jz      short loc_1003604F
0x10036045  cmp     eax, 1
0x10036048  jz      short loc_1003604F
0x1003604a  cmp     eax, 8
0x1003604d  jnz     short loc_10036067
0x1003604f  cmp     ebx, 3
0x10036052  jbe     short loc_10036079
0x10036054  movzx   eax, word ptr [ecx+30h]
0x10036058  test    ax, ax
0x1003605b  jz      short loc_1003607B
0x1003605d  cmp     eax, 1
0x10036060  jz      short loc_1003607B
0x10036062  cmp     eax, 8
0x10036065  jz      short loc_1003607B
0x10036067  mov     ebx, edx
0x10036069  mov     edi, 80070057h
0x1003606e  mov     eax, [ebx+14h]
0x10036071  mov     ecx, [ebx+10h]
0x10036074  jmp     loc_100369EF
0x10036079  jb      short loc_100360B3
0x1003607b  movzx   eax, word ptr [ecx+20h]
0x1003607f  test    ax, ax
0x10036082  jz      short loc_10036098
0x10036084  cmp     eax, 1
0x10036087  jz      short loc_10036098
0x10036089  mov     eax, [ecx+28h]
0x1003608c  mov     [esp+178h+var_144], 1
0x10036094  mov     [esp+178h+String2], eax
0x10036098  cmp     ebx, 4
0x1003609b  jb      short loc_100360B3
0x1003609d  movzx   eax, word ptr [ecx+30h]
0x100360a1  test    ax, ax
0x100360a4  jz      short loc_100360E3
0x100360a6  cmp     eax, 1
0x100360a9  jz      short loc_100360E3
0x100360ab  mov     [esp+178h+var_140], 1
0x100360b3  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100360b9  push    70h ; 'p'
0x100360bb  push    ecx
0x100360bc  mov     eax, [ecx]
0x100360be  mov     esi, [eax+0Ch]
0x100360c1  mov     ecx, esi
0x100360c3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100360c9  call    esi
0x100360cb  mov     esi, eax
0x100360cd  mov     [esp+178h+var_160], esi
0x100360d1  test    esi, esi
0x100360d3  jnz     short loc_100360E9
0x100360d5  mov     edi, 8007000Eh
0x100360da  mov     ebx, [esp+178h+var_13C]
0x100360de  jmp     loc_100369B5
0x100360e3  mov     [esp+178h+var_140], esi
0x100360e7  jmp     short loc_100360B3
0x100360e9  push    0
0x100360eb  push    esi
0x100360ec  lea     eax, [esp+180h+var_168]
0x100360f0  mov     edx, edi
0x100360f2  push    eax
0x100360f3  xor     ecx, ecx
0x100360f5  call    SRSCreateTempTable
0x100360fa  mov     edi, eax
0x100360fc  test    edi, edi
0x100360fe  jnz     short loc_100360DA
0x10036100  mov     edx, [esp+178h+var_124]
0x10036104  lea     eax, [edi+1]
0x10036107  cmp     ebx, 3
0x1003610a  jb      short loc_10036112
0x1003610c  cmp     ax, [edx+20h]
0x10036110  jz      short loc_1003611D
0x10036112  cmp     ebx, 4
0x10036115  jb      short loc_1003611F
0x10036117  cmp     ax, [edx+30h]
0x1003611b  jnz     short loc_1003611F
0x1003611d  xor     eax, eax
0x1003611f  cmp     [esp+178h+var_140], 0
0x10036124  jz      short loc_10036139
0x10036126  mov     ecx, 8
0x1003612b  cmp     cx, [edx+30h]
0x1003612f  jnz     short loc_10036139
0x10036131  xor     ecx, ecx
0x10036133  cmp     [edx+38h], ecx
0x10036136  cmovz   eax, ecx
0x10036139  mov     ecx, [esp+178h+var_144]
0x1003613d  test    ecx, ecx
0x1003613f  jz      short loc_10036153
0x10036141  xor     esi, esi
0x10036143  cmp     [edx+28h], esi
0x10036146  cmovnz  esi, eax
0x10036149  cmp     ecx, 1
0x1003614c  jnz     short loc_10036155
0x1003614e  mov     eax, [edx+28h]
0x10036151  jmp     short loc_10036157
0x10036153  mov     esi, eax
0x10036155  xor     eax, eax
0x10036157  mov     ebx, [esp+178h+var_13C]
0x1003615b  lea     ecx, [esp+178h+var_F8]
0x10036162  push    1
0x10036164  push    30h ; '0'
0x10036166  push    ecx
0x10036167  push    eax
0x10036168  push    offset aTables_0; "tables"
0x1003616d  push    0
0x1003616f  push    dword ptr [ebx+14h]
0x10036172  push    [esp+194h+sesid]
0x10036176  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003617c  mov     dword ptr [esp+178h+var_164], eax
0x10036180  test    eax, eax
0x10036182  jnz     loc_100369AC
0x10036188  push    eax; grbit
0x10036189  push    80000000h; cRow
0x1003618e  push    [esp+180h+tableid]; tableid
0x10036195  push    [esp+184h+sesid]; sesid
0x10036199  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003619f  mov     dword ptr [esp+178h+var_164], eax
0x100361a3  cmp     eax, 0FFFFF9BDh
0x100361a8  jz      short loc_100361B2
0x100361aa  test    eax, eax
0x100361ac  jnz     loc_100369AC
0x100361b2  cmp     [esp+178h+var_F0], 0
0x100361ba  jbe     loc_100368DA
0x100361c0  mov     [esp+178h+var_158], 0
0x100361c8  mov     [esp+178h+var_130], 0
0x100361d0  test    esi, esi
0x100361d2  jz      loc_100368DA
0x100361d8  mov     esi, [esp+178h+sesid]
0x100361dc  push    0; pretinfo
0x100361de  push    0; grbit
0x100361e0  lea     eax, [esp+180h+pcbActual]
0x100361e4  push    eax; pcbActual
0x100361e5  push    4; cbData
0x100361e7  lea     eax, [esp+188h+pvData]
0x100361eb  push    eax; pvData
0x100361ec  push    [esp+18Ch+columnid]; columnid
0x100361f3  push    [esp+190h+tableid]; tableid
0x100361fa  push    esi; sesid
0x100361fb  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036201  mov     dword ptr [esp+178h+var_164], eax
0x10036205  test    eax, eax
0x10036207  jnz     loc_100369B1
0x1003620d  mov     eax, [esp+178h+pvData]
0x10036211  dec     eax; switch 6 cases
0x10036212  cmp     eax, 5
0x10036215  ja      def_10036222; jumptable 10036222 default case, cases 2,3
0x1003621b  movzx   eax, ds:byte_10036AA0[eax]
0x10036222  jmp     ds:jpt_10036222[eax*4]; switch jump
0x10036229  push    0; jumptable 10036222 cases 1,4-6
0x1003622b  push    0; grbit
0x1003622d  lea     eax, [esp+180h+pcbActual]
0x10036231  push    eax; pcbActual
0x10036232  push    81h; cbData
0x10036237  lea     eax, [esp+188h+String1]
0x1003623e  push    eax; pvData
0x1003623f  push    [esp+18Ch+var_E8]; columnid
0x10036246  push    [esp+190h+tableid]; tableid
0x1003624d  push    esi; sesid
0x1003624e  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036254  mov     dword ptr [esp+178h+var_164], eax
0x10036258  test    eax, eax
0x1003625a  jnz     loc_100369AC
0x10036260  mov     eax, [esp+178h+pcbActual]
0x10036264  and     eax, 0FFFFFFFEh
0x10036267  cmp     eax, 82h
0x1003626c  jnb     loc_10036A90
0x10036272  xor     ecx, ecx
0x10036274  cmp     [esp+178h+pvData], 5
0x10036279  mov     [esp+eax+178h+String1], cx
0x10036281  jnz     loc_1003632C
0x10036287  push    ecx; pretinfo
0x10036288  push    ecx; grbit
0x10036289  lea     eax, [esp+180h+var_FC]
0x10036290  mov     [esp+180h+var_C4], 0FFFFFFFFh
0x1003629b  push    eax; pcbActual
0x1003629c  push    4; cbData
0x1003629e  lea     eax, [esp+188h+var_110]
0x100362a2  push    eax; pvData
0x100362a3  push    [esp+18Ch+var_D4]; columnid
0x100362aa  push    [esp+190h+tableid]; tableid
0x100362b1  push    esi; sesid
0x100362b2  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100362b8  mov     dword ptr [esp+178h+var_164], eax
0x100362bc  test    eax, eax
0x100362be  jnz     loc_100369AC
0x100362c4  cmp     [esp+178h+pvData], 5
0x100362c9  jnz     short loc_100362D8
0x100362cb  movzx   eax, word ptr [esp+178h+var_110]
0x100362d0  test    eax, eax
0x100362d2  jnz     def_10036222; jumptable 10036222 default case, cases 2,3
0x100362d8  lea     eax, [esp+178h+var_114]
0x100362dc  push    eax
0x100362dd  push    38h ; '8'
0x100362df  lea     eax, [esp+180h+var_C8]
0x100362e6  push    eax
0x100362e7  lea     eax, [esp+184h+String1]
0x100362ee  push    eax
0x100362ef  push    dword ptr [ebx+14h]
0x100362f2  push    esi
0x100362f3  call    ds:__imp__JetGetQueryParameterInfo@24; JetGetQueryParameterInfo(x,x,x,x,x,x)
0x100362f9  mov     dword ptr [esp+178h+var_164], eax
0x100362fd  test    eax, eax
0x100362ff  jnz     def_10036222; jumptable 10036222 default case, cases 2,3
0x10036305  push    [esp+178h+var_C4]; tableid
0x1003630c  push    esi; sesid
0x1003630d  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10036313  mov     dword ptr [esp+178h+var_164], eax
0x10036317  test    eax, eax
0x10036319  jnz     loc_100369AC
0x1003631f  cmp     [esp+178h+var_C0], eax
0x10036326  jnz     def_10036222; jumptable 10036222 default case, cases 2,3
0x1003632c  mov     eax, [esp+178h+String2]
0x10036330  test    eax, eax
0x10036332  jz      short loc_1003634E
0x10036334  push    eax; String2
0x10036335  lea     eax, [esp+17Ch+String1]
0x1003633c  push    eax; String1
0x1003633d  call    ds:__imp___wcsicmp
0x10036343  add     esp, 8
0x10036346  test    eax, eax
0x10036348  jnz     def_10036222; jumptable 10036222 default case, cases 2,3
0x1003634e  mov     edi, [esp+178h+var_158]
0x10036352  test    edi, edi
0x10036354  jz      short loc_10036369
0x10036356  mov     eax, [edi]
0x10036358  push    1
0x1003635a  mov     esi, [eax+4]
0x1003635d  mov     ecx, esi
0x1003635f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10036365  mov     ecx, edi
0x10036367  call    esi
0x10036369  push    10h; Size
0x1003636b  call    ??2@YAPAXI@Z; operator new(uint)
0x10036370  mov     esi, eax
0x10036372  add     esp, 4
0x10036375  mov     [esp+178h+var_158], esi
0x10036379  mov     [esp+178h+var_120], esi
0x1003637d  test    esi, esi
0x1003637f  jz      loc_1003699D
0x10036385  push    1; int
0x10036387  lea     eax, [esp+17Ch+var_164]
0x1003638b  mov     dword ptr [esi], offset ??_7ColumnData@@6B@; const ColumnData::`vftable'
0x10036391  push    eax; int *
  ... truncated ...
```
