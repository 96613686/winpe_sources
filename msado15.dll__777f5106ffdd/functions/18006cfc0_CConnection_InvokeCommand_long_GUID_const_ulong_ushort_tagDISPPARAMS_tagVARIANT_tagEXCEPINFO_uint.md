# CConnection::InvokeCommand(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18006cfc0`
- end: `0x18006ebe1`
- name: `?InvokeCommand@CConnection@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `7201`
- prototype: `__int64 __usercall@<rax>(CConnection *__hidden this@<rcx>, int@<edx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `41`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180009240`
- `0x18000fcc0`
- `0x180011088`
- `0x180011530`
- `0x180018788`
- `0x18001a750`
- `0x18001a820`
- `0x18001cb68`
- `0x180020da0`
- `0x180020e20`
- `0x180020e50`
- `0x180024d1c`
- `0x180026c74`
- `0x180026cc0`
- `0x180027790`
- `0x180030ce0`
- `0x180034b10`
- `0x180044db0`
- `0x18004ba1c`
- `0x18004c520`
- `0x180059ccc`
- `0x180059e18`
- `0x180059f4c`
- `0x18005a118`
- `0x18005c76c`
- `0x18005cd08`
- `0x180069aec`
- `0x18006a22c`
- `0x18006cfc0`
- `0x180084568`
- `0x1800aa77c`
- `0x1800ab69c`
- `0x1800b4b04`
- `0x1800c8f34`
- `0x1800ca744`
- `0x1800cd1b0`
- `0x1800cd424`
- `0x1800cd4c4`
- `0x1800cdad2`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18006db9b`
- `MSDART!UMSEnterCSWraper` at `0x18006e32f`
- `MSDART!UMSEnterCSWraper` at `0x18006db9b`
- `MSDART!UMSEnterCSWraper` at `0x18006e32f`
- `MSDART!MpHeapAlloc` at `0x18006dee4`
- `MSDART!MpHeapAlloc` at `0x18006dee4`
- `KERNEL32!LeaveCriticalSection` at `0x18006dd3f`
- `KERNEL32!LeaveCriticalSection` at `0x18006e4c3`
- `KERNEL32!LeaveCriticalSection` at `0x18006e4e6`
- `KERNEL32!LeaveCriticalSection` at `0x18006dd3f`
- `KERNEL32!LeaveCriticalSection` at `0x18006e4c3`
- `KERNEL32!LeaveCriticalSection` at `0x18006e4e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d565`
- `OLEAUT32!__imp_SysAllocString` at `0x18006d565`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d838`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d897`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d838`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d897`
- `OLEAUT32!__imp_VariantInit` at `0x18006df7e`
- `OLEAUT32!__imp_VariantInit` at `0x18006df7e`
- `OLEAUT32!__imp_VariantClear` at `0x18006e5f9`
- `OLEAUT32!__imp_VariantClear` at `0x18006e7cf`
- `OLEAUT32!__imp_VariantClear` at `0x18006e83a`
- `OLEAUT32!__imp_VariantClear` at `0x18006e5f9`
- `OLEAUT32!__imp_VariantClear` at `0x18006e7cf`
- `OLEAUT32!__imp_VariantClear` at `0x18006e83a`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18006e77d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18006e77d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18006e7b6`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18006e7b6`

## string_xrefs

- `0x18006d0db`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006d34a`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006d642`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006d9e9`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006dc08`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006e39b`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006e94b`: `<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n`
- `0x18006d101`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006d36f`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006d66c`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006da0c`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006dc2b`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006e49c`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006e970`: `<CConnection::InvokeCommand|ADO|ERR>  line %d\n`
- `0x18006d8dc`: `<CConnection::InvokeCommand|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18006d909`: `<CConnection::InvokeCommand|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::InvokeCommand(
        CConnection *this,
        int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8)
{
  struct tagDISPPARAMS *v8; // rdi
  VARIANTARG *v9; // rsi
  CConnection *v11; // r14
  int v12; // r12d
  unsigned int BidObjectID; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // eax
  struct tagVARIANT *v18; // rcx
  int v19; // ebx
  char v20; // di
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r10
  const unsigned __int16 *v26; // rsi
  __int64 v27; // r10
  int v28; // ebx
  __int64 v29; // rcx
  bool v30; // di
  OLECHAR *v31; // rbx
  unsigned int v32; // ebx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  __int16 v36; // r8
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r9
  __int64 v40; // rdx
  int (__fastcall ***v41)(_QWORD, GUID *, CRecordset **); // rcx
  __int16 v42; // r8
  _QWORD *v43; // rax
  CRecordset *v44; // r12
  CRecordset *v45; // rbx
  unsigned int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // r9
  __int64 v49; // rdx
  VARIANTARG *v50; // rax
  __int64 v51; // rcx
  bool v52; // r12
  CParameters *v53; // rbx
  struct IDispatch *v54; // r13
  VARIANTARG *rgvarg; // rdx
  __int64 v56; // r8
  unsigned int v57; // ebx
  unsigned int cArgs; // edi
  __int64 v59; // rax
  VARIANTARG *v60; // r12
  __int64 v61; // r9
  struct tagDISPPARAMS *v62; // r14
  __int64 v63; // rax
  __int64 v64; // rcx
  unsigned int v65; // ebx
  char v66; // al
  unsigned int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // r9
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rcx
  unsigned int v73; // r12d
  VARIANTARG *v74; // rbx
  struct tagDISPPARAMS *v75; // rcx
  __int64 v76; // r13
  VARTYPE vt; // bx
  unsigned __int16 v78; // bx
  int v79; // edx
  SAFEARRAY *v80; // r13
  CSafeArray *v81; // r12
  int v82; // edx
  int v83; // eax
  PVOID pvData; // rdi
  size_t v85; // rbx
  CSafeArray *v86; // rcx
  const void *v87; // rax
  struct tagVARIANT *v88; // rcx
  int v89; // r8d
  int v90; // eax
  unsigned __int16 v91; // r8
  unsigned __int8 v92; // al
  BSTR v93; // rcx
  size_t v94; // r8
  struct tagDISPPARAMS *v95; // rbx
  unsigned __int16 v96; // r8
  unsigned int v97; // eax
  __int64 v98; // r10
  __int64 v99; // r10
  __int64 v100; // rcx
  unsigned int v101; // ebx
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+20h] [rbp-E0h]
  int v105; // [rsp+20h] [rbp-E0h]
  int v106; // [rsp+20h] [rbp-E0h]
  int v107; // [rsp+20h] [rbp-E0h]
  int Command; // [rsp+80h] [rbp-80h] BYREF
  int Parameter; // [rsp+84h] [rbp-7Ch] BYREF
  bool v110; // [rsp+88h] [rbp-78h]
  int CursorType; // [rsp+8Ch] [rbp-74h] BYREF
  CursorTypeEnum v112; // [rsp+90h] [rbp-70h] BYREF
  char v113; // [rsp+94h] [rbp-6Ch]
  int v114; // [rsp+98h] [rbp-68h] BYREF
  int v115; // [rsp+9Ch] [rbp-64h]
  int v116; // [rsp+A0h] [rbp-60h] BYREF
  struct tagDISPPARAMS *v117; // [rsp+A8h] [rbp-58h]
  struct IDispatch *v118; // [rsp+B0h] [rbp-50h] BYREF
  BSTR v119; // [rsp+B8h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG *pvarg; // [rsp+C8h] [rbp-38h]
  CRecordset *v122; // [rsp+D0h] [rbp-30h] BYREF
  int v123; // [rsp+D8h] [rbp-28h] BYREF
  int v124; // [rsp+DCh] [rbp-24h] BYREF
  _BYTE v125[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v126; // [rsp+100h] [rbp+0h]
  int v127; // [rsp+108h] [rbp+8h]
  struct CParameter *v128; // [rsp+110h] [rbp+10h] BYREF
  int v129; // [rsp+118h] [rbp+18h] BYREF
  int v130; // [rsp+11Ch] [rbp+1Ch] BYREF
  LockTypeEnum v131; // [rsp+120h] [rbp+20h] BYREF
  VARIANTARG *v132; // [rsp+128h] [rbp+28h]
  VARIANTARG *v133; // [rsp+130h] [rbp+30h]
  __int64 v134; // [rsp+138h] [rbp+38h] BYREF
  char v135; // [rsp+140h] [rbp+40h]
  int v136; // [rsp+148h] [rbp+48h] BYREF
  struct tagVARIANT v137; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v138; // [rsp+168h] [rbp+68h]
  CParameters *v139; // [rsp+180h] [rbp+80h]
  __int64 v140; // [rsp+188h] [rbp+88h]
  _QWORD v141[2]; // [rsp+190h] [rbp+90h] BYREF
  __int16 v142; // [rsp+1A0h] [rbp+A0h]
  char Src[16]; // [rsp+1A8h] [rbp+A8h] BYREF
  CSafeArray *v144; // [rsp+1B8h] [rbp+B8h]
  CConnection *v145; // [rsp+1C0h] [rbp+C0h]
  __int64 v146; // [rsp+1C8h] [rbp+C8h]
  _QWORD v147[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  struct tagVARIANT v148; // [rsp+1E0h] [rbp+E0h]
  char v149[8]; // [rsp+200h] [rbp+100h] BYREF
  char *v150; // [rsp+208h] [rbp+108h]
  __int16 v151; // [rsp+218h] [rbp+118h]
  __int64 v152; // [rsp+220h] [rbp+120h]
  __int16 v153; // [rsp+230h] [rbp+130h]
  struct IDispatch *v154; // [rsp+238h] [rbp+138h]
  __int16 v155; // [rsp+248h] [rbp+148h]
  CursorTypeEnum *v156; // [rsp+250h] [rbp+150h]
  __int16 v157; // [rsp+260h] [rbp+160h]
  int *v158; // [rsp+268h] [rbp+168h]
  __int16 v159; // [rsp+278h] [rbp+178h]
  int *v160; // [rsp+280h] [rbp+180h]
  __int16 v161; // [rsp+290h] [rbp+190h]
  int *v162; // [rsp+298h] [rbp+198h]
  __int16 v163; // [rsp+2A8h] [rbp+1A8h]
  BSTR *v164; // [rsp+2B0h] [rbp+1B0h]
  CursorTypeEnum *v165; // [rsp+2E0h] [rbp+1E0h]
  int v166; // [rsp+2F0h] [rbp+1F0h]

  v8 = a6;
  v9 = a7;
  v145 = this;
  v11 = this;
  v117 = a6;
  v132 = a7;
  v126 = ((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v125);
  v135 = 7;
  v12 = 0;
  v116 = 0;
  pvarg = 0;
  v118 = 0;
  v122 = 0;
  v140 = 0;
  v134 = 0;
  v112 = adOpenForwardOnly;
  v131 = adLockReadOnly;
  v146 = 0;
  v128 = 0;
  v114 = 0;
  v113 = 0;
  v123 = 0;
  v124 = 0;
  if ( a6->cNamedArgs )
  {
    v112 = -2147352569;
    CContext::Failed((CContext *)v125, (const int *)&v112);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_290;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
    {
      v15 = 6202;
      v16 = 6350857;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
    v14 = 6350857;
    v103 = 6202;
    goto LABEL_5;
  }
  if ( *((_BYTE *)v11 + 1041) )
  {
    Command = -2146824575;
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6207;
        v16 = 6355977;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6355977;
      v103 = 6207;
      goto LABEL_5;
    }
  }
  if ( !*((_BYTE *)v11 + 390) )
  {
    Command = -2146824584;
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6210;
        v16 = 6359049;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6359049;
      v103 = 6210;
      goto LABEL_5;
    }
  }
  if ( CConnection::GetExecState(v11) )
  {
    Command = -2146824577;
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6213;
        v16 = 6362121;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6362121;
      v103 = 6213;
      goto LABEL_5;
    }
  }
  Command = CCollectionList::LookUpByData(
              (CConnection *)((char *)v11 + 632),
              (void *)(a2 - 1000),
              (struct CSysString *)&v134);
  if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_290;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
    {
      v15 = 6223;
      v16 = 6372361;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
    v14 = 6372361;
    v103 = 6223;
    goto LABEL_5;
  }
  CVar::CVar((CVar *)v147, (const struct CSysString *)&v134, 4u);
  if ( (unsigned int)CContext::VariantFailed((CContext *)v125, (const struct CVar *)v147) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        bidTraceW(off_18012A1C0[0], 6376457, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", 6227);
      }
      else
      {
        v17 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
        bidTraceW(off_18012A1C0[0], 6376457, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v17, 6227);
      }
    }
    v147[0] = &CVar::`vftable';
    v18 = (struct tagVARIANT *)v147;
    goto LABEL_37;
  }
  CVar::UpdateVariant((CVar *)v147);
  v137 = v148;
  v127 = CStdCollection::Item((CConnection *)((char *)v11 + 544), &v137, &IID_IADOCommand, (void **)&v118);
  v147[0] = &CVar::`vftable';
  CVar::Clear((CVar *)v147);
  if ( v127 >= 0 )
  {
    v19 = -1;
  }
  else
  {
    if ( v127 != -2146825023 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6233;
        v16 = 6382601;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6382601;
      v103 = 6233;
      goto LABEL_5;
    }
    Command = CreateCommand(v11, (const struct CSysString *)&v134, 0, (struct _ADOCommand **)&v118);
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6235;
        v16 = 6384649;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6384649;
      v103 = 6235;
      goto LABEL_5;
    }
    v19 = 4;
  }
  v115 = v19;
  if ( !*((_BYTE *)g_pStaticGlobals + 72)
    || !(unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(*((_QWORD *)v11 + 35))
    && !(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(*((_QWORD *)v11 + 34)) )
  {
    goto LABEL_91;
  }
  v130 = 1;
  v129 = -1;
  v136 = -1;
  CNfyContext::CNfyContext((CNfyContext *)v149, (struct IUnknown *)v11, 4, 0);
  v20 = v135;
  v119 = 0;
  if ( v19 == 4 )
  {
    v119 = SysAllocString((const OLECHAR *)(v134 & -(__int64)((v135 & 4) != 0)));
  }
  else
  {
    Command = CCommand::GetRawSQL((CCommand *)v118, &v119);
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
        {
          v21 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
          v22 = 6410249;
          v104 = 6260;
          goto LABEL_65;
        }
        v23 = 6260;
        v24 = 6410249;
LABEL_67:
        bidTraceW(off_18012A1C0[0], v24, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", v23);
      }
LABEL_68:
      CNfyContext::~CNfyContext((CNfyContext *)v149);
      goto LABEL_290;
    }
  }
  if ( !v119 )
  {
    Command = -2147024882;
    if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
        {
          v21 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
          v22 = 6413321;
          v104 = 6263;
LABEL_65:
          bidTraceW(off_18012A1C0[0], v22, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v21, v104);
          goto LABEL_68;
        }
        v23 = 6263;
        v24 = 6413321;
        goto LABEL_67;
      }
      goto LABEL_68;
    }
  }
  v25 = *((_QWORD *)v11 + 34);
  v26 = v119;
  v163 = 16392;
  v164 = &v119;
  v162 = &v129;
  v160 = &v129;
  v158 = &v136;
  v156 = (CursorTypeEnum *)&v130;
  v161 = 16387;
  v159 = 16387;
  v157 = 16387;
  v155 = 16387;
  v165 = (CursorTypeEnum *)&v130;
  v153 = 13;
  v151 = 13;
  v154 = v118;
  v152 = 0;
  if ( !(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v25)
    || (Command = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                    v27,
                    &v123,
                    v149),
        v28 = Command,
        CContext::FailedInvoke((CContext *)v125, &Command, a8, 0),
        v28 >= 0) )
  {
    if ( (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(*((_QWORD *)v11 + 35)) )
    {
      v166 = 1;
      v150 = (char *)v11 + 8;
      Command = CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                  v29,
                  &v124,
                  v149);
      CContext::FailedInvoke((CContext *)v125, &Command, a8, 0);
      v12 = v124;
    }
  }
  if ( v123 || v12 )
  {
    Command = -2146824576;
    CContext::FailedInvoke((CContext *)v125, &Command, a8, 0);
    v113 = 1;
  }
  else if ( v127 >= 0 )
  {
    if ( v115 == 4 )
    {
      v30 = FArgsAreDifferent(v26, v119, (const unsigned __int16 *)(v134 & -(__int64)((v20 & 4) != 0)));
LABEL_82:
      if ( v30 )
      {
        Command = ((__int64 (__fastcall *)(struct IDispatch *, BSTR))v118->lpVtbl[1].GetIDsOfNames)(v118, v119);
        CContext::FailedInvoke((CContext *)v125, &Command, a8, 0);
      }
      goto LABEL_85;
    }
    bstrString = 0;
    if ( (int)CCommand::GetRawSQL((CCommand *)v118, &bstrString) >= 0 )
    {
      v31 = bstrString;
      v30 = FArgsAreDifferent(v26, v119, bstrString);
      if ( v31 )
        SysFreeString(v31);
      goto LABEL_82;
    }
  }
LABEL_85:
  SysFreeString(v119);
  v32 = v127;
  if ( v127 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        bidTraceW(
          off_18012A1C0[0],
          6495241,
          L"<CConnection::InvokeCommand|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          v32,
          6343);
      }
      else
      {
        v33 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
        bidTraceW(
          off_18012A1C0[0],
          6495241,
          L"<CConnection::InvokeCommand|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v33,
          v32,
          6343);
      }
    }
    goto LABEL_68;
  }
  CNfyContext::~CNfyContext((CNfyContext *)v149);
  v8 = v117;
  v9 = v132;
LABEL_91:
  v133 = 0;
  bstrString = 0;
  if ( v8->cArgs )
  {
    CVar::CVar((CVar *)&v137, v8->rgvarg, 4u, 1);
    if ( (((*(_WORD *)(&v137.decVal + 1) & 0xBFFF) - 9) & 0xFFFB) == 0 )
    {
      if ( !CVar::operator IUnknown *(&v137, v34, *((unsigned __int16 *)&v137.decVal + 8), v35) )
      {
        Command = -2146825287;
        if ( CContext::FailedInvoke((CContext *)v125, &Command, a8, 0) )
        {
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_101:
            *(_QWORD *)&v137.vt = &CVar::`vftable';
            v18 = &v137;
LABEL_37:
            CVar::Clear((CVar *)v18);
            goto LABEL_290;
          }
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
          {
            v37 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
            v38 = 6509577;
            v105 = 6357;
LABEL_98:
            bidTraceW(off_18012A1C0[0], v38, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v37, v105);
            goto LABEL_101;
          }
          v39 = 6357;
          v40 = 6509577;
          goto LABEL_100;
        }
        v36 = *((_WORD *)&v137.decVal + 8);
      }
      if ( (((v36 & 0xBFFF) - 9) & 0xFFFB) == 0 )
      {
        v41 = (int (__fastcall ***)(_QWORD, GUID *, CRecordset **))v138;
        v42 = v36 & 0x4000;
        if ( v42 )
          v43 = (_QWORD *)*v138;
        else
          v43 = v138;
        if ( !v43 )
        {
          v44 = 0;
          bstrString = 0;
          v122 = 0;
          goto LABEL_113;
        }
        if ( v42 )
          v41 = (int (__fastcall ***)(_QWORD, GUID *, CRecordset **))*v138;
        if ( (**v41)(v41, &IID_IADORecordset, &v122) >= 0 )
        {
          v44 = v122;
          bstrString = (BSTR)v122;
LABEL_113:
          Command = 0;
          CursorType = (*(__int64 (__fastcall **)(CRecordset *, int *))(*(_QWORD *)v44 + 440LL))(v44, &Command);
          if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_101;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
            {
              v37 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
              v38 = 6517769;
              v105 = 6365;
              goto LABEL_98;
            }
            v39 = 6365;
            v40 = 6517769;
LABEL_100:
            bidTraceW(off_18012A1C0[0], v40, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", v39);
            goto LABEL_101;
          }
          if ( (Command & 1) != 0 )
          {
            v112 = -2146824583;
            CContext::FailedInvoke((CContext *)v125, (const int *)&v112, a8, 0);
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_101;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
            {
              v37 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
              v38 = 6521865;
              v105 = 6369;
              goto LABEL_98;
            }
            v39 = 6369;
            v40 = 6521865;
            goto LABEL_100;
          }
          v45 = v122;
          UMSEnterCSWraper(*((_QWORD *)v122 + 38) + 8LL);
          CursorType = CRecordset::GetCursorType(v44, &v112);
          if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
          {
            if ( (bidGblFlags & 2) == 0 )
            {
LABEL_130:
              *(_QWORD *)&v137.vt = &CVar::`vftable';
              CVar::Clear((CVar *)&v137);
              goto LABEL_240;
            }
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
            {
              v46 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
              v47 = 6525961;
              v106 = 6373;
LABEL_127:
              bidTraceW(off_18012A1C0[0], v47, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v46, v106);
              goto LABEL_130;
            }
            v48 = 6373;
            v49 = 6525961;
            goto LABEL_129;
          }
          CursorType = CRecordset::GetLockType(v44, &v131);
          if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_130;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
            {
              v46 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
              v47 = 6526985;
              v106 = 6374;
              goto LABEL_127;
            }
            v48 = 6374;
            v49 = 6526985;
LABEL_129:
            bidTraceW(off_18012A1C0[0], v49, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", v48);
            goto LABEL_130;
          }
          v50 = (VARIANTARG *)*((_QWORD *)v44 + 180);
          CursorType = 0;
          v133 = v50;
          if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_130;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
            {
              v46 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
              v47 = 6528009;
              v106 = 6375;
              goto LABEL_127;
            }
            v48 = 6375;
            v49 = 6528009;
            goto LABEL_129;
          }
          v51 = *(_QWORD *)(*((_QWORD *)v45 + 38) + 8LL);
          --*(_DWORD *)(v51 + 48);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v51 + 8));
        }
      }
    }
    *(_QWORD *)&v137.vt = &CVar::`vftable';
    CVar::Clear((CVar *)&v137);
  }
  v52 = 0;
  v110 = 0;
  v53 = (CParameters *)&v118[46];
  v139 = (CParameters *)&v118[46];
  v54 = v118 + 49;
  if ( ((unsigned int (__fastcall *)(struct IDispatch *))v118[49].lpVtbl[4].GetTypeInfoCount)(&v118[49]) )
  {
    CursorType = CParameters::GetParameter(v53, 0, &v128);
    v57 = 0;
    if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6387;
        v16 = 6540297;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6540297;
      v103 = 6387;
      goto LABEL_5;
    }
    CursorType = (*(__int64 (__fastcall **)(struct CParameter *, int *))(*(_QWORD *)v128 + 120LL))(v128, &v114);
    if ( CContext::FailedInvoke((CContext *)v125, &CursorType, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6389;
        v16 = 6542345;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6542345;
      v103 = 6389;
      goto LABEL_5;
    }
    v52 = v114 == 4;
    v110 = v114 == 4;
  }
  else
  {
    v57 = 0;
  }
  if ( v9 || v52 )
    cArgs = v8->cArgs + 1;
  else
    cArgs = v8->cArgs;
  CursorType = cArgs;
  if ( v122 )
    CursorType = --cArgs;
  if ( cArgs )
  {
    v59 = 24LL * cArgs;
    if ( !is_mul_ok(cArgs, 0x18u) )
      v59 = -1;
    pvarg = (VARIANTARG *)MpHeapAlloc(g_hHeapHandle, 10485760, v59);
    if ( !pvarg )
    {
      Parameter = -2147024882;
      if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_290;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
        {
          v15 = 6406;
          v16 = 6559753;
          goto LABEL_7;
        }
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
        v14 = 6559753;
        v103 = 6406;
        goto LABEL_5;
      }
    }
  }
  if ( v132 || v52 )
  {
    v60 = pvarg;
    v57 = 1;
    VariantInit(pvarg);
  }
  else
  {
    v60 = pvarg;
  }
  v61 = v117->cArgs - 1;
  if ( v57 < cArgs )
  {
    v62 = v117;
    do
    {
      rgvarg = v62->rgvarg;
      v56 = v61;
      v63 = v57;
      v61 = (unsigned int)(v61 - 1);
      ++v57;
      v64 = v63;
      *(_OWORD *)&v60[v64].vt = *(_OWORD *)&v62->rgvarg[v56].vt;
      v60[v64].pRecInfo = rgvarg[v56].pRecInfo;
    }
    while ( v57 < cArgs );
    v11 = v145;
  }
  v65 = 0;
  if ( ((unsigned int (__fastcall *)(struct IDispatch *, VARIANTARG *, __int64, __int64))v54->lpVtbl[4].GetTypeInfoCount)(
         v54,
         rgvarg,
         v56 * 3,
         v61) )
  {
    if ( ((unsigned int (__fastcall *)(struct IDispatch *))v54->lpVtbl[4].GetTypeInfoCount)(v54) >= cArgs )
      goto LABEL_192;
    Parameter = -2147352562;
    if ( !(unsigned int)CContext::Failed((CContext *)v125, &Parameter) )
      goto LABEL_192;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_290;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
    {
      v15 = 6437;
      v16 = 6591497;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
    v14 = 6591497;
    v103 = 6437;
LABEL_5:
    bidTraceW(off_18012A1C0[0], v14, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", BidObjectID, v103);
    goto LABEL_290;
  }
  if ( v132 )
  {
    Parameter = -2146825287;
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6443;
        v16 = 6597641;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6597641;
      v103 = 6443;
      goto LABEL_5;
    }
  }
LABEL_192:
  while ( v65 < ((unsigned int (__fastcall *)(struct IDispatch *))v54->lpVtbl[4].GetTypeInfoCount)(v54) && v65 < cArgs )
  {
    Parameter = CParameters::GetParameter(v139, v65, &v128);
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6450;
        v16 = 6604809;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6604809;
      v103 = 6450;
      goto LABEL_5;
    }
    Parameter = (*(__int64 (__fastcall **)(struct CParameter *, int *))(*(_QWORD *)v128 + 120LL))(v128, &v114);
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_290;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v15 = 6452;
        v16 = 6606857;
        goto LABEL_7;
      }
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v14 = 6606857;
      v103 = 6452;
      goto LABEL_5;
    }
    if ( v110 )
      goto LABEL_200;
    v66 = v114;
    if ( v114 == 4 && !v132 )
    {
      Parameter = -2146825287;
      if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_290;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
        {
          v15 = 6457;
          v16 = 6611977;
          goto LABEL_7;
        }
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
        v14 = 6611977;
        v103 = 6457;
        goto LABEL_5;
      }
LABEL_200:
      v66 = v114;
    }
    if ( (v66 & 2) != 0 && pvarg[v65].vt != 10 && (pvarg[v65].vt & 0x4000) == 0 )
    {
      Parameter = -2146825287;
      if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_290;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
        {
          v15 = 6463;
          v16 = 6618121;
          goto LABEL_7;
        }
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
        v14 = 6618121;
        v103 = 6463;
        goto LABEL_5;
      }
    }
    ++v65;
  }
  v45 = v122;
  if ( v122 )
  {
    UMSEnterCSWraper(*((_QWORD *)v122 + 38) + 8LL);
    Parameter = CRecordset::SetSourceSimple(v45, 0);
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
        {
          v67 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
          v68 = 6627337;
          v107 = 6472;
          goto LABEL_227;
        }
        v69 = 6472;
        v70 = 6627337;
LABEL_239:
        bidTraceW(off_18012A1C0[0], v70, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", v69);
      }
LABEL_240:
      if ( v45 )
      {
        v71 = *(_QWORD *)(*((_QWORD *)v45 + 38) + 8LL);
        --*(_DWORD *)(v71 + 48);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v71 + 8));
      }
      goto LABEL_290;
    }
    Parameter = CRecordset::SetActiveConnection(v45, 0);
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_240;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v69 = 6473;
        v70 = 6628361;
        goto LABEL_239;
      }
      v67 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v68 = 6628361;
      v107 = 6473;
      goto LABEL_227;
    }
    Parameter = CRecordset::SetSourceSimple(v45, v118);
    if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_240;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
      {
        v69 = 6474;
        v70 = 6629385;
        goto LABEL_239;
      }
      v67 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
      v68 = 6629385;
      v107 = 6474;
LABEL_227:
      bidTraceW(off_18012A1C0[0], v68, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v67, v107);
      goto LABEL_240;
    }
    v72 = *(_QWORD *)(*((_QWORD *)v45 + 38) + 8LL);
    --*(_DWORD *)(v72 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v72 + 8));
  }
  v73 = 1;
  Parameter = ((__int64 (__fastcall *)(struct IDispatch *, __int64, _QWORD))v118->lpVtbl[5].AddRef)(v118, 1, 0);
  if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 1) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_290;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
    {
      v15 = 6492;
      v16 = 6647817;
      goto LABEL_7;
    }
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
    v14 = 6647817;
    v103 = 6492;
    goto LABEL_5;
  }
  v74 = v132;
  if ( v132 || v110 )
  {
    v115 = 1;
    if ( v132 )
    {
      VariantClear(v132);
      *v74 = *pvarg;
    }
  }
  else
  {
    v73 = 0;
    v115 = 0;
  }
  v75 = v117;
  v76 = v117->cArgs - 1;
  while ( 2 )
  {
    v112 = (int)v76;
    if ( v73 >= cArgs )
    {
      CContext::FailedInvoke((CContext *)v125, &v116, a8, 0);
      goto LABEL_290;
    }
    vt = v75->rgvarg[v76].vt;
    Parameter = CParameters::GetParameter(v139, v73, &v128);
    if ( !CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
    {
      Parameter = (*(__int64 (__fastcall **)(struct CParameter *, int *))(*(_QWORD *)v128 + 120LL))(v128, &v114);
      if ( CContext::FailedInvoke((CContext *)v125, &Parameter, a8, 0) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_290;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
          v14 = 6681609;
          v103 = 6525;
          goto LABEL_5;
        }
        v15 = 6525;
        v16 = 6681609;
        goto LABEL_7;
      }
      v75 = v117;
      v78 = vt & 0xBFFF;
      if ( v78 == 10 || v117->rgvarg[v76].lVal == -2147352572 || (v114 & 2) == 0 )
        goto LABEL_275;
      v133 = &pvarg[v73];
      CVar::CVar((CVar *)v141, v133, 4u, 0);
      if ( (unsigned int)CContext::VariantFailed((CContext *)v125, (const struct CVar *)v141) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) == -1 )
          {
            bidTraceW(off_18012A1C0[0], 6690825, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", 6534);
          }
          else
          {
            v97 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
            bidTraceW(off_18012A1C0[0], 6690825, L"<CConnection::InvokeCommand|ADO|ERR> %u#, line %d\n", v97, 6534);
          }
        }
        v141[0] = &CVar::`vftable';
        v18 = (struct tagVARIANT *)v141;
        goto LABEL_37;
      }
      if ( v78 == 12 )
      {
        v95 = v117;
        CVar::DeepVariantClear(v117->rgvarg[v76].pvarVal);
        *v95->rgvarg[v76].bstrVal = v142 & 0xBFFF;
        CVar::UpdateVariant((CVar *)v141);
        v94 = CVar::Size(v96);
        v93 = (BSTR)(v95->rgvarg[v76].llVal + 8);
      }
      else
      {
        if ( v78 == 8209 && (v142 & 0xBFFF) == 0x2011 )
        {
          v80 = (SAFEARRAY *)*v117->rgvarg[v76].pllVal;
          if ( v80 && (v81 = v144, (int)CSafeArray::cDim(v144, v79) <= (signed int)v80->rgsabound[0].cElements) )
          {
            SafeArrayLock(v80);
            v83 = CSafeArray::cDim(v81, v82);
            pvData = v80->pvData;
            v85 = v83;
            v87 = CSafeArray::Lock(v86);
            memcpy_0(pvData, v87, v85);
            CSafeArray::UnlockAll(v81);
            SafeArrayUnlock(v80);
          }
          else
          {
            v116 |= 0x800A0D5D;
          }
          VariantClear(v133);
          v73 = v115;
          LODWORD(v76) = v112;
LABEL_274:
          v141[0] = &CVar::`vftable';
          CVar::Clear((CVar *)v141);
          v75 = v117;
LABEL_275:
          cArgs = CursorType;
          v115 = ++v73;
          v76 = (unsigned int)(v76 - 1);
          continue;
        }
        v88 = &v117->rgvarg[v76];
        bstrString = v88->bstrVal;
        CVar::DeepVariantClear(v88);
        v117->rgvarg[v76].llVal = (LONGLONG)bstrString;
        if ( (v142 & 0xBFFF) != v78 )
        {
          v90 = CVar::Coerce((CVar *)v141, v78, v89);
          v116 |= v90;
          VariantClear(v133);
        }
        v117->rgvarg[v76].vt = v78 | 0x4000;
        CVar::UpdateVariant((CVar *)v141);
        v92 = CVar::Size(v91);
        v93 = bstrString;
        v94 = v92;
      }
      memcpy_0(v93, Src, v94);
      goto LABEL_274;
    }
    break;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_290;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256)) != -1 )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)v11 + 256));
    v14 = 6680585;
    v103 = 6524;
    goto LABEL_5;
  }
  v15 = 6524;
  v16 = 6680585;
LABEL_7:
  bidTraceW(off_18012A1C0[0], v16, L"<CConnection::InvokeCommand|ADO|ERR>  line %d\n", v15);
LABEL_290:
  if ( v140 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
  if ( v122 )
    (*(void (__fastcall **)(CRecordset *))(*(_QWORD *)v122 + 16LL))(v122);
  if ( *((_BYTE *)g_pStaticGlobals + 72) && v113 )
  {
    CNfyContext::CNfyContext((CNfyContext *)v149, (struct IUnknown *)v11, 5, 0);
    v112 = adOpenDynamic;
    v159 = 3;
    LODWORD(v160) = 0;
    CNfyContext::SetError((CNfyContext *)v149, v116, 4u);
    v98 = *((_QWORD *)v11 + 34);
    v153 = 13;
    v155 = 16387;
    v156 = &v112;
    v165 = &v112;
    v151 = 13;
    v154 = v118;
    v152 = 0;
    if ( (!(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v98)
       || (int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                 v99,
                 &v123,
                 v149) >= 0)
      && (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(*((_QWORD *)v11 + 35)) )
    {
      v166 = 1;
      v150 = (char *)v11 + 8;
      CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
        v100,
        &v124,
        v149);
    }
    CNfyContext::~CNfyContext((CNfyContext *)v149);
  }
  if ( v118 )
    ((void (__fastcall *)(struct IDispatch *))v118->lpVtbl->Release)(v118);
  if ( pvarg )
    operator delete(pvarg);
  v101 = v127;
  CSysString::~CSysString((CSysString *)&v134);
  CContext::~CContext((CContext *)v125);
  return v101;
}

```

## disassembly

```asm
0x18006cfc0  push    rbp
0x18006cfc2  push    rbx
0x18006cfc3  push    rsi
0x18006cfc4  push    rdi
0x18006cfc5  push    r12
0x18006cfc7  push    r13
0x18006cfc9  push    r14
0x18006cfcb  push    r15
0x18006cfcd  lea     rbp, [rsp-228h]
0x18006cfd5  sub     rsp, 328h
0x18006cfdc  mov     rax, cs:__security_cookie
0x18006cfe3  xor     rax, rsp
0x18006cfe6  mov     [rbp+260h+var_50], rax
0x18006cfed  mov     rdi, [rbp+260h+arg_28]
0x18006cff4  lea     r8, [rcx+20h]
0x18006cff8  mov     rsi, [rbp+260h+arg_30]
0x18006cfff  mov     rax, rcx
0x18006d002  mov     r15, [rbp+260h+arg_38]
0x18006d009  mov     ebx, edx
0x18006d00b  neg     rax
0x18006d00e  mov     [rbp+260h+var_1A0], rcx
0x18006d015  mov     r14, rcx
0x18006d018  mov     [rbp+260h+var_2B8], rdi
0x18006d01c  sbb     rdx, rdx
0x18006d01f  mov     [rbp+260h+var_238], rsi
0x18006d023  and     rdx, r8
0x18006d026  lea     rcx, [rbp+260h+var_280]; this
0x18006d02a  mov     [rbp+260h+var_260], rdx
0x18006d02e  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x18006d033  xor     r13d, r13d
0x18006d036  mov     [rbp+260h+var_220], 7
0x18006d03a  mov     r12d, r13d
0x18006d03d  mov     [rbp+260h+var_2C0], r13d
0x18006d041  mov     [rbp+260h+pvarg], r13
0x18006d045  mov     [rbp+260h+var_2B0], r13
0x18006d049  mov     [rbp+260h+var_290], r13
0x18006d04d  mov     [rbp+260h+var_1D8], r13
0x18006d054  mov     [rbp+260h+var_228], r13
0x18006d058  mov     [rbp+260h+var_2D0], r13d
0x18006d05c  mov     [rbp+260h+var_240], 1
0x18006d063  mov     [rbp+260h+var_198], r13
0x18006d06a  mov     [rbp+260h+var_250], r13
0x18006d06e  mov     [rbp+260h+var_2C8], r13d
0x18006d072  mov     [rbp+260h+var_2CC], r13b
0x18006d076  mov     [rbp+260h+var_288], r13d
0x18006d07a  mov     [rbp+260h+var_284], r13d
0x18006d07e  cmp     [rdi+14h], r13d
0x18006d082  jz      loc_18006D112
0x18006d088  lea     rdx, [rbp+260h+var_2D0]; int *
0x18006d08c  mov     [rbp+260h+var_2D0], 80020007h
0x18006d093  lea     rcx, [rbp+260h+var_280]; this
0x18006d097  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18006d09c  test    byte ptr cs:_bidGblFlags, 2
0x18006d0a3  jz      loc_18006EA44
0x18006d0a9  lea     rbx, [r14+100h]
0x18006d0b0  mov     rcx, rbx; this
0x18006d0b3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d0b8  or      esi, 0FFFFFFFFh
0x18006d0bb  cmp     eax, esi
0x18006d0bd  jz      short loc_18006D0EF
0x18006d0bf  mov     rcx, rbx; this
0x18006d0c2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d0c7  mov     edx, 60E809h
0x18006d0cc  mov     [rsp+360h+var_340], 183Ah
0x18006d0d4  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18006d0db  lea     r8, aCconnectionInv; "<CConnection::InvokeCommand|ADO|ERR> %u"...
0x18006d0e2  mov     r9d, eax
0x18006d0e5  call    _bidTraceW
0x18006d0ea  jmp     loc_18006EA44
0x18006d0ef  mov     r9d, 183Ah
0x18006d0f5  mov     edx, 60E809h
0x18006d0fa  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18006d101  lea     r8, aCconnectionInv_0; "<CConnection::InvokeCommand|ADO|ERR>  l"...
0x18006d108  call    _bidTraceW
0x18006d10d  jmp     loc_18006EA44
0x18006d112  cmp     [r14+411h], r13b
0x18006d119  jz      short loc_18006D186
0x18006d11b  xor     r9d, r9d; bool
0x18006d11e  mov     [rbp+260h+var_2E0], 800A0E81h
0x18006d125  mov     r8, r15; struct tagEXCEPINFO *
0x18006d128  lea     rdx, [rbp+260h+var_2E0]; int *
0x18006d12c  lea     rcx, [rbp+260h+var_280]; this
0x18006d130  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x18006d135  test    al, al
0x18006d137  jz      short loc_18006D186
0x18006d139  test    byte ptr cs:_bidGblFlags, 2
0x18006d140  jz      loc_18006EA44
0x18006d146  lea     rbx, [r14+100h]
0x18006d14d  mov     rcx, rbx; this
0x18006d150  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d155  or      esi, 0FFFFFFFFh
0x18006d158  cmp     eax, esi
0x18006d15a  jz      short loc_18006D176
0x18006d15c  mov     rcx, rbx; this
0x18006d15f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d164  mov     edx, 60FC09h
0x18006d169  mov     [rsp+360h+var_340], 183Fh
0x18006d171  jmp     loc_18006D0D4
0x18006d176  mov     r9d, 183Fh
0x18006d17c  mov     edx, 60FC09h
0x18006d181  jmp     loc_18006D0FA
0x18006d186  cmp     [r14+186h], r13b
0x18006d18d  jnz     short loc_18006D1FA
0x18006d18f  xor     r9d, r9d; bool
0x18006d192  mov     [rbp+260h+var_2E0], 800A0E78h
0x18006d199  mov     r8, r15; struct tagEXCEPINFO *
0x18006d19c  lea     rdx, [rbp+260h+var_2E0]; int *
0x18006d1a0  lea     rcx, [rbp+260h+var_280]; this
0x18006d1a4  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x18006d1a9  test    al, al
0x18006d1ab  jz      short loc_18006D1FA
0x18006d1ad  test    byte ptr cs:_bidGblFlags, 2
0x18006d1b4  jz      loc_18006EA44
0x18006d1ba  lea     rbx, [r14+100h]
0x18006d1c1  mov     rcx, rbx; this
0x18006d1c4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d1c9  or      esi, 0FFFFFFFFh
0x18006d1cc  cmp     eax, esi
0x18006d1ce  jz      short loc_18006D1EA
0x18006d1d0  mov     rcx, rbx; this
0x18006d1d3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d1d8  mov     edx, 610809h
0x18006d1dd  mov     [rsp+360h+var_340], 1842h
0x18006d1e5  jmp     loc_18006D0D4
0x18006d1ea  mov     r9d, 1842h
0x18006d1f0  mov     edx, 610809h
0x18006d1f5  jmp     loc_18006D0FA
0x18006d1fa  mov     rcx, r14; this
0x18006d1fd  call    ?GetExecState@CConnection@@QEAADXZ; CConnection::GetExecState(void)
0x18006d202  test    al, al
0x18006d204  jz      short loc_18006D271
0x18006d206  xor     r9d, r9d; bool
0x18006d209  mov     [rbp+260h+var_2E0], 800A0E7Fh
0x18006d210  mov     r8, r15; struct tagEXCEPINFO *
0x18006d213  lea     rdx, [rbp+260h+var_2E0]; int *
0x18006d217  lea     rcx, [rbp+260h+var_280]; this
0x18006d21b  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x18006d220  test    al, al
0x18006d222  jz      short loc_18006D271
0x18006d224  test    byte ptr cs:_bidGblFlags, 2
0x18006d22b  jz      loc_18006EA44
0x18006d231  lea     rbx, [r14+100h]
0x18006d238  mov     rcx, rbx; this
0x18006d23b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d240  or      esi, 0FFFFFFFFh
0x18006d243  cmp     eax, esi
0x18006d245  jz      short loc_18006D261
0x18006d247  mov     rcx, rbx; this
0x18006d24a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d24f  mov     edx, 611409h
0x18006d254  mov     [rsp+360h+var_340], 1845h
0x18006d25c  jmp     loc_18006D0D4
0x18006d261  mov     r9d, 1845h
0x18006d267  mov     edx, 611409h
0x18006d26c  jmp     loc_18006D0FA
0x18006d271  lea     eax, [rbx-3E8h]
0x18006d277  movsxd  rdx, eax; void *
0x18006d27a  lea     rcx, [r14+278h]; this
0x18006d281  lea     r8, [rbp+260h+var_228]; struct CSysString *
0x18006d285  call    ?LookUpByData@CCollectionList@@QEAAJPEAXAEAVCSysString@@@Z; CCollectionList::LookUpByData(void *,CSysString &)
0x18006d28a  xor     r9d, r9d; bool
0x18006d28d  mov     [rbp+260h+var_2E0], eax
0x18006d290  mov     r8, r15; struct tagEXCEPINFO *
0x18006d293  lea     rdx, [rbp+260h+var_2E0]; int *
0x18006d297  lea     rcx, [rbp+260h+var_280]; this
0x18006d29b  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x18006d2a0  test    al, al
0x18006d2a2  jz      short loc_18006D2F1
0x18006d2a4  test    byte ptr cs:_bidGblFlags, 2
0x18006d2ab  jz      loc_18006EA44
0x18006d2b1  lea     rbx, [r14+100h]
0x18006d2b8  mov     rcx, rbx; this
0x18006d2bb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d2c0  or      esi, 0FFFFFFFFh
0x18006d2c3  cmp     eax, esi
0x18006d2c5  jz      short loc_18006D2E1
0x18006d2c7  mov     rcx, rbx; this
0x18006d2ca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d2cf  mov     edx, 613C09h
0x18006d2d4  mov     [rsp+360h+var_340], 184Fh
0x18006d2dc  jmp     loc_18006D0D4
0x18006d2e1  mov     r9d, 184Fh
0x18006d2e7  mov     edx, 613C09h
0x18006d2ec  jmp     loc_18006D0FA
0x18006d2f1  mov     r8b, 4; unsigned __int8
0x18006d2f4  lea     rdx, [rbp+260h+var_228]; struct CSysString *
0x18006d2f8  lea     rcx, [rbp+260h+var_190]; this
0x18006d2ff  call    ??0CVar@@QEAA@AEBVCSysString@@E@Z; CVar::CVar(CSysString const &,uchar)
0x18006d304  lea     rdx, [rbp+260h+var_190]; struct CVar *
0x18006d30b  lea     rcx, [rbp+260h+var_280]; this
0x18006d30f  call    ?VariantFailed@CContext@@QEAAHAEBVCVar@@@Z; CContext::VariantFailed(CVar const &)
0x18006d314  test    eax, eax
0x18006d316  jz      loc_18006D3A5
0x18006d31c  test    byte ptr cs:_bidGblFlags, 2
0x18006d323  jz      short loc_18006D386
0x18006d325  lea     rbx, [r14+100h]
0x18006d32c  mov     rcx, rbx; this
0x18006d32f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d334  or      esi, 0FFFFFFFFh
0x18006d337  cmp     eax, esi
0x18006d339  jz      short loc_18006D368
0x18006d33b  mov     rcx, rbx; this
0x18006d33e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d343  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18006d34a  lea     r8, aCconnectionInv; "<CConnection::InvokeCommand|ADO|ERR> %u"...
0x18006d351  mov     r9d, eax
0x18006d354  mov     [rsp+360h+var_340], 1853h
0x18006d35c  mov     edx, 614C09h
0x18006d361  call    _bidTraceW
0x18006d366  jmp     short loc_18006D386
0x18006d368  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18006d36f  lea     r8, aCconnectionInv_0; "<CConnection::InvokeCommand|ADO|ERR>  l"...
0x18006d376  mov     r9d, 1853h
0x18006d37c  mov     edx, 614C09h
0x18006d381  call    _bidTraceW
0x18006d386  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x18006d38d  mov     [rbp+260h+var_190], rax
0x18006d394  lea     rcx, [rbp+260h+var_190]; this
0x18006d39b  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x18006d3a0  jmp     loc_18006EA44
0x18006d3a5  lea     rcx, [rbp+260h+var_190]; this
0x18006d3ac  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x18006d3b1  movups  xmm0, [rbp+260h+var_180]
0x18006d3b8  lea     rcx, [r14+220h]; this
0x18006d3bf  movsd   xmm1, [rbp+260h+var_170]
0x18006d3c7  lea     r9, [rbp+260h+var_2B0]; void **
0x18006d3cb  lea     r8, IID_IADOCommand; struct _GUID *
0x18006d3d2  movaps  xmmword ptr [rbp+260h+var_210], xmm0
0x18006d3d6  lea     rdx, [rbp+260h+var_210]; struct tagVARIANT
0x18006d3da  movsd   qword ptr [rbp+260h+var_210+10h], xmm1
0x18006d3df  call    ?Item@CStdCollection@@UEAAJUtagVARIANT@@AEBU_GUID@@PEAPEAX@Z; CStdCollection::Item(tagVARIANT,_GUID const &,void * *)
0x18006d3e4  lea     r13, ??_7CVar@@6B@; const CVar::`vftable'
0x18006d3eb  mov     [rbp+260h+var_258], eax
0x18006d3ee  lea     rcx, [rbp+260h+var_190]; this
0x18006d3f5  mov     [rbp+260h+var_190], r13
0x18006d3fc  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x18006d401  mov     eax, [rbp+260h+var_258]
0x18006d404  test    eax, eax
0x18006d406  jns     loc_18006D4E1
0x18006d40c  cmp     eax, 800A0CC1h
0x18006d411  jz      short loc_18006D460
0x18006d413  test    byte ptr cs:_bidGblFlags, 2
0x18006d41a  jz      loc_18006EA44
0x18006d420  lea     rbx, [r14+100h]
0x18006d427  mov     rcx, rbx; this
0x18006d42a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d42f  or      esi, 0FFFFFFFFh
0x18006d432  cmp     eax, esi
0x18006d434  jz      short loc_18006D450
0x18006d436  mov     rcx, rbx; this
0x18006d439  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d43e  mov     edx, 616409h
0x18006d443  mov     [rsp+360h+var_340], 1859h
0x18006d44b  jmp     loc_18006D0D4
0x18006d450  mov     r9d, 1859h
0x18006d456  mov     edx, 616409h
0x18006d45b  jmp     loc_18006D0FA
0x18006d460  lea     r9, [rbp+260h+var_2B0]; struct _ADOCommand **
0x18006d464  xor     r8d, r8d; unsigned __int8
0x18006d467  lea     rdx, [rbp+260h+var_228]; struct CSysString *
0x18006d46b  mov     rcx, r14; struct _ADOConnection *
0x18006d46e  call    ?CreateCommand@@YAJPEAU_ADOConnection@@AEBVCSysString@@EPEAPEAU_ADOCommand@@@Z; CreateCommand(_ADOConnection *,CSysString const &,uchar,_ADOCommand * *)
0x18006d473  xor     r9d, r9d; bool
0x18006d476  mov     [rbp+260h+var_2E0], eax
0x18006d479  mov     r8, r15; struct tagEXCEPINFO *
0x18006d47c  lea     rdx, [rbp+260h+var_2E0]; int *
0x18006d480  lea     rcx, [rbp+260h+var_280]; this
0x18006d484  call    ?FailedInvoke@CContext@@QEAA_NAEBJPEAUtagEXCEPINFO@@_N@Z; CContext::FailedInvoke(long const &,tagEXCEPINFO *,bool)
0x18006d489  test    al, al
0x18006d48b  jz      short loc_18006D4DA
0x18006d48d  test    byte ptr cs:_bidGblFlags, 2
0x18006d494  jz      loc_18006EA44
0x18006d49a  lea     rbx, [r14+100h]
0x18006d4a1  mov     rcx, rbx; this
0x18006d4a4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d4a9  or      esi, 0FFFFFFFFh
0x18006d4ac  cmp     eax, esi
0x18006d4ae  jz      short loc_18006D4CA
0x18006d4b0  mov     rcx, rbx; this
0x18006d4b3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18006d4b8  mov     edx, 616C09h
0x18006d4bd  mov     [rsp+360h+var_340], 185Bh
0x18006d4c5  jmp     loc_18006D0D4
0x18006d4ca  mov     r9d, 185Bh
0x18006d4d0  mov     edx, 616C09h
0x18006d4d5  jmp     loc_18006D0FA
0x18006d4da  mov     ebx, 4
0x18006d4df  jmp     short loc_18006D4E4
0x18006d4e1  or      ebx, 0FFFFFFFFh
0x18006d4e4  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18006d4eb  xor     r11d, r11d
0x18006d4ee  mov     [rbp+260h+var_2C4], ebx
0x18006d4f1  cmp     [rax+48h], r11b
0x18006d4f5  jz      loc_18006D931
0x18006d4fb  mov     rcx, [r14+118h]
0x18006d502  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x18006d507  test    eax, eax
0x18006d509  jnz     short loc_18006D51F
0x18006d50b  mov     rcx, [r14+110h]
0x18006d512  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
  ... truncated ...
```
