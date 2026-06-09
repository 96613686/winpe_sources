# CContext::PushError(void)

- ea: `0x180020fc0`
- end: `0x180021c3f`
- name: `?PushError@CContext@@QEAAHXZ`
- size: `3199`
- prototype: `__int64 __fastcall(CContext *__hidden this)`
- caller_count: `93`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002990`
- `0x180003b00`
- `0x180006a34`
- `0x180006c70`
- `0x180007900`
- `0x180007e90`
- `0x180008ec0`
- `0x1800093b0`
- `0x18000a320`
- `0x18000ab60`
- `0x18000b830`
- `0x18000bbc0`
- `0x18000d530`
- `0x18000e020`
- `0x18000e370`
- `0x18000f9d0`
- `0x180011b60`
- `0x180011e40`
- `0x180012824`
- `0x1800139d0`
- `0x180014150`
- `0x1800145d0`
- `0x18001bb80`
- `0x18001c470`
- `0x18001cc80`
- `0x18001d6f0`
- `0x18001e6d0`
- `0x18001fb90`
- `0x180020da0`
- `0x180020de0`
- `0x180020e20`
- `0x180020e50`
- `0x180021fd0`
- `0x180022660`
- `0x180023510`
- `0x180024d50`
- `0x18002536c`
- `0x180025fd0`
- `0x180026760`
- `0x180026d10`
- `0x180026fe0`
- `0x180027ef0`
- `0x180028640`
- `0x180028d48`
- `0x180029830`
- `0x18002d044`
- `0x18002d370`
- `0x18002ddd4`
- `0x18002e050`
- `0x18002e670`

## callees

- `0x180001514`
- `0x180020fc0`
- `0x180021c50`
- `0x180026c74`
- `0x180026cc0`
- `0x180034b10`
- `0x18004c520`
- `0x18005c76c`
- `0x180069aec`
- `0x1800cb5cc`
- `0x1800ccaa4`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x1800214eb`
- `KERNEL32!GetUserDefaultLCID` at `0x180021675`
- `KERNEL32!GetUserDefaultLCID` at `0x180021a5d`
- `KERNEL32!GetUserDefaultLCID` at `0x1800214eb`
- `KERNEL32!GetUserDefaultLCID` at `0x180021675`
- `KERNEL32!GetUserDefaultLCID` at `0x180021a5d`
- `ADVAPI32!RegCloseKey` at `0x180021863`
- `ADVAPI32!RegCloseKey` at `0x18002187f`
- `ADVAPI32!RegCloseKey` at `0x180021863`
- `ADVAPI32!RegCloseKey` at `0x18002187f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002180d`
- `ADVAPI32!RegOpenKeyExW` at `0x18002184e`
- `ADVAPI32!RegOpenKeyExW` at `0x18002180d`
- `ADVAPI32!RegOpenKeyExW` at `0x18002184e`
- `ole32!CoCreateInstance` at `0x1800211c5`
- `ole32!CoCreateInstance` at `0x1800214cb`
- `ole32!CoCreateInstance` at `0x180021762`
- `ole32!CoCreateInstance` at `0x1800211c5`
- `ole32!CoCreateInstance` at `0x1800214cb`
- `ole32!CoCreateInstance` at `0x180021762`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180021531`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800215ca`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180021531`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800215ca`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800213bf`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021561`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800213bf`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021561`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002112d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002112d`

## string_xrefs

- `0x1800217ff`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CContext::PushError(CContext *this)
{
  int v2; // ecx
  bool v3; // r14
  __int64 v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  _QWORD *v7; // rax
  char v8; // r15
  __int64 v9; // rcx
  IErrorInfo *v10; // rcx
  __int64 v11; // rcx
  __int64 (*v12)(void); // rax
  struct _GUID *v13; // rax
  struct _GUID *v14; // r8
  __int64 v16; // rax
  struct IErrorInfo *v17; // r14
  __int64 v18; // rcx
  char v19; // bl
  unsigned int i; // r12d
  void (__fastcall *v21)(__int64, _QWORD, _QWORD, struct IErrorInfo **); // rbx
  LCID v22; // eax
  unsigned int v23; // r13d
  int (__fastcall *v24)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  LCID UserDefaultLCID; // eax
  bool v26; // zf
  HRESULT (__stdcall *SetGUID)(ICreateErrorInfo *, const GUID *const); // rax
  int v28; // eax
  __int64 (*v29)(void); // rax
  struct _GUID *v30; // rax
  struct _GUID *v31; // r8
  struct _GUID *v32; // rax
  struct _GUID *v33; // r8
  const struct _GUID *v34; // rdx
  int v35; // r8d
  int v36; // r9d
  const WCHAR *v37; // rax
  struct _GUID *v38; // rax
  struct _GUID *v39; // r8
  struct _GUID *v40; // rax
  struct _GUID *v41; // r8
  int v42; // ebx
  void (__fastcall *v43)(__int64, _QWORD, _QWORD, struct IErrorInfo **); // rbx
  LCID v44; // eax
  _QWORD *j; // rbx
  struct IUnknown *v46; // rbx
  __int64 v47; // r10
  __int64 v48; // rcx
  _QWORD *v49; // rcx
  int *ppv; // [rsp+20h] [rbp-278h]
  IErrorInfo *perrinfo; // [rsp+40h] [rbp-258h] BYREF
  unsigned int v52; // [rsp+48h] [rbp-250h] BYREF
  __int64 v53; // [rsp+50h] [rbp-248h] BYREF
  __int64 v54; // [rsp+58h] [rbp-240h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+60h] [rbp-238h] BYREF
  __int64 v56; // [rsp+68h] [rbp-230h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-228h] BYREF
  __int64 v58; // [rsp+78h] [rbp-220h] BYREF
  struct IErrorInfo *v59; // [rsp+80h] [rbp-218h] BYREF
  struct tagDISPPARAMS v60; // [rsp+88h] [rbp-210h] BYREF
  CContext *v61; // [rsp+A0h] [rbp-1F8h]
  __int128 v62; // [rsp+A8h] [rbp-1F0h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-1E0h]
  char v64[96]; // [rsp+C0h] [rbp-1D8h] BYREF
  _OWORD v65[3]; // [rsp+120h] [rbp-178h] BYREF
  char v66[8]; // [rsp+150h] [rbp-148h] BYREF
  struct IUnknown *v67; // [rsp+158h] [rbp-140h]
  __int16 v68; // [rsp+168h] [rbp-130h]
  __int64 *v69; // [rsp+170h] [rbp-128h]
  __int64 *v70; // [rsp+230h] [rbp-68h]
  int v71; // [rsp+240h] [rbp-58h]

  v61 = this;
  perrinfo = 0;
  v2 = *((_DWORD *)this + 10);
  if ( (unsigned int)(v2 + 2146825288) <= 0x2F2 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 >= 0 )
      goto LABEL_3;
  }
  if ( *(int *)(*(_QWORD *)this + 24LL) >= 0 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)this + 16LL);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
    }
  }
LABEL_3:
  v4 = *(_QWORD *)this;
  if ( *(_DWORD *)(*(_QWORD *)this + 8LL) == 1 )
  {
    if ( *(_BYTE *)(v4 + 30) )
    {
      v6 = 0;
    }
    else
    {
      v5 = (_QWORD *)*((_QWORD *)this + 4);
      do
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD *))(*v5 + 184LL))(v5);
        if ( v6 )
          break;
        v7 = (_QWORD *)v5[4];
        if ( v5 == v7 )
          goto LABEL_11;
        v5 = (_QWORD *)v5[4];
      }
      while ( v7 );
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
    }
LABEL_11:
    ++*(_DWORD *)(*(_QWORD *)this + 8LL);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
    memset(&v60, 0, sizeof(v60));
    v62 = 0;
    v63 = 0;
    v8 = 0;
    LOWORD(v62) = 3;
    v9 = *(_QWORD *)this;
    DWORD2(v62) = *(_DWORD *)(*(_QWORD *)this + 44LL);
    if ( *(_DWORD *)(v9 + 44) )
    {
      v60.cArgs = 1;
      v60.rgvarg = (VARIANTARG *)&v62;
    }
    if ( !v3 )
    {
      if ( GetErrorInfo(0, &perrinfo) < 0 )
        goto LABEL_32;
      v10 = perrinfo;
      if ( perrinfo )
      {
LABEL_35:
        v16 = *(_QWORD *)this;
        v17 = *(struct IErrorInfo **)(*(_QWORD *)this + 16LL);
        if ( v17 || v10 )
        {
          v59 = 0;
          v54 = 0;
          v52 = 0;
          memset(v65, 0, 44);
          pperrinfo = 0;
          phkResult = 0;
          if ( v17 )
            *((_DWORD *)this + 10) = *(_DWORD *)(v16 + 24);
          else
            v17 = v10;
          if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
                 v17,
                 &IID_IErrorRecords,
                 &v54) >= 0 )
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v54 + 64LL))(v54, &v52);
          if ( !v52 )
            goto LABEL_42;
          v19 = 1;
          for ( i = v52 - 1; (i & 0x80000000) == 0; --i )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)v54 + 32LL))(v54, i, v65) )
            {
              if ( SLODWORD(v65[0]) < 0 || *((int *)this + 10) >= 0 )
              {
                *((_DWORD *)this + 10) = v65[0];
                goto LABEL_64;
              }
              v19 = 0;
            }
          }
          if ( !v19 )
            goto LABEL_42;
LABEL_64:
          v58 = 0;
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v54)(
                 v54,
                 &GUID_6a0d3941_c846_11d2_a99a_00600852f914,
                 &v58) < 0 )
          {
            if ( CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&phkResult) < 0
              || (**(__int64 (__fastcall ***)(HKEY, GUID *, ICreateErrorInfo **))phkResult)(
                   phkResult,
                   &IID_IErrorRecords,
                   &pperrinfo) < 0
              || (**(__int64 (__fastcall ***)(HKEY, GUID *, __int64 *))phkResult)(
                   phkResult,
                   &GUID_6a0d3941_c846_11d2_a99a_00600852f914,
                   &v58) < 0 )
            {
              goto LABEL_72;
            }
            v23 = v52;
            while ( (--v23 & 0x80000000) == 0 )
            {
              v53 = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)v54 + 32LL))(v54, v23, v65) < 0
                || (*(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v54 + 40LL))(
                     v54,
                     v23,
                     &IID_IUnknown,
                     &v53) < 0
                && (v24 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v54 + 48LL),
                    UserDefaultLCID = GetUserDefaultLCID(),
                    v24(v54, v23, UserDefaultLCID, &v53) < 0)
                || ((v26 = (unsigned int)ISOLEDBError(*((_DWORD *)this + 10)) == 0,
                     SetGUID = pperrinfo->lpVtbl->SetGUID,
                     v26)
                  ? (v28 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _OWORD *, _QWORD, _QWORD, __int64, _DWORD))SetGUID)(
                             pperrinfo,
                             v65,
                             0,
                             0,
                             v53,
                             0))
                  : (v28 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _OWORD *, __int64, _QWORD, __int64, _DWORD))SetGUID)(
                             pperrinfo,
                             v65,
                             0x10000000,
                             0,
                             v53,
                             0)),
                    v28 < 0) )
              {
                ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v53);
                goto LABEL_72;
              }
              ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v53);
            }
          }
          LODWORD(v56) = 0;
          if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 32LL))(v58, &v56)
            || (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 24LL))(v58, i) >= 0 )
          {
            if ( phkResult )
              v17 = (struct IErrorInfo *)phkResult;
            goto LABEL_69;
          }
LABEL_72:
          v21 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, struct IErrorInfo **))(*(_QWORD *)v54 + 48LL);
          v22 = GetUserDefaultLCID();
          v21(v54, i, v22, &v59);
LABEL_69:
          if ( v58 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
LABEL_42:
          if ( *(_DWORD *)(*(_QWORD *)this + 44LL) )
          {
            if ( !v8 )
            {
              v56 = 0;
              v40 = (struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 192LL))(*((_QWORD *)this + 4));
              CContext::AddErrorRecord(this, v17, v41, v40, ppv, &v60, 1);
              ++v52;
              if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
                     v17,
                     &GUID_6a0d3941_c846_11d2_a99a_00600852f914,
                     &v56) < 0
                || (v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 24LL))(v56, 0),
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56),
                    v42 < 0) )
              {
                v53 = 0;
                if ( ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
                       v17,
                       &IID_IErrorRecords,
                       &v53) >= 0 )
                {
                  if ( v59 )
                  {
                    ((void (__fastcall *)(struct IErrorInfo *))v59->lpVtbl->Release)(v59);
                    v59 = 0;
                  }
                  v43 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, struct IErrorInfo **))(*(_QWORD *)v53 + 48LL);
                  v44 = GetUserDefaultLCID();
                  v43(v53, 0, v44, &v59);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                }
              }
            }
          }
          if ( v59 )
            v17 = v59;
          if ( v6 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IErrorInfo *, _DWORD))(*(_QWORD *)v6 + 24LL))(
              v6,
              v54,
              v52,
              v17,
              *((_DWORD *)this + 10));
          ((void (__fastcall *)(struct IErrorInfo *))v17->lpVtbl->AddRef)(v17);
          v18 = *(_QWORD *)(*(_QWORD *)this + 16LL);
          if ( v18 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
          }
          *(_QWORD *)(*(_QWORD *)this + 16LL) = v17;
          *(_DWORD *)(*(_QWORD *)this + 24LL) = *((_DWORD *)this + 10);
          if ( perrinfo )
          {
            ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
            perrinfo = 0;
          }
          if ( v59 )
          {
            ((void (__fastcall *)(struct IErrorInfo *))v59->lpVtbl->Release)(v59);
            v59 = 0;
          }
          if ( v54 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            v54 = 0;
          }
          SetErrorInfo(0, *(IErrorInfo **)(*(_QWORD *)this + 16LL));
          if ( *((int *)this + 10) >= 0 )
          {
            for ( j = (_QWORD *)*((_QWORD *)this + 4); j; j = v49 )
            {
              if ( (*(unsigned __int16 (__fastcall **)(_QWORD *))(*j + 168LL))(j) == 5
                && ((unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(j[31])
                 || (unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(j[30])) )
              {
                v46 = (struct IUnknown *)(j - 4);
                ((void (__fastcall *)(struct IUnknown *))v46->lpVtbl->AddRef)(v46);
                if ( !LODWORD(v46[10].lpVtbl) )
                {
                  CNfyContext::CNfyContext((CNfyContext *)v66, v46, 0, 0);
                  LODWORD(v56) = 1;
                  LODWORD(v58) = 0;
                  LODWORD(v53) = 0;
                  v68 = 16387;
                  v69 = &v56;
                  v70 = &v56;
                  CNfyContext::SetError((CNfyContext *)v66, *((_DWORD *)this + 10), 2u);
                  if ( (!(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v46[34].lpVtbl)
                     || (int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                               v47,
                               &v58,
                               v66) >= 0)
                    && (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(v46[35].lpVtbl) )
                  {
                    v67 = v46 + 1;
                    v71 = 1;
                    CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                      v48,
                      &v53,
                      v66);
                  }
                  CNfyContext::~CNfyContext((CNfyContext *)v66);
                }
                ((void (__fastcall *)(struct IUnknown *))v46->lpVtbl->Release)(v46);
                break;
              }
              v49 = (_QWORD *)j[4];
              if ( j == v49 )
                v49 = 0;
            }
          }
          if ( phkResult )
            (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
          if ( pperrinfo )
            ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
        }
LABEL_32:
        --*(_DWORD *)(*(_QWORD *)this + 8LL);
        if ( v6 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
        return 1;
      }
      if ( *(_QWORD *)(*(_QWORD *)this + 16LL) || *((_DWORD *)this + 10) == (_DWORD)perrinfo )
      {
LABEL_17:
        if ( !*(_QWORD *)(*(_QWORD *)this + 16LL) && *((_DWORD *)this + 10) )
        {
          if ( *((_BYTE *)g_pStaticGlobals + 16) == 0xFF )
          {
            pperrinfo = 0;
            *((_BYTE *)g_pStaticGlobals + 16) = 0;
            if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, (PHKEY)&pperrinfo) )
            {
              phkResult = 0;
              v37 = (const WCHAR *)CStrOfGUID::CStrOfGUID((CStrOfGUID *)v64, v34, v35, v36);
              if ( !RegOpenKeyExW((HKEY)pperrinfo, v37, 0, 0x20019u, &phkResult) )
              {
                RegCloseKey(phkResult);
                *((_BYTE *)g_pStaticGlobals + 16) = 1;
              }
              RegCloseKey((HKEY)pperrinfo);
            }
          }
          if ( !*((_BYTE *)g_pStaticGlobals + 16)
            || CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&perrinfo) < 0 )
          {
            pperrinfo = 0;
            if ( CreateErrorInfo(&pperrinfo) >= 0 )
            {
              ((void (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                pperrinfo,
                &IID_IErrorInfo,
                &perrinfo);
              ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
            }
          }
          if ( perrinfo )
          {
            v12 = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 192LL);
            if ( *(_DWORD *)(*(_QWORD *)this + 44LL) )
            {
              v38 = (struct _GUID *)v12();
              CContext::AddErrorRecord(this, perrinfo, v39, v38, ppv, &v60, 1);
            }
            else
            {
              v13 = (struct _GUID *)v12();
              CContext::AddErrorRecord(this, perrinfo, v14, v13, ppv, 0, v3);
            }
            *(_QWORD *)(*(_QWORD *)this + 16LL) = perrinfo;
            *(_DWORD *)(*(_QWORD *)this + 24LL) = *((_DWORD *)this + 10);
          }
          goto LABEL_32;
        }
        goto LABEL_35;
      }
      if ( CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&perrinfo) >= 0 )
      {
        v29 = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 192LL);
        if ( *(_DWORD *)(*(_QWORD *)this + 44LL) )
        {
          v32 = (struct _GUID *)v29();
          CContext::AddErrorRecord(this, perrinfo, v33, v32, ppv, &v60, 1);
          v8 = 1;
        }
        else
        {
          v30 = (struct _GUID *)v29();
          CContext::AddErrorRecord(this, perrinfo, v31, v30, ppv, 0, 0);
        }
      }
    }
    v10 = perrinfo;
    if ( perrinfo )
      goto LABEL_35;
    goto LABEL_17;
  }
  if ( !*(_QWORD *)(v4 + 16) && !v3 && GetErrorInfo(0, &perrinfo) >= 0 && perrinfo )
  {
    *(_QWORD *)(*(_QWORD *)this + 16LL) = perrinfo;
    SetErrorInfo(0, perrinfo);
    *(_DWORD *)(*(_QWORD *)this + 24LL) = *((_DWORD *)this + 10);
  }
  return 1;
}

```

## disassembly

```asm
0x180020fc0  mov     [rsp+arg_8], rbx
0x180020fc5  mov     [rsp+arg_10], rsi
0x180020fca  push    rdi
0x180020fcb  push    r12
0x180020fcd  push    r13
0x180020fcf  push    r14
0x180020fd1  push    r15
0x180020fd3  sub     rsp, 270h
0x180020fda  mov     rax, cs:__security_cookie
0x180020fe1  xor     rax, rsp
0x180020fe4  mov     [rsp+298h+var_38], rax
0x180020fec  mov     rsi, rcx
0x180020fef  mov     [rsp+298h+var_1F8], rcx
0x180020ff7  xor     r13d, r13d
0x180020ffa  mov     [rsp+298h+perrinfo], r13
0x180020fff  mov     ecx, [rcx+28h]
0x180021002  lea     eax, [rcx+7FF5F448h]
0x180021008  cmp     eax, 2F2h
0x18002100d  jbe     loc_180021170
0x180021013  xor     r14b, r14b
0x180021016  test    ecx, ecx
0x180021018  js      loc_180021173
0x18002101e  mov     rax, [rsi]
0x180021021  cmp     dword ptr [rax+8], 1
0x180021025  jnz     loc_180021517
0x18002102b  cmp     [rax+1Eh], r13b
0x18002102f  jnz     loc_1800215A5
0x180021035  mov     rbx, [rsi+20h]
0x180021039  nop     dword ptr [rax+00000000h]
0x180021040  mov     rax, [rbx]
0x180021043  mov     rcx, rbx
0x180021046  mov     rax, [rax+0B8h]
0x18002104d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021052  mov     rdi, rax
0x180021055  test    rax, rax
0x180021058  jnz     short loc_18002106B
0x18002105a  mov     rax, [rbx+20h]
0x18002105e  cmp     rbx, rax
0x180021061  jz      short loc_180021074
0x180021063  mov     rbx, rax
0x180021066  test    rax, rax
0x180021069  jnz     short loc_180021040
0x18002106b  test    rdi, rdi
0x18002106e  jnz     loc_1800216EA
0x180021074  mov     rax, [rsi]
0x180021077  inc     dword ptr [rax+8]
0x18002107a  test    rdi, rdi
0x18002107d  jnz     loc_18002157B
0x180021083  xorps   xmm0, xmm0
0x180021086  xor     eax, eax
0x180021088  movups  xmmword ptr [rsp+298h+var_210.rgvarg], xmm0
0x180021090  mov     qword ptr [rsp+298h+var_210.cArgs], rax
0x180021098  xorps   xmm1, xmm1
0x18002109b  movups  [rsp+298h+var_1F0], xmm1
0x1800210a3  mov     [rsp+298h+var_1E0], rax
0x1800210ab  xor     r15b, r15b
0x1800210ae  mov     eax, 3
0x1800210b3  mov     word ptr [rsp+298h+var_1F0], ax
0x1800210bb  mov     rcx, [rsi]
0x1800210be  mov     eax, [rcx+2Ch]
0x1800210c1  mov     dword ptr [rsp+298h+var_1F0+8], eax
0x1800210c8  cmp     dword ptr [rcx+2Ch], 0
0x1800210cc  jnz     loc_1800216FE
0x1800210d2  test    r14b, r14b
0x1800210d5  jz      loc_1800215C3
0x1800210db  mov     rcx, [rsp+298h+perrinfo]
0x1800210e0  test    rcx, rcx
0x1800210e3  jnz     loc_18002128F
0x1800210e9  mov     rax, [rsi]
0x1800210ec  cmp     qword ptr [rax+10h], 0
0x1800210f1  jnz     loc_18002128F
0x1800210f7  cmp     dword ptr [rsi+28h], 0
0x1800210fb  jz      loc_18002128F
0x180021101  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180021108  cmp     byte ptr [rax+10h], 0FFh
0x18002110c  jz      loc_1800217E3
0x180021112  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180021119  cmp     byte ptr [rax+10h], 0
0x18002111d  jnz     loc_1800211A5
0x180021123  mov     [rsp+298h+pperrinfo], r13
0x180021128  lea     rcx, [rsp+298h+pperrinfo]; pperrinfo
0x18002112d  call    cs:__imp_CreateErrorInfo
0x180021134  nop     dword ptr [rax+rax+00h]
0x180021139  test    eax, eax
0x18002113b  js      loc_1800211D9
0x180021141  mov     rcx, [rsp+298h+pperrinfo]
0x180021146  mov     rax, [rcx]
0x180021149  lea     r8, [rsp+298h+perrinfo]
0x18002114e  lea     rdx, IID_IErrorInfo
0x180021155  mov     rax, [rax]
0x180021158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002115d  mov     rcx, [rsp+298h+pperrinfo]
0x180021162  mov     rax, [rcx]
0x180021165  mov     rax, [rax+10h]
0x180021169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002116e  jmp     short loc_1800211D9
0x180021170  mov     r14b, 1
0x180021173  mov     rax, [rsi]
0x180021176  cmp     [rax+18h], r13d
0x18002117a  jl      loc_18002101E
0x180021180  mov     rcx, [rax+10h]
0x180021184  test    rcx, rcx
0x180021187  jz      loc_18002101E
0x18002118d  mov     rax, [rcx]
0x180021190  mov     rax, [rax+10h]
0x180021194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021199  mov     rax, [rsi]
0x18002119c  mov     [rax+10h], r13
0x1800211a0  jmp     loc_18002101E
0x1800211a5  lea     rax, [rsp+298h+perrinfo]
0x1800211aa  mov     [rsp+298h+ppv], rax; int *
0x1800211af  lea     r9, IID_IErrorInfo; riid
0x1800211b6  xor     edx, edx; pUnkOuter
0x1800211b8  mov     r8d, 1; dwClsContext
0x1800211be  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x1800211c5  call    cs:__imp_CoCreateInstance
0x1800211cc  nop     dword ptr [rax+rax+00h]
0x1800211d1  test    eax, eax
0x1800211d3  js      loc_180021123
0x1800211d9  cmp     [rsp+298h+perrinfo], 0
0x1800211df  jz      short loc_180021233
0x1800211e1  mov     rcx, [rsi+20h]
0x1800211e5  mov     rax, [rcx]
0x1800211e8  mov     rdx, [rax+0C0h]
0x1800211ef  mov     rax, [rsi]
0x1800211f2  cmp     dword ptr [rax+2Ch], 0
0x1800211f6  mov     rax, rdx
0x1800211f9  jnz     loc_180021890
0x1800211ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021204  mov     [rsp+298h+var_268], r14b; bool
0x180021209  mov     [rsp+298h+var_270], r13; struct tagDISPPARAMS *
0x18002120e  mov     r9, rax; struct _GUID *
0x180021211  mov     rdx, [rsp+298h+perrinfo]; struct IErrorInfo *
0x180021216  mov     rcx, rsi; this
0x180021219  call    ?AddErrorRecord@CContext@@QEAAJPEAUIErrorInfo@@PEAU_GUID@@1PEAJPEAUtagDISPPARAMS@@_N@Z; CContext::AddErrorRecord(IErrorInfo *,_GUID *,_GUID *,long *,tagDISPPARAMS *,bool)
0x18002121e  mov     rcx, [rsi]
0x180021221  mov     rax, [rsp+298h+perrinfo]
0x180021226  mov     [rcx+10h], rax
0x18002122a  mov     rcx, [rsi]
0x18002122d  mov     eax, [rsi+28h]
0x180021230  mov     [rcx+18h], eax
0x180021233  mov     rax, [rsi]
0x180021236  dec     dword ptr [rax+8]
0x180021239  test    rdi, rdi
0x18002123c  jz      short loc_18002125C
0x18002123e  mov     rax, [rdi]
0x180021241  mov     rcx, rdi
0x180021244  mov     rax, [rax+30h]
0x180021248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002124d  mov     rax, [rdi]
0x180021250  mov     rcx, rdi
0x180021253  mov     rax, [rax+10h]
0x180021257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002125c  mov     eax, 1
0x180021261  mov     rcx, [rsp+298h+var_38]
0x180021269  xor     rcx, rsp; StackCookie
0x18002126c  call    __security_check_cookie
0x180021271  lea     r11, [rsp+298h+var_28]
0x180021279  mov     rbx, [r11+38h]
0x18002127d  mov     rsi, [r11+40h]
0x180021281  mov     rsp, r11
0x180021284  pop     r15
0x180021286  pop     r14
0x180021288  pop     r13
0x18002128a  pop     r12
0x18002128c  pop     rdi
0x18002128d  retn
0x18002128f  mov     rax, [rsi]
0x180021292  mov     r14, [rax+10h]
0x180021296  test    r14, r14
0x180021299  jnz     short loc_1800212A0
0x18002129b  test    rcx, rcx
0x18002129e  jz      short loc_180021233
0x1800212a0  mov     [rsp+298h+var_218], r13
0x1800212a8  mov     [rsp+298h+var_240], r13
0x1800212ad  mov     [rsp+298h+var_250], r13d
0x1800212b2  xorps   xmm0, xmm0
0x1800212b5  movups  [rsp+298h+var_178], xmm0
0x1800212bd  movups  xmmword ptr [rsp+298h+var_168], xmm0
0x1800212c5  movups  xmmword ptr [rsp+298h+var_168+0Ch], xmm0
0x1800212cd  mov     [rsp+298h+pperrinfo], r13
0x1800212d2  mov     [rsp+298h+phkResult], r13
0x1800212d7  test    r14, r14
0x1800212da  jz      loc_180021408
0x1800212e0  mov     eax, [rax+18h]
0x1800212e3  mov     [rsi+28h], eax
0x1800212e6  mov     rax, [r14]
0x1800212e9  lea     r8, [rsp+298h+var_240]
0x1800212ee  lea     rdx, IID_IErrorRecords
0x1800212f5  mov     rcx, r14
0x1800212f8  mov     rax, [rax]
0x1800212fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021300  test    eax, eax
0x180021302  jns     loc_1800218BC
0x180021308  mov     eax, [rsp+298h+var_250]
0x18002130c  test    eax, eax
0x18002130e  jnz     loc_180021410
0x180021314  mov     rax, [rsi]
0x180021317  cmp     dword ptr [rax+2Ch], 0
0x18002131b  jnz     loc_180021978
0x180021321  mov     rax, [rsp+298h+var_218]
0x180021329  test    rax, rax
0x18002132c  jnz     loc_180021A99
0x180021332  test    rdi, rdi
0x180021335  jz      short loc_18002135A
0x180021337  mov     rax, [rdi]
0x18002133a  mov     ecx, [rsi+28h]
0x18002133d  mov     dword ptr [rsp+298h+ppv], ecx
0x180021341  mov     r9, r14
0x180021344  mov     r8d, [rsp+298h+var_250]
0x180021349  mov     rdx, [rsp+298h+var_240]
0x18002134e  mov     rcx, rdi
0x180021351  mov     rax, [rax+18h]
0x180021355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002135a  mov     rax, [r14]
0x18002135d  mov     rcx, r14
0x180021360  mov     rax, [rax+8]
0x180021364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021369  mov     rax, [rsi]
0x18002136c  mov     rcx, [rax+10h]
0x180021370  test    rcx, rcx
0x180021373  jnz     loc_180021AA1
0x180021379  mov     rax, [rsi]
0x18002137c  mov     [rax+10h], r14
0x180021380  mov     rcx, [rsi]
0x180021383  mov     eax, [rsi+28h]
0x180021386  mov     [rcx+18h], eax
0x180021389  mov     rcx, [rsp+298h+perrinfo]
0x18002138e  test    rcx, rcx
0x180021391  jnz     loc_1800215AD
0x180021397  mov     rcx, [rsp+298h+var_218]
0x18002139f  test    rcx, rcx
0x1800213a2  jnz     loc_180021AB9
0x1800213a8  mov     rcx, [rsp+298h+var_240]
0x1800213ad  test    rcx, rcx
0x1800213b0  jnz     loc_18002158F
0x1800213b6  mov     rdx, [rsi]
0x1800213b9  mov     rdx, [rdx+10h]; perrinfo
0x1800213bd  xor     ecx, ecx; dwReserved
0x1800213bf  call    cs:__imp_SetErrorInfo
0x1800213c6  nop     dword ptr [rax+rax+00h]
0x1800213cb  cmp     dword ptr [rsi+28h], 0
0x1800213cf  jge     loc_180021AD2
0x1800213d5  mov     rcx, [rsp+298h+phkResult]
0x1800213da  test    rcx, rcx
0x1800213dd  jz      short loc_1800213EC
0x1800213df  mov     rax, [rcx]
0x1800213e2  mov     rax, [rax+10h]
0x1800213e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213eb  nop
0x1800213ec  mov     rcx, [rsp+298h+pperrinfo]
0x1800213f1  test    rcx, rcx
0x1800213f4  jz      short loc_180021403
0x1800213f6  mov     rax, [rcx]
0x1800213f9  mov     rax, [rax+10h]
0x1800213fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021402  nop
0x180021403  jmp     loc_180021233
0x180021408  mov     r14, rcx
0x18002140b  jmp     loc_1800212E6
0x180021410  mov     bl, 1
0x180021412  lea     r12d, [rax-1]
0x180021416  test    r12d, r12d
0x180021419  jns     loc_1800218D7
0x18002141f  test    bl, bl
0x180021421  jz      loc_180021314
0x180021427  mov     [rsp+298h+var_220], r13
0x18002142c  mov     rcx, [rsp+298h+var_240]
0x180021431  mov     rax, [rcx]
0x180021434  lea     r8, [rsp+298h+var_220]
0x180021439  lea     rdx, _GUID_6a0d3941_c846_11d2_a99a_00600852f914
0x180021440  mov     rax, [rax]
0x180021443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021448  test    eax, eax
0x18002144a  js      short loc_1800214AB
0x18002144c  mov     dword ptr [rsp+298h+var_230], r13d
0x180021451  mov     rcx, [rsp+298h+var_220]
0x180021456  mov     rax, [rcx]
0x180021459  lea     rdx, [rsp+298h+var_230]
0x18002145e  mov     rax, [rax+20h]
0x180021462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021467  test    eax, eax
0x180021469  jz      short loc_180021483
0x18002146b  mov     rcx, [rsp+298h+var_220]
0x180021470  mov     rax, [rcx]
0x180021473  mov     edx, r12d
0x180021476  mov     rax, [rax+18h]
0x18002147a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002147f  test    eax, eax
0x180021481  js      short loc_1800214DF
0x180021483  mov     rax, [rsp+298h+phkResult]
0x180021488  test    rax, rax
0x18002148b  cmovnz  r14, rax
0x18002148f  mov     rcx, [rsp+298h+var_220]
0x180021494  test    rcx, rcx
0x180021497  jz      short loc_1800214A6
0x180021499  mov     rax, [rcx]
0x18002149c  mov     rax, [rax+10h]
0x1800214a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214a5  nop
  ... truncated ...
```
