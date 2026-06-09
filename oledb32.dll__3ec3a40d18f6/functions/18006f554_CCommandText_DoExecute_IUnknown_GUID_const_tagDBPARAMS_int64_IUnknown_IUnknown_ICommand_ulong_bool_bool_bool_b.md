# CCommandText::DoExecute(IUnknown *,_GUID const &,tagDBPARAMS *,__int64 *,IUnknown * *,IUnknown *,ICommand *,ulong,bool,bool,bool,bool)

- ea: `0x18006f554`
- end: `0x180070699`
- name: `?DoExecute@CCommandText@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAUtagDBPARAMS@@PEA_JPEAPEAU2@0PEAUICommand@@K_N666@Z`
- size: `4421`
- prototype: `__int64 __fastcall(CCommandText *__hidden this, struct IUnknown *, const struct _GUID *, struct tagDBPARAMS *, __int64 *, struct IUnknown **, struct IUnknown *, struct ICommand *, unsigned int, bool, bool, bool, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180029cb0`

## callees

- `0x18000feec`
- `0x1800100c4`
- `0x180011bf0`
- `0x180013870`
- `0x180029560`
- `0x18002a994`
- `0x18002b8ac`
- `0x18002ec0c`
- `0x1800324c8`
- `0x18006da24`
- `0x18006e3b0`
- `0x18006ed60`
- `0x18006f554`
- `0x18007e6ca`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18006f8ae`
- `OLEAUT32!__imp_VariantClear` at `0x18006f8ae`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006f908`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006f9f3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006ffa4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006f908`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006f9f3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18006ffa4`
- `ole32!CoCreateInstance` at `0x18006fc93`
- `ole32!CoCreateInstance` at `0x18006fc93`

## string_xrefs

- `0x18006f61b`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006f639`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006f7ff`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006f81d`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006f959`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fa33`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fba9`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fbc7`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fcb3`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fcd1`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fd5b`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fd79`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fe09`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fe27`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006feba`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006fed8`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18007002e`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x180070050`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x1800700a2`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x1800701aa`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x180070233`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x180070314`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x180070336`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x1800703c1`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x1800703df`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x1800704f4`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x180070512`: `<CCommandText::DoExecute|OLEDB|ERR> `
- `0x18006f658`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006f83c`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006f978`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fa52`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fbe6`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fcf0`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fd98`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fe46`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18006fef7`: `<CCommandText::DoExecute|Trace|HR> `
- `0x180070073`: `<CCommandText::DoExecute|Trace|HR> `
- `0x1800700c1`: `<CCommandText::DoExecute|Trace|HR> `
- `0x1800701c9`: `<CCommandText::DoExecute|Trace|HR> `
- `0x180070252`: `<CCommandText::DoExecute|Trace|HR> `
- `0x180070359`: `<CCommandText::DoExecute|Trace|HR> `
- `0x1800703fe`: `<CCommandText::DoExecute|Trace|HR> `
- `0x180070531`: `<CCommandText::DoExecute|Trace|HR> `
- `0x18007066a`: `<CCommandText::DoExecute|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CCommandText::DoExecute(
        CCommandText *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct tagDBPARAMS *a4,
        __int64 *a5,
        struct IUnknown **a6,
        struct IUnknown *a7,
        struct ICommand *a8,
        unsigned int a9,
        bool a10,
        bool a11,
        bool a12,
        bool a13)
{
  struct tagDBPARAMS *v13; // rdi
  CCommandText *v14; // r12
  struct ICommand *v15; // rsi
  int v16; // ebx
  __int64 v17; // r13
  bool v18; // r14
  bool v19; // si
  IErrorInfo *Provider; // r14
  int v21; // ebx
  struct tagDBPROPSET *v22; // rdi
  unsigned int v23; // r12d
  unsigned int v24; // r13d
  DBPROP *rgProperties; // rbx
  ULONG i; // r14d
  int v27; // eax
  unsigned int v28; // edi
  int v29; // ebx
  HRESULT (__stdcall *GetSource)(IErrorInfo *, BSTR *); // rax
  struct tagDBPROPSET near **v31; // r8
  __int64 v32; // rdx
  int v33; // edi
  HRESULT (__stdcall *Execute)(ICommand *, IUnknown *, const IID *const, DBPARAMS *, DBROWCOUNT *, IUnknown **); // r10
  unsigned int v35; // edi
  CAcm *v36; // rsi
  char v37; // r14
  int v38; // esi
  HRESULT Instance; // edi
  int v40; // edi
  int v41; // edi
  int v42; // edi
  unsigned int v43; // r12d
  __int64 v44; // rsi
  const struct _GUID *v45; // r14
  int v46; // eax
  unsigned int v47; // ebx
  int InheritedAccessors; // ebx
  char v49; // r8
  char v50; // r9
  char v51; // r14
  unsigned int v52; // r11d
  _DWORD *v53; // rcx
  unsigned int j; // r10d
  CAcm *v55; // rsi
  int v56; // ebx
  int inserted; // ebx
  int v58; // ebx
  CAcm *v60; // rbx
  __int64 v61; // rbx
  bool ppv; // [rsp+20h] [rbp-168h]
  int v63; // [rsp+40h] [rbp-148h]
  char v64; // [rsp+44h] [rbp-144h]
  struct IUnknown *v65; // [rsp+48h] [rbp-140h] BYREF
  struct IUnknown *v66; // [rsp+50h] [rbp-138h] BYREF
  __int64 v67; // [rsp+58h] [rbp-130h] BYREF
  struct tagDBPROPSET *v68; // [rsp+60h] [rbp-128h] BYREF
  LPUNKNOWN pUnkOuter; // [rsp+68h] [rbp-120h] BYREF
  CAcm *v70; // [rsp+70h] [rbp-118h]
  IErrorInfo *v71; // [rsp+78h] [rbp-110h] BYREF
  __int64 v72; // [rsp+80h] [rbp-108h] BYREF
  struct IUnknown *v73; // [rsp+88h] [rbp-100h] BYREF
  __int64 v74; // [rsp+90h] [rbp-F8h]
  int pExceptionObject; // [rsp+98h] [rbp-F0h] BYREF
  int v76; // [rsp+9Ch] [rbp-ECh] BYREF
  unsigned int v77; // [rsp+A0h] [rbp-E8h] BYREF
  int v78; // [rsp+A4h] [rbp-E4h] BYREF
  int v79; // [rsp+A8h] [rbp-E0h] BYREF
  HRESULT v80; // [rsp+ACh] [rbp-DCh] BYREF
  int v81; // [rsp+B0h] [rbp-D8h] BYREF
  int v82; // [rsp+B4h] [rbp-D4h] BYREF
  int v83; // [rsp+B8h] [rbp-D0h] BYREF
  int v84; // [rsp+BCh] [rbp-CCh] BYREF
  int v85; // [rsp+C0h] [rbp-C8h] BYREF
  int v86; // [rsp+C4h] [rbp-C4h] BYREF
  unsigned int v87; // [rsp+C8h] [rbp-C0h] BYREF
  int v88; // [rsp+CCh] [rbp-BCh] BYREF
  int v89; // [rsp+D0h] [rbp-B8h] BYREF
  int v90; // [rsp+D4h] [rbp-B4h] BYREF
  IErrorInfo *v91; // [rsp+D8h] [rbp-B0h]
  struct _GUID v92; // [rsp+E0h] [rbp-A8h] BYREF
  __int64 v93; // [rsp+F0h] [rbp-98h]
  struct tagDBPROP v94; // [rsp+100h] [rbp-88h] BYREF

  v13 = a4;
  v14 = this;
  v65 = 0;
  v91 = 0;
  v71 = 0;
  v67 = 0;
  v93 = 0;
  v70 = 0;
  v73 = 0;
  v74 = 0;
  pUnkOuter = 0;
  v72 = 0;
  v64 = 0;
  v15 = a8;
  try
  {
    ((void (*)(void))a8->lpVtbl->AddRef)();
    v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a7->lpVtbl->QueryInterface)(
            a7,
            &IID_IService,
            &v65);
    if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v16, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x20Du);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v16, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x20Du);
          if ( (bidGblFlags & 2) != 0 )
            v16 = bidTraceHR(off_1800C84B0[0], 537609, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v16);
        }
      }
      pExceptionObject = v16;
      throw (long *)&pExceptionObject;
    }
    v17 = *((_QWORD *)v14 + 7);
    *(_QWORD *)&v92.Data1 = v17;
    v93 = v17;
    if ( a12 )
      v70 = (CAcm *)v65;
    else
      v73 = v65;
    v18 = a11;
    if ( !a10 || !a11 )
    {
      v29 = -2147217887;
      goto LABEL_59;
    }
    memset_0(&v94, 0, sizeof(v94));
    v94.dwPropertyID = 127;
    if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v17 + 480), &DBPROPSET_ROWSET, &v94)
      && v94.vValue.vt == 11
      && v94.vValue.iVal == -1 )
    {
      v19 = 1;
    }
    else
    {
      v19 = 0;
      v94.dwPropertyID = 134;
      if ( CDBPROPContainer::GetProperty((CDBPROPContainer *)(v17 + 480), &DBPROPSET_ROWSET, &v94)
        && v94.vValue.vt == 11 )
      {
        v19 = v94.vValue.iVal == 0xFFFF;
      }
    }
    Provider = (IErrorInfo *)GetProviderPointer<CCCM>(*((_QWORD *)v14 + 7), &IID_ICommandProperties);
    v91 = Provider;
    v71 = Provider;
    LODWORD(v66) = 0;
    v68 = 0;
    v21 = CreateMPMallocCopyOfProps(
            *(_DWORD *)(v17 + 544),
            *(struct tagDBPROPSET **)(v17 + 536),
            (unsigned int *)&v66,
            &v68,
            ppv);
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v21, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x238u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v21, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x238u);
          if ( (bidGblFlags & 2) != 0 )
            v21 = bidTraceHR(off_1800C84B0[0], 581641, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v21);
        }
      }
      v76 = v21;
      throw (long *)&v76;
    }
    v22 = v68;
    v23 = 0;
    v24 = (unsigned int)v66;
    if ( (_DWORD)v66 )
    {
      do
      {
        rgProperties = v22->rgProperties;
        for ( i = 0; i < v22->cProperties; ++rgProperties )
        {
          if ( rgProperties->dwPropertyID != 73
            && rgProperties->dwPropertyID != 238
            && rgProperties->dwPropertyID != 217 )
          {
            VariantClear(&rgProperties->vValue);
            rgProperties->dwOptions = 1;
          }
          ++i;
        }
        ++v23;
        ++v22;
      }
      while ( v23 < v24 );
      Provider = v91;
    }
    v27 = ((__int64 (__fastcall *)(IErrorInfo *, _QWORD, struct tagDBPROPSET *))Provider->lpVtbl->GetSource)(
            Provider,
            v24,
            v68);
    v28 = v27;
    v64 = 1;
    v29 = -2147217887;
    if ( v27 < 0 )
    {
      if ( v27 != -2147217887 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v27, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x258u);
          if ( (bidGblFlags & 2) != 0 )
            v28 = bidTraceHR(off_1800C84B0[0], 614409, L"<CCommandText::DoExecute|Trace|HR> ", v28);
        }
        v77 = v28;
        throw (long *)&v77;
      }
      SetErrorInfo(0, 0);
    }
    FreeMPMallocedPropSets(v24, v68);
    GetSource = Provider->lpVtbl->GetSource;
    if ( a13 )
    {
      if ( v19 )
      {
        v31 = &g_rgUpdatableCESetsForKag;
        v32 = 3;
      }
      else
      {
        v31 = &g_rgNonUpdatableCESetsForKag;
        v32 = 2;
      }
    }
    else
    {
      v32 = 1;
      if ( !v19 )
      {
        v33 = ((__int64 (__fastcall *)(IErrorInfo *, __int64, struct tagDBPROPSET near **))GetSource)(
                Provider,
                1,
                &g_rgNonUpdatableCESets);
        goto LABEL_50;
      }
      v31 = &g_rgUpdatableCESets;
    }
    v33 = ((__int64 (__fastcall *)(IErrorInfo *, __int64, struct tagDBPROPSET near **))GetSource)(Provider, v32, v31);
LABEL_50:
    if ( v33 < 0 )
    {
      if ( v33 != -2147217887 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v33, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x27Fu);
          if ( (bidGblFlags & 2) != 0 )
            v33 = bidTraceHR(off_1800C84B0[0], 654345, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v33);
        }
        v78 = v33;
        throw (long *)&v78;
      }
      SetErrorInfo(0, 0);
    }
    v17 = *(_QWORD *)&v92.Data1;
    v13 = a4;
    v14 = this;
    v15 = a8;
    v18 = a11;
LABEL_59:
    Execute = v15->lpVtbl->Execute;
    if ( a12 )
      v35 = ((__int64 (__fastcall *)(struct ICommand *, struct IUnknown *, GUID *, struct tagDBPARAMS *, __int64 *, __int64 *))Execute)(
              v15,
              v65,
              &IID_IUnknown,
              v13,
              a5,
              &v67);
    else
      v35 = ((__int64 (__fastcall *)(struct ICommand *, struct IUnknown *, GUID *, struct tagDBPARAMS *, __int64 *, __int64 *))Execute)(
              v15,
              a2,
              &IID_IMultipleResults,
              v13,
              a5,
              &v67);
    v63 = v35;
    if ( !v67 )
    {
LABEL_175:
      if ( v91 )
      {
        ((void (__fastcall *)(IErrorInfo *))v91->lpVtbl->Release)(v91);
        v71 = 0;
      }
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v74 = 0;
      }
      if ( pUnkOuter )
      {
        ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
        pUnkOuter = 0;
      }
      if ( v72 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( v65 )
      {
        ((void (__fastcall *)(struct IUnknown *))v65->lpVtbl->Release)(v65);
        v65 = 0;
      }
      ((void (__fastcall *)(struct ICommand *))v15->lpVtbl->Release)(v15);
      a8 = 0;
      goto LABEL_225;
    }
    if ( a12 )
    {
      v36 = v70;
      CDBPROPContainer::CreateCopy((CDBPROPContainer *)(v17 + 576), (CAcm *)((char *)v70 + 184));
    }
    else
    {
      v36 = (CAcm *)v73;
      CDBPROPContainer::CreateCopy((CDBPROPContainer *)(v17 + 480), (struct CDBPROPContainer *)&v73[23]);
      *((_BYTE *)v36 + 352) = a10;
      *((_BYTE *)v36 + 353) = v18;
    }
    v37 = a9;
    *((_DWORD *)v36 + 89) = a9;
    v38 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v65->lpVtbl[1].QueryInterface)(v65, v67);
    if ( v38 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v38, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2A4u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v38, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2A4u);
          if ( (bidGblFlags & 2) != 0 )
            v38 = bidTraceHR(off_1800C84B0[0], 692233, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v38);
        }
      }
      v79 = v38;
      throw (long *)&v79;
    }
    if ( !a12 )
    {
      v45 = a3;
LABEL_164:
      if ( a6 )
      {
        if ( !*a6 )
        {
          v58 = CMQI(v45, a2, v65, a7, a6);
          if ( v58 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v58, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x342u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v58, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x342u);
                if ( (bidGblFlags & 2) != 0 )
                  v58 = bidTraceHR(off_1800C84B0[0], 854025, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v58);
              }
            }
            v90 = v58;
            throw (long *)&v90;
          }
        }
      }
      if ( v67 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        v67 = 0;
      }
      v15 = a8;
      goto LABEL_175;
    }
    if ( a10 )
    {
      if ( a11 )
      {
        v66 = 0;
        v68 = 0;
        SetupCM<CCCM,CRCM>::SetupNewCM(*((void **)v14 + 7), (__int64)&pUnkOuter);
        Instance = CoCreateInstance(&CLSID_FoxRowset, pUnkOuter, 1u, &IID_IUnknown, (LPVOID *)&v66);
        if ( Instance < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(Instance, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B4u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(Instance, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B4u);
              if ( (bidGblFlags & 2) != 0 )
                Instance = bidTraceHR(
                             off_1800C84B0[0],
                             708617,
                             L"<CCommandText::DoExecute|Trace|HR> ",
                             (unsigned int)Instance);
            }
          }
          v80 = Instance;
          throw (long *)&v80;
        }
        v40 = ((__int64 (__fastcall *)(LPUNKNOWN, struct IUnknown *))pUnkOuter->lpVtbl[1].QueryInterface)(
                pUnkOuter,
                v66);
        if ( v40 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v40, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B6u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v40, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B6u);
              if ( (bidGblFlags & 2) != 0 )
                v40 = bidTraceHR(off_1800C84B0[0], 710665, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v40);
            }
          }
          v81 = v40;
          throw (long *)&v81;
        }
        v41 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct tagDBPROPSET **))v66->lpVtbl->QueryInterface)(
                v66,
                &IID_IRDSServiceProperties,
                &v68);
        if ( v41 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v41, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B8u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v41, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2B8u);
              if ( (bidGblFlags & 2) != 0 )
                v41 = bidTraceHR(off_1800C84B0[0], 712713, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v41);
            }
          }
          v82 = v41;
          throw (long *)&v82;
        }
        v42 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v66->lpVtbl->QueryInterface)(
                v66,
                &IID_IRDSService,
                &v72);
        if ( v42 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v42, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2BAu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v42, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2BAu);
              if ( (bidGblFlags & 2) != 0 )
                v42 = bidTraceHR(off_1800C84B0[0], 714761, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v42);
            }
          }
          v83 = v42;
          throw (long *)&v83;
        }
        v43 = *(_DWORD *)(v17 + 544);
        v44 = *(_QWORD *)(v17 + 536);
        v35 = ((__int64 (__fastcall *)(struct tagDBPROPSET *, _QWORD, __int64))v68->rgProperties->colid.uName.pwszName)(
                v68,
                v43,
                v44);
        ((void (__fastcall *)(struct tagDBPROPSET *))v68->rgProperties->colid.uGuid.pguid)(v68);
        ((void (__fastcall *)(struct IUnknown *))v66->lpVtbl->Release)(v66);
        if ( v35 == -2147217887 )
        {
          if ( *(_DWORD *)(v44 + 8) != 1 || **(_DWORD **)v44 != 260 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147217887, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x2D0u);
              if ( (bidGblFlags & 2) != 0 )
                v29 = bidTraceHR(off_1800C84B0[0], 737289, L"<CCommandText::DoExecute|Trace|HR> ", 2147749409LL);
            }
            v84 = v29;
            throw (long *)&v84;
          }
          SetErrorInfo(0, 0);
        }
        else
        {
          if ( v35 != 265946 )
            goto LABEL_104;
          v49 = 0;
          v50 = 0;
          v51 = 0;
          v52 = 0;
          if ( !v43 )
            goto LABEL_104;
          do
          {
            if ( v49 )
              goto LABEL_135;
            v53 = *(_DWORD **)v44;
            for ( j = 0; j < *(_DWORD *)(v44 + 8); v53 += 18 )
            {
              if ( v49 )
                break;
              if ( v53[2] && *v53 != 238 )
              {
                if ( *v53 == 260 )
                {
                  if ( *((_WORD *)v53 + 28) == 0xFFFF )
                    v50 = 1;
                }
                else if ( v53[1] )
                {
                  v51 = 1;
                }
                else
                {
                  v49 = 1;
                }
              }
              ++j;
            }
            ++v52;
            v44 += 32;
          }
          while ( v52 < v43 );
          if ( v49 )
          {
LABEL_135:
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147217887, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x302u);
              if ( (bidGblFlags & 2) != 0 )
                v29 = bidTraceHR(off_1800C84B0[0], 788489, L"<CCommandText::DoExecute|Trace|HR> ", 2147749409LL);
            }
            v85 = v29;
            throw (long *)&v85;
          }
          if ( !v50 || v51 )
            goto LABEL_104;
        }
        v35 = 0;
LABEL_104:
        v45 = a3;
        v46 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct IUnknown *, struct IUnknown **))(*(_QWORD *)v72 + 32LL))(
                v72,
                a3,
                v65,
                a6);
        v47 = v46;
        if ( v46 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v46, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x313u);
            if ( (bidGblFlags & 2) != 0 )
              v47 = bidTraceHR(off_1800C84B0[0], 805897, L"<CCommandText::DoExecute|Trace|HR> ", v47);
          }
          v87 = v47;
          throw (long *)&v87;
        }
        if ( v35 != 265946 )
          v35 = v46;
        v63 = v35;
        InheritedAccessors = CAccessorTracker::CreateInheritedAccessors(
                               (CAccessorTracker *)(*((_QWORD *)this + 7) + 352LL),
                               v66);
        if ( InheritedAccessors < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(InheritedAccessors, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x316u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(InheritedAccessors, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x316u);
              if ( (bidGblFlags & 2) != 0 )
                InheritedAccessors = bidTraceHR(
                                       off_1800C84B0[0],
                                       808969,
                                       L"<CCommandText::DoExecute|Trace|HR> ",
                                       (unsigned int)InheritedAccessors);
            }
          }
          v86 = InheritedAccessors;
          throw (long *)&v86;
        }
        goto LABEL_146;
      }
      v35 = 265946;
      v63 = 265946;
    }
    else if ( (v37 & 4) != 0 )
    {
      v92 = IID_IRowsetInfo;
      v55 = v70;
      inserted = CAcm::InsertDynamicInterface(v70, &v92);
      if ( inserted < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(inserted, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x32Fu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inserted, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x32Fu);
            if ( (bidGblFlags & 2) != 0 )
              inserted = bidTraceHR(
                           off_1800C84B0[0],
                           834569,
                           L"<CCommandText::DoExecute|Trace|HR> ",
                           (unsigned int)inserted);
          }
        }
        v88 = inserted;
        throw (long *)&v88;
      }
      v45 = a3;
      goto LABEL_147;
    }
    v45 = a3;
LABEL_146:
    v55 = v70;
LABEL_147:
    v73 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IUnknown **))v67)(v67, &IID_IMultipleResults, &v73) >= 0 )
    {
      v92 = IID_IMultipleResults;
      v56 = CAcm::InsertDynamicInterface(v55, &v92);
      if ( v56 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v56, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x337u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v56, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x337u);
            if ( (bidGblFlags & 2) != 0 )
              v56 = bidTraceHR(off_1800C84B0[0], 842761, L"<CCommandText::DoExecute|Trace|HR> ", (unsigned int)v56);
          }
        }
        v89 = v56;
        throw (long *)&v89;
      }
      *((_BYTE *)v55 + 352) = a10;
      *((_BYTE *)v55 + 353) = a11;
      ((void (__fastcall *)(struct IUnknown *))v73->lpVtbl->Release)(v73);
    }
    goto LABEL_164;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8C10[0] )
      bidTraceA(off_1800C84B0[0], 869376, off_1800C8C10[0], 0);
    if ( v67 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      v67 = 0;
    }
    if ( v71 )
      ((void (__fastcall *)(IErrorInfo *))v71->lpVtbl->Release)(v71);
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    if ( pUnkOuter )
    {
      ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
      pUnkOuter = 0;
    }
    if ( v72 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v65 )
    {
      ((void (__fastcall *)(struct IUnknown *))v65->lpVtbl->Release)(v65);
      v65 = 0;
    }
    if ( a8 )
      ((void (__fastcall *)(struct ICommand *))a8->lpVtbl->Release)(a8);
    if ( a6 && *a6 )
    {
      ((void (__fastcall *)(_QWORD))(*a6)->lpVtbl->Release)(*a6);
      *a6 = 0;
    }
    v60 = v70;
    if ( v70 && *((_QWORD *)v70 + 20) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v70 + 20) + 16LL))(*((_QWORD *)v70 + 20));
      *((_QWORD *)v60 + 20) = 0;
    }
    if ( v64 )
    {
      v61 = v93;
      if ( v93 )
      {
        if ( *((_QWORD *)this + 7) )
        {
          a8 = 0;
          (***((void (__fastcall ****)(_QWORD, GUID *, struct ICommand **))this + 7))(
            *((_QWORD *)this + 7),
            &IID_ICommandProperties,
            &a8);
          if ( a8 )
          {
            v71 = 0;
            GetErrorInfo(0, &v71);
            ((void (__fastcall *)(struct ICommand *, _QWORD, _QWORD))a8->lpVtbl->Execute)(
              a8,
              *(unsigned int *)(v61 + 544),
              *(_QWORD *)(v61 + 536));
            ((void (__fastcall *)(struct ICommand *))a8->lpVtbl->Release)(a8);
            if ( v71 )
            {
              SetErrorInfo(0, v71);
              ((void (__fastcall *)(IErrorInfo *))v71->lpVtbl->Release)(v71);
            }
          }
        }
      }
    }
    if ( v63 >= 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147418113, L"<CCommandText::DoExecute|OLEDB|ERR> ", 0x38Cu);
      v63 = -2147418113;
    }
    v35 = v63;
  }
LABEL_225:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84B0[0], 933897, L"<CCommandText::DoExecute|Trace|HR> ", v35);
  return v35;
}

```

## disassembly

```asm
0x18006f554  mov     rax, rsp
0x18006f557  mov     [rax+20h], r9
0x18006f55b  mov     [rax+18h], r8
0x18006f55f  mov     [rax+10h], rdx
0x18006f563  mov     [rax+8], rcx
0x18006f567  push    rbx
0x18006f568  push    rsi
0x18006f569  push    rdi
0x18006f56a  push    r12
0x18006f56c  push    r13
0x18006f56e  push    r14
0x18006f570  push    r15
0x18006f572  sub     rsp, 150h
0x18006f579  mov     rdi, r9
0x18006f57c  mov     r12, rcx
0x18006f57f  xor     r15d, r15d
0x18006f582  mov     [rsp+188h+var_140], r15
0x18006f587  mov     [rsp+188h+var_B0], r15
0x18006f58f  mov     [rsp+188h+var_110], r15
0x18006f594  mov     [rsp+188h+var_130], r15
0x18006f599  mov     [rsp+188h+var_148], r15d
0x18006f59e  mov     [rsp+188h+var_98], r15
0x18006f5a6  mov     [rsp+188h+var_118], r15
0x18006f5ab  mov     [rsp+188h+var_100], r15
0x18006f5b3  mov     [rax-0F8h], r15
0x18006f5ba  mov     [rsp+188h+pUnkOuter], r15
0x18006f5bf  mov     [rax-108h], r15
0x18006f5c6  mov     [rsp+188h+var_144], r15b
0x18006f5cb  mov     rsi, [rsp+188h+arg_38]
0x18006f5d3  mov     rax, [rsi]
0x18006f5d6  mov     rcx, rsi
0x18006f5d9  mov     rax, [rax+8]
0x18006f5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f5e2  mov     rcx, [rsp+188h+arg_30]
0x18006f5ea  mov     rax, [rcx]
0x18006f5ed  lea     r8, [rsp+188h+var_140]
0x18006f5f2  lea     rdx, IID_IService
0x18006f5f9  mov     rax, [rax]
0x18006f5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f601  mov     ebx, eax
0x18006f603  test    eax, eax
0x18006f605  jns     loc_18006F693
0x18006f60b  mov     eax, cs:_bidGblFlags
0x18006f611  test    al, 2
0x18006f613  jz      short loc_18006F674
0x18006f615  mov     r8d, 20Dh; unsigned int
0x18006f61b  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006f622  mov     ecx, ebx; int
0x18006f624  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f629  mov     eax, cs:_bidGblFlags
0x18006f62f  test    al, 2
0x18006f631  jz      short loc_18006F674
0x18006f633  mov     r8d, 20Dh; unsigned int
0x18006f639  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006f640  mov     ecx, ebx; int
0x18006f642  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f647  mov     eax, cs:_bidGblFlags
0x18006f64d  test    al, 2
0x18006f64f  jz      short loc_18006F674
0x18006f651  mov     [rsp+188h+var_148], ebx
0x18006f655  mov     r9d, ebx
0x18006f658  lea     r8, aCcommandtextDo; "<CCommandText::DoExecute|Trace|HR> "
0x18006f65f  mov     edx, 83409h
0x18006f664  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006f66b  call    _bidTraceHR
0x18006f670  mov     ebx, eax
0x18006f672  jmp     short loc_18006F678
0x18006f674  mov     [rsp+188h+var_148], ebx
0x18006f678  mov     [rsp+188h+pExceptionObject], ebx
0x18006f67f  lea     rdx, _TI1J; pThrowInfo
0x18006f686  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18006f68e  call    _CxxThrowException_0
0x18006f693  mov     r13, [r12+38h]
0x18006f698  mov     qword ptr [rsp+188h+var_A8.Data1], r13
0x18006f6a0  mov     [rsp+188h+var_98], r13
0x18006f6a8  mov     rax, [rsp+188h+var_140]
0x18006f6ad  cmp     [rsp+188h+arg_58], r15b
0x18006f6b5  jz      short loc_18006F6BE
0x18006f6b7  mov     [rsp+188h+var_118], rax
0x18006f6bc  jmp     short loc_18006F6C6
0x18006f6be  mov     [rsp+188h+var_100], rax
0x18006f6c6  mov     r14b, [rsp+188h+arg_50]
0x18006f6ce  cmp     [rsp+188h+arg_48], r15b
0x18006f6d6  jz      loc_18006FA8D
0x18006f6dc  test    r14b, r14b
0x18006f6df  jz      loc_18006FA8D
0x18006f6e5  xor     edx, edx; Val
0x18006f6e7  lea     r8d, [rdx+48h]; Size
0x18006f6eb  lea     rcx, [rsp+188h+var_88]; void *
0x18006f6f3  call    memset_0
0x18006f6f8  mov     [rsp+188h+var_88.dwPropertyID], 7Fh
0x18006f703  lea     rbx, [r13+1E0h]
0x18006f70a  lea     r8, [rsp+188h+var_88]; struct tagDBPROP *
0x18006f712  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x18006f719  mov     rcx, rbx; this
0x18006f71c  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x18006f721  test    al, al
0x18006f723  jz      short loc_18006F746
0x18006f725  cmp     word ptr [rsp+188h+var_88.vValue], 0Bh
0x18006f72e  jnz     short loc_18006F746
0x18006f730  cmp     word ptr [rsp+188h+var_88.vValue+8], 0FFFFh
0x18006f739  jnz     short loc_18006F746
0x18006f73b  mov     r15d, 1
0x18006f741  mov     sil, r15b
0x18006f744  jmp     short loc_18006F796
0x18006f746  movzx   esi, r15b
0x18006f74a  mov     [rsp+188h+var_88.dwPropertyID], 86h
0x18006f755  lea     r8, [rsp+188h+var_88]; struct tagDBPROP *
0x18006f75d  lea     rdx, DBPROPSET_ROWSET; struct _GUID *
0x18006f764  mov     rcx, rbx; this
0x18006f767  call    ?GetProperty@CDBPROPContainer@@QEAA_NAEBU_GUID@@PEAUtagDBPROP@@@Z; CDBPROPContainer::GetProperty(_GUID const &,tagDBPROP *)
0x18006f76c  test    al, al
0x18006f76e  jz      short loc_18006F790
0x18006f770  cmp     word ptr [rsp+188h+var_88.vValue], 0Bh
0x18006f779  jnz     short loc_18006F790
0x18006f77b  mov     r15d, 1
0x18006f781  cmp     word ptr [rsp+188h+var_88.vValue+8], 0FFFFh
0x18006f78a  cmovz   esi, r15d
0x18006f78e  jmp     short loc_18006F796
0x18006f790  mov     r15d, 1
0x18006f796  lea     rdx, IID_ICommandProperties
0x18006f79d  mov     rcx, [r12+38h]
0x18006f7a2  call    ??$GetProviderPointer@VCCCM@@@@YAPEAXPEAV?$CComObject@VCCCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CCCM>(ATL::CComObject<CCCM> *,_GUID const &)
0x18006f7a7  mov     r14, rax
0x18006f7aa  mov     [rsp+188h+var_B0], rax
0x18006f7b2  mov     [rsp+188h+var_110], rax
0x18006f7b7  mov     dword ptr [rsp+188h+var_138], 0
0x18006f7bf  mov     [rsp+188h+var_128], 0
0x18006f7c8  lea     r9, [rsp+188h+var_128]; struct tagDBPROPSET **
0x18006f7cd  lea     r8, [rsp+188h+var_138]; unsigned int *
0x18006f7d2  mov     rdx, [r13+218h]; struct tagDBPROPSET *
0x18006f7d9  mov     ecx, [r13+220h]; unsigned int
0x18006f7e0  call    ?CreateMPMallocCopyOfProps@@YAJKPEAUtagDBPROPSET@@PEAKPEAPEAU1@_N@Z; CreateMPMallocCopyOfProps(ulong,tagDBPROPSET *,ulong *,tagDBPROPSET * *,bool)
0x18006f7e5  mov     ebx, eax
0x18006f7e7  test    eax, eax
0x18006f7e9  jns     loc_18006F877
0x18006f7ef  mov     eax, cs:_bidGblFlags
0x18006f7f5  test    al, 2
0x18006f7f7  jz      short loc_18006F858
0x18006f7f9  mov     r8d, 238h; unsigned int
0x18006f7ff  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006f806  mov     ecx, ebx; int
0x18006f808  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f80d  mov     eax, cs:_bidGblFlags
0x18006f813  test    al, 2
0x18006f815  jz      short loc_18006F858
0x18006f817  mov     r8d, 238h; unsigned int
0x18006f81d  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006f824  mov     ecx, ebx; int
0x18006f826  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f82b  mov     eax, cs:_bidGblFlags
0x18006f831  test    al, 2
0x18006f833  jz      short loc_18006F858
0x18006f835  mov     [rsp+188h+var_148], ebx
0x18006f839  mov     r9d, ebx
0x18006f83c  lea     r8, aCcommandtextDo; "<CCommandText::DoExecute|Trace|HR> "
0x18006f843  mov     edx, 8E009h
0x18006f848  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006f84f  call    _bidTraceHR
0x18006f854  mov     ebx, eax
0x18006f856  jmp     short loc_18006F85C
0x18006f858  mov     [rsp+188h+var_148], ebx
0x18006f85c  mov     [rsp+188h+var_EC], ebx
0x18006f863  lea     rdx, _TI1J; pThrowInfo
0x18006f86a  lea     rcx, [rsp+188h+var_EC]; pExceptionObject
0x18006f872  call    _CxxThrowException_0
0x18006f877  mov     rdi, [rsp+188h+var_128]
0x18006f87c  xor     r12d, r12d
0x18006f87f  mov     r13d, dword ptr [rsp+188h+var_138]
0x18006f884  test    r13d, r13d
0x18006f887  jz      short loc_18006F8D9
0x18006f889  mov     rbx, [rdi]
0x18006f88c  xor     r14d, r14d
0x18006f88f  cmp     [rdi+8], r14d
0x18006f893  jbe     short loc_18006F8C5
0x18006f895  cmp     dword ptr [rbx], 49h ; 'I'
0x18006f898  jz      short loc_18006F8B8
0x18006f89a  cmp     dword ptr [rbx], 0EEh
0x18006f8a0  jz      short loc_18006F8B8
0x18006f8a2  cmp     dword ptr [rbx], 0D9h
0x18006f8a8  jz      short loc_18006F8B8
0x18006f8aa  lea     rcx, [rbx+30h]; pvarg
0x18006f8ae  call    cs:__imp_VariantClear
0x18006f8b4  mov     [rbx+4], r15d
0x18006f8b8  add     r14d, r15d
0x18006f8bb  add     rbx, 48h ; 'H'
0x18006f8bf  cmp     r14d, [rdi+8]
0x18006f8c3  jb      short loc_18006F895
0x18006f8c5  add     r12d, r15d
0x18006f8c8  add     rdi, 20h ; ' '
0x18006f8cc  cmp     r12d, r13d
0x18006f8cf  jb      short loc_18006F889
0x18006f8d1  mov     r14, [rsp+188h+var_B0]
0x18006f8d9  mov     rax, [r14]
0x18006f8dc  mov     r8, [rsp+188h+var_128]
0x18006f8e1  mov     edx, r13d
0x18006f8e4  mov     rcx, r14
0x18006f8e7  mov     rax, [rax+20h]
0x18006f8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8f0  mov     edi, eax
0x18006f8f2  mov     [rsp+188h+var_144], r15b
0x18006f8f7  mov     ebx, 80040E21h
0x18006f8fc  test    eax, eax
0x18006f8fe  jns     short loc_18006F90E
0x18006f900  cmp     eax, ebx
0x18006f902  jnz     short loc_18006F949
0x18006f904  xor     edx, edx; perrinfo
0x18006f906  xor     ecx, ecx; dwReserved
0x18006f908  call    cs:__imp_SetErrorInfo
0x18006f90e  mov     rdx, [rsp+188h+var_128]; struct tagDBPROPSET *
0x18006f913  mov     ecx, r13d; unsigned int
0x18006f916  call    ?FreeMPMallocedPropSets@@YAXKPEAUtagDBPROPSET@@@Z; FreeMPMallocedPropSets(ulong,tagDBPROPSET *)
0x18006f91b  mov     rax, [r14]
0x18006f91e  mov     rax, [rax+20h]
0x18006f922  mov     rcx, r14
0x18006f925  cmp     [rsp+188h+arg_60], 0
0x18006f92d  jz      loc_18006F9C1
0x18006f933  test    sil, sil
0x18006f936  jz      short loc_18006F9B3
0x18006f938  lea     r8, ?g_rgUpdatableCESetsForKag@@3PAUtagDBPROPSET@@A; tagDBPROPSET near * g_rgUpdatableCESetsForKag
0x18006f93f  mov     edx, 3
0x18006f944  jmp     loc_18006F9D0
0x18006f949  mov     eax, cs:_bidGblFlags
0x18006f94f  test    al, 2
0x18006f951  jz      short loc_18006F994
0x18006f953  mov     r8d, 258h; unsigned int
0x18006f959  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006f960  mov     ecx, edi; int
0x18006f962  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006f967  mov     eax, cs:_bidGblFlags
0x18006f96d  test    al, 2
0x18006f96f  jz      short loc_18006F994
0x18006f971  mov     [rsp+188h+var_148], edi
0x18006f975  mov     r9d, edi
0x18006f978  lea     r8, aCcommandtextDo; "<CCommandText::DoExecute|Trace|HR> "
0x18006f97f  mov     edx, 96009h
0x18006f984  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006f98b  call    _bidTraceHR
0x18006f990  mov     edi, eax
0x18006f992  jmp     short loc_18006F998
0x18006f994  mov     [rsp+188h+var_148], edi
0x18006f998  mov     [rsp+188h+var_E8], edi
0x18006f99f  lea     rdx, _TI1J; pThrowInfo
0x18006f9a6  lea     rcx, [rsp+188h+var_E8]; pExceptionObject
0x18006f9ae  call    _CxxThrowException_0
0x18006f9b3  lea     r8, ?g_rgNonUpdatableCESetsForKag@@3PAUtagDBPROPSET@@A; tagDBPROPSET near * g_rgNonUpdatableCESetsForKag
0x18006f9ba  mov     edx, 2
0x18006f9bf  jmp     short loc_18006F9D0
0x18006f9c1  mov     edx, r15d
0x18006f9c4  test    sil, sil
0x18006f9c7  jz      short loc_18006F9D9
0x18006f9c9  lea     r8, ?g_rgUpdatableCESets@@3PAUtagDBPROPSET@@A; tagDBPROPSET near * g_rgUpdatableCESets
0x18006f9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9d5  mov     edi, eax
0x18006f9d7  jmp     short loc_18006F9E7
0x18006f9d9  lea     r8, ?g_rgNonUpdatableCESets@@3PAUtagDBPROPSET@@A; tagDBPROPSET near * g_rgNonUpdatableCESets
0x18006f9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9e5  mov     edi, eax
0x18006f9e7  test    edi, edi
0x18006f9e9  jns     short loc_18006F9F9
0x18006f9eb  cmp     edi, ebx
0x18006f9ed  jnz     short loc_18006FA23
0x18006f9ef  xor     edx, edx; perrinfo
0x18006f9f1  xor     ecx, ecx; dwReserved
0x18006f9f3  call    cs:__imp_SetErrorInfo
0x18006f9f9  mov     r13, qword ptr [rsp+188h+var_A8.Data1]
0x18006fa01  mov     rdi, [rsp+188h+arg_18]
0x18006fa09  mov     r12, [rsp+188h+arg_0]
0x18006fa11  mov     rsi, [rsp+188h+arg_38]
0x18006fa19  mov     r14b, [rsp+188h+arg_50]
0x18006fa21  jmp     short loc_18006FA98
0x18006fa23  mov     eax, cs:_bidGblFlags
0x18006fa29  test    al, 2
0x18006fa2b  jz      short loc_18006FA6E
0x18006fa2d  mov     r8d, 27Fh; unsigned int
0x18006fa33  lea     rdx, aCcommandtextDo_0; "<CCommandText::DoExecute|OLEDB|ERR> "
0x18006fa3a  mov     ecx, edi; int
0x18006fa3c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006fa41  mov     eax, cs:_bidGblFlags
0x18006fa47  test    al, 2
0x18006fa49  jz      short loc_18006FA6E
0x18006fa4b  mov     [rsp+188h+var_148], edi
0x18006fa4f  mov     r9d, edi
0x18006fa52  lea     r8, aCcommandtextDo; "<CCommandText::DoExecute|Trace|HR> "
0x18006fa59  mov     edx, 9FC09h
0x18006fa5e  mov     rcx, cs:off_1800C84B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006fa65  call    _bidTraceHR
0x18006fa6a  mov     edi, eax
0x18006fa6c  jmp     short loc_18006FA72
0x18006fa6e  mov     [rsp+188h+var_148], edi
0x18006fa72  mov     [rsp+188h+var_E4], edi
0x18006fa79  lea     rdx, _TI1J; pThrowInfo
0x18006fa80  lea     rcx, [rsp+188h+var_E4]; pExceptionObject
0x18006fa88  call    _CxxThrowException_0
0x18006fa8d  mov     r15d, 1
0x18006fa93  mov     ebx, 80040E21h
0x18006fa98  mov     rax, [rsi]
0x18006fa9b  mov     r10, [rax+20h]
0x18006fa9f  lea     rax, [rsp+188h+var_130]
0x18006faa4  mov     r9, rdi
  ... truncated ...
```
