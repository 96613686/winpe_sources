# ComputeLib::Diagnostics::SubmitWerReport

- ea: `0x1800266dc`
- end: `0x180027149`
- name: `ComputeLib::Diagnostics::SubmitWerReport`
- size: `2669`
- prototype: `__int64 __fastcall(PCWSTR pwzValue)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027150`

## callees

- `0x1800067c0`
- `0x1800067e4`
- `0x180009968`
- `0x180009e8c`
- `0x18001587c`
- `0x18001c118`
- `0x18001e220`
- `0x18001ebb4`
- `0x18001f9d8`
- `0x180020df0`
- `0x180021a90`
- `0x180021c4c`
- `0x1800266dc`
- `0x180027310`
- `0x1800285b8`
- `0x1800286e0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026baf`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026d37`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026e08`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026e3e`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026baf`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026d37`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026e08`
- `api-ms-win-core-windowserrorreporting-l1-1-1!WerRegisterCustomMetadata` at `0x180026e3e`
- `wer!WerReportCreate` at `0x1800267ab`
- `wer!WerReportCreate` at `0x1800267ab`
- `wer!WerReportAddFile` at `0x180026dd5`
- `wer!WerReportAddFile` at `0x180026dd5`
- `wer!WerReportSubmit` at `0x180027009`
- `wer!WerReportSubmit` at `0x180027009`
- `wer!WerReportCloseHandle` at `0x18002703e`
- `wer!WerReportCloseHandle` at `0x18002703e`
- `wer!WerReportSetParameter` at `0x1800267fc`
- `wer!WerReportSetParameter` at `0x18002685a`
- `wer!WerReportSetParameter` at `0x1800268b8`
- `wer!WerReportSetParameter` at `0x180026916`
- `wer!WerReportSetParameter` at `0x180026974`
- `wer!WerReportSetParameter` at `0x180026f1e`
- `wer!WerReportSetParameter` at `0x180026f78`
- `wer!WerReportSetParameter` at `0x180026fd3`
- `wer!WerReportSetParameter` at `0x1800267fc`
- `wer!WerReportSetParameter` at `0x18002685a`
- `wer!WerReportSetParameter` at `0x1800268b8`
- `wer!WerReportSetParameter` at `0x180026916`
- `wer!WerReportSetParameter` at `0x180026974`
- `wer!WerReportSetParameter` at `0x180026f1e`
- `wer!WerReportSetParameter` at `0x180026f78`
- `wer!WerReportSetParameter` at `0x180026fd3`

## string_xrefs

- `0x180027126`: `onecore\vm\common\mgmt\inc\VirtualizationSettings.h`
- `0x18002673e`: `onecore\vm\compute\common\compute\Wer.h`
- `0x180026f10`: `ComputeSystemId`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall ComputeLib::Diagnostics::SubmitWerReport(_QWORD *pwzValue)
{
  const WCHAR *v2; // rcx
  HRESULT v3; // eax
  __int64 v4; // rax
  const WCHAR *v5; // r9
  HRESULT v6; // eax
  __int64 v7; // rax
  const WCHAR *v8; // r9
  HRESULT v9; // eax
  __int64 v10; // rax
  const WCHAR *v11; // r9
  HRESULT v12; // eax
  __int64 v13; // rax
  const WCHAR *v14; // r9
  HRESULT v15; // eax
  __int64 v16; // rax
  const WCHAR *v17; // r9
  HRESULT v18; // eax
  Marshal::Details *v19; // rcx
  unsigned int v20; // r14d
  __int64 v21; // rdx
  __int64 v22; // rsi
  PCWSTR v23; // rax
  __int64 v24; // rax
  HRESULT v25; // eax
  unsigned int v26; // r14d
  __int64 v27; // rdx
  __int64 v28; // rsi
  PCWSTR v29; // rax
  PCWSTR *v30; // rdx
  const WCHAR *v31; // rdx
  HRESULT v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  PCWSTR v35; // rdi
  PCWSTR v36; // rsi
  const WCHAR *v37; // rdx
  HRESULT v38; // eax
  PCWSTR v39; // rdx
  HRESULT v40; // eax
  PCWSTR v41; // rdx
  HRESULT v42; // eax
  _QWORD *v43; // rdi
  const WCHAR *v44; // r9
  HRESULT v45; // eax
  const WCHAR *v46; // r9
  HRESULT v47; // eax
  __int64 v48; // rax
  HRESULT v49; // eax
  HRESULT v50; // eax
  HRESULT result; // eax
  int v52; // [rsp+20h] [rbp-A9h]
  int v53; // [rsp+20h] [rbp-A9h]
  const char *v54; // [rsp+30h] [rbp-99h]
  _QWORD v55[2]; // [rsp+40h] [rbp-89h] BYREF
  int v56; // [rsp+50h] [rbp-79h] BYREF
  PCWSTR pwzValuea[2]; // [rsp+58h] [rbp-71h] BYREF
  __int64 v58; // [rsp+68h] [rbp-61h]
  unsigned __int64 v59; // [rsp+70h] [rbp-59h]
  HREPORT phReportHandle; // [rsp+78h] [rbp-51h] BYREF
  PCWSTR pwzPath[2]; // [rsp+80h] [rbp-49h] BYREF
  const WCHAR *v62; // [rsp+90h] [rbp-39h]
  __int64 v63; // [rsp+98h] [rbp-31h] BYREF
  PCWSTR value[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-19h]
  unsigned __int64 v66; // [rsp+B8h] [rbp-11h]
  _BYTE v67[6]; // [rsp+CAh] [rbp+1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v56 = 0;
  v55[0] = &v56;
  v55[1] = pwzValue;
  LOBYTE(v52) = pwzValue[2] == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
    (const char *)0x8037010DLL,
    v52,
    (bool)"System Id of crash report is required",
    v54);
  if ( (unsigned __int64)((__int64)(pwzValue[39] - pwzValue[38]) >> 3) < 5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)0x8037010DLL,
      v53);
  if ( *((_DWORD *)pwzValue + 116) )
  {
    v2 = L"VirtualFirmwareCrashDump";
  }
  else
  {
    v2 = L"ContainerCrashDump";
    if ( v56 )
      v2 = L"VirtualMachineCrashDump";
  }
  phReportHandle = 0;
  v3 = WerReportCreate(v2, WerReportCritical, 0, &phReportHandle);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v3,
      v53);
  v4 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v67, *(_QWORD *)pwzValue[38]);
  std::wstring::wstring(pwzValuea, v4, v67);
  v5 = (const WCHAR *)pwzValuea;
  if ( v59 > 7 )
    v5 = pwzValuea[0];
  v6 = WerReportSetParameter(phReportHandle, 0, L"BugcheckCode", v5);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v6,
      v53);
  std::wstring::~wstring(pwzValuea);
  v7 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v67, *(_QWORD *)(pwzValue[38] + 8LL));
  std::wstring::wstring(pwzValuea, v7, v67);
  v8 = (const WCHAR *)pwzValuea;
  if ( v59 > 7 )
    v8 = pwzValuea[0];
  v9 = WerReportSetParameter(phReportHandle, 1u, L"BugcheckParameter1", v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v9,
      v53);
  std::wstring::~wstring(pwzValuea);
  v10 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v67, *(_QWORD *)(pwzValue[38] + 16LL));
  std::wstring::wstring(pwzValuea, v10, v67);
  v11 = (const WCHAR *)pwzValuea;
  if ( v59 > 7 )
    v11 = pwzValuea[0];
  v12 = WerReportSetParameter(phReportHandle, 2u, L"BugcheckParameter2", v11);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v12,
      v53);
  std::wstring::~wstring(pwzValuea);
  v13 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v67, *(_QWORD *)(pwzValue[38] + 24LL));
  std::wstring::wstring(pwzValuea, v13, v67);
  v14 = (const WCHAR *)pwzValuea;
  if ( v59 > 7 )
    v14 = pwzValuea[0];
  v15 = WerReportSetParameter(phReportHandle, 3u, L"BugcheckParameter3", v14);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v15,
      v53);
  std::wstring::~wstring(pwzValuea);
  v16 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v67, *(_QWORD *)(pwzValue[38] + 32LL));
  std::wstring::wstring(pwzValuea, v16, v67);
  v17 = (const WCHAR *)pwzValuea;
  if ( v59 > 7 )
    v17 = pwzValuea[0];
  v18 = WerReportSetParameter(phReportHandle, 4u, L"BugcheckParameter4", v17);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v18,
      v53);
  std::wstring::~wstring(pwzValuea);
  *(_OWORD *)pwzPath = 0;
  v62 = 0;
  if ( *((_BYTE *)pwzValue + 160) )
  {
    if ( *((_DWORD *)pwzValue + 38) > 5u )
      Marshal::Details::FailFast(v19);
    v20 = *((_DWORD *)pwzValue + 37);
    v21 = *(_QWORD *)(Schema::Responses::System::WindowsCrashPhase_EnumData + 8LL * *((unsigned int *)pwzValue + 38));
    *(_OWORD *)pwzValuea = 0;
    v58 = 0;
    v59 = 0;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
    std::wstring::_Construct<1,unsigned short const *>(pwzValuea, v21);
    lambda_c469f1c02173631c153a01afde3efd6b_::operator()(v55, pwzValuea, v20);
    std::wstring::~wstring(pwzValuea);
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 38) != 5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v53);
    if ( pwzPath[1] == v62 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, pwzPath[1], pwzValue + 11);
      v23 = pwzPath[1];
    }
    else
    {
      std::wstring::wstring(pwzPath[1], pwzValue + 11);
      v23 = pwzPath[1] + 16;
      pwzPath[1] += 16;
    }
    if ( *((_BYTE *)pwzValue + 400) && *((int *)pwzValue + 98) >= 0 )
    {
      if ( v23 == v62 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, v23, pwzValue + 45);
        v23 = pwzPath[1];
      }
      else
      {
        std::wstring::wstring(v23, pwzValue + 45);
        v23 = pwzPath[1] + 16;
        pwzPath[1] += 16;
      }
    }
    if ( *((_BYTE *)pwzValue + 448) && *((int *)pwzValue + 110) >= 0 )
    {
      if ( v23 == v62 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, v23, pwzValue + 51);
      }
      else
      {
        std::wstring::wstring(v23, pwzValue + 51);
        pwzPath[1] += 16;
      }
    }
    if ( !*((_BYTE *)pwzValue + 160) )
      __fastfail(5u);
    v53 = *((_DWORD *)pwzValue + 32);
    v24 = Vml::FormatString(pwzValuea, (wchar_t *)L"%d.%d.%d SP %d.%d");
    if ( *(_QWORD *)(v24 + 24) > 7u )
      v24 = *(_QWORD *)v24;
    v25 = WerRegisterCustomMetadata(L"GuestOsVersion", (PCWSTR)v24);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v25,
        v53);
  }
  else if ( *((_BYTE *)pwzValue + 248) )
  {
    if ( *((_DWORD *)pwzValue + 61) > 4u )
      Marshal::Details::FailFast(v19);
    v26 = *((_DWORD *)pwzValue + 60);
    v27 = *(_QWORD *)(Schema::Responses::System::NixCrashPhase_EnumData + 8LL * *((unsigned int *)pwzValue + 61));
    *(_OWORD *)value = 0;
    v65 = 0;
    v66 = 0;
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(v27 + 2 * v28) );
    std::wstring::_Construct<1,unsigned short const *>(value, v27);
    lambda_c469f1c02173631c153a01afde3efd6b_::operator()(v55, value, v26);
    std::wstring::~wstring(value);
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    if ( *((_DWORD *)pwzValue + 61) != 4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)0x80004004LL,
        v53);
    if ( pwzPath[1] == v62 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(pwzPath, pwzPath[1], pwzValue + 21);
    }
    else
    {
      std::wstring::wstring(pwzPath[1], pwzValue + 21);
      pwzPath[1] += 16;
    }
    if ( !*((_BYTE *)pwzValue + 248) )
      __fastfail(5u);
    v29 = (PCWSTR)(pwzValue + 26);
    if ( pwzValue[29] > 7u )
      v29 = *(PCWSTR *)v29;
    v53 = (int)v29;
    Vml::FormatString(pwzValuea, (wchar_t *)L"%d.%d; %ws");
    *(_OWORD *)value = 0;
    v65 = 0;
    v66 = 0;
    v30 = pwzValuea;
    if ( v59 > 7 )
      v30 = (PCWSTR *)pwzValuea[0];
    std::wstring::_Construct<1,unsigned short const *>(value, v30);
    v31 = (const WCHAR *)value;
    if ( v66 > 7 )
      v31 = value[0];
    v32 = WerRegisterCustomMetadata(L"GuestOsVersion", v31);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v32,
        v53);
    std::wstring::~wstring(value);
  }
  else
  {
    v33 = *(_QWORD *)(Schema::Responses::System::WindowsCrashPhase_EnumData + 8LL);
    *(_OWORD *)pwzValuea = 0;
    v58 = 0;
    v59 = 0;
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v33 + 2 * v34) );
    std::wstring::_Construct<1,unsigned short const *>(pwzValuea, v33);
    lambda_c469f1c02173631c153a01afde3efd6b_::operator()(v55, pwzValuea, 0xFFFFFFFFLL);
  }
  std::wstring::~wstring(pwzValuea);
  v35 = pwzPath[0];
  v36 = pwzPath[1];
  while ( v35 != v36 )
  {
    if ( *((_QWORD *)v35 + 2) )
    {
      v37 = *((_QWORD *)v35 + 3) <= 7u ? v35 : *(const WCHAR **)v35;
      v38 = WerReportAddFile(phReportHandle, v37, WerFileTypeOther, 0);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v38,
          v53);
    }
    v35 += 16;
  }
  v39 = (PCWSTR)(pwzValue + 59);
  if ( pwzValue[62] > 7u )
    v39 = *(PCWSTR *)v39;
  v40 = WerRegisterCustomMetadata(L"ContainerSkuType", v39);
  if ( v40 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v40,
      v53);
  v41 = (PCWSTR)(pwzValue + 63);
  if ( pwzValue[66] > 7u )
    v41 = *(PCWSTR *)v41;
  v42 = WerRegisterCustomMetadata(L"ScenarioOwner", v41);
  if ( v42 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v42,
      v53);
  *(_OWORD *)value = 0;
  v43 = operator new(0x30u);
  *v43 = &Vml::VmMachineLocalSettingsStore::`vftable';
  v43[1] = 0;
  *((_OWORD *)v43 + 1) = 0;
  v43[4] = 0;
  v43[5] = 7;
  *((_WORD *)v43 + 8) = 0;
  v63 = 0;
  value[0] = (PCWSTR)&VirtualizationSettings::`vftable';
  v55[0] = 0;
  value[1] = (PCWSTR)v43;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, __int64))(*v43 + 8LL))(v43, 0, 131097) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\vm\\common\\mgmt\\inc\\VirtualizationSettings.h",
      (const char *)0x8000FFFFLL,
      v53);
  LODWORD(v63) = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, const unsigned __int16 *, __int64 *))(*v43 + 56LL))(
         v43,
         L"AzureFeatureSet",
         &v63)
    && (_DWORD)v63 )
  {
    if ( pwzValue[3] <= 7u )
      v44 = (const WCHAR *)pwzValue;
    else
      v44 = (const WCHAR *)*pwzValue;
    v45 = WerReportSetParameter(phReportHandle, 5u, L"ComputeSystemId", v44);
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v45,
        v53);
    if ( *((_BYTE *)pwzValue + 64) )
    {
      std::wstring::wstring(pwzValuea, pwzValue + 4);
      v46 = (const WCHAR *)pwzValuea;
      if ( v59 > 7 )
        v46 = pwzValuea[0];
      v47 = WerReportSetParameter(phReportHandle, 6u, L"AzureContainerId", v46);
      if ( v47 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
          (const char *)(unsigned int)v47,
          v53);
      std::wstring::~wstring(pwzValuea);
    }
    v48 = Vml::FormatString(pwzValuea, (wchar_t *)L"%d");
    if ( *(_QWORD *)(v48 + 24) > 7u )
      v48 = *(_QWORD *)v48;
    v49 = WerReportSetParameter(phReportHandle, 7u, L"Vtl", (PCWSTR)v48);
    if ( v49 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
        (const char *)(unsigned int)v49,
        v53);
    std::wstring::~wstring(pwzValuea);
  }
  v50 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x20u, 0);
  if ( v50 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\vm\\compute\\common\\compute\\Wer.h",
      (const char *)(unsigned int)v50,
      v53);
  (*(void (__fastcall **)(_QWORD *, __int64))*v43)(v43, 1);
  result = std::vector<std::wstring>::_Tidy(pwzPath);
  if ( phReportHandle )
    return WerReportCloseHandle(phReportHandle);
  return result;
}

```

## disassembly

```asm
0x1800266dc  push    rbp
0x1800266de  push    rbx
0x1800266df  push    rsi
0x1800266e0  push    rdi
0x1800266e1  push    r12
0x1800266e3  push    r13
0x1800266e5  push    r14
0x1800266e7  push    r15
0x1800266e9  lea     rbp, [rsp-1Fh]
0x1800266ee  sub     rsp, 0E8h
0x1800266f5  mov     rax, cs:__security_cookie
0x1800266fc  xor     rax, rsp
0x1800266ff  mov     [rbp+57h+var_50], rax
0x180026703  mov     rbx, rcx
0x180026706  xor     r15d, r15d
0x180026709  mov     [rbp+57h+var_D0], r15d
0x18002670d  lea     rax, [rbp+57h+var_D0]
0x180026711  mov     [rsp+120h+var_E0], rax
0x180026716  mov     [rsp+120h+var_D8], rcx
0x18002671b  cmp     [rcx+10h], r15
0x18002671f  setz    al
0x180026722  mov     rcx, [rbp+5Fh]; this
0x180026726  lea     rdx, aSystemIdOfCras; "System Id of crash report is required"
0x18002672d  mov     qword ptr [rsp+120h+var_F8], rdx; bool
0x180026732  mov     byte ptr [rsp+120h+var_100], al; int
0x180026736  mov     edi, 8037010Dh
0x18002673b  mov     r9d, edi; char *
0x18002673e  lea     r13, aOnecoreVmCompu_19; "onecore\\vm\\compute\\common\\compute\\"...
0x180026745  mov     r8, r13; unsigned int
0x180026748  lea     edx, [r15+4Ah]; void *
0x18002674c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180026751  mov     rcx, [rbp+5Fh]; this
0x180026755  mov     rax, [rbx+138h]
0x18002675c  sub     rax, [rbx+130h]
0x180026763  sar     rax, 3
0x180026767  lea     r12d, [r15+5]
0x18002676b  cmp     rax, r12
0x18002676e  jb      loc_180027075
0x180026774  cmp     [rbx+1D0h], r15d
0x18002677b  jnz     short loc_180026795
0x18002677d  lea     rcx, aContainercrash; "ContainerCrashDump"
0x180026784  lea     rax, aVirtualmachine; "VirtualMachineCrashDump"
0x18002678b  cmp     [rbp+57h+var_D0], r15d
0x18002678f  cmovnz  rcx, rax
0x180026793  jmp     short loc_18002679C
0x180026795  lea     rcx, pwzEventType; "VirtualFirmwareCrashDump"
0x18002679c  mov     [rbp+57h+phReportHandle], r15
0x1800267a0  lea     r9, [rbp+57h+phReportHandle]; phReportHandle
0x1800267a4  xor     r8d, r8d; pReportInformation
0x1800267a7  lea     edx, [r8+1]; repType
0x1800267ab  call    cs:__imp_WerReportCreate
0x1800267b1  mov     rcx, [rbp+5Fh]; this
0x1800267b5  test    eax, eax
0x1800267b7  js      loc_180027086
0x1800267bd  mov     rdx, [rbx+130h]
0x1800267c4  mov     rdx, [rdx]
0x1800267c7  lea     rcx, [rbp+57h+var_56]
0x1800267cb  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x1800267d0  lea     r8, [rbp+57h+var_56]
0x1800267d4  mov     rdx, rax
0x1800267d7  lea     rcx, [rbp+57h+pwzValue]
0x1800267db  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800267e0  nop
0x1800267e1  lea     r9, [rbp+57h+pwzValue]
0x1800267e5  cmp     [rbp+57h+var_B0], 7
0x1800267ea  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x1800267ef  lea     r8, pwzName; "BugcheckCode"
0x1800267f6  xor     edx, edx; dwparamID
0x1800267f8  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x1800267fc  call    cs:__imp_WerReportSetParameter
0x180026802  mov     rcx, [rbp+5Fh]; this
0x180026806  test    eax, eax
0x180026808  js      loc_180027097
0x18002680e  lea     rcx, [rbp+57h+pwzValue]
0x180026812  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026817  mov     rdx, [rbx+130h]
0x18002681e  mov     rdx, [rdx+8]
0x180026822  lea     rcx, [rbp+57h+var_56]
0x180026826  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18002682b  lea     r8, [rbp+57h+var_56]
0x18002682f  mov     rdx, rax
0x180026832  lea     rcx, [rbp+57h+pwzValue]
0x180026836  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002683b  nop
0x18002683c  lea     r9, [rbp+57h+pwzValue]
0x180026840  cmp     [rbp+57h+var_B0], 7
0x180026845  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x18002684a  lea     r8, aBugcheckparame_1; "BugcheckParameter1"
0x180026851  mov     edx, 1; dwparamID
0x180026856  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x18002685a  call    cs:__imp_WerReportSetParameter
0x180026860  mov     rcx, [rbp+5Fh]; this
0x180026864  test    eax, eax
0x180026866  js      loc_1800270A8
0x18002686c  lea     rcx, [rbp+57h+pwzValue]
0x180026870  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026875  mov     rdx, [rbx+130h]
0x18002687c  mov     rdx, [rdx+10h]
0x180026880  lea     rcx, [rbp+57h+var_56]
0x180026884  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180026889  lea     r8, [rbp+57h+var_56]
0x18002688d  mov     rdx, rax
0x180026890  lea     rcx, [rbp+57h+pwzValue]
0x180026894  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180026899  nop
0x18002689a  lea     r9, [rbp+57h+pwzValue]
0x18002689e  cmp     [rbp+57h+var_B0], 7
0x1800268a3  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x1800268a8  lea     r8, aBugcheckparame_0; "BugcheckParameter2"
0x1800268af  mov     edx, 2; dwparamID
0x1800268b4  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x1800268b8  call    cs:__imp_WerReportSetParameter
0x1800268be  mov     rcx, [rbp+5Fh]; this
0x1800268c2  test    eax, eax
0x1800268c4  js      loc_1800270B9
0x1800268ca  lea     rcx, [rbp+57h+pwzValue]
0x1800268ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800268d3  mov     rdx, [rbx+130h]
0x1800268da  mov     rdx, [rdx+18h]
0x1800268de  lea     rcx, [rbp+57h+var_56]
0x1800268e2  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x1800268e7  lea     r8, [rbp+57h+var_56]
0x1800268eb  mov     rdx, rax
0x1800268ee  lea     rcx, [rbp+57h+pwzValue]
0x1800268f2  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800268f7  nop
0x1800268f8  lea     r9, [rbp+57h+pwzValue]
0x1800268fc  cmp     [rbp+57h+var_B0], 7
0x180026901  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180026906  lea     r8, aBugcheckparame_2; "BugcheckParameter3"
0x18002690d  mov     edx, 3; dwparamID
0x180026912  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180026916  call    cs:__imp_WerReportSetParameter
0x18002691c  mov     rcx, [rbp+5Fh]; this
0x180026920  test    eax, eax
0x180026922  js      loc_1800270CA
0x180026928  lea     rcx, [rbp+57h+pwzValue]
0x18002692c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026931  mov     rdx, [rbx+130h]
0x180026938  mov     rdx, [rdx+20h]
0x18002693c  lea     rcx, [rbp+57h+var_56]
0x180026940  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x180026945  lea     r8, [rbp+57h+var_56]
0x180026949  mov     rdx, rax
0x18002694c  lea     rcx, [rbp+57h+pwzValue]
0x180026950  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180026955  nop
0x180026956  lea     r9, [rbp+57h+pwzValue]
0x18002695a  cmp     [rbp+57h+var_B0], 7
0x18002695f  cmova   r9, [rbp+57h+pwzValue]; pwzValue
0x180026964  lea     r8, aBugcheckparame; "BugcheckParameter4"
0x18002696b  mov     edx, 4; dwparamID
0x180026970  mov     rcx, [rbp+57h+phReportHandle]; hReportHandle
0x180026974  call    cs:__imp_WerReportSetParameter
0x18002697a  mov     rcx, [rbp+5Fh]; this
0x18002697e  test    eax, eax
0x180026980  js      loc_1800270DB
0x180026986  lea     rcx, [rbp+57h+pwzValue]
0x18002698a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002698f  xorps   xmm0, xmm0
0x180026992  xorps   xmm1, xmm1
0x180026995  movdqu  xmmword ptr [rbp+57h+pwzPath], xmm1
0x18002699a  mov     [rbp+57h+var_90], r15
0x18002699e  cmp     [rbx+0A0h], r15b
0x1800269a5  jz      loc_180026BD6
0x1800269ab  mov     al, [rbx+0A0h]
0x1800269b1  test    al, al
0x1800269b3  jnz     short loc_1800269C0
0x1800269b5  mov     rcx, r12
0x1800269b8  int     29h; Win8: RtlFailFast(ecx)
0x1800269ba  test    al, al
0x1800269bc  jnz     short loc_1800269C0
0x1800269be  int     29h; Win8: RtlFailFast(ecx)
0x1800269c0  cmp     [rbx+98h], r12d
0x1800269c7  ja      loc_180027100
0x1800269cd  mov     r14d, [rbx+94h]
0x1800269d4  mov     rcx, cs:?WindowsCrashPhase_EnumData@System@Responses@Schema@@3UEnumData@Marshal@@B; Marshal::EnumData const Schema::Responses::System::WindowsCrashPhase_EnumData
0x1800269db  mov     eax, [rbx+98h]
0x1800269e1  mov     rdx, [rcx+rax*8]
0x1800269e5  movups  xmmword ptr [rbp+57h+pwzValue], xmm0
0x1800269e9  mov     [rbp+57h+var_B8], r15
0x1800269ed  mov     [rbp+57h+var_B0], r15
0x1800269f1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800269f5  inc     rsi
0x1800269f8  cmp     [rdx+rsi*2], r15w
0x1800269fd  jnz     short loc_1800269F5
0x1800269ff  mov     r8, rsi
0x180026a02  lea     rcx, [rbp+57h+pwzValue]
0x180026a06  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026a0b  mov     r8d, r14d
0x180026a0e  lea     rdx, [rbp+57h+pwzValue]
0x180026a12  lea     rcx, [rsp+120h+var_E0]
0x180026a17  call    _lambda_c469f1c02173631c153a01afde3efd6b___operator__
0x180026a1c  lea     rcx, [rbp+57h+pwzValue]
0x180026a20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026a25  mov     al, [rbx+0A0h]
0x180026a2b  test    al, al
0x180026a2d  jnz     short loc_180026A34
0x180026a2f  mov     rcx, r12
0x180026a32  int     29h; Win8: RtlFailFast(ecx)
0x180026a34  mov     rcx, [rbp+5Fh]; this
0x180026a38  cmp     [rbx+98h], r12d
0x180026a3f  jnz     loc_1800270EC
0x180026a45  test    al, al
0x180026a47  jnz     short loc_180026A4E
0x180026a49  mov     rcx, r12
0x180026a4c  int     29h; Win8: RtlFailFast(ecx)
0x180026a4e  mov     rax, [rbp+57h+pwzPath+8]
0x180026a52  cmp     rax, [rbp+57h+var_90]
0x180026a56  jz      short loc_180026A72
0x180026a58  lea     rdx, [rbx+58h]
0x180026a5c  mov     rcx, rax
0x180026a5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026a64  mov     rax, [rbp+57h+pwzPath+8]
0x180026a68  add     rax, 20h ; ' '
0x180026a6c  mov     [rbp+57h+pwzPath+8], rax
0x180026a70  jmp     short loc_180026A86
0x180026a72  lea     r8, [rbx+58h]
0x180026a76  mov     rdx, rax
0x180026a79  lea     rcx, [rbp+57h+pwzPath]
0x180026a7d  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180026a82  mov     rax, [rbp+57h+pwzPath+8]
0x180026a86  cmp     [rbx+190h], r15b
0x180026a8d  jz      short loc_180026AE1
0x180026a8f  lea     r8, [rbx+168h]
0x180026a96  mov     dl, [r8+28h]
0x180026a9a  test    dl, dl
0x180026a9c  jnz     short loc_180026AA3
0x180026a9e  mov     rcx, r12
0x180026aa1  int     29h; Win8: RtlFailFast(ecx)
0x180026aa3  cmp     [r8+20h], r15d
0x180026aa7  jl      short loc_180026AE1
0x180026aa9  test    dl, dl
0x180026aab  jnz     short loc_180026AB2
0x180026aad  mov     rcx, r12
0x180026ab0  int     29h; Win8: RtlFailFast(ecx)
0x180026ab2  cmp     rax, [rbp+57h+var_90]
0x180026ab6  jz      short loc_180026AD1
0x180026ab8  mov     rdx, r8
0x180026abb  mov     rcx, rax
0x180026abe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026ac3  mov     rax, [rbp+57h+pwzPath+8]
0x180026ac7  add     rax, 20h ; ' '
0x180026acb  mov     [rbp+57h+pwzPath+8], rax
0x180026acf  jmp     short loc_180026AE1
0x180026ad1  mov     rdx, rax
0x180026ad4  lea     rcx, [rbp+57h+pwzPath]
0x180026ad8  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180026add  mov     rax, [rbp+57h+pwzPath+8]
0x180026ae1  cmp     [rbx+1C0h], r15b
0x180026ae8  jz      short loc_180026B31
0x180026aea  lea     r8, [rbx+198h]
0x180026af1  mov     dl, [r8+28h]
0x180026af5  test    dl, dl
0x180026af7  jnz     short loc_180026AFE
0x180026af9  mov     rcx, r12
0x180026afc  int     29h; Win8: RtlFailFast(ecx)
0x180026afe  cmp     [r8+20h], r15d
0x180026b02  jl      short loc_180026B31
0x180026b04  test    dl, dl
0x180026b06  jnz     short loc_180026B0D
0x180026b08  mov     rcx, r12
0x180026b0b  int     29h; Win8: RtlFailFast(ecx)
0x180026b0d  cmp     rax, [rbp+57h+var_90]
0x180026b11  jz      short loc_180026B25
0x180026b13  mov     rdx, r8
0x180026b16  mov     rcx, rax
0x180026b19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026b1e  add     [rbp+57h+pwzPath+8], 20h ; ' '
0x180026b23  jmp     short loc_180026B31
0x180026b25  mov     rdx, rax
0x180026b28  lea     rcx, [rbp+57h+pwzPath]
0x180026b2c  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180026b31  mov     al, [rbx+0A0h]
0x180026b37  test    al, al
0x180026b39  jnz     short loc_180026B40
0x180026b3b  mov     rcx, r12
0x180026b3e  int     29h; Win8: RtlFailFast(ecx)
0x180026b40  mov     r9d, [rbx+88h]
0x180026b47  test    al, al
0x180026b49  jnz     short loc_180026B50
0x180026b4b  mov     rcx, r12
0x180026b4e  int     29h; Win8: RtlFailFast(ecx)
0x180026b50  mov     r8d, [rbx+84h]
0x180026b57  test    al, al
0x180026b59  jnz     short loc_180026B60
0x180026b5b  mov     rcx, r12
0x180026b5e  int     29h; Win8: RtlFailFast(ecx)
0x180026b60  mov     edx, [rbx+80h]
0x180026b66  test    al, al
0x180026b68  jnz     short loc_180026B75
0x180026b6a  mov     rcx, r12
0x180026b6d  int     29h; Win8: RtlFailFast(ecx)
0x180026b6f  test    al, al
0x180026b71  jnz     short loc_180026B75
0x180026b73  int     29h; Win8: RtlFailFast(ecx)
0x180026b75  mov     [rsp+120h+var_F0], r9d
0x180026b7a  mov     dword ptr [rsp+120h+var_F8], r8d
0x180026b7f  mov     [rsp+120h+var_100], edx; int
0x180026b83  mov     r9d, [rbx+7Ch]
  ... truncated ...
```
