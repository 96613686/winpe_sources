# CRdlsSqlTableKeyPack::PrepareUpdateQueryStatement(IOdbcExecutionContext *,void *,ulong)

- ea: `0x180090330`
- end: `0x180090f37`
- name: `?PrepareUpdateQueryStatement@CRdlsSqlTableKeyPack@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXK@Z`
- size: `3079`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableKeyPack *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x180086778`
- `0x18008f650`
- `0x180090330`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180090ed7`
- `msvcrt!wprintf_s` at `0x180090eec`
- `msvcrt!wprintf_s` at `0x180090ed7`
- `msvcrt!wprintf_s` at `0x180090eec`
- `OLEAUT32!__imp_SysFreeString` at `0x18009036e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009036e`

## string_xrefs

- `0x180090ed0`: `"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement"`
- `0x18009037e`: `UPDATE [Rdls].[LicensedPack] SET `
- `0x1800904f9`: `"pOdbcExecContext->BindNTSParameter, PrepareUpdateQueryStatement"`
- `0x1800908fb`: `, [CompanyName] = ? `
- `0x18009090e`: `[CompanyName] = ? `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CRdlsSqlTableKeyPack::PrepareUpdateQueryStatement(
        CRdlsSqlTableKeyPack *this,
        struct IOdbcExecutionContext *a2,
        char *a3,
        int a4)
{
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // edi
  __int64 v13; // r8
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  const unsigned __int16 *v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r8
  const unsigned __int16 *v26; // rdx
  __int64 v27; // r8
  const unsigned __int16 *v28; // rdx
  __int64 v29; // r8
  const unsigned __int16 *v30; // rdx
  __int64 v31; // r8
  const unsigned __int16 *v32; // rdx
  __int64 v33; // r8
  const unsigned __int16 *v34; // rdx
  __int64 v35; // r8
  const unsigned __int16 *v36; // rdx
  __int64 v37; // r8
  const unsigned __int16 *v38; // rdx
  __int64 v39; // r8
  const unsigned __int16 *v40; // rdx
  __int64 v41; // r8
  const unsigned __int16 *v42; // rdx
  __int64 v43; // r8
  const unsigned __int16 *v44; // rdx
  __int64 v45; // r8
  const unsigned __int16 *v46; // rdx
  __int64 v47; // r8
  const unsigned __int16 *v48; // rdx
  __int64 v49; // r8
  const unsigned __int16 *v50; // rdx
  __int64 v51; // r8
  const unsigned __int16 *v52; // rdx
  __int64 v53; // r8
  const unsigned __int16 *v54; // rdx
  __int64 v55; // r8
  const unsigned __int16 *v56; // rdx
  __int64 v57; // rbx
  __int64 v59; // [rsp+80h] [rbp+40h] BYREF

  v59 = 0;
  v8 = 0;
  if ( !a4 )
    goto LABEL_213;
  SysFreeString(0);
  v59 = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( aUpdateRdlsLice[v10] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, L"UPDATE [Rdls].[LicensedPack] SET ", v10);
  CRdlsSqlTableKeyPack::InitDataSizes(this, a3);
  if ( (a4 & 0x40000) != 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( aActivationdate[v11] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, L"[ActivationDate] = ? ", v11);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 24,
            (char *)this + 104);
    if ( v12 )
      goto LABEL_209;
    v8 = 1;
  }
  if ( (a4 & 2) != 0 )
  {
    v13 = -1;
    if ( v8 )
    {
      v14 = L", [AgreementType] = ? ";
      do
        ++v13;
      while ( aAgreementtype_0[v13] );
    }
    else
    {
      v14 = L"[AgreementType] = ? ";
      do
        ++v13;
      while ( aAgreementtype_2[v13] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v14, v13);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3 + 2100,
            (char *)this + 16);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 4) != 0 )
  {
    v15 = -1;
    if ( v8 )
    {
      v16 = L", [ProductID] = ? ";
      do
        ++v15;
      while ( aProductid_0[v15] );
    }
    else
    {
      v16 = L"[ProductID] = ? ";
      do
        ++v15;
      while ( aProductid_2[v15] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v16, v15);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 2614);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 8) != 0 )
  {
    v17 = -1;
    if ( v8 )
    {
      v18 = L", [ProductMajorVersion] = ? ";
      do
        ++v17;
      while ( aProductmajorve_0[v17] );
    }
    else
    {
      v18 = L"[ProductMajorVersion] = ? ";
      do
        ++v17;
      while ( aProductmajorve[v17] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v18, v17);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            10,
            1,
            0,
            a3 + 3126,
            (char *)this + 24);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x10) != 0 )
  {
    v19 = -1;
    if ( v8 )
    {
      v20 = L", [ProductMinorVersion] = ? ";
      do
        ++v19;
      while ( aProductminorve_0[v19] );
    }
    else
    {
      v20 = L"[ProductMinorVersion] = ? ";
      do
        ++v19;
      while ( aProductminorve[v19] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v20, v19);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            10,
            1,
            0,
            a3 + 3128,
            (char *)this + 32);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x20) != 0 )
  {
    v21 = -1;
    if ( v8 )
    {
      v22 = L", [PlatformType] = ? ";
      do
        ++v21;
      while ( aPlatformtype_0[v21] );
    }
    else
    {
      v22 = L"[PlatformType] = ? ";
      do
        ++v21;
      while ( aPlatformtype[v21] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v22, v21);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 3132,
            (char *)this + 40);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x40) != 0 )
  {
    v23 = -1;
    if ( v8 )
    {
      v24 = L", [LicenseType] = ? ";
      do
        ++v23;
      while ( aLicensetype_0[v23] );
    }
    else
    {
      v24 = L"[LicenseType] = ? ";
      do
        ++v23;
      while ( aLicensetype_1[v23] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v24, v23);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3 + 3136,
            (char *)this + 48);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x100) != 0 )
  {
    v25 = -1;
    if ( v8 )
    {
      v26 = L", [ChannelOfPurchase] = ? ";
      do
        ++v25;
      while ( aChannelofpurch[v25] );
    }
    else
    {
      v26 = L"[ChannelOfPurchase] = ? ";
      do
        ++v25;
      while ( aChannelofpurch_1[v25] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v26, v25);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3 + 3137,
            (char *)this + 56);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x200) != 0 )
  {
    v27 = -1;
    if ( v8 )
    {
      v28 = L", [BeginSerialNumber] = ? ";
      do
        ++v27;
      while ( aBeginserialnum_1[v27] );
    }
    else
    {
      v28 = L"[BeginSerialNumber] = ? ";
      do
        ++v27;
      while ( aBeginserialnum[v27] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v28, v27);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 3138);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 0x400) != 0 )
  {
    v29 = -1;
    if ( v8 )
    {
      v30 = L", [TotalLicenses] = ? ";
      do
        ++v29;
      while ( aTotallicenses_0[v29] );
    }
    else
    {
      v30 = L"[TotalLicenses] = ? ";
      do
        ++v29;
      while ( aTotallicenses[v29] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v30, v29);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 3652,
            (char *)this + 64);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x800) != 0 )
  {
    v31 = -1;
    if ( v8 )
    {
      v32 = L", [ProductFlag] = ? ";
      do
        ++v31;
      while ( aProductflag_0[v31] );
    }
    else
    {
      v32 = L"[ProductFlag] = ? ";
      do
        ++v31;
      while ( aProductflag_1[v31] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v32, v31);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 3656,
            (char *)this + 72);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x1000) != 0 )
  {
    v33 = -1;
    if ( v8 )
    {
      v34 = L", [CompanyName] = ? ";
      do
        ++v33;
      while ( aCompanyname_1[v33] );
    }
    else
    {
      v34 = L"[CompanyName] = ? ";
      do
        ++v33;
      while ( aCompanyname_0[v33] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v34, v33);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 2102);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 0x400000) != 0 )
  {
    v35 = -1;
    if ( v8 )
    {
      v36 = L", [KeyPackAttribute] = ? ";
      do
        ++v35;
      while ( aKeypackattribu_0[v35] );
    }
    else
    {
      v36 = L"[KeyPackAttribute] = ? ";
      do
        ++v35;
      while ( aKeypackattribu[v35] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v36, v35);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 16,
            (char *)this + 80);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 1) != 0 )
  {
    v37 = -1;
    if ( v8 )
    {
      v38 = L", [LPID] = ? ";
      do
        ++v37;
      while ( aLpid_0[v37] );
    }
    else
    {
      v38 = L"[LPID] = ? ";
      do
        ++v37;
      while ( aLpid_3[v37] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v38, v37);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 1588);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 0x20000) != 0 )
  {
    v39 = -1;
    if ( v8 )
    {
      v40 = L", [KeyPackStatus] = ? ";
      do
        ++v39;
      while ( aKeypackstatus_0[v39] );
    }
    else
    {
      v40 = L"[KeyPackStatus] = ? ";
      do
        ++v39;
      while ( aKeypackstatus_1[v39] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v40, v39);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            11,
            4,
            0,
            a3 + 36,
            (char *)this + 88);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x100000) != 0 )
  {
    v41 = -1;
    if ( v8 )
    {
      v42 = L", [NumberLicenses] = ? ";
      do
        ++v41;
      while ( aNumberlicenses[v41] );
    }
    else
    {
      v42 = L"[NumberLicenses] = ? ";
      do
        ++v41;
      while ( aNumberlicenses_0[v41] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v42, v41);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 32,
            (char *)this + 96);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x80000) != 0 )
  {
    v43 = -1;
    if ( v8 )
    {
      v44 = L", [ExpirationDate] = ? ";
      do
        ++v43;
      while ( aExpirationdate_0[v43] );
    }
    else
    {
      v44 = L"[ExpirationDate] = ? ";
      do
        ++v43;
      while ( aExpirationdate[v43] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v44, v43);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 28,
            (char *)this + 112);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x1000000) != 0 )
  {
    v45 = -1;
    if ( v8 )
    {
      v46 = L", [TLSSetupId] = ? ";
      do
        ++v45;
      while ( aTlssetupid[v45] );
    }
    else
    {
      v46 = L"[TLSSetupId] = ? ";
      do
        ++v45;
      while ( aTlssetupid_0[v45] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v46, v45);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 52);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 0x2000000) != 0 )
  {
    v47 = -1;
    if ( v8 )
    {
      v48 = L", [DomainName] = ? ";
      do
        ++v47;
      while ( aDomainname_0[v47] );
    }
    else
    {
      v48 = L"[DomainName] = ? ";
      do
        ++v47;
      while ( aDomainname[v47] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v48, v47);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 564);
    if ( v12 )
      goto LABEL_26;
    ++v8;
  }
  if ( (a4 & 0x4000000) == 0 )
    goto LABEL_181;
  v49 = -1;
  if ( v8 )
  {
    v50 = L", [ServerName] = ? ";
    do
      ++v49;
    while ( aServername_0[v49] );
  }
  else
  {
    v50 = L"[ServerName] = ? ";
    do
      ++v49;
    while ( aServername_1[v49] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v50, v49);
  v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
          a2,
          0,
          0,
          256,
          a3 + 1076);
  if ( v12 )
  {
LABEL_26:
    wprintf_s(L"\"pOdbcExecContext->BindNTSParameter, PrepareUpdateQueryStatement\"");
LABEL_210:
    wprintf_s(L" 0x%x \n", (unsigned int)v12);
    goto LABEL_211;
  }
  ++v8;
LABEL_181:
  if ( (a4 & 0x8000000) != 0 )
  {
    v51 = -1;
    if ( v8 )
    {
      v52 = L", [NextSerialNumber] = ? ";
      do
        ++v51;
      while ( aNextserialnumb_1[v51] );
    }
    else
    {
      v52 = L"[NextSerialNumber] = ? ";
      do
        ++v51;
      while ( aNextserialnumb[v51] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v52, v51);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            2,
            2,
            0,
            a3 + 20,
            (char *)this + 120);
    if ( v12 )
      goto LABEL_209;
    ++v8;
  }
  if ( (a4 & 0x10000000) == 0 )
    goto LABEL_199;
  v53 = -1;
  if ( v8 )
  {
    v54 = L", [EntryStatus] = ? ";
    do
      ++v53;
    while ( aEntrystatus_0[v53] );
  }
  else
  {
    v54 = L"[EntryStatus] = ? ";
    do
      ++v53;
    while ( aEntrystatus[v53] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v54, v53);
  v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
          a2,
          0,
          11,
          4,
          0,
          a3,
          (char *)this + 128);
  if ( v12 )
  {
LABEL_209:
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement\"");
    goto LABEL_210;
  }
  ++v8;
LABEL_199:
  if ( (a4 & 0x200000) != 0 )
  {
    v55 = -1;
    if ( v8 )
    {
      v56 = L", [LastModifyTime] = ? ";
      do
        ++v55;
      while ( aLastmodifytime_2[v55] );
    }
    else
    {
      v56 = L"[LastModifyTime] = ? ";
      do
        ++v55;
      while ( aLastmodifytime_1[v55] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, v56, v55);
    v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            12,
            5,
            0,
            a3 + 8,
            (char *)this + 136);
    if ( v12 )
      goto LABEL_209;
  }
  do
    ++v9;
  while ( aWhereInternalk[v9] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v59, L" WHERE [InternalKeyPackId] = ? ", v9);
  v12 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
          a2,
          0,
          2,
          2,
          0,
          a3 + 4,
          (char *)this + 8);
  if ( v12 )
    goto LABEL_209;
LABEL_211:
  if ( v12 < 0 )
  {
LABEL_213:
    v57 = 0;
    goto LABEL_214;
  }
  v57 = v59;
  v59 = 0;
LABEL_214:
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v59);
  return (unsigned __int16 *)v57;
}

```

## disassembly

```asm
0x180090330  mov     [rsp-28h+arg_0], rbx
0x180090335  mov     [rsp-28h+arg_8], rsi
0x18009033a  mov     [rsp-28h+arg_18], rdi
0x18009033f  push    rbp
0x180090340  push    r12
0x180090342  push    r13
0x180090344  push    r14
0x180090346  push    r15
0x180090348  mov     rbp, rsp
0x18009034b  sub     rsp, 40h
0x18009034f  mov     r14d, r9d
0x180090352  mov     r13, r8
0x180090355  mov     r15, rdx
0x180090358  mov     r12, rcx
0x18009035b  xor     edi, edi
0x18009035d  mov     [rbp+arg_10], rdi
0x180090361  mov     ebx, edi
0x180090363  test    r9d, r9d
0x180090366  jz      loc_180090F09
0x18009036c  xor     ecx, ecx; bstrString
0x18009036e  call    cs:__imp_SysFreeString
0x180090375  nop     dword ptr [rax+rax+00h]
0x18009037a  mov     [rbp+arg_10], rdi
0x18009037e  lea     rdx, aUpdateRdlsLice; "UPDATE [Rdls].[LicensedPack] SET "
0x180090385  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180090389  mov     r8, rsi
0x18009038c  inc     r8; int
0x18009038f  cmp     [rdx+r8*2], di
0x180090394  jnz     short loc_18009038C
0x180090396  lea     rcx, [rbp+arg_10]; this
0x18009039a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009039f  mov     rdx, r13; void *
0x1800903a2  mov     rcx, r12; this
0x1800903a5  call    ?InitDataSizes@CRdlsSqlTableKeyPack@@AEAAXPEAX@Z; CRdlsSqlTableKeyPack::InitDataSizes(void *)
0x1800903aa  bt      r14d, 12h
0x1800903af  jnb     short loc_180090412
0x1800903b1  lea     rdx, aActivationdate; "[ActivationDate] = ? "
0x1800903b8  mov     r8, rsi
0x1800903bb  inc     r8; int
0x1800903be  cmp     [rdx+r8*2], di
0x1800903c3  jnz     short loc_1800903BB
0x1800903c5  lea     rcx, [rbp+arg_10]; this
0x1800903c9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800903ce  mov     rax, [r15]
0x1800903d1  lea     rcx, [r12+68h]
0x1800903d6  lea     rdx, [r13+18h]
0x1800903da  mov     [rsp+40h+var_10], rcx
0x1800903df  mov     [rsp+40h+var_18], rdx
0x1800903e4  mov     dword ptr [rsp+40h+var_20], edi
0x1800903e8  mov     ecx, 2
0x1800903ed  mov     r9d, ecx
0x1800903f0  mov     r8d, ecx
0x1800903f3  xor     edx, edx
0x1800903f5  mov     rcx, r15
0x1800903f8  mov     rax, [rax+28h]
0x1800903fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090401  mov     edi, eax
0x180090403  xor     eax, eax
0x180090405  test    edi, edi
0x180090407  jnz     loc_180090ED0
0x18009040d  lea     ebx, [rax+1]
0x180090410  jmp     short loc_180090414
0x180090412  xor     eax, eax
0x180090414  test    r14b, 2
0x180090418  jz      short loc_180090491
0x18009041a  mov     r8, rsi
0x18009041d  test    ebx, ebx
0x18009041f  jz      short loc_180090434
0x180090421  lea     rdx, aAgreementtype_0; ", [AgreementType] = ? "
0x180090428  inc     r8
0x18009042b  cmp     [rdx+r8*2], ax
0x180090430  jnz     short loc_180090428
0x180090432  jmp     short loc_180090445
0x180090434  lea     rdx, aAgreementtype_2; "[AgreementType] = ? "
0x18009043b  inc     r8; int
0x18009043e  cmp     [rdx+r8*2], ax
0x180090443  jnz     short loc_18009043B
0x180090445  lea     rcx, [rbp+arg_10]; this
0x180090449  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009044e  mov     rax, [r15]
0x180090451  lea     rcx, [r12+10h]
0x180090456  lea     rdx, [r13+834h]
0x18009045d  mov     [rsp+40h+var_10], rcx
0x180090462  mov     [rsp+40h+var_18], rdx
0x180090467  xor     ecx, ecx
0x180090469  mov     dword ptr [rsp+40h+var_20], ecx
0x18009046d  xor     edx, edx
0x18009046f  lea     r9d, [rcx+4]
0x180090473  lea     r8d, [rcx+0Bh]
0x180090477  mov     rcx, r15
0x18009047a  mov     rax, [rax+28h]
0x18009047e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090483  mov     edi, eax
0x180090485  xor     eax, eax
0x180090487  test    edi, edi
0x180090489  jnz     loc_180090ED0
0x18009048f  inc     ebx
0x180090491  test    r14b, 4
0x180090495  jz      short loc_180090507
0x180090497  mov     r8, rsi
0x18009049a  test    ebx, ebx
0x18009049c  jz      short loc_1800904B1
0x18009049e  lea     rdx, aProductid_0; ", [ProductID] = ? "
0x1800904a5  inc     r8
0x1800904a8  cmp     [rdx+r8*2], ax
0x1800904ad  jnz     short loc_1800904A5
0x1800904af  jmp     short loc_1800904C2
0x1800904b1  lea     rdx, aProductid_2; "[ProductID] = ? "
0x1800904b8  inc     r8; int
0x1800904bb  cmp     [rdx+r8*2], ax
0x1800904c0  jnz     short loc_1800904B8
0x1800904c2  lea     rcx, [rbp+arg_10]; this
0x1800904c6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800904cb  mov     rax, [r15]
0x1800904ce  lea     rcx, [r13+0A36h]
0x1800904d5  mov     [rsp+40h+var_20], rcx
0x1800904da  mov     r9d, 100h
0x1800904e0  xor     r8d, r8d
0x1800904e3  xor     edx, edx
0x1800904e5  mov     rcx, r15
0x1800904e8  mov     rax, [rax+20h]
0x1800904ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904f1  mov     edi, eax
0x1800904f3  xor     eax, eax
0x1800904f5  test    edi, edi
0x1800904f7  jz      short loc_180090505
0x1800904f9  lea     rcx, aPodbcexecconte_8; "\"pOdbcExecContext->BindNTSParameter, P"...
0x180090500  jmp     loc_180090ED7
0x180090505  inc     ebx
0x180090507  test    r14b, 8
0x18009050b  jz      short loc_180090584
0x18009050d  mov     r8, rsi
0x180090510  test    ebx, ebx
0x180090512  jz      short loc_180090527
0x180090514  lea     rdx, aProductmajorve_0; ", [ProductMajorVersion] = ? "
0x18009051b  inc     r8
0x18009051e  cmp     [rdx+r8*2], ax
0x180090523  jnz     short loc_18009051B
0x180090525  jmp     short loc_180090538
0x180090527  lea     rdx, aProductmajorve; "[ProductMajorVersion] = ? "
0x18009052e  inc     r8; int
0x180090531  cmp     [rdx+r8*2], ax
0x180090536  jnz     short loc_18009052E
0x180090538  lea     rcx, [rbp+arg_10]; this
0x18009053c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180090541  mov     rax, [r15]
0x180090544  lea     rcx, [r12+18h]
0x180090549  lea     rdx, [r13+0C36h]
0x180090550  mov     [rsp+40h+var_10], rcx
0x180090555  mov     [rsp+40h+var_18], rdx
0x18009055a  xor     ecx, ecx
0x18009055c  mov     dword ptr [rsp+40h+var_20], ecx
0x180090560  xor     edx, edx
0x180090562  lea     r9d, [rcx+1]
0x180090566  lea     r8d, [rcx+0Ah]
0x18009056a  mov     rcx, r15
0x18009056d  mov     rax, [rax+28h]
0x180090571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090576  mov     edi, eax
0x180090578  xor     eax, eax
0x18009057a  test    edi, edi
0x18009057c  jnz     loc_180090ED0
0x180090582  inc     ebx
0x180090584  test    r14b, 10h
0x180090588  jz      short loc_180090601
0x18009058a  mov     r8, rsi
0x18009058d  test    ebx, ebx
0x18009058f  jz      short loc_1800905A4
0x180090591  lea     rdx, aProductminorve_0; ", [ProductMinorVersion] = ? "
0x180090598  inc     r8
0x18009059b  cmp     [rdx+r8*2], ax
0x1800905a0  jnz     short loc_180090598
0x1800905a2  jmp     short loc_1800905B5
0x1800905a4  lea     rdx, aProductminorve; "[ProductMinorVersion] = ? "
0x1800905ab  inc     r8; int
0x1800905ae  cmp     [rdx+r8*2], ax
0x1800905b3  jnz     short loc_1800905AB
0x1800905b5  lea     rcx, [rbp+arg_10]; this
0x1800905b9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800905be  mov     rax, [r15]
0x1800905c1  lea     rcx, [r12+20h]
0x1800905c6  lea     rdx, [r13+0C38h]
0x1800905cd  mov     [rsp+40h+var_10], rcx
0x1800905d2  mov     [rsp+40h+var_18], rdx
0x1800905d7  xor     ecx, ecx
0x1800905d9  mov     dword ptr [rsp+40h+var_20], ecx
0x1800905dd  xor     edx, edx
0x1800905df  lea     r9d, [rcx+1]
0x1800905e3  lea     r8d, [rcx+0Ah]
0x1800905e7  mov     rcx, r15
0x1800905ea  mov     rax, [rax+28h]
0x1800905ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905f3  mov     edi, eax
0x1800905f5  xor     eax, eax
0x1800905f7  test    edi, edi
0x1800905f9  jnz     loc_180090ED0
0x1800905ff  inc     ebx
0x180090601  test    r14b, 20h
0x180090605  jz      short loc_180090681
0x180090607  mov     r8, rsi
0x18009060a  test    ebx, ebx
0x18009060c  jz      short loc_180090621
0x18009060e  lea     rdx, aPlatformtype_0; ", [PlatformType] = ? "
0x180090615  inc     r8
0x180090618  cmp     [rdx+r8*2], ax
0x18009061d  jnz     short loc_180090615
0x18009061f  jmp     short loc_180090632
0x180090621  lea     rdx, aPlatformtype; "[PlatformType] = ? "
0x180090628  inc     r8; int
0x18009062b  cmp     [rdx+r8*2], ax
0x180090630  jnz     short loc_180090628
0x180090632  lea     rcx, [rbp+arg_10]; this
0x180090636  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009063b  mov     rax, [r15]
0x18009063e  lea     rcx, [r12+28h]
0x180090643  lea     rdx, [r13+0C3Ch]
0x18009064a  mov     [rsp+40h+var_10], rcx
0x18009064f  mov     [rsp+40h+var_18], rdx
0x180090654  xor     ecx, ecx
0x180090656  mov     dword ptr [rsp+40h+var_20], ecx
0x18009065a  mov     ecx, 2
0x18009065f  mov     r9d, ecx
0x180090662  mov     r8d, ecx
0x180090665  xor     edx, edx
0x180090667  mov     rcx, r15
0x18009066a  mov     rax, [rax+28h]
0x18009066e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090673  mov     edi, eax
0x180090675  xor     eax, eax
0x180090677  test    edi, edi
0x180090679  jnz     loc_180090ED0
0x18009067f  inc     ebx
0x180090681  test    r14b, 40h
0x180090685  jz      short loc_1800906FE
0x180090687  mov     r8, rsi
0x18009068a  test    ebx, ebx
0x18009068c  jz      short loc_1800906A1
0x18009068e  lea     rdx, aLicensetype_0; ", [LicenseType] = ? "
0x180090695  inc     r8
0x180090698  cmp     [rdx+r8*2], ax
0x18009069d  jnz     short loc_180090695
0x18009069f  jmp     short loc_1800906B2
0x1800906a1  lea     rdx, aLicensetype_1; "[LicenseType] = ? "
0x1800906a8  inc     r8; int
0x1800906ab  cmp     [rdx+r8*2], ax
0x1800906b0  jnz     short loc_1800906A8
0x1800906b2  lea     rcx, [rbp+arg_10]; this
0x1800906b6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800906bb  mov     rax, [r15]
0x1800906be  lea     rcx, [r12+30h]
0x1800906c3  lea     rdx, [r13+0C40h]
0x1800906ca  mov     [rsp+40h+var_10], rcx
0x1800906cf  mov     [rsp+40h+var_18], rdx
0x1800906d4  xor     ecx, ecx
0x1800906d6  mov     dword ptr [rsp+40h+var_20], ecx
0x1800906da  xor     edx, edx
0x1800906dc  lea     r9d, [rcx+4]
0x1800906e0  lea     r8d, [rcx+0Bh]
0x1800906e4  mov     rcx, r15
0x1800906e7  mov     rax, [rax+28h]
0x1800906eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906f0  mov     edi, eax
0x1800906f2  xor     eax, eax
0x1800906f4  test    edi, edi
0x1800906f6  jnz     loc_180090ED0
0x1800906fc  inc     ebx
0x1800906fe  bt      r14d, 8
0x180090703  jnb     short loc_18009077C
0x180090705  mov     r8, rsi
0x180090708  test    ebx, ebx
0x18009070a  jz      short loc_18009071F
0x18009070c  lea     rdx, aChannelofpurch; ", [ChannelOfPurchase] = ? "
0x180090713  inc     r8
0x180090716  cmp     [rdx+r8*2], ax
0x18009071b  jnz     short loc_180090713
0x18009071d  jmp     short loc_180090730
0x18009071f  lea     rdx, aChannelofpurch_1; "[ChannelOfPurchase] = ? "
0x180090726  inc     r8; int
0x180090729  cmp     [rdx+r8*2], ax
0x18009072e  jnz     short loc_180090726
0x180090730  lea     rcx, [rbp+arg_10]; this
0x180090734  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180090739  mov     rax, [r15]
0x18009073c  lea     rcx, [r12+38h]
0x180090741  lea     rdx, [r13+0C41h]
0x180090748  mov     [rsp+40h+var_10], rcx
0x18009074d  mov     [rsp+40h+var_18], rdx
0x180090752  xor     ecx, ecx
0x180090754  mov     dword ptr [rsp+40h+var_20], ecx
0x180090758  xor     edx, edx
0x18009075a  lea     r9d, [rcx+4]
0x18009075e  lea     r8d, [rcx+0Bh]
0x180090762  mov     rcx, r15
0x180090765  mov     rax, [rax+28h]
0x180090769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009076e  mov     edi, eax
0x180090770  xor     eax, eax
0x180090772  test    edi, edi
0x180090774  jnz     loc_180090ED0
0x18009077a  inc     ebx
  ... truncated ...
```
