# CCommandText::Execute(IUnknown *,_GUID const &,tagDBPARAMS *,__int64 *,IUnknown * *)

- ea: `0x180029cb0`
- end: `0x18002a90b`
- name: `?Execute@CCommandText@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAUtagDBPARAMS@@PEA_JPEAPEAU2@@Z`
- size: `3163`
- prototype: `int(CCommandText *__hidden this, struct IUnknown *, const struct _GUID *, struct tagDBPARAMS *, __int64 *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800100c4`
- `0x180013870`
- `0x180029560`
- `0x180029cb0`
- `0x18002a914`
- `0x18002a93c`
- `0x18002a994`
- `0x18002aba4`
- `0x18002b8ac`
- `0x18002c060`
- `0x18002ec0c`
- `0x180031ef8`
- `0x1800324c8`
- `0x18006ed60`
- `0x18006f554`
- `0x180073550`
- `0x1800772d4`
- `0x180077da4`
- `0x180078414`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002a3c0`
- `OLEAUT32!__imp_VariantInit` at `0x18002a430`
- `OLEAUT32!__imp_VariantInit` at `0x18002a3c0`
- `OLEAUT32!__imp_VariantInit` at `0x18002a430`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002a831`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002a831`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a89f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a89f`

## string_xrefs

- `0x180029dab`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a07e`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a09c`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a132`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a150`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a4c3`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a5a6`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a5c4`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a629`: `<CCommandText::Execute|OLEDB|ERR> `
- `0x18002a0b7`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a16b`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a279`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a4de`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a5df`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a644`: `<CCommandText::Execute|Trace|HR> `
- `0x18002a8cb`: `<CCommandText::Execute|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCommandText::Execute(
        void **this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct tagDBPARAMS *a4,
        __int64 *a5,
        struct IUnknown **a6)
{
  struct IUnknown **v9; // r15
  struct IUnknown *v10; // r12
  __int64 v11; // rax
  struct ICommand *Provider; // r13
  char *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  CCommandText *v21; // r12
  __int64 v22; // rax
  HRESULT (__stdcall *Execute)(ICommand *, IUnknown *, const IID *const, DBPARAMS *, DBROWCOUNT *, IUnknown **); // rax
  int v24; // r14d
  int Copy; // edi
  struct IUnknown *v26; // rdx
  int v27; // edi
  struct IUnknown *v28; // rdi
  struct IUnknown *v29; // r12
  __int64 v30; // rcx
  __int64 v31; // rax
  char v32; // r12
  CDPO *CDPO; // rax
  CDPO *v34; // rdi
  bool v35; // al
  bool v36; // cl
  char v37; // r8
  bool v38; // di
  char v39; // r13
  ULONG i; // r12d
  char *v41; // r12
  char v42; // dl
  bool v43; // cl
  int v44; // ebx
  const struct _GUID *v45; // r8
  struct IUnknown *v46; // rsi
  unsigned int v47; // edi
  int v48; // ebx
  const struct _GUID *v49; // r8
  CCommandText *v50; // rsi
  unsigned int v51; // ebx
  bool v52; // [rsp+48h] [rbp-1D0h]
  bool v53; // [rsp+70h] [rbp-1A8h]
  char v54; // [rsp+71h] [rbp-1A7h]
  char v55; // [rsp+72h] [rbp-1A6h]
  char v56; // [rsp+73h] [rbp-1A5h]
  unsigned int OLEDBServices; // [rsp+74h] [rbp-1A4h]
  unsigned int v58; // [rsp+74h] [rbp-1A4h]
  struct IUnknown *v59; // [rsp+78h] [rbp-1A0h] BYREF
  CDCM *RootAcm; // [rsp+80h] [rbp-198h] BYREF
  struct IUnknown *v61; // [rsp+88h] [rbp-190h]
  IErrorInfo *pperrinfo; // [rsp+90h] [rbp-188h] BYREF
  __int64 v63; // [rsp+98h] [rbp-180h] BYREF
  __int64 *v64; // [rsp+A0h] [rbp-178h]
  struct tagDBPARAMS *v65; // [rsp+A8h] [rbp-170h]
  struct IUnknown *v66; // [rsp+B0h] [rbp-168h]
  CCommandText *v67; // [rsp+B8h] [rbp-160h]
  int pExceptionObject; // [rsp+C0h] [rbp-158h] BYREF
  int v69; // [rsp+C4h] [rbp-154h] BYREF
  int v70; // [rsp+C8h] [rbp-150h] BYREF
  unsigned int v71; // [rsp+CCh] [rbp-14Ch] BYREF
  int v72; // [rsp+D0h] [rbp-148h] BYREF
  unsigned int v73; // [rsp+D4h] [rbp-144h] BYREF
  __int64 v74; // [rsp+D8h] [rbp-140h] BYREF
  char *v75; // [rsp+E0h] [rbp-138h]
  struct tagDBPROPSET *v76; // [rsp+E8h] [rbp-130h] BYREF
  __int64 v77; // [rsp+F0h] [rbp-128h]
  void **v78; // [rsp+F8h] [rbp-120h]
  struct ICommand *v79; // [rsp+100h] [rbp-118h]
  struct IUnknown **v80; // [rsp+108h] [rbp-110h]
  struct tagDBPROP v81; // [rsp+110h] [rbp-108h] BYREF
  tagDBPROPSET v82; // [rsp+160h] [rbp-B8h] BYREF
  struct tagDBPROP v83; // [rsp+180h] [rbp-98h] BYREF

  v65 = a4;
  v66 = a2;
  v67 = (CCommandText *)this;
  v78 = this;
  v64 = a5;
  v9 = a6;
  v80 = a6;
  v10 = 0;
  v61 = 0;
  v59 = 0;
  pperrinfo = 0;
  v63 = 0;
  memset(&v82, 0, sizeof(v82));
  memset_0(&v83, 0, sizeof(v83));
  v55 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a2 )
  {
    v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v11 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147217886, L"<CCommandText::Execute|OLEDB|ERR> ", 0x84u);
      return 2147749410LL;
    }
  }
  try
  {
    Provider = (struct ICommand *)GetProviderPointer<CCCM>(this[7], &IID_ICommand);
    v79 = Provider;
    pperrinfo = (IErrorInfo *)Provider;
    v77 = GetProviderPointer<CCCM>(this[7], &IID_ICommandProperties);
    v63 = v77;
    v14 = (char *)this[7];
    v75 = v14;
    RootAcm = CAcm::GetRootAcm((CAcm *)v14);
    *((_BYTE *)RootAcm + 616) = 0;
    v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  }
  catch ( long v73 )
  {
    v51 = v73;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v73, L"<CCommandText::Execute|OLEDB|ERR> ", 0x190u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8C28[0] )
          bidTraceA(off_1800C84B0[0], 410624, off_1800C8C28[0], v51);
      }
    }
    v58 = v51;
    goto LABEL_126;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147418113, L"<CCommandText::Execute|OLEDB|ERR> ", 0x197u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8C20[0] )
          bidTraceA(off_1800C84B0[0], 417792, off_1800C8C20[0], 0);
      }
    }
    v58 = -2147418113;
LABEL_126:
    if ( v59 )
    {
      ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl->Release)(v59);
      v59 = 0;
    }
    if ( v61 )
      ((void (__fastcall *)(struct IUnknown *))v61->lpVtbl->Release)(v61);
    if ( pperrinfo )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    if ( v63 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v9 = v80;
    if ( !v80 )
    {
      v47 = v58;
LABEL_143:
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(off_1800C84B0[0], 452617, L"<CCommandText::Execute|Trace|HR> ", v47);
      return v47;
    }
    if ( *v80 )
    {
      ((void (__fastcall *)(struct IUnknown *))(*v80)->lpVtbl->Release)(*v80);
      *v9 = 0;
    }
    v50 = (CCommandText *)v78;
    v47 = v58;
LABEL_138:
    if ( !*v9 )
    {
      if ( v55 )
      {
        v63 = 0;
        pperrinfo = 0;
        GetErrorInfo(0, &pperrinfo);
        v83.vValue.vt = 0;
        (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))v50 + 7))(
          *((_QWORD *)v50 + 7),
          &IID_ICommandProperties,
          &v63);
        (*(void (__fastcall **)(__int64, __int64, tagDBPROPSET *))(*(_QWORD *)v63 + 32LL))(v63, 1, &v82);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
        if ( pperrinfo )
        {
          SetErrorInfo(0, pperrinfo);
          ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
        }
      }
    }
    goto LABEL_143;
  }
  if ( !v15 || !a6 )
    goto LABEL_111;
  v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMDDataset.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMDDataset.Data1 )
    v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMDDataset.Data4;
  if ( !v16 )
    goto LABEL_111;
  v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMDFind.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMDFind.Data1 )
    v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMDFind.Data4;
  if ( !v17 )
    goto LABEL_111;
  v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IStream.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IStream.Data1 )
    v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IStream.Data4;
  if ( !v18 )
    goto LABEL_111;
  v19 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ISequentialStream.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ISequentialStream.Data1 )
    v19 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ISequentialStream.Data4;
  if ( !v19 || CRCM::IsRowIID(a3) )
  {
LABEL_111:
    v49 = a3;
    v46 = v66;
    v47 = ((__int64 (__fastcall *)(struct ICommand *, struct IUnknown *, const struct _GUID *, struct tagDBPARAMS *, __int64 *, struct IUnknown **))Provider->lpVtbl->Execute)(
            Provider,
            v66,
            v49,
            v65,
            v64,
            a6);
LABEL_112:
    if ( v59 )
    {
      ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl->Release)(v59);
      v59 = 0;
    }
    if ( v10 )
    {
      ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      v61 = 0;
    }
    if ( Provider )
    {
      ((void (__fastcall *)(struct ICommand *))Provider->lpVtbl->Release)(Provider);
      pperrinfo = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      v63 = 0;
    }
    if ( v46 && a6 && *a6 )
      AggregateCM(v46, *a6);
    if ( !a6 )
      goto LABEL_143;
    v50 = v67;
    goto LABEL_138;
  }
  v20 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMultipleResults.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMultipleResults.Data1 )
    v20 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMultipleResults.Data4;
  if ( v20 )
  {
    v53 = 1;
    v21 = v67;
    SetupCM<CCCM,CRCM>::SetupNewCM(*((void **)v67 + 7), (__int64)&v59);
  }
  else
  {
    SetupCM<CCCM,CMRCM>::SetupNewCM(this[7], (__int64)&v59);
    v53 = 0;
    v21 = v67;
  }
  v22 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IMultipleResults.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IMultipleResults.Data1 )
    v22 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IMultipleResults.Data4;
  if ( !v22 )
  {
LABEL_63:
    memset_0(&v81, 0, sizeof(v81));
    if ( !*((_DWORD *)v14 + 136) )
      goto LABEL_69;
    if ( *((_DWORD *)v14 + 136) != 1 )
      goto LABEL_68;
    v30 = *((_QWORD *)v14 + 67);
    v31 = *(_QWORD *)(v30 + 12) - *(_QWORD *)&DBPROPSET_ROWSET.Data1;
    if ( !v31 )
      v31 = *(_QWORD *)(v30 + 20) - *(_QWORD *)DBPROPSET_ROWSET.Data4;
    if ( v31 )
LABEL_68:
      v32 = 1;
    else
LABEL_69:
      v32 = 0;
    CDPO = CDCM::GetCDPO(RootAcm);
    v34 = CDPO;
    if ( !CDPO )
    {
      v48 = -2147418113;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147418113, L"<CCommandText::Execute|OLEDB|ERR> ", 0x11Fu);
        if ( (bidGblFlags & 2) != 0 )
          v48 = bidTraceHR(off_1800C84B0[0], 293897, L"<CCommandText::Execute|Trace|HR> ", 2147549183LL);
      }
      v72 = v48;
      throw (long *)&v72;
    }
    OLEDBServices = CDPO::GetOLEDBServices(CDPO);
    v56 = *(_BYTE *)(*((_QWORD *)v34 + 15) + 1080LL);
    if ( (OLEDBServices & 4) != 0 )
    {
      v35 = CDCM::DCMAllowsFoxCE(RootAcm);
      v36 = (OLEDBServices & 4) == 0;
      if ( !v35 )
        v36 = 1;
    }
    else
    {
      v36 = 1;
    }
    v37 = 0;
    v54 = 0;
    v38 = 1;
    if ( v32 || v36 )
      goto LABEL_101;
    v39 = 0;
    v76 = 0;
    CSupportedPropDispenser::GetAllSupportedFoxProps(
      (CSupportedPropDispenser *)(v75 + 328),
      (unsigned int *)&RootAcm,
      (const struct tagDBPROPSET **)&v76);
    for ( i = 0; i < v76->cProperties; ++i )
    {
      v81.dwPropertyID = v76->rgProperties[i].dwPropertyID;
      VariantInit(&v81.vValue);
      if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v75 + 184), &DBPROPSET_ROWSET, &v81) )
      {
        if ( v81.dwStatus )
        {
          if ( v81.vValue.iVal == -1 )
          {
            v54 = 1;
            if ( !v81.dwOptions )
              v39 = 1;
          }
        }
      }
    }
    v81.dwPropertyID = 260;
    VariantInit(&v81.vValue);
    v41 = v75;
    if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v75 + 480), &DBPROPSET_ROWSET, &v81) && !v81.dwOptions )
    {
      if ( v81.vValue.iVal )
      {
        v37 = 1;
        goto LABEL_91;
      }
      v38 = 0;
    }
    v37 = v54;
    if ( !v54 )
    {
LABEL_101:
      v52 = v37;
      Provider = v79;
      v10 = v61;
      v45 = a3;
      v46 = v66;
      v47 = CCommandText::DoExecute(v67, v66, v45, v65, v64, a6, v61, v79, OLEDBServices, v52, v38, v53, v56);
      if ( (v47 & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v47, L"<CCommandText::Execute|OLEDB|ERR> ", 0x17Eu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v47, L"<CCommandText::Execute|OLEDB|ERR> ", 0x17Eu);
            if ( (bidGblFlags & 2) != 0 )
              v47 = bidTraceHR(off_1800C84B0[0], 391177, L"<CCommandText::Execute|Trace|HR> ", v47);
          }
        }
        v71 = v47;
        throw (long *)&v71;
      }
      goto LABEL_112;
    }
LABEL_91:
    v42 = v41[472];
    if ( v42 || !v38 )
    {
      v43 = 0;
      if ( !v42 )
        v43 = v38;
      v38 = v43;
      if ( v39 )
      {
        v44 = -2147217887;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147217887, L"<CCommandText::Execute|OLEDB|ERR> ", 0x16Fu);
          if ( (bidGblFlags & 2) != 0 )
            v44 = bidTraceHR(off_1800C84B0[0], 375817, L"<CCommandText::Execute|Trace|HR> ", 2147749409LL);
        }
        v70 = v44;
        throw (long *)&v70;
      }
    }
    goto LABEL_101;
  }
  if ( SetPropertyForIID(a3, &v82, &v83) )
  {
    v74 = 0;
    (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))v21 + 7))(
      *((_QWORD *)v21 + 7),
      &IID_ICommandProperties,
      &v74);
    (*(void (__fastcall **)(__int64, __int64, tagDBPROPSET *))(*(_QWORD *)v74 + 32LL))(v74, 1, &v82);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v55 = 1;
    goto LABEL_63;
  }
  if ( *((_DWORD *)v14 + 136) )
    goto LABEL_63;
  RootAcm = 0;
  Execute = Provider->lpVtbl->Execute;
  if ( v53 )
  {
    v24 = ((__int64 (__fastcall *)(struct ICommand *, struct IUnknown *, GUID *, struct tagDBPARAMS *, __int64 *, CDCM **))Execute)(
            Provider,
            v59,
            &IID_IUnknown,
            v65,
            v64,
            &RootAcm);
    Copy = CDBPROPContainer::CreateCopy((CDBPROPContainer *)(v14 + 576), (struct CDBPROPContainer *)&v59[23]);
    if ( Copy < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(Copy, L"<CCommandText::Execute|OLEDB|ERR> ", 0xE0u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(Copy, L"<CCommandText::Execute|OLEDB|ERR> ", 0xE0u);
          if ( (bidGblFlags & 2) != 0 )
            Copy = bidTraceHR(off_1800C84B0[0], 229385, L"<CCommandText::Execute|Trace|HR> ", (unsigned int)Copy);
        }
      }
      pExceptionObject = Copy;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v24 = ((__int64 (__fastcall *)(struct ICommand *, _QWORD, GUID *, struct tagDBPARAMS *, __int64 *, CDCM **))Execute)(
            Provider,
            0,
            &IID_IMultipleResults,
            v65,
            v64,
            &RootAcm);
    v26 = v59;
    LOWORD(v59[44].lpVtbl) = 0;
    v27 = CDBPROPContainer::CreateCopy((CDBPROPContainer *)(v14 + 576), (struct CDBPROPContainer *)&v26[23]);
    if ( v27 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v27, L"<CCommandText::Execute|OLEDB|ERR> ", 0xECu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v27, L"<CCommandText::Execute|OLEDB|ERR> ", 0xECu);
          if ( (bidGblFlags & 2) != 0 )
            v27 = bidTraceHR(off_1800C84B0[0], 241673, L"<CCommandText::Execute|Trace|HR> ", (unsigned int)v27);
        }
      }
      v69 = v27;
      throw (long *)&v69;
    }
  }
  if ( v24 >= 0 && RootAcm )
  {
    ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl[1].QueryInterface)(v59);
    v28 = v61;
    v29 = v66;
    v24 = CMQI(a3, v66, v59, v61, a6);
    (*(void (__fastcall **)(CDCM *))(*(_QWORD *)RootAcm + 16LL))(RootAcm);
  }
  else
  {
    v28 = v61;
    v29 = v66;
  }
  ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl->Release)(v59);
  ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  ((void (__fastcall *)(struct ICommand *))Provider->lpVtbl->Release)(Provider);
  if ( v29 && *a6 )
    AggregateCM(v29, *a6);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84B0[0], 265225, L"<CCommandText::Execute|Trace|HR> ", (unsigned int)v24);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180029cb0  push    rbx
0x180029cb2  push    rsi
0x180029cb3  push    rdi
0x180029cb4  push    r12
0x180029cb6  push    r13
0x180029cb8  push    r14
0x180029cba  push    r15
0x180029cbc  sub     rsp, 1E0h
0x180029cc3  mov     rax, cs:__security_cookie
0x180029cca  xor     rax, rsp
0x180029ccd  mov     [rsp+218h+var_48], rax
0x180029cd5  mov     [rsp+218h+var_170], r9
0x180029cdd  mov     rsi, r8
0x180029ce0  mov     rdi, rdx
0x180029ce3  mov     [rsp+218h+var_168], rdx
0x180029ceb  mov     r14, rcx
0x180029cee  mov     [rsp+218h+var_160], rcx
0x180029cf6  mov     [rsp+218h+var_120], rcx
0x180029cfe  mov     r13, [rsp+218h+arg_20]
0x180029d06  mov     [rsp+218h+var_178], r13
0x180029d0e  mov     r15, [rsp+218h+arg_28]
0x180029d16  mov     [rsp+218h+var_110], r15
0x180029d1e  xor     ebx, ebx
0x180029d20  mov     r12d, ebx
0x180029d23  mov     [rsp+218h+var_190], rbx
0x180029d2b  mov     [rsp+218h+var_1A0], rbx
0x180029d30  mov     [rsp+218h+pperrinfo], rbx
0x180029d38  mov     [rsp+218h+var_180], rbx
0x180029d40  xorps   xmm0, xmm0
0x180029d43  movups  xmmword ptr [rsp+218h+var_B8.rgProperties], xmm0
0x180029d4b  movups  xmmword ptr [rsp+218h+var_B8.guidPropertySet.Data2], xmm0
0x180029d53  xor     edx, edx; Val
0x180029d55  lea     r8d, [rbx+48h]; Size
0x180029d59  lea     rcx, [rsp+218h+var_98]; void *
0x180029d61  call    memset_0
0x180029d66  mov     [rsp+218h+var_1A6], bl
0x180029d6a  test    r13, r13
0x180029d6d  jz      short loc_180029D73
0x180029d6f  mov     [r13+0], rbx
0x180029d73  test    r15, r15
0x180029d76  jz      short loc_180029D7B
0x180029d78  mov     [r15], rbx
0x180029d7b  test    rdi, rdi
0x180029d7e  jz      short loc_180029DC6
0x180029d80  mov     rax, [rsi]
0x180029d83  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180029d8a  jnz     short loc_180029D97
0x180029d8c  mov     rax, [rsi+8]
0x180029d90  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180029d97  test    rax, rax
0x180029d9a  jz      short loc_180029DC6
0x180029d9c  test    byte ptr cs:_bidGblFlags, 2
0x180029da3  jz      short loc_180029DBC
0x180029da5  mov     r8d, 84h; unsigned int
0x180029dab  lea     rdx, aCcommandtextEx; "<CCommandText::Execute|OLEDB|ERR> "
0x180029db2  mov     ecx, 80040E22h; int
0x180029db7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180029dbc  mov     eax, 80040E22h
0x180029dc1  jmp     loc_18002A8E7
0x180029dc6  lea     rdx, IID_ICommand
0x180029dcd  mov     rcx, [r14+38h]
0x180029dd1  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x180029dd6  mov     r13, rax
0x180029dd9  mov     [rsp+218h+var_118], rax
0x180029de1  mov     [rsp+218h+pperrinfo], rax
0x180029de9  lea     rdx, IID_ICommandProperties
0x180029df0  mov     rcx, [r14+38h]
0x180029df4  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x180029df9  mov     [rsp+218h+var_128], rax
0x180029e01  mov     [rsp+218h+var_180], rax
0x180029e09  mov     rdi, [r14+38h]
0x180029e0d  mov     [rsp+218h+var_138], rdi
0x180029e15  mov     rcx, rdi; this
0x180029e18  call    ?GetRootAcm@CAcm@@QEAAPEAV1@XZ; CAcm::GetRootAcm(void)
0x180029e1d  mov     [rsp+218h+var_198], rax
0x180029e25  mov     [rax+268h], bl
0x180029e2b  mov     rcx, [rsi]
0x180029e2e  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x180029e35  jnz     short loc_180029E42
0x180029e37  mov     rcx, [rsi+8]
0x180029e3b  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x180029e42  test    rcx, rcx
0x180029e45  jz      loc_18002A679
0x180029e4b  test    r15, r15
0x180029e4e  jz      loc_18002A679
0x180029e54  mov     rax, [rsi]
0x180029e57  sub     rax, qword ptr cs:IID_IMDDataset.Data1
0x180029e5e  jnz     short loc_180029E6B
0x180029e60  mov     rax, [rsi+8]
0x180029e64  sub     rax, qword ptr cs:IID_IMDDataset.Data4
0x180029e6b  test    rax, rax
0x180029e6e  jz      loc_18002A679
0x180029e74  mov     rax, [rsi]
0x180029e77  sub     rax, qword ptr cs:IID_IMDFind.Data1
0x180029e7e  jnz     short loc_180029E8B
0x180029e80  mov     rax, [rsi+8]
0x180029e84  sub     rax, qword ptr cs:IID_IMDFind.Data4
0x180029e8b  test    rax, rax
0x180029e8e  jz      loc_18002A679
0x180029e94  mov     rax, [rsi]
0x180029e97  sub     rax, qword ptr cs:IID_IStream.Data1
0x180029e9e  jnz     short loc_180029EAB
0x180029ea0  mov     rax, [rsi+8]
0x180029ea4  sub     rax, qword ptr cs:IID_IStream.Data4
0x180029eab  test    rax, rax
0x180029eae  jz      loc_18002A679
0x180029eb4  mov     rax, [rsi]
0x180029eb7  sub     rax, qword ptr cs:IID_ISequentialStream.Data1
0x180029ebe  jnz     short loc_180029ECB
0x180029ec0  mov     rax, [rsi+8]
0x180029ec4  sub     rax, qword ptr cs:IID_ISequentialStream.Data4
0x180029ecb  test    rax, rax
0x180029ece  jz      loc_18002A679
0x180029ed4  mov     rcx, rsi; struct _GUID *
0x180029ed7  call    ?IsRowIID@CRCM@@SA_NAEBU_GUID@@@Z; CRCM::IsRowIID(_GUID const &)
0x180029edc  test    al, al
0x180029ede  jnz     loc_18002A679
0x180029ee4  mov     rax, [rsi]
0x180029ee7  sub     rax, qword ptr cs:IID_IMultipleResults.Data1
0x180029eee  jnz     short loc_180029EFB
0x180029ef0  mov     rax, [rsi+8]
0x180029ef4  sub     rax, qword ptr cs:IID_IMultipleResults.Data4
0x180029efb  lea     r9, [rsp+218h+var_190]
0x180029f03  test    rax, rax
0x180029f06  lea     rax, [rsp+218h+var_1A0]
0x180029f0b  mov     [rsp+218h+var_1F8], rax; __int64
0x180029f10  jnz     short loc_180029F2F
0x180029f12  mov     rcx, [r14+38h]; void *
0x180029f16  call    ?SetupNewCM@?$SetupCM@VCCCM@@VCMRCM@@@@SAJPEAV?$CComObject@VCCCM@@@ATL@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@PEAPEAUIService@@@Z; SetupCM<CCCM,CMRCM>::SetupNewCM(ATL::CComObject<CCCM> *,IUnknown *,_GUID const &,IUnknown * *,IService * *)
0x180029f1b  mov     [rsp+218h+var_1A8], bl
0x180029f1f  mov     r14d, 1
0x180029f25  mov     r12, [rsp+218h+var_160]
0x180029f2d  jmp     short loc_180029F4C
0x180029f2f  mov     r14d, 1
0x180029f35  mov     [rsp+218h+var_1A8], r14b
0x180029f3a  mov     r12, [rsp+218h+var_160]
0x180029f42  mov     rcx, [r12+38h]; void *
0x180029f47  call    ?SetupNewCM@?$SetupCM@VCCCM@@VCRCM@@@@SAJPEAV?$CComObject@VCCCM@@@ATL@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@PEAPEAUIService@@@Z; SetupCM<CCCM,CRCM>::SetupNewCM(ATL::CComObject<CCCM> *,IUnknown *,_GUID const &,IUnknown * *,IService * *)
0x180029f4c  mov     rax, [rsi]
0x180029f4f  sub     rax, qword ptr cs:IID_IMultipleResults.Data1
0x180029f56  jnz     short loc_180029F63
0x180029f58  mov     rax, [rsi+8]
0x180029f5c  sub     rax, qword ptr cs:IID_IMultipleResults.Data4
0x180029f63  test    rax, rax
0x180029f66  jz      loc_18002A29C
0x180029f6c  lea     r8, [rsp+218h+var_98]; struct tagDBPROP *
0x180029f74  lea     rdx, [rsp+218h+var_B8]; struct tagDBPROPSET *
0x180029f7c  mov     rcx, rsi; struct _GUID *
0x180029f7f  call    ?SetPropertyForIID@@YA_NAEBU_GUID@@AEAUtagDBPROPSET@@AEAUtagDBPROP@@@Z; SetPropertyForIID(_GUID const &,tagDBPROPSET &,tagDBPROP &)
0x180029f84  test    al, al
0x180029f86  jz      short loc_180029FEC
0x180029f88  mov     [rsp+218h+var_140], rbx
0x180029f90  mov     rcx, [r12+38h]
0x180029f95  mov     rax, [rcx]
0x180029f98  lea     r8, [rsp+218h+var_140]
0x180029fa0  lea     rdx, IID_ICommandProperties
0x180029fa7  mov     rax, [rax]
0x180029faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029faf  mov     rcx, [rsp+218h+var_140]
0x180029fb7  mov     rax, [rcx]
0x180029fba  lea     r8, [rsp+218h+var_B8]
0x180029fc2  mov     edx, r14d
0x180029fc5  mov     rax, [rax+20h]
0x180029fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fce  mov     rcx, [rsp+218h+var_140]
0x180029fd6  mov     rax, [rcx]
0x180029fd9  mov     rax, [rax+10h]
0x180029fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fe2  mov     [rsp+218h+var_1A6], r14b
0x180029fe7  jmp     loc_18002A29C
0x180029fec  cmp     [rdi+220h], ebx
0x180029ff2  jnz     loc_18002A29C
0x180029ff8  mov     [rsp+218h+var_198], rbx
0x18002a000  mov     rax, [r13+0]
0x18002a004  mov     rax, [rax+20h]
0x18002a008  lea     rcx, [rsp+218h+var_198]
0x18002a010  mov     r9, [rsp+218h+var_170]
0x18002a018  mov     [rsp+218h+var_1F0], rcx
0x18002a01d  mov     rcx, [rsp+218h+var_178]
0x18002a025  mov     [rsp+218h+var_1F8], rcx
0x18002a02a  mov     rcx, r13
0x18002a02d  cmp     [rsp+218h+var_1A8], 0
0x18002a032  jz      loc_18002A0EC
0x18002a038  lea     r8, IID_IUnknown
0x18002a03f  mov     rdx, [rsp+218h+var_1A0]
0x18002a044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a049  mov     r14d, eax
0x18002a04c  mov     rdx, [rsp+218h+var_1A0]
0x18002a051  add     rdx, 0B8h; struct CDBPROPContainer *
0x18002a058  lea     rcx, [rdi+240h]; this
0x18002a05f  call    ?CreateCopy@CDBPROPContainer@@QEAAJAEAV1@@Z; CDBPROPContainer::CreateCopy(CDBPROPContainer &)
0x18002a064  mov     edi, eax
0x18002a066  test    eax, eax
0x18002a068  jns     loc_18002A1A0
0x18002a06e  mov     eax, cs:_bidGblFlags
0x18002a074  test    al, 2
0x18002a076  jz      short loc_18002A0D1
0x18002a078  mov     r8d, 0E0h; unsigned int
0x18002a07e  lea     rdx, aCcommandtextEx; "<CCommandText::Execute|OLEDB|ERR> "
0x18002a085  mov     ecx, edi; int
0x18002a087  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002a08c  mov     eax, cs:_bidGblFlags
0x18002a092  test    al, 2
0x18002a094  jz      short loc_18002A0D1
0x18002a096  mov     r8d, 0E0h; unsigned int
0x18002a09c  lea     rdx, aCcommandtextEx; "<CCommandText::Execute|OLEDB|ERR> "
0x18002a0a3  mov     ecx, edi; int
0x18002a0a5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002a0aa  mov     eax, cs:_bidGblFlags
0x18002a0b0  test    al, 2
0x18002a0b2  jz      short loc_18002A0D1
0x18002a0b4  mov     r9d, edi
0x18002a0b7  lea     r8, aCcommandtextEx_2; "<CCommandText::Execute|Trace|HR> "
0x18002a0be  mov     edx, 38009h
0x18002a0c3  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18002a0ca  call    _bidTraceHR
0x18002a0cf  mov     edi, eax
0x18002a0d1  mov     [rsp+218h+pExceptionObject], edi
0x18002a0d8  lea     rdx, _TI1J; pThrowInfo
0x18002a0df  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x18002a0e7  call    _CxxThrowException_0
0x18002a0ec  lea     r8, IID_IMultipleResults
0x18002a0f3  xor     edx, edx
0x18002a0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0fa  mov     r14d, eax
0x18002a0fd  mov     rdx, [rsp+218h+var_1A0]
0x18002a102  mov     [rdx+160h], bx
0x18002a109  add     rdx, 0B8h; struct CDBPROPContainer *
0x18002a110  lea     rcx, [rdi+240h]; this
0x18002a117  call    ?CreateCopy@CDBPROPContainer@@QEAAJAEAV1@@Z; CDBPROPContainer::CreateCopy(CDBPROPContainer &)
0x18002a11c  mov     edi, eax
0x18002a11e  test    eax, eax
0x18002a120  jns     short loc_18002A1A0
0x18002a122  mov     eax, cs:_bidGblFlags
0x18002a128  test    al, 2
0x18002a12a  jz      short loc_18002A185
0x18002a12c  mov     r8d, 0ECh; unsigned int
0x18002a132  lea     rdx, aCcommandtextEx; "<CCommandText::Execute|OLEDB|ERR> "
0x18002a139  mov     ecx, edi; int
0x18002a13b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002a140  mov     eax, cs:_bidGblFlags
0x18002a146  test    al, 2
0x18002a148  jz      short loc_18002A185
0x18002a14a  mov     r8d, 0ECh; unsigned int
0x18002a150  lea     rdx, aCcommandtextEx; "<CCommandText::Execute|OLEDB|ERR> "
0x18002a157  mov     ecx, edi; int
0x18002a159  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002a15e  mov     eax, cs:_bidGblFlags
0x18002a164  test    al, 2
0x18002a166  jz      short loc_18002A185
0x18002a168  mov     r9d, edi
0x18002a16b  lea     r8, aCcommandtextEx_2; "<CCommandText::Execute|Trace|HR> "
0x18002a172  mov     edx, 3B009h
0x18002a177  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18002a17e  call    _bidTraceHR
0x18002a183  mov     edi, eax
0x18002a185  mov     [rsp+218h+var_154], edi
0x18002a18c  lea     rdx, _TI1J; pThrowInfo
0x18002a193  lea     rcx, [rsp+218h+var_154]; pExceptionObject
0x18002a19b  call    _CxxThrowException_0
0x18002a1a0  test    r14d, r14d
0x18002a1a3  js      short loc_18002A204
0x18002a1a5  mov     rdx, [rsp+218h+var_198]
0x18002a1ad  test    rdx, rdx
0x18002a1b0  jz      short loc_18002A204
0x18002a1b2  mov     rcx, [rsp+218h+var_1A0]
0x18002a1b7  mov     rax, [rcx]
0x18002a1ba  mov     rax, [rax+18h]
0x18002a1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1c3  mov     [rsp+218h+var_1F8], r15; struct IUnknown **
0x18002a1c8  mov     rdi, [rsp+218h+var_190]
0x18002a1d0  mov     r9, rdi; struct IUnknown *
0x18002a1d3  mov     r8, [rsp+218h+var_1A0]; struct IUnknown *
0x18002a1d8  mov     r12, [rsp+218h+var_168]
0x18002a1e0  mov     rdx, r12; struct IUnknown *
0x18002a1e3  mov     rcx, rsi; struct _GUID *
0x18002a1e6  call    ?CMQI@@YAJAEBU_GUID@@PEAUIUnknown@@11PEAPEAU2@@Z; CMQI(_GUID const &,IUnknown *,IUnknown *,IUnknown *,IUnknown * *)
0x18002a1eb  mov     r14d, eax
0x18002a1ee  mov     rcx, [rsp+218h+var_198]
0x18002a1f6  mov     rax, [rcx]
0x18002a1f9  mov     rax, [rax+10h]
0x18002a1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a202  jmp     short loc_18002A214
0x18002a204  mov     rdi, [rsp+218h+var_190]
0x18002a20c  mov     r12, [rsp+218h+var_168]
0x18002a214  mov     rcx, [rsp+218h+var_1A0]
0x18002a219  mov     rax, [rcx]
0x18002a21c  mov     rax, [rax+10h]
0x18002a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a225  mov     rax, [rdi]
0x18002a228  mov     rcx, rdi
0x18002a22b  mov     rax, [rax+10h]
0x18002a22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a234  mov     rcx, [rsp+218h+var_128]
0x18002a23c  mov     rax, [rcx]
0x18002a23f  mov     rax, [rax+10h]
0x18002a243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a248  mov     rax, [r13+0]
0x18002a24c  mov     rcx, r13
0x18002a24f  mov     rax, [rax+10h]
  ... truncated ...
```
