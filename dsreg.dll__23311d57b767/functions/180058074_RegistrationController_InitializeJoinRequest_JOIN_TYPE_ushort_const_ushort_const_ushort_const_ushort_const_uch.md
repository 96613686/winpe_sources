# RegistrationController::InitializeJoinRequest(_JOIN_TYPE,ushort const *,ushort const *,ushort const *,ushort const *,uchar const *,ulong,ushort const *,_DSREG_EXT_TOKEN_PROPERTIES_EX * const,_DISCOVERY_METADATA * const,_JOIN_OPERATION_CONTEXT const *,int,int,ushort const *,ushort const *,_JOIN_REQUEST * *)

- ea: `0x180058074`
- end: `0x180058e92`
- name: `?InitializeJoinRequest@RegistrationController@@QEAAJW4_JOIN_TYPE@@PEBG111PEBEK1QEAU_DSREG_EXT_TOKEN_PROPERTIES_EX@@QEAU_DISCOVERY_METADATA@@PEBU_JOIN_OPERATION_CONTEXT@@HH11PEAPEAU_JOIN_REQUEST@@@Z`
- size: `3614`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180052ba4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x18000ddf0`
- `0x18000fc20`
- `0x180011fc0`
- `0x180012948`
- `0x180012eb8`
- `0x18001f230`
- `0x1800307c4`
- `0x180032234`
- `0x18003334c`
- `0x18003e7bc`
- `0x18003fa98`
- `0x1800436a4`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x18004651c`
- `0x1800518a8`
- `0x180053e60`
- `0x180053e6c`
- `0x180055138`
- `0x18005541c`
- `0x180055a5c`
- `0x180056418`
- `0x1800565d8`
- `0x18005693c`
- `0x180056ccc`
- `0x180057bd8`
- `0x180057e64`
- `0x180058074`
- `0x18005adb8`
- `0x18005b348`
- `0x18005d774`
- `0x18005f178`
- `0x18005f7fc`
- `0x18006e14c`
- `0x180074278`
- `0x1800742e8`
- `0x180074300`
- `0x1800760f0`
- `0x18007a218`
- `0x18007a324`
- `0x18008a978`
- `0x18008af7c`
- `0x18008b6ac`
- `0x180097d14`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800588a8`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800588a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058e44`

## string_xrefs

- `0x180058523`: `CopyStringW`
- `0x180058c2e`: `GetCurrentUserSid`
- `0x1800587eb`: `GetComputerDnsHostname`
- `0x18005874e`: `CopyStringA`
- `0x180058810`: `CopyStringSafeW`
- `0x18005868a`: `CopyStringNullSafeW`
- `0x180058906`: `ByteArray::CopyTo(DevicePublicKey)`
- `0x1800587a9`: `CopyDiscoveryMetadataContent`
- `0x1800587cb`: `CopyTokenProperties`
- `0x180058199`: `pTokenProperties`
- `0x1800581b6`: `pTokenProperties`
- `0x1800582fa`: `%s: registrationInfo->pszPrecreateEndpointReference is null or empty`
- `0x180058306`: `registrationInfo->pszPrecreateEndpointReference`
- `0x1800584d1`: `ReadVdiSettingsFromRegistry`
- `0x180058a04`: `%s: RegistrationController::UpdateJoinRequestFromToken failed with error code: 0x%08x. Cannot parse the token as an ID token. The token could be an access token or encrypted. Checking if all required parameters are present...`
- `0x180058a29`: `%s: The UPN must be provided or found in the token.`
- `0x180058a52`: `%s: The tenant Id must be provided or found in the token.`
- `0x180058a81`: `%s: User SID is not provided for device join.`
- `0x180058b6b`: `RegistrationController::CreateTransportKeyNew`
- `0x180058bdc`: `RegistrationController::CreateTransportKey`
- `0x180058c81`: `RegistrationController::CreateTokenBindingAik(Software)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistrationController::InitializeJoinRequest(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        char *a7,
        unsigned int SourceSize,
        unsigned __int16 *a9,
        struct _DSREG_EXT_TOKEN_PROPERTIES_EX *a10,
        __int64 a11,
        __int64 a12,
        int a13,
        int a14,
        unsigned __int16 *a15,
        unsigned __int16 *a16,
        _JOIN_REQUEST **a17)
{
  _JOIN_REQUEST *v18; // r14
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // rdx
  _JOIN_REQUEST *v21; // rax
  __int64 v22; // rdx
  unsigned int v23; // edx
  const char *v24; // r8
  int appended; // eax
  unsigned int v26; // edx
  const char *v27; // r8
  const wchar_t *v28; // r8
  int v29; // eax
  const WCHAR *v30; // r15
  unsigned __int16 *v31; // r12
  int VdiSettingsFromRegistry; // eax
  void **v33; // r12
  const unsigned __int16 *v34; // rcx
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // rdx
  const unsigned __int16 *v37; // rdi
  char IsEnabled; // al
  const unsigned __int16 *v39; // rcx
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // rcx
  unsigned __int64 v42; // rdx
  const unsigned __int16 *v43; // rcx
  unsigned __int64 v44; // rdx
  char v45; // al
  unsigned __int16 *v46; // rdi
  const unsigned __int16 *v47; // rcx
  __int16 v48; // r8
  unsigned __int64 v49; // rdx
  const unsigned __int16 *v50; // rcx
  unsigned __int64 v51; // rdx
  const unsigned __int16 *v52; // rcx
  unsigned __int64 v53; // rdx
  const unsigned __int16 *v54; // rcx
  unsigned __int16 *v55; // rdi
  __time64_t v56; // rbx
  int updated; // eax
  __int64 v58; // rdx
  const unsigned __int16 *v59; // rcx
  const struct DevicePolicy *v60; // rax
  unsigned int KeyPolicy; // eax
  const unsigned __int16 *v62; // rdx
  int v63; // r8d
  unsigned __int16 *v64; // rdi
  int v65; // edi
  int v66; // eax
  int v67; // eax
  unsigned int v68; // edx
  WCHAR *v70; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v71; // [rsp+58h] [rbp-A8h]
  int v72; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v74; // [rsp+70h] [rbp-90h] BYREF
  int v75; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v77; // [rsp+88h] [rbp-78h]
  LPCWSTR pszKeyName; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v79; // [rsp+98h] [rbp-68h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v81; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v82; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v83; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v84; // [rsp+C0h] [rbp-40h] BYREF
  _JOIN_REQUEST *v85; // [rsp+C8h] [rbp-38h] BYREF
  BOOL v86; // [rsp+D0h] [rbp-30h]
  struct _DSREG_EXT_TOKEN_PROPERTIES_EX *v87; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v88; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v89; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int8 *v90; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v91; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v92; // [rsp+100h] [rbp+0h]
  __int64 v93; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v94; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v95; // [rsp+118h] [rbp+18h]
  char *Source; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v97; // [rsp+128h] [rbp+28h]
  struct _DISCOVERY_METADATA *v98; // [rsp+130h] [rbp+30h]
  unsigned __int16 *v99; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v100; // [rsp+140h] [rbp+40h]
  _JOIN_REQUEST **v101; // [rsp+148h] [rbp+48h]
  wchar_t Buffer; // [rsp+150h] [rbp+50h] BYREF
  char v103[110]; // [rsp+152h] [rbp+52h] BYREF

  v92 = a4;
  v77 = a3;
  v94 = a5;
  v95 = a6;
  Source = a7;
  v97 = a9;
  v87 = a10;
  v98 = (struct _DISCOVERY_METADATA *)a11;
  v93 = a12;
  v99 = a15;
  v100 = a16;
  v101 = a17;
  lpMem = 0;
  v88 = 0;
  Block = 0;
  v74 = 0;
  v90 = 0;
  v91 = 0;
  v81 = 0;
  v89 = 0;
  v70 = 0;
  pszKeyName = 0;
  v71 = 0;
  v79 = 0;
  v82 = 0;
  v83 = 0;
  memset_0(v103, 0, 0x62u);
  Buffer = 0;
  v18 = 0;
  v75 = 0;
  v72 = 0;
  hMem = 0;
  v84 = 0;
  if ( a17 )
    *a17 = 0;
  if ( a10 )
  {
    if ( !a11 )
    {
      v19 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"RegistrationController::InitializeJoinRequest",
        L"registrationInfo");
      v20 = L"registrationInfo";
      goto LABEL_5;
    }
    if ( !a17 )
    {
      v19 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"RegistrationController::InitializeJoinRequest",
        L"ppJoinRequest");
      v20 = L"ppJoinRequest";
      goto LABEL_5;
    }
    if ( !a12 )
    {
      v19 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationController::InitializeJoinRequest", L"pCtx");
      v20 = L"pCtx";
      goto LABEL_5;
    }
    if ( a2 == 11 )
    {
      if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(a11 + 152)) )
      {
        v19 = -2145648587;
        Logger::TraceError(
          L"%s: registrationInfo->pszPrecreateEndpointReference is null or empty",
          L"RegistrationController::InitializeJoinRequest");
        v20 = L"registrationInfo->pszPrecreateEndpointReference";
        goto LABEL_5;
      }
    }
    else if ( a2 - 13 <= 1 )
    {
      if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(a11 + 192)) )
      {
        v19 = -2145648587;
        Logger::TraceError(
          L"%s: registrationInfo->pszDeviceJoinResourceEndpointReference is null or empty",
          L"RegistrationController::InitializeJoinRequest");
        v20 = L"registrationInfo->pszDeviceJoinResourceEndpointReference";
        goto LABEL_5;
      }
    }
    else if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(a11 + 48)) )
    {
      v19 = -2145648587;
      Logger::TraceError(
        L"%s: registrationInfo->pszDeviceJoinEndpointReference is null or empty",
        L"RegistrationController::InitializeJoinRequest");
      v20 = L"registrationInfo->pszDeviceJoinEndpointReference";
      goto LABEL_5;
    }
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Function started. joinType: %u, pcszDomain: %s, pcszUserEmail: %s.",
      L"RegistrationController::InitializeJoinRequest",
      a2);
    v21 = (_JOIN_REQUEST *)operator new(0x2D8u, (const struct std::nothrow_t *)&std::nothrow);
    v85 = v21;
    if ( !v21 || (v18 = _JOIN_REQUEST::_JOIN_REQUEST(v21)) == 0 )
    {
      v19 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistrationController::InitializeJoinRequest");
      goto LABEL_145;
    }
    if ( a2 - 8 > 1 )
    {
      DevicePolicy::Get();
      v86 = IsDeviceJoin(a2) != 0;
      LODWORD(v85) = DevicePolicy::GetKeyPolicy(v22);
      HIDWORD(v85) = DevicePolicy::GetHardwarePolicy();
      appended = RegistrationCertHelper::GenerateCertRequest(
                   (RegistrationCertHelper *)&v85,
                   v23,
                   v24,
                   (unsigned __int8 **)&lpMem,
                   &v88,
                   (unsigned __int16 **)&Block,
                   &v74,
                   (struct ByteArray *)&v90,
                   &v75);
      v19 = appended;
      if ( appended < 0 )
      {
        v28 = L"RegistrationCertHelper::GenerateCertRequest";
        goto LABEL_25;
      }
      if ( a2 - 13 > 1 )
      {
        v30 = 0;
        v31 = 0;
      }
      else
      {
        v29 = RegistrationCertHelper::GenerateCertRequest(
                (RegistrationCertHelper *)&v85,
                v26,
                v27,
                &v81,
                &v89,
                (unsigned __int16 **)&pszKeyName,
                &v79,
                0,
                &v72);
        v19 = v29;
        if ( v29 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistrationController::InitializeJoinRequest",
            L"RegistrationCertHelper::GenerateCertRequest",
            (unsigned int)v29);
          v30 = pszKeyName;
          v70 = (WCHAR *)pszKeyName;
          v31 = v79;
          v71 = v79;
          goto LABEL_146;
        }
        v30 = pszKeyName;
        v70 = (WCHAR *)pszKeyName;
        v31 = v79;
        v71 = v79;
      }
      VdiSettingsFromRegistry = ReadVdiSettingsFromRegistry((unsigned __int16 **)v18 + 87, 1);
      v19 = VdiSettingsFromRegistry;
      if ( VdiSettingsFromRegistry < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationController::InitializeJoinRequest",
          L"ReadVdiSettingsFromRegistry",
          (unsigned int)VdiSettingsFromRegistry);
        goto LABEL_146;
      }
      if ( a2 == 11 )
      {
        v33 = (void **)((char *)v18 + 160);
        v34 = *(const unsigned __int16 **)(a11 + 152);
        v35 = -1;
        v36 = -1;
        do
          ++v36;
        while ( v34[v36] );
        appended = CopyStringW(v34, v36, (unsigned __int16 **)v18 + 20);
        v19 = appended;
        if ( appended < 0 )
        {
LABEL_37:
          v28 = L"CopyStringW";
          goto LABEL_25;
        }
        v37 = *(const unsigned __int16 **)(a11 + 144);
        goto LABEL_39;
      }
      if ( a2 - 13 <= 1 )
      {
        v33 = (void **)((char *)v18 + 160);
        v41 = *(const unsigned __int16 **)(a11 + 192);
        v35 = -1;
        v42 = -1;
        do
          ++v42;
        while ( v41[v42] );
        appended = CopyStringW(v41, v42, (unsigned __int16 **)v18 + 20);
        v19 = appended;
        if ( appended < 0 )
          goto LABEL_37;
        v37 = *(const unsigned __int16 **)(a11 + 208);
LABEL_39:
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::GetImpl'::`2'::impl);
        v39 = L"4.0";
        if ( !IsEnabled )
          v39 = L"2.0";
        v40 = v37;
        goto LABEL_42;
      }
    }
    v33 = (void **)((char *)v18 + 160);
    v43 = *(const unsigned __int16 **)(a11 + 48);
    v35 = -1;
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    appended = CopyStringW(v43, v44, (unsigned __int16 **)v18 + 20);
    v19 = appended;
    if ( appended < 0 )
      goto LABEL_37;
    if ( a2 == 15 )
    {
      v39 = L"4.0";
    }
    else if ( a2 - 8 > 1 )
    {
      v45 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::GetImpl'::`2'::impl);
      v39 = L"4.0";
      if ( !v45 )
        v39 = L"2.0";
    }
    else
    {
      v39 = L"2.0";
    }
    v40 = *(const unsigned __int16 **)(a11 + 40);
LABEL_42:
    appended = UrlHelper::NegotiateVersion(v39, v40, (unsigned __int16 **)v18 + 21);
    v19 = appended;
    if ( appended < 0 )
    {
      v28 = L"UrlHelper::NegotiateVersion";
      goto LABEL_25;
    }
    v46 = v92;
    appended = RegistrationController::AppendDeviceIdToEndpointIfRequired(a2, *((_QWORD *)v87 + 3), v93, v92, v33);
    v19 = appended;
    if ( appended < 0 )
    {
      v28 = L"RegistrationController::AppendDeviceIdToEndpointIfRequired";
      goto LABEL_25;
    }
    appended = CopyStringNullSafeW(v77, (unsigned __int16 **)v18 + 18);
    v19 = appended;
    if ( appended < 0 )
      goto LABEL_62;
    if ( !(unsigned int)IsEmptyString(v46) )
    {
      v49 = -1;
      do
        ++v49;
      while ( v46[v49] != v48 );
      appended = CopyStringW(v47, v49, (unsigned __int16 **)v18 + 29);
      v19 = appended;
      if ( appended < 0 )
        goto LABEL_37;
    }
    if ( !(unsigned int)IsEmptyString(v94) )
    {
      v51 = -1;
      do
        ++v51;
      while ( v50[v51] );
      appended = CopyStringW(v50, v51, (unsigned __int16 **)v18 + 30);
      v19 = appended;
      if ( appended < 0 )
        goto LABEL_37;
    }
    if ( !(unsigned int)IsEmptyString(v95) )
    {
      v53 = -1;
      do
        ++v53;
      while ( v52[v53] );
      appended = CopyStringW(v52, v53, (unsigned __int16 **)v18 + 31);
      v19 = appended;
      if ( appended < 0 )
        goto LABEL_37;
    }
    if ( Source )
    {
      appended = CopyStringA(Source, SourceSize, (char **)v18 + 32);
      v19 = appended;
      if ( appended < 0 )
      {
        v28 = L"CopyStringA";
        goto LABEL_25;
      }
      *((_DWORD *)v18 + 66) = SourceSize;
    }
    if ( !(unsigned int)IsEmptyString(v97) )
    {
      do
        ++v35;
      while ( v54[v35] );
      appended = CopyStringW(v54, v35, (unsigned __int16 **)v18 + 28);
      v19 = appended;
      if ( appended < 0 )
        goto LABEL_37;
    }
    appended = CopyDiscoveryMetadataContent(v98, (_JOIN_REQUEST *)((char *)v18 + 272));
    v19 = appended;
    if ( appended < 0 )
    {
      v28 = L"CopyDiscoveryMetadataContent";
      goto LABEL_25;
    }
    appended = CopyTokenProperties(v87, (_JOIN_REQUEST *)((char *)v18 + 528));
    v19 = appended;
    if ( appended < 0 )
    {
      v28 = L"CopyTokenProperties";
      goto LABEL_25;
    }
    appended = GetComputerDnsHostname(ComputerNamePhysicalDnsHostname, &v82);
    v19 = appended;
    if ( appended < 0 )
    {
LABEL_87:
      v28 = L"GetComputerDnsHostname";
      goto LABEL_25;
    }
    v55 = v82;
    appended = CopyStringSafeW(v82, (unsigned __int16 **)v18 + 81);
    v19 = appended;
    if ( appended >= 0 )
    {
      if ( (unsigned int)GetHostNameMode(a2) == 1 )
        goto LABEL_94;
      appended = CopyStringSafeW(v55, (unsigned __int16 **)v18 + 85);
      v19 = appended;
      if ( appended >= 0 )
      {
        appended = GetComputerDnsHostname(ComputerNamePhysicalDnsFullyQualified, &v83);
        v19 = appended;
        if ( appended < 0 )
          goto LABEL_87;
        appended = CopyStringSafeW(v83, (unsigned __int16 **)v18 + 86);
        v19 = appended;
        if ( appended >= 0 )
        {
LABEL_94:
          appended = GetOSVersionInfo(&Buffer, 0x32u);
          v19 = appended;
          if ( appended < 0 )
          {
            v28 = L"GetOSVersionInfo";
            goto LABEL_25;
          }
          appended = CopyStringSafeW(&Buffer, (unsigned __int16 **)v18 + 82);
          v19 = appended;
          if ( appended >= 0 )
          {
            v56 = _time64(0);
            if ( v56 < 0 )
              Logger::TraceError(
                L"%s: Cannot get system time. time() returned -1.",
                L"RegistrationController::InitializeJoinRequest");
            *((_QWORD *)v18 + 84) = v56;
            appended = ByteArray::Assign((_JOIN_REQUEST *)((char *)v18 + 24), (const unsigned __int8 *)lpMem, v88);
            v19 = appended;
            if ( appended < 0 )
            {
              v28 = L"ByteArray::Assign(DeviceCSR)";
              goto LABEL_25;
            }
            appended = ByteArray::Assign((_JOIN_REQUEST *)((char *)v18 + 40), v90, v91);
            v19 = appended;
            if ( appended < 0 )
            {
              v28 = L"ByteArray::CopyTo(DevicePublicKey)";
              goto LABEL_25;
            }
            *((_QWORD *)v18 + 1) = v74;
            v74 = 0;
            *(_QWORD *)v18 = Block;
            Block = 0;
            *((_DWORD *)v18 + 4) = v75;
            appended = ByteArray::Assign((_JOIN_REQUEST *)((char *)v18 + 80), v81, v89);
            v19 = appended;
            if ( appended < 0 )
            {
              v28 = L"ByteArray::Assign(RaCSR)";
              goto LABEL_25;
            }
            *((_QWORD *)v18 + 8) = v71;
            v71 = 0;
            *((_QWORD *)v18 + 7) = v70;
            v70 = 0;
            *((_DWORD *)v18 + 18) = v72;
            *((_DWORD *)v18 + 157) = a2;
            *((_DWORD *)v18 + 159) = a13;
            *((_DWORD *)v18 + 160) = a14;
            appended = CopyStringNullSafeW(v99, (unsigned __int16 **)v18 + 77);
            v19 = appended;
            if ( appended >= 0 )
            {
              appended = CopyStringNullSafeW(v100, (unsigned __int16 **)v18 + 19);
              v19 = appended;
              if ( appended >= 0 )
              {
                if ( a2 - 11 > 4 && a2 != 7 )
                {
                  updated = RegistrationController::UpdateJoinRequestFromToken(
                              *((const unsigned __int16 **)v18 + 19),
                              v18);
                  v19 = updated;
                  if ( updated < 0 )
                    Logger::TraceWarning(
                      (wchar_t *)L"%s: RegistrationController::UpdateJoinRequestFromToken failed with error code: 0x%08x. "
                                  "Cannot parse the token as an ID token. The token could be an access token or encrypted"
                                  ". Checking if all required parameters are present...",
                      L"RegistrationController::InitializeJoinRequest",
                      (unsigned int)updated);
                  if ( a2 != 8 && (unsigned int)IsEmptyString(*((const unsigned __int16 **)v18 + 67)) )
                  {
                    Logger::TraceError(
                      L"%s: The UPN must be provided or found in the token.",
                      L"RegistrationController::InitializeJoinRequest");
                    v19 = -2145647631;
                    goto LABEL_145;
                  }
                  if ( (unsigned int)IsEmptyString(*((const unsigned __int16 **)v18 + 69)) )
                  {
                    Logger::TraceError(
                      L"%s: The tenant Id must be provided or found in the token.",
                      L"RegistrationController::InitializeJoinRequest");
                    v19 = -2145648621;
                    goto LABEL_145;
                  }
                  if ( a2 == 1 && (unsigned int)IsEmptyString(*((const unsigned __int16 **)v18 + 68)) )
                    Logger::TraceInformation(
                      L"%s: User SID is not provided for device join.",
                      L"RegistrationController::InitializeJoinRequest");
                }
                if ( !(unsigned int)IsEmptyString(*((const unsigned __int16 **)v18 + 18))
                  || (unsigned int)IsEmptyString(*((const unsigned __int16 **)v18 + 67))
                  || (appended = GetDomainFromEmail(v59, (unsigned __int16 **)v18 + 18, 0), v19 = appended,
                                                                                            appended >= 0) )
                {
                  if ( (unsigned int)IsJoin(*((unsigned int *)v18 + 157), v58) )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EntraIdClientPlutonKsp>::GetImpl'::`2'::impl) )
                    {
                      v72 = 0;
                      appended = GeneratedKey::GetKeyStorageProvider(v18, (enum _KEY_STORAGE_PROVIDER *)&v72);
                      v19 = appended;
                      if ( appended < 0 )
                      {
                        v28 = L"GeneratedKey::GetKeyStorageProvider";
                        goto LABEL_25;
                      }
                      appended = RegistrationController::CreateTransportKeyNew(
                                   *((_QWORD *)v18 + 69),
                                   *((_QWORD *)v18 + 67),
                                   *((unsigned int *)v18 + 157),
                                   (unsigned int)v72,
                                   (char *)v18 + 624,
                                   (char *)v18 + 176,
                                   (char *)v18 + 208,
                                   (char *)v18 + 192);
                      v19 = appended;
                      if ( appended < 0 )
                      {
                        v28 = L"RegistrationController::CreateTransportKeyNew";
                        goto LABEL_25;
                      }
                    }
                    else
                    {
                      DevicePolicy::Get();
                      v60 = DevicePolicy::Get();
                      KeyPolicy = DevicePolicy::GetKeyPolicy(v60);
                      appended = RegistrationController::CreateTransportKey(
                                   *((_QWORD *)v18 + 69),
                                   *((_QWORD *)v18 + 67),
                                   *((unsigned int *)v18 + 157),
                                   KeyPolicy);
                      v19 = appended;
                      if ( appended < 0 )
                      {
                        v28 = L"RegistrationController::CreateTransportKey";
                        goto LABEL_25;
                      }
                    }
                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::GetImpl'::`2'::impl)
                      && (unsigned int)UrlHelper::IsVersionEqualOrGreater(*((wchar_t **)v18 + 21), v62) )
                    {
                      if ( (unsigned int)(*((_DWORD *)v18 + 157) - 5) <= 1 )
                      {
                        appended = GetCurrentUserSid((LPWSTR *)&hMem);
                        v19 = appended;
                        if ( appended < 0 )
                        {
                          v28 = L"GetCurrentUserSid";
                          goto LABEL_25;
                        }
                      }
                      appended = ByteArray::GetEncodedHash((_JOIN_REQUEST *)((char *)v18 + 40), &v84, v63);
                      v19 = appended;
                      if ( appended < 0 )
                      {
                        v28 = L"ByteArray::GetEncodedHash";
                        goto LABEL_25;
                      }
                      v64 = v84;
                      appended = RegistrationController::CreateTokenBindingAik(
                                   0,
                                   v84,
                                   *((_QWORD *)v18 + 69),
                                   hMem,
                                   (char *)v18 + 96);
                      v19 = appended;
                      if ( appended < 0 )
                      {
                        v28 = L"RegistrationController::CreateTokenBindingAik(Software)";
                        goto LABEL_25;
                      }
                      RegistrationController::CreateTokenBindingAik(
                        1,
                        v64,
                        *((_QWORD *)v18 + 69),
                        hMem,
                        (char *)v18 + 112);
                      RegistrationController::CreateTokenBindingAik(
                        2,
                        v64,
                        *((_QWORD *)v18 + 69),
                        hMem,
                        (char *)v18 + 128);
                    }
                  }
                  *v101 = v18;
                  if ( (v19 & 0x80000000) == 0 )
                  {
                    Logger::WriteInitJoinRequestSuccessEvent(a2, v77);
                    v18 = 0;
                    goto LABEL_156;
                  }
                  v18 = 0;
                  goto LABEL_145;
                }
                v28 = L"GetDomainFromEmail";
LABEL_25:
                Logger::TraceError(
                  L"%s: %s failed with error code: 0x%08x.",
                  L"RegistrationController::InitializeJoinRequest",
                  v28,
                  (unsigned int)appended);
                goto LABEL_145;
              }
            }
LABEL_62:
            v28 = L"CopyStringNullSafeW";
            goto LABEL_25;
          }
        }
      }
    }
    v28 = L"CopyStringSafeW";
    goto LABEL_25;
  }
  v19 = -2147024809;
  Logger::TraceError(
    L"%s: \"%s\" should not be null.",
    L"RegistrationController::InitializeJoinRequest",
    L"pTokenProperties");
  v20 = L"pTokenProperties";
LABEL_5:
  Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationController::InitializeJoinRequest", v20);
LABEL_145:
  v31 = v71;
  v30 = v70;
LABEL_146:
  Logger::WriteInitJoinRequestFailureEvent(v19, a2, v77);
  v65 = IsDeviceJoin(a2);
  if ( v18 )
  {
    _JOIN_REQUEST::DeleteGeneratedKeys(v18);
  }
  else
  {
    if ( !(unsigned int)IsEmptyString(v74) && !(unsigned int)IsEmptyString((const unsigned __int16 *)Block) )
    {
      Logger::TraceInformation(L"%s: Deleting generated device key", L"RegistrationController::InitializeJoinRequest");
      v66 = RegistrationKeyHelper::DeleteKey(v74, (LPCWSTR)Block, v65);
      if ( v66 < 0 )
        Logger::TraceWarning(
          (wchar_t *)L"%s: Deleting device key failed with error 0x%08x. Ignoring.",
          L"RegistrationController::InitializeJoinRequest",
          (unsigned int)v66);
    }
    if ( !(unsigned int)IsEmptyString(v31) && !(unsigned int)IsEmptyString(v30) )
    {
      Logger::TraceInformation(
        L"%s: Deleting generated resource account key",
        L"RegistrationController::InitializeJoinRequest");
      v67 = RegistrationKeyHelper::DeleteKey(v31, v30, v65);
      if ( v67 < 0 )
        Logger::TraceWarning(
          (wchar_t *)L"%s: Deleting resource account key failed with error 0x%08x. Ignoring.",
          L"RegistrationController::InitializeJoinRequest",
          (unsigned int)v67);
    }
  }
LABEL_156:
  operator delete(Block);
  operator delete(v74);
  SafeFree(lpMem);
  operator delete(v70);
  operator delete(v71);
  SafeFree(v81);
  SafeFree(v82);
  SafeFree(v83);
  if ( v18 )
    _JOIN_REQUEST::`scalar deleting destructor'(v18, v68);
  SafeFree(v84);
  LocalFree(hMem);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationController::InitializeJoinRequest", v19);
  ByteArray::Reset((ByteArray *)&v90);
  return v19;
}

```

## disassembly

```asm
0x180058074  mov     [rsp-8+arg_0], rbx
0x180058079  push    rbp
0x18005807a  push    rsi
0x18005807b  push    rdi
0x18005807c  push    r12
0x18005807e  push    r13
0x180058080  push    r14
0x180058082  push    r15
0x180058084  lea     rbp, [rsp-0D0h]
0x18005808c  sub     rsp, 1D0h
0x180058093  mov     rax, cs:__security_cookie
0x18005809a  xor     rax, rsp
0x18005809d  mov     [rbp+100h+var_40], rax
0x1800580a4  mov     [rbp+100h+var_100], r9
0x1800580a8  mov     [rbp+100h+var_178], r8
0x1800580ac  mov     r13d, edx
0x1800580af  mov     rax, [rbp+100h+arg_20]
0x1800580b6  mov     [rbp+100h+var_F0], rax
0x1800580ba  mov     rcx, [rbp+100h+arg_28]
0x1800580c1  mov     [rbp+100h+var_E8], rcx
0x1800580c5  mov     rax, [rbp+100h+arg_30]
0x1800580cc  mov     [rbp+100h+Source], rax
0x1800580d0  mov     rax, [rbp+100h+arg_40]
0x1800580d7  mov     [rbp+100h+var_D8], rax
0x1800580db  mov     rsi, [rbp+100h+arg_48]
0x1800580e2  mov     [rbp+100h+var_128], rsi
0x1800580e6  mov     rdi, [rbp+100h+arg_50]
0x1800580ed  mov     [rbp+100h+var_D0], rdi
0x1800580f1  mov     rbx, [rbp+100h+arg_58]
0x1800580f8  mov     [rbp+100h+var_F8], rbx
0x1800580fc  mov     rax, [rbp+100h+arg_70]
0x180058103  mov     [rbp+100h+var_C8], rax
0x180058107  mov     rax, [rbp+100h+arg_78]
0x18005810e  mov     [rbp+100h+var_C0], rax
0x180058112  mov     r15, [rbp+100h+arg_80]
0x180058119  mov     [rbp+100h+var_B8], r15
0x18005811d  xor     ecx, ecx
0x18005811f  mov     [rbp+100h+lpMem], rcx
0x180058123  mov     [rbp+100h+var_120], rcx
0x180058127  mov     [rsp+200h+Block], rcx
0x18005812c  mov     [rsp+200h+var_190], rcx
0x180058131  mov     [rbp+100h+var_110], rcx
0x180058135  mov     [rbp+100h+var_108], rcx
0x180058139  mov     [rbp+100h+var_158], rcx
0x18005813d  mov     [rbp+100h+var_118], rcx
0x180058141  mov     [rsp+200h+var_1B0], rcx
0x180058146  mov     [rbp+100h+pszKeyName], rcx
0x18005814a  mov     [rsp+200h+var_1A8], rcx
0x18005814f  mov     [rbp+100h+var_168], rcx
0x180058153  xor     r12d, r12d
0x180058156  mov     [rbp+100h+var_150], r12
0x18005815a  mov     [rbp+100h+var_148], r12
0x18005815e  xor     edx, edx; Val
0x180058160  lea     r8d, [rcx+62h]; Size
0x180058164  lea     rcx, [rbp+100h+var_AE]; void *
0x180058168  call    memset_0
0x18005816d  mov     [rbp+100h+Buffer], r12w
0x180058172  mov     r14d, r12d
0x180058175  mov     [rsp+200h+var_188], r12d
0x18005817a  mov     [rsp+200h+var_1A0], r12d
0x18005817f  mov     [rbp+100h+hMem], r12
0x180058183  mov     [rbp+100h+var_140], r12
0x180058187  test    r15, r15
0x18005818a  jz      short loc_18005818F
0x18005818c  mov     [r15], r12
0x18005818f  test    rsi, rsi
0x180058192  jnz     short loc_1800581CA
0x180058194  mov     ebx, 80070057h
0x180058199  lea     r8, aPtokenproperti_1; "pTokenProperties"
0x1800581a0  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x1800581a7  mov     rdx, rsi
0x1800581aa  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800581b1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800581b6  lea     rdx, aPtokenproperti_1; "pTokenProperties"
0x1800581bd  mov     rcx, rsi; unsigned __int16 *
0x1800581c0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800581c5  jmp     loc_180058D0C
0x1800581ca  test    rdi, rdi
0x1800581cd  jnz     short loc_1800581FA
0x1800581cf  mov     ebx, 80070057h
0x1800581d4  lea     r8, aRegistrationin_0; "registrationInfo"
0x1800581db  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x1800581e2  mov     rdx, rsi
0x1800581e5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800581ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800581f1  lea     rdx, aRegistrationin_0; "registrationInfo"
0x1800581f8  jmp     short loc_1800581BD
0x1800581fa  test    r15, r15
0x1800581fd  jnz     short loc_18005822A
0x1800581ff  mov     ebx, 80070057h
0x180058204  lea     r8, aPpjoinrequest; "ppJoinRequest"
0x18005820b  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x180058212  mov     rdx, rsi
0x180058215  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005821c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180058221  lea     rdx, aPpjoinrequest; "ppJoinRequest"
0x180058228  jmp     short loc_1800581BD
0x18005822a  test    rbx, rbx
0x18005822d  jnz     short loc_18005825D
0x18005822f  mov     ebx, 80070057h
0x180058234  lea     r8, aPctx; "pCtx"
0x18005823b  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x180058242  mov     rdx, rsi
0x180058245  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005824c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180058251  lea     rdx, aPctx; "pCtx"
0x180058258  jmp     loc_1800581BD
0x18005825d  cmp     r13d, 0Bh
0x180058261  jz      short loc_1800582DB
0x180058263  lea     eax, [r13-0Dh]
0x180058267  cmp     eax, 1
0x18005826a  jbe     short loc_1800582A4
0x18005826c  mov     rcx, [rdi+30h]; unsigned __int16 *
0x180058270  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180058275  test    eax, eax
0x180058277  jz      loc_180058312
0x18005827d  mov     ebx, 801C0035h
0x180058282  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x180058289  mov     rdx, rsi
0x18005828c  lea     rcx, aSRegistrationi_0; "%s: registrationInfo->pszDeviceJoinEndp"...
0x180058293  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180058298  lea     rdx, aRegistrationin_2; "registrationInfo->pszDeviceJoinEndpoint"...
0x18005829f  jmp     loc_1800581BD
0x1800582a4  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x1800582ab  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800582b0  test    eax, eax
0x1800582b2  jz      short loc_180058312
0x1800582b4  mov     ebx, 801C0035h
0x1800582b9  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x1800582c0  mov     rdx, rsi
0x1800582c3  lea     rcx, aSRegistrationi_1; "%s: registrationInfo->pszDeviceJoinReso"...
0x1800582ca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800582cf  lea     rdx, aRegistrationin_1; "registrationInfo->pszDeviceJoinResource"...
0x1800582d6  jmp     loc_1800581BD
0x1800582db  mov     rcx, [rdi+98h]; unsigned __int16 *
0x1800582e2  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800582e7  test    eax, eax
0x1800582e9  jz      short loc_180058312
0x1800582eb  mov     ebx, 801C0035h
0x1800582f0  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x1800582f7  mov     rdx, rsi
0x1800582fa  lea     rcx, aSRegistrationi; "%s: registrationInfo->pszPrecreateEndpo"...
0x180058301  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180058306  lea     rdx, aRegistrationin; "registrationInfo->pszPrecreateEndpointR"...
0x18005830d  jmp     loc_1800581BD
0x180058312  lea     r9, cchOriginalDestLength
0x180058319  mov     rax, r9
0x18005831c  cmp     [rsi+8], r12
0x180058320  cmovnz  rax, [rsi+8]
0x180058325  mov     rcx, [rbp+100h+var_178]
0x180058329  test    rcx, rcx
0x18005832c  cmovnz  r9, rcx
0x180058330  mov     [rsp+200h+var_1E0], rax
0x180058335  mov     r8d, r13d
0x180058338  lea     rsi, aRegistrationco_10; "RegistrationController::InitializeJoinR"...
0x18005833f  mov     rdx, rsi
0x180058342  lea     rcx, aSFunctionStart; "%s: Function started. joinType: %u, pcs"...
0x180058349  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005834e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180058355  mov     ecx, 2D8h; unsigned __int64
0x18005835a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005835f  mov     [rbp+100h+var_138], rax
0x180058363  test    rax, rax
0x180058366  jz      loc_180058CF8
0x18005836c  mov     rcx, rax; this
0x18005836f  call    ??0_JOIN_REQUEST@@QEAA@XZ; _JOIN_REQUEST::_JOIN_REQUEST(void)
0x180058374  mov     r14, rax
0x180058377  test    rax, rax
0x18005837a  jz      loc_180058CF8
0x180058380  lea     eax, [r13-8]
0x180058384  cmp     eax, 1
0x180058387  jbe     loc_1800585C1
0x18005838d  call    ?Get@DevicePolicy@@SAAEBV1@XZ; DevicePolicy::Get(void)
0x180058392  mov     rdx, rax
0x180058395  mov     ecx, r13d
0x180058398  call    ?IsDeviceJoin@@YAHW4_JOIN_TYPE@@@Z; IsDeviceJoin(_JOIN_TYPE)
0x18005839d  mov     ecx, r12d
0x1800583a0  test    eax, eax
0x1800583a2  setnz   cl
0x1800583a5  mov     [rbp+100h+var_130], ecx
0x1800583a8  mov     rcx, rdx
0x1800583ab  call    ?GetKeyPolicy@DevicePolicy@@QEBA?AW4_KEY_POLICY@@XZ; DevicePolicy::GetKeyPolicy(void)
0x1800583b0  mov     dword ptr [rbp+100h+var_138], eax
0x1800583b3  call    ?GetHardwarePolicy@DevicePolicy@@QEBA?AW4_HARDWARE_POLICY@@XZ; DevicePolicy::GetHardwarePolicy(void)
0x1800583b8  mov     dword ptr [rbp+100h+var_138+4], eax
0x1800583bb  lea     rax, [rsp+200h+var_188]
0x1800583c0  mov     [rsp+200h+var_1C0], rax; int *
0x1800583c5  lea     rax, [rbp+100h+var_110]
0x1800583c9  mov     [rsp+200h+var_1C8], rax; struct ByteArray *
0x1800583ce  lea     rax, [rsp+200h+var_190]
0x1800583d3  mov     [rsp+200h+var_1D0], rax; unsigned __int16 **
0x1800583d8  lea     rax, [rsp+200h+Block]
0x1800583dd  mov     [rsp+200h+var_1D8], rax; unsigned __int16 **
0x1800583e2  lea     rax, [rbp+100h+var_120]
0x1800583e6  mov     [rsp+200h+var_1E0], rax; unsigned __int64 *
0x1800583eb  lea     r9, [rbp+100h+lpMem]; unsigned __int8 **
0x1800583ef  lea     rcx, [rbp+100h+var_138]; this
0x1800583f3  call    ?GenerateCertRequest@RegistrationCertHelper@@QEAAJKPEBDPEAPEAEPEA_KPEAPEAG3PEAVByteArray@@PEAH@Z; RegistrationCertHelper::GenerateCertRequest(ulong,char const *,uchar * *,unsigned __int64 *,ushort * *,ushort * *,ByteArray *,int *)
0x1800583f8  mov     ebx, eax
0x1800583fa  test    eax, eax
0x1800583fc  jns     short loc_18005841C
0x1800583fe  lea     r8, aRegistrationce_18; "RegistrationCertHelper::GenerateCertReq"...
0x180058405  mov     r9d, eax
0x180058408  mov     rdx, rsi
0x18005840b  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180058412  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180058417  jmp     loc_180058D0C
0x18005841c  lea     eax, [r13-0Dh]
0x180058420  cmp     eax, 1
0x180058423  ja      loc_1800584AA
0x180058429  lea     rax, [rsp+200h+var_1A0]
0x18005842e  mov     [rsp+200h+var_1C0], rax; int *
0x180058433  mov     [rsp+200h+var_1C8], r12; struct ByteArray *
0x180058438  lea     rax, [rbp+100h+var_168]
0x18005843c  mov     [rsp+200h+var_1D0], rax; unsigned __int16 **
0x180058441  lea     rax, [rbp+100h+pszKeyName]
0x180058445  mov     [rsp+200h+var_1D8], rax; unsigned __int16 **
0x18005844a  lea     rax, [rbp+100h+var_118]
0x18005844e  mov     [rsp+200h+var_1E0], rax; unsigned __int64 *
0x180058453  lea     r9, [rbp+100h+var_158]; unsigned __int8 **
0x180058457  lea     rcx, [rbp+100h+var_138]; this
0x18005845b  call    ?GenerateCertRequest@RegistrationCertHelper@@QEAAJKPEBDPEAPEAEPEA_KPEAPEAG3PEAVByteArray@@PEAH@Z; RegistrationCertHelper::GenerateCertRequest(ulong,char const *,uchar * *,unsigned __int64 *,ushort * *,ushort * *,ByteArray *,int *)
0x180058460  mov     ebx, eax
0x180058462  test    eax, eax
0x180058464  jns     short loc_180058496
0x180058466  mov     r9d, eax
0x180058469  lea     r8, aRegistrationce_18; "RegistrationCertHelper::GenerateCertReq"...
0x180058470  mov     rdx, rsi
0x180058473  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005847a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005847f  mov     r15, [rbp+100h+pszKeyName]
0x180058483  mov     [rsp+200h+var_1B0], r15
0x180058488  mov     r12, [rbp+100h+var_168]
0x18005848c  mov     [rsp+200h+var_1A8], r12
0x180058491  jmp     loc_180058D16
0x180058496  mov     r15, [rbp+100h+pszKeyName]
0x18005849a  mov     [rsp+200h+var_1B0], r15
0x18005849f  mov     r12, [rbp+100h+var_168]
0x1800584a3  mov     [rsp+200h+var_1A8], r12
0x1800584a8  jmp     short loc_1800584B4
0x1800584aa  mov     r15, [rsp+200h+var_1B0]
0x1800584af  mov     r12, [rsp+200h+var_1A8]
0x1800584b4  lea     rcx, [r14+2B8h]; unsigned __int16 **
0x1800584bb  mov     edx, 1; int
0x1800584c0  call    ?ReadVdiSettingsFromRegistry@@YAJAEAU_VDI_SETTINGS@@H@Z; ReadVdiSettingsFromRegistry(_VDI_SETTINGS &,int)
0x1800584c5  mov     ebx, eax
0x1800584c7  xor     r8d, r8d
0x1800584ca  test    eax, eax
0x1800584cc  jns     short loc_1800584EC
0x1800584ce  mov     r9d, eax
0x1800584d1  lea     r8, aReadvdisetting; "ReadVdiSettingsFromRegistry"
0x1800584d8  mov     rdx, rsi
0x1800584db  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800584e2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800584e7  jmp     loc_180058D16
0x1800584ec  cmp     r13d, 0Bh
0x1800584f0  jnz     loc_18005857B
0x1800584f6  lea     r12, [r14+0A0h]
0x1800584fd  mov     rcx, [rdi+98h]; Source
0x180058504  or      r15, 0FFFFFFFFFFFFFFFFh
0x180058508  mov     rdx, r15
0x18005850b  inc     rdx; unsigned __int64
0x18005850e  cmp     [rcx+rdx*2], r8w
0x180058513  jnz     short loc_18005850B
0x180058515  mov     r8, r12; unsigned __int16 **
0x180058518  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18005851d  mov     ebx, eax
0x18005851f  test    eax, eax
0x180058521  jns     short loc_18005852F
0x180058523  lea     r8, aCopystringw; "CopyStringW"
0x18005852a  jmp     loc_180058405
0x18005852f  mov     rdi, [rdi+90h]
0x180058536  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport> `wil::Feature<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::GetImpl(void)'::`2'::impl
0x18005853d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADJoinWithTokenBindingSupport>::__private_IsEnabled(void)
0x180058542  lea     rdx, a20; "2.0"
0x180058549  lea     rcx, a40; "4.0"
0x180058550  test    al, al
0x180058552  cmovz   rcx, rdx; Source
0x180058556  mov     rdx, rdi; unsigned __int16 *
0x180058559  lea     r8, [r14+0A8h]; unsigned __int16 **
0x180058560  call    ?NegotiateVersion@UrlHelper@@SAJPEBG0PEAPEAG@Z; UrlHelper::NegotiateVersion(ushort const *,ushort const *,ushort * *)
0x180058565  mov     ebx, eax
0x180058567  test    eax, eax
0x180058569  jns     loc_18005863C
0x18005856f  lea     r8, aUrlhelperNegot; "UrlHelper::NegotiateVersion"
0x180058576  jmp     loc_180058405
0x18005857b  lea     eax, [r13-0Dh]
0x18005857f  cmp     eax, 1
0x180058582  ja      short loc_1800585C4
0x180058584  lea     r12, [r14+0A0h]
0x18005858b  mov     rcx, [rdi+0C0h]; Source
0x180058592  or      r15, 0FFFFFFFFFFFFFFFFh
0x180058596  mov     rdx, r15
0x180058599  inc     rdx; unsigned __int64
0x18005859c  cmp     [rcx+rdx*2], r8w
0x1800585a1  jnz     short loc_180058599
0x1800585a3  mov     r8, r12; unsigned __int16 **
0x1800585a6  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x1800585ab  mov     ebx, eax
0x1800585ad  test    eax, eax
  ... truncated ...
```
