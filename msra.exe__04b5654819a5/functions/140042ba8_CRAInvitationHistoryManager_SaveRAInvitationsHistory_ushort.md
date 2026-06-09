# CRAInvitationHistoryManager::SaveRAInvitationsHistory(ushort *)

- ea: `0x140042ba8`
- end: `0x140043b5d`
- name: `?SaveRAInvitationsHistory@CRAInvitationHistoryManager@@QEAAJPEAG@Z`
- size: `4021`
- prototype: `__int64 __fastcall(CRAInvitationHistoryManager *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002b3c8`
- `0x14002f0d0`

## callees

- `0x140002463`
- `0x1400044f8`
- `0x1400080fc`
- `0x14000a0e4`
- `0x140034ce4`
- `0x1400350b0`
- `0x140042ba8`
- `0x140043b64`
- `0x140043bcc`
- `0x140043c34`
- `0x140043c9c`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140042c8a`
- `ole32!CoCreateInstance` at `0x140042c8a`
- `OLEAUT32!__imp_SysAllocString` at `0x140043036`
- `OLEAUT32!__imp_SysAllocString` at `0x140043165`
- `OLEAUT32!__imp_SysAllocString` at `0x1400439e6`
- `OLEAUT32!__imp_SysAllocString` at `0x140043036`
- `OLEAUT32!__imp_SysAllocString` at `0x140043165`
- `OLEAUT32!__imp_SysAllocString` at `0x1400439e6`
- `OLEAUT32!__imp_SysFreeString` at `0x140042fca`
- `OLEAUT32!__imp_SysFreeString` at `0x140043026`
- `OLEAUT32!__imp_SysFreeString` at `0x140043075`
- `OLEAUT32!__imp_SysFreeString` at `0x1400430d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14004312d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400431a3`
- `OLEAUT32!__imp_SysFreeString` at `0x140043aac`
- `OLEAUT32!__imp_SysFreeString` at `0x140043abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140043acd`
- `OLEAUT32!__imp_SysFreeString` at `0x140043add`
- `OLEAUT32!__imp_SysFreeString` at `0x140042fca`
- `OLEAUT32!__imp_SysFreeString` at `0x140043026`
- `OLEAUT32!__imp_SysFreeString` at `0x140043075`
- `OLEAUT32!__imp_SysFreeString` at `0x1400430d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14004312d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400431a3`
- `OLEAUT32!__imp_SysFreeString` at `0x140043aac`
- `OLEAUT32!__imp_SysFreeString` at `0x140043abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140043acd`
- `OLEAUT32!__imp_SysFreeString` at `0x140043add`
- `OLEAUT32!__imp_VariantClear` at `0x140042ced`
- `OLEAUT32!__imp_VariantClear` at `0x140042d4d`
- `OLEAUT32!__imp_VariantClear` at `0x140042dad`
- `OLEAUT32!__imp_VariantClear` at `0x140042f4c`
- `OLEAUT32!__imp_VariantClear` at `0x1400439ca`
- `OLEAUT32!__imp_VariantClear` at `0x140043a38`
- `OLEAUT32!__imp_VariantClear` at `0x140042ced`
- `OLEAUT32!__imp_VariantClear` at `0x140042d4d`
- `OLEAUT32!__imp_VariantClear` at `0x140042dad`
- `OLEAUT32!__imp_VariantClear` at `0x140042f4c`
- `OLEAUT32!__imp_VariantClear` at `0x1400439ca`
- `OLEAUT32!__imp_VariantClear` at `0x140043a38`

## string_xrefs

- `0x140042dcc`: `<?xml version="1.0" ?><RAINVITATIONCOLL></RAINVITATIONCOLL>`
- `0x140042ffe`: `COMPUTERNAME`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CRAInvitationHistoryManager::SaveRAInvitationsHistory(
        CRAInvitationHistoryManager *this,
        unsigned __int16 *a2)
{
  OLECHAR *v3; // rbx
  OLECHAR *v4; // rdi
  OLECHAR *v5; // r15
  HRESULT Instance; // eax
  CEventLogger *v7; // rcx
  signed int v8; // esi
  unsigned int v9; // r9d
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  CEventLogger *v11; // rcx
  struct IXMLDOMDocumentVtbl *v12; // rax
  CEventLogger *v13; // rcx
  struct IXMLDOMDocumentVtbl *v14; // rax
  CEventLogger *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  signed int v18; // eax
  CEventLogger *v19; // rcx
  signed int v20; // eax
  CEventLogger *v21; // rcx
  signed int v22; // eax
  CEventLogger *v23; // rcx
  char *v24; // rcx
  char *v25; // rax
  int v26; // r12d
  __int64 v27; // r14
  struct IXMLDOMDocumentVtbl *v28; // rax
  CEventLogger *v29; // rcx
  signed int v30; // eax
  CEventLogger *v31; // rcx
  signed int Name; // eax
  CEventLogger *v33; // rcx
  signed int v34; // eax
  CEventLogger *v35; // rcx
  signed int ComputerName; // eax
  CEventLogger *v37; // rcx
  signed int v38; // eax
  CEventLogger *v39; // rcx
  signed int v40; // eax
  CEventLogger *v41; // rcx
  signed int PublicKey; // eax
  CEventLogger *v43; // rcx
  signed int v44; // eax
  CEventLogger *v45; // rcx
  signed int Address; // eax
  CEventLogger *v47; // rcx
  signed int v48; // eax
  CEventLogger *v49; // rcx
  const OLECHAR *v50; // rcx
  unsigned __int16 *v51; // rax
  CEventLogger *v52; // rcx
  signed int v53; // eax
  CEventLogger *v54; // rcx
  __int128 v55; // xmm1
  unsigned __int64 v56; // rcx
  signed int v57; // eax
  CEventLogger *v58; // rcx
  signed int v59; // eax
  CEventLogger *v60; // rcx
  struct IXMLDOMDocument *v61; // rsi
  struct IXMLDOMDocumentVtbl *v62; // r14
  OLECHAR *v63; // r12
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v66; // [rsp+28h] [rbp-D8h]
  __int64 v67; // [rsp+30h] [rbp-D0h]
  __int64 v68; // [rsp+38h] [rbp-C8h]
  __int64 v69; // [rsp+40h] [rbp-C0h]
  __int64 v70; // [rsp+48h] [rbp-B8h]
  struct IXMLDOMNamedNodeMap *v71; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v74; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMDocument *v75; // [rsp+70h] [rbp-90h] BYREF
  __int16 v76; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  __int64 v78; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v79; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR *v80; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR *v81; // [rsp+C8h] [rbp-38h] BYREF
  BSTR v82; // [rsp+D0h] [rbp-30h] BYREF
  char *v83; // [rsp+D8h] [rbp-28h]
  OLECHAR *psz; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v85[264]; // [rsp+F0h] [rbp-10h] BYREF

  psz = a2;
  v75 = 0;
  v78 = 0;
  v76 = -1;
  memset_0(v85, 0, 0x208u);
  v3 = 0;
  v81 = 0;
  v82 = 0;
  v4 = 0;
  v80 = 0;
  v5 = 0;
  bstrString = 0;
  Instance = ATL::CComBSTR::Append((ATL::CComBSTR *)&v82, L"RAINVITATIONITEM");
  v8 = Instance;
  if ( Instance < 0 )
  {
    v9 = 436;
LABEL_3:
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      v9,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      Instance);
    goto LABEL_175;
  }
  if ( !*(_DWORD *)this )
    goto LABEL_175;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&v75);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v9 = 447;
    goto LABEL_3;
  }
  lpVtbl = v75->lpVtbl;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v79 = pvarg;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))lpVtbl[1].GetTypeInfo)(
         v75,
         L"ProhibitDTD",
         &v79);
  VariantClear(&pvarg);
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      v11,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1C1u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v8);
    goto LABEL_175;
  }
  v12 = v75->lpVtbl;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v79 = pvarg;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))v12[1].GetTypeInfo)(
         v75,
         L"AllowXsltScript",
         &v79);
  VariantClear(&pvarg);
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1C2u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v8);
    goto LABEL_175;
  }
  v14 = v75->lpVtbl;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v79 = pvarg;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, VARIANTARG *))v14[1].GetTypeInfo)(
         v75,
         L"AllowDocumentFunction",
         &v79);
  VariantClear(&pvarg);
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      v15,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1C3u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v8);
    goto LABEL_175;
  }
  v16 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v80, L"<?xml version=\"1.0\" ?><RAINVITATIONCOLL></RAINVITATIONCOLL>");
  v8 = v16;
  if ( v16 < 0 )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1C6u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v16);
    v4 = v80;
    goto LABEL_175;
  }
  v4 = v80;
  v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int16 *))v75->lpVtbl->loadXML)(v75, v80, &v76);
  if ( v18 < 0 || !v76 )
  {
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1CAu,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v18);
    v8 = -2147467259;
    goto LABEL_173;
  }
  v20 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v81, L"RAINVITATIONCOLL");
  v8 = v20;
  if ( v20 < 0 )
  {
    CEventLogger::LogError(
      v21,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1D2u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v20);
    v3 = v81;
    goto LABEL_175;
  }
  v3 = v81;
  v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))v75->lpVtbl->selectSingleNode)(
          v75,
          v81,
          &v78);
  if ( v22 < 0 || !v78 )
  {
    CEventLogger::LogError(
      v23,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x1D6u,
      L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
      v22);
    v8 = -2147467259;
    goto LABEL_175;
  }
  v24 = (char *)this + 488;
  v25 = (char *)*((_QWORD *)this + 61);
  v26 = 0;
  if ( *(int *)this <= 0 )
  {
LABEL_168:
    v61 = v75;
    v62 = v75->lpVtbl;
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    v63 = psz;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( !pvarg.llVal && v63 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v79 = pvarg;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *))v62->save)(v61, &v79);
    VariantClear(&pvarg);
    goto LABEL_173;
  }
  while ( 1 )
  {
    v72 = 0;
    v74 = 0;
    v71 = 0;
    if ( v25 == v24 )
      goto LABEL_168;
    v27 = *((_QWORD *)v25 + 2);
    v83 = *(char **)v25;
    v28 = v75->lpVtbl;
    pvarg.vt = 3;
    pvarg.lVal = 1;
    v79 = pvarg;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, BSTR, _QWORD, __int64 *))v28->createNode)(
           v75,
           &v79,
           v82,
           0,
           &v72);
    VariantClear(&pvarg);
    if ( v8 < 0 )
      break;
    v30 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v72 + 136LL))(v72, &v71);
    v8 = v30;
    if ( v30 < 0 )
    {
      CEventLogger::LogError(
        v31,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x1FDu,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v30);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    Name = CRAInvitationHistoryItem::get_Name((CRAInvitationHistoryItem *)v27, &bstrString);
    v8 = Name;
    if ( Name < 0 )
    {
      CEventLogger::LogError(
        v33,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x202u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        Name);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_153;
    }
    v5 = bstrString;
    v34 = AddAttributeToAttributeList(v75, v71, L"NAME", bstrString);
    v8 = v34;
    if ( v34 < 0 )
    {
      CEventLogger::LogError(
        v35,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x207u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v34);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v5 )
    {
      SysFreeString(v5);
      bstrString = 0;
    }
    ComputerName = CRAInvitationHistoryItem::get_ComputerName((CRAInvitationHistoryItem *)v27, &bstrString);
    v8 = ComputerName;
    if ( ComputerName < 0 )
    {
      CEventLogger::LogError(
        v37,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x20Eu,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        ComputerName);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_153;
    }
    v5 = bstrString;
    v38 = AddAttributeToAttributeList(v75, v71, L"COMPUTERNAME", bstrString);
    v8 = v38;
    if ( v38 < 0 )
    {
      CEventLogger::LogError(
        v39,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x213u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v38);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v5 )
      SysFreeString(v5);
    v5 = SysAllocString(*(const OLECHAR **)(v27 + 16));
    bstrString = v5;
    v40 = AddAttributeToAttributeList(v75, v71, L"AVATAR", v5);
    v8 = v40;
    if ( v40 < 0 )
    {
      CEventLogger::LogError(
        v41,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x21Fu,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v40);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v5 )
    {
      SysFreeString(v5);
      bstrString = 0;
    }
    PublicKey = CRAInvitationHistoryItem::get_PublicKey((CRAInvitationHistoryItem *)v27, &bstrString);
    v8 = PublicKey;
    if ( PublicKey < 0 )
    {
      CEventLogger::LogError(
        v43,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x226u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        PublicKey);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_153;
    }
    v5 = bstrString;
    v44 = AddAttributeToAttributeList(v75, v71, L"PUBLICKEY", bstrString);
    v8 = v44;
    if ( v44 < 0 )
    {
      CEventLogger::LogError(
        v45,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x22Bu,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v44);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v5 )
    {
      SysFreeString(v5);
      bstrString = 0;
    }
    Address = CRAInvitationHistoryItem::get_Address((CRAInvitationHistoryItem *)v27, &bstrString);
    v8 = Address;
    if ( Address < 0 )
    {
      CEventLogger::LogError(
        v47,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x233u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        Address);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
LABEL_153:
      v5 = bstrString;
      goto LABEL_173;
    }
    v5 = bstrString;
    v48 = AddAttributeToAttributeList(v75, v71, L"ADDRESS", bstrString);
    v8 = v48;
    if ( v48 < 0 )
    {
      CEventLogger::LogError(
        v49,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x238u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v48);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v5 )
      SysFreeString(v5);
    if ( *(_DWORD *)(v27 + 56) != 1 )
    {
      if ( *(_DWORD *)(v27 + 56) == 2 )
      {
        v50 = L"2";
        goto LABEL_51;
      }
      if ( *(_DWORD *)(v27 + 56) == 3 )
      {
        v50 = L"3";
        goto LABEL_51;
      }
    }
    v50 = L"1";
LABEL_51:
    v51 = SysAllocString(v50);
    v5 = v51;
    if ( !v51 )
    {
      v8 = -2147024882;
      CEventLogger::LogError(
        v52,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x250u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        0x8007000E);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    v53 = AddAttributeToAttributeList(v75, v71, L"TYPE", v51);
    v8 = v53;
    if ( v53 < 0 )
    {
      CEventLogger::LogError(
        v54,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x255u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v53);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    SysFreeString(v5);
    v5 = 0;
    bstrString = 0;
    v55 = *(_OWORD *)(v27 + 40);
    v56 = *(_QWORD *)(v27 + 48);
    LODWORD(v70) = 1000 * HIWORD(v56);
    LODWORD(v69) = WORD2(v56);
    LODWORD(v68) = WORD1(v56);
    LODWORD(v67) = (unsigned __int16)v56;
    LODWORD(v66) = WORD3(v55);
    LODWORD(ppv) = WORD1(v55);
    StringCchPrintfW(v85, 0x104u, L"%04d%02d%02d%02d%02d%02d.%06d", (unsigned __int16)v55, ppv, v66, v67, v68, v69, v70);
    v57 = AddAttributeToAttributeList(v75, v71, L"TIME", v85);
    v8 = v57;
    if ( v57 < 0 )
    {
      CEventLogger::LogError(
        v58,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x26Fu,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v57);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    v59 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v78 + 168LL))(v78, v72, &v74);
    v8 = v59;
    if ( v59 < 0 )
    {
      CEventLogger::LogError(
        v60,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x271u,
        L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
        v59);
      if ( v71 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
      goto LABEL_173;
    }
    if ( v71 )
      ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    if ( v72 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    if ( ++v26 >= *(_DWORD *)this )
      goto LABEL_168;
    v25 = v83;
    v24 = (char *)this + 488;
  }
  CEventLogger::LogError(
    v29,
    &Recoverable_Error,
    (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
    0x1F8u,
    L"CRAInvitationHistoryManager::SaveRAInvitationsHistory",
    v8);
  if ( v71 )
    ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v71->lpVtbl->Release)(v71);
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
LABEL_173:
  if ( v5 )
    SysFreeString(v5);
LABEL_175:
  SysFreeString(v4);
  SysFreeString(v82);
  SysFreeString(v3);
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  if ( v75 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v75->lpVtbl->Release)(v75);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140042ba8  mov     [rsp-8+arg_10], rbx
0x140042bad  push    rbp
0x140042bae  push    rsi
0x140042baf  push    rdi
0x140042bb0  push    r12
0x140042bb2  push    r13
0x140042bb4  push    r14
0x140042bb6  push    r15
0x140042bb8  lea     rbp, [rsp-210h]
0x140042bc0  sub     rsp, 310h
0x140042bc7  mov     rax, cs:__security_cookie
0x140042bce  xor     rax, rsp
0x140042bd1  mov     [rbp+240h+var_40], rax
0x140042bd8  mov     [rbp+240h+psz], rdx
0x140042bdc  mov     r13, rcx
0x140042bdf  xor     r14d, r14d
0x140042be2  mov     [rsp+340h+var_2D0], r14
0x140042be7  mov     [rbp+240h+var_2A8], r14
0x140042beb  or      eax, 0FFFFFFFFh
0x140042bee  mov     [rsp+340h+var_2C8], ax
0x140042bf3  xor     edx, edx; Val
0x140042bf5  mov     r8d, 208h; Size
0x140042bfb  lea     rcx, [rbp+240h+var_250]; void *
0x140042bff  call    memset_0
0x140042c04  mov     ebx, r14d
0x140042c07  mov     [rbp+240h+var_278], rbx
0x140042c0b  mov     [rbp+240h+var_270], r14
0x140042c0f  mov     edi, r14d
0x140042c12  mov     [rbp+240h+var_280], r14
0x140042c16  mov     r15d, r14d
0x140042c19  mov     [rsp+340h+bstrString], r14
0x140042c1e  lea     rdx, aRainvitationit; "RAINVITATIONITEM"
0x140042c25  lea     rcx, [rbp+240h+var_270]; this
0x140042c29  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140042c2e  mov     esi, eax
0x140042c30  test    eax, eax
0x140042c32  jns     short loc_140042C62
0x140042c34  mov     r9d, 1B4h; unsigned int
0x140042c3a  mov     dword ptr [rsp+340h+var_318], eax; unsigned int
0x140042c3e  lea     rax, aCrainvitationh_1; "CRAInvitationHistoryManager::SaveRAInvi"...
0x140042c45  mov     [rsp+340h+ppv], rax; unsigned __int16 *
0x140042c4a  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140042c51  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140042c58  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140042c5d  jmp     loc_140043AB9
0x140042c62  cmp     [r13+0], r14d
0x140042c66  jz      loc_140043AB9
0x140042c6c  lea     rax, [rsp+340h+var_2D0]
0x140042c71  mov     [rsp+340h+ppv], rax; ppv
0x140042c76  lea     r9, IID_IXMLDOMDocument; riid
0x140042c7d  xor     edx, edx; pUnkOuter
0x140042c7f  lea     r8d, [rdx+1]; dwClsContext
0x140042c83  lea     rcx, CLSID_DOMDocument60; rclsid
0x140042c8a  call    cs:__imp_CoCreateInstance
0x140042c91  nop     dword ptr [rax+rax+00h]
0x140042c96  mov     esi, eax
0x140042c98  test    eax, eax
0x140042c9a  jns     short loc_140042CA4
0x140042c9c  mov     r9d, 1BFh
0x140042ca2  jmp     short loc_140042C3A
0x140042ca4  mov     rcx, [rsp+340h+var_2D0]
0x140042ca9  mov     rax, [rcx]
0x140042cac  mov     r12d, 0Bh
0x140042cb2  mov     word ptr [rbp+240h+pvarg], r12w
0x140042cb7  or      edx, 0FFFFFFFFh
0x140042cba  mov     word ptr [rbp+240h+pvarg+8], dx
0x140042cbe  movups  xmm0, xmmword ptr [rbp+240h+pvarg]
0x140042cc2  movaps  [rbp+240h+var_2A0], xmm0
0x140042cc6  movsd   xmm1, qword ptr [rbp+240h+pvarg+10h]
0x140042ccb  movsd   [rbp+240h+var_290], xmm1
0x140042cd0  lea     r8, [rbp+240h+var_2A0]
0x140042cd4  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x140042cdb  mov     rax, [rax+280h]
0x140042ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042ce7  mov     esi, eax
0x140042ce9  lea     rcx, [rbp+240h+pvarg]; pvarg
0x140042ced  call    cs:__imp_VariantClear
0x140042cf4  nop     dword ptr [rax+rax+00h]
0x140042cf9  test    esi, esi
0x140042cfb  jns     short loc_140042D0C
0x140042cfd  mov     dword ptr [rsp+340h+var_318], esi
0x140042d01  mov     r9d, 1C1h
0x140042d07  jmp     loc_140042C3E
0x140042d0c  mov     rcx, [rsp+340h+var_2D0]
0x140042d11  mov     rax, [rcx]
0x140042d14  mov     word ptr [rbp+240h+pvarg], r12w
0x140042d19  mov     word ptr [rbp+240h+pvarg+8], r14w
0x140042d1e  movups  xmm0, xmmword ptr [rbp+240h+pvarg]
0x140042d22  movaps  [rbp+240h+var_2A0], xmm0
0x140042d26  movsd   xmm1, qword ptr [rbp+240h+pvarg+10h]
0x140042d2b  movsd   [rbp+240h+var_290], xmm1
0x140042d30  lea     r8, [rbp+240h+var_2A0]
0x140042d34  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x140042d3b  mov     rax, [rax+280h]
0x140042d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042d47  mov     esi, eax
0x140042d49  lea     rcx, [rbp+240h+pvarg]; pvarg
0x140042d4d  call    cs:__imp_VariantClear
0x140042d54  nop     dword ptr [rax+rax+00h]
0x140042d59  test    esi, esi
0x140042d5b  jns     short loc_140042D6C
0x140042d5d  mov     dword ptr [rsp+340h+var_318], esi
0x140042d61  mov     r9d, 1C2h
0x140042d67  jmp     loc_140042C3E
0x140042d6c  mov     rcx, [rsp+340h+var_2D0]
0x140042d71  mov     rax, [rcx]
0x140042d74  mov     word ptr [rbp+240h+pvarg], r12w
0x140042d79  mov     word ptr [rbp+240h+pvarg+8], r14w
0x140042d7e  movups  xmm0, xmmword ptr [rbp+240h+pvarg]
0x140042d82  movaps  [rbp+240h+var_2A0], xmm0
0x140042d86  movsd   xmm1, qword ptr [rbp+240h+pvarg+10h]
0x140042d8b  movsd   [rbp+240h+var_290], xmm1
0x140042d90  lea     r8, [rbp+240h+var_2A0]
0x140042d94  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140042d9b  mov     rax, [rax+280h]
0x140042da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042da7  mov     esi, eax
0x140042da9  lea     rcx, [rbp+240h+pvarg]; pvarg
0x140042dad  call    cs:__imp_VariantClear
0x140042db4  nop     dword ptr [rax+rax+00h]
0x140042db9  test    esi, esi
0x140042dbb  jns     short loc_140042DCC
0x140042dbd  mov     dword ptr [rsp+340h+var_318], esi
0x140042dc1  mov     r9d, 1C3h
0x140042dc7  jmp     loc_140042C3E
0x140042dcc  lea     rdx, aXmlVersion10Ra; "<?xml version=\"1.0\" ?><RAINVITATIONCO"...
0x140042dd3  lea     rcx, [rbp+240h+var_280]; this
0x140042dd7  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140042ddc  mov     esi, eax
0x140042dde  test    eax, eax
0x140042de0  jns     short loc_140042E14
0x140042de2  mov     dword ptr [rsp+340h+var_318], eax; unsigned int
0x140042de6  lea     rax, aCrainvitationh_1; "CRAInvitationHistoryManager::SaveRAInvi"...
0x140042ded  mov     [rsp+340h+ppv], rax; unsigned __int16 *
0x140042df2  mov     r9d, 1C6h; unsigned int
0x140042df8  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140042dff  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140042e06  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140042e0b  mov     rdi, [rbp+240h+var_280]
0x140042e0f  jmp     loc_140043AB9
0x140042e14  mov     rcx, [rsp+340h+var_2D0]
0x140042e19  mov     rax, [rcx]
0x140042e1c  lea     r8, [rsp+340h+var_2C8]
0x140042e21  mov     rdi, [rbp+240h+var_280]
0x140042e25  mov     rdx, rdi
0x140042e28  mov     rax, [rax+208h]
0x140042e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042e34  test    eax, eax
0x140042e36  js      loc_140043A76
0x140042e3c  cmp     [rsp+340h+var_2C8], r14w
0x140042e42  jz      loc_140043A76
0x140042e48  lea     rdx, aRainvitationco; "RAINVITATIONCOLL"
0x140042e4f  lea     rcx, [rbp+240h+var_278]; this
0x140042e53  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140042e58  mov     esi, eax
0x140042e5a  test    eax, eax
0x140042e5c  jns     short loc_140042E90
0x140042e5e  mov     dword ptr [rsp+340h+var_318], eax; unsigned int
0x140042e62  lea     rax, aCrainvitationh_1; "CRAInvitationHistoryManager::SaveRAInvi"...
0x140042e69  mov     [rsp+340h+ppv], rax; unsigned __int16 *
0x140042e6e  mov     r9d, 1D2h; unsigned int
0x140042e74  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140042e7b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140042e82  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140042e87  mov     rbx, [rbp+240h+var_278]
0x140042e8b  jmp     loc_140043AB9
0x140042e90  mov     rcx, [rsp+340h+var_2D0]
0x140042e95  mov     rax, [rcx]
0x140042e98  lea     r8, [rbp+240h+var_2A8]
0x140042e9c  mov     rbx, [rbp+240h+var_278]
0x140042ea0  mov     rdx, rbx
0x140042ea3  mov     rax, [rax+128h]
0x140042eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042eaf  test    eax, eax
0x140042eb1  js      loc_140043A46
0x140042eb7  cmp     [rbp+240h+var_2A8], r14
0x140042ebb  jz      loc_140043A46
0x140042ec1  lea     rcx, [r13+1E8h]
0x140042ec8  mov     rax, [rcx]
0x140042ecb  mov     r12d, r14d
0x140042ece  cmp     [r13+0], r14d
0x140042ed2  jle     loc_1400439B8
0x140042ed8  mov     [rsp+340h+var_2E8], r14
0x140042edd  mov     [rsp+340h+var_2D8], r14
0x140042ee2  mov     [rsp+340h+var_2F0], r14
0x140042ee7  cmp     rax, rcx
0x140042eea  jz      loc_1400439B8
0x140042ef0  mov     r14, [rax+10h]
0x140042ef4  mov     rax, [rax]
0x140042ef7  mov     [rbp+240h+var_268], rax
0x140042efb  mov     rcx, [rsp+340h+var_2D0]
0x140042f00  mov     rax, [rcx]
0x140042f03  mov     edx, 3
0x140042f08  mov     word ptr [rbp+240h+pvarg], dx
0x140042f0c  mov     dword ptr [rbp+240h+pvarg+8], 1
0x140042f13  movups  xmm0, xmmword ptr [rbp+240h+pvarg]
0x140042f17  movaps  [rbp+240h+var_2A0], xmm0
0x140042f1b  movsd   xmm1, qword ptr [rbp+240h+pvarg+10h]
0x140042f20  movsd   [rbp+240h+var_290], xmm1
0x140042f25  lea     rdx, [rsp+340h+var_2E8]
0x140042f2a  mov     [rsp+340h+ppv], rdx
0x140042f2f  xor     r9d, r9d
0x140042f32  mov     r8, [rbp+240h+var_270]
0x140042f36  lea     rdx, [rbp+240h+var_2A0]
0x140042f3a  mov     rax, [rax+1C0h]
0x140042f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042f46  mov     esi, eax
0x140042f48  lea     rcx, [rbp+240h+pvarg]; pvarg
0x140042f4c  call    cs:__imp_VariantClear
0x140042f53  nop     dword ptr [rax+rax+00h]
0x140042f58  test    esi, esi
0x140042f5a  js      loc_140043944
0x140042f60  mov     rcx, [rsp+340h+var_2E8]
0x140042f65  mov     rax, [rcx]
0x140042f68  lea     rdx, [rsp+340h+var_2F0]
0x140042f6d  mov     rax, [rax+88h]
0x140042f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042f79  mov     esi, eax
0x140042f7b  test    eax, eax
0x140042f7d  js      loc_1400438D0
0x140042f83  lea     rdx, [rsp+340h+bstrString]; unsigned __int16 **
0x140042f88  mov     rcx, r14; this
0x140042f8b  call    ?get_Name@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Name(ushort * *)
0x140042f90  mov     esi, eax
0x140042f92  test    eax, eax
0x140042f94  js      loc_140043857
0x140042f9a  mov     r15, [rsp+340h+bstrString]
0x140042f9f  mov     r9, r15; unsigned __int16 *
0x140042fa2  lea     r8, aName; "NAME"
0x140042fa9  mov     rdx, [rsp+340h+var_2F0]; struct IXMLDOMNamedNodeMap *
0x140042fae  mov     rcx, [rsp+340h+var_2D0]; struct IXMLDOMDocument *
0x140042fb3  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140042fb8  mov     esi, eax
0x140042fba  test    eax, eax
0x140042fbc  js      loc_1400437E3
0x140042fc2  test    r15, r15
0x140042fc5  jz      short loc_140042FDF
0x140042fc7  mov     rcx, r15; bstrString
0x140042fca  call    cs:__imp_SysFreeString
0x140042fd1  nop     dword ptr [rax+rax+00h]
0x140042fd6  mov     [rsp+340h+bstrString], 0
0x140042fdf  lea     rdx, [rsp+340h+bstrString]; unsigned __int16 **
0x140042fe4  mov     rcx, r14; this
0x140042fe7  call    ?get_ComputerName@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_ComputerName(ushort * *)
0x140042fec  mov     esi, eax
0x140042fee  test    eax, eax
0x140042ff0  js      loc_14004376F
0x140042ff6  mov     r15, [rsp+340h+bstrString]
0x140042ffb  mov     r9, r15; unsigned __int16 *
0x140042ffe  lea     r8, aComputername; "COMPUTERNAME"
0x140043005  mov     rdx, [rsp+340h+var_2F0]; struct IXMLDOMNamedNodeMap *
0x14004300a  mov     rcx, [rsp+340h+var_2D0]; struct IXMLDOMDocument *
0x14004300f  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140043014  mov     esi, eax
0x140043016  test    eax, eax
0x140043018  js      loc_1400436FB
0x14004301e  test    r15, r15
0x140043021  jz      short loc_140043032
0x140043023  mov     rcx, r15; bstrString
0x140043026  call    cs:__imp_SysFreeString
0x14004302d  nop     dword ptr [rax+rax+00h]
0x140043032  mov     rcx, [r14+10h]; psz
0x140043036  call    cs:__imp_SysAllocString
0x14004303d  nop     dword ptr [rax+rax+00h]
0x140043042  mov     r15, rax
0x140043045  mov     [rsp+340h+bstrString], rax
0x14004304a  mov     r9, rax; unsigned __int16 *
0x14004304d  lea     r8, aAvatar; "AVATAR"
0x140043054  mov     rdx, [rsp+340h+var_2F0]; struct IXMLDOMNamedNodeMap *
0x140043059  mov     rcx, [rsp+340h+var_2D0]; struct IXMLDOMDocument *
0x14004305e  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x140043063  mov     esi, eax
0x140043065  test    eax, eax
0x140043067  js      loc_140043687
0x14004306d  test    r15, r15
0x140043070  jz      short loc_14004308A
0x140043072  mov     rcx, r15; bstrString
0x140043075  call    cs:__imp_SysFreeString
0x14004307c  nop     dword ptr [rax+rax+00h]
0x140043081  mov     [rsp+340h+bstrString], 0
0x14004308a  lea     rdx, [rsp+340h+bstrString]; unsigned __int16 **
0x14004308f  mov     rcx, r14; this
0x140043092  call    ?get_PublicKey@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_PublicKey(ushort * *)
0x140043097  mov     esi, eax
0x140043099  test    eax, eax
0x14004309b  js      loc_140043613
0x1400430a1  mov     r15, [rsp+340h+bstrString]
0x1400430a6  mov     r9, r15; unsigned __int16 *
0x1400430a9  lea     r8, aPublickey; "PUBLICKEY"
0x1400430b0  mov     rdx, [rsp+340h+var_2F0]; struct IXMLDOMNamedNodeMap *
0x1400430b5  mov     rcx, [rsp+340h+var_2D0]; struct IXMLDOMDocument *
0x1400430ba  call    ?AddAttributeToAttributeList@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNamedNodeMap@@PEAG2@Z; AddAttributeToAttributeList(IXMLDOMDocument *,IXMLDOMNamedNodeMap *,ushort *,ushort *)
0x1400430bf  mov     esi, eax
0x1400430c1  test    eax, eax
0x1400430c3  js      loc_14004359F
0x1400430c9  test    r15, r15
0x1400430cc  jz      short loc_1400430E6
0x1400430ce  mov     rcx, r15; bstrString
0x1400430d1  call    cs:__imp_SysFreeString
0x1400430d8  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
