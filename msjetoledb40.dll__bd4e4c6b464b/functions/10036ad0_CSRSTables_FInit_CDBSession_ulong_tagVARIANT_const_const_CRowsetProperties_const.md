# CSRSTables::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x10036ad0`
- end: `0x100372bc`
- name: `?FInit@CSRSTables@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `2028`
- prototype: `int(CSRSTables *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d570`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035d90`
- `0x10035e60`
- `0x10036ad0`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc8d`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10036ca2`
- `msvcrt!_wcsicmp` at `0x10036cbb`
- `msvcrt!_wcsicmp` at `0x10036cd4`
- `msvcrt!_wcsicmp` at `0x10036ced`
- `msvcrt!_wcsicmp` at `0x10036d06`
- `msvcrt!_wcsicmp` at `0x10036d1b`
- `msvcrt!_wcsicmp` at `0x10036d30`
- `msvcrt!_wcsicmp` at `0x10036d45`
- `msvcrt!_wcsicmp` at `0x10036d5a`
- `msvcrt!_wcsicmp` at `0x10036d6f`
- `msvcrt!_wcsicmp` at `0x10036f15`
- `msvcrt!_wcsicmp` at `0x100370ef`
- `msvcrt!_wcsicmp` at `0x10036ca2`
- `msvcrt!_wcsicmp` at `0x10036cbb`
- `msvcrt!_wcsicmp` at `0x10036cd4`
- `msvcrt!_wcsicmp` at `0x10036ced`
- `msvcrt!_wcsicmp` at `0x10036d06`
- `msvcrt!_wcsicmp` at `0x10036d1b`
- `msvcrt!_wcsicmp` at `0x10036d30`
- `msvcrt!_wcsicmp` at `0x10036d45`
- `msvcrt!_wcsicmp` at `0x10036d5a`
- `msvcrt!_wcsicmp` at `0x10036d6f`
- `msvcrt!_wcsicmp` at `0x10036f15`
- `msvcrt!_wcsicmp` at `0x100370ef`
- `msjet40!__imp__JetCloseTable@8` at `0x10036f6a`
- `msjet40!__imp__JetCloseTable@8` at `0x10037285`
- `msjet40!__imp__JetCloseTable@8` at `0x10037298`
- `msjet40!__imp__JetCloseTable@8` at `0x10036f6a`
- `msjet40!__imp__JetCloseTable@8` at `0x10037285`
- `msjet40!__imp__JetCloseTable@8` at `0x10037298`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003724b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003724b`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10036d96`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10036d96`
- `msjet40!__imp__JetMove@16` at `0x10036dac`
- `msjet40!__imp__JetMove@16` at `0x10037137`
- `msjet40!__imp__JetMove@16` at `0x10036dac`
- `msjet40!__imp__JetMove@16` at `0x10037137`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10036f8e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10037107`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10036f8e`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10037107`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036def`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036e39`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036e7e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036ec6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036ef2`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036def`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036e39`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036e7e`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036ec6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10036ef2`
- `msjet40!__imp__JetSetColumn@28` at `0x1003701d`
- `msjet40!__imp__JetSetColumn@28` at `0x10037054`
- `msjet40!__imp__JetSetColumn@28` at `0x100370a0`
- `msjet40!__imp__JetSetColumn@28` at `0x100370c5`
- `msjet40!__imp__JetSetColumn@28` at `0x1003701d`
- `msjet40!__imp__JetSetColumn@28` at `0x10037054`
- `msjet40!__imp__JetSetColumn@28` at `0x100370a0`
- `msjet40!__imp__JetSetColumn@28` at `0x100370c5`
- `msjet40!__imp__JetUpdate@20` at `0x1003711a`
- `msjet40!__imp__JetUpdate@20` at `0x1003711a`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x10036f58`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x10036f58`

## string_xrefs

- `0x10036d52`: `ACCESS TABLE`
- `0x10036fc2`: `ACCESS TABLE`
- `0x10036d13`: `GLOBAL TEMPORARY`
- `0x10036d28`: `LOCAL TEMPORARY`

## pseudocode

```c
int __userpurge CSRSTables::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSTables *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_SESID v8; // ebx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // eax
  int v13; // edi
  JET_COLUMNID *v14; // esi
  int v15; // eax
  int v16; // ecx
  JET_COLUMNID *v17; // eax
  struct CDBSession *v18; // edi
  BOOL v19; // esi
  BOOL v20; // eax
  const wchar_t *v21; // ecx
  BOOL v22; // eax
  int v23; // esi
  _DWORD *v24; // edi
  wchar_t *v25; // esi
  JET_ERR v26; // eax
  wchar_t *v27; // ecx
  wchar_t *v28; // edx
  CSchemaRowset *v30; // ecx
  int v31; // eax
  JET_ERR v32; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v33; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v34; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v35; // esi
  _DWORD *v36; // eax
  int v37; // ecx
  unsigned int v39; // [esp-24h] [ebp-174h]
  wchar_t *v40; // [esp-10h] [ebp-160h]
  const struct _GUID *v41; // [esp+0h] [ebp-150h]
  const struct _GUID *v42; // [esp+4h] [ebp-14Ch]
  unsigned int QueryParameterInfo; // [esp+10h] [ebp-140h] BYREF
  JET_COLUMNID *v44; // [esp+14h] [ebp-13Ch]
  JET_TABLEID v45; // [esp+18h] [ebp-138h] BYREF
  _DWORD *v46; // [esp+1Ch] [ebp-134h]
  wchar_t *String1; // [esp+20h] [ebp-130h]
  int v48; // [esp+24h] [ebp-12Ch]
  unsigned int pcbActual; // [esp+28h] [ebp-128h] BYREF
  int v50; // [esp+2Ch] [ebp-124h]
  int pvData; // [esp+30h] [ebp-120h] BYREF
  struct CDBSession *v52; // [esp+34h] [ebp-11Ch]
  int v53; // [esp+38h] [ebp-118h] BYREF
  ColumnDataWithFakeNamesAndDBTYPES *v54; // [esp+3Ch] [ebp-114h] BYREF
  unsigned int v55; // [esp+40h] [ebp-110h]
  int v56; // [esp+44h] [ebp-10Ch]
  _BYTE v57[8]; // [esp+48h] [ebp-108h] BYREF
  _BYTE v58[8]; // [esp+50h] [ebp-100h] BYREF
  JET_TABLEID v59[12]; // [esp+58h] [ebp-F8h] BYREF
  JET_TABLEID v60[14]; // [esp+88h] [ebp-C8h] BYREF
  wchar_t String2[70]; // [esp+C0h] [ebp-90h] BYREF

  v55 = a5;
  v46 = a1;
  v56 = a2;
  v52 = a4;
  v45 = 0;
  v48 = 0;
  v50 = 0;
  QueryParameterInfo = 0;
  memset(v59, 0, sizeof(v59));
  v8 = a1[4];
  if ( (unsigned int)this <= 2 )
    goto LABEL_10;
  v9 = *((unsigned __int16 *)a4 + 16);
  if ( !(_WORD)v9 || (v48 = 1, v9 == 1) )
    v48 = 0;
  if ( (unsigned int)this > 3 )
  {
    v10 = *((unsigned __int16 *)a4 + 24);
    if ( !(_WORD)v10 || (v50 = 1, v10 == 1) )
      v50 = 0;
    if ( (unsigned int)this > 4 )
      goto LABEL_25;
LABEL_10:
    if ( !this )
      goto LABEL_16;
  }
  if ( !a4 || (v11 = *(unsigned __int16 *)a4, (_WORD)v11) && v11 != 1 && (v11 != 8 || *((_DWORD *)a4 + 2)) )
  {
LABEL_25:
    v13 = -2147024809;
    v14 = 0;
    v15 = v46[5];
    v16 = v46[4];
LABEL_109:
    if ( !JetGetDatabaseInfo(v16, v15, &v54, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v41, (int)v42);
    goto LABEL_111;
  }
LABEL_16:
  if ( (unsigned int)this > 1 )
  {
    v12 = *((unsigned __int16 *)a4 + 8);
    if ( (_WORD)v12 )
    {
      if ( v12 != 1 && (v12 != 8 || *((_DWORD *)a4 + 6)) )
        goto LABEL_25;
    }
  }
  if ( v48 && *((_WORD *)a4 + 16) != 8 || v50 && *((_WORD *)a4 + 24) != 8 )
    goto LABEL_25;
  v17 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          36);
  v14 = v17;
  v44 = v17;
  if ( !v17 )
  {
    v13 = -2147024882;
    goto LABEL_105;
  }
  v13 = SRSCreateTempTable(1, a1, &v45, v17, 0);
  if ( !v13 )
  {
    v18 = v52;
    v19 = ((unsigned int)this < 3 || *((_WORD *)v52 + 16) != 1) && ((unsigned int)this < 4 || *((_WORD *)v52 + 24) != 1);
    if ( v48 )
    {
      v20 = 0;
      if ( *((_DWORD *)v52 + 10) )
        v20 = v19;
      v19 = v20;
    }
    if ( v50 )
    {
      v21 = (const wchar_t *)*((_DWORD *)v52 + 14);
      v22 = 0;
      if ( v21 )
        v22 = v19;
      v19 = v22;
      if ( v21
        && __wcsicmp(v21, L"TABLE")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"SYSTEM TABLE")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"ALIAS")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"SYNONYM")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"VIEW")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"GLOBAL TEMPORARY")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"LOCAL TEMPORARY")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"PASS-THROUGH")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"ACCESS TABLE")
        && __wcsicmp(*((const wchar_t **)v18 + 14), L"LINK") )
      {
        v19 = 0;
      }
    }
    JetGetObjectInfo(v8, v46[5], 0, 0, 0, v59, 48, 1);
    QueryParameterInfo = JetMove(v8, v59[1], 0x80000000, 0);
    if ( !QueryParameterInfo && v19 )
    {
      while ( 1 )
      {
        v53 = 0;
        v23 = 1;
        QueryParameterInfo = JetRetrieveColumn(v8, v59[1], v59[5], &pvData, 4u, &pcbActual, 0, 0);
        if ( QueryParameterInfo )
        {
LABEL_97:
          v13 = -2147467259;
          goto LABEL_104;
        }
        switch ( pvData )
        {
          case 1:
          case 4:
          case 5:
          case 6:
            QueryParameterInfo = JetRetrieveColumn(v8, v59[1], v59[9], &v53, 4u, &pcbActual, 0, 0);
            if ( QueryParameterInfo )
              goto LABEL_97;
            if ( pvData == 5 && (_WORD)v53 )
              goto LABEL_67;
            QueryParameterInfo = JetRetrieveColumn(v8, v59[1], v59[4], String2, 0x82u, &pcbActual, 0, 0);
            if ( QueryParameterInfo )
              goto LABEL_97;
            if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
              __report_rangecheckfailure();
            *(wchar_t *)((char *)String2 + (pcbActual & 0xFFFFFFFE)) = 0;
            QueryParameterInfo = JetRetrieveColumn(v8, v59[1], v59[6], v57, 8u, &pcbActual, 0, 0);
            if ( QueryParameterInfo )
              goto LABEL_97;
            QueryParameterInfo = JetRetrieveColumn(v8, v59[1], v59[7], v58, 8u, &pcbActual, 0, 0);
            if ( QueryParameterInfo )
              goto LABEL_97;
            if ( v48 && __wcsicmp(*((const wchar_t **)v18 + 10), String2) )
              goto LABEL_67;
            break;
          default:
LABEL_67:
            v23 = 0;
            break;
        }
        if ( v23 )
        {
          v24 = v46;
          v25 = 0;
          String1 = 0;
          if ( pvData != 5
            || (QueryParameterInfo = JetGetQueryParameterInfo(v8, v46[5], String2, v60, 56, &v54),
                JetCloseTable(v8, v60[1]),
                !QueryParameterInfo)
            && !v60[2] )
          {
            QueryParameterInfo = JetPrepareUpdate(v8, v45, 0);
            if ( QueryParameterInfo )
              goto LABEL_97;
            switch ( pvData )
            {
              case 1:
                if ( v53 >= 0 )
                {
                  v25 = (wchar_t *)L"ACCESS TABLE";
                  if ( (v53 & 2) == 0 )
                    v25 = (wchar_t *)L"TABLE";
                }
                else
                {
                  v25 = (wchar_t *)L"SYSTEM TABLE";
                }
                goto LABEL_82;
              case 4:
                v25 = (wchar_t *)L"PASS-THROUGH";
                goto LABEL_82;
              case 5:
                v25 = (wchar_t *)L"VIEW";
                goto LABEL_82;
              case 6:
                v25 = (wchar_t *)L"LINK";
LABEL_82:
                String1 = v25;
                break;
              default:
                break;
            }
            v26 = JetSetColumn(v8, v45, v44[2], String2, 2 * wcslen(String2), 0, 0);
            v27 = v25;
            QueryParameterInfo = v26;
            v28 = v25 + 1;
            while ( *v27++ )
              ;
            v40 = v25;
            v14 = v44;
            QueryParameterInfo = JetSetColumn(v8, v45, v44[3], v40, 2 * (v27 - v28), 0, 0);
            v13 = CSchemaRowset::MapStringPropertyValueToColumn(
                    v30,
                    v8,
                    v24[5],
                    (const unsigned __int16 *)v30,
                    String2,
                    0,
                    L"Description",
                    v45,
                    v14[5],
                    (int *)&QueryParameterInfo);
            if ( v13 < 0 )
              goto LABEL_105;
            QueryParameterInfo = JetSetColumn(v8, v45, v14[7], v57, 8u, 0, 0);
            if ( (QueryParameterInfo & 0x80000000) != 0
              || (QueryParameterInfo = JetSetColumn(v8, v45, v14[8], v58, 8u, 0, 0),
                  (QueryParameterInfo & 0x80000000) != 0)
              || (!v50 || v50 == 1 && (v31 = __wcsicmp(String1, *((const wchar_t **)v52 + 14)), v14 = v44, !v31)
                ? (v32 = JetUpdate(v8, v45, 0, 0, 0))
                : (v32 = JetPrepareUpdate(v8, v45, 3u)),
                  (QueryParameterInfo = v32) != 0) )
            {
              v13 = -2147467259;
              goto LABEL_105;
            }
            if ( v48 )
              break;
          }
        }
        QueryParameterInfo = JetMove(v8, v59[1], 1, 0);
        if ( QueryParameterInfo )
          break;
        v18 = v52;
      }
    }
    QueryParameterInfo = 0;
    v33 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
    v54 = v33;
    if ( v33 && (v34 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v33), (v35 = v34) != 0) )
    {
      *((_DWORD *)v34 + 4) = dword_10007E30;
      v36 = v46;
      *((_DWORD *)v35 + 5) = &SRSTablesDefNames;
      *((_DWORD *)v35 + 7) = 0;
      v13 = ColumnData::FInit(v35, v8, v36[5], v45, (int *)&QueryParameterInfo, 0, (int)&SRSTablesDefNames);
      if ( v13 >= 0 )
      {
        v37 = v56;
        v39 = v55;
        *((_DWORD *)v35 + 1) = 9;
        v13 = CRowset::FInit(v37, 0, v46, 0, 0, 0, v45, v39, 1, 0, 0, v35, 1, 0, 0, &GUID_NULL);
      }
    }
    else
    {
      v13 = -2147024882;
    }
LABEL_104:
    v14 = v44;
  }
LABEL_105:
  if ( QueryParameterInfo )
  {
    CExtError::SendJetErrortoOLEAuto(QueryParameterInfo, (int)&IID_IDBSchemaRowset, (int)v41, v42);
    goto LABEL_111;
  }
  if ( v13 < 0 )
  {
    v15 = v46[5];
    v16 = v46[4];
    if ( v13 != -2147024882 )
      goto LABEL_109;
  }
LABEL_111:
  if ( v14 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v14);
  QueryParameterInfo = JetCloseTable(v8, v59[1]);
  if ( v13 < 0 )
    JetCloseTable(v8, v45);
  return v13;
}

```

## disassembly

```asm
0x10036ad0  mov     edi, edi
0x10036ad2  push    ebp
0x10036ad3  mov     ebp, esp
0x10036ad5  and     esp, 0FFFFFFF8h
0x10036ad8  sub     esp, 144h
0x10036ade  mov     eax, ___security_cookie
0x10036ae3  xor     eax, esp
0x10036ae5  mov     [esp+144h+var_4], eax
0x10036aec  mov     eax, [ebp+arg_8]
0x10036aef  push    ebx
0x10036af0  push    esi; int
0x10036af1  mov     esi, [ebp+arg_4]
0x10036af4  push    edi; struct _GUID *
0x10036af5  push    30h ; '0'; Size
0x10036af7  mov     [esp+154h+var_110], eax
0x10036afb  mov     edi, edx
0x10036afd  lea     eax, [esp+154h+var_F8]
0x10036b01  mov     [esp+154h+var_134], edi
0x10036b05  push    0; Val
0x10036b07  push    eax; void *
0x10036b08  mov     [esp+15Ch+var_10C], ecx
0x10036b0c  mov     [esp+15Ch+var_11C], esi
0x10036b10  mov     [esp+15Ch+var_138], 0
0x10036b18  mov     [esp+15Ch+var_12C], 0
0x10036b20  mov     [esp+15Ch+var_124], 0
0x10036b28  mov     [esp+15Ch+var_140], 0
0x10036b30  call    _memset
0x10036b35  mov     eax, [ebp+this]
0x10036b38  add     esp, 0Ch
0x10036b3b  mov     ebx, [edi+10h]
0x10036b3e  cmp     eax, 2
0x10036b41  jbe     short loc_10036B89
0x10036b43  movzx   ecx, word ptr [esi+20h]
0x10036b47  test    cx, cx
0x10036b4a  jz      short loc_10036B59
0x10036b4c  mov     [esp+150h+var_12C], 1
0x10036b54  cmp     ecx, 1
0x10036b57  jnz     short loc_10036B61
0x10036b59  mov     [esp+150h+var_12C], 0
0x10036b61  cmp     eax, 3
0x10036b64  jbe     short loc_10036B8D
0x10036b66  movzx   ecx, word ptr [esi+30h]
0x10036b6a  test    cx, cx
0x10036b6d  jz      short loc_10036B7C
0x10036b6f  mov     [esp+150h+var_124], 1
0x10036b77  cmp     ecx, 1
0x10036b7a  jnz     short loc_10036B84
0x10036b7c  mov     [esp+150h+var_124], 0
0x10036b84  cmp     eax, 4
0x10036b87  ja      short loc_10036BE3
0x10036b89  test    eax, eax
0x10036b8b  jz      short loc_10036BA9
0x10036b8d  test    esi, esi
0x10036b8f  jz      short loc_10036BE3
0x10036b91  movzx   ecx, word ptr [esi]
0x10036b94  test    cx, cx
0x10036b97  jz      short loc_10036BA9
0x10036b99  cmp     ecx, 1
0x10036b9c  jz      short loc_10036BA9
0x10036b9e  cmp     ecx, 8
0x10036ba1  jnz     short loc_10036BE3
0x10036ba3  cmp     dword ptr [esi+8], 0
0x10036ba7  jnz     short loc_10036BE3
0x10036ba9  cmp     eax, 1
0x10036bac  jbe     short loc_10036BC7
0x10036bae  movzx   eax, word ptr [esi+10h]
0x10036bb2  test    ax, ax
0x10036bb5  jz      short loc_10036BC7
0x10036bb7  cmp     eax, 1
0x10036bba  jz      short loc_10036BC7
0x10036bbc  cmp     eax, 8
0x10036bbf  jnz     short loc_10036BE3
0x10036bc1  cmp     dword ptr [esi+18h], 0
0x10036bc5  jnz     short loc_10036BE3
0x10036bc7  cmp     [esp+150h+var_12C], 0
0x10036bcc  jz      short loc_10036BD5
0x10036bce  cmp     word ptr [esi+20h], 8
0x10036bd3  jnz     short loc_10036BE3
0x10036bd5  cmp     [esp+150h+var_124], 0
0x10036bda  jz      short loc_10036BF9
0x10036bdc  cmp     word ptr [esi+30h], 8
0x10036be1  jz      short loc_10036BF9
0x10036be3  mov     ecx, [esp+150h+var_134]
0x10036be7  mov     edi, 80070057h
0x10036bec  xor     esi, esi
0x10036bee  mov     eax, [ecx+14h]
0x10036bf1  mov     ecx, [ecx+10h]
0x10036bf4  jmp     loc_10037240
0x10036bf9  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10036bff  push    24h ; '$'
0x10036c01  push    ecx
0x10036c02  mov     eax, [ecx]
0x10036c04  mov     esi, [eax+0Ch]
0x10036c07  mov     ecx, esi
0x10036c09  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10036c0f  call    esi
0x10036c11  mov     esi, eax
0x10036c13  mov     [esp+150h+var_13C], esi
0x10036c17  test    esi, esi
0x10036c19  jnz     short loc_10036C25
0x10036c1b  mov     edi, 8007000Eh
0x10036c20  jmp     loc_1003720A
0x10036c25  push    0
0x10036c27  push    esi
0x10036c28  lea     eax, [esp+158h+var_138]
0x10036c2c  mov     edx, edi
0x10036c2e  push    eax
0x10036c2f  mov     ecx, 1
0x10036c34  call    SRSCreateTempTable
0x10036c39  mov     edi, eax
0x10036c3b  test    edi, edi
0x10036c3d  jnz     loc_1003720A
0x10036c43  mov     eax, [ebp+this]
0x10036c46  mov     ecx, 1
0x10036c4b  mov     edi, [esp+150h+var_11C]
0x10036c4f  cmp     eax, 3
0x10036c52  jb      short loc_10036C5A
0x10036c54  cmp     cx, [edi+20h]
0x10036c58  jz      short loc_10036C65
0x10036c5a  cmp     eax, 4
0x10036c5d  jb      short loc_10036C69
0x10036c5f  cmp     cx, [edi+30h]
0x10036c63  jnz     short loc_10036C69
0x10036c65  xor     esi, esi
0x10036c67  jmp     short loc_10036C6E
0x10036c69  mov     esi, 1
0x10036c6e  cmp     [esp+150h+var_12C], 0
0x10036c73  jz      short loc_10036C7F
0x10036c75  xor     eax, eax
0x10036c77  cmp     [edi+28h], eax
0x10036c7a  cmovnz  eax, esi
0x10036c7d  mov     esi, eax
0x10036c7f  cmp     [esp+150h+var_124], 0
0x10036c84  jz      loc_10036D7F
0x10036c8a  mov     ecx, [edi+38h]
0x10036c8d  xor     eax, eax
0x10036c8f  test    ecx, ecx
0x10036c91  cmovnz  eax, esi
0x10036c94  mov     esi, eax
0x10036c96  jz      loc_10036D7F
0x10036c9c  push    offset aTable; "TABLE"
0x10036ca1  push    ecx; String1
0x10036ca2  call    ds:__imp___wcsicmp
0x10036ca8  add     esp, 8
0x10036cab  test    eax, eax
0x10036cad  jz      loc_10036D7F
0x10036cb3  push    offset aSystemTable; "SYSTEM TABLE"
0x10036cb8  push    dword ptr [edi+38h]; String1
0x10036cbb  call    ds:__imp___wcsicmp
0x10036cc1  add     esp, 8
0x10036cc4  test    eax, eax
0x10036cc6  jz      loc_10036D7F
0x10036ccc  push    offset aAlias; "ALIAS"
0x10036cd1  push    dword ptr [edi+38h]; String1
0x10036cd4  call    ds:__imp___wcsicmp
0x10036cda  add     esp, 8
0x10036cdd  test    eax, eax
0x10036cdf  jz      loc_10036D7F
0x10036ce5  push    offset aSynonym; "SYNONYM"
0x10036cea  push    dword ptr [edi+38h]; String1
0x10036ced  call    ds:__imp___wcsicmp
0x10036cf3  add     esp, 8
0x10036cf6  test    eax, eax
0x10036cf8  jz      loc_10036D7F
0x10036cfe  push    offset aView; "VIEW"
0x10036d03  push    dword ptr [edi+38h]; String1
0x10036d06  call    ds:__imp___wcsicmp
0x10036d0c  add     esp, 8
0x10036d0f  test    eax, eax
0x10036d11  jz      short loc_10036D7F
0x10036d13  push    offset aGlobalTemporar; "GLOBAL TEMPORARY"
0x10036d18  push    dword ptr [edi+38h]; String1
0x10036d1b  call    ds:__imp___wcsicmp
0x10036d21  add     esp, 8
0x10036d24  test    eax, eax
0x10036d26  jz      short loc_10036D7F
0x10036d28  push    offset aLocalTemporary; "LOCAL TEMPORARY"
0x10036d2d  push    dword ptr [edi+38h]; String1
0x10036d30  call    ds:__imp___wcsicmp
0x10036d36  add     esp, 8
0x10036d39  test    eax, eax
0x10036d3b  jz      short loc_10036D7F
0x10036d3d  push    offset aPassThrough; "PASS-THROUGH"
0x10036d42  push    dword ptr [edi+38h]; String1
0x10036d45  call    ds:__imp___wcsicmp
0x10036d4b  add     esp, 8
0x10036d4e  test    eax, eax
0x10036d50  jz      short loc_10036D7F
0x10036d52  push    offset aAccessTable; "ACCESS TABLE"
0x10036d57  push    dword ptr [edi+38h]; String1
0x10036d5a  call    ds:__imp___wcsicmp
0x10036d60  add     esp, 8
0x10036d63  test    eax, eax
0x10036d65  jz      short loc_10036D7F
0x10036d67  push    offset aLink; "LINK"
0x10036d6c  push    dword ptr [edi+38h]; String1
0x10036d6f  call    ds:__imp___wcsicmp
0x10036d75  xor     ecx, ecx
0x10036d77  add     esp, 8
0x10036d7a  test    eax, eax
0x10036d7c  cmovnz  esi, ecx
0x10036d7f  push    1
0x10036d81  push    30h ; '0'
0x10036d83  lea     eax, [esp+158h+var_F8]
0x10036d87  push    eax
0x10036d88  mov     eax, [esp+15Ch+var_134]
0x10036d8c  push    0
0x10036d8e  push    0
0x10036d90  push    0
0x10036d92  push    dword ptr [eax+14h]
0x10036d95  push    ebx
0x10036d96  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10036d9c  push    0; grbit
0x10036d9e  push    80000000h; cRow
0x10036da3  push    [esp+158h+tableid]; tableid
0x10036da7  mov     [esp+15Ch+var_140], eax
0x10036dab  push    ebx; sesid
0x10036dac  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10036db2  mov     [esp+150h+var_140], eax
0x10036db6  test    eax, eax
0x10036db8  jnz     loc_10037162
0x10036dbe  test    esi, esi
0x10036dc0  jz      loc_10037162
0x10036dc6  push    0; pretinfo
0x10036dc8  push    0; grbit
0x10036dca  lea     eax, [esp+158h+pcbActual]
0x10036dce  mov     [esp+158h+var_118], 0
0x10036dd6  push    eax; pcbActual
0x10036dd7  push    4; cbData
0x10036dd9  lea     eax, [esp+160h+pvData]
0x10036ddd  mov     esi, 1
0x10036de2  push    eax; pvData
0x10036de3  push    [esp+164h+columnid]; columnid
0x10036dea  push    [esp+168h+tableid]; tableid
0x10036dee  push    ebx; sesid
0x10036def  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036df5  mov     [esp+150h+var_140], eax
0x10036df9  test    eax, eax
0x10036dfb  jnz     loc_1003714E
0x10036e01  mov     eax, [esp+150h+pvData]
0x10036e05  dec     eax; switch 6 cases
0x10036e06  cmp     eax, 5
0x10036e09  ja      def_10036E16; jumptable 10036E16 default case, cases 2,3
0x10036e0f  movzx   eax, ds:byte_100372C4[eax]
0x10036e16  jmp     ds:jpt_10036E16[eax*4]; switch jump
0x10036e1d  push    0; jumptable 10036E16 cases 1,4-6
0x10036e1f  push    0; grbit
0x10036e21  lea     eax, [esp+158h+pcbActual]
0x10036e25  push    eax; pcbActual
0x10036e26  push    4; cbData
0x10036e28  lea     eax, [esp+160h+var_118]
0x10036e2c  push    eax; pvData
0x10036e2d  push    [esp+164h+var_D4]; columnid
0x10036e34  push    [esp+168h+tableid]; tableid
0x10036e38  push    ebx; sesid
0x10036e39  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036e3f  mov     [esp+150h+var_140], eax
0x10036e43  test    eax, eax
0x10036e45  jnz     loc_1003714E
0x10036e4b  cmp     [esp+150h+pvData], 5
0x10036e50  jnz     short loc_10036E5F
0x10036e52  movzx   eax, word ptr [esp+150h+var_118]
0x10036e57  test    eax, eax
0x10036e59  jnz     def_10036E16; jumptable 10036E16 default case, cases 2,3
0x10036e5f  push    0; pretinfo
0x10036e61  push    0; grbit
0x10036e63  lea     eax, [esp+158h+pcbActual]
0x10036e67  push    eax; pcbActual
0x10036e68  push    82h; cbData
0x10036e6d  lea     eax, [esp+160h+String2]
0x10036e74  push    eax; pvData
0x10036e75  push    [esp+164h+var_E8]; columnid
0x10036e79  push    [esp+168h+tableid]; tableid
0x10036e7d  push    ebx; sesid
0x10036e7e  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036e84  mov     [esp+150h+var_140], eax
0x10036e88  test    eax, eax
0x10036e8a  jnz     loc_1003714E
0x10036e90  mov     eax, [esp+150h+pcbActual]
0x10036e94  and     eax, 0FFFFFFFEh
0x10036e97  cmp     eax, 82h
0x10036e9c  jnb     loc_100372B7
0x10036ea2  xor     ecx, ecx
0x10036ea4  push    ecx; pretinfo
0x10036ea5  push    ecx; grbit
0x10036ea6  mov     [esp+eax+158h+String2], cx
0x10036eae  lea     eax, [esp+158h+pcbActual]
0x10036eb2  push    eax; pcbActual
0x10036eb3  push    8; cbData
0x10036eb5  lea     eax, [esp+160h+var_108]
0x10036eb9  push    eax; pvData
0x10036eba  push    [esp+164h+var_E0]; columnid
0x10036ec1  push    [esp+168h+tableid]; tableid
0x10036ec5  push    ebx; sesid
0x10036ec6  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10036ecc  mov     [esp+150h+var_140], eax
0x10036ed0  test    eax, eax
0x10036ed2  jnz     loc_1003714E
0x10036ed8  push    eax; pretinfo
0x10036ed9  push    eax; grbit
  ... truncated ...
```
