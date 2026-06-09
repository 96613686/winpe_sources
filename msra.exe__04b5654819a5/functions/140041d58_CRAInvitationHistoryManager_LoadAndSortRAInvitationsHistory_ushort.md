# CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory(ushort *)

- ea: `0x140041d58`
- end: `0x140042ba2`
- name: `?LoadAndSortRAInvitationsHistory@CRAInvitationHistoryManager@@QEAAJPEAG@Z`
- size: `3658`
- prototype: `int(CRAInvitationHistoryManager *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140029334`
- `0x14002f0d0`

## callees

- `0x140001cc4`
- `0x1400044f8`
- `0x14000a0e4`
- `0x140034ce4`
- `0x140035600`
- `0x140041cc8`
- `0x140041d58`
- `0x140043d04`
- `0x140043d58`
- `0x140043dac`
- `0x1400441fc`
- `0x140044250`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14004241f`
- `KERNEL32!GetProcessHeap` at `0x14004241f`
- `KERNEL32!HeapAlloc` at `0x140042434`
- `KERNEL32!HeapAlloc` at `0x140042434`
- `msvcrt!_wtoi` at `0x1400421bd`
- `msvcrt!_wtoi` at `0x1400421bd`
- `msvcrt!swscanf_s` at `0x140042267`
- `msvcrt!swscanf_s` at `0x140042267`
- `ole32!CoCreateInstance` at `0x140041e0a`
- `ole32!CoCreateInstance` at `0x140041e0a`
- `OLEAUT32!__imp_SysAllocString` at `0x140041f94`
- `OLEAUT32!__imp_SysAllocString` at `0x140041f94`
- `OLEAUT32!__imp_SysFreeString` at `0x140042188`
- `OLEAUT32!__imp_SysFreeString` at `0x1400421f6`
- `OLEAUT32!__imp_SysFreeString` at `0x140042284`
- `OLEAUT32!__imp_SysFreeString` at `0x1400422ec`
- `OLEAUT32!__imp_SysFreeString` at `0x140042348`
- `OLEAUT32!__imp_SysFreeString` at `0x1400423a4`
- `OLEAUT32!__imp_SysFreeString` at `0x140042400`
- `OLEAUT32!__imp_SysFreeString` at `0x140042b0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140042188`
- `OLEAUT32!__imp_SysFreeString` at `0x1400421f6`
- `OLEAUT32!__imp_SysFreeString` at `0x140042284`
- `OLEAUT32!__imp_SysFreeString` at `0x1400422ec`
- `OLEAUT32!__imp_SysFreeString` at `0x140042348`
- `OLEAUT32!__imp_SysFreeString` at `0x1400423a4`
- `OLEAUT32!__imp_SysFreeString` at `0x140042400`
- `OLEAUT32!__imp_SysFreeString` at `0x140042b0f`
- `OLEAUT32!__imp_VariantClear` at `0x140041e69`
- `OLEAUT32!__imp_VariantClear` at `0x140041ec8`
- `OLEAUT32!__imp_VariantClear` at `0x140041f27`
- `OLEAUT32!__imp_VariantClear` at `0x140041f7c`
- `OLEAUT32!__imp_VariantClear` at `0x140041fea`
- `OLEAUT32!__imp_VariantClear` at `0x140041e69`
- `OLEAUT32!__imp_VariantClear` at `0x140041ec8`
- `OLEAUT32!__imp_VariantClear` at `0x140041f27`
- `OLEAUT32!__imp_VariantClear` at `0x140041f7c`
- `OLEAUT32!__imp_VariantClear` at `0x140041fea`

## string_xrefs

- `0x1400422b7`: `COMPUTERNAME`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory(
        CRAInvitationHistoryManager *this,
        unsigned __int16 *a2)
{
  HRESULT v4; // eax
  CEventLogger *v5; // rcx
  signed int v6; // ebx
  unsigned int v7; // r9d
  __int64 v8; // rax
  CEventLogger *v9; // rcx
  __int64 v10; // rax
  CEventLogger *v11; // rcx
  __int64 v12; // rax
  CEventLogger *v13; // rcx
  LPVOID v14; // rbx
  __int64 v15; // rsi
  signed int v16; // ebx
  CEventLogger *v17; // rcx
  signed int v18; // eax
  CEventLogger *v19; // rcx
  int v20; // r14d
  char *v21; // rax
  CEventLogger *v22; // rcx
  char *v23; // rdi
  signed int v24; // eax
  CEventLogger *v25; // rcx
  signed int v26; // eax
  CEventLogger *v27; // rcx
  signed int AttributeFromAttributeList; // eax
  CEventLogger *v29; // rcx
  OLECHAR *v30; // rsi
  signed int v31; // eax
  CEventLogger *v32; // rcx
  signed int v33; // eax
  CEventLogger *v34; // rcx
  OLECHAR *v35; // rbx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  signed int v39; // eax
  CEventLogger *v40; // rcx
  OLECHAR *v41; // rbx
  CEventLogger *v42; // rcx
  OLECHAR *v43; // rsi
  signed int v44; // eax
  CEventLogger *v45; // rcx
  signed int v46; // eax
  CEventLogger *v47; // rcx
  OLECHAR *v48; // rsi
  signed int v49; // eax
  CEventLogger *v50; // rcx
  signed int v51; // eax
  CEventLogger *v52; // rcx
  OLECHAR *v53; // rsi
  signed int v54; // eax
  CEventLogger *v55; // rcx
  signed int v56; // eax
  CEventLogger *v57; // rcx
  OLECHAR *v58; // rsi
  signed int v59; // eax
  CEventLogger *v60; // rcx
  signed int v61; // eax
  CEventLogger *v62; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v64; // rax
  CEventLogger *v65; // rcx
  _QWORD *v66; // rcx
  struct IXMLDOMNamedNodeMap *v68; // [rsp+50h] [rbp-79h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-71h] BYREF
  CEventLogger *v70; // [rsp+60h] [rbp-69h] BYREF
  __int16 v71; // [rsp+68h] [rbp-61h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-59h] BYREF
  int v73; // [rsp+78h] [rbp-51h] BYREF
  __int64 v74; // [rsp+80h] [rbp-49h] BYREF
  BSTR v75; // [rsp+88h] [rbp-41h] BYREF
  CEventLogger *v76; // [rsp+90h] [rbp-39h] BYREF
  VARIANTARG v77; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v78; // [rsp+C0h] [rbp-9h]
  char *v79; // [rsp+C8h] [rbp-1h]
  VARIANTARG pvarg; // [rsp+D0h] [rbp+7h] BYREF

  ppv = 0;
  v71 = -1;
  v76 = 0;
  v74 = 0;
  v75 = 0;
  CRAInvitationHistoryManager::EmptyList(this);
  v4 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v75, L"RAINVITATIONCOLL");
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 656;
LABEL_3:
    CEventLogger::LogError(
      v5,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      v7,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v4);
    goto LABEL_165;
  }
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 663;
    goto LABEL_3;
  }
  v8 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v77 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v8 + 640))(ppv, L"ProhibitDTD", &v77);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x299u,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v6);
    goto LABEL_165;
  }
  v10 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v77 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v10 + 640))(ppv, L"AllowXsltScript", &v77);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v11,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x29Au,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v6);
    goto LABEL_165;
  }
  v12 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v77 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v12 + 640))(
         ppv,
         L"AllowDocumentFunction",
         &v77);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x29Bu,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v6);
    goto LABEL_165;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 669;
    goto LABEL_3;
  }
  v14 = ppv;
  v15 = *(_QWORD *)ppv;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a2);
  if ( !pvarg.llVal && a2 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v77 = pvarg;
  v16 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v15 + 464))(v14, &v77, &v71);
  VariantClear(&pvarg);
  if ( v16 < 0 || !v71 )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x2A2u,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v16);
    goto LABEL_164;
  }
  v18 = (*(__int64 (__fastcall **)(LPVOID, BSTR, CEventLogger **))(*(_QWORD *)ppv + 296LL))(ppv, v75, &v76);
  if ( v18 < 0 || (v19 = v76) == 0 )
  {
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x2AAu,
      L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
      v18);
LABEL_164:
    v6 = -2147467259;
    goto LABEL_165;
  }
  v4 = (*(__int64 (__fastcall **)(CEventLogger *, __int64 *))(*(_QWORD *)v76 + 96LL))(v76, &v74);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 688;
    goto LABEL_3;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, CRAInvitationHistoryManager *))(*(_QWORD *)v74 + 64LL))(v74, this);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 690;
    goto LABEL_3;
  }
  v20 = 0;
  if ( *(int *)this > 60 )
  {
    *(_DWORD *)this = 60;
    goto LABEL_28;
  }
  if ( *(int *)this <= 0 )
    goto LABEL_166;
LABEL_28:
  while ( 1 )
  {
    v70 = 0;
    v78 = 0;
    v68 = 0;
    *(_OWORD *)&pvarg.vt = 0;
    v73 = 0;
    bstrString = 0;
    v21 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v21;
    v79 = v21;
    if ( !v21 )
      break;
    *(_OWORD *)(v21 + 40) = 0;
    *((_DWORD *)v21 + 14) = 0;
    *(_QWORD *)v21 = 0;
    *((_QWORD *)v21 + 1) = 0;
    *((_QWORD *)v21 + 2) = 0;
    *((_QWORD *)v21 + 3) = 0;
    *((_QWORD *)v21 + 4) = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, CEventLogger **))(*(_QWORD *)v74 + 72LL))(v74, &v70);
    if ( v24 < 0 || (v25 = v70) == 0 )
    {
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x2C9u,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        v24);
      v6 = -2147467259;
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    v26 = (*(__int64 (__fastcall **)(CEventLogger *, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v70 + 136LL))(v70, &v68);
    if ( v26 < 0 || (v27 = (CEventLogger *)v68) == 0 )
    {
      CEventLogger::LogError(
        v27,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x2D1u,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        v26);
      v6 = -2147467259;
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    AttributeFromAttributeList = GetAttributeFromAttributeList(v68, L"NAME", &bstrString);
    v6 = AttributeFromAttributeList;
    if ( AttributeFromAttributeList < 0 )
    {
      CEventLogger::LogError(
        v29,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x2DCu,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        AttributeFromAttributeList);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    v30 = bstrString;
    v31 = CRAInvitationHistoryItem::put_Name((CRAInvitationHistoryItem *)v23, bstrString);
    v6 = v31;
    if ( v31 < 0 )
    {
      CEventLogger::LogError(
        v32,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x2DEu,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        v31);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    if ( v30 )
    {
      SysFreeString(v30);
      bstrString = 0;
    }
    v33 = GetAttributeFromAttributeList(v68, L"TYPE", &bstrString);
    v6 = v33;
    if ( v33 < 0 )
    {
      CEventLogger::LogError(
        v34,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x2E7u,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        v33);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    v35 = bstrString;
    v36 = _wtoi(bstrString) - 1;
    if ( v36 )
    {
      v37 = v36 - 1;
      if ( !v37 )
      {
        v38 = 2;
        goto LABEL_44;
      }
      if ( v37 == 1 )
      {
        v38 = 3;
        goto LABEL_44;
      }
    }
    v38 = 1;
LABEL_44:
    *((_DWORD *)v23 + 14) = v38;
    if ( v35 )
    {
      SysFreeString(v35);
      bstrString = 0;
    }
    v39 = GetAttributeFromAttributeList(v68, L"TIME", &bstrString);
    v6 = v39;
    if ( v39 < 0 )
    {
      CEventLogger::LogError(
        v40,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x301u,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        v39);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    v41 = bstrString;
    if ( swscanf_s(
           bstrString,
           L"%04hd%02hd%02hd%02hd%02hd%02hd.%06d",
           &pvarg,
           &pvarg.decVal.scale,
           (char *)&pvarg.decVal.Hi32 + 2,
           &pvarg.decVal.Lo32,
           (char *)&pvarg.decVal.Lo64 + 2,
           (char *)&pvarg.decVal.Lo64 + 4,
           &v73) != 7 )
    {
      v6 = -2147024809;
      CEventLogger::LogError(
        v42,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x30Eu,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        0x80070057);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    if ( v41 )
    {
      SysFreeString(v41);
      bstrString = 0;
    }
    HIWORD(pvarg.decVal.Lo64) = (__int16)v73 / 1000;
    *(_OWORD *)(v23 + 40) = *(_OWORD *)&pvarg.vt;
    if ( GetAttributeFromAttributeList(v68, L"COMPUTERNAME", &bstrString) < 0 )
    {
      v46 = CRAInvitationHistoryItem::put_ComputerName((CRAInvitationHistoryItem *)v23, 0);
      v6 = v46;
      if ( v46 < 0 )
      {
        CEventLogger::LogError(
          v47,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x324u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v46);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
    }
    else
    {
      v43 = bstrString;
      v44 = CRAInvitationHistoryItem::put_ComputerName((CRAInvitationHistoryItem *)v23, bstrString);
      v6 = v44;
      if ( v44 < 0 )
      {
        CEventLogger::LogError(
          v45,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x31Fu,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v44);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
      if ( v43 )
      {
        SysFreeString(v43);
        bstrString = 0;
      }
    }
    if ( GetAttributeFromAttributeList(v68, L"AVATAR", &bstrString) < 0 )
    {
      v51 = CRAInvitationHistoryItem::put_Avatar((CRAInvitationHistoryItem *)v23, 0);
      v6 = v51;
      if ( v51 < 0 )
      {
        CEventLogger::LogError(
          v52,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x335u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v51);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
    }
    else
    {
      v48 = bstrString;
      v49 = CRAInvitationHistoryItem::put_Avatar((CRAInvitationHistoryItem *)v23, bstrString);
      v6 = v49;
      if ( v49 < 0 )
      {
        CEventLogger::LogError(
          v50,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x330u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v49);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
      if ( v48 )
      {
        SysFreeString(v48);
        bstrString = 0;
      }
    }
    if ( GetAttributeFromAttributeList(v68, L"PUBLICKEY", &bstrString) < 0 )
    {
      v56 = CRAInvitationHistoryItem::put_PublicKey((CRAInvitationHistoryItem *)v23, 0);
      v6 = v56;
      if ( v56 < 0 )
      {
        CEventLogger::LogError(
          v57,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x346u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v56);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
    }
    else
    {
      v53 = bstrString;
      v54 = CRAInvitationHistoryItem::put_PublicKey((CRAInvitationHistoryItem *)v23, bstrString);
      v6 = v54;
      if ( v54 < 0 )
      {
        CEventLogger::LogError(
          v55,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x341u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v54);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
      if ( v53 )
      {
        SysFreeString(v53);
        bstrString = 0;
      }
    }
    if ( GetAttributeFromAttributeList(v68, L"ADDRESS", &bstrString) < 0 )
    {
      v61 = CRAInvitationHistoryItem::put_Address((CRAInvitationHistoryItem *)v23, 0);
      v6 = v61;
      if ( v61 < 0 )
      {
        CEventLogger::LogError(
          v62,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x357u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v61);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
    }
    else
    {
      v58 = bstrString;
      v59 = CRAInvitationHistoryItem::put_Address((CRAInvitationHistoryItem *)v23, bstrString);
      v6 = v59;
      if ( v59 < 0 )
      {
        CEventLogger::LogError(
          v60,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x352u,
          L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
          v59);
        if ( v68 )
          ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
        if ( v70 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
        goto LABEL_165;
      }
      if ( v58 )
        SysFreeString(v58);
    }
    ProcessHeap = GetProcessHeap();
    v64 = HeapAlloc(ProcessHeap, 0, 0x18u);
    if ( !v64 )
    {
      v6 = -2147467261;
      CEventLogger::LogError(
        v65,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x35Du,
        L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
        0x80004003);
      if ( v68 )
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
      if ( v70 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
      goto LABEL_165;
    }
    v64[2] = v23;
    v66 = (_QWORD *)*((_QWORD *)this + 62);
    *v64 = (char *)this + 488;
    v64[1] = v66;
    *v66 = v64;
    *((_QWORD *)this + 62) = v64;
    if ( v68 )
      ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
    if ( v70 )
      (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
    if ( ++v20 >= *(_DWORD *)this )
      goto LABEL_166;
  }
  v6 = -2147024882;
  CEventLogger::LogError(
    v22,
    &Recoverable_Error,
    (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
    0x2C5u,
    L"CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory",
    0x8007000E);
  if ( v68 )
    ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v68->lpVtbl->Release)(v68);
  if ( v70 )
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v70 + 16LL))(v70);
LABEL_165:
  *(_DWORD *)this = 0;
LABEL_166:
  SysFreeString(v75);
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  if ( v76 )
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v76 + 16LL))(v76);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140041d58  mov     [rsp-8+arg_10], rbx
0x140041d5d  mov     [rsp-8+arg_18], rsi
0x140041d62  push    rbp
0x140041d63  push    rdi
0x140041d64  push    r12
0x140041d66  push    r14
0x140041d68  push    r15
0x140041d6a  lea     rbp, [rsp-37h]
0x140041d6f  sub     rsp, 100h
0x140041d76  mov     rax, cs:__security_cookie
0x140041d7d  xor     rax, rsp
0x140041d80  mov     [rbp+57h+var_30], rax
0x140041d84  mov     rdi, rdx
0x140041d87  mov     r15, rcx
0x140041d8a  xor     r12d, r12d
0x140041d8d  mov     [rbp+57h+var_B0], r12
0x140041d91  or      esi, 0FFFFFFFFh
0x140041d94  mov     [rbp+57h+var_B8], si
0x140041d98  mov     [rbp+57h+var_90], r12
0x140041d9c  mov     [rbp+57h+var_A0], r12
0x140041da0  mov     [rbp+57h+var_98], r12
0x140041da4  call    ?EmptyList@CRAInvitationHistoryManager@@AEAAXXZ; CRAInvitationHistoryManager::EmptyList(void)
0x140041da9  lea     rdx, aRainvitationco; "RAINVITATIONCOLL"
0x140041db0  lea     rcx, [rbp+57h+var_98]; this
0x140041db4  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140041db9  mov     ebx, eax
0x140041dbb  test    eax, eax
0x140041dbd  jns     short loc_140041DED
0x140041dbf  mov     r9d, 290h; unsigned int
0x140041dc5  mov     [rsp+120h+var_F8], eax; unsigned int
0x140041dc9  lea     rax, aCrainvitationh_7; "CRAInvitationHistoryManager::LoadAndSor"...
0x140041dd0  mov     [rsp+120h+ppv], rax; unsigned __int16 *
0x140041dd5  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140041ddc  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140041de3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140041de8  jmp     loc_140042B08
0x140041ded  lea     rax, [rbp+57h+var_B0]
0x140041df1  mov     [rsp+120h+ppv], rax; ppv
0x140041df6  lea     r9, IID_IXMLDOMDocument; riid
0x140041dfd  xor     edx, edx; pUnkOuter
0x140041dff  lea     r8d, [rdx+1]; dwClsContext
0x140041e03  lea     rcx, CLSID_DOMDocument60; rclsid
0x140041e0a  call    cs:__imp_CoCreateInstance
0x140041e11  nop     dword ptr [rax+rax+00h]
0x140041e16  mov     ebx, eax
0x140041e18  test    eax, eax
0x140041e1a  jns     short loc_140041E24
0x140041e1c  mov     r9d, 297h
0x140041e22  jmp     short loc_140041DC5
0x140041e24  mov     rcx, [rbp+57h+var_B0]
0x140041e28  mov     rax, [rcx]
0x140041e2b  mov     r14d, 0Bh
0x140041e31  mov     word ptr [rbp+57h+pvarg], r14w
0x140041e36  mov     word ptr [rbp+57h+pvarg+8], si
0x140041e3a  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140041e3e  movaps  [rbp+57h+var_80], xmm0
0x140041e42  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140041e47  movsd   [rbp+57h+var_70], xmm1
0x140041e4c  lea     r8, [rbp+57h+var_80]
0x140041e50  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x140041e57  mov     rax, [rax+280h]
0x140041e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041e63  mov     ebx, eax
0x140041e65  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041e69  call    cs:__imp_VariantClear
0x140041e70  nop     dword ptr [rax+rax+00h]
0x140041e75  test    ebx, ebx
0x140041e77  jns     short loc_140041E88
0x140041e79  mov     [rsp+120h+var_F8], ebx
0x140041e7d  mov     r9d, 299h
0x140041e83  jmp     loc_140041DC9
0x140041e88  mov     rcx, [rbp+57h+var_B0]
0x140041e8c  mov     rax, [rcx]
0x140041e8f  mov     word ptr [rbp+57h+pvarg], r14w
0x140041e94  mov     word ptr [rbp+57h+pvarg+8], r12w
0x140041e99  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140041e9d  movaps  [rbp+57h+var_80], xmm0
0x140041ea1  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140041ea6  movsd   [rbp+57h+var_70], xmm1
0x140041eab  lea     r8, [rbp+57h+var_80]
0x140041eaf  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x140041eb6  mov     rax, [rax+280h]
0x140041ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041ec2  mov     ebx, eax
0x140041ec4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041ec8  call    cs:__imp_VariantClear
0x140041ecf  nop     dword ptr [rax+rax+00h]
0x140041ed4  test    ebx, ebx
0x140041ed6  jns     short loc_140041EE7
0x140041ed8  mov     [rsp+120h+var_F8], ebx
0x140041edc  mov     r9d, 29Ah
0x140041ee2  jmp     loc_140041DC9
0x140041ee7  mov     rcx, [rbp+57h+var_B0]
0x140041eeb  mov     rax, [rcx]
0x140041eee  mov     word ptr [rbp+57h+pvarg], r14w
0x140041ef3  mov     word ptr [rbp+57h+pvarg+8], r12w
0x140041ef8  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140041efc  movaps  [rbp+57h+var_80], xmm0
0x140041f00  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140041f05  movsd   [rbp+57h+var_70], xmm1
0x140041f0a  lea     r8, [rbp+57h+var_80]
0x140041f0e  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140041f15  mov     rax, [rax+280h]
0x140041f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f21  mov     ebx, eax
0x140041f23  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041f27  call    cs:__imp_VariantClear
0x140041f2e  nop     dword ptr [rax+rax+00h]
0x140041f33  test    ebx, ebx
0x140041f35  jns     short loc_140041F46
0x140041f37  mov     [rsp+120h+var_F8], ebx
0x140041f3b  mov     r9d, 29Bh
0x140041f41  jmp     loc_140041DC9
0x140041f46  mov     rcx, [rbp+57h+var_B0]
0x140041f4a  mov     rax, [rcx]
0x140041f4d  xor     edx, edx
0x140041f4f  mov     rax, [rax+1F8h]
0x140041f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f5b  mov     ebx, eax
0x140041f5d  test    eax, eax
0x140041f5f  jns     short loc_140041F6C
0x140041f61  mov     r9d, 29Dh
0x140041f67  jmp     loc_140041DC5
0x140041f6c  mov     rbx, [rbp+57h+var_B0]
0x140041f70  mov     rsi, [rbx]
0x140041f73  mov     word ptr [rbp+57h+pvarg], r12w
0x140041f78  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041f7c  call    cs:__imp_VariantClear
0x140041f83  nop     dword ptr [rax+rax+00h]
0x140041f88  mov     eax, 8
0x140041f8d  mov     word ptr [rbp+57h+pvarg], ax
0x140041f91  mov     rcx, rdi; psz
0x140041f94  call    cs:__imp_SysAllocString
0x140041f9b  nop     dword ptr [rax+rax+00h]
0x140041fa0  mov     dword ptr [rbp+57h+pvarg+8], eax
0x140041fa3  mov     rcx, rax
0x140041fa6  sar     rcx, 20h
0x140041faa  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x140041fad  test    rax, rax
0x140041fb0  jnz     short loc_140041FBB
0x140041fb2  test    rdi, rdi
0x140041fb5  jnz     loc_140042B89
0x140041fbb  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140041fbf  movaps  [rbp+57h+var_80], xmm0
0x140041fc3  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140041fc8  movsd   [rbp+57h+var_70], xmm1
0x140041fcd  lea     r8, [rbp+57h+var_B8]
0x140041fd1  lea     rdx, [rbp+57h+var_80]
0x140041fd5  mov     rcx, rbx
0x140041fd8  mov     rax, [rsi+1D0h]
0x140041fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041fe4  mov     ebx, eax
0x140041fe6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140041fea  call    cs:__imp_VariantClear
0x140041ff1  nop     dword ptr [rax+rax+00h]
0x140041ff6  test    ebx, ebx
0x140041ff8  js      loc_140042ADA
0x140041ffe  cmp     [rbp+57h+var_B8], r12w
0x140042003  jz      loc_140042ADA
0x140042009  mov     rcx, [rbp+57h+var_B0]
0x14004200d  mov     rax, [rcx]
0x140042010  lea     r8, [rbp+57h+var_90]
0x140042014  mov     rdx, [rbp+57h+var_98]
0x140042018  mov     rax, [rax+128h]
0x14004201f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042024  test    eax, eax
0x140042026  js      loc_140042ACE
0x14004202c  mov     rcx, [rbp+57h+var_90]
0x140042030  test    rcx, rcx
0x140042033  jz      loc_140042ACE
0x140042039  mov     rax, [rcx]
0x14004203c  lea     rdx, [rbp+57h+var_A0]
0x140042040  mov     rax, [rax+60h]
0x140042044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042049  mov     ebx, eax
0x14004204b  test    eax, eax
0x14004204d  jns     short loc_14004205A
0x14004204f  mov     r9d, 2B0h
0x140042055  jmp     loc_140041DC5
0x14004205a  mov     rcx, [rbp+57h+var_A0]
0x14004205e  mov     rax, [rcx]
0x140042061  mov     rdx, r15
0x140042064  mov     rax, [rax+40h]
0x140042068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004206d  mov     ebx, eax
0x14004206f  test    eax, eax
0x140042071  jns     short loc_14004207E
0x140042073  mov     r9d, 2B2h
0x140042079  jmp     loc_140041DC5
0x14004207e  mov     r14d, r12d
0x140042081  cmp     dword ptr [r15], 3Ch ; '<'
0x140042085  jle     short loc_140042090
0x140042087  mov     dword ptr [r15], 3Ch ; '<'
0x14004208e  jmp     short loc_140042099
0x140042090  cmp     [r15], r12d
0x140042093  jle     loc_140042B0B
0x140042099  mov     [rbp+57h+var_C0], r12
0x14004209d  mov     [rbp+57h+var_60], r12
0x1400420a1  mov     [rbp+57h+var_D0], r12
0x1400420a5  xorps   xmm0, xmm0
0x1400420a8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1400420ac  mov     [rbp+57h+var_A8], r12d
0x1400420b0  mov     [rbp+57h+bstrString], r12
0x1400420b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400420bb  mov     ecx, 40h ; '@'; unsigned __int64
0x1400420c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400420c5  mov     rdi, rax
0x1400420c8  mov     [rbp+57h+var_58], rax
0x1400420cc  test    rax, rax
0x1400420cf  jz      loc_140042A6D
0x1400420d5  xorps   xmm0, xmm0
0x1400420d8  movups  xmmword ptr [rax+28h], xmm0
0x1400420dc  mov     [rax+38h], r12d
0x1400420e0  mov     [rax], r12
0x1400420e3  mov     [rax+8], r12
0x1400420e7  mov     [rax+10h], r12
0x1400420eb  mov     [rax+18h], r12
0x1400420ef  mov     [rax+20h], r12
0x1400420f3  test    rax, rax
0x1400420f6  jz      loc_140042A6D
0x1400420fc  mov     rcx, [rbp+57h+var_A0]
0x140042100  mov     rax, [rcx]
0x140042103  lea     rdx, [rbp+57h+var_C0]
0x140042107  mov     rax, [rax+48h]
0x14004210b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042110  test    eax, eax
0x140042112  js      loc_140042A0E
0x140042118  mov     rcx, [rbp+57h+var_C0]
0x14004211c  test    rcx, rcx
0x14004211f  jz      loc_140042A0E
0x140042125  mov     rax, [rcx]
0x140042128  lea     rdx, [rbp+57h+var_D0]
0x14004212c  mov     rax, [rax+88h]
0x140042133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042138  test    eax, eax
0x14004213a  js      loc_1400429AF
0x140042140  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNamedNodeMap *
0x140042144  test    rcx, rcx
0x140042147  jz      loc_1400429AF
0x14004214d  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x140042151  lea     rdx, aName; "NAME"
0x140042158  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x14004215d  mov     ebx, eax
0x14004215f  test    eax, eax
0x140042161  js      loc_140042954
0x140042167  mov     rsi, [rbp+57h+bstrString]
0x14004216b  mov     rdx, rsi; unsigned __int16 *
0x14004216e  mov     rcx, rdi; this
0x140042171  call    ?put_Name@CRAInvitationHistoryItem@@QEAAJPEAG@Z; CRAInvitationHistoryItem::put_Name(ushort *)
0x140042176  mov     ebx, eax
0x140042178  test    eax, eax
0x14004217a  js      loc_1400428F9
0x140042180  test    rsi, rsi
0x140042183  jz      short loc_140042198
0x140042185  mov     rcx, rsi; bstrString
0x140042188  call    cs:__imp_SysFreeString
0x14004218f  nop     dword ptr [rax+rax+00h]
0x140042194  mov     [rbp+57h+bstrString], r12
0x140042198  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x14004219c  lea     rdx, aType; "TYPE"
0x1400421a3  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNamedNodeMap *
0x1400421a7  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x1400421ac  mov     ebx, eax
0x1400421ae  test    eax, eax
0x1400421b0  js      loc_14004289E
0x1400421b6  mov     rbx, [rbp+57h+bstrString]
0x1400421ba  mov     rcx, rbx; String
0x1400421bd  call    cs:__imp__wtoi
0x1400421c4  nop     dword ptr [rax+rax+00h]
0x1400421c9  sub     eax, 1
0x1400421cc  jz      short loc_1400421E6
0x1400421ce  sub     eax, 1
0x1400421d1  jz      short loc_1400421DF
0x1400421d3  cmp     eax, 1
0x1400421d6  jnz     short loc_1400421E6
0x1400421d8  mov     eax, 3
0x1400421dd  jmp     short loc_1400421EB
0x1400421df  mov     eax, 2
0x1400421e4  jmp     short loc_1400421EB
0x1400421e6  mov     eax, 1
0x1400421eb  mov     [rdi+38h], eax
0x1400421ee  test    rbx, rbx
0x1400421f1  jz      short loc_140042206
0x1400421f3  mov     rcx, rbx; bstrString
0x1400421f6  call    cs:__imp_SysFreeString
0x1400421fd  nop     dword ptr [rax+rax+00h]
0x140042202  mov     [rbp+57h+bstrString], r12
0x140042206  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x14004220a  lea     rdx, aTime; "TIME"
0x140042211  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMNamedNodeMap *
0x140042215  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x14004221a  mov     ebx, eax
0x14004221c  test    eax, eax
0x14004221e  js      loc_140042843
0x140042224  lea     rax, [rbp+57h+var_A8]
0x140042228  mov     [rsp+120h+var_E0], rax
0x14004222d  lea     rax, [rbp+57h+pvarg+0Ch]
0x140042231  mov     [rsp+120h+var_E8], rax
0x140042236  lea     rax, [rbp+57h+pvarg+0Ah]
0x14004223a  mov     [rsp+120h+var_F0], rax
  ... truncated ...
```
