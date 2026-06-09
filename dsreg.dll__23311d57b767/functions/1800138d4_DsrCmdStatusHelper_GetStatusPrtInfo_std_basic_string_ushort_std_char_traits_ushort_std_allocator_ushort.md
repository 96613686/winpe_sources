# DsrCmdStatusHelper::GetStatusPrtInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800138d4`
- end: `0x18001522a`
- name: `?GetStatusPrtInfo@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `6486`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, installer_update`

## callers

- `0x1800a523c`
- `0x1800a674c`

## callees

- `0x180012948`
- `0x180012c7c`
- `0x18001327c`
- `0x18001378c`
- `0x1800138d4`
- `0x180015230`
- `0x1800154f8`
- `0x180015f3c`
- `0x180016438`
- `0x180016ae0`
- `0x180016b90`
- `0x180017724`
- `0x18001de18`
- `0x180029470`
- `0x180029554`
- `0x1800295f8`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002ba70`
- `0x18002deec`
- `0x1800306e0`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x18007d20c`
- `0x1800a1f4c`
- `0x1800a2010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800151e3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800151f7`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800151e3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800151f7`
- `CRYPT32!CertFreeCertificateContext` at `0x180014faa`
- `CRYPT32!CertFreeCertificateContext` at `0x180014faa`

## string_xrefs

- `0x180013a38`: `AzureAdPrtAuthority`
- `0x180013bcc`: `AzureAdPrtAuthority`
- `0x180013e2d`: `AzureAdPrtAuthority`
- `0x180014124`: `AzureAdPrtAuthority`
- `0x1800142bc`: `AzureAdPrtAuthority`
- `0x180014085`: `GetAcquirePrtDiagnosticInfo(AADPLUGIN_AUTHORITY_CLOUD)`
- `0x180013f40`: `DsrGetPrtAuthorityInfo(AADPLUGIN_AUTHORITY_CLOUD)`
- `0x180014dc0`: `GetRefreshPrtDiagnosticInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)`
- `0x180014803`: `DsrGetPrtAuthorityInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)`
- `0x1800144e2`: `GetRefreshPrtDiagnosticInfo(AADPLUGIN_AUTHORITY_CLOUD)`
- `0x1800139df`: `AzureAdPrt`
- `0x180013b73`: `AzureAdPrt`
- `0x180013cf7`: `AzureAdPrt`
- `0x18001494c`: `GetAcquirePrtDiagnosticInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)`
- `0x1800141d6`: `AzureAdPrtUpdateTime`
- `0x18001422c`: `AzureAdPrtExpiryTime`
- `0x180014aa7`: `EnterprisePrtUpdateTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DsrCmdStatusHelper::GetStatusPrtInfo(__int64 a1)
{
  __int64 v1; // r15
  _BYTE *v2; // rsi
  _AADPLUGIN_PRT_INFO *v3; // r14
  __int128 v4; // xmm0
  int DeviceCertificate; // edi
  PCCERT_CONTEXT v6; // r13
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  int v15; // r14d
  FILETIME NotBefore; // rbx
  int PrtAuthorityInfo; // edi
  __m128i si128; // xmm6
  void **v19; // rdx
  void **v20; // rdx
  DWORD dwLowDateTime; // r9d
  int PrtDiagnosticInfo; // edi
  __int64 v23; // r8
  _QWORD *v24; // rax
  __int64 v25; // r8
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rdi
  _QWORD *v30; // rax
  __int64 v31; // rdi
  _QWORD *v32; // rax
  __int64 v33; // rdi
  _QWORD *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rax
  DWORD v38; // r9d
  int v39; // edi
  __int64 v40; // r8
  _QWORD *v41; // rax
  __int64 v42; // r8
  _QWORD *v43; // rax
  int v44; // edi
  void **v45; // rdx
  void **v46; // rdx
  int v47; // r15d
  DWORD v48; // r9d
  int v49; // edi
  __int64 v50; // r8
  _QWORD *v51; // rax
  __int64 v52; // r8
  _QWORD *v53; // rax
  _QWORD *v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // rdi
  _QWORD *v57; // rax
  __int64 v58; // rdi
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  __int64 v61; // rdi
  _QWORD *v62; // rax
  __int64 v63; // rax
  _QWORD *v64; // rax
  __int64 v65; // rax
  __int64 v66; // r8
  _QWORD *v67; // rax
  __int64 v68; // r8
  _QWORD *v69; // rax
  char v70; // bl
  __int64 v71; // r8
  _QWORD *v72; // rax
  char v73; // bl
  __int64 v74; // r8
  _QWORD *v75; // rax
  __int64 v76; // rbx
  _QWORD *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  const wchar_t *v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // rcx
  const wchar_t *v87; // rbx
  __int64 v88; // rax
  const unsigned __int16 *v89; // rcx
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE *v92; // [rsp+40h] [rbp-C8h] BYREF
  _AADPLUGIN_PRT_INFO *v93; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v94; // [rsp+50h] [rbp-B8h]
  char v95[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v96; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v97[104]; // [rsp+E0h] [rbp-28h] BYREF
  char v98[8]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v99[128]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v100[104]; // [rsp+1D0h] [rbp+C8h] BYREF
  wchar_t *Format[2]; // [rsp+238h] [rbp+130h] BYREF
  __int128 v102; // [rsp+248h] [rbp+140h]
  __int128 v103; // [rsp+258h] [rbp+150h] BYREF
  __m128i v104; // [rsp+268h] [rbp+160h]
  void *v105[2]; // [rsp+278h] [rbp+170h] BYREF
  __m128i v106; // [rsp+288h] [rbp+180h]
  __int128 v107; // [rsp+298h] [rbp+190h] BYREF
  __int64 v108; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v109; // [rsp+2B0h] [rbp+1A8h]
  __int128 v110; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v111; // [rsp+2C8h] [rbp+1C0h]
  unsigned __int64 v112; // [rsp+2D0h] [rbp+1C8h]
  __int128 v113; // [rsp+2D8h] [rbp+1D0h] BYREF
  __int64 v114; // [rsp+2E8h] [rbp+1E0h]
  unsigned __int64 v115; // [rsp+2F0h] [rbp+1E8h]
  __int128 v116; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int64 v117; // [rsp+308h] [rbp+200h]
  unsigned __int64 v118; // [rsp+310h] [rbp+208h]

  v1 = a1;
  v94 = a1;
  pCertContext = 0;
  v2 = 0;
  v92 = 0;
  v3 = 0;
  v93 = 0;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v95);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v98);
  v4 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v116);
  v113 = v4;
  v114 = 0;
  v115 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v113);
  v110 = v4;
  v111 = 0;
  v112 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v110);
  v107 = v4;
  v108 = 0;
  v109 = 0;
  std::wstring::_Construct_empty(&v107);
  DeviceCertificate = DsrGetDeviceCertificate(&pCertContext);
  v6 = pCertContext;
  if ( DeviceCertificate < 0 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrt");
    v7 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"ERROR");
    std::operator<<<unsigned short>((__int64)v95, v7);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtAuthority");
    v8 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"ERROR");
    std::operator<<<unsigned short>((__int64)v95, v8);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrt");
    v9 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"ERROR");
    std::operator<<<unsigned short>((__int64)v95, v9);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtAuthority");
    v10 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"ERROR");
    std::operator<<<unsigned short>((__int64)v95, v10);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"DsrGetDeviceCertificate");
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)DeviceCertificate);
    std::wstring::_Tidy_deallocate((__int64)Format);
    goto LABEL_113;
  }
  if ( !pCertContext )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrt");
    v11 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v11);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtAuthority");
    v12 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v12);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrt");
    v13 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v13);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtAuthority");
    v14 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v14);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    goto LABEL_111;
  }
  v15 = 0;
  LODWORD(pCertContext) = 0;
  NotBefore = v6->pCertInfo->NotBefore;
  PrtAuthorityInfo = DsrGetPrtAuthorityInfo(1, &v92);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v2 = v92;
  if ( PrtAuthorityInfo < 0 )
  {
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"AzureAdPrt", 10);
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v103, L"ERROR", 5);
    DsrCmdStatusHelper::CreateMsgRow(v105, Format, &v103);
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v19 = v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v19 = (void **)v105[0];
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v19, v106.m128i_i64[0]);
    if ( v106.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v105[0], 2 * v106.m128i_i64[1] + 2);
    v106 = si128;
    LOWORD(v105[0]) = 0;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v103, L"AzureAdPrtAuthority", 19);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"ERROR", 5);
    DsrCmdStatusHelper::CreateMsgRow(v105, &v103, Format);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    v20 = v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v20 = (void **)v105[0];
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v20, v106.m128i_i64[0]);
    if ( v106.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v105[0], 2 * v106.m128i_i64[1] + 2);
    v106 = si128;
    LOWORD(v105[0]) = 0;
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"DsrGetPrtAuthorityInfo(AADPLUGIN_AUTHORITY_CLOUD)", 49);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)PrtAuthorityInfo);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    goto LABEL_24;
  }
  if ( !v92 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrt");
    v26 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v26);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtAuthority");
    v27 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v27);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
LABEL_24:
    dwLowDateTime = NotBefore.dwLowDateTime;
    goto LABEL_25;
  }
  if ( *v92 )
  {
    v15 = 1;
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrt");
    v28 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"YES");
    std::operator<<<unsigned short>((__int64)v95, v28);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v29 = *((_QWORD *)v2 + 3);
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtUpdateTime");
    v30 = (_QWORD *)DsrCmdStatusHelper::CreateTimeMsgRow(&v103, Format, v29);
    std::operator<<<unsigned short>((__int64)v95, v30);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v31 = *((_QWORD *)v2 + 4);
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtExpiryTime");
    v32 = (_QWORD *)DsrCmdStatusHelper::CreateTimeMsgRow(&v103, Format, v31);
  }
  else
  {
    std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrt");
    v32 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
  }
  std::operator<<<unsigned short>((__int64)v95, v32);
  std::wstring::_Tidy_deallocate((__int64)&v103);
  std::wstring::_Tidy_deallocate((__int64)Format);
  v33 = *((_QWORD *)v2 + 1);
  std::wstring::wstring((__int64)Format, (__int64)L"AzureAdPrtAuthority");
  v34 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, v33);
  std::operator<<<unsigned short>((__int64)v95, v34);
  std::wstring::_Tidy_deallocate((__int64)&v103);
  std::wstring::_Tidy_deallocate((__int64)Format);
  if ( !v15 )
    goto LABEL_24;
  v35 = *((int *)v2 + 6) + 0x2B6109100LL;
  LODWORD(v92) = 10000000 * (*((_DWORD *)v2 + 6) - 1240428288);
  HIDWORD(v92) = (unsigned __int64)(10000000 * v35) >> 32;
  dwLowDateTime = (unsigned int)v92;
LABEL_25:
  PrtDiagnosticInfo = DsrCmdStatusHelper::GetPrtDiagnosticInfo(1, 1250, 1251, dwLowDateTime, (__int64)&v116);
  if ( PrtDiagnosticInfo >= 0 )
  {
    if ( v117 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"AcquirePrtDiagnostics");
      v36 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"PRESENT");
      std::operator<<<unsigned short>((__int64)v95, v36);
      std::wstring::_Tidy_deallocate((__int64)&v103);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::operator<<<unsigned short>((__int64)v95, &v116);
    }
  }
  else
  {
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"AcquirePrtDiagnostics", 21);
    v24 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(&v103, Format, v23, (unsigned int)PrtDiagnosticInfo);
    v25 = v24[2];
    if ( v24[3] > 7u )
      v24 = (_QWORD *)*v24;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v24, v25);
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v104 = si128;
    LOWORD(v103) = 0;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Format,
      L"GetAcquirePrtDiagnosticInfo(AADPLUGIN_AUTHORITY_CLOUD)",
      54);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)PrtDiagnosticInfo);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  }
  if ( v15 )
  {
    v37 = *((int *)v2 + 6) + 0x2B6109100LL;
    LODWORD(v92) = 10000000 * (*((_DWORD *)v2 + 6) - 1240428288);
    HIDWORD(v92) = (unsigned __int64)(10000000 * v37) >> 32;
    v38 = (unsigned int)v92;
  }
  else
  {
    v38 = NotBefore.dwLowDateTime;
  }
  v39 = DsrCmdStatusHelper::GetPrtDiagnosticInfo(1, 1252, 1253, v38, (__int64)&v113);
  if ( v39 >= 0 )
  {
    if ( v114 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"RefreshPrtDiagnostics");
      v43 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"PRESENT");
      std::operator<<<unsigned short>((__int64)v95, v43);
      std::wstring::_Tidy_deallocate((__int64)&v103);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::operator<<<unsigned short>((__int64)v95, &v113);
    }
  }
  else
  {
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"RefreshPrtDiagnostics", 21);
    v41 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(&v103, Format, v40, (unsigned int)v39);
    v42 = v41[2];
    if ( v41[3] > 7u )
      v41 = (_QWORD *)*v41;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v41, v42);
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v104 = si128;
    LOWORD(v103) = 0;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Format,
      L"GetRefreshPrtDiagnosticInfo(AADPLUGIN_AUTHORITY_CLOUD)",
      54);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)v39);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  }
  v44 = DsrGetPrtAuthorityInfo(2, &v93);
  v3 = v93;
  if ( v44 < 0 )
  {
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v103, L"EnterprisePrt", 13);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"ERROR", 5);
    DsrCmdStatusHelper::CreateMsgRow(v105, &v103, Format);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    v45 = v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v45 = (void **)v105[0];
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v45, v106.m128i_i64[0]);
    if ( v106.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v105[0], 2 * v106.m128i_i64[1] + 2);
    v106 = si128;
    LOWORD(v105[0]) = 0;
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v103, L"EnterprisePrtAuthority", 22);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"ERROR", 5);
    DsrCmdStatusHelper::CreateMsgRow(v105, &v103, Format);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    v46 = v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v46 = (void **)v105[0];
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v46, v106.m128i_i64[0]);
    if ( v106.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v105[0], 2 * v106.m128i_i64[1] + 2);
    v106 = si128;
    LOWORD(v105[0]) = 0;
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Format,
      L"DsrGetPrtAuthorityInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)",
      54);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)v44);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    goto LABEL_76;
  }
  if ( !v93 )
  {
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrt");
    v53 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v53);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtAuthority");
    v54 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v54);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
LABEL_76:
    v47 = (int)pCertContext;
    goto LABEL_77;
  }
  if ( *(_BYTE *)v93 )
  {
    v47 = 1;
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrt");
    v55 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"YES");
    std::operator<<<unsigned short>((__int64)v95, v55);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v56 = *((_QWORD *)v3 + 3);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtUpdateTime");
    v57 = (_QWORD *)DsrCmdStatusHelper::CreateTimeMsgRow(&v103, Format, v56);
    std::operator<<<unsigned short>((__int64)v95, v57);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v58 = *((_QWORD *)v3 + 4);
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtExpiryTime");
    v59 = (_QWORD *)DsrCmdStatusHelper::CreateTimeMsgRow(&v103, Format, v58);
    std::operator<<<unsigned short>((__int64)v95, v59);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
  }
  else
  {
    std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrt");
    v60 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"NO");
    std::operator<<<unsigned short>((__int64)v95, v60);
    std::wstring::_Tidy_deallocate((__int64)&v103);
    std::wstring::_Tidy_deallocate((__int64)Format);
    v47 = (int)pCertContext;
  }
  v61 = *((_QWORD *)v3 + 1);
  std::wstring::wstring((__int64)Format, (__int64)L"EnterprisePrtAuthority");
  v62 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, v61);
  std::operator<<<unsigned short>((__int64)v95, v62);
  std::wstring::_Tidy_deallocate((__int64)&v103);
  std::wstring::_Tidy_deallocate((__int64)Format);
  if ( v47 )
  {
    v63 = *((int *)v2 + 6) + 0x2B6109100LL;
    LODWORD(v93) = 10000000 * (*((_DWORD *)v2 + 6) - 1240428288);
    HIDWORD(v93) = (unsigned __int64)(10000000 * v63) >> 32;
    v48 = (unsigned int)v93;
    goto LABEL_78;
  }
LABEL_77:
  v48 = NotBefore.dwLowDateTime;
LABEL_78:
  v49 = DsrCmdStatusHelper::GetPrtDiagnosticInfo(2, 1250, 1251, v48, (__int64)&v110);
  if ( v49 >= 0 )
  {
    if ( v111 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"AcquirePrtDiagnostics");
      v64 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"PRESENT");
      std::operator<<<unsigned short>((__int64)v95, v64);
      std::wstring::_Tidy_deallocate((__int64)&v103);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::operator<<<unsigned short>((__int64)v95, &v110);
    }
  }
  else
  {
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"AcquirePrtDiagnostics", 21);
    v51 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(&v103, Format, v50, (unsigned int)v49);
    v52 = v51[2];
    if ( v51[3] > 7u )
      v51 = (_QWORD *)*v51;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v51, v52);
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v104 = si128;
    LOWORD(v103) = 0;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Format,
      L"GetAcquirePrtDiagnosticInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)",
      59);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)v49);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  }
  if ( v47 )
  {
    v65 = *((int *)v2 + 6) + 0x2B6109100LL;
    LODWORD(v93) = 10000000 * (*((_DWORD *)v2 + 6) - 1240428288);
    HIDWORD(v93) = (unsigned __int64)(10000000 * v65) >> 32;
    NotBefore.dwLowDateTime = (unsigned int)v93;
  }
  DeviceCertificate = DsrCmdStatusHelper::GetPrtDiagnosticInfo(2, 1252, 1253, NotBefore.dwLowDateTime, (__int64)&v107);
  if ( DeviceCertificate >= 0 )
  {
    if ( v108 )
    {
      std::wstring::wstring((__int64)Format, (__int64)L"RefreshPrtDiagnostics");
      v69 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, L"PRESENT");
      std::operator<<<unsigned short>((__int64)v95, v69);
      std::wstring::_Tidy_deallocate((__int64)&v103);
      std::wstring::_Tidy_deallocate((__int64)Format);
      std::operator<<<unsigned short>((__int64)v95, &v107);
    }
  }
  else
  {
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Format, L"RefreshPrtDiagnostics", 21);
    v67 = (_QWORD *)DsrCmdStatusHelper::CreateErrorMsgRow(&v103, Format, v66, (unsigned int)DeviceCertificate);
    v68 = v67[2];
    if ( v67[3] > 7u )
      v67 = (_QWORD *)*v67;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v95, v67, v68);
    if ( v104.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v103, 2 * v104.m128i_i64[1] + 2);
    v104 = si128;
    LOWORD(v103) = 0;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
    *(_OWORD *)Format = 0;
    v102 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Format,
      L"GetRefreshPrtDiagnosticInfo(AADPLUGIN_AUTHORITY_ENTERPRISE)",
      59);
    DsrCmdStatusHelper::PrintError(v98, Format, (unsigned int)DeviceCertificate);
    if ( *((_QWORD *)&v102 + 1) > 7u )
      std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  }
  if ( !*v2 )
    goto LABEL_112;
  v70 = v2[40];
  std::wstring::wstring((__int64)Format, (__int64)L"OnPremTgt");
  LOBYTE(v71) = v70;
  v72 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, v71);
  std::operator<<<unsigned short>((__int64)v95, v72);
  std::wstring::_Tidy_deallocate((__int64)&v103);
  std::wstring::_Tidy_deallocate((__int64)Format);
  v73 = v2[41];
  std::wstring::wstring((__int64)Format, (__int64)L"CloudTgt");
  LOBYTE(v74) = v73;
  v75 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, v74);
  std::operator<<<unsigned short>((__int64)v95, v75);
  std::wstring::_Tidy_deallocate((__int64)&v103);
  std::wstring::_Tidy_deallocate((__int64)Format);
  v76 = *((_QWORD *)v2 + 6);
  std::wstring::wstring((__int64)Format, (__int64)L"KerbTopLevelNames");
  v77 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(&v103, Format, v76);
  std::operator<<<unsigned short>((__int64)v95, v77);
  std::wstring::_Tidy_deallocate((__int64)&v103);
LABEL_111:
  std::wstring::_Tidy_deallocate((__int64)Format);
LABEL_112:
  v1 = v94;
LABEL_113:
  if ( v2 )
    _AADPLUGIN_PRT_INFO::`scalar deleting destructor'((_AADPLUGIN_PRT_INFO *)v2);
  if ( v3 )
    _AADPLUGIN_PRT_INFO::`scalar deleting destructor'(v3);
  CertFreeCertificateContext(v6);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v79, v78) )
  {
    std::basic_stringbuf<unsigned short>::str(v99, Format);
    v80 = (const wchar_t *)Format;
    if ( *((_QWORD *)&v102 + 1) > 7u )
      v80 = Format[0];
    wprintf(v80);
    std::wstring::_Tidy_deallocate((__int64)Format);
    CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v82, v81);
    if ( *(_BYTE *)(*CurrentRef + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v84) + 184LL) )
    {
      std::basic_stringbuf<unsigned short>::str(v99, Format);
      v87 = (const wchar_t *)Format;
      if ( *((_QWORD *)&v102 + 1) > 7u )
        v87 = Format[0];
      v88 = CmdOptions::GetCurrentRef(v86, v85);
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v88 + 184LL), v87);
      std::wstring::_Tidy_deallocate((__int64)Format);
    }
  }
  std::basic_stringbuf<unsigned short>::str(v99, Format);
  v89 = (const unsigned __int16 *)Format;
  if ( *((_QWORD *)&v102 + 1) > 7u )
    v89 = Format[0];
  Logger::TraceInformation(v89);
  if ( *((_QWORD *)&v102 + 1) > 7u )
    std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  std::basic_stringbuf<unsigned short>::str(&v96, Format);
  std::wstring::operator=(v1, (__int64)Format);
  if ( *((_QWORD *)&v102 + 1) > 7u )
    std::_Deallocate<16>(Format[0], 2LL * *((_QWORD *)&v102 + 1) + 2);
  if ( v109 > 7 )
    std::_Deallocate<16>((void *)v107, 2 * v109 + 2);
  v108 = 0;
  v109 = 7;
  LOWORD(v107) = 0;
  if ( v112 > 7 )
    std::_Deallocate<16>((void *)v110, 2 * v112 + 2);
  v111 = 0;
  v112 = 7;
  LOWORD(v110) = 0;
  if ( v115 > 7 )
    std::_Deallocate<16>((void *)v113, 2 * v115 + 2);
  v114 = 0;
  v115 = 7;
  LOWORD(v113) = 0;
  if ( v118 > 7 )
    std::_Deallocate<16>((void *)v116, 2 * v118 + 2);
  v117 = 0;
  v118 = 7;
  LOWORD(v116) = 0;
  std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>(v100);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v100);
  std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>(v97);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v97);
  return (unsigned int)DeviceCertificate;
}

```

## disassembly

```asm
0x1800138d4  mov     rax, rsp
0x1800138d7  push    rbp
0x1800138d8  push    rbx
0x1800138d9  push    rsi
0x1800138da  push    rdi
0x1800138db  push    r12
0x1800138dd  push    r13
0x1800138df  push    r14
0x1800138e1  push    r15
0x1800138e3  lea     rbp, [rax-278h]
0x1800138ea  sub     rsp, 338h
0x1800138f1  movaps  xmmword ptr [rax-58h], xmm6
0x1800138f5  mov     rax, cs:__security_cookie
0x1800138fc  xor     rax, rsp
0x1800138ff  mov     [rbp+270h+var_60], rax
0x180013906  mov     r15, rcx
0x180013909  mov     [rsp+370h+var_328], rcx
0x18001390e  xor     r12d, r12d
0x180013911  mov     [rsp+370h+pCertContext], r12
0x180013916  mov     esi, r12d
0x180013919  mov     [rsp+370h+var_338], r12
0x18001391e  mov     r14d, r12d
0x180013921  mov     [rsp+370h+var_330], r12
0x180013926  lea     rcx, [rsp+370h+var_320]
0x18001392b  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180013930  nop
0x180013931  lea     rcx, [rbp+270h+var_230]
0x180013935  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18001393a  nop
0x18001393b  xorps   xmm0, xmm0
0x18001393e  movups  [rbp+270h+var_80], xmm0
0x180013945  mov     [rbp+270h+var_70], r12
0x18001394c  mov     [rbp+270h+var_68], r12
0x180013953  lea     rcx, [rbp+270h+var_80]
0x18001395a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001395f  nop
0x180013960  movups  [rbp+270h+var_A0], xmm0
0x180013967  mov     [rbp+270h+var_90], r12
0x18001396e  mov     [rbp+270h+var_88], r12
0x180013975  lea     rcx, [rbp+270h+var_A0]
0x18001397c  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180013981  nop
0x180013982  movups  [rbp+270h+var_C0], xmm0
0x180013989  mov     [rbp+270h+var_B0], r12
0x180013990  mov     [rbp+270h+var_A8], r12
0x180013997  lea     rcx, [rbp+270h+var_C0]
0x18001399e  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800139a3  nop
0x1800139a4  movups  [rbp+270h+var_E0], xmm0
0x1800139ab  mov     [rbp+270h+var_D0], r12
0x1800139b2  mov     [rbp+270h+var_C8], r12
0x1800139b9  lea     rcx, [rbp+270h+var_E0]
0x1800139c0  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800139c5  nop
0x1800139c6  lea     rcx, [rsp+370h+pCertContext]
0x1800139cb  call    DsrGetDeviceCertificate
0x1800139d0  mov     edi, eax
0x1800139d2  mov     r13, [rsp+370h+pCertContext]
0x1800139d7  test    eax, eax
0x1800139d9  jns     loc_180013B6A
0x1800139df  lea     rdx, aAzureadprt; "AzureAdPrt"
0x1800139e6  lea     rcx, [rbp+270h+Format]
0x1800139ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800139f2  nop
0x1800139f3  lea     r12, aError_3; "ERROR"
0x1800139fa  mov     r8, r12
0x1800139fd  lea     rdx, [rbp+270h+Format]
0x180013a04  lea     rcx, [rbp+270h+var_120]
0x180013a0b  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013a10  nop
0x180013a11  mov     rdx, rax
0x180013a14  lea     rcx, [rsp+370h+var_320]
0x180013a19  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013a1e  nop
0x180013a1f  lea     rcx, [rbp+270h+var_120]
0x180013a26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013a2b  nop
0x180013a2c  lea     rcx, [rbp+270h+Format]
0x180013a33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013a38  lea     rdx, aAzureadprtauth; "AzureAdPrtAuthority"
0x180013a3f  lea     rcx, [rbp+270h+Format]
0x180013a46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013a4b  nop
0x180013a4c  mov     r8, r12
0x180013a4f  lea     rdx, [rbp+270h+Format]
0x180013a56  lea     rcx, [rbp+270h+var_120]
0x180013a5d  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013a62  nop
0x180013a63  mov     rdx, rax
0x180013a66  lea     rcx, [rsp+370h+var_320]
0x180013a6b  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013a70  nop
0x180013a71  lea     rcx, [rbp+270h+var_120]
0x180013a78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013a7d  nop
0x180013a7e  lea     rcx, [rbp+270h+Format]
0x180013a85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013a8a  lea     rdx, aEnterpriseprt; "EnterprisePrt"
0x180013a91  lea     rcx, [rbp+270h+Format]
0x180013a98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013a9d  nop
0x180013a9e  mov     r8, r12
0x180013aa1  lea     rdx, [rbp+270h+Format]
0x180013aa8  lea     rcx, [rbp+270h+var_120]
0x180013aaf  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013ab4  nop
0x180013ab5  mov     rdx, rax
0x180013ab8  lea     rcx, [rsp+370h+var_320]
0x180013abd  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013ac2  nop
0x180013ac3  lea     rcx, [rbp+270h+var_120]
0x180013aca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013acf  nop
0x180013ad0  lea     rcx, [rbp+270h+Format]
0x180013ad7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013adc  lea     rdx, aEnterpriseprta; "EnterprisePrtAuthority"
0x180013ae3  lea     rcx, [rbp+270h+Format]
0x180013aea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013aef  nop
0x180013af0  mov     r8, r12
0x180013af3  lea     rdx, [rbp+270h+Format]
0x180013afa  lea     rcx, [rbp+270h+var_120]
0x180013b01  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013b06  nop
0x180013b07  mov     rdx, rax
0x180013b0a  lea     rcx, [rsp+370h+var_320]
0x180013b0f  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013b14  nop
0x180013b15  lea     rcx, [rbp+270h+var_120]
0x180013b1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013b21  nop
0x180013b22  lea     rcx, [rbp+270h+Format]
0x180013b29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013b2e  lea     rdx, aDsrgetdevicece; "DsrGetDeviceCertificate"
0x180013b35  lea     rcx, [rbp+270h+Format]
0x180013b3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013b41  nop
0x180013b42  mov     r8d, edi
0x180013b45  lea     rdx, [rbp+270h+Format]
0x180013b4c  lea     rcx, [rbp+270h+var_230]
0x180013b50  call    ?PrintError@DsrCmdStatusHelper@@CAXAEAV?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@J@Z; DsrCmdStatusHelper::PrintError(std::basic_ostringstream<ushort> &,std::wstring const &,long)
0x180013b55  nop
0x180013b56  lea     rcx, [rbp+270h+Format]
0x180013b5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013b62  xor     r12d, r12d
0x180013b65  jmp     loc_180014F8D
0x180013b6a  test    r13, r13
0x180013b6d  jnz     loc_180013CBB
0x180013b73  lea     rdx, aAzureadprt; "AzureAdPrt"
0x180013b7a  lea     rcx, [rbp+270h+Format]
0x180013b81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013b86  nop
0x180013b87  lea     r15, aNo_0; "NO"
0x180013b8e  mov     r8, r15
0x180013b91  lea     rdx, [rbp+270h+Format]
0x180013b98  lea     rcx, [rbp+270h+var_120]
0x180013b9f  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013ba4  nop
0x180013ba5  mov     rdx, rax
0x180013ba8  lea     rcx, [rsp+370h+var_320]
0x180013bad  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013bb2  nop
0x180013bb3  lea     rcx, [rbp+270h+var_120]
0x180013bba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013bbf  nop
0x180013bc0  lea     rcx, [rbp+270h+Format]
0x180013bc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013bcc  lea     rdx, aAzureadprtauth; "AzureAdPrtAuthority"
0x180013bd3  lea     rcx, [rbp+270h+Format]
0x180013bda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013bdf  nop
0x180013be0  mov     r8, r15
0x180013be3  lea     rdx, [rbp+270h+Format]
0x180013bea  lea     rcx, [rbp+270h+var_120]
0x180013bf1  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013bf6  nop
0x180013bf7  mov     rdx, rax
0x180013bfa  lea     rcx, [rsp+370h+var_320]
0x180013bff  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013c04  nop
0x180013c05  lea     rcx, [rbp+270h+var_120]
0x180013c0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013c11  nop
0x180013c12  lea     rcx, [rbp+270h+Format]
0x180013c19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013c1e  lea     rdx, aEnterpriseprt; "EnterprisePrt"
0x180013c25  lea     rcx, [rbp+270h+Format]
0x180013c2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013c31  nop
0x180013c32  mov     r8, r15
0x180013c35  lea     rdx, [rbp+270h+Format]
0x180013c3c  lea     rcx, [rbp+270h+var_120]
0x180013c43  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013c48  nop
0x180013c49  mov     rdx, rax
0x180013c4c  lea     rcx, [rsp+370h+var_320]
0x180013c51  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013c56  nop
0x180013c57  lea     rcx, [rbp+270h+var_120]
0x180013c5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013c63  nop
0x180013c64  lea     rcx, [rbp+270h+Format]
0x180013c6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013c70  lea     rdx, aEnterpriseprta; "EnterprisePrtAuthority"
0x180013c77  lea     rcx, [rbp+270h+Format]
0x180013c7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013c83  nop
0x180013c84  mov     r8, r15
0x180013c87  lea     rdx, [rbp+270h+Format]
0x180013c8e  lea     rcx, [rbp+270h+var_120]
0x180013c95  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180013c9a  nop
0x180013c9b  mov     rdx, rax
0x180013c9e  lea     rcx, [rsp+370h+var_320]
0x180013ca3  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180013ca8  nop
0x180013ca9  lea     rcx, [rbp+270h+var_120]
0x180013cb0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013cb5  nop
0x180013cb6  jmp     loc_180014F7C
0x180013cbb  mov     r14d, r12d
0x180013cbe  mov     dword ptr [rsp+370h+pCertContext], r12d
0x180013cc3  mov     rbx, [r13+18h]
0x180013cc7  mov     rbx, [rbx+40h]
0x180013ccb  lea     rdx, [rsp+370h+var_338]
0x180013cd0  mov     ecx, 1
0x180013cd5  call    DsrGetPrtAuthorityInfo
0x180013cda  mov     edi, eax
0x180013cdc  lea     r12, aError_3; "ERROR"
0x180013ce3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180013ceb  lea     r15, aNo_0; "NO"
0x180013cf2  mov     rsi, [rsp+370h+var_338]
0x180013cf7  lea     rdx, aAzureadprt; "AzureAdPrt"
0x180013cfe  lea     rcx, [rbp+270h+Format]
0x180013d05  test    eax, eax
0x180013d07  jns     loc_1800140D7
0x180013d0d  xorps   xmm0, xmm0
0x180013d10  movups  xmmword ptr [rbp+270h+Format], xmm0
0x180013d17  xorps   xmm1, xmm1
0x180013d1a  movdqu  [rbp+270h+var_130], xmm1
0x180013d22  mov     r8d, 0Ah
0x180013d28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013d2d  nop
0x180013d2e  xorps   xmm0, xmm0
0x180013d31  movups  [rbp+270h+var_120], xmm0
0x180013d38  xorps   xmm1, xmm1
0x180013d3b  movdqu  [rbp+270h+var_110], xmm1
0x180013d43  mov     r8d, 5
0x180013d49  mov     rdx, r12
0x180013d4c  lea     rcx, [rbp+270h+var_120]
0x180013d53  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013d58  nop
0x180013d59  lea     r8, [rbp+270h+var_120]
0x180013d60  lea     rdx, [rbp+270h+Format]
0x180013d67  lea     rcx, [rbp+270h+var_100]
0x180013d6e  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,std::wstring const &)
0x180013d73  nop
0x180013d74  mov     rdx, qword ptr [rbp+270h+var_110+8]
0x180013d7b  cmp     rdx, 7
0x180013d7f  jbe     short loc_180013D96
0x180013d81  lea     rdx, ds:2[rdx*2]
0x180013d89  mov     rcx, qword ptr [rbp+270h+var_120]
0x180013d90  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013d95  nop
0x180013d96  lea     rdx, [rbp+270h+var_100]
0x180013d9d  cmp     qword ptr [rbp+270h+var_F0+8], 7
0x180013da5  cmova   rdx, [rbp+270h+var_100]
0x180013dad  mov     r8, qword ptr [rbp+270h+var_F0]
0x180013db4  lea     rcx, [rsp+370h+var_320]
0x180013db9  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180013dbe  nop
0x180013dbf  mov     rdx, qword ptr [rbp+270h+var_F0+8]
0x180013dc6  cmp     rdx, 7
0x180013dca  jbe     short loc_180013DE0
0x180013dcc  lea     rdx, ds:2[rdx*2]
0x180013dd4  mov     rcx, [rbp+270h+var_100]
0x180013ddb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013de0  movdqu  [rbp+270h+var_F0], xmm6
0x180013de8  xor     eax, eax
0x180013dea  mov     word ptr [rbp+270h+var_100], ax
0x180013df1  mov     rdx, qword ptr [rbp+270h+var_130+8]
0x180013df8  cmp     rdx, 7
0x180013dfc  jbe     short loc_180013E12
0x180013dfe  lea     rdx, ds:2[rdx*2]
0x180013e06  mov     rcx, [rbp+270h+Format]
0x180013e0d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013e12  xorps   xmm0, xmm0
0x180013e15  movups  [rbp+270h+var_120], xmm0
0x180013e1c  xorps   xmm1, xmm1
0x180013e1f  movdqu  [rbp+270h+var_110], xmm1
0x180013e27  mov     r8d, 13h
0x180013e2d  lea     rdx, aAzureadprtauth; "AzureAdPrtAuthority"
0x180013e34  lea     rcx, [rbp+270h+var_120]
0x180013e3b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013e40  nop
0x180013e41  xorps   xmm0, xmm0
0x180013e44  movups  xmmword ptr [rbp+270h+Format], xmm0
0x180013e4b  xorps   xmm1, xmm1
0x180013e4e  movdqu  [rbp+270h+var_130], xmm1
0x180013e56  mov     r8d, 5
  ... truncated ...
```
