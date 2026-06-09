# CRATicket::SaveRATicket(ushort *,int)

- ea: `0x14003db44`
- end: `0x14003e9fe`
- name: `?SaveRATicket@CRATicket@@QEAAJPEAGH@Z`
- size: `3770`
- prototype: `__int64 __fastcall(CRATicket *__hidden this, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f624`
- `0x140027ce0`
- `0x14002b4a0`

## callees

- `0x140001cc4`
- `0x1400044f8`
- `0x14000a0e4`
- `0x140034ce4`
- `0x14003db44`
- `0x140040390`
- `0x140041058`
- `0x140041914`
- `0x14004d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14003e6ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x14003e6ba`
- `ole32!CoCreateInstance` at `0x14003dc86`
- `ole32!CoCreateInstance` at `0x14003dc86`
- `OLEAUT32!__imp_SysAllocString` at `0x14003dfe5`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e154`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e284`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e556`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e63c`
- `OLEAUT32!__imp_SysAllocString` at `0x14003dfe5`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e154`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e284`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e556`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e63c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6e0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6ef`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6fe`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e70d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e71d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e72e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e73e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e74e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e75d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e76d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e77d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e78c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e79c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e7ac`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e7bd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6e0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6ef`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e6fe`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e70d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e71d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e72e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e73e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e74e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e75d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e76d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e77d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e78c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e79c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e7ac`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e7bd`
- `OLEAUT32!__imp_VariantInit` at `0x14003dbd4`
- `OLEAUT32!__imp_VariantInit` at `0x14003dbd4`
- `OLEAUT32!__imp_VariantClear` at `0x14003dd18`
- `OLEAUT32!__imp_VariantClear` at `0x14003dd86`
- `OLEAUT32!__imp_VariantClear` at `0x14003ddf4`
- `OLEAUT32!__imp_VariantClear` at `0x14003df28`
- `OLEAUT32!__imp_VariantClear` at `0x14003dfc8`
- `OLEAUT32!__imp_VariantClear` at `0x14003e137`
- `OLEAUT32!__imp_VariantClear` at `0x14003e267`
- `OLEAUT32!__imp_VariantClear` at `0x14003e37d`
- `OLEAUT32!__imp_VariantClear` at `0x14003e469`
- `OLEAUT32!__imp_VariantClear` at `0x14003e539`
- `OLEAUT32!__imp_VariantClear` at `0x14003e620`
- `OLEAUT32!__imp_VariantClear` at `0x14003e6a1`
- `OLEAUT32!__imp_VariantClear` at `0x14003e7cf`
- `OLEAUT32!__imp_VariantClear` at `0x14003dd18`
- `OLEAUT32!__imp_VariantClear` at `0x14003dd86`
- `OLEAUT32!__imp_VariantClear` at `0x14003ddf4`
- `OLEAUT32!__imp_VariantClear` at `0x14003df28`
- `OLEAUT32!__imp_VariantClear` at `0x14003dfc8`
- `OLEAUT32!__imp_VariantClear` at `0x14003e137`
- `OLEAUT32!__imp_VariantClear` at `0x14003e267`
- `OLEAUT32!__imp_VariantClear` at `0x14003e37d`
- `OLEAUT32!__imp_VariantClear` at `0x14003e469`
- `OLEAUT32!__imp_VariantClear` at `0x14003e539`
- `OLEAUT32!__imp_VariantClear` at `0x14003e620`
- `OLEAUT32!__imp_VariantClear` at `0x14003e6a1`
- `OLEAUT32!__imp_VariantClear` at `0x14003e7cf`

## string_xrefs

- `0x14003de15`: `<?xml version="1.0" ?><UPLOADINFO TYPE="Escalated"></UPLOADINFO>`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
__int64 __fastcall CRATicket::SaveRATicket(OLECHAR **this, unsigned __int16 *a2, int a3)
{
  OLECHAR *v3; // rsi
  OLECHAR *v4; // rdi
  OLECHAR *v5; // rbx
  OLECHAR *v6; // r12
  OLECHAR *v7; // r13
  OLECHAR *v8; // r14
  OLECHAR *v9; // r15
  HRESULT Instance; // eax
  CEventLogger *v11; // rcx
  unsigned int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  CRAEncryption *v17; // rax
  CRAEncryption *v18; // rcx
  int v19; // eax
  int v20; // eax
  VARIANTARG pvarg; // [rsp+38h] [rbp-D0h] BYREF
  IRecordInfo *v23; // [rsp+50h] [rbp-B8h]
  __int64 v24; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v25; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v26; // [rsp+88h] [rbp-80h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-30h] BYREF
  OLECHAR *v35; // [rsp+E0h] [rbp-28h] BYREF
  OLECHAR *v36; // [rsp+E8h] [rbp-20h] BYREF
  OLECHAR *v37; // [rsp+F0h] [rbp-18h] BYREF
  OLECHAR *v38; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *v39; // [rsp+100h] [rbp-8h] BYREF
  OLECHAR *v40; // [rsp+108h] [rbp+0h] BYREF
  OLECHAR *v41; // [rsp+110h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+118h] [rbp+10h] BYREF
  BSTR v43; // [rsp+120h] [rbp+18h] BYREF
  __int64 v44; // [rsp+128h] [rbp+20h] BYREF
  __int64 v45; // [rsp+130h] [rbp+28h] BYREF
  __int64 v46; // [rsp+138h] [rbp+30h] BYREF
  __int64 v47; // [rsp+140h] [rbp+38h] BYREF
  __int64 v48; // [rsp+148h] [rbp+40h] BYREF
  CRAEncryption *v49; // [rsp+150h] [rbp+48h]
  __int64 v50; // [rsp+158h] [rbp+50h] BYREF
  __int64 v51; // [rsp+160h] [rbp+58h] BYREF
  __int64 v52; // [rsp+168h] [rbp+60h]
  __int64 v53; // [rsp+170h] [rbp+68h]
  __int64 v54; // [rsp+178h] [rbp+70h]
  __int64 v55; // [rsp+180h] [rbp+78h]
  __int64 v56; // [rsp+188h] [rbp+80h]
  __int64 v57; // [rsp+190h] [rbp+88h]
  __int64 v58; // [rsp+198h] [rbp+90h]
  __int64 v59; // [rsp+1A0h] [rbp+98h]
  __int64 v60; // [rsp+1A8h] [rbp+A0h]
  __int64 v61; // [rsp+1B0h] [rbp+A8h]
  __int64 v62; // [rsp+1B8h] [rbp+B0h]
  __int64 v63; // [rsp+1C0h] [rbp+B8h]
  int v66; // [rsp+228h] [rbp+120h] BYREF
  OLECHAR *psz; // [rsp+230h] [rbp+128h]

  v66 = a3;
  v3 = 0;
  *(_QWORD *)&pvarg.vt = 0;
  v24 = 0;
  v34 = 0;
  v33 = 0;
  v54 = 0;
  v32 = 0;
  v52 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v48 = 0;
  v47 = 0;
  v56 = 0;
  v46 = 0;
  v55 = 0;
  v45 = 0;
  v44 = 0;
  v51 = 0;
  v50 = 0;
  v57 = 0;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v43 = 0;
  v4 = 0;
  v40 = 0;
  v5 = 0;
  v39 = 0;
  v58 = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v37 = 0;
  v59 = 0;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v36 = 0;
  bstrString = 0;
  v41 = 0;
  LOWORD(v66) = -1;
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  v60 = 0;
  v63 = 0;
  v61 = 0;
  v62 = 0;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&pvarg);
  LODWORD(psz) = Instance;
  if ( Instance < 0 )
  {
    v12 = 3121;
LABEL_5:
    CEventLogger::LogError(
      v11,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      v12,
      L"CRATicket::SaveRATicket",
      Instance);
    goto LABEL_65;
  }
  v13 = **(_QWORD **)&pvarg.vt;
  v26.vt = 11;
  v26.iVal = -1;
  v25 = v26;
  LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(v13 + 640))(
                   *(_QWORD *)&pvarg.vt,
                   L"ProhibitDTD",
                   &v25);
  VariantClear(&v26);
  Instance = (int)psz;
  if ( (int)psz < 0 )
  {
    v12 = 3123;
    goto LABEL_5;
  }
  v14 = **(_QWORD **)&pvarg.vt;
  v26.vt = 11;
  v26.iVal = 0;
  v25 = v26;
  LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(v14 + 640))(
                   *(_QWORD *)&pvarg.vt,
                   L"AllowXsltScript",
                   &v25);
  VariantClear(&v26);
  Instance = (int)psz;
  if ( (int)psz < 0 )
  {
    v12 = 3124;
    goto LABEL_5;
  }
  v15 = **(_QWORD **)&pvarg.vt;
  v26.vt = 11;
  v26.iVal = 0;
  v25 = v26;
  LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(v15 + 640))(
                   *(_QWORD *)&pvarg.vt,
                   L"AllowDocumentFunction",
                   &v25);
  VariantClear(&v26);
  Instance = (int)psz;
  if ( (int)psz < 0 )
  {
    v12 = 3125;
    goto LABEL_5;
  }
  LODWORD(psz) = ATL::CComBSTR::Append(
                   (ATL::CComBSTR *)&v41,
                   L"<?xml version=\"1.0\" ?><UPLOADINFO TYPE=\"Escalated\"></UPLOADINFO>");
  v3 = v41;
  if ( (int)psz >= 0 )
  {
    LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, int *))(**(_QWORD **)&pvarg.vt + 520LL))(
                     *(_QWORD *)&pvarg.vt,
                     v41,
                     &v66);
    if ( (int)psz >= 0 )
    {
      LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v40, L"UPLOADINFO");
      v4 = v40;
      if ( (int)psz >= 0 )
      {
        if ( (*(int (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt + 296LL))(
               *(_QWORD *)&pvarg.vt,
               v40,
               &v27) >= 0
          && v27 )
        {
          LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v43, L"UPLOADDATA");
          if ( (int)psz >= 0 )
          {
            v16 = **(_QWORD **)&pvarg.vt;
            v26.vt = 3;
            v26.lVal = 1;
            v25 = v26;
            LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *, BSTR, _QWORD, __int64 *))(v16 + 448))(
                             *(_QWORD *)&pvarg.vt,
                             &v25,
                             v43,
                             0,
                             &v28);
            VariantClear(&v26);
            if ( (int)psz >= 0 )
            {
              LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 136LL))(v28, &v24);
              if ( (int)psz >= 0 )
              {
                LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v39, L"USERNAME");
                v5 = v39;
                if ( (int)psz >= 0 )
                {
                  LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt + 424LL))(
                                   *(_QWORD *)&pvarg.vt,
                                   v39,
                                   &v34);
                  if ( (int)psz >= 0 )
                  {
                    psz = *this;
                    VariantClear((VARIANTARG *)&pvarg.decVal.8);
                    pvarg.iVal = 8;
                    pvarg.pRecInfo = (IRecordInfo *)SysAllocString(psz);
                    if ( !pvarg.pRecInfo && psz )
                      goto LABEL_109;
                    *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                    v25.pRecInfo = v23;
                    LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v34 + 72LL))(v34, &v25);
                    if ( (int)psz >= 0 )
                    {
                      LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                       v24,
                                       v34,
                                       &v48);
                      if ( (int)psz >= 0 )
                      {
                        v17 = (CRAEncryption *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
                        v49 = v17;
                        if ( v17 )
                        {
                          *(_QWORD *)v17 = 0;
                          *((_QWORD *)v17 + 1) = 0;
                          *((_QWORD *)v17 + 2) = 0;
                          *((_QWORD *)v17 + 3) = 0;
                          *((_QWORD *)v17 + 4) = 0;
                          *((_QWORD *)v17 + 5) = 0;
                          LODWORD(psz) = CRAEncryption::EncryptTicket(v17, this[22], this[3], this + 5);
                          if ( (int)psz < 0 )
                            goto LABEL_62;
                          LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v38, L"LHTICKET");
                          v6 = v38;
                          if ( (int)psz < 0 )
                            goto LABEL_62;
                          LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt
                                                                                                 + 424LL))(
                                           *(_QWORD *)&pvarg.vt,
                                           v38,
                                           &v33);
                          if ( (int)psz < 0 )
                            goto LABEL_62;
                          psz = this[5];
                          VariantClear((VARIANTARG *)&pvarg.decVal.8);
                          pvarg.iVal = 8;
                          pvarg.pRecInfo = (IRecordInfo *)SysAllocString(psz);
                          if ( !pvarg.pRecInfo && psz )
                            goto LABEL_109;
                          *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                          v25.pRecInfo = v23;
                          LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v33 + 72LL))(
                                           v33,
                                           &v25);
                          if ( (int)psz < 0
                            || (LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                                 v24,
                                                 v33,
                                                 &v47),
                                (int)psz < 0)
                            || (LODWORD(psz) = CRAEncryption::get_PassStub(v18, this + 21), (int)psz < 0)
                            || (LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v37, L"PassStub"),
                                v7 = v37,
                                (int)psz < 0)
                            || (LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt + 424LL))(
                                                 *(_QWORD *)&pvarg.vt,
                                                 v37,
                                                 &v32),
                                (int)psz < 0) )
                          {
LABEL_62:
                            CRAEncryption::~CRAEncryption(v49);
                            operator delete(v49);
                            goto LABEL_65;
                          }
                          psz = this[21];
                          VariantClear((VARIANTARG *)&pvarg.decVal.8);
                          pvarg.iVal = 8;
                          pvarg.pRecInfo = (IRecordInfo *)SysAllocString(psz);
                          if ( pvarg.pRecInfo || !psz )
                          {
                            *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                            v25.pRecInfo = v23;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v32 + 72LL))(
                                             v32,
                                             &v25);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                             v24,
                                             v32,
                                             &v46);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v36, L"DtStart");
                            v9 = v36;
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt + 424LL))(
                                             *(_QWORD *)&pvarg.vt,
                                             v36,
                                             &v31);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            v19 = *((_DWORD *)this + 4);
                            LODWORD(psz) = v19;
                            if ( pvarg.iVal != 19 )
                            {
                              VariantClear((VARIANTARG *)&pvarg.decVal.8);
                              pvarg.iVal = 19;
                              v19 = (int)psz;
                            }
                            *((_DWORD *)&pvarg.decVal + 4) = v19;
                            *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                            v25.pRecInfo = v23;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v31 + 72LL))(
                                             v31,
                                             &v25);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                             v24,
                                             v31,
                                             &v45);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"DtLength");
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**(_QWORD **)&pvarg.vt
                                                                                              + 424LL))(
                                             *(_QWORD *)&pvarg.vt,
                                             bstrString,
                                             &v30);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            v20 = *((_DWORD *)this + 36);
                            LODWORD(psz) = v20;
                            if ( pvarg.iVal != 19 )
                            {
                              VariantClear((VARIANTARG *)&pvarg.decVal.8);
                              pvarg.iVal = 19;
                              v20 = (int)psz;
                            }
                            *((_DWORD *)&pvarg.decVal + 4) = v20;
                            *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                            v25.pRecInfo = v23;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v30 + 72LL))(
                                             v30,
                                             &v25);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                             v24,
                                             v30,
                                             &v44);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = ATL::CComBSTR::Append((ATL::CComBSTR *)&v35, L"L");
                            v8 = v35;
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            LODWORD(psz) = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)&pvarg.vt + 424LL))(
                                             *(_QWORD *)&pvarg.vt,
                                             v35,
                                             &v29);
                            if ( (int)psz < 0 )
                              goto LABEL_62;
                            VariantClear((VARIANTARG *)&pvarg.decVal.8);
                            pvarg.iVal = 8;
                            pvarg.pRecInfo = (IRecordInfo *)SysAllocString(L"0");
                            if ( pvarg.pRecInfo )
                            {
                              *(_OWORD *)&v25.vt = *(_OWORD *)&pvarg.decVal.Lo32;
                              v25.pRecInfo = v23;
                              LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v29 + 72LL))(
                                               v29,
                                               &v25);
                              if ( (int)psz >= 0 )
                              {
                                LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(
                                                 v24,
                                                 v29,
                                                 &v51);
                                if ( (int)psz >= 0 )
                                {
                                  LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 168LL))(
                                                   v27,
                                                   v28,
                                                   &v50);
                                  if ( (int)psz >= 0 )
                                  {
                                    psz = *(OLECHAR **)&pvarg.vt;
                                    v53 = **(_QWORD **)&pvarg.vt;
                                    v26.vt = 0;
                                    VariantClear(&v26);
                                    v26.vt = 8;
                                    v26.llVal = (LONGLONG)SysAllocString(a2);
                                    if ( !v26.llVal && a2 )
                                    {
                                      v26.vt = 10;
                                      v26.lVal = -2147024882;
                                      ATL::AtlThrowImpl(-2147024882);
                                    }
                                    v25 = v26;
                                    LODWORD(psz) = (*(__int64 (__fastcall **)(OLECHAR *, VARIANTARG *))(v53 + 528))(
                                                     psz,
                                                     &v25);
                                    VariantClear(&v26);
                                  }
                                }
                              }
                              goto LABEL_62;
                            }
                          }
LABEL_109:
                          pvarg.iVal = 10;
                          *((_DWORD *)&pvarg.decVal + 4) = -2147024882;
                          ATL::AtlThrowImpl(-2147024882);
                        }
                        LODWORD(psz) = -2147024882;
                      }
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          LODWORD(psz) = -2147467259;
        }
      }
    }
  }
LABEL_65:
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(v3);
  SysFreeString(bstrString);
  SysFreeString(v9);
  SysFreeString(v8);
  SysFreeString(0);
  SysFreeString(v7);
  SysFreeString(v6);
  SysFreeString(0);
  SysFreeString(v5);
  SysFreeString(v4);
  SysFreeString(v43);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( *(_QWORD *)&pvarg.vt )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
  return (unsigned int)psz;
}

```

## disassembly

```asm
0x14003db44  mov     rax, rsp
0x14003db47  mov     [rax+18h], r8d
0x14003db4b  mov     [rax+10h], rdx
0x14003db4f  mov     [rax+8], rcx
0x14003db53  push    rbp
0x14003db54  push    rbx
0x14003db55  push    rsi
0x14003db56  push    rdi
0x14003db57  push    r12
0x14003db59  push    r13
0x14003db5b  push    r14
0x14003db5d  push    r15
0x14003db5f  lea     rbp, [rax-108h]
0x14003db66  sub     rsp, 1C8h
0x14003db6d  xor     esi, esi
0x14003db6f  mov     qword ptr [rsp+200h+pvarg], rsi
0x14003db74  mov     [rsp+200h+var_1B0], rsi
0x14003db79  mov     [rbp+100h+var_130], rsi
0x14003db7d  mov     [rbp+100h+var_138], rsi
0x14003db81  mov     [rbp+100h+var_90], rsi
0x14003db85  mov     [rbp+100h+var_140], rsi
0x14003db89  mov     [rbp+100h+var_A0], rsi
0x14003db8d  mov     [rbp+100h+var_148], rsi
0x14003db91  mov     [rbp+100h+var_150], rsi
0x14003db95  mov     [rbp+100h+var_158], rsi
0x14003db99  mov     [rbp+100h+var_160], rsi
0x14003db9d  mov     [rbp+100h+var_168], rsi
0x14003dba1  mov     [rbp+100h+var_C0], rsi
0x14003dba5  mov     [rbp+100h+var_C8], rsi
0x14003dba9  mov     [rbp+100h+var_80], rsi
0x14003dbb0  mov     [rbp+100h+var_D0], rsi
0x14003dbb4  mov     [rbp+100h+var_88], rsi
0x14003dbb8  mov     [rbp+100h+var_D8], rsi
0x14003dbbc  mov     [rbp+100h+var_E0], rsi
0x14003dbc0  mov     [rbp+100h+var_A8], rsi
0x14003dbc4  mov     [rbp+100h+var_B0], rsi
0x14003dbc8  mov     [rbp+100h+var_78], rsi
0x14003dbcf  lea     rcx, [rsp+200h+pvarg+8]; pvarg
0x14003dbd4  call    cs:__imp_VariantInit
0x14003dbdb  nop     dword ptr [rax+rax+00h]
0x14003dbe0  nop
0x14003dbe1  mov     [rbp+100h+var_E8], rsi
0x14003dbe5  mov     edi, esi
0x14003dbe7  mov     [rbp+100h+var_100], rsi
0x14003dbeb  mov     ebx, esi
0x14003dbed  mov     [rbp+100h+var_108], rbx
0x14003dbf1  mov     [rbp+100h+var_70], rsi
0x14003dbf8  mov     r12d, esi
0x14003dbfb  mov     [rbp+100h+var_110], rsi
0x14003dbff  mov     r13d, esi
0x14003dc02  mov     [rbp+100h+var_118], rsi
0x14003dc06  mov     [rbp+100h+var_68], rsi
0x14003dc0d  mov     r14d, esi
0x14003dc10  mov     [rbp+100h+var_128], rsi
0x14003dc14  mov     r15d, esi
0x14003dc17  mov     [rbp+100h+var_120], rsi
0x14003dc1b  mov     [rbp+100h+bstrString], rsi
0x14003dc1f  mov     [rbp+100h+var_F8], rsi
0x14003dc23  or      eax, 0FFFFFFFFh
0x14003dc26  mov     word ptr [rbp+100h+arg_10], ax
0x14003dc2d  mov     rcx, [rsp+200h+var_1B0]
0x14003dc32  xor     eax, eax
0x14003dc34  test    rcx, rcx
0x14003dc37  jz      short loc_14003DC4C
0x14003dc39  mov     rax, [rcx]
0x14003dc3c  mov     rax, [rax+10h]
0x14003dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dc45  xor     eax, eax
0x14003dc47  mov     [rsp+200h+var_1B0], rax
0x14003dc4c  mov     [rbp+100h+var_60], rax
0x14003dc53  mov     [rbp+100h+var_48], rax
0x14003dc5a  mov     [rbp+100h+var_58], rax
0x14003dc61  mov     [rbp+100h+var_50], rax
0x14003dc68  lea     rax, [rsp+200h+pvarg]
0x14003dc6d  mov     [rsp+200h+ppv], rax; ppv
0x14003dc72  lea     r9, IID_IXMLDOMDocument; riid
0x14003dc79  xor     edx, edx; pUnkOuter
0x14003dc7b  lea     r8d, [rdx+1]; dwClsContext
0x14003dc7f  lea     rcx, CLSID_DOMDocument60; rclsid
0x14003dc86  call    cs:__imp_CoCreateInstance
0x14003dc8d  nop     dword ptr [rax+rax+00h]
0x14003dc92  mov     dword ptr [rbp+100h+psz], eax
0x14003dc98  test    eax, eax
0x14003dc9a  jns     short loc_14003DCCA
0x14003dc9c  mov     r9d, 0C31h; unsigned int
0x14003dca2  mov     [rsp+200h+var_1D8], eax; unsigned int
0x14003dca6  lea     rax, aCraticketSaver; "CRATicket::SaveRATicket"
0x14003dcad  mov     [rsp+200h+ppv], rax; unsigned __int16 *
0x14003dcb2  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003dcb9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003dcc0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003dcc5  jmp     loc_14003E6DE
0x14003dcca  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003dccf  mov     rax, [rcx]
0x14003dcd2  mov     edx, 0Bh
0x14003dcd7  mov     word ptr [rbp+100h+var_180], dx
0x14003dcdb  or      edx, 0FFFFFFFFh
0x14003dcde  mov     word ptr [rbp+100h+var_180+8], dx
0x14003dce2  movups  xmm0, xmmword ptr [rbp+100h+var_180]
0x14003dce6  movaps  [rsp+200h+var_1A8+8], xmm0
0x14003dceb  movsd   xmm1, qword ptr [rbp+100h+var_180+10h]
0x14003dcf0  movsd   [rsp+200h+var_190], xmm1
0x14003dcf6  lea     r8, [rsp+200h+var_1A8+8]
0x14003dcfb  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x14003dd02  mov     rax, [rax+280h]
0x14003dd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd0e  mov     dword ptr [rbp+100h+psz], eax
0x14003dd14  lea     rcx, [rbp+100h+var_180]; pvarg
0x14003dd18  call    cs:__imp_VariantClear
0x14003dd1f  nop     dword ptr [rax+rax+00h]
0x14003dd24  mov     eax, dword ptr [rbp+100h+psz]
0x14003dd2a  test    eax, eax
0x14003dd2c  jns     short loc_14003DD39
0x14003dd2e  mov     r9d, 0C33h
0x14003dd34  jmp     loc_14003DCA2
0x14003dd39  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003dd3e  mov     rax, [rcx]
0x14003dd41  mov     edx, 0Bh
0x14003dd46  mov     word ptr [rbp+100h+var_180], dx
0x14003dd4a  xor     edx, edx
0x14003dd4c  mov     word ptr [rbp+100h+var_180+8], dx
0x14003dd50  movups  xmm0, xmmword ptr [rbp+100h+var_180]
0x14003dd54  movaps  [rsp+200h+var_1A8+8], xmm0
0x14003dd59  movsd   xmm1, qword ptr [rbp+100h+var_180+10h]
0x14003dd5e  movsd   [rsp+200h+var_190], xmm1
0x14003dd64  lea     r8, [rsp+200h+var_1A8+8]
0x14003dd69  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14003dd70  mov     rax, [rax+280h]
0x14003dd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd7c  mov     dword ptr [rbp+100h+psz], eax
0x14003dd82  lea     rcx, [rbp+100h+var_180]; pvarg
0x14003dd86  call    cs:__imp_VariantClear
0x14003dd8d  nop     dword ptr [rax+rax+00h]
0x14003dd92  mov     eax, dword ptr [rbp+100h+psz]
0x14003dd98  test    eax, eax
0x14003dd9a  jns     short loc_14003DDA7
0x14003dd9c  mov     r9d, 0C34h
0x14003dda2  jmp     loc_14003DCA2
0x14003dda7  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003ddac  mov     rax, [rcx]
0x14003ddaf  mov     edx, 0Bh
0x14003ddb4  mov     word ptr [rbp+100h+var_180], dx
0x14003ddb8  xor     edx, edx
0x14003ddba  mov     word ptr [rbp+100h+var_180+8], dx
0x14003ddbe  movups  xmm0, xmmword ptr [rbp+100h+var_180]
0x14003ddc2  movaps  [rsp+200h+var_1A8+8], xmm0
0x14003ddc7  movsd   xmm1, qword ptr [rbp+100h+var_180+10h]
0x14003ddcc  movsd   [rsp+200h+var_190], xmm1
0x14003ddd2  lea     r8, [rsp+200h+var_1A8+8]
0x14003ddd7  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x14003ddde  mov     rax, [rax+280h]
0x14003dde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ddea  mov     dword ptr [rbp+100h+psz], eax
0x14003ddf0  lea     rcx, [rbp+100h+var_180]; pvarg
0x14003ddf4  call    cs:__imp_VariantClear
0x14003ddfb  nop     dword ptr [rax+rax+00h]
0x14003de00  mov     eax, dword ptr [rbp+100h+psz]
0x14003de06  test    eax, eax
0x14003de08  jns     short loc_14003DE15
0x14003de0a  mov     r9d, 0C35h
0x14003de10  jmp     loc_14003DCA2
0x14003de15  lea     rdx, aXmlVersion10Up; "<?xml version=\"1.0\" ?><UPLOADINFO TYP"...
0x14003de1c  lea     rcx, [rbp+100h+var_F8]; this
0x14003de20  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003de25  mov     dword ptr [rbp+100h+psz], eax
0x14003de2b  mov     rsi, [rbp+100h+var_F8]
0x14003de2f  test    eax, eax
0x14003de31  js      loc_14003E6DE
0x14003de37  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003de3c  mov     rax, [rcx]
0x14003de3f  lea     r8, [rbp+100h+arg_10]
0x14003de46  mov     rdx, rsi
0x14003de49  mov     rax, [rax+208h]
0x14003de50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003de55  mov     dword ptr [rbp+100h+psz], eax
0x14003de5b  test    eax, eax
0x14003de5d  js      loc_14003E6DE
0x14003de63  lea     rdx, aUploadinfo; "UPLOADINFO"
0x14003de6a  lea     rcx, [rbp+100h+var_100]; this
0x14003de6e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003de73  mov     dword ptr [rbp+100h+psz], eax
0x14003de79  mov     rdi, [rbp+100h+var_100]
0x14003de7d  test    eax, eax
0x14003de7f  js      loc_14003E6DE
0x14003de85  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003de8a  mov     rax, [rcx]
0x14003de8d  lea     r8, [rbp+100h+var_168]
0x14003de91  mov     rdx, rdi
0x14003de94  mov     rax, [rax+128h]
0x14003de9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dea0  test    eax, eax
0x14003dea2  js      loc_14003E6D4
0x14003dea8  cmp     [rbp+100h+var_168], 0
0x14003dead  jz      loc_14003E6D4
0x14003deb3  lea     rdx, aUploaddata; "UPLOADDATA"
0x14003deba  lea     rcx, [rbp+100h+var_E8]; this
0x14003debe  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003dec3  mov     dword ptr [rbp+100h+psz], eax
0x14003dec9  test    eax, eax
0x14003decb  js      loc_14003E6DE
0x14003ded1  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003ded6  mov     rax, [rcx]
0x14003ded9  mov     edx, 3
0x14003dede  mov     word ptr [rbp+100h+var_180], dx
0x14003dee2  mov     dword ptr [rbp+100h+var_180+8], 1
0x14003dee9  movups  xmm0, xmmword ptr [rbp+100h+var_180]
0x14003deed  movaps  [rsp+200h+var_1A8+8], xmm0
0x14003def2  movsd   xmm1, qword ptr [rbp+100h+var_180+10h]
0x14003def7  movsd   [rsp+200h+var_190], xmm1
0x14003defd  lea     rdx, [rbp+100h+var_160]
0x14003df01  mov     [rsp+200h+ppv], rdx
0x14003df06  xor     r9d, r9d
0x14003df09  mov     r8, [rbp+100h+var_E8]
0x14003df0d  lea     rdx, [rsp+200h+var_1A8+8]
0x14003df12  mov     rax, [rax+1C0h]
0x14003df19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df1e  mov     dword ptr [rbp+100h+psz], eax
0x14003df24  lea     rcx, [rbp+100h+var_180]; pvarg
0x14003df28  call    cs:__imp_VariantClear
0x14003df2f  nop     dword ptr [rax+rax+00h]
0x14003df34  cmp     dword ptr [rbp+100h+psz], 0
0x14003df3b  jl      loc_14003E6DE
0x14003df41  mov     rcx, [rbp+100h+var_160]
0x14003df45  mov     rax, [rcx]
0x14003df48  lea     rdx, [rsp+200h+var_1B0]
0x14003df4d  mov     rax, [rax+88h]
0x14003df54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df59  mov     dword ptr [rbp+100h+psz], eax
0x14003df5f  test    eax, eax
0x14003df61  js      loc_14003E6DE
0x14003df67  lea     rdx, aUsername; "USERNAME"
0x14003df6e  lea     rcx, [rbp+100h+var_108]; this
0x14003df72  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003df77  mov     dword ptr [rbp+100h+psz], eax
0x14003df7d  mov     rbx, [rbp+100h+var_108]
0x14003df81  test    eax, eax
0x14003df83  js      loc_14003E6DE
0x14003df89  mov     rcx, qword ptr [rsp+200h+pvarg]
0x14003df8e  mov     rax, [rcx]
0x14003df91  lea     r8, [rbp+100h+var_130]
0x14003df95  mov     rdx, rbx
0x14003df98  mov     rax, [rax+1A8h]
0x14003df9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dfa4  mov     dword ptr [rbp+100h+psz], eax
0x14003dfaa  test    eax, eax
0x14003dfac  js      loc_14003E6DE
0x14003dfb2  mov     rax, [rbp+100h+arg_0]
0x14003dfb9  mov     rax, [rax]
0x14003dfbc  mov     [rbp+100h+psz], rax
0x14003dfc3  lea     rcx, [rsp+200h+pvarg+8]; pvarg
0x14003dfc8  call    cs:__imp_VariantClear
0x14003dfcf  nop     dword ptr [rax+rax+00h]
0x14003dfd4  mov     eax, 8
0x14003dfd9  mov     word ptr [rsp+200h+pvarg+8], ax
0x14003dfde  mov     rcx, [rbp+100h+psz]; psz
0x14003dfe5  call    cs:__imp_SysAllocString
0x14003dfec  nop     dword ptr [rax+rax+00h]
0x14003dff1  mov     dword ptr [rsp+200h+pvarg+10h], eax
0x14003dff5  mov     rcx, rax
0x14003dff8  sar     rcx, 20h
0x14003dffc  mov     dword ptr [rsp+200h+pvarg+14h], ecx
0x14003e000  test    rax, rax
0x14003e003  jnz     short loc_14003E012
0x14003e005  cmp     [rbp+100h+psz], rax
0x14003e00c  jnz     loc_14003E9E3
0x14003e012  mov     rcx, [rbp+100h+var_130]
0x14003e016  movups  xmm0, xmmword ptr [rsp+200h+pvarg+8]
0x14003e01b  movaps  [rsp+200h+var_1A8+8], xmm0
0x14003e020  movsd   xmm1, [rsp+200h+var_1B8]
0x14003e026  movsd   [rsp+200h+var_190], xmm1
0x14003e02c  mov     rax, [rcx]
0x14003e02f  lea     rdx, [rsp+200h+var_1A8+8]
0x14003e034  mov     rax, [rax+48h]
0x14003e038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e03d  mov     dword ptr [rbp+100h+psz], eax
0x14003e043  test    eax, eax
0x14003e045  js      loc_14003E6DE
0x14003e04b  mov     rcx, [rsp+200h+var_1B0]
0x14003e050  mov     rax, [rcx]
0x14003e053  lea     r8, [rbp+100h+var_C0]
0x14003e057  mov     rdx, [rbp+100h+var_130]
0x14003e05b  mov     rax, [rax+40h]
0x14003e05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e064  mov     dword ptr [rbp+100h+psz], eax
0x14003e06a  test    eax, eax
0x14003e06c  js      loc_14003E6DE
0x14003e072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003e079  mov     ecx, 30h ; '0'; unsigned __int64
0x14003e07e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e083  mov     [rbp+100h+var_B8], rax
0x14003e087  xor     ecx, ecx
0x14003e089  test    rax, rax
0x14003e08c  jz      loc_14003E6C8
0x14003e092  mov     [rax], rcx
0x14003e095  mov     [rax+8], rcx
0x14003e099  mov     [rax+10h], rcx
0x14003e09d  mov     [rax+18h], rcx
0x14003e0a1  mov     [rax+20h], rcx
0x14003e0a5  mov     [rax+28h], rcx
0x14003e0a9  mov     rdx, [rbp+100h+arg_0]
  ... truncated ...
```
