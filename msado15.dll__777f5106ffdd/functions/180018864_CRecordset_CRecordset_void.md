# CRecordset::~CRecordset(void)

- ea: `0x180018864`
- end: `0x1800193c0`
- name: `??1CRecordset@@UEAA@XZ`
- size: `2908`
- prototype: `void __fastcall(CRecordset *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800184b0`
- `0x1800a59e0`
- `0x1800c4cfc`

## callees

- `0x180018864`
- `0x1800193c8`
- `0x1800193f0`
- `0x180019460`
- `0x1800195ac`
- `0x180019634`
- `0x1800196c0`
- `0x180019700`
- `0x18005b91c`
- `0x1800657d0`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x180018a50`
- `MSDART!MpHeapFree` at `0x180018a72`
- `MSDART!MpHeapFree` at `0x180018a8c`
- `MSDART!MpHeapFree` at `0x180018ac0`
- `MSDART!MpHeapFree` at `0x180018ae8`
- `MSDART!MpHeapFree` at `0x180018b17`
- `MSDART!MpHeapFree` at `0x180018b46`
- `MSDART!MpHeapFree` at `0x180018b75`
- `MSDART!MpHeapFree` at `0x180018ba4`
- `MSDART!MpHeapFree` at `0x18001906c`
- `MSDART!MpHeapFree` at `0x180019092`
- `MSDART!MpHeapFree` at `0x1800190b8`
- `MSDART!MpHeapFree` at `0x18001912c`
- `MSDART!MpHeapFree` at `0x18001915b`
- `MSDART!MpHeapFree` at `0x1800191d7`
- `MSDART!MpHeapFree` at `0x180019206`
- `MSDART!MpHeapFree` at `0x180019282`
- `MSDART!MpHeapFree` at `0x1800192b1`
- `MSDART!MpHeapFree` at `0x180018a50`
- `MSDART!MpHeapFree` at `0x180018a72`
- `MSDART!MpHeapFree` at `0x180018a8c`
- `MSDART!MpHeapFree` at `0x180018ac0`
- `MSDART!MpHeapFree` at `0x180018ae8`
- `MSDART!MpHeapFree` at `0x180018b17`
- `MSDART!MpHeapFree` at `0x180018b46`
- `MSDART!MpHeapFree` at `0x180018b75`
- `MSDART!MpHeapFree` at `0x180018ba4`
- `MSDART!MpHeapFree` at `0x18001906c`
- `MSDART!MpHeapFree` at `0x180019092`
- `MSDART!MpHeapFree` at `0x1800190b8`
- `MSDART!MpHeapFree` at `0x18001912c`
- `MSDART!MpHeapFree` at `0x18001915b`
- `MSDART!MpHeapFree` at `0x1800191d7`
- `MSDART!MpHeapFree` at `0x180019206`
- `MSDART!MpHeapFree` at `0x180019282`
- `MSDART!MpHeapFree` at `0x1800192b1`
- `ole32!CoTaskMemFree` at `0x180019180`
- `ole32!CoTaskMemFree` at `0x18001922b`
- `ole32!CoTaskMemFree` at `0x1800192d6`
- `ole32!CoTaskMemFree` at `0x180019180`
- `ole32!CoTaskMemFree` at `0x18001922b`
- `ole32!CoTaskMemFree` at `0x1800192d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180018a04`
- `OLEAUT32!__imp_SysFreeString` at `0x180018bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180019342`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180018a04`
- `OLEAUT32!__imp_SysFreeString` at `0x180018bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180019342`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRecordset::~CRecordset(CRecordset *this)
{
  CStdComObjectRoot *v2; // rdi
  __int64 v3; // rax
  CPropSetRefInfo *v4; // rcx
  unsigned int v5; // ebp
  _QWORD *i; // rsi
  __int64 v7; // rdi
  __int64 v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rcx
  int v19; // edx
  __int64 v20; // rdx
  __int64 v21; // rdx
  void *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  void *v28; // rcx
  OLECHAR *v29; // rcx
  char **v30; // rdi
  char *v31; // rsi
  __int64 v32; // rcx
  char *v33; // rax
  char **v34; // rdi
  char *v35; // rsi
  __int64 v36; // rcx
  char *v37; // rax
  char **v38; // rdi
  char *v39; // rsi
  char *v40; // rax
  char *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  char *v46; // rcx

  *((_QWORD *)this + 229) = &ATL::CComObject<CRowPositionChange>::`vftable'{for `IRowPositionChange'};
  v2 = (CRecordset *)((char *)this + 1840);
  *((_QWORD *)this + 230) = &ATL::CComObject<CRowPositionChange>::`vftable'{for `CNotify'};
  *((_DWORD *)this + 462) = 1;
  _InterlockedDecrement(&dword_180122C88);
  *((_QWORD *)this + 229) = &CRowPositionChange::`vftable'{for `IRowPositionChange'};
  *((_QWORD *)this + 230) = &CRowPositionChange::`vftable'{for `CNotify'};
  v3 = *((_QWORD *)this + 238);
  if ( v3 )
    *(_QWORD *)(v3 + 48) = 0;
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 1936);
  CStdComObjectRoot::~CStdComObjectRoot(v2);
  *((_QWORD *)this + 213) = &CADOStackComObject<CRsetProperties>::`vftable'{for `ADOIDispatchImpl<ADOProperties>'};
  *((_QWORD *)this + 214) = &CADOStackComObject<CFldProperties>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'};
  *((_QWORD *)this + 215) = &CADOStackComObject<CRsetProperties>::`vftable'{for `CStdCollection'};
  *((_DWORD *)this + 432) = 1;
  _InterlockedDecrement(&dword_180122C88);
  *((_QWORD *)this + 213) = &CStdPropSetProperties2::`vftable'{for `ADOIDispatchImpl<ADOProperties>'};
  *((_QWORD *)this + 214) = &CStdProperties::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'};
  *((_QWORD *)this + 215) = &CStdPropSetProperties2::`vftable'{for `CStdCollection'};
  v4 = (CPropSetRefInfo *)*((_QWORD *)this + 226);
  if ( v4 )
    CPropSetRefInfo::`vector deleting destructor'(v4, 1u);
  CStdProperties::~CStdProperties((CRecordset *)((char *)this + 1704));
  *((_QWORD *)this + 197) = &CADOStackComObject<CRsetFields>::`vftable'{for `ADOIDispatchImpl<ADOFields>'};
  *((_QWORD *)this + 198) = &CADOStackComObject<CRsetFields>::`vftable'{for `CStdCollection'};
  *((_QWORD *)this + 210) = &CADOStackComObject<CRsetFields>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 211) = &CADOStackComObject<CRsetFields>::`vftable'{for `ADOIDispatchImpl<ADOFieldsEx>'};
  *((_DWORD *)this + 398) = 1;
  _InterlockedDecrement(&dword_180122C88);
  CStdCollection::~CStdCollection((CRecordset *)((char *)this + 1584));
  *((_QWORD *)this + 195) = &CRecordset::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 392) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRecordset::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_1208[0],
      7,
      *((int *)this + 392),
      0);
  *((_DWORD *)this + 392) = 0;
  if ( (*((_BYTE *)this + 1544) & 2) != 0 )
  {
    SysFreeString(*((BSTR *)this + 192));
    *((_QWORD *)this + 192) = 0;
  }
  if ( (*((_BYTE *)this + 1520) & 2) != 0 )
  {
    SysFreeString(*((BSTR *)this + 189));
    *((_QWORD *)this + 189) = 0;
  }
  v5 = 0;
  for ( i = (_QWORD *)((char *)this + 1472); v5 < *((_DWORD *)this + 366); ++v5 )
  {
    v7 = *(_QWORD *)(*i + 8LL * v5);
    if ( v7 )
    {
      do
      {
        v8 = *(_QWORD *)(v7 + 40);
        v9 = *(_QWORD *)(v7 + 32);
        if ( v9 )
          MpHeapFree(g_hHeapHandle, v9);
        if ( (*(_BYTE *)(v7 + 16) & 2) != 0 )
        {
          v10 = *(_QWORD *)(v7 + 8);
          if ( v10 )
            MpHeapFree(g_hHeapHandle, v10);
          *(_QWORD *)(v7 + 8) = 0;
        }
        MpHeapFree(g_hHeapHandle, v7);
        v7 = v8;
      }
      while ( v8 );
    }
  }
  if ( *i )
    MpHeapFree(g_hHeapHandle, *i);
  if ( (*((_BYTE *)this + 1352) & 2) != 0 )
  {
    v11 = *((_QWORD *)this + 168);
    if ( v11 )
      MpHeapFree(g_hHeapHandle, v11);
    *((_QWORD *)this + 168) = 0;
  }
  if ( (*((_BYTE *)this + 1336) & 2) != 0 )
  {
    v12 = *((_QWORD *)this + 166);
    if ( v12 )
      MpHeapFree(g_hHeapHandle, v12);
    *((_QWORD *)this + 166) = 0;
  }
  if ( (*((_BYTE *)this + 1320) & 2) != 0 )
  {
    v13 = *((_QWORD *)this + 164);
    if ( v13 )
      MpHeapFree(g_hHeapHandle, v13);
    *((_QWORD *)this + 164) = 0;
  }
  if ( (*((_BYTE *)this + 1304) & 2) != 0 )
  {
    v14 = *((_QWORD *)this + 162);
    if ( v14 )
      MpHeapFree(g_hHeapHandle, v14);
    *((_QWORD *)this + 162) = 0;
  }
  if ( (*((_BYTE *)this + 1288) & 2) != 0 )
  {
    v15 = *((_QWORD *)this + 160);
    if ( v15 )
      MpHeapFree(g_hHeapHandle, v15);
    *((_QWORD *)this + 160) = 0;
  }
  if ( (*((_BYTE *)this + 1272) & 2) != 0 )
  {
    SysFreeString(*((BSTR *)this + 158));
    *((_QWORD *)this + 158) = 0;
  }
  v16 = *((_QWORD *)this + 143);
  if ( v16 )
  {
    v17 = *((_DWORD *)this + 288) & 2;
    if ( (*((_DWORD *)this + 288) & 1) != 0 )
    {
      if ( v17
        || (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)g_pStaticGlobals + 10) + 32LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             *((unsigned int *)this + 286)) >= 0 )
      {
        *((_DWORD *)this + 286) = 0;
      }
    }
    else
    {
      if ( !v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *((_QWORD *)this + 143) = 0;
    }
  }
  v18 = *((_QWORD *)this + 141);
  if ( v18 )
  {
    v19 = *((_DWORD *)this + 284) & 2;
    if ( (*((_DWORD *)this + 284) & 1) != 0 )
    {
      if ( v19
        || (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)g_pStaticGlobals + 10) + 32LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             *((unsigned int *)this + 282)) >= 0 )
      {
        *((_DWORD *)this + 282) = 0;
      }
    }
    else
    {
      if ( !v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      *((_QWORD *)this + 141) = 0;
    }
  }
  v20 = *((_QWORD *)this + 127);
  if ( v20 )
  {
    MpHeapFree(g_hHeapHandle, v20);
    *((_QWORD *)this + 127) = 0;
  }
  if ( *((_BYTE *)this + 1072) )
  {
    v43 = *((_QWORD *)this + 128);
    if ( v43 )
    {
      MpHeapFree(g_hHeapHandle, v43);
      *((_QWORD *)this + 128) = 0;
    }
  }
  *((_QWORD *)this + 125) = 0;
  v21 = *((_QWORD *)this + 132);
  if ( v21 )
  {
    MpHeapFree(g_hHeapHandle, v21);
    *((_QWORD *)this + 132) = 0;
    *((_QWORD *)this + 133) = 0;
  }
  v22 = (void *)*((_QWORD *)this + 131);
  if ( v22 && *((_DWORD *)this + 259) )
  {
    CoTaskMemFree(v22);
    *((_QWORD *)this + 131) = 0;
  }
  *((_BYTE *)this + 1073) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 135) = &CRecordGroup::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 272) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRecordGroup::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_88[0],
      7,
      *((int *)this + 272),
      0);
  *((_DWORD *)this + 272) = 0;
  v23 = *((_QWORD *)this + 112);
  if ( v23 )
  {
    MpHeapFree(g_hHeapHandle, v23);
    *((_QWORD *)this + 112) = 0;
  }
  if ( *((_BYTE *)this + 952) )
  {
    v44 = *((_QWORD *)this + 113);
    if ( v44 )
    {
      MpHeapFree(g_hHeapHandle, v44);
      *((_QWORD *)this + 113) = 0;
    }
  }
  *((_QWORD *)this + 110) = 0;
  v24 = *((_QWORD *)this + 117);
  if ( v24 )
  {
    MpHeapFree(g_hHeapHandle, v24);
    *((_QWORD *)this + 117) = 0;
    *((_QWORD *)this + 118) = 0;
  }
  v25 = (void *)*((_QWORD *)this + 116);
  if ( v25 && *((_DWORD *)this + 229) )
  {
    CoTaskMemFree(v25);
    *((_QWORD *)this + 116) = 0;
  }
  *((_BYTE *)this + 953) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 120) = &CRecordGroup::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 242) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRecordGroup::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_88[0],
      7,
      *((int *)this + 242),
      0);
  *((_DWORD *)this + 242) = 0;
  v26 = *((_QWORD *)this + 97);
  if ( v26 )
  {
    MpHeapFree(g_hHeapHandle, v26);
    *((_QWORD *)this + 97) = 0;
  }
  if ( *((_BYTE *)this + 832) )
  {
    v45 = *((_QWORD *)this + 98);
    if ( v45 )
    {
      MpHeapFree(g_hHeapHandle, v45);
      *((_QWORD *)this + 98) = 0;
    }
  }
  *((_QWORD *)this + 95) = 0;
  v27 = *((_QWORD *)this + 102);
  if ( v27 )
  {
    MpHeapFree(g_hHeapHandle, v27);
    *((_QWORD *)this + 102) = 0;
    *((_QWORD *)this + 103) = 0;
  }
  v28 = (void *)*((_QWORD *)this + 101);
  if ( v28 && *((_DWORD *)this + 199) )
  {
    CoTaskMemFree(v28);
    *((_QWORD *)this + 101) = 0;
  }
  *((_BYTE *)this + 833) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 105) = &CRecordGroup::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 212) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRecordGroup::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_88[0],
      7,
      *((int *)this + 212),
      0);
  *((_DWORD *)this + 212) = 0;
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 656);
  CAdoInterfacePtr<IRowsetIndex,&_GUID const IID_IRowsetIndex>::SetNullInterface((char *)this + 632);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 608);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 584);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 560);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 536);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 512);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 488);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 464);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 440);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 416);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 392);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 368);
  CAdoInterfacePtr<IAccessor,&_GUID const IID_IAccessor>::SetNullInterface((unsigned int *)this + 86);
  CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface((char *)this + 320);
  *((_QWORD *)this + 31) = &CStream::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 32) = &CStream::`vftable'{for `IADOSecurity'};
  if ( *((_DWORD *)this + 67) )
    CADOIGlobalInterfaceTable::RevokeInterfaceFromGlobal(
      (CDAOStaticGlobals *)((char *)g_pStaticGlobals + 80),
      (unsigned int *)this + 66);
  *((_DWORD *)this + 67) = 0;
  v29 = (OLECHAR *)*((_QWORD *)this + 34);
  if ( v29 )
  {
    SysFreeString(v29);
    *((_QWORD *)this + 34) = 0;
  }
  v30 = (char **)((char *)this + 216);
  v31 = (char *)this + 216;
  if ( *((int *)this + 56) >= 2 )
    v31 = *v30;
  while ( 1 )
  {
    v32 = *((int *)this + 56);
    v33 = (char *)this + 216;
    if ( (int)v32 >= 2 )
      v33 = *v30;
    if ( v31 >= &v33[8 * v32] )
      break;
    if ( *(_QWORD *)v31 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
    v31 += 8;
  }
  ATL::CComDynamicUnkArray::~CComDynamicUnkArray((CRecordset *)((char *)this + 216));
  v34 = (char **)((char *)this + 160);
  v35 = (char *)this + 160;
  if ( *((int *)this + 42) >= 2 )
    v35 = *v34;
  while ( 1 )
  {
    v36 = *((int *)this + 42);
    v37 = (char *)this + 160;
    if ( (int)v36 >= 2 )
      v37 = *v34;
    if ( v35 >= &v37[8 * v36] )
      break;
    if ( *(_QWORD *)v35 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 16LL))(*(_QWORD *)v35);
    v35 += 8;
  }
  ATL::CComDynamicUnkArray::~CComDynamicUnkArray((CRecordset *)((char *)this + 160));
  v38 = (char **)((char *)this + 112);
  v39 = (char *)this + 112;
  if ( *((int *)this + 30) >= 2 )
    v39 = *v38;
  while ( 1 )
  {
    v40 = (char *)this + 112;
    if ( *((int *)this + 30) >= 2 )
      v40 = *v38;
    if ( v39 >= &v40[8 * *((int *)this + 30)] )
      break;
    if ( *(_QWORD *)v39 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    v39 += 8;
  }
  ATL::CComDynamicUnkArray::~CComDynamicUnkArray((CRecordset *)((char *)this + 112));
  v41 = (char *)this + 32;
  *(_QWORD *)v41 = &CStdSymbiontObject::`vftable';
  if ( _InterlockedExchange((volatile __int32 *)v41 + 14, 0) == 1 )
  {
    *((_DWORD *)v41 + 12) = 1;
    v46 = (char *)*((_QWORD *)v41 + 4);
    if ( v41 == v46 )
      v46 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v46 + 16LL))(v46);
  }
  *(_QWORD *)v41 = &CStdComObjectRoot::`vftable';
  v42 = *((_QWORD *)v41 + 5);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    *((_QWORD *)v41 + 5) = 0;
  }
}

```

## disassembly

```asm
0x180018864  push    rbx
0x180018866  push    rbp
0x180018867  push    rsi
0x180018868  push    rdi
0x180018869  push    r12
0x18001886b  push    r13
0x18001886d  push    r14
0x18001886f  push    r15
0x180018871  sub     rsp, 38h
0x180018875  mov     rbx, rcx
0x180018878  lea     rax, ??_7?$CComObject@VCRowPositionChange@@@ATL@@6BIRowPositionChange@@@; const ATL::CComObject<CRowPositionChange>::`vftable'{for `IRowPositionChange'}
0x18001887f  mov     [rcx+728h], rax
0x180018886  lea     rdi, [rcx+730h]
0x18001888d  lea     rax, ??_7?$CComObject@VCRowPositionChange@@@ATL@@6BCNotify@@@; const ATL::CComObject<CRowPositionChange>::`vftable'{for `CNotify'}
0x180018894  mov     [rdi], rax
0x180018897  mov     r13d, 1
0x18001889d  mov     [rcx+738h], r13d
0x1800188a4  lock dec cs:dword_180122C88
0x1800188ab  lea     rax, ??_7CRowPositionChange@@6BIRowPositionChange@@@; const CRowPositionChange::`vftable'{for `IRowPositionChange'}
0x1800188b2  mov     [rcx+728h], rax
0x1800188b9  lea     rax, ??_7CRowPositionChange@@6BCNotify@@@; const CRowPositionChange::`vftable'{for `CNotify'}
0x1800188c0  mov     [rdi], rax
0x1800188c3  mov     rax, [rcx+770h]
0x1800188ca  xor     r15d, r15d
0x1800188cd  test    rax, rax
0x1800188d0  jnz     loc_1800190D7
0x1800188d6  add     rcx, 790h
0x1800188dd  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x1800188e2  nop
0x1800188e3  mov     rcx, rdi; this
0x1800188e6  call    ??1CStdComObjectRoot@@UEAA@XZ; CStdComObjectRoot::~CStdComObjectRoot(void)
0x1800188eb  lea     rdi, [rbx+6A8h]
0x1800188f2  lea     rax, ??_7?$CADOStackComObject@VCRsetProperties@@@@6B?$ADOIDispatchImpl@UADOProperties@@@@@; const CADOStackComObject<CRsetProperties>::`vftable'{for `ADOIDispatchImpl<ADOProperties>'}
0x1800188f9  mov     [rdi], rax
0x1800188fc  lea     rax, ??_7?$CADOStackComObject@VCFldProperties@@@@6B?$ISupportErrorInfoImpl@$1?IID_IADOProperties@@3U_GUID@@B@ATL@@@; const CADOStackComObject<CFldProperties>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'}
0x180018903  mov     [rdi+8], rax
0x180018907  lea     rax, ??_7?$CADOStackComObject@VCRsetProperties@@@@6BCStdCollection@@@; const CADOStackComObject<CRsetProperties>::`vftable'{for `CStdCollection'}
0x18001890e  mov     [rdi+10h], rax
0x180018912  mov     [rdi+18h], r13d
0x180018916  lock dec cs:dword_180122C88
0x18001891d  lea     rax, ??_7CStdPropSetProperties2@@6B?$ADOIDispatchImpl@UADOProperties@@@@@; const CStdPropSetProperties2::`vftable'{for `ADOIDispatchImpl<ADOProperties>'}
0x180018924  mov     [rdi], rax
0x180018927  lea     rax, ??_7CStdProperties@@6B?$ISupportErrorInfoImpl@$1?IID_IADOProperties@@3U_GUID@@B@ATL@@@; const CStdProperties::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_IADOProperties>'}
0x18001892e  mov     [rdi+8], rax
0x180018932  lea     rax, ??_7CStdPropSetProperties2@@6BCStdCollection@@@; const CStdPropSetProperties2::`vftable'{for `CStdCollection'}
0x180018939  mov     [rdi+10h], rax
0x18001893d  mov     rcx, [rdi+68h]; this
0x180018941  test    rcx, rcx
0x180018944  jnz     loc_1800190E0
0x18001894a  mov     rcx, rdi; this
0x18001894d  call    ??1CStdProperties@@UEAA@XZ; CStdProperties::~CStdProperties(void)
0x180018952  lea     rax, ??_7?$CADOStackComObject@VCRsetFields@@@@6B?$ADOIDispatchImpl@UADOFields@@@@@; const CADOStackComObject<CRsetFields>::`vftable'{for `ADOIDispatchImpl<ADOFields>'}
0x180018959  mov     [rbx+628h], rax
0x180018960  lea     rcx, [rbx+630h]; this
0x180018967  lea     rax, ??_7?$CADOStackComObject@VCRsetFields@@@@6BCStdCollection@@@; const CADOStackComObject<CRsetFields>::`vftable'{for `CStdCollection'}
0x18001896e  mov     [rcx], rax
0x180018971  lea     rax, ??_7?$CADOStackComObject@VCRsetFields@@@@6BISupportErrorInfo@@@; const CADOStackComObject<CRsetFields>::`vftable'{for `ISupportErrorInfo'}
0x180018978  mov     [rbx+690h], rax
0x18001897f  lea     rax, ??_7?$CADOStackComObject@VCRsetFields@@@@6B?$ADOIDispatchImpl@UADOFieldsEx@@@@@; const CADOStackComObject<CRsetFields>::`vftable'{for `ADOIDispatchImpl<ADOFieldsEx>'}
0x180018986  mov     [rbx+698h], rax
0x18001898d  mov     [rbx+638h], r13d
0x180018994  lock dec cs:dword_180122C88
0x18001899b  call    ??1CStdCollection@@UEAA@XZ; CStdCollection::~CStdCollection(void)
0x1800189a0  nop
0x1800189a1  lea     rax, ??_7CNotUpdt_BidGeneric@CRecordset@@6B@; const CRecordset::CNotUpdt_BidGeneric::`vftable'
0x1800189a8  mov     [rbx+618h], rax
0x1800189af  movsxd  rcx, dword ptr [rbx+620h]
0x1800189b6  mov     r14d, 7
0x1800189bc  test    ecx, ecx
0x1800189be  jnz     loc_1800190ED
0x1800189c4  mov     [rbx+620h], r15d
0x1800189cb  mov     r12d, 2
0x1800189d1  test    [rbx+608h], r12b
0x1800189d8  jz      short loc_1800189F4
0x1800189da  mov     rcx, [rbx+600h]; bstrString
0x1800189e1  call    cs:__imp_SysFreeString
0x1800189e8  nop     dword ptr [rax+rax+00h]
0x1800189ed  mov     [rbx+600h], r15
0x1800189f4  test    [rbx+5F0h], r12b
0x1800189fb  jz      short loc_180018A17
0x1800189fd  mov     rcx, [rbx+5E8h]; bstrString
0x180018a04  call    cs:__imp_SysFreeString
0x180018a0b  nop     dword ptr [rax+rax+00h]
0x180018a10  mov     [rbx+5E8h], r15
0x180018a17  mov     ebp, r15d
0x180018a1a  lea     rsi, [rbx+5C0h]
0x180018a21  cmp     [rbx+5B8h], r15d
0x180018a28  jbe     loc_180018AB1
0x180018a2e  mov     ecx, ebp
0x180018a30  mov     rax, [rsi]
0x180018a33  mov     rdi, [rax+rcx*8]
0x180018a37  test    rdi, rdi
0x180018a3a  jz      short loc_180018AA0
0x180018a3c  mov     r14, [rdi+28h]
0x180018a40  mov     rdx, [rdi+20h]
0x180018a44  test    rdx, rdx
0x180018a47  jz      short loc_180018A5C
0x180018a49  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018a50  call    cs:__imp_MpHeapFree
0x180018a57  nop     dword ptr [rax+rax+00h]
0x180018a5c  test    [rdi+10h], r12b
0x180018a60  jz      short loc_180018A82
0x180018a62  mov     rdx, [rdi+8]
0x180018a66  test    rdx, rdx
0x180018a69  jz      short loc_180018A7E
0x180018a6b  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018a72  call    cs:__imp_MpHeapFree
0x180018a79  nop     dword ptr [rax+rax+00h]
0x180018a7e  mov     [rdi+8], r15
0x180018a82  mov     rdx, rdi
0x180018a85  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018a8c  call    cs:__imp_MpHeapFree
0x180018a93  nop     dword ptr [rax+rax+00h]
0x180018a98  mov     rdi, r14
0x180018a9b  test    r14, r14
0x180018a9e  jnz     short loc_180018A3C
0x180018aa0  add     ebp, r13d
0x180018aa3  cmp     ebp, [rbx+5B8h]
0x180018aa9  jb      short loc_180018A2E
0x180018aab  mov     r14d, 7
0x180018ab1  mov     rdx, [rsi]
0x180018ab4  test    rdx, rdx
0x180018ab7  jz      short loc_180018ACC
0x180018ab9  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018ac0  call    cs:__imp_MpHeapFree
0x180018ac7  nop     dword ptr [rax+rax+00h]
0x180018acc  test    [rbx+548h], r12b
0x180018ad3  jz      short loc_180018AFB
0x180018ad5  mov     rdx, [rbx+540h]
0x180018adc  test    rdx, rdx
0x180018adf  jz      short loc_180018AF4
0x180018ae1  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018ae8  call    cs:__imp_MpHeapFree
0x180018aef  nop     dword ptr [rax+rax+00h]
0x180018af4  mov     [rbx+540h], r15
0x180018afb  test    [rbx+538h], r12b
0x180018b02  jz      short loc_180018B2A
0x180018b04  mov     rdx, [rbx+530h]
0x180018b0b  test    rdx, rdx
0x180018b0e  jz      short loc_180018B23
0x180018b10  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018b17  call    cs:__imp_MpHeapFree
0x180018b1e  nop     dword ptr [rax+rax+00h]
0x180018b23  mov     [rbx+530h], r15
0x180018b2a  test    [rbx+528h], r12b
0x180018b31  jz      short loc_180018B59
0x180018b33  mov     rdx, [rbx+520h]
0x180018b3a  test    rdx, rdx
0x180018b3d  jz      short loc_180018B52
0x180018b3f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018b46  call    cs:__imp_MpHeapFree
0x180018b4d  nop     dword ptr [rax+rax+00h]
0x180018b52  mov     [rbx+520h], r15
0x180018b59  test    [rbx+518h], r12b
0x180018b60  jz      short loc_180018B88
0x180018b62  mov     rdx, [rbx+510h]
0x180018b69  test    rdx, rdx
0x180018b6c  jz      short loc_180018B81
0x180018b6e  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018b75  call    cs:__imp_MpHeapFree
0x180018b7c  nop     dword ptr [rax+rax+00h]
0x180018b81  mov     [rbx+510h], r15
0x180018b88  test    [rbx+508h], r12b
0x180018b8f  jz      short loc_180018BB7
0x180018b91  mov     rdx, [rbx+500h]
0x180018b98  test    rdx, rdx
0x180018b9b  jz      short loc_180018BB0
0x180018b9d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180018ba4  call    cs:__imp_MpHeapFree
0x180018bab  nop     dword ptr [rax+rax+00h]
0x180018bb0  mov     [rbx+500h], r15
0x180018bb7  test    [rbx+4F8h], r12b
0x180018bbe  jz      short loc_180018BDA
0x180018bc0  mov     rcx, [rbx+4F0h]; bstrString
0x180018bc7  call    cs:__imp_SysFreeString
0x180018bce  nop     dword ptr [rax+rax+00h]
0x180018bd3  mov     [rbx+4F0h], r15
0x180018bda  mov     rcx, [rbx+478h]
0x180018be1  test    rcx, rcx
0x180018be4  jz      short loc_180018C09
0x180018be6  mov     eax, [rbx+480h]
0x180018bec  mov     edx, eax
0x180018bee  and     edx, r12d
0x180018bf1  test    r13b, al
0x180018bf4  jnz     loc_180018FD9
0x180018bfa  test    edx, edx
0x180018bfc  jz      loc_180019043
0x180018c02  mov     [rbx+478h], r15
0x180018c09  mov     rcx, [rbx+468h]
0x180018c10  test    rcx, rcx
0x180018c13  jz      short loc_180018C38
0x180018c15  mov     eax, [rbx+470h]
0x180018c1b  mov     edx, eax
0x180018c1d  and     edx, r12d
0x180018c20  test    r13b, al
0x180018c23  jnz     loc_18001900E
0x180018c29  test    edx, edx
0x180018c2b  jz      loc_180019054
0x180018c31  mov     [rbx+468h], r15
0x180018c38  mov     rdx, [rbx+3F8h]
0x180018c3f  test    rdx, rdx
0x180018c42  jnz     loc_180019125
0x180018c48  cmp     [rbx+430h], r15b
0x180018c4f  jnz     loc_180019144
0x180018c55  mov     [rbx+3E8h], r15
0x180018c5c  mov     rdx, [rbx+420h]
0x180018c63  test    rdx, rdx
0x180018c66  jnz     loc_180019065
0x180018c6c  mov     rcx, [rbx+418h]; pv
0x180018c73  test    rcx, rcx
0x180018c76  jnz     loc_180019173
0x180018c7c  mov     [rbx+431h], r15b
0x180018c83  mov     [rbx+3D8h], r15
0x180018c8a  lea     rdi, ??_7CNotUpdt_BidGeneric@CRecordGroup@@6B@; const CRecordGroup::CNotUpdt_BidGeneric::`vftable'
0x180018c91  mov     [rbx+438h], rdi
0x180018c98  movsxd  rcx, dword ptr [rbx+440h]
0x180018c9f  test    ecx, ecx
0x180018ca1  jnz     loc_180019198
0x180018ca7  mov     [rbx+440h], r15d
0x180018cae  mov     rdx, [rbx+380h]
0x180018cb5  test    rdx, rdx
0x180018cb8  jnz     loc_1800191D0
0x180018cbe  cmp     [rbx+3B8h], r15b
0x180018cc5  jnz     loc_1800191EF
0x180018ccb  mov     [rbx+370h], r15
0x180018cd2  mov     rdx, [rbx+3A8h]
0x180018cd9  test    rdx, rdx
0x180018cdc  jnz     loc_18001908B
0x180018ce2  mov     rcx, [rbx+3A0h]; pv
0x180018ce9  test    rcx, rcx
0x180018cec  jnz     loc_18001921E
0x180018cf2  mov     [rbx+3B9h], r15b
0x180018cf9  mov     [rbx+360h], r15
0x180018d00  mov     [rbx+3C0h], rdi
0x180018d07  movsxd  rcx, dword ptr [rbx+3C8h]
0x180018d0e  test    ecx, ecx
0x180018d10  jnz     loc_180019243
0x180018d16  mov     [rbx+3C8h], r15d
0x180018d1d  mov     rdx, [rbx+308h]
0x180018d24  test    rdx, rdx
0x180018d27  jnz     loc_18001927B
0x180018d2d  cmp     [rbx+340h], r15b
0x180018d34  jnz     loc_18001929A
0x180018d3a  mov     [rbx+2F8h], r15
0x180018d41  mov     rdx, [rbx+330h]
0x180018d48  test    rdx, rdx
0x180018d4b  jnz     loc_1800190B1
0x180018d51  mov     rcx, [rbx+328h]; pv
0x180018d58  test    rcx, rcx
0x180018d5b  jnz     loc_1800192C9
0x180018d61  mov     [rbx+341h], r15b
0x180018d68  mov     [rbx+2E8h], r15
0x180018d6f  mov     [rbx+348h], rdi
0x180018d76  movsxd  rcx, dword ptr [rbx+350h]
0x180018d7d  test    ecx, ecx
0x180018d7f  jnz     loc_1800192EE
0x180018d85  mov     [rbx+350h], r15d
0x180018d8c  lea     rcx, [rbx+290h]
0x180018d93  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018d98  nop
0x180018d99  lea     rcx, [rbx+278h]
0x180018da0  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetIndex@@$1?IID_IRowsetIndex@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetIndex,&_GUID const IID_IRowsetIndex>::SetNullInterface(void)
0x180018da5  nop
0x180018da6  lea     rcx, [rbx+260h]
0x180018dad  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018db2  nop
0x180018db3  lea     rcx, [rbx+248h]
0x180018dba  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018dbf  nop
0x180018dc0  lea     rcx, [rbx+230h]
0x180018dc7  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018dcc  nop
0x180018dcd  lea     rcx, [rbx+218h]
0x180018dd4  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018dd9  nop
0x180018dda  lea     rcx, [rbx+200h]
0x180018de1  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018de6  nop
0x180018de7  lea     rcx, [rbx+1E8h]
0x180018dee  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018df3  nop
0x180018df4  lea     rcx, [rbx+1D0h]
0x180018dfb  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018e00  nop
0x180018e01  lea     rcx, [rbx+1B8h]
0x180018e08  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018e0d  nop
0x180018e0e  lea     rcx, [rbx+1A0h]
0x180018e15  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018e1a  nop
0x180018e1b  lea     rcx, [rbx+188h]
0x180018e22  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018e27  nop
0x180018e28  lea     rcx, [rbx+170h]
0x180018e2f  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x180018e34  nop
0x180018e35  lea     rcx, [rbx+158h]; unsigned int *
0x180018e3c  call    ?SetNullInterface@?$CAdoInterfacePtr@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IAccessor,&_GUID const IID_IAccessor>::SetNullInterface(void)
0x180018e41  nop
0x180018e42  lea     rcx, [rbx+140h]
  ... truncated ...
```
