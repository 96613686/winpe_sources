# CCommand::ExecuteWithModeFlag(tagVARIANT *,tagVARIANT *,long,_ADORecordset * *,int)

- ea: `0x180082f30`
- end: `0x180083abf`
- name: `?ExecuteWithModeFlag@CCommand@@AEAAJPEAUtagVARIANT@@0JPEAPEAU_ADORecordset@@H@Z`
- size: `2959`
- prototype: `__int64 __usercall@<rax>(CCommand *__hidden this@<rcx>, struct tagVARIANT *@<rdx>, struct tagVARIANT *@<r8>, int@<r9d>, struct _ADORecordset **, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x180082b70`
- `0x180082d50`

## callees

- `0x180009240`
- `0x18001fb90`
- `0x180020e20`
- `0x180026c74`
- `0x180026cc0`
- `0x180027790`
- `0x1800278c0`
- `0x180034b10`
- `0x18003c620`
- `0x180042a04`
- `0x18004c520`
- `0x18004f140`
- `0x18004f1b0`
- `0x18004f2b0`
- `0x180056ccc`
- `0x180058338`
- `0x18005a118`
- `0x18005c76c`
- `0x180069aec`
- `0x18006a22c`
- `0x180082f30`
- `0x180084568`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800833c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800833c4`
- `OLEAUT32!__imp_VariantInit` at `0x180082fdc`
- `OLEAUT32!__imp_VariantInit` at `0x180082fec`
- `OLEAUT32!__imp_VariantInit` at `0x180082fdc`
- `OLEAUT32!__imp_VariantInit` at `0x180082fec`
- `OLEAUT32!__imp_VariantClear` at `0x180083a58`
- `OLEAUT32!__imp_VariantClear` at `0x180083a68`
- `OLEAUT32!__imp_VariantClear` at `0x180083a58`
- `OLEAUT32!__imp_VariantClear` at `0x180083a68`

## string_xrefs

- `0x1800830cc`: `<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#, line %d\n`
- `0x1800834ba`: `<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#, line %d\n`
- `0x1800835dc`: `<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#, line %d\n`
- `0x1800830ec`: `<CCommand::ExecuteWithModeFlag|ADO|ERR>  line %d\n`
- `0x1800834e0`: `<CCommand::ExecuteWithModeFlag|ADO|ERR>  line %d\n`
- `0x1800835f8`: `<CCommand::ExecuteWithModeFlag|ADO|ERR>  line %d\n`
- `0x180083416`: `<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180083437`: `<CCommand::ExecuteWithModeFlag|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCommand::ExecuteWithModeFlag(
        CCommand *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        int a4,
        struct _ADORecordset **a5,
        int a6)
{
  struct tagVARIANT *v6; // r15
  struct _ADOConnection *Connection; // rax
  struct IUnknown *v10; // r14
  int v11; // esi
  __int64 BidObjectID; // r9
  __int64 v13; // r10
  __int64 v14; // rcx
  CCommand *v15; // rdi
  const unsigned __int16 *v16; // r15
  __int64 v17; // r10
  int v18; // ebx
  __int64 v19; // rcx
  CCommand *v20; // rax
  const unsigned __int16 *v21; // r8
  unsigned int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdx
  unsigned int v28; // ebx
  int v29; // ecx
  int v30; // edx
  int (__fastcall ***llVal)(_QWORD, GUID *, __int64 *); // rcx
  LONGLONG v33; // rdx
  struct tagVARIANT *v34; // r8
  __int64 v35; // r8
  unsigned int v36; // ebx
  struct tagVARIANT **v38; // [rsp+20h] [rbp-E0h]
  int RawSQL; // [rsp+80h] [rbp-80h] BYREF
  char v40; // [rsp+84h] [rbp-7Ch] BYREF
  char v41; // [rsp+85h] [rbp-7Bh]
  int v42; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v43; // [rsp+90h] [rbp-70h] BYREF
  __int16 v44; // [rsp+94h] [rbp-6Ch] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+9Ch] [rbp-64h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+A8h] [rbp-58h] BYREF
  int v49; // [rsp+ACh] [rbp-54h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v51[5]; // [rsp+B8h] [rbp-48h] BYREF
  int v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v54; // [rsp+F0h] [rbp-10h] BYREF
  struct tagVARIANT *v55; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h] BYREF
  struct tagVARIANT *v57; // [rsp+108h] [rbp+8h]
  struct CSafeArray *v58; // [rsp+110h] [rbp+10h] BYREF
  struct tagVARIANT *v59; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG pvarg; // [rsp+120h] [rbp+20h] BYREF
  VARIANTARG v61; // [rsp+138h] [rbp+38h] BYREF
  __int128 v62; // [rsp+150h] [rbp+50h] BYREF
  __int64 v63; // [rsp+160h] [rbp+60h]
  _BYTE v64[8]; // [rsp+170h] [rbp+70h] BYREF
  struct IUnknown *v65; // [rsp+178h] [rbp+78h]
  __int16 v66; // [rsp+188h] [rbp+88h]
  __int64 v67; // [rsp+190h] [rbp+90h]
  __int16 v68; // [rsp+1A0h] [rbp+A0h]
  CCommand *v69; // [rsp+1A8h] [rbp+A8h]
  __int16 v70; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v71; // [rsp+1C0h] [rbp+C0h]
  __int16 v72; // [rsp+1D0h] [rbp+D0h]
  int *v73; // [rsp+1D8h] [rbp+D8h]
  __int16 v74; // [rsp+1E8h] [rbp+E8h]
  int *v75; // [rsp+1F0h] [rbp+F0h]
  __int16 v76; // [rsp+200h] [rbp+100h]
  int *v77; // [rsp+208h] [rbp+108h]
  __int16 v78; // [rsp+218h] [rbp+118h]
  BSTR *p_bstrString; // [rsp+220h] [rbp+120h]
  unsigned int *v80; // [rsp+250h] [rbp+150h]
  int v81; // [rsp+260h] [rbp+160h]

  v6 = a3;
  v57 = a3;
  v42 = a4;
  v51[4] = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v51);
  v56 = -1;
  v40 = 0;
  v44 = -1;
  v54 = 0;
  v55 = 0;
  v62 = 0;
  v63 = 0;
  v59 = 0;
  v53 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v61, 0, sizeof(v61));
  v50 = 0;
  VariantInit(&pvarg);
  VariantInit(&v61);
  v58 = 0;
  Connection = CCommand::GetConnection(this);
  v10 = (struct IUnknown *)Connection;
  v41 = 0;
  v43 = 0;
  v45 = 0;
  v11 = 0;
  v46 = 0;
  if ( !*((_BYTE *)g_pStaticGlobals + 72)
    || !Connection
    || !(unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(*((_QWORD *)Connection + 35))
    && !(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v10[34].lpVtbl) )
  {
    goto LABEL_45;
  }
  v49 = 1;
  v48 = -1;
  CNfyContext::CNfyContext((CNfyContext *)v64, v10, 4, 0);
  bstrString = 0;
  RawSQL = CCommand::GetRawSQL(this, &bstrString);
  if ( (unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 1841161, L"<CCommand::ExecuteWithModeFlag|ADO|ERR>  line %d\n", 1798);
      }
      else
      {
        BidObjectID = (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(
          off_18012A1E0[0],
          1841161,
          L"<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#, line %d\n",
          BidObjectID,
          1798);
      }
    }
LABEL_10:
    CNfyContext::~CNfyContext((CNfyContext *)v64);
    goto LABEL_11;
  }
  v16 = bstrString;
  v78 = 16392;
  p_bstrString = &bstrString;
  v76 = 16387;
  v77 = &v48;
  v74 = 16387;
  v75 = &v48;
  v72 = 16387;
  v73 = &v42;
  v70 = 16387;
  v71 = (unsigned int *)&v49;
  v80 = (unsigned int *)&v49;
  v68 = 13;
  v69 = this;
  v66 = 13;
  v67 = 0;
  if ( !(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v10[34].lpVtbl)
    || (v18 = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                v17,
                &v45,
                v64),
        RawSQL = v18,
        CContext::Failed((CContext *)v51, &RawSQL),
        v18 >= 0) )
  {
    if ( (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(v10[35].lpVtbl) )
    {
      v65 = v10 + 1;
      v20 = (CCommand *)((char *)this + 8);
      if ( !this )
        v20 = 0;
      v69 = v20;
      v81 = 1;
      RawSQL = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                 v19,
                 &v46,
                 v64);
      CContext::Failed((CContext *)v51, &RawSQL);
      v11 = v46;
    }
  }
  v41 = 1;
  *(_BYTE *)(v51[0] + 28LL) = 1;
  if ( v45 || v11 )
  {
    RawSQL = -2146824576;
  }
  else
  {
    if ( v52 < 0 )
      goto LABEL_37;
    v21 = (*((_BYTE *)this + 184) & 4) != 0 ? (const unsigned __int16 *)*((_QWORD *)this + 22) : 0LL;
    if ( !FArgsAreDifferent(v16, bstrString, v21) )
      goto LABEL_37;
    RawSQL = (*(__int64 (__fastcall **)(CCommand *, BSTR))(*(_QWORD *)this + 96LL))(this, bstrString);
  }
  CContext::Failed((CContext *)v51, &RawSQL);
LABEL_37:
  if ( bstrString )
    SysFreeString(bstrString);
  v22 = v52;
  if ( v52 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(
          off_18012A1E0[0],
          1912841,
          L"<CCommand::ExecuteWithModeFlag|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          v22,
          1868);
      }
      else
      {
        v23 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(
          off_18012A1E0[0],
          1912841,
          L"<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v23,
          v22,
          1868);
      }
    }
    goto LABEL_10;
  }
  CNfyContext::~CNfyContext((CNfyContext *)v64);
  v6 = v57;
LABEL_45:
  RawSQL = ProcessExecuteOption(v42, 1, &v40, &v43, &v42);
  if ( (unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_11;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      LODWORD(v38) = 1872;
      v25 = 1916937;
LABEL_49:
      bidTraceW(off_18012A1E0[0], v25, L"<CCommand::ExecuteWithModeFlag|ADO|ERR> %u#, line %d\n", v24, v38);
      goto LABEL_11;
    }
    v26 = 1872;
    v27 = 1916937;
    goto LABEL_51;
  }
  RawSQL = ValidateCmdType(v42, 1);
  if ( !(unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
  {
    v28 = v43;
    if ( (v43 & 0x80u) != 0 )
    {
      v30 = 0;
      if ( (unsigned int)(v42 + 1) <= 9 )
      {
        v29 = 549;
        if ( _bittest(&v29, v42 + 1) )
          v30 = 1;
      }
      if ( (unsigned int)CContext::ArgFailed((CContext *)v51, v30) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_11;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          LODWORD(v38) = 1878;
          v25 = 1923081;
          goto LABEL_49;
        }
        v26 = 1878;
        v27 = 1923081;
        goto LABEL_51;
      }
    }
    if ( (v28 & 0x400) == 0 )
      goto LABEL_100;
    RawSQL = ((*(int (__fastcall **)(CCommand *, const GUID *, __int64, VARIANTARG *))(*(_QWORD *)this + 296LL))(
                this,
                &DBPROPSET_STREAM,
                286,
                &pvarg) >> 31)
           & 0x800A0CB3;
    if ( (unsigned int)CContext::FailedDescription((CContext *)v51, &RawSQL, 0x2727u) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_11;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v38) = 1884;
        v25 = 1929225;
        goto LABEL_49;
      }
      v26 = 1884;
      v27 = 1929225;
      goto LABEL_51;
    }
    if ( (((pvarg.vt & 0xBFFF) - 9) & 0xFFFFFFFB) != 0 )
      goto LABEL_100;
    llVal = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))pvarg.llVal;
    if ( !((pvarg.vt & 0x4000) != 0 ? *pvarg.pllVal : pvarg.llVal) )
      goto LABEL_100;
    if ( (pvarg.vt & 0x4000) != 0 )
      llVal = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*pvarg.pllVal;
    if ( (**llVal)(llVal, &IID_IADOStream_Deprecated, &v50) < 0 )
      goto LABEL_100;
    RawSQL = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 72LL))(v50, &v53);
    if ( (unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_11;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v38) = 1896;
        v25 = 1941513;
        goto LABEL_49;
      }
      v26 = 1896;
      v27 = 1941513;
      goto LABEL_51;
    }
    if ( v53 )
      goto LABEL_100;
    RawSQL = ((*(int (__fastcall **)(CCommand *, const GUID *, __int64, VARIANTARG *))(*(_QWORD *)this + 296LL))(
                this,
                &DBPROPSET_STREAM,
                287,
                &v61) >> 31)
           & 0x800A0CB3;
    if ( (unsigned int)CContext::FailedDescription((CContext *)v51, &RawSQL, 0x2728u) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_11;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v38) = 1901;
        v25 = 1946633;
        goto LABEL_49;
      }
      v26 = 1901;
      v27 = 1946633;
      goto LABEL_51;
    }
    v33 = (v61.vt & 0x4000) != 0 ? *v61.pllVal : v61.llVal;
    RawSQL = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v50 + 152LL))(v50, v33);
    if ( (unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_11;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v38) = 1907;
        v25 = 1952777;
        goto LABEL_49;
      }
      v26 = 1907;
      v27 = 1952777;
    }
    else
    {
LABEL_100:
      LOWORD(v62) = 10;
      DWORD2(v62) = -2147352572;
      v34 = (struct tagVARIANT *)&v62;
      if ( v6 )
        v34 = v6;
      RawSQL = ExtractArray(&v44, &v54, v34, &v55, &v59, &v58);
      if ( (unsigned int)CContext::Failed((CContext *)v51, &RawSQL) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_11;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          LODWORD(v38) = 1923;
          v25 = 1969161;
          goto LABEL_49;
        }
        v26 = 1923;
        v27 = 1969161;
      }
      else
      {
        LOBYTE(v38) = 0;
        LOBYTE(v35) = v40;
        RawSQL = (*(__int64 (__fastcall **)(CCommand *, __int64, __int64, _QWORD, _DWORD, _DWORD, int, int, _DWORD, struct tagVARIANT *, unsigned __int64, _QWORD, __int64 *, struct _ADORecordset **))(*(_QWORD *)this + 288LL))(
                   this,
                   2,
                   v35,
                   v28,
                   (_DWORD)v38,
                   0,
                   -1,
                   v42,
                   0,
                   v55,
                   v54,
                   0,
                   &v56,
                   a5);
        if ( !(unsigned int)CContext::FailedPushWarning((CContext *)v51, &RawSQL) )
        {
          RawSQL = ProcessRecordsAffected(v56, a2, a6);
          CContext::Failed((CContext *)v51, &RawSQL);
          goto LABEL_11;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_11;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          LODWORD(v38) = 1938;
          v25 = 1984521;
          goto LABEL_49;
        }
        v26 = 1938;
        v27 = 1984521;
      }
    }
LABEL_51:
    bidTraceW(off_18012A1E0[0], v27, L"<CCommand::ExecuteWithModeFlag|ADO|ERR>  line %d\n", v26);
    goto LABEL_11;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      LODWORD(v38) = 1873;
      v25 = 1917961;
      goto LABEL_49;
    }
    v26 = 1873;
    v27 = 1917961;
    goto LABEL_51;
  }
LABEL_11:
  if ( v57 )
    UnlockArray(v57, v59, v58);
  if ( v41 && *((_BYTE *)g_pStaticGlobals + 72) && *(_BYTE *)(v51[0] + 28LL) )
  {
    CNfyContext::CNfyContext((CNfyContext *)v64, v10, 5, 0);
    v43 = 2;
    v74 = 3;
    LODWORD(v75) = 0;
    CNfyContext::SetError((CNfyContext *)v64, v52, 4u);
    v70 = 16387;
    v71 = &v43;
    v80 = &v43;
    v68 = 13;
    v69 = this;
    v66 = 13;
    v67 = 0;
    if ( (!(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v10[34].lpVtbl)
       || (int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                 v13,
                 &v45,
                 v64) >= 0)
      && (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(v10[35].lpVtbl) )
    {
      v65 = v10 + 1;
      if ( this )
        v15 = (CCommand *)((char *)this + 8);
      else
        v15 = 0;
      v69 = v15;
      v81 = 1;
      CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
        v14,
        &v46,
        v64);
    }
    CNfyContext::~CNfyContext((CNfyContext *)v64);
  }
  VariantClear(&pvarg);
  VariantClear(&v61);
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  v36 = v52;
  CContext::~CContext((CContext *)v51);
  return v36;
}

```

## disassembly

```asm
0x180082f30  push    rbp
0x180082f32  push    rbx
0x180082f33  push    rsi
0x180082f34  push    rdi
0x180082f35  push    r12
0x180082f37  push    r13
0x180082f39  push    r14
0x180082f3b  push    r15
0x180082f3d  lea     rbp, [rsp-198h]
0x180082f45  sub     rsp, 298h
0x180082f4c  mov     rax, cs:__security_cookie
0x180082f53  xor     rax, rsp
0x180082f56  mov     [rbp+1D0h+var_50], rax
0x180082f5d  mov     r15, r8
0x180082f60  mov     [rbp+1D0h+var_1C8], r8
0x180082f64  mov     r12, rdx
0x180082f67  mov     rdi, rcx
0x180082f6a  mov     [rbp+1D0h+var_248], r9d
0x180082f6e  mov     r13, [rbp+1D0h+arg_20]
0x180082f75  mov     rax, rcx
0x180082f78  lea     rdx, [rcx+20h]
0x180082f7c  neg     rax
0x180082f7f  sbb     rcx, rcx
0x180082f82  and     rcx, rdx
0x180082f85  mov     [rbp+1D0h+var_1F8], rcx
0x180082f89  lea     rcx, [rbp+1D0h+var_218]; this
0x180082f8d  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180082f92  nop
0x180082f93  or      rax, 0FFFFFFFFFFFFFFFFh
0x180082f97  mov     [rbp+1D0h+var_1D0], rax
0x180082f9b  xor     ebx, ebx
0x180082f9d  mov     [rbp+1D0h+var_24C], bl
0x180082fa0  mov     [rbp+1D0h+var_23C], ax
0x180082fa4  mov     [rbp+1D0h+var_1E0], rbx
0x180082fa8  mov     [rbp+1D0h+var_1D8], rbx
0x180082fac  xorps   xmm0, xmm0
0x180082faf  xor     eax, eax
0x180082fb1  movups  [rbp+1D0h+var_180], xmm0
0x180082fb5  mov     [rbp+1D0h+var_170], rax
0x180082fb9  mov     [rbp+1D0h+var_1B8], rbx
0x180082fbd  mov     [rbp+1D0h+var_1E8], rbx
0x180082fc1  movups  xmmword ptr [rbp+1D0h+pvarg], xmm0
0x180082fc5  mov     qword ptr [rbp+1D0h+pvarg+10h], rax
0x180082fc9  xorps   xmm1, xmm1
0x180082fcc  movups  xmmword ptr [rbp+1D0h+var_198], xmm1
0x180082fd0  mov     qword ptr [rbp+1D0h+var_198+10h], rax
0x180082fd4  mov     [rbp+1D0h+var_220], rbx
0x180082fd8  lea     rcx, [rbp+1D0h+pvarg]; pvarg
0x180082fdc  call    cs:__imp_VariantInit
0x180082fe3  nop     dword ptr [rax+rax+00h]
0x180082fe8  lea     rcx, [rbp+1D0h+var_198]; pvarg
0x180082fec  call    cs:__imp_VariantInit
0x180082ff3  nop     dword ptr [rax+rax+00h]
0x180082ff8  mov     [rbp+1D0h+var_1C0], rbx
0x180082ffc  mov     rcx, rdi; this
0x180082fff  call    ?GetConnection@CCommand@@QEAAPEAU_ADOConnection@@XZ; CCommand::GetConnection(void)
0x180083004  mov     r14, rax
0x180083007  mov     [rbp+1D0h+var_24B], bl
0x18008300a  mov     [rbp+1D0h+var_240], ebx
0x18008300d  mov     [rbp+1D0h+var_238], ebx
0x180083010  mov     esi, ebx
0x180083012  mov     [rbp+1D0h+var_234], ebx
0x180083015  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18008301c  cmp     [rcx+48h], bl
0x18008301f  jz      loc_180083455
0x180083025  test    rax, rax
0x180083028  jz      loc_180083455
0x18008302e  mov     rcx, [rax+118h]
0x180083035  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x18008303a  test    eax, eax
0x18008303c  jnz     short loc_180083052
0x18008303e  mov     rcx, [r14+110h]
0x180083045  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x18008304a  test    eax, eax
0x18008304c  jz      loc_180083455
0x180083052  mov     [rbp+1D0h+var_224], 1
0x180083059  mov     [rbp+1D0h+var_228], 0FFFFFFFFh
0x180083060  xor     r9d, r9d; struct IErrorInfo *
0x180083063  lea     r8d, [r9+4]; int
0x180083067  mov     rdx, r14; struct IUnknown *
0x18008306a  lea     rcx, [rbp+1D0h+var_160]; this
0x18008306e  call    ??0CNfyContext@@QEAA@PEAUIUnknown@@JPEAUIErrorInfo@@@Z; CNfyContext::CNfyContext(IUnknown *,long,IErrorInfo *)
0x180083073  nop
0x180083074  mov     [rbp+1D0h+bstrString], rbx
0x180083078  lea     rdx, [rbp+1D0h+bstrString]; unsigned __int16 **
0x18008307c  mov     rcx, rdi; this
0x18008307f  call    ?GetRawSQL@CCommand@@QEAAJPEAPEAG@Z; CCommand::GetRawSQL(ushort * *)
0x180083084  mov     [rbp+1D0h+var_250], eax
0x180083087  lea     rdx, [rbp+1D0h+var_250]; int *
0x18008308b  lea     rcx, [rbp+1D0h+var_218]; this
0x18008308f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180083094  test    eax, eax
0x180083096  jz      loc_180083228
0x18008309c  test    byte ptr cs:_bidGblFlags, 2
0x1800830a3  jz      short loc_180083105
0x1800830a5  lea     rbx, [rdi+90h]
0x1800830ac  mov     rcx, rbx; this
0x1800830af  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800830b4  cmp     eax, 0FFFFFFFFh
0x1800830b7  jz      short loc_1800830E6
0x1800830b9  mov     rcx, rbx; this
0x1800830bc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800830c1  mov     dword ptr [rsp+2D0h+var_2B0], 706h
0x1800830c9  mov     r9d, eax
0x1800830cc  lea     r8, aCcommandExecut_3; "<CCommand::ExecuteWithModeFlag|ADO|ERR>"...
0x1800830d3  mov     edx, 1C1809h
0x1800830d8  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800830df  call    _bidTraceW
0x1800830e4  jmp     short loc_180083105
0x1800830e6  mov     r9d, 706h
0x1800830ec  lea     r8, aCcommandExecut_0; "<CCommand::ExecuteWithModeFlag|ADO|ERR>"...
0x1800830f3  mov     edx, 1C1809h
0x1800830f8  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800830ff  call    _bidTraceW
0x180083104  nop
0x180083105  lea     rcx, [rbp+1D0h+var_160]; this
0x180083109  call    ??1CNfyContext@@QEAA@XZ; CNfyContext::~CNfyContext(void)
0x18008310e  xor     esi, esi
0x180083110  mov     rcx, [rbp+1D0h+var_1C8]; struct tagVARIANT *
0x180083114  test    rcx, rcx
0x180083117  jz      short loc_180083126
0x180083119  mov     r8, [rbp+1D0h+var_1C0]; struct CSafeArray *
0x18008311d  mov     rdx, [rbp+1D0h+var_1B8]; struct tagVARIANT *
0x180083121  call    ?UnlockArray@@YAJAEAUtagVARIANT@@PEAU1@PEAVCSafeArray@@@Z; UnlockArray(tagVARIANT &,tagVARIANT *,CSafeArray *)
0x180083126  cmp     [rbp+1D0h+var_24B], sil
0x18008312a  jz      loc_180083A54
0x180083130  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180083137  cmp     [rax+48h], sil
0x18008313b  jz      loc_180083A54
0x180083141  mov     rax, [rbp+1D0h+var_218]
0x180083145  cmp     [rax+1Ch], sil
0x180083149  jz      loc_180083A54
0x18008314f  xor     r9d, r9d; struct IErrorInfo *
0x180083152  lea     r8d, [r9+5]; int
0x180083156  mov     rdx, r14; struct IUnknown *
0x180083159  lea     rcx, [rbp+1D0h+var_160]; this
0x18008315d  call    ??0CNfyContext@@QEAA@PEAUIUnknown@@JPEAUIErrorInfo@@@Z; CNfyContext::CNfyContext(IUnknown *,long,IErrorInfo *)
0x180083162  nop
0x180083163  mov     [rbp+1D0h+var_240], 2
0x18008316a  mov     eax, 3
0x18008316f  mov     [rbp+1D0h+var_E8], ax
0x180083176  mov     dword ptr [rbp+1D0h+var_E0], esi
0x18008317c  lea     r8d, [rax+1]; unsigned int
0x180083180  mov     edx, [rbp+1D0h+var_1F0]; int
0x180083183  lea     rcx, [rbp+1D0h+var_160]; this
0x180083187  call    ?SetError@CNfyContext@@QEAAXJI@Z; CNfyContext::SetError(long,uint)
0x18008318c  mov     eax, 4003h
0x180083191  mov     [rbp+1D0h+var_118], ax
0x180083198  lea     rax, [rbp+1D0h+var_240]
0x18008319c  mov     [rbp+1D0h+var_110], rax
0x1800831a3  lea     rax, [rbp+1D0h+var_240]
0x1800831a7  mov     [rbp+1D0h+var_80], rax
0x1800831ae  mov     eax, 0Dh
0x1800831b3  mov     [rbp+1D0h+var_130], ax
0x1800831ba  mov     [rbp+1D0h+var_128], rdi
0x1800831c1  mov     [rbp+1D0h+var_148], ax
0x1800831c8  mov     [rbp+1D0h+var_140], rsi
0x1800831cf  mov     r10, [r14+110h]
0x1800831d6  mov     rcx, r10
0x1800831d9  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x1800831de  test    eax, eax
0x1800831e0  jz      short loc_1800831FA
0x1800831e2  lea     r8, [rbp+1D0h+var_160]
0x1800831e6  lea     rdx, [rbp+1D0h+var_238]
0x1800831ea  mov     rcx, r10
0x1800831ed  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x1800831f2  test    eax, eax
0x1800831f4  js      loc_180083A4B
0x1800831fa  mov     rcx, [r14+118h]
0x180083201  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x180083206  test    eax, eax
0x180083208  jz      loc_180083A4B
0x18008320e  lea     rax, [r14+8]
0x180083212  mov     [rbp+1D0h+var_158], rax
0x180083216  test    rdi, rdi
0x180083219  jz      loc_180083A29
0x18008321f  add     rdi, 8
0x180083223  jmp     loc_180083A2C
0x180083228  mov     r15, [rbp+1D0h+bstrString]
0x18008322c  mov     eax, 4008h
0x180083231  mov     [rbp+1D0h+var_B8], ax
0x180083238  lea     rax, [rbp+1D0h+bstrString]
0x18008323c  mov     [rbp+1D0h+var_B0], rax
0x180083243  mov     ecx, 4003h
0x180083248  mov     [rbp+1D0h+var_D0], cx
0x18008324f  lea     rax, [rbp+1D0h+var_228]
0x180083253  mov     [rbp+1D0h+var_C8], rax
0x18008325a  mov     [rbp+1D0h+var_E8], cx
0x180083261  lea     rax, [rbp+1D0h+var_228]
0x180083265  mov     [rbp+1D0h+var_E0], rax
0x18008326c  mov     [rbp+1D0h+var_100], cx
0x180083273  lea     rax, [rbp+1D0h+var_248]
0x180083277  mov     [rbp+1D0h+var_F8], rax
0x18008327e  mov     [rbp+1D0h+var_118], cx
0x180083285  lea     rax, [rbp+1D0h+var_224]
0x180083289  mov     [rbp+1D0h+var_110], rax
0x180083290  lea     rax, [rbp+1D0h+var_224]
0x180083294  mov     [rbp+1D0h+var_80], rax
0x18008329b  mov     eax, 0Dh
0x1800832a0  mov     [rbp+1D0h+var_130], ax
0x1800832a7  mov     [rbp+1D0h+var_128], rdi
0x1800832ae  mov     [rbp+1D0h+var_148], ax
0x1800832b5  mov     [rbp+1D0h+var_140], rbx
0x1800832bc  mov     r10, [r14+110h]
0x1800832c3  mov     rcx, r10
0x1800832c6  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x1800832cb  test    eax, eax
0x1800832cd  jz      short loc_1800832F7
0x1800832cf  lea     r8, [rbp+1D0h+var_160]
0x1800832d3  lea     rdx, [rbp+1D0h+var_238]
0x1800832d7  mov     rcx, r10
0x1800832da  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x1800832df  mov     ebx, eax
0x1800832e1  mov     [rbp+1D0h+var_250], eax
0x1800832e4  lea     rdx, [rbp+1D0h+var_250]; int *
0x1800832e8  lea     rcx, [rbp+1D0h+var_218]; this
0x1800832ec  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800832f1  test    ebx, ebx
0x1800832f3  js      short loc_18008334E
0x1800832f5  xor     ebx, ebx
0x1800832f7  mov     rcx, [r14+118h]
0x1800832fe  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x180083303  test    eax, eax
0x180083305  jz      short loc_180083350
0x180083307  lea     rax, [r14+8]
0x18008330b  mov     [rbp+1D0h+var_158], rax
0x18008330f  test    rdi, rdi
0x180083312  lea     rax, [rdi+8]
0x180083316  jnz     short loc_18008331B
0x180083318  mov     rax, rbx
0x18008331b  mov     [rbp+1D0h+var_128], rax
0x180083322  mov     [rbp+1D0h+var_70], 1
0x18008332c  lea     r8, [rbp+1D0h+var_160]
0x180083330  lea     rdx, [rbp+1D0h+var_234]
0x180083334  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x180083339  mov     [rbp+1D0h+var_250], eax
0x18008333c  lea     rdx, [rbp+1D0h+var_250]; int *
0x180083340  lea     rcx, [rbp+1D0h+var_218]; this
0x180083344  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180083349  mov     esi, [rbp+1D0h+var_234]
0x18008334c  jmp     short loc_180083350
0x18008334e  xor     ebx, ebx
0x180083350  mov     [rbp+1D0h+var_24B], 1
0x180083354  mov     rax, [rbp+1D0h+var_218]
0x180083358  mov     byte ptr [rax+1Ch], 1
0x18008335c  cmp     [rbp+1D0h+var_238], ebx
0x18008335f  jnz     short loc_1800833A7
0x180083361  test    esi, esi
0x180083363  jnz     short loc_1800833A7
0x180083365  cmp     [rbp+1D0h+var_1F0], ebx
0x180083368  jl      short loc_1800833BB
0x18008336a  test    byte ptr [rdi+0B8h], 4
0x180083371  jz      short loc_18008337C
0x180083373  mov     r8, [rdi+0B0h]
0x18008337a  jmp     short loc_18008337F
0x18008337c  mov     r8, rbx; unsigned __int16 *
0x18008337f  mov     rdx, [rbp+1D0h+bstrString]; unsigned __int16 *
0x180083383  mov     rcx, r15; unsigned __int16 *
0x180083386  call    ?FArgsAreDifferent@@YA_NPEBG00@Z; FArgsAreDifferent(ushort const *,ushort const *,ushort const *)
0x18008338b  test    al, al
0x18008338d  jz      short loc_1800833BB
0x18008338f  mov     rax, [rdi]
0x180083392  mov     rdx, [rbp+1D0h+bstrString]
0x180083396  mov     rcx, rdi
0x180083399  mov     rax, [rax+60h]
0x18008339d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833a2  mov     [rbp+1D0h+var_250], eax
0x1800833a5  jmp     short loc_1800833AE
0x1800833a7  mov     [rbp+1D0h+var_250], 800A0E80h
0x1800833ae  lea     rdx, [rbp+1D0h+var_250]; int *
0x1800833b2  lea     rcx, [rbp+1D0h+var_218]; this
0x1800833b6  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800833bb  mov     rcx, [rbp+1D0h+bstrString]; bstrString
0x1800833bf  test    rcx, rcx
0x1800833c2  jz      short loc_1800833D0
0x1800833c4  call    cs:__imp_SysFreeString
0x1800833cb  nop     dword ptr [rax+rax+00h]
0x1800833d0  mov     ebx, [rbp+1D0h+var_1F0]
0x1800833d3  test    ebx, ebx
0x1800833d5  jns     short loc_180083448
0x1800833d7  test    byte ptr cs:_bidGblFlags, 2
0x1800833de  jz      loc_180083105
0x1800833e4  lea     rsi, [rdi+90h]
0x1800833eb  mov     rcx, rsi; this
0x1800833ee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800833f3  cmp     eax, 0FFFFFFFFh
0x1800833f6  jz      short loc_18008342C
0x1800833f8  mov     rcx, rsi; this
0x1800833fb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180083400  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180083407  mov     dword ptr [rsp+2D0h+var_2A8], 74Ch
0x18008340f  mov     dword ptr [rsp+2D0h+var_2B0], ebx
0x180083413  mov     r9d, eax
0x180083416  lea     r8, aCcommandExecut_14; "<CCommand::ExecuteWithModeFlag|ADO|ERR>"...
0x18008341d  mov     edx, 1D3009h
0x180083422  call    _bidTraceW
0x180083427  jmp     loc_180083105
0x18008342c  mov     dword ptr [rsp+2D0h+var_2B0], 74Ch
0x180083434  mov     r9d, ebx
0x180083437  lea     r8, aCcommandExecut_8; "<CCommand::ExecuteWithModeFlag|ADO|ERR>"...
  ... truncated ...
```
