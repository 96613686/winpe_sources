# CDBProperties::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180074850`
- end: `0x180075612`
- name: `?GetProperties@CDBProperties@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `3522`
- prototype: `int(CDBProperties *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180011b00`
- `0x180012250`
- `0x1800130d0`
- `0x180013394`
- `0x180013870`
- `0x180022bf8`
- `0x180028e3c`
- `0x180029560`
- `0x18002a93c`
- `0x18002b8ac`
- `0x18002c060`
- `0x18002ec0c`
- `0x180074850`
- `0x180076e50`
- `0x1800771ac`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800751be`
- `OLEAUT32!__imp_VariantInit` at `0x1800754b8`
- `OLEAUT32!__imp_VariantInit` at `0x1800751be`
- `OLEAUT32!__imp_VariantInit` at `0x1800754b8`
- `ole32!CoTaskMemAlloc` at `0x180074fbb`
- `ole32!CoTaskMemAlloc` at `0x1800750f4`
- `ole32!CoTaskMemAlloc` at `0x1800753de`
- `ole32!CoTaskMemAlloc` at `0x180074fbb`
- `ole32!CoTaskMemAlloc` at `0x1800750f4`
- `ole32!CoTaskMemAlloc` at `0x1800753de`
- `ole32!CoTaskMemFree` at `0x180074b80`
- `ole32!CoTaskMemFree` at `0x180074b8b`
- `ole32!CoTaskMemFree` at `0x180074b80`
- `ole32!CoTaskMemFree` at `0x180074b8b`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CDBProperties::GetProperties(
        CDBProperties *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  const struct tagDBPROPIDSET *v6; // r15
  unsigned int v7; // r12d
  int v9; // r14d
  const struct tagDBPROPIDSET *v11; // rax
  unsigned int i; // edx
  __int64 v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 Provider; // rbx
  unsigned int v20; // edi
  __int64 v21; // rdi
  CDPO *CDPO; // rax
  char v23; // r10
  const struct tagDBPROPIDSET *v24; // rdx
  unsigned int j; // r11d
  __int64 v26; // rcx
  DBPROPID *v27; // rcx
  ULONG m; // r9d
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // r14
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  int v36; // ebx
  struct tagDBPROPSET *v37; // rax
  int v38; // ebx
  struct tagDBPROPSET *v39; // rbx
  unsigned int v40; // eax
  DBPROPID *rgPropertyIDs; // r12
  GUID *p_guidPropertySet; // rsi
  int v43; // ebx
  DBPROP *v44; // rcx
  int v45; // ebx
  struct tagDBPROP *rgProperties; // r14
  unsigned int v47; // eax
  int v48; // r13d
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // r9d
  int v53; // ebx
  __int64 v54; // rax
  __int64 v55; // rax
  struct tagDBPROPSET *v56; // rsi
  DBPROP *v57; // rcx
  int v58; // ebx
  const struct tagDBPROP *v59; // r14
  struct tagDBPROP *v60; // r13
  ULONG k; // r12d
  __int64 v62; // rax
  unsigned int v63; // ebx
  int v64; // ebx
  bool Property; // [rsp+30h] [rbp-198h]
  unsigned int v67; // [rsp+38h] [rbp-190h] BYREF
  int v68; // [rsp+3Ch] [rbp-18Ch]
  int v69; // [rsp+40h] [rbp-188h]
  struct tagDBPROPSET *v70; // [rsp+48h] [rbp-180h] BYREF
  struct tagDBPROPSET *v71; // [rsp+50h] [rbp-178h] BYREF
  unsigned int v72; // [rsp+58h] [rbp-170h]
  LPVOID pv; // [rsp+60h] [rbp-168h] BYREF
  int v74; // [rsp+68h] [rbp-160h] BYREF
  int v75; // [rsp+6Ch] [rbp-15Ch] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-158h] BYREF
  int v77; // [rsp+74h] [rbp-154h] BYREF
  int v78; // [rsp+78h] [rbp-150h] BYREF
  int v79; // [rsp+7Ch] [rbp-14Ch] BYREF
  int v80; // [rsp+80h] [rbp-148h] BYREF
  int v81; // [rsp+84h] [rbp-144h] BYREF
  int v82; // [rsp+88h] [rbp-140h] BYREF
  int v83; // [rsp+8Ch] [rbp-13Ch] BYREF
  int v84; // [rsp+90h] [rbp-138h] BYREF
  int v85; // [rsp+94h] [rbp-134h] BYREF
  int v86; // [rsp+98h] [rbp-130h] BYREF
  struct tagDBPROPSET *v87; // [rsp+A0h] [rbp-128h]
  struct tagDBPROPSET **v88; // [rsp+A8h] [rbp-120h]
  unsigned int *v89; // [rsp+B0h] [rbp-118h]
  struct tagDBPROP v90; // [rsp+C0h] [rbp-108h] BYREF
  struct tagDBPROP v91; // [rsp+110h] [rbp-B8h] BYREF
  int *v92; // [rsp+160h] [rbp-68h] BYREF
  int v93; // [rsp+168h] [rbp-60h]
  struct _GUID v94; // [rsp+16Ch] [rbp-5Ch] BYREF

  v6 = a3;
  v7 = a2;
  v89 = a4;
  v88 = a5;
  v9 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a4 || !a5 )
    return 2147942487LL;
  if ( a2 && !a3 )
    return 2147942487LL;
  v11 = a3;
  for ( i = 0; ; ++i )
  {
    if ( i >= v7 )
    {
      if ( v7 == 1 && a3 )
      {
        v16 = *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1;
        v17 = *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1 - *(_QWORD *)&v6->guidPropertySet.Data1;
        v18 = *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4;
        if ( *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1 == *(_QWORD *)&v6->guidPropertySet.Data1 )
          v17 = *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4 - *(_QWORD *)v6->guidPropertySet.Data4;
        if ( !v17 && v6->cPropertyIDs == 1 && v6->rgPropertyIDs && *v6->rgPropertyIDs == 109 )
        {
          Provider = GetProviderPointer<CDCM>(*((_QWORD *)this + 7), &IID_IDBProperties);
          v20 = (*(__int64 (__fastcall **)(__int64, __int64, const struct tagDBPROPIDSET *, unsigned int *, struct tagDBPROPSET **))(*(_QWORD *)Provider + 24LL))(
                  Provider,
                  1,
                  v6,
                  a4,
                  a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)Provider + 16LL))(Provider);
          return v20;
        }
      }
      else
      {
        v18 = *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4;
        v16 = *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1;
      }
      v21 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(v21 + 616) )
      {
        CDPO = CDCM::GetCDPO(*((CDCM **)this + 7));
        if ( CDPO && (CDPO::GetOLEDBServices(CDPO) & 8) == 0 )
          *(_BYTE *)(v21 + 616) = 0;
        v16 = *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1;
        v18 = *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4;
      }
      if ( !*(_BYTE *)(v21 + 817) || !*(_BYTE *)(v21 + 616) )
      {
        memset_0(&v90, 0, sizeof(v90));
        v90.dwPropertyID = 248;
        Property = CDBPROPContainer::GetProperty((CDBPROPContainer *)(v21 + 520), &DBPROPSET_DBINIT, &v90);
        *(_BYTE *)(v21 + 616) = 0;
        CDBPROPContainer::ClearAllProperties((CDBPROPContainer *)(v21 + 520));
        v31 = GetProviderPointer<CDCM>(*((_QWORD *)this + 7), &IID_IDBProperties);
        v67 = 0;
        v70 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, struct tagDBPROPSET **))(*(_QWORD *)v31 + 24LL))(
                v31,
                0,
                0,
                &v67,
                &v70);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v32 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v32, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x34Eu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v32, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x34Eu);
              if ( (bidGblFlags & 2) != 0 )
                v32 = bidTraceHR(
                        off_1800C84E0[0],
                        866313,
                        L"<CDBProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v32);
            }
          }
          pExceptionObject = v32;
          throw (long *)&pExceptionObject;
        }
        v33 = CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v21 + 520), v67, v70, 1, 1);
        if ( v33 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v33, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x353u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v33, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x353u);
              if ( (bidGblFlags & 2) != 0 )
                v33 = bidTraceHR(
                        off_1800C84E0[0],
                        871433,
                        L"<CDBProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v33);
            }
          }
          v77 = v33;
          throw (long *)&v77;
        }
        v34 = CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v21 + 624), v67, v70, 0, 1);
        if ( v34 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v34, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x359u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v34, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x359u);
              if ( (bidGblFlags & 2) != 0 )
                v34 = bidTraceHR(
                        off_1800C84E0[0],
                        877577,
                        L"<CDBProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v34);
            }
          }
          v78 = v34;
          throw (long *)&v78;
        }
        FreePropSets(v67, v70);
        v67 = CSupportedPropDispenser::sm_AllSupportedInitPropSets;
        v70 = off_1800BD2C8;
        v35 = CDBPROPContainer::AddNewPropSets(
                (CDBPROPContainer *)(v21 + 520),
                CSupportedPropDispenser::sm_AllSupportedInitPropSets,
                off_1800BD2C8,
                0,
                1);
        if ( v35 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v35, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x35Eu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v35, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x35Eu);
              if ( (bidGblFlags & 2) != 0 )
                v35 = bidTraceHR(
                        off_1800C84E0[0],
                        882697,
                        L"<CDBProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v35);
            }
          }
          v79 = v35;
          throw (long *)&v79;
        }
        v36 = CDBPROPContainer::AddNewPropSets((CDBPROPContainer *)(v21 + 624), v67, v70, 0, 1);
        v9 = 0;
        if ( v36 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v36, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x35Fu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v36, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x35Fu);
              if ( (bidGblFlags & 2) != 0 )
                v36 = bidTraceHR(
                        off_1800C84E0[0],
                        883721,
                        L"<CDBProperties::GetProperties|Trace|HR> ",
                        (unsigned int)v36);
            }
          }
          v80 = v36;
          throw (long *)&v80;
        }
        if ( *(_BYTE *)(v21 + 817) )
          *(_BYTE *)(v21 + 616) = 1;
        if ( Property )
          CDBPROPContainer::SetProperty((CDBPROPContainer *)(v21 + 520), &DBPROPSET_DBINIT, &v90, 0, 0);
        v7 = a2;
        goto LABEL_94;
      }
      if ( !v7 )
        goto LABEL_55;
      v23 = 0;
      v24 = v6;
      for ( j = 0; ; ++j )
      {
        if ( j >= v7 )
          goto LABEL_54;
        v26 = *(_QWORD *)&v24->guidPropertySet.Data1 - v16;
        if ( !v26 )
          v26 = *(_QWORD *)v24->guidPropertySet.Data4 - v18;
        if ( !v26 )
        {
          if ( !v24->cPropertyIDs )
          {
            v23 = 1;
LABEL_54:
            if ( v23 )
            {
LABEL_55:
              v74 = 244;
              v92 = &v74;
              v93 = 1;
              *(_QWORD *)&v94.Data1 = v16;
              *(_QWORD *)v94.Data4 = v18;
              pv = 0;
              v75 = 1;
              v29 = GetProviderPointer<CDCM>(*((_QWORD *)this + 7), &IID_IDBProperties);
              v30 = v29;
              if ( v29 )
              {
                if ( (*(int (__fastcall **)(__int64, __int64, int **, int *, LPVOID *))(*(_QWORD *)v29 + 24LL))(
                       v29,
                       1,
                       &v92,
                       &v75,
                       &pv) >= 0 )
                {
                  CDBPROPContainer::SetProperty((CDBPROPContainer *)(v21 + 520), &v94, *(struct tagDBPROP **)pv, 1, 0);
                  CoTaskMemFree(*(LPVOID *)pv);
                  CoTaskMemFree(pv);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
            }
LABEL_94:
            if ( !v7 )
              return CreateIMallocCopyOfProps(*(_DWORD *)(v21 + 584), *(struct tagDBPROPSET **)(v21 + 576), a4, a5, 1);
            v37 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * v7);
            *a5 = v37;
            if ( !v37 )
            {
              v38 = -2147024882;
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(-2147024882, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x3FAu);
                if ( (bidGblFlags & 2) != 0 )
                  v38 = bidTraceHR(off_1800C84E0[0], 1042441, L"<CDBProperties::GetProperties|Trace|HR> ", 2147942414LL);
              }
              v81 = v38;
              throw (long *)&v81;
            }
            v68 = 0;
            v69 = 0;
            *a4 = v7;
            memset_0(*a5, 0, 32LL * v7);
            v39 = *a5;
            v40 = 0;
            while ( 2 )
            {
              v72 = v40;
              v87 = v39;
              if ( v40 >= v7 )
              {
                if ( v69 )
                  return v9 != 0 ? 265946 : -2147217887;
                else
                  return 0;
              }
              rgPropertyIDs = v6->rgPropertyIDs;
              p_guidPropertySet = &v6->guidPropertySet;
              v39->guidPropertySet = v6->guidPropertySet;
              if ( v6->cPropertyIDs )
              {
                if ( !rgPropertyIDs )
                {
                  v43 = -2147024809;
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(-2147024809, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x40Bu);
                    if ( (bidGblFlags & 2) != 0 )
                      v43 = bidTraceHR(
                              off_1800C84E0[0],
                              1059849,
                              L"<CDBProperties::GetProperties|Trace|HR> ",
                              2147942487LL);
                  }
                  v82 = v43;
                  throw (long *)&v82;
                }
                v44 = (DBPROP *)CoTaskMemAlloc(72LL * v6->cPropertyIDs);
                v39->rgProperties = v44;
                if ( !v44 )
                {
                  v45 = -2147024882;
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(-2147024882, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x411u);
                    if ( (bidGblFlags & 2) != 0 )
                      v45 = bidTraceHR(
                              off_1800C84E0[0],
                              1065993,
                              L"<CDBProperties::GetProperties|Trace|HR> ",
                              2147942414LL);
                  }
                  v83 = v45;
                  throw (long *)&v83;
                }
                memset_0(v44, 0, 72LL * v6->cPropertyIDs);
                v39->cProperties = v6->cPropertyIDs;
                rgProperties = v39->rgProperties;
                v47 = 0;
                v48 = v68;
                while ( 1 )
                {
                  LODWORD(v71) = v47;
                  if ( v47 >= v6->cPropertyIDs )
                    break;
                  memset_0(&v91, 0, sizeof(v91));
                  v91.dwPropertyID = *rgPropertyIDs;
                  VariantInit(&rgProperties->vValue);
                  if ( !CDBPROPContainer::GetProperty((CDBPROPContainer *)(v21 + 520), &v6->guidPropertySet, &v91) )
                    goto LABEL_139;
                  if ( !*(_BYTE *)(v21 + 818) || *(_BYTE *)(v21 + 817) )
                    goto LABEL_125;
                  v49 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DATASOURCE.Data1;
                  if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DATASOURCE.Data1 )
                    v49 = *(_QWORD *)v6->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCE.Data4;
                  if ( !v49 )
                    goto LABEL_139;
                  v50 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1;
                  if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1 )
                    v50 = *(_QWORD *)v6->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4;
                  if ( v50 )
                  {
LABEL_125:
                    v51 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
                    if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DBINIT.Data1 )
                      v51 = *(_QWORD *)v6->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
                    if ( !v51 && (*rgPropertyIDs == 9 || *rgPropertyIDs == 160) )
                      v52 = 2;
                    else
                      v52 = 0;
                    v53 = CopyProperty(rgProperties, &v91, 1, v52);
                    if ( v53 < 0 )
                    {
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        OLEDBTraceErr(v53, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x434u);
                        if ( (bidGblFlags & 2) != 0 )
                        {
                          OLEDBTraceErr(v53, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x434u);
                          if ( (bidGblFlags & 2) != 0 )
                            v53 = bidTraceHR(
                                    off_1800C84E0[0],
                                    1101833,
                                    L"<CDBProperties::GetProperties|Trace|HR> ",
                                    (unsigned int)v53);
                        }
                      }
                      v84 = v53;
                      throw (long *)&v84;
                    }
                    v68 = ++v48;
                  }
                  else
                  {
LABEL_139:
                    rgProperties->dwStatus = 1;
                    rgProperties->dwOptions = 0;
                    rgProperties->colid = DB_NULLID;
                    rgProperties->dwPropertyID = *rgPropertyIDs;
                    ++v69;
                  }
                  v47 = (_DWORD)v71 + 1;
                  ++rgPropertyIDs;
                  ++rgProperties;
                }
                v9 = v68;
                goto LABEL_174;
              }
              v71 = *(struct tagDBPROPSET **)(v21 + 576);
              if ( FindPropSet(&v6->guidPropertySet, *(_DWORD *)(v21 + 584), v71, &v71) == -1 )
                goto LABEL_172;
              if ( !*(_BYTE *)(v21 + 818) || *(_BYTE *)(v21 + 817) )
                goto LABEL_150;
              v54 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DATASOURCE.Data1;
              if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DATASOURCE.Data1 )
                v54 = *(_QWORD *)v6->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCE.Data4;
              if ( !v54 )
                goto LABEL_172;
              v55 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1;
              if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DATASOURCEINFO.Data1 )
                v55 = *(_QWORD *)v6->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCEINFO.Data4;
              if ( v55 )
              {
LABEL_150:
                v56 = v71;
                v57 = (DBPROP *)CoTaskMemAlloc(72LL * v71->cProperties);
                v39->rgProperties = v57;
                if ( !v57 )
                {
                  v58 = -2147024882;
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(-2147024882, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x449u);
                    if ( (bidGblFlags & 2) != 0 )
                      v58 = bidTraceHR(
                              off_1800C84E0[0],
                              1123337,
                              L"<CDBProperties::GetProperties|Trace|HR> ",
                              2147942414LL);
                  }
                  v85 = v58;
                  throw (long *)&v85;
                }
                memset_0(v57, 0, 72LL * v56->cProperties);
                v39->cProperties = v56->cProperties;
                v59 = v56->rgProperties;
                v60 = v39->rgProperties;
                for ( k = 0; k < v56->cProperties; ++k )
                {
                  v62 = *(_QWORD *)&v56->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
                  if ( !v62 )
                    v62 = *(_QWORD *)v56->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
                  if ( !v62 && (v59->dwPropertyID == 9 || v59->dwPropertyID == 160) )
                    v63 = 2;
                  else
                    v63 = 0;
                  VariantInit(&v60->vValue);
                  v64 = CopyProperty(v60, v59, 1, v63);
                  if ( v64 < 0 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      OLEDBTraceErr(v64, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x457u);
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        OLEDBTraceErr(v64, L"<CDBProperties::GetProperties|OLEDB|ERR> ", 0x457u);
                        if ( (bidGblFlags & 2) != 0 )
                          v64 = bidTraceHR(
                                  off_1800C84E0[0],
                                  1137673,
                                  L"<CDBProperties::GetProperties|Trace|HR> ",
                                  (unsigned int)v64);
                      }
                    }
                    v86 = v64;
                    throw (long *)&v86;
                  }
                  ++v59;
                  ++v60;
                }
                v9 = ++v68;
LABEL_174:
                v39 = v87;
              }
              else
              {
LABEL_172:
                ++v69;
              }
              v40 = v72 + 1;
              ++v6;
              ++v39;
              v7 = a2;
              continue;
            }
          }
          v27 = v24->rgPropertyIDs;
          if ( v24->rgPropertyIDs )
          {
            for ( m = 0; m < v24->cPropertyIDs; ++m )
            {
              if ( *v27 == 244 )
              {
                v23 = 1;
                break;
              }
              ++v27;
            }
          }
        }
        ++v24;
      }
    }
    v13 = *(_QWORD *)&v11->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_PROPERTIESINERROR.Data1;
    if ( !v13 )
      v13 = *(_QWORD *)v11->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_PROPERTIESINERROR.Data4;
    if ( !v13 )
      break;
    ++v11;
  }
  if ( v7 > 1 || v11->cPropertyIDs || v11->rgPropertyIDs )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v14 = GetProviderPointer<CDCM>(*((_QWORD *)this + 7), &IID_IDBProperties);
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct tagDBPROPIDSET *, unsigned int *, struct tagDBPROPSET **))(*(_QWORD *)v14 + 24LL))(
            v14,
            v7,
            v6,
            a4,
            a5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return v15;
}

```

## disassembly

```asm
0x180074850  push    rbx
0x180074852  push    rsi
0x180074853  push    rdi
0x180074854  push    r12
0x180074856  push    r13
0x180074858  push    r14
0x18007485a  push    r15
0x18007485c  sub     rsp, 190h
0x180074863  mov     rax, cs:__security_cookie
0x18007486a  xor     rax, rsp
0x18007486d  mov     [rsp+1C8h+var_48], rax
0x180074875  mov     r13, r9
0x180074878  mov     r15, r8
0x18007487b  mov     r12d, edx
0x18007487e  mov     [rsp+1C8h+var_194], edx
0x180074882  mov     rbx, rcx
0x180074885  mov     [rsp+1C8h+var_118], r9
0x18007488d  mov     rsi, [rsp+1C8h+arg_20]
0x180074895  mov     [rsp+1C8h+var_120], rsi
0x18007489d  xor     r14d, r14d
0x1800748a0  test    r9, r9
0x1800748a3  jz      short loc_1800748A8
0x1800748a5  mov     [r9], r14d
0x1800748a8  test    rsi, rsi
0x1800748ab  jz      short loc_1800748B0
0x1800748ad  mov     [rsi], r14
0x1800748b0  test    r13, r13
0x1800748b3  jz      loc_1800755B9
0x1800748b9  test    rsi, rsi
0x1800748bc  jz      loc_1800755B9
0x1800748c2  test    r12d, r12d
0x1800748c5  jz      short loc_1800748D6
0x1800748c7  test    r15, r15
0x1800748ca  jnz     short loc_1800748D6
0x1800748cc  mov     eax, 80070057h
0x1800748d1  jmp     loc_1800755EE
0x1800748d6  mov     rax, r15
0x1800748d9  mov     edx, r14d
0x1800748dc  cmp     edx, r12d
0x1800748df  jnb     loc_18007496D
0x1800748e5  mov     rcx, [rax+0Ch]
0x1800748e9  sub     rcx, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x1800748f0  jnz     short loc_1800748FD
0x1800748f2  mov     rcx, [rax+14h]
0x1800748f6  sub     rcx, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data4
0x1800748fd  test    rcx, rcx
0x180074900  jnz     short loc_180074962
0x180074902  cmp     r12d, 1
0x180074906  ja      short loc_180074956
0x180074908  cmp     [rax+8], r14d
0x18007490c  jnz     short loc_180074956
0x18007490e  cmp     [rax], r14
0x180074911  jnz     short loc_180074956
0x180074913  lea     rdx, IID_IDBProperties
0x18007491a  mov     rcx, [rbx+38h]
0x18007491e  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x180074923  mov     rdi, rax
0x180074926  mov     rcx, [rax]
0x180074929  mov     rax, [rcx+18h]
0x18007492d  mov     qword ptr [rsp+1C8h+var_1A8], rsi
0x180074932  mov     r9, r13
0x180074935  mov     r8, r15
0x180074938  mov     edx, r12d
0x18007493b  mov     rcx, rdi
0x18007493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074943  mov     ebx, eax
0x180074945  mov     rax, [rdi]
0x180074948  mov     rcx, rdi
0x18007494b  mov     rax, [rax+10h]
0x18007494f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074954  jmp     short loc_18007495B
0x180074956  mov     ebx, 80070057h
0x18007495b  mov     eax, ebx
0x18007495d  jmp     loc_1800755EE
0x180074962  inc     edx
0x180074964  add     rax, 20h ; ' '
0x180074968  jmp     loc_1800748DC
0x18007496d  cmp     r12d, 1
0x180074971  jnz     loc_180074A01
0x180074977  test    r15, r15
0x18007497a  jz      loc_180074A01
0x180074980  mov     r8, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x180074987  mov     rcx, r8
0x18007498a  sub     rcx, [r15+0Ch]
0x18007498e  mov     rax, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data4
0x180074995  jnz     short loc_18007499E
0x180074997  mov     rcx, rax
0x18007499a  sub     rcx, [r15+14h]
0x18007499e  test    rcx, rcx
0x1800749a1  jnz     short loc_180074A0F
0x1800749a3  cmp     dword ptr [r15+8], 1
0x1800749a8  jnz     short loc_180074A0F
0x1800749aa  mov     rcx, [r15]
0x1800749ad  test    rcx, rcx
0x1800749b0  jz      short loc_180074A0F
0x1800749b2  cmp     dword ptr [rcx], 6Dh ; 'm'
0x1800749b5  jnz     short loc_180074A0F
0x1800749b7  lea     rdx, IID_IDBProperties
0x1800749be  mov     rcx, [rbx+38h]
0x1800749c2  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x1800749c7  mov     rbx, rax
0x1800749ca  mov     rcx, [rax]
0x1800749cd  mov     rax, [rcx+18h]
0x1800749d1  mov     qword ptr [rsp+1C8h+var_1A8], rsi
0x1800749d6  mov     r9, r13
0x1800749d9  mov     r8, r15
0x1800749dc  mov     edx, 1
0x1800749e1  mov     rcx, rbx
0x1800749e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749e9  mov     edi, eax
0x1800749eb  mov     rcx, [rbx]
0x1800749ee  mov     rax, [rcx+10h]
0x1800749f2  mov     rcx, rbx
0x1800749f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800749fa  mov     eax, edi
0x1800749fc  jmp     loc_1800755EE
0x180074a01  mov     rax, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data4
0x180074a08  mov     r8, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x180074a0f  mov     rdi, [rbx+38h]
0x180074a13  cmp     [rdi+268h], r14b
0x180074a1a  jz      short loc_180074A4A
0x180074a1c  mov     rcx, rdi; this
0x180074a1f  call    ?GetCDPO@CDCM@@QEAAPEAVCDPO@@XZ; CDCM::GetCDPO(void)
0x180074a24  test    rax, rax
0x180074a27  jz      short loc_180074A3C
0x180074a29  mov     rcx, rax; this
0x180074a2c  call    ?GetOLEDBServices@CDPO@@QEAAKXZ; CDPO::GetOLEDBServices(void)
0x180074a31  test    al, 8
0x180074a33  jnz     short loc_180074A3C
0x180074a35  mov     [rdi+268h], r14b
0x180074a3c  mov     r8, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x180074a43  mov     rax, qword ptr cs:DBPROPSET_DATASOURCEINFO.Data4
0x180074a4a  cmp     [rdi+331h], r14b
0x180074a51  jz      loc_180074BA5
0x180074a57  cmp     [rdi+268h], r14b
0x180074a5e  jz      loc_180074BA5
0x180074a64  test    r12d, r12d
0x180074a67  jz      short loc_180074ACC
0x180074a69  mov     r10b, r14b
0x180074a6c  mov     rdx, r15
0x180074a6f  mov     r11d, r14d
0x180074a72  cmp     r11d, r12d
0x180074a75  jnb     short loc_180074AC3
0x180074a77  mov     rcx, [rdx+0Ch]
0x180074a7b  sub     rcx, r8
0x180074a7e  jnz     short loc_180074A87
0x180074a80  mov     rcx, [rdx+14h]
0x180074a84  sub     rcx, rax
0x180074a87  test    rcx, rcx
0x180074a8a  jnz     short loc_180074AB7
0x180074a8c  cmp     [rdx+8], r14d
0x180074a90  jz      short loc_180074AC0
0x180074a92  mov     rcx, [rdx]
0x180074a95  test    rcx, rcx
0x180074a98  jz      short loc_180074AB7
0x180074a9a  mov     r9d, r14d
0x180074a9d  cmp     r9d, [rdx+8]
0x180074aa1  jnb     short loc_180074AB7
0x180074aa3  cmp     dword ptr [rcx], 0F4h
0x180074aa9  jz      short loc_180074AB4
0x180074aab  inc     r9d
0x180074aae  add     rcx, 4
0x180074ab2  jmp     short loc_180074A9D
0x180074ab4  mov     r10b, 1
0x180074ab7  inc     r11d
0x180074aba  add     rdx, 20h ; ' '
0x180074abe  jmp     short loc_180074A72
0x180074ac0  mov     r10b, 1
0x180074ac3  test    r10b, r10b
0x180074ac6  jz      loc_180074F8A
0x180074acc  mov     [rsp+1C8h+var_160], 0F4h
0x180074ad4  lea     rcx, [rsp+1C8h+var_160]
0x180074ad9  mov     [rsp+1C8h+var_68], rcx
0x180074ae1  mov     [rsp+1C8h+var_60], 1
0x180074aec  mov     qword ptr [rsp+1C8h+var_5C.Data1], r8
0x180074af4  mov     qword ptr [rsp+1C8h+var_5C.Data4], rax
0x180074afc  mov     [rsp+1C8h+pv], r14
0x180074b01  mov     [rsp+1C8h+var_15C], 1
0x180074b09  lea     rdx, IID_IDBProperties
0x180074b10  mov     rcx, [rbx+38h]
0x180074b14  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x180074b19  mov     rbx, rax
0x180074b1c  test    rax, rax
0x180074b1f  jz      loc_180074F8A
0x180074b25  mov     rcx, [rax]
0x180074b28  mov     rax, [rcx+18h]
0x180074b2c  lea     rcx, [rsp+1C8h+pv]
0x180074b31  mov     qword ptr [rsp+1C8h+var_1A8], rcx
0x180074b36  lea     r9, [rsp+1C8h+var_15C]
0x180074b3b  lea     r8, [rsp+1C8h+var_68]
0x180074b43  mov     edx, 1
0x180074b48  mov     rcx, rbx
0x180074b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b50  test    eax, eax
0x180074b52  js      short loc_180074B91
0x180074b54  lea     rcx, [rdi+208h]; this
0x180074b5b  mov     [rsp+1C8h+var_1A8], r14b; bool
0x180074b60  mov     r9b, 1; bool
0x180074b63  mov     r8, [rsp+1C8h+pv]
0x180074b68  mov     r8, [r8]; struct tagDBPROP *
0x180074b6b  lea     rdx, [rsp+1C8h+var_5C]; struct _GUID *
0x180074b73  call    ?SetProperty@CDBPROPContainer@@QEAAHAEBU_GUID@@AEAUtagDBPROP@@_N2@Z; CDBPROPContainer::SetProperty(_GUID const &,tagDBPROP &,bool,bool)
0x180074b78  mov     rcx, [rsp+1C8h+pv]
0x180074b7d  mov     rcx, [rcx]; pv
0x180074b80  call    cs:__imp_CoTaskMemFree
0x180074b86  mov     rcx, [rsp+1C8h+pv]; pv
0x180074b8b  call    cs:__imp_CoTaskMemFree
0x180074b91  mov     rax, [rbx]
0x180074b94  mov     rcx, rbx
0x180074b97  mov     rax, [rax+10h]
0x180074b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ba0  jmp     loc_180074F8A
0x180074ba5  xor     edx, edx; Val
0x180074ba7  lea     r8d, [rdx+48h]; Size
0x180074bab  lea     rcx, [rsp+1C8h+var_108]; void *
0x180074bb3  call    memset_0
0x180074bb8  mov     [rsp+1C8h+var_108.dwPropertyID], 0F8h
0x180074bc3  lea     r12, [rdi+208h]
0x180074bca  lea     r8, [rsp+1C8h+var_108]; struct tagDBPROP *
0x180074bd2  lea     rdx, DBPROPSET_DBINIT; struct _GUID *
0x180074bd9  mov     rcx, r12; this
0x180074bdc  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x180074be1  mov     [rsp+1C8h+var_198], al
0x180074be5  mov     [rdi+268h], r14b
0x180074bec  mov     rcx, r12; this
0x180074bef  call    ?ClearAllProperties@CDBPROPContainer@@QEAAXXZ; CDBPROPContainer::ClearAllProperties(void)
0x180074bf4  lea     rdx, IID_IDBProperties
0x180074bfb  mov     rcx, [rbx+38h]
0x180074bff  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x180074c04  mov     r14, rax
0x180074c07  mov     [rsp+1C8h+var_190], 0
0x180074c0f  mov     [rsp+1C8h+var_180], 0
0x180074c18  mov     rcx, [rax]
0x180074c1b  mov     rax, [rcx+18h]
0x180074c1f  lea     rcx, [rsp+1C8h+var_180]
0x180074c24  mov     qword ptr [rsp+1C8h+var_1A8], rcx
0x180074c29  lea     r9, [rsp+1C8h+var_190]
0x180074c2e  xor     r8d, r8d
0x180074c31  xor     edx, edx
0x180074c33  mov     rcx, r14
0x180074c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c3b  mov     ebx, eax
0x180074c3d  mov     rax, [r14]
0x180074c40  mov     rcx, r14
0x180074c43  mov     rax, [rax+10h]
0x180074c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c4c  test    ebx, ebx
0x180074c4e  jns     short loc_180074CC8
0x180074c50  mov     eax, cs:_bidGblFlags
0x180074c56  test    al, 2
0x180074c58  jz      short loc_180074CB3
0x180074c5a  mov     r8d, 34Eh; unsigned int
0x180074c60  lea     rdx, aCdbpropertiesG_2; "<CDBProperties::GetProperties|OLEDB|ERR"...
0x180074c67  mov     ecx, ebx; int
0x180074c69  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074c6e  mov     eax, cs:_bidGblFlags
0x180074c74  test    al, 2
0x180074c76  jz      short loc_180074CB3
0x180074c78  mov     r8d, 34Eh; unsigned int
0x180074c7e  lea     rdx, aCdbpropertiesG_2; "<CDBProperties::GetProperties|OLEDB|ERR"...
0x180074c85  mov     ecx, ebx; int
0x180074c87  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074c8c  mov     eax, cs:_bidGblFlags
0x180074c92  test    al, 2
0x180074c94  jz      short loc_180074CB3
0x180074c96  mov     r9d, ebx
0x180074c99  lea     r8, aCdbpropertiesG_6; "<CDBProperties::GetProperties|Trace|HR>"...
0x180074ca0  mov     edx, 0D3809h
0x180074ca5  mov     rcx, cs:off_1800C84E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180074cac  call    _bidTraceHR
0x180074cb1  mov     ebx, eax
0x180074cb3  mov     [rsp+1C8h+pExceptionObject], ebx
0x180074cb7  lea     rdx, _TI1J; pThrowInfo
0x180074cbe  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x180074cc3  call    _CxxThrowException_0
0x180074cc8  mov     [rsp+1C8h+var_1A8], 1; bool
0x180074ccd  mov     r9b, 1; bool
0x180074cd0  mov     r8, [rsp+1C8h+var_180]; struct tagDBPROPSET *
0x180074cd5  mov     edx, [rsp+1C8h+var_190]; unsigned int
0x180074cd9  mov     rcx, r12; this
0x180074cdc  call    ?AddNewPropSets@CDBPROPContainer@@QEAAJKPEAUtagDBPROPSET@@_N1@Z; CDBPROPContainer::AddNewPropSets(ulong,tagDBPROPSET *,bool,bool)
0x180074ce1  mov     ebx, eax
0x180074ce3  test    eax, eax
0x180074ce5  jns     short loc_180074D5F
0x180074ce7  mov     eax, cs:_bidGblFlags
0x180074ced  test    al, 2
0x180074cef  jz      short loc_180074D4A
0x180074cf1  mov     r8d, 353h; unsigned int
0x180074cf7  lea     rdx, aCdbpropertiesG_2; "<CDBProperties::GetProperties|OLEDB|ERR"...
0x180074cfe  mov     ecx, ebx; int
0x180074d00  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074d05  mov     eax, cs:_bidGblFlags
0x180074d0b  test    al, 2
0x180074d0d  jz      short loc_180074D4A
0x180074d0f  mov     r8d, 353h; unsigned int
0x180074d15  lea     rdx, aCdbpropertiesG_2; "<CDBProperties::GetProperties|OLEDB|ERR"...
0x180074d1c  mov     ecx, ebx; int
0x180074d1e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074d23  mov     eax, cs:_bidGblFlags
0x180074d29  test    al, 2
  ... truncated ...
```
