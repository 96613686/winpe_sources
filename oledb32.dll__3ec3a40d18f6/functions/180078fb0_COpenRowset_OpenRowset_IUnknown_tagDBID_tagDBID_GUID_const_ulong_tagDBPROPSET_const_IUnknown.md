# COpenRowset::OpenRowset(IUnknown *,tagDBID *,tagDBID *,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x180078fb0`
- end: `0x18007a101`
- name: `?OpenRowset@COpenRowset@@UEAAJPEAUIUnknown@@PEAUtagDBID@@1AEBU_GUID@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `4433`
- prototype: `int(COpenRowset *__hidden this, struct IUnknown *, struct tagDBID *, struct tagDBID *, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180011bcc`
- `0x180011bf0`
- `0x180013870`
- `0x180028e3c`
- `0x180029560`
- `0x18002a914`
- `0x18002a93c`
- `0x18002bc80`
- `0x18002c060`
- `0x18002ec32`
- `0x180031ef8`
- `0x1800324c8`
- `0x18006d1c0`
- `0x18006e3b0`
- `0x1800719d4`
- `0x180071a70`
- `0x180071b44`
- `0x180071cd4`
- `0x1800720a0`
- `0x18007219c`
- `0x180073550`
- `0x180077e30`
- `0x180078414`
- `0x180078fb0`
- `0x18007a108`
- `0x18007e6ca`
- `0x18007e700`
- `0x18007e7c0`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180079154`
- `MSDART!MpHeapAlloc` at `0x180079973`
- `MSDART!MpHeapAlloc` at `0x180079154`
- `MSDART!MpHeapAlloc` at `0x180079973`
- `OLEAUT32!__imp_SysAllocString` at `0x1800798a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800798a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800798d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800798d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800794ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800794ab`
- `ole32!CoCreateInstance` at `0x180079795`
- `ole32!CoCreateInstance` at `0x180079795`

## string_xrefs

- `0x180079099`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x1800791e3`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079263`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079314`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079428`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x1800795a3`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x1800796c5`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079739`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x1800797b1`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079999`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079b19`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079bc2`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079c71`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079d3c`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079dbd`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079e3b`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079e9f`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x180079f02`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x18007a0a7`: `<COpenRowset::OpenRowset|OLEDB|ERR> `
- `0x1800790b3`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x1800791fe`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x18007927d`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x18007932e`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079442`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x1800795bd`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x1800796df`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079753`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x1800797cb`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079b36`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079bdc`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079c8f`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079dd7`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079f1c`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x180079f6f`: `<COpenRowset::OpenRowset|Trace|HR> `
- `0x18007a0c1`: `<COpenRowset::OpenRowset|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall COpenRowset::OpenRowset(
        COpenRowset *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  struct IUnknown *v9; // rsi
  CAcm *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rsi
  int v18; // eax
  __int64 m; // rdx
  OLECHAR *pwszName; // rax
  struct CMCommonPropertyClass *v21; // r8
  int v22; // eax
  int v23; // r15d
  struct tagDBPROPSET *v24; // rax
  CDCM *RootAcm; // rdi
  struct CDPO *CDPO; // r14
  int v27; // eax
  unsigned int v28; // edi
  struct tagDBPROPSET *v29; // r8
  struct tagDBPROPSET *v30; // r14
  unsigned int Property; // edi
  struct tagDBPROPSET *v32; // r15
  ULONG cProperties; // eax
  unsigned int v34; // r15d
  int v35; // eax
  char v36; // dl
  unsigned int i; // r8d
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r8
  int inserted; // eax
  unsigned int v42; // r14d
  int v43; // eax
  unsigned int v44; // r14d
  HRESULT v45; // eax
  unsigned int v46; // r14d
  size_t v47; // r8
  __int64 v48; // rax
  void *v49; // rsp
  DBPROPSTATUS **v50; // r12
  struct tagDBPROPSET *v51; // r14
  unsigned int j; // r15d
  __int64 v53; // rax
  DBPROPSTATUS *v54; // rcx
  DBPROP *rgProperties; // rdx
  ULONG k; // r8d
  unsigned int v57; // r10d
  char v58; // cl
  struct tagDBPROPSET *v59; // rdx
  __int64 v60; // r9
  DBPROP *v61; // rax
  bool v62; // zf
  bool v63; // r14
  int v64; // eax
  struct tagDBPROPSET *v65; // r14
  unsigned int v66; // r15d
  struct IUnknown *v67; // r14
  struct tagDBPROPSET *v68; // rcx
  unsigned int v69; // edx
  unsigned int v70; // eax
  DBPROP *v71; // r9
  DBPROPSTATUS *v72; // r10
  ULONG v73; // r11d
  char v74; // r14
  int v75; // eax
  unsigned int v76; // r14d
  unsigned int v77; // r15d
  ULONG n; // r8d
  int v79; // r14d
  _BYTE *v80; // r15
  __int64 result; // rax
  _BYTE v82[4]; // [rsp+50h] [rbp+0h] BYREF
  unsigned int v83; // [rsp+54h] [rbp+4h] BYREF
  bool v84; // [rsp+58h] [rbp+8h]
  __int64 v85; // [rsp+60h] [rbp+10h] BYREF
  struct tagDBPROPSET *v86; // [rsp+68h] [rbp+18h] BYREF
  struct tagDBPROPSET *v87; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v88; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v89[2]; // [rsp+80h] [rbp+30h] BYREF
  struct IUnknown *Provider; // [rsp+88h] [rbp+38h]
  struct IUnknown *v91; // [rsp+90h] [rbp+40h]
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v93; // [rsp+A0h] [rbp+50h]
  int v94; // [rsp+A4h] [rbp+54h]
  OLECHAR *psz; // [rsp+B0h] [rbp+60h]
  struct IUnknown *v96; // [rsp+B8h] [rbp+68h]
  LPUNKNOWN pUnkOuter; // [rsp+C0h] [rbp+70h] BYREF
  __int64 v98; // [rsp+C8h] [rbp+78h] BYREF
  __int64 v99; // [rsp+D0h] [rbp+80h]
  struct tagDBID *v100; // [rsp+D8h] [rbp+88h]
  struct tagDBPROPSET *v101; // [rsp+E0h] [rbp+90h]
  _BYTE *v102; // [rsp+E8h] [rbp+98h]
  struct IUnknown *v103; // [rsp+F0h] [rbp+A0h]
  struct IUnknown **v104; // [rsp+F8h] [rbp+A8h]
  CAcm *v105; // [rsp+100h] [rbp+B0h]
  struct tagDBID *v106; // [rsp+108h] [rbp+B8h]
  struct _GUID *v107; // [rsp+110h] [rbp+C0h]
  struct IUnknown *v108; // [rsp+118h] [rbp+C8h]
  __int64 v109; // [rsp+120h] [rbp+D0h]
  _BYTE v110[28]; // [rsp+130h] [rbp+E0h] BYREF
  int v111; // [rsp+14Ch] [rbp+FCh]
  _DWORD v112[4]; // [rsp+150h] [rbp+100h] BYREF
  DBID v113; // [rsp+160h] [rbp+110h]
  __int16 v114; // [rsp+180h] [rbp+130h]
  BSTR bstrString; // [rsp+188h] [rbp+138h]

  v106 = a4;
  v100 = a3;
  v9 = a2;
  v91 = a2;
  *(_QWORD *)v110 = this;
  v108 = a2;
  v107 = a5;
  v93 = a6;
  v101 = a7;
  v104 = a8;
  v103 = 0;
  v99 = 0;
  v96 = 0;
  v88 = 0;
  v109 = 0;
  pUnkOuter = 0;
  v98 = 0;
  ppv = 0;
  v94 = -1;
  v102 = 0;
  v11 = (CAcm *)*((_QWORD *)this + 7);
  if ( a8 )
    *a8 = 0;
  if ( !a3 && !a4 )
  {
    v12 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x69u);
      if ( (bidGblFlags & 2) != 0 )
        v12 = bidTraceHR(off_1800C8518[0], 107529, L"<COpenRowset::OpenRowset|Trace|HR> ", 2147942487LL);
    }
    goto LABEL_202;
  }
  v13 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v13 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v13 )
  {
    v14 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v14 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IStream.Data4;
    if ( v14 )
    {
      v15 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_ISequentialStream.Data1;
      if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_ISequentialStream.Data1 )
        v15 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_ISequentialStream.Data4;
      if ( v15 && !CRCM::IsRowIID(a5) )
      {
        v16 = MpHeapAlloc(g_hHeapHandle, 19922944, 120);
        v17 = v16;
        v105 = (CAcm *)v16;
        if ( !v16 )
        {
          v99 = 0;
          v12 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x80u);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8518[0], 131081, L"<COpenRowset::OpenRowset|Trace|HR> ", 2147942414LL);
          }
          goto LABEL_199;
        }
        *(_QWORD *)(v16 + 8) = a5;
        *(_QWORD *)v16 = v91;
        *(_DWORD *)(v16 + 16) = v93;
        *(_QWORD *)(v16 + 24) = v101;
        *(_QWORD *)(v16 + 32) = a8;
        *(_QWORD *)(v16 + 80) = 0;
        *(_QWORD *)(v16 + 88) = 0;
        *(_QWORD *)(v16 + 72) = 0;
        *(_QWORD *)(v16 + 96) = 0;
        *(_QWORD *)(v16 + 40) = 0;
        *(_DWORD *)(v16 + 48) = 0;
        *(_QWORD *)(v16 + 56) = 0;
        *(_DWORD *)(v16 + 65) = 0;
        *(_BYTE *)(v16 + 64) = 0;
        *(_BYTE *)(v16 + 69) = 0;
        *(_QWORD *)(v16 + 104) = 0;
        v99 = v16;
        v12 = CImmediateRowset::ValidateParameters((CImmediateRowset *)v16);
        if ( (v12 & 0x80000000) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v12, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x82u);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8518[0], 133129, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
          }
LABEL_198:
          CImmediateRowset::~CImmediateRowset((CImmediateRowset *)v17);
          operator delete((void *)v17);
LABEL_199:
          if ( v96 )
            ((void (__fastcall *)(struct IUnknown *))v96->lpVtbl->Release)(v96);
          v9 = v91;
LABEL_202:
          if ( v88 )
          {
            ((void (__fastcall *)(struct IUnknown *))v88->lpVtbl->Release)(v88);
            v88 = 0;
          }
          if ( v109 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
          if ( pUnkOuter )
          {
            ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
            pUnkOuter = 0;
          }
          if ( v98 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
            v98 = 0;
          }
          if ( ppv )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            ppv = 0;
          }
          if ( (v12 & 0x80000000) != 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              return v12;
            OLEDBTraceErr(v12, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x250u);
          }
          else if ( v9 && a8 && *a8 )
          {
            AggregateCM(v9, *a8);
          }
          if ( (bidGblFlags & 2) != 0 )
            return (unsigned int)bidTraceHR(off_1800C8518[0], 609289, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
          return v12;
        }
        Provider = (struct IUnknown *)GetProviderPointer<CSCM>(*((_QWORD *)this + 7), &IID_IOpenRowset);
        v103 = Provider;
        v18 = SetupCM<CSCM,CRCM>::SetupNewCM(*((void **)this + 7), (__int64)&v88);
        v12 = v18;
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v18, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x89u);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8518[0], 140297, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
          }
          goto LABEL_195;
        }
        v105 = (CAcm *)v88;
        pwszName = 0;
        psz = 0;
        if ( a3 && (a3->eKind & 0xFFFFFFFC) == 0 && v100->eKind != 1 )
        {
          pwszName = v100->uName.pwszName;
          psz = pwszName;
        }
        v21 = (CAcm *)((char *)v11 + 192);
        if ( !v11 )
          v21 = 0;
        v22 = CImmediateRowset::Initialize((CImmediateRowset *)v17, Provider, v21, pwszName);
        v12 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v22, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x96u);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8518[0], 153609, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
          }
          goto LABEL_195;
        }
        v87 = 0;
        v23 = 2;
        LODWORD(v85) = 2;
        if ( FindPropSet(&DBPROPSET_ROWSET, *(_DWORD *)(v17 + 16), *(struct tagDBPROPSET **)(v17 + 24), &v87) != -1 )
        {
          v86 = 0;
          if ( FindProperty(v87, 0x104u, (struct tagDBPROP **)&v86) != -1 )
          {
            v24 = v86;
            v86->cProperties = 0;
            if ( !HIDWORD(v24->rgProperties) )
            {
              v23 = *(_WORD *)&v24[1].guidPropertySet.Data4[4] != 0xFFFF;
              LODWORD(v85) = v23;
            }
          }
        }
        RootAcm = CAcm::GetRootAcm(v11);
        CDPO = CDCM::GetCDPO(RootAcm);
        *(_QWORD *)v89 = CDPO;
        if ( (CDPO::GetOLEDBServices(CDPO) & 4) == 0 || !CDCM::DCMAllowsFoxCE(RootAcm) )
        {
          v23 = 1;
          LODWORD(v85) = 1;
        }
        v84 = *(_BYTE *)(*((_QWORD *)CDPO + 15) + 1080LL);
        v83 = 0;
        v87 = 0;
        v27 = CImmediateRowset::AddPropertiesForRequestedInterface(
                (CImmediateRowset *)v17,
                &v83,
                &v87,
                (struct tagDBPROP **)&v86);
        v12 = v27;
        if ( v27 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v27, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0xA8u);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8518[0], 172041, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
          }
          goto LABEL_195;
        }
        v86 = 0;
        v28 = v83;
        if ( FindPropSet(&DBPROPSET_ROWSET, v83, v87, &v86) != -1 )
        {
          v30 = v86;
          v86 = 0;
          Property = FindProperty(v30, 0x104u, (struct tagDBPROP **)&v86);
          if ( Property != -1 )
          {
            v32 = v86;
            VariantClear((VARIANTARG *)&v86[1].guidPropertySet.Data2);
            cProperties = v30->cProperties;
            if ( Property < cProperties - 1 )
              memmove_0(v32, &v32[2].cProperties, 72LL * (cProperties + ~Property));
            --v30->cProperties;
            v23 = v85;
          }
          v29 = v87;
          v28 = v83;
          CDPO = *(struct CDPO **)v89;
        }
        if ( v23 )
        {
          v34 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, struct tagDBID *, struct tagDBID *, GUID *, unsigned int, struct tagDBPROPSET *, struct IUnknown **))Provider->lpVtbl[1].QueryInterface)(
                  Provider,
                  v88,
                  v100,
                  v106,
                  &IID_IUnknown,
                  v28,
                  v29,
                  a8);
          v89[0] = v34;
        }
        else
        {
          v34 = -2147217887;
          v89[0] = -2147217887;
        }
        if ( a8 )
        {
          if ( *a8 )
          {
            ((void (__fastcall *)(struct IUnknown *, _QWORD))v88->lpVtbl[1].QueryInterface)(v88, *a8);
            ((void (__fastcall *)(_QWORD))(*a8)->lpVtbl->Release)(*a8);
            v35 = CMQI(v107, v91, v88, v96, a8);
            v12 = v35;
            if ( v35 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v35, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0xD5u);
                if ( (bidGblFlags & 2) != 0 )
                  v12 = bidTraceHR(off_1800C8518[0], 218121, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
              }
              goto LABEL_195;
            }
          }
        }
        v12 = v34;
        v36 = 0;
        for ( i = 0; i < v83; ++i )
        {
          v38 = i;
          v39 = *(_QWORD *)&v87[v38].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_ROWSET.Data1;
          if ( !v39 )
            v39 = *(_QWORD *)v87[v38].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_ROWSET.Data4;
          if ( v39 )
            v36 = 1;
        }
        v82[0] = 0;
        if ( !v36 )
        {
          if ( !(_DWORD)v85 )
            goto LABEL_82;
          if ( v34 && (_DWORD)v85 != 1 && CImmediateRowset::AFoxPropIsInError((CImmediateRowset *)v17) )
          {
            if ( v34 != -2147217887 && v34 != 265946 )
            {
              if ( (CDPO::GetOLEDBServices(CDPO) & 4) != 0 )
              {
                *(GUID *)v110 = IID_IRowsetInfo;
                inserted = CAcm::InsertDynamicInterface(v105, (struct _GUID *)v110);
                v42 = inserted;
                if ( inserted < 0 )
                {
                  if ( (bidGblFlags & 2) != 0
                    && (OLEDBTraceErr(inserted, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x1DFu), (bidGblFlags & 2) != 0) )
                  {
                    v12 = bidTraceHR(off_1800C8518[0], 490505, L"<COpenRowset::OpenRowset|Trace|HR> ", v42);
                  }
                  else
                  {
                    v12 = v42;
                  }
                  goto LABEL_195;
                }
              }
              goto LABEL_171;
            }
LABEL_82:
            v43 = SetupCM<CSCM,CRCM>::SetupNewCM(*(void **)(*(_QWORD *)v110 + 56LL), (__int64)&pUnkOuter);
            v44 = v43;
            if ( v43 < 0 )
            {
              if ( (bidGblFlags & 2) != 0
                && (OLEDBTraceErr(v43, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0xF5u), (bidGblFlags & 2) != 0) )
              {
                v12 = bidTraceHR(off_1800C8518[0], 250889, L"<COpenRowset::OpenRowset|Trace|HR> ", v44);
              }
              else
              {
                v12 = v44;
              }
              goto LABEL_195;
            }
            v45 = CoCreateInstance(&CLSID_FoxRowset, pUnkOuter, 1u, &IID_IUnknown, &ppv);
            v46 = v45;
            if ( v45 < 0 )
            {
              if ( (bidGblFlags & 2) != 0
                && (OLEDBTraceErr(v45, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0xF8u), (bidGblFlags & 2) != 0) )
              {
                v12 = bidTraceHR(off_1800C8518[0], 253961, L"<COpenRowset::OpenRowset|Trace|HR> ", v46);
              }
              else
              {
                v12 = v46;
              }
              goto LABEL_195;
            }
            ((void (__fastcall *)(LPUNKNOWN, LPVOID))pUnkOuter->lpVtbl[1].QueryInterface)(pUnkOuter, ppv);
            LODWORD(v86) = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                             ppv,
                             &IID_IRDSServiceProperties,
                             &v98);
            if ( psz )
            {
              v111 = 0;
              memset_0(v112, 0, 0x48u);
              *(GUID *)&v110[12] = DBPROPSET_ROWSET;
              *(_DWORD *)&v110[8] = 1;
              *(_QWORD *)v110 = v112;
              v112[0] = 61183;
              v112[1] = 1;
              v113 = DB_NULLID;
              v114 = 8;
              bstrString = SysAllocString(psz);
              (*(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v98 + 40LL))(v98, 1, v110);
              SysFreeString(bstrString);
            }
            if ( (_DWORD)v85 && (v34 == -2147217887 || v34 == 265946) )
            {
              v47 = 8LL * v83;
              v48 = v47 + 15;
              if ( v47 + 15 < v47 )
                v48 = 0xFFFFFFFFFFFFFF0LL;
              v49 = alloca(v48 & 0xFFFFFFFFFFFFFFF0uLL);
              v102 = v82;
              memset_0(v82, 0, v47);
              v50 = (DBPROPSTATUS **)v82;
              v51 = v87;
              for ( j = 0; ; ++j )
              {
                if ( j >= v83 )
                {
                  v34 = v89[0];
                  goto LABEL_110;
                }
                v53 = 16LL * v51->cProperties;
                if ( !is_mul_ok(4LL * v51->cProperties, 4u) )
                  v53 = -1;
                v54 = (DBPROPSTATUS *)MpHeapAlloc(g_hHeapHandle, 19922944, v53);
                *v50 = v54;
                if ( !v54 )
                  break;
                v94 = j;
                rgProperties = v51->rgProperties;
                for ( k = 0; k < v51->cProperties; ++v54 )
                {
                  *v54 = rgProperties->dwStatus;
                  ++k;
                  ++rgProperties;
                }
                ++v50;
                ++v51;
              }
              v12 = -2147024882;
              if ( (bidGblFlags & 2) != 0 )
                OLEDBTraceErr(-2147024882, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x12Au);
              goto LABEL_186;
            }
LABEL_110:
            v57 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *))(*(_QWORD *)v98 + 40LL))(
                    v98,
                    v83,
                    v87);
            LODWORD(psz) = v57;
            if ( v57 == -2147217887 )
            {
LABEL_150:
              if ( (_DWORD)v85 )
              {
                if ( v34 == -2147217887 || v34 == 265946 )
                {
                  v40 = (unsigned __int64)v102;
                  v68 = v87;
                  v69 = 0;
                  if ( v83 )
                  {
                    v70 = v83;
                    do
                    {
                      v71 = v68->rgProperties;
                      v72 = *(DBPROPSTATUS **)v40;
                      v73 = 0;
                      if ( v68->cProperties )
                      {
                        do
                        {
                          v71->dwStatus = *v72;
                          ++v73;
                          ++v71;
                          ++v72;
                        }
                        while ( v73 < v68->cProperties );
                        v70 = v83;
                      }
                      ++v69;
                      v40 += 8LL;
                      ++v68;
                    }
                    while ( v69 < v70 );
                  }
                  v74 = 1;
LABEL_172:
                  v77 = v93;
                  if ( !UpdateOverlappingProps(v93, v101, v40, v87) )
                  {
                    if ( v74 == 1 )
                    {
                      v12 = -2147467262;
                      if ( (bidGblFlags & 2) != 0 )
                        OLEDBTraceErr(-2147467262, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x1F7u);
                    }
                    else if ( v12 == -2147217887 )
                    {
                      v12 = -2147467262;
                      for ( m = 0; (unsigned int)m < v77; m = (unsigned int)(m + 1) )
                      {
                        for ( n = 0; n < v101[(unsigned int)m].cProperties; ++n )
                        {
                          if ( v101[(unsigned int)m].rgProperties[n].dwStatus )
                          {
                            if ( (bidGblFlags & 2) != 0 )
                              OLEDBTraceErr(-2147217887, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x20Cu);
                            v12 = -2147217887;
                            LODWORD(m) = v77;
                            break;
                          }
                        }
                      }
                    }
                  }
LABEL_186:
                  v79 = v94;
                  if ( v94 >= 0 )
                  {
                    v80 = v102;
                    do
                      operator delete(*(void **)&v80[8 * v79--]);
                    while ( v79 >= 0 );
                  }
                  goto LABEL_195;
                }
              }
              else
              {
                if ( (bidGblFlags & 2) != 0 )
                  OLEDBTraceErr(-2147217887, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x1CBu);
                v12 = -2147217887;
                if ( a8 && *a8 )
                {
                  ((void (__fastcall *)(_QWORD))(*a8)->lpVtbl->Release)(*a8);
                  *a8 = 0;
                }
              }
LABEL_171:
              v74 = v82[0];
              goto LABEL_172;
            }
            v58 = 0;
            v59 = v87;
            v60 = 0;
            if ( v83 )
            {
              while ( !v58 )
              {
                v61 = v59->rgProperties;
                v40 = 0;
                while ( (unsigned int)v40 < v59->cProperties )
                {
                  if ( v61->dwOptions )
                    v62 = v61->dwOptions == 1;
                  else
                    v62 = v61->dwStatus == 0;
                  if ( !v62 )
                  {
                    v58 = 1;
                    break;
                  }
                  v40 = (unsigned int)(v40 + 1);
                  ++v61;
                }
                v60 = (unsigned int)(v60 + 1);
                ++v59;
                if ( (unsigned int)v60 >= v83 )
                {
                  if ( v58 )
                    goto LABEL_150;
                  goto LABEL_123;
                }
              }
              goto LABEL_150;
            }
LABEL_123:
            if ( a8 )
            {
              if ( v34 == -2147217887 )
              {
                v63 = v84;
              }
              else
              {
                if ( v34 != 265946 )
                  goto LABEL_148;
                v63 = v84;
                if ( !v84 )
                  goto LABEL_148;
                if ( *a8 )
                {
                  if ( v88 )
                  {
                    ((void (__fastcall *)(struct IUnknown *, struct tagDBPROPSET *, unsigned __int64, __int64))v88->lpVtbl->Release)(
                      v88,
                      v59,
                      v40,
                      v60);
                    v88 = 0;
                  }
                  ((void (__fastcall *)(_QWORD, struct tagDBPROPSET *, unsigned __int64, __int64))(*a8)->lpVtbl->Release)(
                    *a8,
                    v59,
                    v40,
                    v60);
                  *a8 = 0;
                  if ( v96 )
                  {
                    ((void (__fastcall *)(struct IUnknown *))v96->lpVtbl->Release)(v96);
                    v96 = 0;
                  }
                }
              }
              v89[0] = 0;
              v86 = 0;
              v64 = CImmediateRowset::CreateFoRoProps((CImmediateRowset *)v17, v89, &v86, v63);
              if ( v64 < 0 )
              {
                if ( (bidGblFlags & 2) != 0
                  && (OLEDBTraceErr(v64, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x16Eu), (bidGblFlags & 2) != 0) )
                {
                  v12 = bidTraceHR(off_1800C8518[0], 374793, L"<COpenRowset::OpenRowset|Trace|HR> ", 2147942414LL);
                }
                else
                {
                  v12 = -2147024882;
                }
                goto LABEL_195;
              }
              v65 = v86;
              v66 = v89[0];
              v12 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct tagDBID *, struct tagDBID *, GUID *, unsigned int, struct tagDBPROPSET *, struct IUnknown **))Provider->lpVtbl[1].QueryInterface)(
                      Provider,
                      0,
                      v100,
                      v106,
                      &IID_IUnknown,
                      v89[0],
                      v86,
                      a8);
              FreeMPMallocedPropSets(v66, v65);
              if ( (v12 & 0x80000000) != 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v12, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x180u);
                  if ( (bidGblFlags & 2) != 0 )
                    v12 = bidTraceHR(off_1800C8518[0], 398345, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
                }
                goto LABEL_195;
              }
              v67 = *a8;
              v85 = 0;
              (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IRDSService, &v85);
              v12 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, struct IUnknown *, struct IUnknown **))(*(_QWORD *)v85 + 32LL))(
                      v85,
                      v107,
                      v67,
                      a8);
              LODWORD(v86) = v12;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              ((void (__fastcall *)(struct IUnknown *))v67->lpVtbl->Release)(v67);
              if ( (v12 & 0x80000000) != 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                  OLEDBTraceErr(v12, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x19Du);
                *a8 = 0;
                if ( (bidGblFlags & 2) != 0 )
                  v12 = bidTraceHR(off_1800C8518[0], 430089, L"<COpenRowset::OpenRowset|Trace|HR> ", v12);
LABEL_195:
                if ( Provider )
                  ((void (__fastcall *)(struct IUnknown *, __int64))Provider->lpVtbl->Release)(Provider, m);
                if ( !v17 )
                  goto LABEL_199;
                goto LABEL_198;
              }
              v57 = (unsigned int)psz;
            }
LABEL_148:
            v12 = v57;
            if ( !v57 )
              v12 = (unsigned int)v86;
            goto LABEL_171;
          }
        }
        if ( (CDPO::GetOLEDBServices(CDPO) & 4) != 0 )
        {
          *(GUID *)v110 = IID_IRowsetInfo;
          v75 = CAcm::InsertDynamicInterface(v105, (struct _GUID *)v110);
          v76 = v75;
          if ( v75 < 0 )
          {
            if ( (bidGblFlags & 2) != 0
              && (OLEDBTraceErr(v75, L"<COpenRowset::OpenRowset|OLEDB|ERR> ", 0x1EDu), (bidGblFlags & 2) != 0) )
            {
              v12 = bidTraceHR(off_1800C8518[0], 504841, L"<COpenRowset::OpenRowset|Trace|HR> ", v76);
            }
            else
            {
              v12 = v76;
            }
            goto LABEL_195;
          }
        }
        goto LABEL_171;
      }
    }
  }
  result = (*(__int64 (__fastcall **)(COpenRowset *, struct IUnknown *, struct tagDBID *))(*(_QWORD *)this + 40LL))(
             this,
             v9,
             a3);
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(off_1800C8518[0], 121865, L"<COpenRowset::OpenRowset|Trace|HR> ", (unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x180078fb0  push    rbp
0x180078fb2  push    rbx
0x180078fb3  push    rsi
0x180078fb4  push    rdi
0x180078fb5  push    r12
0x180078fb7  push    r13
0x180078fb9  push    r14
0x180078fbb  push    r15
0x180078fbd  sub     rsp, 1B8h
0x180078fc4  lea     rbp, [rsp+50h]
0x180078fc9  mov     rax, cs:__security_cookie
0x180078fd0  xor     rax, rbp
0x180078fd3  mov     [rbp+1A0h+var_50], rax
0x180078fda  mov     [rbp+1A0h+var_E8], r9
0x180078fe1  mov     r12, r8
0x180078fe4  mov     [rbp+1A0h+var_118], r8
0x180078feb  mov     rsi, rdx
0x180078fee  mov     [rbp+1A0h+var_160], rdx
0x180078ff2  mov     r15, rcx
0x180078ff5  mov     qword ptr [rbp+1A0h+var_C0], rcx
0x180078ffc  mov     [rbp+1A0h+var_D8], rdx
0x180079003  mov     rdi, [rbp+1A0h+arg_20]
0x18007900a  mov     [rbp+1A0h+var_E0], rdi
0x180079011  mov     edx, [rbp+1A0h+arg_28]
0x180079017  mov     [rbp+1A0h+var_150], edx
0x18007901a  mov     r8, [rbp+1A0h+arg_30]
0x180079021  mov     [rbp+1A0h+var_110], r8
0x180079028  mov     r13, [rbp+1A0h+arg_38]
0x18007902f  mov     [rbp+1A0h+var_F8], r13
0x180079036  xor     ebx, ebx
0x180079038  mov     [rbp+1A0h+var_100], rbx
0x18007903f  mov     [rbp+1A0h+var_120], rbx
0x180079046  mov     [rbp+1A0h+var_138], rbx
0x18007904a  mov     [rbp+1A0h+var_178], rbx
0x18007904e  mov     [rbp+1A0h+var_D0], rbx
0x180079055  mov     [rbp+1A0h+pUnkOuter], rbx
0x180079059  mov     [rbp+1A0h+var_128], rbx
0x18007905d  mov     [rbp+1A0h+var_158], rbx
0x180079061  mov     [rbp+1A0h+var_14C], 0FFFFFFFFh
0x180079068  mov     [rbp+1A0h+var_108], rbx
0x18007906f  mov     r14, [rcx+38h]
0x180079073  test    r13, r13
0x180079076  jz      short loc_18007907C
0x180079078  mov     [r13+0], rbx
0x18007907c  test    r12, r12
0x18007907f  jnz     short loc_1800790D2
0x180079081  test    r9, r9
0x180079084  jnz     short loc_1800790D2
0x180079086  mov     edi, 80070057h
0x18007908b  test    byte ptr cs:_bidGblFlags, 2
0x180079092  jz      short loc_1800790CD
0x180079094  lea     r8d, [r12+69h]; unsigned int
0x180079099  lea     rdx, aCopenrowsetOpe_3; "<COpenRowset::OpenRowset|OLEDB|ERR> "
0x1800790a0  mov     ecx, edi; int
0x1800790a2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800790a7  test    byte ptr cs:_bidGblFlags, 2
0x1800790ae  jz      short loc_1800790CD
0x1800790b0  mov     r9d, edi
0x1800790b3  lea     r8, aCopenrowsetOpe_0; "<COpenRowset::OpenRowset|Trace|HR> "
0x1800790ba  mov     edx, 1A409h
0x1800790bf  mov     rcx, cs:off_1800C8518; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800790c6  call    _bidTraceHR
0x1800790cb  mov     edi, eax
0x1800790cd  jmp     loc_180079FFA
0x1800790d2  mov     rax, [rdi]
0x1800790d5  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800790dc  jnz     short loc_1800790E9
0x1800790de  mov     rax, [rdi+8]
0x1800790e2  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800790e9  test    rax, rax
0x1800790ec  jz      loc_180079F3B
0x1800790f2  mov     rax, [rdi]
0x1800790f5  sub     rax, qword ptr cs:IID_IStream.Data1
0x1800790fc  jnz     short loc_180079109
0x1800790fe  mov     rax, [rdi+8]
0x180079102  sub     rax, qword ptr cs:IID_IStream.Data4
0x180079109  test    rax, rax
0x18007910c  jz      loc_180079F3B
0x180079112  mov     rax, [rdi]
0x180079115  sub     rax, qword ptr cs:IID_ISequentialStream.Data1
0x18007911c  jnz     short loc_180079129
0x18007911e  mov     rax, [rdi+8]
0x180079122  sub     rax, qword ptr cs:IID_ISequentialStream.Data4
0x180079129  test    rax, rax
0x18007912c  jz      loc_180079F3B
0x180079132  mov     rcx, rdi; struct _GUID *
0x180079135  call    ?IsRowIID@CRCM@@SA_NAEBU_GUID@@@Z; CRCM::IsRowIID(_GUID const &)
0x18007913a  test    al, al
0x18007913c  jnz     loc_180079F3B
0x180079142  mov     edx, 1300000h
0x180079147  mov     r8d, 78h ; 'x'
0x18007914d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180079154  call    cs:__imp_MpHeapAlloc
0x18007915a  mov     rsi, rax
0x18007915d  mov     [rbp+1A0h+var_F0], rax
0x180079164  test    rax, rax
0x180079167  jz      loc_180079EE7
0x18007916d  mov     [rax+8], rdi
0x180079171  mov     rax, [rbp+1A0h+var_160]
0x180079175  mov     [rsi], rax
0x180079178  mov     eax, [rbp+1A0h+var_150]
0x18007917b  mov     [rsi+10h], eax
0x18007917e  mov     rax, [rbp+1A0h+var_110]
0x180079185  mov     [rsi+18h], rax
0x180079189  mov     [rsi+20h], r13
0x18007918d  mov     [rsi+50h], rbx
0x180079191  mov     [rsi+58h], rbx
0x180079195  mov     [rsi+48h], rbx
0x180079199  mov     [rsi+60h], rbx
0x18007919d  mov     [rsi+28h], rbx
0x1800791a1  mov     [rsi+30h], ebx
0x1800791a4  mov     [rsi+38h], rbx
0x1800791a8  mov     [rsi+41h], ebx
0x1800791ab  mov     [rsi+40h], bl
0x1800791ae  mov     [rsi+45h], bl
0x1800791b1  mov     [rsi+68h], rbx
0x1800791b5  mov     [rbp+1A0h+var_120], rsi
0x1800791bc  test    rsi, rsi
0x1800791bf  jz      loc_180079EEE
0x1800791c5  mov     rcx, rsi; this
0x1800791c8  call    ?ValidateParameters@CImmediateRowset@@QEAAJXZ; CImmediateRowset::ValidateParameters(void)
0x1800791cd  mov     edi, eax
0x1800791cf  test    eax, eax
0x1800791d1  jns     short loc_18007921D
0x1800791d3  mov     eax, cs:_bidGblFlags
0x1800791d9  test    al, 2
0x1800791db  jz      short loc_180079218
0x1800791dd  mov     r8d, 82h; unsigned int
0x1800791e3  lea     rdx, aCopenrowsetOpe_3; "<COpenRowset::OpenRowset|OLEDB|ERR> "
0x1800791ea  mov     ecx, edi; int
0x1800791ec  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800791f1  mov     eax, cs:_bidGblFlags
0x1800791f7  test    al, 2
0x1800791f9  jz      short loc_180079218
0x1800791fb  mov     r9d, edi
0x1800791fe  lea     r8, aCopenrowsetOpe_0; "<COpenRowset::OpenRowset|Trace|HR> "
0x180079205  mov     edx, 20809h
0x18007920a  mov     rcx, cs:off_1800C8518; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180079211  call    _bidTraceHR
0x180079216  mov     edi, eax
0x180079218  jmp     loc_180079FD1
0x18007921d  lea     rdx, IID_IOpenRowset
0x180079224  mov     rcx, [r15+38h]
0x180079228  call    ??$GetProviderPointer@VCSCM@@@@YAPEAXPEAV?$CComObject@VCSCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CSCM>(ATL::CComObject<CSCM> *,_GUID const &)
0x18007922d  mov     [rbp+1A0h+var_168], rax
0x180079231  mov     [rbp+1A0h+var_100], rax
0x180079238  lea     rax, [rbp+1A0h+var_178]
0x18007923c  mov     [rsp+1F0h+ppv], rax; __int64
0x180079241  lea     r9, [rbp+1A0h+var_138]
0x180079245  mov     rcx, [r15+38h]; void *
0x180079249  call    ?SetupNewCM@?$SetupCM@VCSCM@@VCRCM@@@@SAJPEAV?$CComObject@VCSCM@@@ATL@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@PEAPEAUIService@@@Z; SetupCM<CSCM,CRCM>::SetupNewCM(ATL::CComObject<CSCM> *,IUnknown *,_GUID const &,IUnknown * *,IService * *)
0x18007924e  mov     edi, eax
0x180079250  test    eax, eax
0x180079252  jns     short loc_18007929C
0x180079254  test    byte ptr cs:_bidGblFlags, 2
0x18007925b  jz      short loc_180079297
0x18007925d  mov     r8d, 89h; unsigned int
0x180079263  lea     rdx, aCopenrowsetOpe_3; "<COpenRowset::OpenRowset|OLEDB|ERR> "
0x18007926a  mov     ecx, eax; int
0x18007926c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180079271  test    byte ptr cs:_bidGblFlags, 2
0x180079278  jz      short loc_180079297
0x18007927a  mov     r9d, edi
0x18007927d  lea     r8, aCopenrowsetOpe_0; "<COpenRowset::OpenRowset|Trace|HR> "
0x180079284  mov     edx, 22409h
0x180079289  mov     rcx, cs:off_1800C8518; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180079290  call    _bidTraceHR
0x180079295  mov     edi, eax
0x180079297  jmp     loc_180079FB7
0x18007929c  mov     rax, [rbp+1A0h+var_178]
0x1800792a0  mov     [rbp+1A0h+var_F0], rax
0x1800792a7  mov     rax, rbx
0x1800792aa  mov     [rbp+1A0h+psz], rbx
0x1800792ae  test    r12, r12
0x1800792b1  jz      short loc_1800792DB
0x1800792b3  test    dword ptr [r12+10h], 0FFFFFFFCh
0x1800792bc  jnz     short loc_1800792DB
0x1800792be  mov     r12d, 1
0x1800792c4  mov     rcx, [rbp+1A0h+var_118]
0x1800792cb  cmp     [rcx+10h], r12d
0x1800792cf  jz      short loc_1800792E1
0x1800792d1  mov     rax, [rcx+18h]
0x1800792d5  mov     [rbp+1A0h+psz], rax
0x1800792d9  jmp     short loc_1800792E1
0x1800792db  mov     r12d, 1
0x1800792e1  test    r14, r14
0x1800792e4  lea     r8, [r14+0C0h]
0x1800792eb  jnz     short loc_1800792F0
0x1800792ed  mov     r8, rbx; struct CMCommonPropertyClass *
0x1800792f0  mov     r9, rax; unsigned __int16 *
0x1800792f3  mov     rdx, [rbp+1A0h+var_168]; struct IUnknown *
0x1800792f7  mov     rcx, rsi; this
0x1800792fa  call    ?Initialize@CImmediateRowset@@QEAAJPEAUIUnknown@@PEAVCMCommonPropertyClass@@PEBG@Z; CImmediateRowset::Initialize(IUnknown *,CMCommonPropertyClass *,ushort const *)
0x1800792ff  mov     edi, eax
0x180079301  test    eax, eax
0x180079303  jns     short loc_18007934D
0x180079305  test    byte ptr cs:_bidGblFlags, 2
0x18007930c  jz      short loc_180079348
0x18007930e  mov     r8d, 96h; unsigned int
0x180079314  lea     rdx, aCopenrowsetOpe_3; "<COpenRowset::OpenRowset|OLEDB|ERR> "
0x18007931b  mov     ecx, eax; int
0x18007931d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180079322  test    byte ptr cs:_bidGblFlags, 2
0x180079329  jz      short loc_180079348
0x18007932b  mov     r9d, edi
0x18007932e  lea     r8, aCopenrowsetOpe_0; "<COpenRowset::OpenRowset|Trace|HR> "
0x180079335  mov     edx, 25809h
0x18007933a  mov     rcx, cs:off_1800C8518; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180079341  call    _bidTraceHR
0x180079346  mov     edi, eax
0x180079348  jmp     loc_180079FB7
0x18007934d  mov     [rbp+1A0h+var_180], rbx
0x180079351  mov     r15d, 2
0x180079357  mov     dword ptr [rbp+1A0h+var_190], r15d
0x18007935b  lea     r9, [rbp+1A0h+var_180]; struct tagDBPROPSET **
0x18007935f  mov     r8, [rsi+18h]; struct tagDBPROPSET *
0x180079363  mov     edx, [rsi+10h]; unsigned int
0x180079366  lea     rcx, DBPROPSET_ROWSET; struct _GUID *
0x18007936d  call    ?FindPropSet@@YAKAEBU_GUID@@KPEAUtagDBPROPSET@@PEAPEAU2@@Z; FindPropSet(_GUID const &,ulong,tagDBPROPSET *,tagDBPROPSET * *)
0x180079372  or      edi, 0FFFFFFFFh
0x180079375  cmp     eax, edi
0x180079377  jz      short loc_1800793B2
0x180079379  mov     [rbp+1A0h+var_188], rbx
0x18007937d  lea     r8, [rbp+1A0h+var_188]; struct tagDBPROP **
0x180079381  mov     edx, 104h; unsigned int
0x180079386  mov     rcx, [rbp+1A0h+var_180]; struct tagDBPROPSET *
0x18007938a  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x18007938f  cmp     eax, edi
0x180079391  jz      short loc_1800793B2
0x180079393  mov     rax, [rbp+1A0h+var_188]
0x180079397  mov     [rax+8], ebx
0x18007939a  cmp     [rax+4], ebx
0x18007939d  jnz     short loc_1800793B2
0x18007939f  mov     r15d, ebx
0x1800793a2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800793a6  cmp     [rax+38h], cx
0x1800793aa  setnz   r15b
0x1800793ae  mov     dword ptr [rbp+1A0h+var_190], r15d
0x1800793b2  mov     rcx, r14; this
0x1800793b5  call    ?GetRootAcm@CAcm@@QEAAPEAV1@XZ; CAcm::GetRootAcm(void)
0x1800793ba  mov     rdi, rax
0x1800793bd  mov     rcx, rax; this
0x1800793c0  call    ?GetCDPO@CDCM@@QEAAPEAVCDPO@@XZ; CDCM::GetCDPO(void)
0x1800793c5  mov     r14, rax
0x1800793c8  mov     qword ptr [rbp+1A0h+var_170], rax
0x1800793cc  mov     rcx, rax; this
0x1800793cf  call    ?GetOLEDBServices@CDPO@@QEAAKXZ; CDPO::GetOLEDBServices(void)
0x1800793d4  test    al, 4
0x1800793d6  jz      short loc_1800793E4
0x1800793d8  mov     rcx, rdi; this
0x1800793db  call    ?DCMAllowsFoxCE@CDCM@@QEAA_NXZ; CDCM::DCMAllowsFoxCE(void)
0x1800793e0  test    al, al
0x1800793e2  jnz     short loc_1800793EB
0x1800793e4  mov     r15d, r12d
0x1800793e7  mov     dword ptr [rbp+1A0h+var_190], r12d
0x1800793eb  mov     rax, [r14+78h]
0x1800793ef  mov     al, [rax+438h]
0x1800793f5  mov     [rbp+1A0h+var_198], al
0x1800793f8  mov     [rbp+1A0h+var_19C], ebx
0x1800793fb  mov     [rbp+1A0h+var_180], rbx
0x1800793ff  lea     r9, [rbp+1A0h+var_188]; struct tagDBPROP **
0x180079403  lea     r8, [rbp+1A0h+var_180]; struct tagDBPROPSET **
0x180079407  lea     rdx, [rbp+1A0h+var_19C]; unsigned int *
0x18007940b  mov     rcx, rsi; this
0x18007940e  call    ?AddPropertiesForRequestedInterface@CImmediateRowset@@QEAAJPEAKPEAPEAUtagDBPROPSET@@PEAPEAUtagDBPROP@@@Z; CImmediateRowset::AddPropertiesForRequestedInterface(ulong *,tagDBPROPSET * *,tagDBPROP * *)
0x180079413  mov     edi, eax
0x180079415  test    eax, eax
0x180079417  jns     short loc_180079461
0x180079419  test    byte ptr cs:_bidGblFlags, 2
0x180079420  jz      short loc_18007945C
0x180079422  mov     r8d, 0A8h; unsigned int
0x180079428  lea     rdx, aCopenrowsetOpe_3; "<COpenRowset::OpenRowset|OLEDB|ERR> "
0x18007942f  mov     ecx, eax; int
0x180079431  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180079436  test    byte ptr cs:_bidGblFlags, 2
0x18007943d  jz      short loc_18007945C
0x18007943f  mov     r9d, edi
0x180079442  lea     r8, aCopenrowsetOpe_0; "<COpenRowset::OpenRowset|Trace|HR> "
0x180079449  mov     edx, 2A009h
0x18007944e  mov     rcx, cs:off_1800C8518; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180079455  call    _bidTraceHR
0x18007945a  mov     edi, eax
0x18007945c  jmp     loc_180079FB7
0x180079461  mov     [rbp+1A0h+var_188], rbx
0x180079465  lea     r9, [rbp+1A0h+var_188]; struct tagDBPROPSET **
0x180079469  mov     r8, [rbp+1A0h+var_180]; struct tagDBPROPSET *
0x18007946d  mov     edi, [rbp+1A0h+var_19C]
0x180079470  mov     edx, edi; unsigned int
0x180079472  lea     rcx, DBPROPSET_ROWSET; struct _GUID *
0x180079479  call    ?FindPropSet@@YAKAEBU_GUID@@KPEAUtagDBPROPSET@@PEAPEAU2@@Z; FindPropSet(_GUID const &,ulong,tagDBPROPSET *,tagDBPROPSET * *)
0x18007947e  cmp     eax, 0FFFFFFFFh
0x180079481  jz      short loc_1800794E7
0x180079483  mov     r14, [rbp+1A0h+var_188]
0x180079487  mov     [rbp+1A0h+var_188], rbx
0x18007948b  lea     r8, [rbp+1A0h+var_188]; struct tagDBPROP **
0x18007948f  mov     edx, 104h; unsigned int
0x180079494  mov     rcx, r14; struct tagDBPROPSET *
0x180079497  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x18007949c  mov     edi, eax
0x18007949e  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
