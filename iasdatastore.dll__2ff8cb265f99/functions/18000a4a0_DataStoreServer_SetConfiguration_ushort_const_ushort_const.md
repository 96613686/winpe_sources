# DataStoreServer::SetConfiguration(ushort const *,ushort const *)

- ea: `0x18000a4a0`
- end: `0x18000b209`
- name: `?SetConfiguration@DataStoreServer@@QEAAJPEBG0@Z`
- size: `3433`
- prototype: `__int64 __fastcall(DataStoreServer *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006f90`
- `0x18000be1c`

## callees

- `0x180007150`
- `0x1800071ac`
- `0x180007628`
- `0x1800076dc`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000bf74`
- `0x18000c000`
- `0x18000c08c`
- `0x18000d8f0`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000a5e9`
- `KERNEL32!TryEnterCriticalSection` at `0x18000a5e9`
- `KERNEL32!SwitchToThread` at `0x18000a5e0`
- `KERNEL32!SwitchToThread` at `0x18000a5e0`
- `KERNEL32!EnterCriticalSection` at `0x18000a5f8`
- `KERNEL32!EnterCriticalSection` at `0x18000a5f8`
- `KERNEL32!LeaveCriticalSection` at `0x18000b025`
- `KERNEL32!LeaveCriticalSection` at `0x18000b025`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a79a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000acfd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000adff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000af13`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a79a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000acfd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000adff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000af13`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7fc`
- `OLEAUT32!__imp_VariantClear` at `0x18000ad5f`
- `OLEAUT32!__imp_VariantClear` at `0x18000ae62`
- `OLEAUT32!__imp_VariantClear` at `0x18000af71`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7fc`
- `OLEAUT32!__imp_VariantClear` at `0x18000ad5f`
- `OLEAUT32!__imp_VariantClear` at `0x18000ae62`
- `OLEAUT32!__imp_VariantClear` at `0x18000af71`

## string_xrefs

- `0x18000a581`: `Invalid data for DataStoreServer::SetConfiguration`
- `0x18000a75e`: `DataStoreServer::SetConfiguration() failed LoadXML() to Dnary Dom:%!hresult!`
- `0x18000a88b`: `Load() failed:%!hresult! for SetConfiguration`
- `0x18000a909`: `DataStoreServer::SetConfiguration() failed to load xml text to IAS Dom `
- `0x18000aed6`: `DataStoreServer::SetConfiguration() error: existing data doesn't have the:%S node`
- `0x18000ab8b`: `DataStoreServer::SetConfiguration(), failed to loadXML for a root replacement`
- `0x18000ac8a`: `DataStoreServer::SetConfiguration(), failed to loadXML for a root replacement`
- `0x18000afab`: `Error: DataStoreServer::SetConfiguration() tries to save no data to a non-existing file`
- `0x18000abf7`: `<Root xmlns:dt="urn:schemas-microsoft-com:datatypes"/>`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DataStoreServer::SetConfiguration(
        DataStoreServer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  DataStoreServer *v5; // r12
  __int64 v6; // rbx
  int v8; // edi
  __int64 v9; // rcx
  int XML; // edi
  struct IUnknown *v11; // rdi
  int v12; // eax
  struct IUnknown *v13; // rdi
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct IUnknown **v17; // rsi
  struct IUnknown *v18; // rdi
  BSTR v19; // rax
  int v20; // eax
  HRESULT v21; // eax
  const WCHAR *v22; // r13
  struct IUnknown **v23; // r12
  char v24; // al
  struct IUnknown *v25; // rcx
  struct IUnknown *v26; // rdi
  int v27; // eax
  struct IUnknown *v28; // rdi
  struct IUnknown **v29; // rax
  struct IUnknown *v30; // rcx
  struct IUnknown *v31; // r14
  int v32; // eax
  int v33; // eax
  struct IUnknown *v34; // rsi
  int v35; // eax
  struct IUnknown *v36; // r14
  struct IUnknown *v37; // rdi
  int v38; // eax
  struct IUnknown *v39; // rdi
  _bstr_t *v40; // r15
  __int64 v41; // rdx
  int v42; // eax
  __int16 v43; // di
  _bstr_t *v44; // r15
  __int64 v45; // rdx
  int v46; // eax
  __int16 v47; // di
  struct IUnknown *v48; // r15
  BSTR v49; // rax
  int v50; // eax
  HRESULT v51; // eax
  int v52; // eax
  struct IUnknown *v53; // r15
  struct IUnknown *v54; // r12
  BSTR v55; // rax
  int v56; // eax
  HRESULT v57; // eax
  int v58; // r8d
  int v59; // r9d
  struct IUnknown *v60; // rsi
  BSTR v61; // rax
  int v62; // eax
  HRESULT v63; // eax
  __int64 v64; // rcx
  __int64 v65; // [rsp+30h] [rbp-B8h] BYREF
  struct IUnknown *v66; // [rsp+38h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-A8h] BYREF
  struct IUnknown *v68; // [rsp+58h] [rbp-90h] BYREF
  struct IUnknown *v69; // [rsp+60h] [rbp-88h]
  VARIANTARG v70; // [rsp+70h] [rbp-78h] BYREF
  struct IUnknown *v71; // [rsp+90h] [rbp-58h]
  __int64 v72; // [rsp+98h] [rbp-50h]
  _bstr_t *v73; // [rsp+A0h] [rbp-48h]
  struct IUnknown *v76; // [rsp+108h] [rbp+20h] BYREF

  v5 = this;
  v6 = 0;
  v72 = 0;
  v69 = 0;
  v66 = 0;
  if ( !*((_BYTE *)this + 48) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer() is not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Invalid data for DataStoreServer::SetConfiguration");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147942487LL;
  }
  v8 = 0;
  while ( !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8)) )
  {
    if ( ++v8 >= 100 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
      break;
    }
    SwitchToThread();
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 272) + 16LL))(*((_QWORD *)v5 + 272));
  try
  {
    if ( a3 )
    {
      XML = DataStoreServer::LoadXML(v9, a3, &v66);
      if ( XML < 0 )
        goto LABEL_145;
      v11 = v66;
      if ( !v66 )
        _com_issue_error(-2147467261);
      v76 = 0;
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v66->lpVtbl[15].QueryInterface)(v66, &v76);
      if ( v12 < 0 )
        _com_issue_errorex(v12, v11, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v13 = v76;
      if ( !v76 )
        _com_issue_error(-2147467261);
      _bstr_t::_bstr_t((_bstr_t *)&v68, L".");
      v14 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v13);
      v15 = *v14;
      if ( *v14 )
      {
        v6 = *v14;
        v72 = *v14;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      }
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      if ( v13 )
        ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
    }
    if ( !IASFileExists((const WCHAR *)v5 + 808) )
    {
      v17 = (struct IUnknown **)((char *)v5 + 2160);
      if ( !*((_QWORD *)v5 + 270) )
      {
        XML = DataStoreServer::LoadXML(v16, *((_QWORD *)v5 + 276), (char *)v5 + 2160);
        if ( XML < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WppDbgPrint("DataStoreServer::SetConfiguration() failed LoadXML() to Dnary Dom:%!hresult!");
            WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
          }
          goto LABEL_145;
        }
      }
      v18 = *v17;
      if ( *v17 )
      {
        v19 = SysAllocString((const OLECHAR *)v5 + 808);
        if ( !v19 && v5 != (DataStoreServer *)-1616LL )
          _com_issue_error(-2147024882);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)v19;
        v70 = pvarg;
        v20 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v18->lpVtbl[22].QueryInterface)(v18, &v70);
        if ( v20 < 0 )
          _com_issue_errorex(v20, v18, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v21 = VariantClear(&pvarg);
        if ( v21 < 0 )
          _com_issue_error(v21);
      }
    }
    v22 = (const WCHAR *)((char *)v5 + 50);
    v23 = (struct IUnknown **)((char *)v5 + 2144);
    v24 = IASFileExists(v22);
    v25 = *v23;
    if ( v24 )
    {
      if ( v25 )
      {
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
        *v23 = 0;
      }
      XML = DataStoreServer::Load(v25, v22, v23);
      if ( XML < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Load() failed:%!hresult! for SetConfiguration");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
LABEL_144:
        v5 = this;
LABEL_145:
        v64 = *((_QWORD *)v5 + 268);
        if ( v64 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          *((_QWORD *)v5 + 268) = 0;
        }
        goto LABEL_186;
      }
    }
    else if ( !v25 )
    {
      XML = DataStoreServer::LoadXML(0, *((_QWORD *)this + 274), v23);
      if ( XML < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("DataStoreServer::SetConfiguration() failed to load xml text to IAS Dom ");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
        }
        goto LABEL_144;
      }
    }
    v26 = *v23;
    if ( *v23 )
    {
      v76 = 0;
      v27 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v26->lpVtbl[15].QueryInterface)(v26, &v76);
      if ( v27 < 0 )
        _com_issue_errorex(v27, v26, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v28 = v76;
      if ( !v76 )
        _com_issue_error(-2147467261);
      _bstr_t::_bstr_t((_bstr_t *)&v65, a2);
      v29 = (struct IUnknown **)MSXML2::IXMLDOMNode::selectNodes(v28);
      v30 = *v29;
      if ( *v29 )
      {
        v31 = *v29;
        v69 = *v29;
        ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->AddRef)(v30);
      }
      else
      {
        v31 = v69;
      }
      if ( v68 )
        ((void (__fastcall *)(struct IUnknown *))v68->lpVtbl->Release)(v68);
      if ( v28 )
        ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
      if ( !v31 )
        goto LABEL_130;
      LODWORD(v76) = 0;
      v32 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v31->lpVtbl[2].Release)(v31, &v76);
      if ( v32 < 0 )
        _com_issue_errorex(v32, v31, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
      if ( (_DWORD)v76 != 1 )
      {
LABEL_130:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("DataStoreServer::SetConfiguration() error: existing data doesn't have the:%S node");
          WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v58, v59, (__int64)a2);
        }
        XML = -2147024809;
        goto LABEL_144;
      }
      v76 = 0;
      v33 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v31->lpVtbl[3].QueryInterface)(v31, &v76);
      if ( v33 < 0 )
        _com_issue_errorex(v33, v31, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
      v34 = v76;
      v71 = v76;
      if ( !v76 )
        _com_issue_error(-2147467261);
      v76 = 0;
      v35 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v34->lpVtbl[3].Release)(v34, &v76);
      if ( v35 < 0 )
        _com_issue_errorex(v35, v34, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v36 = v76;
      v68 = v76;
      if ( v76 )
      {
        v76 = 0;
        v52 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown *, struct IUnknown **))v36->lpVtbl[6].AddRef)(
                v36,
                v6,
                v34,
                &v76);
        if ( v52 < 0 )
          _com_issue_errorex(v52, v36, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
        v53 = v76;
        if ( !v76 )
        {
          XML = -2147467259;
          if ( v36 )
            ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
          if ( v34 )
            ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
          goto LABEL_144;
        }
        v54 = *v23;
        if ( !v54 )
          _com_issue_error(-2147467261);
        v55 = SysAllocString(v22);
        if ( !v55 && v22 )
          _com_issue_error(-2147024882);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)v55;
        v70 = pvarg;
        v56 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v54->lpVtbl[22].QueryInterface)(v54, &v70);
        XML = v56;
        if ( v56 < 0 )
          _com_issue_errorex(v56, v54, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v57 = VariantClear(&pvarg);
        if ( v57 < 0 )
          _com_issue_error(v57);
        if ( v53 )
          ((void (__fastcall *)(struct IUnknown *))v53->lpVtbl->Release)(v53);
      }
      else
      {
        v37 = *v23;
        if ( !*v23 )
          _com_issue_error(-2147467261);
        v38 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v37->lpVtbl[21].QueryInterface)(*v23, 0);
        if ( v38 < 0 )
          _com_issue_errorex(v38, v37, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v39 = *v23;
        if ( a3 )
        {
          if ( !v39 )
            _com_issue_error(-2147467261);
          v40 = _bstr_t::_bstr_t((_bstr_t *)&v65, a3);
          v73 = v40;
          LOWORD(v76) = 0;
          if ( *(_QWORD *)v40 )
            v41 = **(_QWORD **)v40;
          else
            v41 = 0;
          v42 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v39->lpVtbl[21].Release)(
                  v39,
                  v41,
                  &v76);
          if ( v42 < 0 )
            _com_issue_errorex(v42, v39, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
          v43 = (__int16)v76;
          _bstr_t::~_bstr_t(v40);
          if ( v43 != -1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WppDbgPrint("DataStoreServer::SetConfiguration(), failed to loadXML for a root replacement");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids,
                "NPSDS");
            }
            XML = -2147467259;
            if ( v34 )
              ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
            goto LABEL_144;
          }
        }
        else
        {
          if ( !v39 )
            _com_issue_error(-2147467261);
          v44 = _bstr_t::_bstr_t((_bstr_t *)&v65, L"<Root xmlns:dt=\"urn:schemas-microsoft-com:datatypes\"/>");
          v73 = v44;
          LOWORD(v76) = 0;
          if ( *(_QWORD *)v44 )
            v45 = **(_QWORD **)v44;
          else
            v45 = 0;
          v46 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v39->lpVtbl[21].Release)(
                  v39,
                  v45,
                  &v76);
          if ( v46 < 0 )
            _com_issue_errorex(v46, v39, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
          v47 = (__int16)v76;
          _bstr_t::~_bstr_t(v44);
          if ( v47 != -1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WppDbgPrint("DataStoreServer::SetConfiguration(), failed to loadXML for a root replacement");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                39,
                &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids,
                "NPSDS");
            }
            XML = -2147467259;
            if ( v34 )
              ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
            goto LABEL_144;
          }
        }
        v48 = *v23;
        if ( !*v23 )
          _com_issue_error(-2147467261);
        v49 = SysAllocString(v22);
        if ( !v49 && v22 )
          _com_issue_error(-2147024882);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)v49;
        v70 = pvarg;
        v50 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v48->lpVtbl[22].QueryInterface)(v48, &v70);
        XML = v50;
        if ( v50 < 0 )
          _com_issue_errorex(v50, v48, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v51 = VariantClear(&pvarg);
        if ( v51 < 0 )
          _com_issue_error(v51);
      }
      if ( v36 )
        ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
      if ( v34 )
        ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
    }
    else
    {
      v60 = v66;
      if ( !v66 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Error: DataStoreServer::SetConfiguration() tries to save no data to a non-existing file");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
        }
        XML = -2147467259;
        goto LABEL_144;
      }
      v61 = SysAllocString(v22);
      if ( !v61 && v22 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v61;
      v70 = pvarg;
      v62 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v60->lpVtbl[22].QueryInterface)(v60, &v70);
      XML = v62;
      if ( v62 < 0 )
        _com_issue_errorex(v62, v60, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v63 = VariantClear(&pvarg);
      if ( v63 < 0 )
        _com_issue_error(v63);
    }
    v5 = this;
  }
  catch ( ... )
  {
    IASTraceExcept();
  }
LABEL_186:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 272) + 24LL))(*((_QWORD *)v5 + 272));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
  if ( v66 )
    ((void (__fastcall *)(struct IUnknown *))v66->lpVtbl->Release)(v66);
  if ( v69 )
    ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x18000a4a0  mov     rax, rsp
0x18000a4a3  mov     [rax+18h], r8
0x18000a4a7  mov     [rax+8], rcx
0x18000a4ab  push    rbx
0x18000a4ac  push    rsi
0x18000a4ad  push    rdi
0x18000a4ae  push    r12
0x18000a4b0  push    r13
0x18000a4b2  push    r14
0x18000a4b4  push    r15
0x18000a4b6  sub     rsp, 0B0h
0x18000a4bd  mov     rsi, r8
0x18000a4c0  mov     r15, rdx
0x18000a4c3  mov     r12, rcx
0x18000a4c6  xor     ebx, ebx
0x18000a4c8  mov     [rax-50h], rbx
0x18000a4cc  xor     r14d, r14d
0x18000a4cf  mov     [rsp+0E8h+var_88], r14
0x18000a4d4  xor     ecx, ecx
0x18000a4d6  mov     [rsp+0E8h+var_B0], rcx
0x18000a4db  cmp     [r12+30h], cl
0x18000a4e0  jnz     short loc_18000A55D
0x18000a4e2  lea     rax, WPP_GLOBAL_Control
0x18000a4e9  mov     rdx, cs:WPP_GLOBAL_Control
0x18000a4f0  cmp     rdx, rax
0x18000a4f3  jz      short loc_18000A533
0x18000a4f5  cmp     byte ptr [rdx+19h], 2
0x18000a4f9  jb      short loc_18000A533
0x18000a4fb  test    byte ptr [rdx+1Ch], 10h
0x18000a4ff  jz      short loc_18000A533
0x18000a501  lea     rcx, aDatastoreserve_6; "DataStoreServer() is not initialized"
0x18000a508  call    WppDbgPrint
0x18000a50d  lea     edx, [rbx+1Fh]
0x18000a510  lea     r9, aNpsds; "NPSDS"
0x18000a517  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a51e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a525  mov     rcx, [rcx+10h]
0x18000a529  call    WPP_SF_s
0x18000a52e  mov     rcx, [rsp+0E8h+var_B0]
0x18000a533  test    rcx, rcx
0x18000a536  jz      short loc_18000A545
0x18000a538  mov     rax, [rcx]
0x18000a53b  mov     rax, [rax+10h]
0x18000a53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a544  nop
0x18000a545  mov     eax, 80004005h
0x18000a54a  add     rsp, 0B0h
0x18000a551  pop     r15
0x18000a553  pop     r14
0x18000a555  pop     r13
0x18000a557  pop     r12
0x18000a559  pop     rdi
0x18000a55a  pop     rsi
0x18000a55b  pop     rbx
0x18000a55c  retn
0x18000a55d  test    r15, r15
0x18000a560  jnz     short loc_18000A5D0
0x18000a562  lea     rax, WPP_GLOBAL_Control
0x18000a569  mov     rdx, cs:WPP_GLOBAL_Control
0x18000a570  cmp     rdx, rax
0x18000a573  jz      short loc_18000A5B4
0x18000a575  cmp     byte ptr [rdx+19h], 2
0x18000a579  jb      short loc_18000A5B4
0x18000a57b  test    byte ptr [rdx+1Ch], 10h
0x18000a57f  jz      short loc_18000A5B4
0x18000a581  lea     rcx, aInvalidDataFor_0; "Invalid data for DataStoreServer::SetCo"...
0x18000a588  call    WppDbgPrint
0x18000a58d  lea     edx, [r15+20h]
0x18000a591  lea     r9, aNpsds; "NPSDS"
0x18000a598  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5a6  mov     rcx, [rcx+10h]
0x18000a5aa  call    WPP_SF_s
0x18000a5af  mov     rcx, [rsp+0E8h+var_B0]
0x18000a5b4  test    rcx, rcx
0x18000a5b7  jz      short loc_18000A5C6
0x18000a5b9  mov     rax, [rcx]
0x18000a5bc  mov     rax, [rax+10h]
0x18000a5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c5  nop
0x18000a5c6  mov     eax, 80070057h
0x18000a5cb  jmp     loc_18000A54A
0x18000a5d0  lea     r14, [r12+8]
0x18000a5d5  xor     edi, edi
0x18000a5d7  jmp     short loc_18000A5E6
0x18000a5d9  inc     edi
0x18000a5db  cmp     edi, 64h ; 'd'
0x18000a5de  jge     short loc_18000A5F5
0x18000a5e0  call    cs:__imp_SwitchToThread
0x18000a5e6  mov     rcx, r14; lpCriticalSection
0x18000a5e9  call    cs:__imp_TryEnterCriticalSection
0x18000a5ef  test    eax, eax
0x18000a5f1  jz      short loc_18000A5D9
0x18000a5f3  jmp     short loc_18000A5FE
0x18000a5f5  mov     rcx, r14; lpCriticalSection
0x18000a5f8  call    cs:__imp_EnterCriticalSection
0x18000a5fe  mov     rcx, [r12+880h]
0x18000a606  mov     rax, [rcx]
0x18000a609  mov     rax, [rax+10h]
0x18000a60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a612  nop
0x18000a613  test    rsi, rsi
0x18000a616  jz      loc_18000A6F5
0x18000a61c  lea     r8, [rsp+0E8h+var_B0]
0x18000a621  mov     rdx, rsi
0x18000a624  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a629  mov     edi, eax
0x18000a62b  test    eax, eax
0x18000a62d  js      loc_18000AFE7
0x18000a633  mov     rdi, [rsp+0E8h+var_B0]
0x18000a638  test    rdi, rdi
0x18000a63b  jz      loc_18000B076
0x18000a641  mov     [rsp+0E8h+arg_18], 0
0x18000a64d  mov     rax, [rdi]
0x18000a650  lea     rdx, [rsp+0E8h+arg_18]
0x18000a658  mov     rcx, rdi
0x18000a65b  mov     rax, [rax+168h]
0x18000a662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a667  test    eax, eax
0x18000a669  js      loc_18000B080
0x18000a66f  mov     rdi, [rsp+0E8h+arg_18]
0x18000a677  mov     [rsp+0E8h+arg_18], rdi
0x18000a67f  test    rdi, rdi
0x18000a682  jz      loc_18000B092
0x18000a688  lea     rdx, asc_180014B8C; "."
0x18000a68f  lea     rcx, [rsp+0E8h+var_90]; this
0x18000a694  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000a699  mov     r8, rax
0x18000a69c  lea     rdx, [rsp+0E8h+var_B8]
0x18000a6a1  mov     rcx, rdi; struct IUnknown *
0x18000a6a4  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18000a6a9  mov     rcx, [rax]
0x18000a6ac  test    rcx, rcx
0x18000a6af  jz      short loc_18000A6C9
0x18000a6b1  mov     rbx, rcx
0x18000a6b4  mov     [rsp+0E8h+var_50], rcx
0x18000a6bc  mov     rax, [rcx]
0x18000a6bf  mov     rax, [rax+8]
0x18000a6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c8  nop
0x18000a6c9  mov     rcx, [rsp+0E8h+var_B8]
0x18000a6ce  test    rcx, rcx
0x18000a6d1  jz      short loc_18000A6E0
0x18000a6d3  mov     rax, [rcx]
0x18000a6d6  mov     rax, [rax+10h]
0x18000a6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6df  nop
0x18000a6e0  test    rdi, rdi
0x18000a6e3  jz      short loc_18000A6F5
0x18000a6e5  mov     rax, [rdi]
0x18000a6e8  mov     rcx, rdi
0x18000a6eb  mov     rax, [rax+10h]
0x18000a6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f4  nop
0x18000a6f5  lea     r14, [r12+650h]
0x18000a6fd  mov     rcx, r14
0x18000a700  call    IASFileExists
0x18000a705  test    al, al
0x18000a707  jnz     loc_18000A80C
0x18000a70d  lea     rsi, [r12+870h]
0x18000a715  cmp     qword ptr [rsi], 0
0x18000a719  jnz     short loc_18000A78F
0x18000a71b  mov     r8, rsi
0x18000a71e  mov     rdx, [r12+8A0h]
0x18000a726  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a72b  mov     edi, eax
0x18000a72d  test    eax, eax
0x18000a72f  jns     short loc_18000A78F
0x18000a731  lea     rax, WPP_GLOBAL_Control
0x18000a738  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a73f  cmp     rcx, rax
0x18000a742  jz      loc_18000AFE7
0x18000a748  cmp     byte ptr [rcx+19h], 2
0x18000a74c  jb      loc_18000AFE7
0x18000a752  test    byte ptr [rcx+1Ch], 10h
0x18000a756  jz      loc_18000AFE7
0x18000a75c  mov     edx, edi
0x18000a75e  lea     rcx, aDatastoreserve_16; "DataStoreServer::SetConfiguration() fai"...
0x18000a765  call    WppDbgPrint
0x18000a76a  mov     edx, 21h ; '!'
0x18000a76f  mov     dword ptr [rsp+0E8h+var_C8], edi
0x18000a773  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a781  mov     rcx, [rcx+10h]
0x18000a785  call    WPP_SF_sd
0x18000a78a  jmp     loc_18000AFE7
0x18000a78f  mov     rdi, [rsi]
0x18000a792  test    rdi, rdi
0x18000a795  jz      short loc_18000A80C
0x18000a797  mov     rcx, r14; psz
0x18000a79a  call    cs:__imp_SysAllocString
0x18000a7a0  test    rax, rax
0x18000a7a3  jnz     short loc_18000A7AE
0x18000a7a5  test    r14, r14
0x18000a7a8  jnz     loc_18000B09D
0x18000a7ae  mov     r14d, 8
0x18000a7b4  mov     word ptr [rsp+0E8h+pvarg], r14w
0x18000a7ba  mov     qword ptr [rsp+0E8h+pvarg+8], rax
0x18000a7bf  movups  xmm0, xmmword ptr [rsp+0E8h+pvarg]
0x18000a7c4  movaps  [rsp+0E8h+var_78], xmm0
0x18000a7c9  movsd   xmm1, qword ptr [rsp+0E8h+pvarg+10h]
0x18000a7cf  movsd   [rsp+0E8h+var_68], xmm1
0x18000a7d8  mov     rax, [rdi]
0x18000a7db  lea     rdx, [rsp+0E8h+var_78]
0x18000a7e0  mov     rcx, rdi
0x18000a7e3  mov     rax, [rax+210h]
0x18000a7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7ef  test    eax, eax
0x18000a7f1  js      loc_18000B0A8
0x18000a7f7  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x18000a7fc  call    cs:__imp_VariantClear
0x18000a802  test    eax, eax
0x18000a804  js      loc_18000B0BA
0x18000a80a  jmp     short loc_18000A812
0x18000a80c  mov     r14d, 8
0x18000a812  lea     r13, [r12+32h]
0x18000a817  add     r12, 860h
0x18000a81e  mov     rcx, r13
0x18000a821  call    IASFileExists
0x18000a826  mov     rcx, [r12]
0x18000a82a  xor     esi, esi
0x18000a82c  test    al, al
0x18000a82e  jz      loc_18000A8BC
0x18000a834  test    rcx, rcx
0x18000a837  jz      short loc_18000A849
0x18000a839  mov     rax, [rcx]
0x18000a83c  mov     rax, [rax+10h]
0x18000a840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a845  mov     [r12], rsi
0x18000a849  mov     r8, r12
0x18000a84c  mov     rdx, r13
0x18000a84f  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a854  mov     edi, eax
0x18000a856  test    eax, eax
0x18000a858  jns     loc_18000A93D
0x18000a85e  lea     rax, WPP_GLOBAL_Control
0x18000a865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a86c  cmp     rcx, rax
0x18000a86f  jz      loc_18000AFDF
0x18000a875  cmp     byte ptr [rcx+19h], 2
0x18000a879  jb      loc_18000AFDF
0x18000a87f  test    byte ptr [rcx+1Ch], 10h
0x18000a883  jz      loc_18000AFDF
0x18000a889  mov     edx, edi
0x18000a88b  lea     rcx, aLoadFailedHres_2; "Load() failed:%!hresult! for SetConfigu"...
0x18000a892  call    WppDbgPrint
0x18000a897  mov     edx, 23h ; '#'
0x18000a89c  mov     dword ptr [rsp+0E8h+var_C8], edi
0x18000a8a0  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a8a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ae  mov     rcx, [rcx+10h]
0x18000a8b2  call    WPP_SF_sd
0x18000a8b7  jmp     loc_18000AFDF
0x18000a8bc  test    rcx, rcx
0x18000a8bf  jnz     short loc_18000A93D
0x18000a8c1  mov     r8, r12
0x18000a8c4  mov     rdx, [rsp+0E8h+arg_0]
0x18000a8cc  mov     rdx, [rdx+890h]
0x18000a8d3  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a8d8  mov     edi, eax
0x18000a8da  test    eax, eax
0x18000a8dc  jns     short loc_18000A93D
0x18000a8de  lea     rax, WPP_GLOBAL_Control
0x18000a8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ec  cmp     rcx, rax
0x18000a8ef  jz      loc_18000AFDF
0x18000a8f5  cmp     byte ptr [rcx+19h], 2
0x18000a8f9  jb      loc_18000AFDF
0x18000a8ff  test    byte ptr [rcx+1Ch], 10h
0x18000a903  jz      loc_18000AFDF
0x18000a909  lea     rcx, aDatastoreserve_4; "DataStoreServer::SetConfiguration() fai"...
0x18000a910  call    WppDbgPrint
0x18000a915  mov     edx, 24h ; '$'
0x18000a91a  lea     r9, aNpsds; "NPSDS"
0x18000a921  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a92f  mov     rcx, [rcx+10h]
0x18000a933  call    WPP_SF_s
0x18000a938  jmp     loc_18000AFDF
0x18000a93d  mov     rdi, [r12]
0x18000a941  test    rdi, rdi
0x18000a944  jz      loc_18000AF06
0x18000a94a  mov     [rsp+0E8h+arg_18], rsi
0x18000a952  mov     rax, [rdi]
0x18000a955  lea     rdx, [rsp+0E8h+arg_18]
0x18000a95d  mov     rcx, rdi
0x18000a960  mov     rax, [rax+168h]
0x18000a967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a96c  test    eax, eax
0x18000a96e  js      loc_18000B0C2
0x18000a974  mov     rdi, [rsp+0E8h+arg_18]
0x18000a97c  mov     [rsp+0E8h+arg_18], rdi
0x18000a984  test    rdi, rdi
0x18000a987  jz      loc_18000B0D4
0x18000a98d  mov     rdx, r15; unsigned __int16 *
0x18000a990  lea     rcx, [rsp+0E8h+var_B8]; this
0x18000a995  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000a99a  mov     r8, rax
0x18000a99d  lea     rdx, [rsp+0E8h+var_90]
0x18000a9a2  mov     rcx, rdi; struct IUnknown *
  ... truncated ...
```
