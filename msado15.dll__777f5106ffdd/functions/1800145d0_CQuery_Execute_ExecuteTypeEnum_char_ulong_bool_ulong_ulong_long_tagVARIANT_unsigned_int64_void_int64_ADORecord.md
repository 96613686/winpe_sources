# CQuery::Execute(ExecuteTypeEnum,char,ulong,bool,ulong,ulong,long,tagVARIANT *,unsigned __int64,void *,__int64 *,_ADORecordset * *)

- ea: `0x1800145d0`
- end: `0x180016728`
- name: `?Execute@CQuery@@QEAAJW4ExecuteTypeEnum@@DK_NKKJPEAUtagVARIANT@@_KPEAXPEA_JPEAPEAU_ADORecordset@@@Z`
- size: `8536`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014150`

## callees

- `0x180010fac`
- `0x180011458`
- `0x1800145d0`
- `0x180016b90`
- `0x1800170f0`
- `0x1800174b0`
- `0x180018788`
- `0x18001a750`
- `0x18001a910`
- `0x18001afa0`
- `0x180020e20`
- `0x180020fc0`
- `0x1800265d0`
- `0x1800337d0`
- `0x180042a04`
- `0x180045580`
- `0x180049070`
- `0x18004c170`
- `0x18004f140`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x180052bf8`
- `0x180053fec`
- `0x18005410c`
- `0x180056144`
- `0x180056554`
- `0x180057a78`
- `0x180057e80`
- `0x180059d44`
- `0x180059f4c`
- `0x18005a3d4`
- `0x18005b3d4`
- `0x18005cc58`
- `0x18006a22c`
- `0x1800746f0`
- `0x18007dd20`
- `0x180084608`
- `0x1800870a4`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800152a8`
- `msvcrt!_wcsnicmp` at `0x1800152da`
- `msvcrt!_wcsnicmp` at `0x1800152a8`
- `msvcrt!_wcsnicmp` at `0x1800152da`
- `MSDART!UMSEnterCSWraper` at `0x180014747`
- `MSDART!UMSEnterCSWraper` at `0x180016062`
- `MSDART!UMSEnterCSWraper` at `0x180014747`
- `MSDART!UMSEnterCSWraper` at `0x180016062`
- `MSDART!MpHeapAlloc` at `0x180014d1c`
- `MSDART!MpHeapAlloc` at `0x180014d1c`
- `MSDART!MpHeapFree` at `0x180014be0`
- `MSDART!MpHeapFree` at `0x180014bfc`
- `MSDART!MpHeapFree` at `0x180014be0`
- `MSDART!MpHeapFree` at `0x180014bfc`
- `KERNEL32!CreateThread` at `0x1800161ab`
- `KERNEL32!CreateThread` at `0x1800161ab`
- `KERNEL32!CloseHandle` at `0x180016179`
- `KERNEL32!CloseHandle` at `0x180016179`
- `KERNEL32!LeaveCriticalSection` at `0x1800160df`
- `KERNEL32!LeaveCriticalSection` at `0x180016674`
- `KERNEL32!LeaveCriticalSection` at `0x1800160df`
- `KERNEL32!LeaveCriticalSection` at `0x180016674`
- `KERNEL32!TlsSetValue` at `0x18001469e`
- `KERNEL32!TlsSetValue` at `0x1800166e1`
- `KERNEL32!TlsSetValue` at `0x18001469e`
- `KERNEL32!TlsSetValue` at `0x1800166e1`
- `KERNEL32!TlsGetValue` at `0x18001465a`
- `KERNEL32!TlsGetValue` at `0x18001465a`
- `ole32!CoUninitialize` at `0x18001632f`
- `ole32!CoUninitialize` at `0x18001632f`
- `ole32!CoInitialize` at `0x1800162c9`
- `ole32!CoInitialize` at `0x1800162c9`
- `ole32!CoTaskMemFree` at `0x180014afe`
- `ole32!CoTaskMemFree` at `0x180014b25`
- `ole32!CoTaskMemFree` at `0x180014afe`
- `ole32!CoTaskMemFree` at `0x180014b25`
- `OLEAUT32!__imp_SysAllocString` at `0x180015beb`
- `OLEAUT32!__imp_SysAllocString` at `0x180015beb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015b10`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015c63`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015b10`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015c63`
- `OLEAUT32!__imp_SysFreeString` at `0x18001591b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180015bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cd0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001591b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180015bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015cd0`
- `OLEAUT32!__imp_SysStringLen` at `0x180015940`
- `OLEAUT32!__imp_SysStringLen` at `0x180015c2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180015c49`
- `OLEAUT32!__imp_SysStringLen` at `0x180015940`
- `OLEAUT32!__imp_SysStringLen` at `0x180015c2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180015c49`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae6`
- `OLEAUT32!__imp_VariantClear` at `0x180014b9f`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae6`
- `OLEAUT32!__imp_VariantClear` at `0x180014b9f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800166ab`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800166ab`

## string_xrefs

- `0x180015a25`: `<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n`
- `0x180015a41`: `<CCommand::GetCommandText|ADO|ERR>  line %d\n`
- `0x180015ac8`: `<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180015d2e`: `<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180015d4f`: `<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CQuery::Execute(
        _QWORD *a1,
        int a2,
        char a3,
        __int16 a4,
        char a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        struct tagVARIANT *a9,
        unsigned __int64 a10,
        struct CParameter *a11,
        _QWORD *a12,
        struct _ADORecordset **a13)
{
  char v14; // r13
  _DWORD *Value; // rax
  _QWORD *v17; // r15
  _QWORD *v18; // rcx
  CConnection *v19; // rdx
  int v20; // r14d
  int v21; // r12d
  int v22; // edi
  char v23; // r13
  char v24; // si
  unsigned int v25; // eax
  unsigned int BidObjectID; // eax
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // esi
  char *v32; // rcx
  unsigned int i; // r14d
  char *v34; // rdi
  unsigned int v35; // r15d
  __int64 v36; // rsi
  __int64 *v37; // rdx
  unsigned int v38; // eax
  __int64 v39; // rdi
  unsigned int v40; // r15d
  __int64 v41; // rdx
  __int64 v42; // rdx
  CParamBuffer *v43; // rcx
  CParameters *v44; // r12
  unsigned int v45; // eax
  __int64 v46; // rdx
  CExecInfo *v47; // rax
  CExecInfo *v48; // rsi
  unsigned int v49; // eax
  char v50; // r14
  struct _ADORecordset **v51; // r13
  __int64 v52; // r9
  __int64 v53; // rdx
  enum CursorLocationEnum v54; // edi
  __int64 v55; // rdx
  int *v56; // rcx
  __int64 v57; // rdx
  char v58; // cl
  unsigned int v59; // eax
  int v60; // eax
  unsigned int v61; // esi
  int v62; // eax
  unsigned __int8 v63; // r8
  unsigned int v64; // r12d
  int v65; // eax
  unsigned int j; // ecx
  unsigned int v67; // eax
  unsigned int v68; // eax
  enum CursorLocationEnum v69; // r12d
  CConnection *v70; // r14
  const wchar_t *v71; // rcx
  struct CRecordset *v72; // rax
  unsigned int v73; // eax
  int v74; // edi
  LONG v75; // eax
  CVar *v76; // rax
  __int64 v77; // r8
  int v78; // edi
  __int64 v79; // rsi
  unsigned __int64 *v80; // rdi
  unsigned int v81; // eax
  unsigned int v82; // eax
  int Parameter; // r14d
  unsigned int v84; // eax
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rsi
  struct tagVARIANT *v87; // rdi
  int v88; // ecx
  OLECHAR *v89; // rsi
  char v90; // di
  __int64 v91; // r12
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  __int64 v95; // r12
  UINT v96; // eax
  const OLECHAR *v97; // rcx
  __int64 v98; // rax
  int StoredProc; // r14d
  struct _ADOConnection *Connection; // rax
  int v101; // eax
  unsigned int v102; // eax
  unsigned __int16 *v103; // rdx
  OLECHAR *v104; // rcx
  UINT v105; // r14d
  UINT v106; // eax
  BSTR v107; // r14
  void *v108; // rax
  const void *v109; // rdx
  unsigned int v110; // eax
  struct IMultipleResults *v111; // r8
  unsigned int v112; // eax
  struct _ADORecordset *v113; // rdi
  __int64 v114; // rcx
  DWORD v115; // edi
  unsigned int v116; // eax
  __int64 v117; // rcx
  __int64 v118; // rcx
  _QWORD *v119; // rax
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  void *v124; // rcx
  HANDLE Thread; // rax
  unsigned int v126; // eax
  struct CExecInfo *v127; // rdi
  CCommand *v128; // rsi
  int v129; // r14d
  HRESULT v130; // r14d
  char v131; // dl
  int v132; // edi
  unsigned int v133; // eax
  unsigned int v134; // eax
  unsigned int v135; // eax
  unsigned int v136; // eax
  __int64 v137; // rcx
  unsigned int v138; // ebx
  _DWORD *v140; // rax
  IErrorInfo *v141; // rdx
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-E0h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  bool v145; // [rsp+50h] [rbp-B0h]
  bool v146; // [rsp+51h] [rbp-AFh]
  unsigned __int8 v147; // [rsp+51h] [rbp-AFh]
  struct _ADORecordset *v148; // [rsp+58h] [rbp-A8h]
  char v150; // [rsp+61h] [rbp-9Fh]
  int v151; // [rsp+70h] [rbp-90h] BYREF
  int v152; // [rsp+78h] [rbp-88h] BYREF
  int v153; // [rsp+80h] [rbp-80h] BYREF
  int v154; // [rsp+84h] [rbp-7Ch] BYREF
  int v155; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *TlsValue; // [rsp+90h] [rbp-70h] BYREF
  int v157; // [rsp+98h] [rbp-68h]
  __int64 v158; // [rsp+A0h] [rbp-60h]
  int v159; // [rsp+A8h] [rbp-58h]
  __int16 v160; // [rsp+ACh] [rbp-54h]
  char v161; // [rsp+AEh] [rbp-52h]
  _QWORD *v162; // [rsp+B0h] [rbp-50h]
  int ParameterBuffer; // [rsp+B8h] [rbp-48h]
  int v164; // [rsp+BCh] [rbp-44h]
  OLECHAR *v165; // [rsp+C0h] [rbp-40h] BYREF
  char v166; // [rsp+C8h] [rbp-38h]
  struct CParameter *v167; // [rsp+D0h] [rbp-30h] BYREF
  int v168; // [rsp+D8h] [rbp-28h]
  __int64 v169; // [rsp+E0h] [rbp-20h] BYREF
  struct CRecordset *v170; // [rsp+E8h] [rbp-18h]
  LPVOID pv; // [rsp+F0h] [rbp-10h]
  CConnection *v172; // [rsp+F8h] [rbp-8h]
  struct _ADORecordset *v173; // [rsp+100h] [rbp+0h] BYREF
  struct tagVARIANT *v174; // [rsp+108h] [rbp+8h]
  _QWORD *v175; // [rsp+110h] [rbp+10h]
  _QWORD *v176; // [rsp+118h] [rbp+18h]
  tagDBPROPSET v177; // [rsp+120h] [rbp+20h] BYREF
  tagDBPROP v178; // [rsp+150h] [rbp+50h] BYREF

  v14 = a3;
  v168 = a2;
  v153 = a8;
  v174 = a9;
  v167 = a11;
  v176 = a12;
  v162 = a1;
  v164 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  ParameterBuffer = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v157 = 1;
    v158 = 0;
    v159 = 0;
    v160 = 0;
    v161 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v17 = (_QWORD *)a1[17];
  v175 = v17;
  v18 = (_QWORD *)a1[4];
  if ( a1 == v18 )
    v18 = 0;
  v19 = (CConnection *)(v18 - 4);
  if ( !v18 )
    v19 = 0;
  v172 = v19;
  v148 = 0;
  v173 = 0;
  v20 = a4 & 0x80;
  v155 = v20;
  v21 = a4 & 0x400;
  v22 = a4 & 0x800;
  v151 = v22;
  if ( v20 || v21 || v22 )
  {
    v150 = 0;
    if ( v22 || v21 )
    {
      v170 = 0;
      goto LABEL_16;
    }
  }
  else
  {
    v150 = 1;
  }
  v170 = a11;
LABEL_16:
  (*(void (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
  UMSEnterCSWraper(a1 + 27);
  if ( !a5 && !v20 && !v21 && !v22 )
  {
    v23 = v14 & 0x10;
    if ( v23 || v168 )
    {
      v24 = 0;
      v145 = 0;
      goto LABEL_23;
    }
    v14 = a3;
  }
  v24 = 1;
  v145 = 1;
  v23 = v14 & 0x10;
  if ( v20 && (unsigned int)CContext::ArgFailed((CContext *)&TlsValue, (a3 & 0x60) == 0) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_403;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
      bidTraceW(off_18012A1E0[0], 3263497, L"<CQuery::Execute|ADO|ERR> %u#, line %d\n", BidObjectID, 3187);
      goto LABEL_403;
    }
    v27 = 3187;
    v28 = 3263497;
    goto LABEL_402;
  }
LABEL_23:
  if ( *((_BYTE *)v17 + 544) )
  {
    v152 = -2146824577;
    if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v152) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_403;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
      {
        v25 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
        bidTraceW(off_18012A1E0[0], 3268617, L"<CQuery::Execute|ADO|ERR> %u#, line %d\n", v25, 3192);
        goto LABEL_403;
      }
      v27 = 3192;
      v28 = 3268617;
LABEL_402:
      bidTraceW(off_18012A1E0[0], v28, L"<CQuery::Execute|ADO|ERR>  line %d\n", v27);
      goto LABEL_403;
    }
  }
  *((_DWORD *)v17 + 34) = 0;
  if ( v23 )
  {
    LODWORD(v169) = 0;
    v152 = 0;
    if ( (*(int (__fastcall **)(CConnection *, const GUID *, __int64, __int64 *, int *))(*(_QWORD *)v172 + 384LL))(
           v172,
           &DBPROPSET_DATASOURCEINFO,
           169,
           &v169,
           &v152) < 0
      || (v152 & 1) == 0 )
    {
      v154 = -2146825037;
      if ( (unsigned int)CContext::FailedDescription((CContext *)&TlsValue, &v154, 0x2725u) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_403;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
        {
          v29 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
          dwCreationFlags[0] = 3207;
          bidTraceW(
            off_18012A1E0[0],
            3283977,
            L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
            v29,
            *(_QWORD *)dwCreationFlags);
          goto LABEL_403;
        }
        v27 = 3207;
        v28 = 3283977;
        goto LABEL_402;
      }
    }
  }
  if ( *((_QWORD *)g_pStaticGlobals + 3) && (*((_DWORD *)v17 + 56) == 4 || *((_BYTE *)v17 + 547)) )
  {
    CVar::CVar((CVar *)&v177, 0, 0);
    CConnection::StartDebugging(v172, v23 != 0, (_DWORD)v17 + 546);
    CVar::UpdateVariant((CVar *)&v177);
    CQuery::SetProperty((CQuery *)a1, &DBPROPSET_ROWSET, 0x22u, 0, (struct tagVARIANT *)&v177.guidPropertySet.Data2, 0);
    *((_BYTE *)v17 + 546) = 1;
    v177.rgProperties = (DBPROP *)&CVar::`vftable';
    CVar::Clear((CVar *)&v177);
  }
  if ( !v24 )
  {
    ParameterBuffer = CQuery::Clone((CQuery *)a1);
    if ( ParameterBuffer < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_403;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
      {
        v30 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
        dwCreationFlags[0] = 3245;
        bidTraceW(
          off_18012A1E0[0],
          3322889,
          L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
          v30,
          *(_QWORD *)dwCreationFlags);
        goto LABEL_403;
      }
      v27 = 3245;
      v28 = 3322889;
      goto LABEL_402;
    }
  }
  v31 = *((_DWORD *)a1 + 46);
  if ( v31 )
  {
    v32 = (char *)a1[24];
    pv = v32;
    for ( i = 0; i < v31; ++i )
    {
      v34 = &v32[32 * i];
      if ( *((_DWORD *)v34 + 2) )
      {
        v35 = 0;
        do
          VariantClear((VARIANTARG *)(*(_QWORD *)v34 + 8 * (9LL * v35++ + 6)));
        while ( v35 < *((_DWORD *)v34 + 2) );
        CoTaskMemFree(*(LPVOID *)v34);
        v32 = (char *)pv;
      }
    }
    v22 = v151;
    v20 = v155;
    v17 = v175;
    CoTaskMemFree(v32);
  }
  *((_DWORD *)a1 + 46) = 0;
  a1[24] = 0;
  if ( !v145 )
    *((_DWORD *)a1 + 50) = 1;
  v36 = a1[19];
  if ( v36 )
  {
    v37 = *(__int64 **)(v36 + 88);
    if ( v37 )
    {
      if ( *(_DWORD *)(v36 + 84) )
      {
        v38 = 0;
        v154 = 0;
        do
        {
          v39 = 4LL * v38;
          if ( LODWORD(v37[v39 + 1]) )
          {
            v40 = 0;
            do
            {
              VariantClear((VARIANTARG *)(v37[v39] + 8 * (9LL * v40++ + 6)));
              v37 = *(__int64 **)(v36 + 88);
            }
            while ( v40 < LODWORD(v37[v39 + 1]) );
            v38 = v154;
          }
          v154 = ++v38;
        }
        while ( v38 < *(_DWORD *)(v36 + 84) );
        v22 = v151;
        v17 = v175;
      }
      v41 = *v37;
      if ( v41 )
        MpHeapFree(g_hHeapHandle, v41);
      v42 = *(_QWORD *)(v36 + 88);
      if ( v42 )
        MpHeapFree(g_hHeapHandle, v42);
      *(_QWORD *)(v36 + 88) = 0;
      *(_DWORD *)(v36 + 84) = 0;
    }
    v43 = *(CParamBuffer **)(v36 + 8);
    if ( v43 )
      CParamBuffer::Release(v43);
    *(_OWORD *)v36 = 0;
    *(_OWORD *)(v36 + 16) = 0;
    *(_OWORD *)(v36 + 32) = 0;
    *(_OWORD *)(v36 + 48) = 0;
    *(_OWORD *)(v36 + 64) = 0;
    *(_OWORD *)(v36 + 80) = 0;
    *(_OWORD *)(v36 + 96) = 0;
    *(_DWORD *)(v36 + 56) = 2;
    v169 = -1;
    *(_QWORD *)(v36 + 48) = -1;
  }
  else
  {
    v47 = (CExecInfo *)MpHeapAlloc(g_hHeapHandle, 10485760, 112);
    v48 = v47;
    pv = v47;
    if ( v47 )
    {
      memset_0(v47, 0, 0x70u);
      CExecInfo::Term(v48);
      memset_0(v48, 0, 0x70u);
      *((_DWORD *)v48 + 14) = 2;
      v169 = -1;
      *((_QWORD *)v48 + 6) = -1;
      a1[19] = v48;
    }
    else
    {
      a1[19] = 0;
      v169 = -1;
      v155 = -2147024882;
      if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, &v155) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
          {
            bidTraceW(off_18012A1E0[0], 3347465, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3269);
          }
          else
          {
            v49 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
            dwCreationFlags[0] = 3269;
            bidTraceW(
              off_18012A1E0[0],
              3347465,
              L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
              v49,
              *(_QWORD *)dwCreationFlags);
          }
        }
        goto LABEL_378;
      }
    }
  }
  *(_QWORD *)a1[19] = a1;
  if ( v21 )
  {
    *(_DWORD *)(a1[19] + 56LL) |= 0x100u;
    if ( v167 )
    {
      *(_QWORD *)(a1[19] + 104LL) = v167;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1[19] + 104LL) + 8LL))(*(_QWORD *)(a1[19] + 104LL));
    }
    goto LABEL_85;
  }
  if ( v22 )
  {
    *(_DWORD *)(a1[19] + 56LL) |= 0x200u;
    if ( v167 )
    {
      *(_QWORD *)(a1[19] + 96LL) = v167;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1[19] + 96LL) + 8LL))(*(_QWORD *)(a1[19] + 96LL));
    }
    v155 = CQuery::SetProperties(
             (CQuery *)a1,
             a6,
             a7,
             0,
             0,
             v145,
             (enum CursorLocationEnum)-1,
             (unsigned int *)(a1[19] + 84LL),
             (struct tagDBPROPSET **)(a1[19] + 88LL),
             1);
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v155) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
        {
          v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
          dwCreationFlags[0] = 3301;
          v46 = 3380233;
          goto LABEL_103;
        }
        v52 = 3301;
        v53 = 3380233;
LABEL_107:
        bidTraceW(off_18012A1E0[0], v53, L"<CQuery::Execute|ADO|ERR>  line %d\n", v52);
        v50 = 0;
        v51 = a13;
        goto LABEL_370;
      }
LABEL_104:
      v50 = 0;
LABEL_105:
      v51 = a13;
      goto LABEL_370;
    }
LABEL_85:
    v44 = (CParameters *)(v17 + 46);
    ParameterBuffer = CParameters::SetParamInfo((CParameters *)(v17 + 46), a10, v174);
    if ( ParameterBuffer < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
        {
          v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
          dwCreationFlags[0] = 3423;
          v46 = 3505161;
LABEL_103:
          bidTraceW(off_18012A1E0[0], v46, L"<CQuery::Execute|ADO|ERR> %u#, line %d\n", v45, *(_QWORD *)dwCreationFlags);
          goto LABEL_104;
        }
        v52 = 3423;
        v53 = 3505161;
        goto LABEL_107;
      }
      goto LABEL_104;
    }
    v79 = a1[19];
    v80 = (unsigned __int64 *)(v79 + 24);
    v167 = 0;
    v81 = (*(__int64 (__fastcall **)(_QWORD *))(v17[49] + 248LL))(v17 + 49);
    v151 = v81;
    *(_BYTE *)(v79 + 16) = 0;
    *(_QWORD *)(v79 + 24) = 0;
    if ( !v81 )
    {
      Parameter = 0;
      v86 = a10;
      v85 = a10;
LABEL_224:
      *v80 = v85;
      ParameterBuffer = Parameter;
      v87 = v174;
      *(_QWORD *)(a1[19] + 32LL) = v174;
      if ( !*((_BYTE *)v17 + 216) )
      {
        v153 = CQuery::SetCommandStream((CQuery *)a1);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v153) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_104;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
          {
            v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
            dwCreationFlags[0] = 3440;
            v46 = 3522569;
            goto LABEL_103;
          }
          v52 = 3440;
          v53 = 3522569;
          goto LABEL_107;
        }
        goto LABEL_301;
      }
      v88 = *((_DWORD *)v17 + 56);
      v89 = 0;
      v165 = 0;
      v90 = 7;
      v166 = 7;
      v91 = a1[17];
      if ( v88 == 2 )
      {
        SysFreeString(0);
        v89 = SysAllocString(L"select * from ");
        v165 = v89;
        if ( v89 )
          v90 = 7;
        else
          v90 = 3;
        v166 = v90;
        if ( (*(_BYTE *)(v91 + 184) & 4) != 0 )
        {
          v104 = *(OLECHAR **)(v91 + 176);
          if ( v104 )
          {
            v105 = SysStringLen(v104);
            v153 = v105;
            if ( v89 )
              v106 = SysStringLen(v89);
            else
              v106 = 0;
            v151 = v106;
            v107 = SysAllocStringLen(0, v105 + v106);
            if ( v107 )
            {
              v108 = (void *)(2LL * v151);
              pv = v108;
              if ( v151 > 0 )
              {
                memcpy_0(v107, v89, 2LL * v151);
                v108 = pv;
              }
              if ( (*(_BYTE *)(v91 + 184) & 4) != 0 )
                v109 = *(const void **)(v91 + 176);
              else
                v109 = 0;
              memcpy_0((char *)v107 + (_QWORD)v108, v109, 2LL * v153);
              SysFreeString(v89);
              v89 = v107;
              v165 = v107;
            }
            else
            {
              v90 &= ~4u;
              v166 = v90;
            }
          }
        }
        if ( (v90 & 4) != 0 )
          goto LABEL_263;
      }
      else
      {
        v92 = v88 - 1;
        if ( !v92 )
        {
LABEL_230:
          v95 = v91 + 176;
          if ( (OLECHAR **)v95 != &v165 && *(_QWORD *)v95 )
          {
            SysFreeString(0);
            if ( (*(_BYTE *)(v95 + 8) & 4) != 0 && *(_QWORD *)v95 )
            {
              v96 = SysStringLen(*(BSTR *)v95);
              if ( (*(_BYTE *)(v95 + 8) & 4) != 0 )
                v97 = *(const OLECHAR **)v95;
              else
                v97 = 0;
              v89 = SysAllocStringLen(v97, v96);
              v165 = v89;
              if ( v89 )
              {
                v90 = 7;
                v166 = 7;
              }
              else
              {
                v90 = 3;
                v166 = 3;
              }
            }
            else
            {
              v89 = 0;
              v165 = 0;
            }
          }
          StoredProc = -2147024882;
          if ( (v90 & 4) != 0 )
            StoredProc = 0;
LABEL_262:
          if ( StoredProc >= 0 )
          {
LABEL_263:
            v103 = 0;
            if ( (v90 & 4) != 0 )
              v103 = v89;
            StoredProc = CQuery::SetSQL((CQuery *)a1, v103);
            goto LABEL_266;
          }
LABEL_290:
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
            {
              dwCreationFlags[0] = 4298;
              bidTraceW(
                off_18012A1E0[0],
                4401161,
                L"<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)StoredProc,
                *(_QWORD *)dwCreationFlags);
            }
            else
            {
              v110 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
              LODWORD(lpThreadId) = 4298;
              dwCreationFlags[0] = StoredProc;
              bidTraceW(
                off_18012A1E0[0],
                4401161,
                L"<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v110,
                *(_QWORD *)dwCreationFlags,
                lpThreadId);
            }
          }
          goto LABEL_266;
        }
        v93 = v92 - 3;
        if ( v93 )
        {
          v94 = v93 - 4;
          if ( v94 && v94 != 504 )
            goto LABEL_263;
          goto LABEL_230;
        }
        v98 = a1[19];
        v147 = *(_BYTE *)(v98 + 16);
        pv = *(LPVOID *)(v98 + 24);
        StoredProc = 0;
        v151 = 256;
        v152 = 0;
        Connection = CCommand::GetConnection((CCommand *)v91);
        if ( Connection )
        {
          v101 = (*(__int64 (__fastcall **)(struct _ADOConnection *, const GUID *, __int64, int *, int *))(*(_QWORD *)Connection + 384LL))(
                   Connection,
                   &DBPROPSET_DATASOURCEINFO,
                   109,
                   &v152,
                   &v151);
          StoredProc = v101;
          if ( v101 < 0 )
          {
            if ( v101 != -2147217887 || v152 != 1 )
            {
              if ( (bidGblFlags & 2) == 0 )
              {
LABEL_266:
                if ( (v90 & 2) != 0 )
                  SysFreeString(v89);
                ParameterBuffer = StoredProc;
                if ( StoredProc < 0 )
                {
                  CContext::PushError((CContext *)&TlsValue);
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_104;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
                  {
                    v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                    dwCreationFlags[0] = 3435;
                    v46 = 3517449;
                    goto LABEL_103;
                  }
                  v52 = 3435;
                  v53 = 3517449;
                  goto LABEL_107;
                }
                v44 = (CParameters *)(v17 + 46);
                v86 = a10;
                v87 = v174;
LABEL_301:
                ParameterBuffer = CParameters::SetTypeInfo(v44);
                if ( ParameterBuffer < 0 )
                {
                  CContext::PushError((CContext *)&TlsValue);
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_104;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
                  {
                    v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                    dwCreationFlags[0] = 3444;
                    v46 = 3526665;
                    goto LABEL_103;
                  }
                  v52 = 3444;
                  v53 = 3526665;
                  goto LABEL_107;
                }
                if ( *((_BYTE *)v17 + 218) )
                {
                  v153 = CQuery::Prepare((CQuery *)a1, 1u);
                  if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v153) )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_104;
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
                    {
                      v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                      dwCreationFlags[0] = 3449;
                      v46 = 3531785;
                      goto LABEL_103;
                    }
                    v52 = 3449;
                    v53 = 3531785;
                    goto LABEL_107;
                  }
                }
                ParameterBuffer = CParameters::GetParameterBuffer(v44, v86, v87, (struct CParamBuffer **)(a1[19] + 8LL));
                if ( ParameterBuffer < 0 )
                {
                  CContext::PushError((CContext *)&TlsValue);
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_104;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
                  {
                    v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                    dwCreationFlags[0] = 3459;
                    v46 = 3542025;
                    goto LABEL_103;
                  }
                  v52 = 3459;
                  v53 = 3542025;
                  goto LABEL_107;
                }
                if ( a13 && v150 )
                {
                  ParameterBuffer = CConnection::GetRecordset(v172, 0, v111, v170, &v173);
                  if ( ParameterBuffer < 0 )
                  {
                    CContext::PushError((CContext *)&TlsValue);
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
                      {
                        v112 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                        dwCreationFlags[0] = 3471;
                        bidTraceW(
                          off_18012A1E0[0],
                          3554313,
                          L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                          v112,
                          *(_QWORD *)dwCreationFlags);
                        v113 = v173;
                        v50 = 0;
                        v51 = a13;
                        goto LABEL_371;
                      }
                      bidTraceW(off_18012A1E0[0], 3554313, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3471);
                    }
                    v113 = v173;
                    v50 = 0;
                    goto LABEL_325;
                  }
                  v113 = v173;
                  v148 = v173;
                  if ( (_DWORD)v169 != -1 )
                    *((_DWORD *)v173 + 177) = v169;
                  if ( v168 == 2 )
                    *((_BYTE *)v113 + 1432) = 0;
                  *(_QWORD *)(a1[19] + 40LL) = v113;
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1[19] + 40LL) + 8LL))(*(_QWORD *)(a1[19] + 40LL));
                  *a13 = 0;
                }
                else
                {
                  v113 = 0;
                }
                *(_DWORD *)(a1[19] + 68LL) = v168;
                v114 = v17[14];
                if ( v114 )
                  UMSEnterCSWraper(v114 + 8);
                if ( (bidGblFlags & 2) != 0 && off_18012A500[0] )
                {
                  v115 = *((char *)v17 + 544);
                  v116 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 18));
                  LODWORD(lpThreadId) = 1;
                  dwCreationFlags[0] = v115;
                  bidTraceW(off_18012A1E0[0], 2300928, off_18012A500[0], v116, *(_QWORD *)dwCreationFlags, lpThreadId);
                  v113 = v148;
                }
                *((_BYTE *)v17 + 544) = 1;
                v117 = v17[14];
                if ( v117 )
                {
                  v118 = *(_QWORD *)(v117 + 8);
                  --*(_DWORD *)(v118 + 48);
                  LeaveCriticalSection((LPCRITICAL_SECTION)(v118 + 8));
                }
                v119 = (_QWORD *)a1[19];
                v120 = v119[5];
                if ( v120 )
                  *(_BYTE *)(v120 + 1505) = 1;
                v121 = v119[12];
                if ( v121 )
                  *(_BYTE *)(v121 + 572) = 1;
                v122 = v119[13];
                if ( v122 )
                  *(_BYTE *)(v122 + 236) = 1;
                v123 = *(_QWORD *)(a1[19] + 40LL);
                if ( v123 && (a3 & 0x60) != 0 )
                  *(_BYTE *)(v123 + 1504) = 1;
                (*(void (__fastcall **)(_QWORD *))(*v17 + 8LL))(v17);
                v50 = 1;
                if ( v23 )
                {
                  *(_BYTE *)(a1[19] + 80LL) = 1;
                  v124 = (void *)_InterlockedExchange64(a1 + 20, 0);
                  if ( v124 )
                    CloseHandle(v124);
                  Thread = CreateThread(0, 0, ExecuteAsync, (LPVOID)a1[19], 0, (LPDWORD)a1 + 42);
                  a1[20] = Thread;
                  if ( !Thread )
                  {
                    CCommand::SetExecState((CCommand *)v17, 0);
                    SetExecuteState(a1[19], 0);
                    ReleaseObjects(a1[19]);
                    (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
                    v153 = -2147467259;
                    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v153) )
                    {
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
                        {
                          bidTraceW(off_18012A1E0[0], 3613705, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3529);
                        }
                        else
                        {
                          v126 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                          dwCreationFlags[0] = 3529;
                          bidTraceW(
                            off_18012A1E0[0],
                            3613705,
                            L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                            v126,
                            *(_QWORD *)dwCreationFlags);
                        }
                        goto LABEL_105;
                      }
LABEL_325:
                      v51 = a13;
                      goto LABEL_371;
                    }
                  }
                  *((_BYTE *)TlsValue + 28) = 0;
                  *v176 = *(_QWORD *)(a1[19] + 48LL);
                  v51 = a13;
LABEL_384:
                  a1[22] = v113;
                  ParameterBuffer = CParameters::SetOutputParamValuesArray(v44, 0, v86, v174);
                  if ( ParameterBuffer >= 0 || (CContext::PushError((CContext *)&TlsValue), (bidGblFlags & 2) == 0) )
                  {
LABEL_371:
                    if ( ParameterBuffer >= 0 )
                    {
                      if ( v51 && v150 )
                      {
                        *v51 = v113;
LABEL_378:
                        if ( !*((_BYTE *)a1 + 173) )
                        {
                          FreeDbPropSet(*((_DWORD *)a1 + 46), (struct tagDBPROPSET *)a1[24], 1);
                          *((_DWORD *)a1 + 46) = 0;
                          a1[24] = 0;
                        }
                        goto LABEL_403;
                      }
                    }
                    else
                    {
                      if ( !v50 )
                      {
                        CCommand::SetExecState((CCommand *)v17, 0);
                        SetExecuteState(a1[19], 0);
                        ReleaseObjects(a1[19]);
                      }
                      if ( !v113 )
                        goto LABEL_378;
                      *((_BYTE *)v113 + 1504) = 0;
                    }
                    if ( v113 )
                      (*(void (__fastcall **)(struct _ADORecordset *))(*(_QWORD *)v113 + 16LL))(v113);
                    goto LABEL_378;
                  }
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
                  {
                    bidTraceW(off_18012A1E0[0], 3669001, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3583);
                  }
                  else
                  {
                    v134 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                    dwCreationFlags[0] = 3583;
                    bidTraceW(
                      off_18012A1E0[0],
                      3669001,
                      L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                      v134,
                      *(_QWORD *)dwCreationFlags);
                  }
LABEL_370:
                  v113 = v148;
                  goto LABEL_371;
                }
                *((_BYTE *)TlsValue + 28) = 0;
                v127 = (struct CExecInfo *)a1[19];
                v128 = *(CCommand **)(*(_QWORD *)v127 + 136LL);
                v129 = 0;
                if ( *((_BYTE *)v127 + 80) )
                {
                  v130 = CoInitialize(0);
                  if ( v130 < 0 )
                  {
                    SetExecuteState(v127, 0);
                    CCommand::SetExecState(v128, v131);
                    ReleaseObjects(v127);
                    (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v128 + 16LL))(v128);
                    ParameterBuffer = v130;
                    goto LABEL_365;
                  }
                  v129 = 1;
                }
                v132 = _ExecuteAsync(v127);
                (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v128 + 16LL))(v128);
                if ( v129 )
                  CoUninitialize();
                ParameterBuffer = v132;
                if ( v132 >= 0 )
                {
                  *((_BYTE *)a1 + 173) = 1;
                  *v176 = *(_QWORD *)(a1[19] + 48LL);
                  v51 = a13;
                  if ( a13 && v150 )
                  {
                    v113 = v148;
                    v86 = a10;
                    v50 = 1;
                    goto LABEL_384;
                  }
                  *((_BYTE *)a1 + 173) = 0;
                  v153 = CParameters::SetOutputParamValuesArray(v44, 1, a10, v174);
                  if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v153) && (bidGblFlags & 2) != 0 )
                  {
                    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
                    {
                      bidTraceW(off_18012A1E0[0], 3659785, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3574);
                    }
                    else
                    {
                      v135 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                      dwCreationFlags[0] = 3574;
                      bidTraceW(
                        off_18012A1E0[0],
                        3659785,
                        L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                        v135,
                        *(_QWORD *)dwCreationFlags);
                    }
                  }
LABEL_369:
                  v50 = 1;
                  goto LABEL_370;
                }
LABEL_365:
                CContext::PushError((CContext *)&TlsValue);
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) == -1 )
                  {
                    bidTraceW(off_18012A1E0[0], 3627017, L"<CQuery::Execute|ADO|ERR>  line %d\n", 3542);
                  }
                  else
                  {
                    v133 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                    dwCreationFlags[0] = 3542;
                    bidTraceW(
                      off_18012A1E0[0],
                      3627017,
                      L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                      v133,
                      *(_QWORD *)dwCreationFlags);
                  }
                }
                v51 = a13;
                goto LABEL_369;
              }
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v91 + 144)) == -1 )
              {
                bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR>  line %d\n", 1220);
              }
              else
              {
                v102 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v91 + 144));
                dwCreationFlags[0] = 1220;
                bidTraceW(
                  off_18012A1E0[0],
                  1249289,
                  L"<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n",
                  v102,
                  *(_QWORD *)dwCreationFlags);
              }
              goto LABEL_290;
            }
            goto LABEL_253;
          }
        }
        if ( v152 == 1 || (v151 & 0x100) != 0 )
        {
LABEL_253:
          StoredProc = CCommand::GetStoredProc((CCommand *)v91, (unsigned __int64)pv, v147, (struct CSysString *)&v165);
          v90 = v166;
LABEL_254:
          v89 = v165;
          goto LABEL_262;
        }
        if ( v151 )
        {
          CSysString::operator=(&v165, L"exec ");
          CSysString::operator+=(&v165, v91 + 176);
        }
        else
        {
          CSysString::operator=(&v165, v91 + 176);
        }
        v90 = v166;
        if ( (v166 & 4) != 0 )
          goto LABEL_254;
        if ( (bidGblFlags & 2) != 0 )
        {
          dwCreationFlags[0] = 1238;
          bidTraceW(
            off_18012A1E0[0],
            1267721,
            L"<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2147942414LL,
            *(_QWORD *)dwCreationFlags);
        }
        v89 = v165;
      }
      StoredProc = -2147024882;
      goto LABEL_290;
    }
    if ( a10 > v81 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60)) != -1 )
        {
          v82 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60));
          dwCreationFlags[0] = 3265;
          bidTraceW(
            off_18012A1D0[0],
            3343369,
            L"<CParameters::GetParamInfo|ADO|ERR> %u#, line %d\n",
            v82,
            *(_QWORD *)dwCreationFlags);
          ParameterBuffer = -2146825287;
LABEL_213:
          CContext::PushError((CContext *)&TlsValue);
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_104;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
          {
            v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
            dwCreationFlags[0] = 3426;
            v46 = 3508233;
            goto LABEL_103;
          }
          v52 = 3426;
          v53 = 3508233;
          goto LABEL_107;
        }
        bidTraceW(off_18012A1D0[0], 3343369, L"<CParameters::GetParamInfo|ADO|ERR>  line %d\n", 3265);
      }
      ParameterBuffer = -2146825287;
      goto LABEL_213;
    }
    Parameter = CParameters::GetParameter((CParameters *)(v17 + 46), 0, &v167);
    if ( Parameter < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60)) == -1 )
        {
          dwCreationFlags[0] = 3269;
          bidTraceW(
            off_18012A1D0[0],
            3347465,
            L"<CParameters::GetParamInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)Parameter,
            *(_QWORD *)dwCreationFlags);
        }
        else
        {
          v84 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60));
          LODWORD(lpThreadId) = 3269;
          dwCreationFlags[0] = Parameter;
          bidTraceW(
            off_18012A1D0[0],
            3347465,
            L"<CParameters::GetParamInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v84,
            *(_QWORD *)dwCreationFlags,
            lpThreadId);
        }
      }
      ParameterBuffer = Parameter;
      goto LABEL_213;
    }
    if ( *((_DWORD *)v167 + 47) == 4 )
    {
      *(_BYTE *)(v79 + 16) = 1;
    }
    else if ( !*(_BYTE *)(v79 + 16) )
    {
      v85 = (unsigned int)v151;
      goto LABEL_222;
    }
    v85 = (unsigned int)(v151 - 1);
LABEL_222:
    v86 = a10;
    goto LABEL_224;
  }
  if ( v20 )
  {
    *(_DWORD *)(a1[19] + 56LL) |= 0x80u;
    goto LABEL_85;
  }
  if ( !v170 || (v54 = *((_DWORD *)v170 + 177), v54 == -1) )
    v54 = *((_DWORD *)v172 + 103);
  v55 = *(_QWORD *)(a1[17] + 64LL);
  if ( a1[17] + 32LL == v55 )
    v55 = 0;
  v56 = (int *)(v55 - 32);
  if ( !v55 )
    v56 = 0;
  v57 = v56[99];
  v151 = 0;
  v152 = 0;
  if ( (unsigned int)(v57 - 2) <= 1 )
  {
    if ( !v56 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
        {
          v59 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
          LODWORD(lpThreadId) = 4246;
          dwCreationFlags[0] = -2146824868;
          bidTraceW(
            off_18012A1E0[0],
            4347913,
            L"<CQuery::MultipleResultsSupported|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v59,
            *(_QWORD *)dwCreationFlags,
            lpThreadId);
          ParameterBuffer = -2146824868;
          goto LABEL_398;
        }
        dwCreationFlags[0] = 4246;
        bidTraceW(
          off_18012A1E0[0],
          4347913,
          L"<CQuery::MultipleResultsSupported|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          2148142428LL,
          *(_QWORD *)dwCreationFlags);
      }
      ParameterBuffer = -2146824868;
      goto LABEL_398;
    }
    v60 = (*(__int64 (__fastcall **)(int *, const GUID *, __int64, int *, int *))(*(_QWORD *)v56 + 384LL))(
            v56,
            &DBPROPSET_DATASOURCEINFO,
            196,
            &v152,
            &v151);
    if ( v60 >= 0 )
    {
      v58 = v151 & 1;
      goto LABEL_131;
    }
    if ( v60 == -2147217887 && v152 == 1 )
    {
      v58 = 0;
      goto LABEL_130;
    }
    ParameterBuffer = v60;
LABEL_398:
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_403;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
    {
      v136 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
      dwCreationFlags[0] = 3326;
      bidTraceW(
        off_18012A1E0[0],
        3405833,
        L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
        v136,
        *(_QWORD *)dwCreationFlags);
      goto LABEL_403;
    }
    v27 = 3326;
    v28 = 3405833;
    goto LABEL_402;
  }
  v58 = byte_180121408[16 * v57];
LABEL_130:
  v60 = 0;
LABEL_131:
  ParameterBuffer = v60;
  if ( v58 )
    *(_DWORD *)(a1[19] + 56LL) |= 4u;
  v61 = a6;
  if ( (a3 & 0x20) != 0 )
  {
    *(_DWORD *)(a1[19] + 56LL) |= 0x20u;
    v62 = 0x100000;
  }
  else
  {
    v152 = 0;
    if ( (a3 & 0x40) == 0 )
      goto LABEL_138;
    *(_DWORD *)(a1[19] + 56LL) |= 0x40u;
    v62 = 3145728;
  }
  v61 = v62 | a6;
  v152 = v62;
LABEL_138:
  v64 = (*(__int64 (__fastcall **)(_QWORD *))(v17[49] + 248LL))(v17 + 49);
  if ( !v64 )
  {
    ParameterBuffer = 0;
    v146 = a10 != 0;
LABEL_156:
    v69 = v54;
    v70 = v172;
    if ( (*((_BYTE *)v172 + 360) & 4) != 0 && !(unsigned int)CMPString::IsEmpty((CConnection *)((char *)v172 + 352)) )
    {
      if ( !_wcsnicmp(*((const wchar_t **)v70 + 44), L"MSDATASHAPE", 0xBu)
        || ((*((_BYTE *)v70 + 360) & 4) == 0 ? (v71 = 0) : (v71 = (const wchar_t *)*((_QWORD *)v70 + 44)),
            !_wcsnicmp(v71, L"MS Remote", 9u)) )
      {
        v54 = adUseServer;
      }
    }
    v72 = v170;
    if ( v170 )
    {
      *(_QWORD *)(a1[19] + 72LL) = *((_QWORD *)v170 + 245);
      v72 = v170;
    }
    if ( v54 == adUseServer || v54 == -1 )
    {
      *(_DWORD *)(a1[19] + 56LL) |= 8u;
      v72 = v170;
    }
    else if ( v54 != adUseNone )
    {
      if ( v54 == adUseClient )
      {
        *(_DWORD *)(a1[19] + 56LL) |= 1u;
        *(_DWORD *)(a1[19] + 60LL) = v61;
        *(_DWORD *)(a1[19] + 64LL) = a7;
        if ( !a5 )
        {
          v155 = CQuery::SetProperties(
                   (CQuery *)a1,
                   0x1000u,
                   0,
                   v61 & 0x1000000,
                   v146,
                   v145,
                   adUseClient,
                   (unsigned int *)(a1[19] + 84LL),
                   (struct tagDBPROPSET **)(a1[19] + 88LL),
                   0);
          if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v155) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_104;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
            {
              v73 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
              dwCreationFlags[0] = 3408;
              bidTraceW(
                off_18012A1E0[0],
                3489801,
                L"<CQuery::Execute|ADO|ERR> %u#, line %d\n",
                v73,
                *(_QWORD *)dwCreationFlags);
              v50 = 0;
              v51 = a13;
              goto LABEL_370;
            }
            v52 = 3408;
            v53 = 3489801;
            goto LABEL_107;
          }
        }
      }
LABEL_193:
      LODWORD(v169) = v69;
      if ( v153 )
      {
        v76 = CVar::CVar((CVar *)&v177, v153, v63);
        CVar::UpdateVariant(v76);
        v153 = CQuery::SetProperty((CQuery *)a1, &DBPROPSET_ROWSET, 0x49u, 0, (struct tagVARIANT *)(v77 + 16), 0);
        v78 = CContext::Failed((CContext *)&TlsValue, &v153);
        v177.rgProperties = (DBPROP *)&CVar::`vftable';
        CVar::Clear((CVar *)&v177);
        if ( v78 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_104;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
          {
            v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
            dwCreationFlags[0] = 3417;
            v46 = 3499017;
            goto LABEL_103;
          }
          v52 = 3417;
          v53 = 3499017;
          goto LABEL_107;
        }
      }
      goto LABEL_85;
    }
    if ( a5 )
    {
      if ( v72 )
      {
        if ( *((_BYTE *)v72 + 1457) )
        {
          v74 = v152;
          if ( v152 )
          {
            *((_DWORD *)&v177.guidPropertySet + 4) = 0;
            memset_0(&v178, 0, sizeof(v178));
            v177.rgProperties = &v178;
            v177.guidPropertySet = DBPROPSET_ROWSET;
            v177.cProperties = 1;
            FillDBProp(0xC9u, &v178, 0, 0, 0);
            v178.vValue.vt = 3;
            v75 = 8;
            if ( (v74 & 0x200000) != 0 )
              v75 = 14;
            v178.vValue.lVal = v75;
            v155 = CQuery::SetProperties((CQuery *)a1, 1u, 1u, &v177, 0);
            if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v155) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_104;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
              {
                v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
                dwCreationFlags[0] = 3390;
                v46 = 3471369;
                goto LABEL_103;
              }
              v52 = 3390;
              v53 = 3471369;
              goto LABEL_107;
            }
          }
        }
      }
    }
    else
    {
      ParameterBuffer = CQuery::SetProperties(
                          (CQuery *)a1,
                          v61,
                          a7,
                          0,
                          v146,
                          v145,
                          v54,
                          (unsigned int *)(a1[19] + 84LL),
                          (struct tagDBPROPSET **)(a1[19] + 88LL),
                          0);
      if ( ParameterBuffer < 0 )
      {
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_104;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
        {
          v45 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
          dwCreationFlags[0] = 3373;
          v46 = 3453961;
          goto LABEL_103;
        }
        v52 = 3373;
        v53 = 3453961;
        goto LABEL_107;
      }
    }
    goto LABEL_193;
  }
  v65 = 0;
  v167 = 0;
  v146 = 1;
  for ( j = 0; ; j = v151 + 1 )
  {
    v151 = j;
    if ( j >= v64 )
      goto LABEL_145;
    v65 = CParameters::GetParameter((CParameters *)(v17 + 46), j, &v167);
    v154 = v65;
    if ( v65 < 0 )
      break;
    if ( !*((_BYTE *)v167 + 224) )
    {
      v146 = 0;
LABEL_145:
      ParameterBuffer = v65;
      goto LABEL_156;
    }
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60)) == -1 )
    {
      dwCreationFlags[0] = 3103;
      bidTraceW(
        off_18012A1D0[0],
        3177481,
        L"<CParameters::IsTypeInfoOverridden|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)v154,
        *(_QWORD *)dwCreationFlags);
    }
    else
    {
      v67 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v17 + 60));
      LODWORD(lpThreadId) = 3103;
      dwCreationFlags[0] = v154;
      bidTraceW(
        off_18012A1D0[0],
        3177481,
        L"<CParameters::IsTypeInfoOverridden|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v67,
        *(_QWORD *)dwCreationFlags,
        lpThreadId);
    }
    v65 = v154;
  }
  ParameterBuffer = v65;
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8)) != -1 )
    {
      v68 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 8));
      dwCreationFlags[0] = 3345;
      bidTraceW(off_18012A1E0[0], 3425289, L"<CQuery::Execute|ADO|ERR> %u#, line %d\n", v68, *(_QWORD *)dwCreationFlags);
      goto LABEL_403;
    }
    v27 = 3345;
    v28 = 3425289;
    goto LABEL_402;
  }
LABEL_403:
  v137 = a1[27];
  --*(_DWORD *)(v137 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v137 + 8));
  (*(void (__fastcall **)(_QWORD *))(*a1 + 88LL))(a1);
  v138 = ParameterBuffer;
  if ( TlsValue[2]-- == 1 )
  {
    v140 = TlsValue;
    v141 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v141 )
    {
      SetErrorInfo(0, v141);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v140 = TlsValue;
    }
    if ( *((_BYTE *)v140 + 30) )
    {
      *((_QWORD *)v140 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v138;
}

```

## disassembly

```asm
0x1800145d0  push    rbp
0x1800145d2  push    rbx
0x1800145d3  push    rsi
0x1800145d4  push    rdi
0x1800145d5  push    r12
0x1800145d7  push    r13
0x1800145d9  push    r14
0x1800145db  push    r15
0x1800145dd  lea     rbp, [rsp-0B8h]
0x1800145e5  sub     rsp, 1B8h
0x1800145ec  mov     rax, cs:__security_cookie
0x1800145f3  xor     rax, rsp
0x1800145f6  mov     [rbp+0F0h+var_50], rax
0x1800145fd  mov     edi, r9d
0x180014600  movzx   r13d, r8b
0x180014604  mov     [rsp+1F0h+var_190], r8b
0x180014609  mov     [rbp+0F0h+var_118], edx
0x18001460c  mov     rbx, rcx
0x18001460f  mov     eax, [rbp+0F0h+arg_38]
0x180014615  mov     [rbp+0F0h+var_170], eax
0x180014618  mov     rax, [rbp+0F0h+arg_40]
0x18001461f  mov     [rbp+0F0h+var_E8], rax
0x180014623  mov     rsi, [rbp+0F0h+arg_50]
0x18001462a  mov     [rbp+0F0h+var_120], rsi
0x18001462e  mov     rax, [rbp+0F0h+arg_58]
0x180014635  mov     [rbp+0F0h+var_D8], rax
0x180014639  mov     rax, [rbp+0F0h+arg_60]
0x180014640  mov     [rsp+1F0h+var_188], rax
0x180014645  mov     [rbp+0F0h+var_140], rcx
0x180014649  xor     r14d, r14d
0x18001464c  mov     [rbp+0F0h+var_134], r14d
0x180014650  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180014657  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001465a  call    cs:__imp_TlsGetValue
0x180014661  nop     dword ptr [rax+rax+00h]
0x180014666  mov     [rbp+0F0h+TlsValue], rax
0x18001466a  mov     [rbp+0F0h+var_138], r14d
0x18001466e  test    rax, rax
0x180014671  jz      short loc_180014678
0x180014673  inc     dword ptr [rax+8]
0x180014676  jmp     short loc_1800146B2
0x180014678  mov     [rbp+0F0h+var_158], 1
0x18001467f  mov     [rbp+0F0h+var_150], r14
0x180014683  mov     [rbp+0F0h+var_148], r14d
0x180014687  mov     [rbp+0F0h+var_144], r14w
0x18001468c  mov     [rbp+0F0h+var_142], r14b
0x180014690  lea     rdx, [rbp+0F0h+TlsValue]; lpTlsValue
0x180014694  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001469b  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001469e  call    cs:__imp_TlsSetValue
0x1800146a5  nop     dword ptr [rax+rax+00h]
0x1800146aa  lea     rax, [rbp+0F0h+TlsValue]
0x1800146ae  mov     [rbp+0F0h+TlsValue], rax
0x1800146b2  mov     r15, [rbx+88h]
0x1800146b9  mov     [rbp+0F0h+var_E0], r15
0x1800146bd  mov     rcx, [rbx+20h]
0x1800146c1  cmp     rbx, rcx
0x1800146c4  cmovz   rcx, r14
0x1800146c8  lea     rdx, [rcx-20h]
0x1800146cc  test    rcx, rcx
0x1800146cf  cmovz   rdx, r14
0x1800146d3  mov     [rbp+0F0h+var_F8], rdx
0x1800146d7  mov     rax, r14
0x1800146da  mov     [rsp+1F0h+var_198], rax
0x1800146df  mov     [rbp+0F0h+var_F0], rax
0x1800146e3  mov     r14d, edi
0x1800146e6  and     r14d, 80h
0x1800146ed  mov     [rbp+0F0h+var_168], r14d
0x1800146f1  mov     r12d, edi
0x1800146f4  and     r12d, 400h
0x1800146fb  and     edi, 800h
0x180014701  mov     [rsp+1F0h+var_180], edi
0x180014705  test    r14d, r14d
0x180014708  jnz     short loc_18001471A
0x18001470a  test    r12d, r12d
0x18001470d  jnz     short loc_18001471A
0x18001470f  test    edi, edi
0x180014711  jnz     short loc_18001471A
0x180014713  mov     [rsp+1F0h+var_18F], 1
0x180014718  jmp     short loc_180014727
0x18001471a  mov     [rsp+1F0h+var_18F], al
0x18001471e  test    edi, edi
0x180014720  jnz     short loc_18001472D
0x180014722  test    r12d, r12d
0x180014725  jnz     short loc_18001472D
0x180014727  mov     [rbp+0F0h+var_108], rsi
0x18001472b  jmp     short loc_180014731
0x18001472d  mov     [rbp+0F0h+var_108], rax
0x180014731  mov     rax, [rbx]
0x180014734  mov     rcx, rbx
0x180014737  mov     rax, [rax+50h]
0x18001473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014740  lea     rcx, [rbx+0D8h]
0x180014747  call    cs:__imp_UMSEnterCSWraper
0x18001474e  nop     dword ptr [rax+rax+00h]
0x180014753  cmp     [rbp+0F0h+arg_20], 0
0x18001475a  jnz     loc_180014813
0x180014760  test    r14d, r14d
0x180014763  jnz     loc_180014813
0x180014769  test    r12d, r12d
0x18001476c  jnz     loc_180014813
0x180014772  test    edi, edi
0x180014774  jnz     loc_180014813
0x18001477a  and     r13b, 10h
0x18001477e  jnz     short loc_180014789
0x180014780  cmp     [rbp+0F0h+var_118], edi
0x180014783  jz      loc_18001480D
0x180014789  xor     sil, sil
0x18001478c  mov     [rsp+1F0h+var_1A0], sil
0x180014791  cmp     byte ptr [r15+220h], 0
0x180014799  jz      loc_1800148B2
0x18001479f  mov     [rsp+1F0h+var_178], 800A0E7Fh
0x1800147a7  lea     rdx, [rsp+1F0h+var_178]; int *
0x1800147ac  lea     rcx, [rbp+0F0h+TlsValue]; this
0x1800147b0  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800147b5  test    eax, eax
0x1800147b7  jz      loc_1800148B2
0x1800147bd  test    byte ptr cs:_bidGblFlags, 2
0x1800147c4  jz      loc_180016666
0x1800147ca  lea     rcx, [rbx+40h]; this
0x1800147ce  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800147d3  cmp     eax, 0FFFFFFFFh
0x1800147d6  jz      loc_1800148A2
0x1800147dc  lea     rcx, [rbx+40h]; this
0x1800147e0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800147e5  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800147ec  mov     [rsp+1F0h+dwCreationFlags], 0C78h
0x1800147f4  mov     r9d, eax
0x1800147f7  lea     r8, aCqueryExecuteA_0; "<CQuery::Execute|ADO|ERR> %u#, line %d"...
0x1800147fe  mov     edx, 31E009h
0x180014803  call    _bidTraceW
0x180014808  jmp     loc_180016666
0x18001480d  movzx   r13d, [rsp+1F0h+var_190]
0x180014813  mov     sil, 1
0x180014816  mov     [rsp+1F0h+var_1A0], sil
0x18001481b  and     r13b, 10h
0x18001481f  test    r14d, r14d
0x180014822  jz      loc_180014791
0x180014828  test    [rsp+1F0h+var_190], 60h
0x18001482d  mov     edx, 0
0x180014832  setz    dl; int
0x180014835  lea     rcx, [rbp+0F0h+TlsValue]; this
0x180014839  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x18001483e  test    eax, eax
0x180014840  jz      loc_180014791
0x180014846  test    byte ptr cs:_bidGblFlags, 2
0x18001484d  jz      loc_180016666
0x180014853  lea     rcx, [rbx+40h]; this
0x180014857  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001485c  cmp     eax, 0FFFFFFFFh
0x18001485f  jz      short loc_180014892
0x180014861  lea     rcx, [rbx+40h]; this
0x180014865  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001486a  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180014871  mov     [rsp+1F0h+dwCreationFlags], 0C73h
0x180014879  mov     r9d, eax
0x18001487c  lea     r8, aCqueryExecuteA_0; "<CQuery::Execute|ADO|ERR> %u#, line %d"...
0x180014883  mov     edx, 31CC09h
0x180014888  call    _bidTraceW
0x18001488d  jmp     loc_180016666
0x180014892  mov     r9d, 0C73h
0x180014898  mov     edx, 31CC09h
0x18001489d  jmp     loc_180016653
0x1800148a2  mov     r9d, 0C78h
0x1800148a8  mov     edx, 31E009h
0x1800148ad  jmp     loc_180016653
0x1800148b2  xor     r8d, r8d
0x1800148b5  mov     [r15+88h], r8d
0x1800148bc  test    r13b, r13b
0x1800148bf  jz      loc_180014984
0x1800148c5  mov     dword ptr [rbp+0F0h+var_110], r8d
0x1800148c9  mov     [rsp+1F0h+var_178], r8d
0x1800148ce  mov     rcx, [rbp+0F0h+var_F8]
0x1800148d2  mov     rax, [rcx]
0x1800148d5  lea     rdx, [rsp+1F0h+var_178]
0x1800148da  mov     qword ptr [rsp+1F0h+dwCreationFlags], rdx
0x1800148df  lea     r9, [rbp+0F0h+var_110]
0x1800148e3  mov     r8d, 0A9h
0x1800148e9  lea     rdx, DBPROPSET_DATASOURCEINFO
0x1800148f0  mov     rax, [rax+180h]
0x1800148f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148fc  test    eax, eax
0x1800148fe  js      short loc_180014907
0x180014900  test    byte ptr [rsp+1F0h+var_178], 1
0x180014905  jnz     short loc_180014981
0x180014907  mov     [rbp+0F0h+var_16C], 800A0CB3h
0x18001490e  mov     r8d, 2725h; unsigned int
0x180014914  lea     rdx, [rbp+0F0h+var_16C]; int *
0x180014918  lea     rcx, [rbp+0F0h+TlsValue]; this
0x18001491c  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x180014921  test    eax, eax
0x180014923  jz      short loc_180014981
0x180014925  test    byte ptr cs:_bidGblFlags, 2
0x18001492c  jz      loc_180016666
0x180014932  lea     rcx, [rbx+40h]; this
0x180014936  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001493b  cmp     eax, 0FFFFFFFFh
0x18001493e  jz      short loc_180014971
0x180014940  lea     rcx, [rbx+40h]; this
0x180014944  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014949  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180014950  mov     [rsp+1F0h+dwCreationFlags], 0C87h
0x180014958  mov     r9d, eax
0x18001495b  lea     r8, aCqueryExecuteA_0; "<CQuery::Execute|ADO|ERR> %u#, line %d"...
0x180014962  mov     edx, 321C09h
0x180014967  call    _bidTraceW
0x18001496c  jmp     loc_180016666
0x180014971  mov     r9d, 0C87h
0x180014977  mov     edx, 321C09h
0x18001497c  jmp     loc_180016653
0x180014981  xor     r8d, r8d; unsigned __int8
0x180014984  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001498b  cmp     qword ptr [rax+18h], 0
0x180014990  jz      loc_180014A1E
0x180014996  cmp     dword ptr [r15+0E0h], 4
0x18001499e  jz      short loc_1800149AA
0x1800149a0  cmp     byte ptr [r15+223h], 0
0x1800149a8  jz      short loc_180014A1E
0x1800149aa  xor     edx, edx; int
0x1800149ac  lea     rcx, [rbp+0F0h+var_D0]; this
0x1800149b0  call    ??0CVar@@QEAA@JE@Z; CVar::CVar(long,uchar)
0x1800149b5  nop
0x1800149b6  lea     r8d, [r15+222h]; unsigned int
0x1800149bd  test    r13b, r13b
0x1800149c0  setnz   dl; bool
0x1800149c3  mov     rcx, [rbp+0F0h+var_F8]; this
0x1800149c7  call    ?StartDebugging@CConnection@@QEAAJ_NK@Z; CConnection::StartDebugging(bool,ulong)
0x1800149cc  lea     rcx, [rbp+0F0h+var_D0]; this
0x1800149d0  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800149d5  mov     [rsp+1F0h+lpThreadId], 0; unsigned int *
0x1800149de  lea     rax, [rbp+0F0h+var_D0.guidPropertySet.Data2]
0x1800149e2  mov     qword ptr [rsp+1F0h+dwCreationFlags], rax; struct tagVARIANT *
0x1800149e7  xor     r9d, r9d; int
0x1800149ea  mov     r8d, 22h ; '"'; unsigned int
0x1800149f0  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x1800149f7  mov     rcx, rbx; this
0x1800149fa  call    ?SetProperty@CQuery@@QEAAJAEBU_GUID@@KHPEAUtagVARIANT@@PEAK@Z; CQuery::SetProperty(_GUID const &,ulong,int,tagVARIANT *,ulong *)
0x1800149ff  mov     byte ptr [r15+222h], 1
0x180014a07  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x180014a0e  mov     [rbp+0F0h+var_D0.rgProperties], rax
0x180014a12  lea     rcx, [rbp+0F0h+var_D0]; this
0x180014a16  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x180014a1b  xor     r8d, r8d
0x180014a1e  test    sil, sil
0x180014a21  jnz     short loc_180014A9A
0x180014a23  mov     rcx, rbx; this
0x180014a26  call    ?Clone@CQuery@@QEAAJXZ; CQuery::Clone(void)
0x180014a2b  mov     [rbp+0F0h+var_138], eax
0x180014a2e  test    eax, eax
0x180014a30  jns     short loc_180014A97
0x180014a32  lea     rcx, [rbp+0F0h+TlsValue]; this
0x180014a36  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180014a3b  test    byte ptr cs:_bidGblFlags, 2
0x180014a42  jz      loc_180016666
0x180014a48  lea     rcx, [rbx+40h]; this
0x180014a4c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014a51  cmp     eax, 0FFFFFFFFh
0x180014a54  jz      short loc_180014A87
0x180014a56  lea     rcx, [rbx+40h]; this
0x180014a5a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014a5f  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180014a66  mov     [rsp+1F0h+dwCreationFlags], 0CADh
0x180014a6e  mov     r9d, eax
0x180014a71  lea     r8, aCqueryExecuteA_0; "<CQuery::Execute|ADO|ERR> %u#, line %d"...
0x180014a78  mov     edx, 32B409h
0x180014a7d  call    _bidTraceW
0x180014a82  jmp     loc_180016666
0x180014a87  mov     r9d, 0CADh
0x180014a8d  mov     edx, 32B409h
0x180014a92  jmp     loc_180016653
0x180014a97  xor     r8d, r8d
0x180014a9a  mov     esi, [rbx+0B8h]
0x180014aa0  test    esi, esi
0x180014aa2  jz      loc_180014B34
0x180014aa8  mov     rcx, [rbx+0C0h]
0x180014aaf  mov     [rbp+0F0h+pv], rcx
0x180014ab3  mov     r14d, r8d
0x180014ab6  nop     word ptr [rax+rax+00000000h]
0x180014ac0  mov     edi, r14d
0x180014ac3  shl     rdi, 5
0x180014ac7  add     rdi, rcx
0x180014aca  mov     eax, [rdi+8]
0x180014acd  test    eax, eax
0x180014acf  jz      short loc_180014B11
0x180014ad1  mov     r15d, r8d
0x180014ad4  mov     eax, r15d
0x180014ad7  lea     rcx, [rax+rax*8]
0x180014adb  mov     rax, [rdi]
0x180014ade  lea     rcx, [rcx+6]
0x180014ae2  lea     rcx, [rax+rcx*8]; pvarg
0x180014ae6  call    cs:__imp_VariantClear
0x180014aed  nop     dword ptr [rax+rax+00h]
0x180014af2  inc     r15d
0x180014af5  cmp     r15d, [rdi+8]
0x180014af9  jb      short loc_180014AD4
0x180014afb  mov     rcx, [rdi]; pv
0x180014afe  call    cs:__imp_CoTaskMemFree
0x180014b05  nop     dword ptr [rax+rax+00h]
0x180014b0a  mov     rcx, [rbp+0F0h+pv]; pv
0x180014b0e  xor     r8d, r8d
  ... truncated ...
```
