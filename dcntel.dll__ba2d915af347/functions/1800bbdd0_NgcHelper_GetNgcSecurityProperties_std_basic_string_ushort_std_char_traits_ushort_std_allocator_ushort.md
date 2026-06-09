# NgcHelper::GetNgcSecurityProperties(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800bbdd0`
- end: `0x1800bd080`
- name: `?GetNgcSecurityProperties@NgcHelper@@UEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `4784`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ef60`
- `0x1800c9810`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180011cc4`
- `0x180011ce4`
- `0x180014f2c`
- `0x1800157b8`
- `0x180015fd4`
- `0x180016748`
- `0x180016db0`
- `0x18001702c`
- `0x180019970`
- `0x180019d1c`
- `0x18001c194`
- `0x18001c210`
- `0x180021fe4`
- `0x18009ee9c`
- `0x1800a268c`
- `0x1800b9118`
- `0x1800b9374`
- `0x1800b96b4`
- `0x1800b9f30`
- `0x1800ba42c`
- `0x1800bbdd0`
- `0x1800bd088`
- `0x1800bd360`
- `0x1800bd5e0`
- `0x1800bd6ac`
- `0x1800bd8f4`
- `0x1800bd984`
- `0x1800bdc00`
- `0x1800bdcf0`
- `0x1800bddf4`
- `0x1800bde4c`
- `0x1800bde90`
- `0x1800bdffc`
- `0x1800be3a8`
- `0x1800be424`
- `0x1800d2d18`
- `0x1800d2de8`
- `0x1800d2e7c`
- `0x1800d3474`
- `0x1800db0cc`
- `0x1800db1a4`
- `0x1800db520`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc89d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bccab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bce3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcf30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcf90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd02e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bccab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bce3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcf30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcf90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd02e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd03d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bc317`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bc317`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bcd4e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bcd4e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bcd1d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bcd1d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bccd1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bccd1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bcc33`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bcc33`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800bc126`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800bc126`
- `ncrypt!NCryptGetProperty` at `0x1800bc16d`
- `ncrypt!NCryptGetProperty` at `0x1800bc16d`
- `ncrypt!NCryptFreeObject` at `0x1800bc13a`
- `ncrypt!NCryptFreeObject` at `0x1800bc189`
- `ncrypt!NCryptFreeObject` at `0x1800bc13a`
- `ncrypt!NCryptFreeObject` at `0x1800bc189`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bc864`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bc864`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800bc8f8`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800bc8f8`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x1800bcd68`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioGetEnrolledFactors` at `0x1800bcd68`
- `TpmCoreProvisioning!TpmIsLockedOut` at `0x1800bc1c7`
- `TpmCoreProvisioning!TpmIsLockedOut` at `0x1800bc1c7`
- `cryptngc!NgcQueryEnabled` at `0x1800bc9a0`
- `cryptngc!NgcQueryEnabled` at `0x1800bc9a0`
- `cryptngc!NgcFreeEnumState` at `0x1800bcf44`
- `cryptngc!NgcFreeEnumState` at `0x1800bcf58`
- `cryptngc!NgcFreeEnumState` at `0x1800bcf44`
- `cryptngc!NgcFreeEnumState` at `0x1800bcf58`
- `cryptngc!NgcEnumContainers` at `0x1800bce01`
- `cryptngc!NgcEnumContainers` at `0x1800bce01`
- `cryptngc!NgcGetKeyImplType` at `0x1800bcb63`
- `cryptngc!NgcGetKeyImplType` at `0x1800bcb63`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800bcab9`
- `cryptngc!NgcEnumUserIdKeys` at `0x1800bcab9`
- `cryptngc!NgcQueryHardwarePolicy` at `0x1800bca38`
- `cryptngc!NgcQueryHardwarePolicy` at `0x1800bca38`
- `cryptngc!NgcGetUserIdKeyCertificate` at `0x1800bcba9`
- `cryptngc!NgcGetUserIdKeyCertificate` at `0x1800bcba9`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x1800bceca`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x1800bceca`

## string_xrefs

- `0x1800bbfe0`: `ntdll.dll`
- `0x1800bbe94`: `policymanager.dll`
- `0x1800bc48d`: `LastLoggedOnUserSID`
- `0x1800bcc8a`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bccec`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bcd2f`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bcd7a`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bce98`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`
- `0x1800bc363`: `SYSTEM\CurrentControlSet\Services\TPM\ClearInfo`
- `0x1800bc344`: `SYSTEM\CurrentControlSet\Services\TPM\WMI\ProvisionInfo`
- `0x1800bc38a`: `LastClearCommandTimestamp`
- `0x1800bbf70`: `cryptngc.dll`
- `0x1800bbf04`: `tpmcoreprovisioning.dll`
- `0x1800bc8cf`: `NgcHelper::GetNgcSecurityProperties`
- `0x1800bcf71`: `NgcHelper::GetNgcSecurityProperties`
- `0x1800bc8c2`: `ConvertStringSidToSidW failed to convert string %ws to SID [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall NgcHelper::GetNgcSecurityProperties(__int64 a1, _QWORD *a2, __int64 a3)
{
  _DWORD *v3; // rax
  __int64 v4; // rbx
  char v5; // r15
  __int64 v6; // rbx
  char v7; // si
  __int64 v8; // rbx
  char v9; // di
  __int64 v10; // rbx
  char v11; // al
  bool *v12; // rdx
  bool *v13; // rdx
  SECURITY_STATUS v14; // eax
  bool *v15; // rdx
  NCRYPT_PROV_HANDLE v16; // rcx
  SECURITY_STATUS Property; // eax
  bool v18; // bl
  const unsigned __int16 *v19; // r8
  int StateSeparatedRegistryLocation; // eax
  struct _FILETIME v21; // rbx
  int RegistryKeyDWORD64; // r15d
  const unsigned __int16 *v23; // r8
  int v24; // eax
  HLOCAL v25; // rsi
  unsigned __int64 v26; // rcx
  bool v27; // al
  bool v28; // cl
  int v29; // eax
  int ProfileSids2; // eax
  wchar_t *v31; // r15
  wchar_t *v32; // rbx
  __int64 v33; // r9
  wchar_t **v34; // rax
  wchar_t *v35; // r15
  wchar_t *i; // rbx
  const wchar_t *v37; // rdx
  size_t v38; // r8
  const wchar_t *v39; // rcx
  wchar_t *v40; // r15
  wchar_t *j; // rbx
  const wchar_t *v42; // rdx
  size_t v43; // r8
  const wchar_t *v44; // rcx
  wchar_t *v45; // r13
  const wchar_t *v46; // rdx
  size_t v47; // r8
  const wchar_t *v48; // rcx
  wchar_t *v49; // r13
  wchar_t *v50; // r13
  wchar_t *k; // r15
  wchar_t *v52; // r13
  wchar_t *v53; // r15
  wchar_t *v54; // rbx
  wchar_t *v55; // r15
  wchar_t *v56; // r13
  wchar_t *v57; // rbx
  wchar_t *v58; // rbx
  char v59; // di
  __int64 v60; // rdx
  __int64 v61; // r15
  __int64 v62; // r15
  const WCHAR *v63; // rcx
  BOOL v64; // r13d
  void *v65; // rcx
  signed int LastError; // eax
  int v67; // eax
  const WCHAR *v68; // rax
  const WCHAR *v69; // rcx
  int v70; // eax
  const WCHAR *v71; // rcx
  const WCHAR *v72; // r9
  int v73; // r13d
  void *v74; // rcx
  __int64 v75; // rdx
  __int64 v76; // r13
  int UserIdKeyCertificate; // eax
  bool *v78; // r9
  HLOCAL v79; // rcx
  HLOCAL v80; // rcx
  void *v81; // r13
  int EnrolledFactors; // eax
  const char *v83; // r9
  __int64 v84; // rdx
  char v85; // cl
  const WCHAR *v86; // rcx
  int v87; // eax
  unsigned int v88; // edx
  bool v89; // r13
  void *v90; // rcx
  char v91; // cl
  const WCHAR *v92; // rcx
  unsigned __int16 *v93; // rcx
  HLOCAL v94; // rcx
  void *v95; // rcx
  HLOCAL v96; // rdi
  DWORD *pcbResult; // [rsp+20h] [rbp-2B8h]
  const char *dwFlags; // [rsp+28h] [rbp-2B0h]
  const char *v100; // [rsp+30h] [rbp-2A8h] BYREF
  BYTE pbOutput[4]; // [rsp+38h] [rbp-2A0h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-298h] BYREF
  DWORD v103; // [rsp+48h] [rbp-290h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-288h] BYREF
  wchar_t *S1[2]; // [rsp+58h] [rbp-280h] BYREF
  wchar_t *v106; // [rsp+68h] [rbp-270h]
  int v107; // [rsp+70h] [rbp-268h] BYREF
  int v108; // [rsp+74h] [rbp-264h]
  int v109; // [rsp+78h] [rbp-260h]
  __int16 v110; // [rsp+7Ch] [rbp-25Ch]
  __int64 v111; // [rsp+80h] [rbp-258h]
  int v112; // [rsp+88h] [rbp-250h]
  __int16 v113; // [rsp+8Ch] [rbp-24Ch]
  __int64 v114; // [rsp+90h] [rbp-248h]
  char v115; // [rsp+98h] [rbp-240h]
  __int128 v116; // [rsp+A0h] [rbp-238h] BYREF
  __int64 v117; // [rsp+B0h] [rbp-228h]
  __int64 v118; // [rsp+C0h] [rbp-218h] BYREF
  void ***v119; // [rsp+C8h] [rbp-210h] BYREF
  int v120; // [rsp+D0h] [rbp-208h] BYREF
  int v121; // [rsp+D4h] [rbp-204h] BYREF
  int v122; // [rsp+D8h] [rbp-200h] BYREF
  int v123; // [rsp+DCh] [rbp-1FCh] BYREF
  int v124; // [rsp+E0h] [rbp-1F8h] BYREF
  int v125; // [rsp+E4h] [rbp-1F4h] BYREF
  HLOCAL v126; // [rsp+E8h] [rbp-1F0h] BYREF
  HLOCAL v127; // [rsp+F0h] [rbp-1E8h]
  unsigned __int16 *v128; // [rsp+F8h] [rbp-1E0h] BYREF
  HLOCAL v129; // [rsp+100h] [rbp-1D8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+108h] [rbp-1D0h] BYREF
  unsigned __int64 v131; // [rsp+110h] [rbp-1C8h] BYREF
  unsigned __int64 v132; // [rsp+118h] [rbp-1C0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+120h] [rbp-1B8h] BYREF
  HLOCAL v134; // [rsp+128h] [rbp-1B0h]
  _BYTE v135[24]; // [rsp+130h] [rbp-1A8h] BYREF
  char v136[232]; // [rsp+148h] [rbp-190h] BYREF
  wchar_t *S2[2]; // [rsp+230h] [rbp-A8h] BYREF
  __int64 v138; // [rsp+240h] [rbp-98h]
  unsigned __int64 v139; // [rsp+248h] [rbp-90h]
  void **p_phProvider; // [rsp+250h] [rbp-88h] BYREF
  PSID Sid; // [rsp+258h] [rbp-80h] BYREF
  char v142; // [rsp+260h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v134 = a2;
  v127 = a2;
  if ( a2[3] )
  {
    if ( a2[3] <= 7u )
      v3 = a2;
    else
      v3 = (_DWORD *)*a2;
    a2[2] = 1;
    *v3 = 35;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      1u,
      a3,
      L"#");
  }
  v4 = std::string::string(&p_phProvider, &dword_1801B3FA4);
  *(_OWORD *)S2 = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S2, L"policymanager.dll", 17u);
  v5 = IsApiAvailable(S2, v4);
  BYTE2(v100) = v5;
  v6 = std::string::string(&p_phProvider, &dword_1801B3FA4);
  *(_OWORD *)S2 = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S2, L"tpmcoreprovisioning.dll", 23u);
  v7 = IsApiAvailable(S2, v6);
  v8 = std::string::string(&p_phProvider, &dword_1801B3FA4);
  *(_OWORD *)S2 = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S2, L"cryptngc.dll", 12u);
  v9 = IsApiAvailable(S2, v8);
  v119 = &p_phProvider;
  v10 = std::string::string(&p_phProvider, "RtlGetPersistedStateLocation");
  *(_OWORD *)S2 = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S2, L"ntdll.dll", 9u);
  v11 = IsApiAvailable(S2, v10);
  if ( !v9 || !v11 )
    return 0;
  BYTE1(v100) = v5;
  memset_0(&v107, 0, 0x48u);
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  if ( (int)Utils::GetTpmVersion() > 0 )
  {
    LOWORD(v107) = 257;
    LOBYTE(v100) = 0;
    if ( (int)PolicyManager::IsExcludeTpm12PolicySet((PolicyManager *)&v100, v12) >= 0 )
    {
      BYTE2(v108) = (_BYTE)v100;
      HIBYTE(v108) = 1;
    }
    LOBYTE(v100) = 0;
    if ( (int)NgcUtils::IsInsecureTpm((NgcUtils *)&v100, v13) >= 0 )
    {
      LOBYTE(v108) = (_BYTE)v100;
      BYTE1(v108) = 1;
    }
    phProvider = 0;
    v14 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
    v16 = phProvider;
    if ( v14 < 0
      || (*(_DWORD *)pbOutput = 0,
          v103 = 0,
          Property = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED", pbOutput, 4u, &v103, 0),
          v16 = phProvider,
          Property < 0) )
    {
      if ( v16 )
        NCryptFreeObject(v16);
    }
    else
    {
      v18 = *(_DWORD *)pbOutput != 0;
      if ( phProvider )
        NCryptFreeObject(phProvider);
      LOBYTE(v109) = v18;
      BYTE1(v109) = 1;
    }
    LOBYTE(v100) = 0;
    if ( (int)PolicyManager::IsInsecureTpmBlockedByWHfBPolicy((PolicyManager *)&v100, v15) >= 0 )
    {
      BYTE2(v109) = (_BYTE)v100;
      HIBYTE(v109) = 1;
    }
    if ( v7 )
    {
      LOBYTE(v100) = 0;
      if ( (int)TpmIsLockedOut((unsigned __int8 *)&v100) >= 0 )
      {
        BYTE2(v107) = (_BYTE)v100 != 0;
        HIBYTE(v107) = 1;
      }
    }
  }
  if ( v5 )
  {
    *(_DWORD *)pbOutput = 0;
    if ( (int)IsDevicePasswordLess(pbOutput) >= 0 )
    {
      LOBYTE(v110) = *(_DWORD *)pbOutput != 0;
      HIBYTE(v110) = 1;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      LODWORD(v111) = GetPasswordLessPolicyValue();
      BYTE4(v111) = 1;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
      {
        BYTE2(v100) = BYTE1(v100);
        v134 = v127;
        __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_1800BC21D);
      }
    }
  }
  LOWORD(v100) = 0;
  if ( isBiometricTypeAvailable(2u, (bool *)&v100) >= 0 )
  {
    LOBYTE(v112) = (_BYTE)v100;
    BYTE1(v112) = 1;
  }
  if ( isBiometricTypeAvailable(8u, (bool *)&v100 + 1) >= 0 )
  {
    BYTE2(v112) = BYTE1(v100);
    HIBYTE(v112) = 1;
  }
  v128 = 0;
  StateSeparatedRegistryLocation = GetStateSeparatedRegistryLocation(
                                     L"WinBio",
                                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                     v19,
                                     &v128);
  v127 = v128;
  if ( StateSeparatedRegistryLocation >= 0 )
  {
    *(_DWORD *)pbOutput = 0;
    if ( (int)Utils::GetRegistryKeyDWORDEx(
                HKEY_LOCAL_MACHINE,
                v128,
                L"SecureBioAvailabilityInCensus",
                (unsigned int *)pbOutput) >= 0 )
    {
      LOBYTE(v113) = pbOutput[0] & 1;
      HIBYTE(v113) = 1;
    }
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v21 = SystemTimeAsFileTime;
  v131 = 0;
  v132 = 0;
  RegistryKeyDWORD64 = Utils::GetRegistryKeyDWORD64(
                         L"SYSTEM\\CurrentControlSet\\Services\\TPM\\WMI\\ProvisionInfo",
                         L"LastTPMProvisionedTime",
                         &v131);
  v129 = 0;
  v24 = GetStateSeparatedRegistryLocation(
          L"TpmRegDriverClearInfo",
          L"SYSTEM\\CurrentControlSet\\Services\\TPM\\ClearInfo",
          v23,
          (unsigned __int16 **)&v129);
  v25 = v129;
  if ( v24 >= 0 && (int)Utils::GetRegistryKeyDWORD64((LPCWSTR)v129, L"LastClearCommandTimestamp", &v132) >= 0
    || RegistryKeyDWORD64 >= 0 )
  {
    v26 = 0;
    if ( *(unsigned __int64 *)&v21 > 0xC92A69C000LL )
      v26 = *(_QWORD *)&v21 - 864000000000LL;
    v27 = v131 > v26;
    v28 = v132 > v26;
    if ( v27 )
    {
      v29 = v28 ? 3 : 1;
    }
    else
    {
      v29 = 0;
      if ( v28 )
        v29 = 2;
    }
    LODWORD(v114) = v29;
    BYTE4(v114) = 1;
  }
  *(_OWORD *)S1 = 0;
  v106 = 0;
  *(_OWORD *)S2 = 0;
  v138 = 0;
  v139 = 7;
  LOWORD(S2[0]) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetProfileSids_MemoryLeak_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetProfileSids_MemoryLeak_Fix>::GetImpl'::`2'::impl) )
    ProfileSids2 = GetProfileSids2((__int64 *)S1);
  else
    ProfileSids2 = GetProfileSids(S1);
  if ( ProfileSids2 < 0 )
  {
    v31 = S1[1];
    v32 = S1[0];
    if ( S1[0] != S1[1] )
    {
      do
      {
        std::wstring::~wstring((char **)v32);
        v32 += 16;
      }
      while ( v32 != v31 );
      S1[1] = S1[0];
    }
  }
  if ( (int)Utils::GetRegistryKeyStringEx(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
              L"LastLoggedOnUserSID") < 0 )
  {
    v138 = 0;
    v34 = S2;
    if ( v139 > 7 )
      v34 = (wchar_t **)S2[0];
    *(_WORD *)v34 = 0;
  }
  if ( S1[0] != S1[1] )
  {
    LOBYTE(v33) = 0;
    std::_Sort_unchecked<std::wstring *,std::less<void>>(S1[0], S1[1], ((char *)S1[1] - (char *)S1[0]) >> 5, v33);
    if ( v138 )
    {
      v35 = S1[1];
      for ( i = S1[0]; i != v35; i += 16 )
      {
        v37 = (const wchar_t *)S2;
        if ( v139 > 7 )
          v37 = S2[0];
        v38 = *((_QWORD *)i + 2);
        v39 = *((_QWORD *)i + 3) <= 7u ? i : *(const wchar_t **)i;
        if ( v38 == v138 && (!v38 || !wmemcmp(v39, v37, v38)) )
          break;
      }
      v40 = S1[1];
      if ( i != S1[1] )
      {
        for ( j = S1[0]; j != v40; j += 16 )
        {
          v42 = (const wchar_t *)S2;
          if ( v139 > 7 )
            v42 = S2[0];
          v43 = *((_QWORD *)j + 2);
          v44 = *((_QWORD *)j + 3) <= 7u ? j : *(const wchar_t **)j;
          if ( v43 == v138 && (!v43 || !wmemcmp(v44, v42, v43)) )
            break;
        }
        if ( j != v40 )
        {
          v45 = j + 16;
          if ( j + 16 == v40 )
            goto LABEL_95;
          do
          {
            v46 = (const wchar_t *)S2;
            if ( v139 > 7 )
              v46 = S2[0];
            v47 = *((_QWORD *)v45 + 2);
            if ( *((_QWORD *)v45 + 3) <= 7u )
              v48 = v45;
            else
              v48 = *(const wchar_t **)v45;
            if ( v47 != v138 || v47 && wmemcmp(v48, v46, v47) )
            {
              std::wstring::operator=(j, v45);
              j += 16;
            }
            v45 += 16;
          }
          while ( v45 != v40 );
          if ( j != v40 )
          {
LABEL_95:
            v49 = S1[1];
            while ( v40 != v49 )
            {
              std::wstring::operator=(j, v40);
              j += 16;
              v40 += 16;
            }
            v50 = S1[1];
            for ( k = j; k != v50; k += 16 )
              std::wstring::~wstring((char **)k);
            S1[1] = j;
          }
        }
        v52 = S1[0];
        v53 = S1[1];
        if ( S1[1] == v106 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(S1, S1[0], S2);
        }
        else if ( S1[0] == S1[1] )
        {
          std::wstring::wstring((__int64)S1[1], (__int64)S2);
          S1[1] += 16;
        }
        else
        {
          p_phProvider = (void **)S1;
          std::wstring::wstring((__int64)&Sid, (__int64)S2);
          v54 = v53 - 16;
          *(_OWORD *)v53 = *((_OWORD *)v53 - 2);
          *((_OWORD *)v53 + 1) = *((_OWORD *)v53 - 1);
          *((_QWORD *)v54 + 2) = 0;
          *((_QWORD *)v54 + 3) = 7;
          *v54 = 0;
          S1[1] += 16;
          while ( v54 != v52 )
          {
            v54 -= 16;
            v53 -= 16;
            std::wstring::operator=(v53, v54);
          }
          std::wstring::operator=(v52, &Sid);
          std::wstring::~wstring((char **)&Sid);
        }
        v115 = 1;
      }
    }
    v55 = S1[1];
    if ( (unsigned __int64)(((char *)S1[1] - (char *)S1[0]) >> 5) > 5 )
    {
      v56 = S1[0] + 80;
      v57 = S1[0] + 80;
      if ( S1[0] + 80 != S1[1] )
      {
        do
        {
          std::wstring::~wstring((char **)v57);
          v57 += 16;
        }
        while ( v57 != v55 );
      }
      S1[1] = v56;
    }
  }
  v58 = S1[0];
  v59 = BYTE2(v100);
  while ( v58 != S1[1] )
  {
    v60 = *((_QWORD *)&v116 + 1);
    if ( *((_QWORD *)&v116 + 1) == v117 )
    {
      std::vector<NgcCensusUserInfo>::_Emplace_reallocate<>(&v116);
      v61 = *((_QWORD *)&v116 + 1);
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)&v116 + 1) + 80LL) = 0;
      *(_OWORD *)v60 = 0;
      *(_QWORD *)(v60 + 16) = 0;
      *(_QWORD *)(v60 + 24) = 7;
      *(_WORD *)v60 = 0;
      *(_QWORD *)(v60 + 32) = 0;
      *(_QWORD *)(v60 + 40) = 0;
      *(_QWORD *)(v60 + 48) = 0;
      *(_DWORD *)(v60 + 56) = 0;
      *(_QWORD *)(v60 + 60) = 0;
      *(_QWORD *)(v60 + 68) = 0;
      *(_DWORD *)(v60 + 76) = 0;
      *(_QWORD *)(v60 + 88) = 0;
      *(_QWORD *)(v60 + 96) = 0;
      *(_QWORD *)(v60 + 104) = 0;
      *(_QWORD *)(v60 + 112) = 0;
      v61 = *((_QWORD *)&v116 + 1) + 120LL;
      *((_QWORD *)&v116 + 1) += 120LL;
    }
    v62 = v61 - 120;
    std::wstring::operator=(v62, v58);
    phProvider = 0;
    p_phProvider = (void **)&phProvider;
    Sid = 0;
    v142 = 1;
    v63 = (const WCHAR *)v62;
    if ( *(_QWORD *)(v62 + 24) > 7u )
      v63 = *(const WCHAR **)v62;
    v64 = ConvertStringSidToSidW(v63, &Sid);
    if ( v142 )
    {
      v65 = *p_phProvider;
      *p_phProvider = Sid;
      if ( v65 )
        LocalFree(v65);
    }
    if ( !v64 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( *(_QWORD *)(v62 + 24) > 7u )
        v62 = *(_QWORD *)v62;
      LODWORD(dwFlags) = LastError;
      AslLogCallPrintf(
        1,
        "NgcHelper::GetNgcSecurityProperties",
        1229,
        "ConvertStringSidToSidW failed to convert string %ws to SID [%#x]",
        v62,
        dwFlags);
      goto LABEL_223;
    }
    v120 = 0;
    v67 = LsaLookupUserAccountType(phProvider, &v120);
    if ( v67 < 0 )
    {
      AslLogCallPrintf(1, "NgcHelper::GetNgcSecurityProperties", 1243, "LsaLookupUserAccountType failed [%#x]", v67);
      goto LABEL_223;
    }
    *(_DWORD *)(v62 + 32) = v120;
    *(_BYTE *)(v62 + 36) = 1;
    HIDWORD(v100) = 0;
    v68 = (const WCHAR *)std::wstring::wstring((__int64)&p_phProvider, v62);
    if ( (int)GetUserAdminPrivileges(v68) >= 0 )
    {
      *(_DWORD *)(v62 + 88) = HIDWORD(v100);
      *(_BYTE *)(v62 + 92) = 1;
    }
    v121 = 2;
    *(_DWORD *)pbOutput = 0;
    v123 = 0;
    v122 = 0;
    v69 = (const WCHAR *)v62;
    if ( *(_QWORD *)(v62 + 24) > 7u )
      v69 = *(const WCHAR **)v62;
    if ( (int)NgcQueryEnabled(v69, 0, &v121, pbOutput, &v123, &v122) >= 0 )
    {
      *(_DWORD *)(v62 + 40) = v121;
      *(_BYTE *)(v62 + 44) = 1;
      *(_DWORD *)(v62 + 48) = *(_DWORD *)pbOutput;
      *(_BYTE *)(v62 + 52) = 1;
      if ( *(_BYTE *)(v62 + 57) )
        *(_BYTE *)(v62 + 57) = 0;
      *(_BYTE *)(v62 + 56) = v122 != 0;
      *(_BYTE *)(v62 + 57) = 1;
      *(_BYTE *)(v62 + 58) = (v123 & 2) != 0;
      *(_BYTE *)(v62 + 59) = 1;
      if ( *(_DWORD *)pbOutput == 1 )
        v70 = 2;
      else
        v70 = *(_DWORD *)pbOutput == 2;
      *(_DWORD *)(v62 + 68) = v70;
      *(_BYTE *)(v62 + 72) = 1;
    }
    v124 = 0;
    v71 = (const WCHAR *)v62;
    if ( *(_QWORD *)(v62 + 24) > 7u )
      v71 = *(const WCHAR **)v62;
    if ( (int)NgcQueryHardwarePolicy(v71, 0, 0, &v124) >= 0 )
    {
      *(_DWORD *)(v62 + 60) = v124;
      *(_BYTE *)(v62 + 64) = 1;
    }
    v119 = 0;
    HIDWORD(v100) = 0;
    while ( 1 )
    {
      hMem = 0;
      p_phProvider = &hMem;
      Sid = 0;
      v142 = 1;
      if ( *(_QWORD *)(v62 + 24) <= 7u )
        v72 = (const WCHAR *)v62;
      else
        v72 = *(const WCHAR **)v62;
      dwFlags = (const char *)&v119;
      pcbResult = (DWORD *)&Sid;
      v73 = NgcEnumUserIdKeys(&word_1801B4598, &word_1801B4598, &word_1801B4598, v72);
      if ( v142 )
      {
        v74 = *p_phProvider;
        *p_phProvider = Sid;
        if ( v74 )
          LocalFree(v74);
      }
      if ( v73 < 0 )
        break;
      v75 = *(_QWORD *)(v62 + 104);
      if ( v75 == *(_QWORD *)(v62 + 112) )
      {
        std::vector<NgcCensusUserKeyInfo>::_Emplace_reallocate<>();
      }
      else
      {
        *(_QWORD *)(v75 + 40) = 0;
        *(_OWORD *)v75 = 0;
        *(_QWORD *)(v75 + 16) = 0;
        *(_QWORD *)(v75 + 24) = 7;
        *(_WORD *)v75 = 0;
        *(_QWORD *)(v75 + 32) = 0;
        *(_QWORD *)(v62 + 104) += 48LL;
      }
      v76 = *(_QWORD *)(v62 + 104);
      std::wstring::operator=(v76 - 48, *((_QWORD *)hMem + 4));
      v125 = 0;
      if ( (int)NgcGetKeyImplType(*((_QWORD *)hMem + 4), &v125) >= 0 )
      {
        if ( *(_BYTE *)(v76 - 12) )
          *(_BYTE *)(v76 - 12) = 0;
        *(_DWORD *)(v76 - 16) = v125;
        *(_BYTE *)(v76 - 12) = 1;
      }
      *(_WORD *)((char *)&v100 + 1) = 0;
      pCertContext = 0;
      UserIdKeyCertificate = NgcGetUserIdKeyCertificate(*((_QWORD *)hMem + 4), &pCertContext);
      if ( UserIdKeyCertificate == -2146893807 )
      {
        if ( *(_BYTE *)(v76 - 7) )
          *(_BYTE *)(v76 - 7) = 0;
        *(_WORD *)(v76 - 8) = 256;
      }
      else if ( UserIdKeyCertificate >= 0 )
      {
        if ( *(_BYTE *)(v76 - 7) )
          *(_BYTE *)(v76 - 7) = 0;
        *(_WORD *)(v76 - 8) = 257;
        if ( (int)NgcPinManagement::ValidateAadCert(
                    *((NgcPinManagement **)hMem + 4),
                    (const unsigned __int16 *)&v100 + 1,
                    (bool *)&v100 + 1,
                    v78) >= 0 )
        {
          if ( *(_BYTE *)(v76 - 5) )
            *(_BYTE *)(v76 - 5) = 0;
          *(_BYTE *)(v76 - 6) = BYTE2(v100);
          *(_BYTE *)(v76 - 5) = 1;
          if ( *(_BYTE *)(v76 - 3) )
            *(_BYTE *)(v76 - 3) = 0;
          *(_BYTE *)(v76 - 4) = BYTE1(v100);
          *(_BYTE *)(v76 - 3) = 1;
        }
      }
      if ( pCertContext )
        CertFreeCertificateContext(pCertContext);
      v79 = hMem;
      hMem = 0;
      if ( v79 )
        LocalFree(v79);
      ++HIDWORD(v100);
      if ( SHIDWORD(v100) >= 10 )
        goto LABEL_182;
    }
    LOBYTE(pcbResult) = v73 != -2146893782;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x520,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
      (const char *)(unsigned int)v73,
      (int)pcbResult,
      (bool)"NgcEnumUserIdKeys failed!",
      v100);
    v80 = hMem;
    hMem = 0;
    if ( v80 )
      LocalFree(v80);
LABEL_182:
    v81 = (void *)phProvider;
    HIDWORD(v100) = 0;
    memset_0(&p_phProvider, 0, 0x4Cu);
    if ( !IsValidSid(v81) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
        (const char *)0x80070057LL,
        (int)pcbResult);
      EnrolledFactors = -2147024809;
LABEL_186:
      v84 = 164;
      goto LABEL_190;
    }
    LODWORD(p_phProvider) = 3;
    if ( CopySid(0x44u, &Sid, v81) )
    {
      HIDWORD(p_phProvider) = GetLengthSid(v81);
    }
    else
    {
      EnrolledFactors = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x95,
                          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
                          v83);
      if ( EnrolledFactors < 0 )
        goto LABEL_186;
    }
    EnrolledFactors = WinBioGetEnrolledFactors(&p_phProvider, (char *)&v100 + 4);
    if ( EnrolledFactors >= 0 )
      goto LABEL_191;
    v84 = 168;
LABEL_190:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v84,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
      (const char *)(unsigned int)EnrolledFactors,
      (int)pcbResult);
LABEL_191:
    v85 = BYTE4(v100);
    *(_BYTE *)(v62 + 76) = (BYTE4(v100) & 2) != 0;
    *(_BYTE *)(v62 + 77) = 1;
    *(_BYTE *)(v62 + 78) = (v85 & 8) != 0;
    *(_BYTE *)(v62 + 79) = 1;
    BYTE2(v100) = 0;
    v118 = 0;
    v126 = 0;
    while ( 1 )
    {
      p_phProvider = &v126;
      Sid = 0;
      v142 = 1;
      v86 = (const WCHAR *)v62;
      if ( *(_QWORD *)(v62 + 24) > 7u )
        v86 = *(const WCHAR **)v62;
      v87 = NgcEnumContainers(v86, &Sid, &v118);
      v88 = v87;
      HIDWORD(v100) = v87;
      v89 = v87 >= 0;
      if ( v142 )
      {
        v90 = *p_phProvider;
        *p_phProvider = Sid;
        if ( v90 )
        {
          LocalFree(v90);
          v88 = HIDWORD(v100);
        }
        else
        {
          v88 = v87;
        }
      }
      if ( !v89 )
        break;
      if ( (*((_BYTE *)v126 + 56) & 1) != 0 )
      {
        v91 = 1;
        goto LABEL_202;
      }
    }
    v91 = BYTE2(v100);
LABEL_202:
    if ( (int)(v88 + 0x80000000) < 0 || v88 == -2146893782 )
    {
      *(_BYTE *)(v62 + 80) = v91;
      *(_BYTE *)(v62 + 81) = 1;
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x565,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
        (const char *)v88,
        (int)"NgcEnumContainters failed!",
        dwFlags);
    }
    v103 = 0;
    v92 = (const WCHAR *)v62;
    if ( *(_QWORD *)(v62 + 24) > 7u )
      v92 = *(const WCHAR **)v62;
    if ( (int)NgcLocalFindCredential(v92, &v103) >= 0 )
    {
      *(_BYTE *)(v62 + 82) = v103 != 0;
      *(_BYTE *)(v62 + 83) = 1;
    }
    if ( v59 )
    {
      HIDWORD(v100) = 0;
      v93 = *(_QWORD *)(v62 + 24) <= 7u ? (unsigned __int16 *)v62 : *(unsigned __int16 **)v62;
      if ( (int)IsAccountPasswordLess(v93, (int *)&v100 + 1) >= 0 )
      {
        *(_BYTE *)(v62 + 84) = HIDWORD(v100) != 0;
        *(_BYTE *)(v62 + 85) = 1;
      }
    }
    v94 = v126;
    v126 = 0;
    if ( v94 )
      LocalFree(v94);
    if ( v118 )
      NgcFreeEnumState();
    if ( v119 )
      NgcFreeEnumState();
LABEL_223:
    v95 = (void *)phProvider;
    phProvider = 0;
    if ( v95 )
      LocalFree(v95);
    v58 += 16;
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v135);
  NgcCensusInfo::toDeviceCensusStringFormat(&v107, v135);
  std::basic_stringbuf<unsigned short>::str(v136, &p_phProvider);
  std::wstring::operator=(v134, &p_phProvider);
  std::wstring::~wstring((char **)&p_phProvider);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v135);
  std::wstring::~wstring((char **)S2);
  std::vector<std::wstring>::~vector<std::wstring>(S1);
  v96 = v127;
  if ( v25 )
    LocalFree(v25);
  if ( v96 )
    LocalFree(v96);
  std::vector<NgcCensusUserInfo>::~vector<NgcCensusUserInfo>(&v116);
  return 0;
}

```

## disassembly

```asm
0x1800bbdd0  mov     [rsp+arg_0], rbx
0x1800bbdd5  mov     [rsp+arg_10], rsi
0x1800bbdda  push    rdi
0x1800bbddb  push    r12
0x1800bbddd  push    r13
0x1800bbddf  push    r14
0x1800bbde1  push    r15
0x1800bbde3  sub     rsp, 2B0h
0x1800bbdea  mov     rax, cs:__security_cookie
0x1800bbdf1  xor     rax, rsp
0x1800bbdf4  mov     [rsp+2D8h+var_38], rax
0x1800bbdfc  mov     r15, rdx
0x1800bbdff  mov     [rsp+2D8h+var_1B0], rdx
0x1800bbe07  mov     [rsp+2D8h+var_1E8], rdx
0x1800bbe0f  xor     r14d, r14d
0x1800bbe12  lea     r12d, [r14+1]
0x1800bbe16  cmp     [rdx+18h], r12
0x1800bbe1a  jb      short loc_1800BBE37
0x1800bbe1c  cmp     qword ptr [rdx+18h], 7
0x1800bbe21  jbe     short loc_1800BBE28
0x1800bbe23  mov     rax, [rdx]
0x1800bbe26  jmp     short loc_1800BBE2B
0x1800bbe28  mov     rax, r15
0x1800bbe2b  mov     [rdx+10h], r12
0x1800bbe2f  mov     dword ptr [rax], 23h ; '#'
0x1800bbe35  jmp     short loc_1800BBE49
0x1800bbe37  lea     r9, asc_1801B4764; "#"
0x1800bbe3e  mov     rdx, r12
0x1800bbe41  mov     rcx, r15
0x1800bbe44  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800bbe49  lea     rax, [rsp+2D8h+var_88]
0x1800bbe51  mov     [rsp+2D8h+var_210], rax
0x1800bbe59  lea     rdi, dword_1801B3FA4
0x1800bbe60  mov     rdx, rdi
0x1800bbe63  lea     rcx, [rsp+2D8h+var_88]
0x1800bbe6b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bbe70  mov     rbx, rax
0x1800bbe73  xorps   xmm0, xmm0
0x1800bbe76  movups  xmmword ptr [rsp+2D8h+S2], xmm0
0x1800bbe7e  mov     [rsp+2D8h+var_98], r14
0x1800bbe86  mov     [rsp+2D8h+var_90], r14
0x1800bbe8e  mov     r8d, 11h
0x1800bbe94  lea     rdx, aPolicymanagerD; "policymanager.dll"
0x1800bbe9b  lea     rcx, [rsp+2D8h+S2]
0x1800bbea3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bbea8  nop
0x1800bbea9  mov     rdx, rbx
0x1800bbeac  lea     rcx, [rsp+2D8h+S2]
0x1800bbeb4  call    ?IsApiAvailable@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; IsApiAvailable(std::wstring,std::string)
0x1800bbeb9  mov     r15b, al
0x1800bbebc  mov     byte ptr [rsp+2D8h+var_2A6], al
0x1800bbec0  lea     rax, [rsp+2D8h+var_88]
0x1800bbec8  mov     [rsp+2D8h+var_210], rax
0x1800bbed0  mov     rdx, rdi
0x1800bbed3  lea     rcx, [rsp+2D8h+var_88]
0x1800bbedb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bbee0  mov     rbx, rax
0x1800bbee3  xorps   xmm0, xmm0
0x1800bbee6  movups  xmmword ptr [rsp+2D8h+S2], xmm0
0x1800bbeee  mov     [rsp+2D8h+var_98], r14
0x1800bbef6  mov     [rsp+2D8h+var_90], r14
0x1800bbefe  mov     r8d, 17h
0x1800bbf04  lea     rdx, aTpmcoreprovisi_0; "tpmcoreprovisioning.dll"
0x1800bbf0b  lea     rcx, [rsp+2D8h+S2]
0x1800bbf13  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bbf18  nop
0x1800bbf19  mov     rdx, rbx
0x1800bbf1c  lea     rcx, [rsp+2D8h+S2]
0x1800bbf24  call    ?IsApiAvailable@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; IsApiAvailable(std::wstring,std::string)
0x1800bbf29  mov     sil, al
0x1800bbf2c  lea     rax, [rsp+2D8h+var_88]
0x1800bbf34  mov     [rsp+2D8h+var_210], rax
0x1800bbf3c  mov     rdx, rdi
0x1800bbf3f  lea     rcx, [rsp+2D8h+var_88]
0x1800bbf47  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bbf4c  mov     rbx, rax
0x1800bbf4f  xorps   xmm0, xmm0
0x1800bbf52  movups  xmmword ptr [rsp+2D8h+S2], xmm0
0x1800bbf5a  mov     [rsp+2D8h+var_98], r14
0x1800bbf62  mov     [rsp+2D8h+var_90], r14
0x1800bbf6a  mov     r8d, 0Ch
0x1800bbf70  lea     rdx, aCryptngcDll_0; "cryptngc.dll"
0x1800bbf77  lea     rcx, [rsp+2D8h+S2]
0x1800bbf7f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bbf84  nop
0x1800bbf85  mov     rdx, rbx
0x1800bbf88  lea     rcx, [rsp+2D8h+S2]
0x1800bbf90  call    ?IsApiAvailable@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; IsApiAvailable(std::wstring,std::string)
0x1800bbf95  mov     dil, al
0x1800bbf98  lea     rax, [rsp+2D8h+var_88]
0x1800bbfa0  mov     [rsp+2D8h+var_210], rax
0x1800bbfa8  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800bbfaf  lea     rcx, [rsp+2D8h+var_88]
0x1800bbfb7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bbfbc  mov     rbx, rax
0x1800bbfbf  xorps   xmm0, xmm0
0x1800bbfc2  movups  xmmword ptr [rsp+2D8h+S2], xmm0
0x1800bbfca  mov     [rsp+2D8h+var_98], r14
0x1800bbfd2  mov     [rsp+2D8h+var_90], r14
0x1800bbfda  mov     r8d, 9
0x1800bbfe0  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x1800bbfe7  lea     rcx, [rsp+2D8h+S2]
0x1800bbfef  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800bbff4  nop
0x1800bbff5  mov     rdx, rbx
0x1800bbff8  lea     rcx, [rsp+2D8h+S2]
0x1800bc000  call    ?IsApiAvailable@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; IsApiAvailable(std::wstring,std::string)
0x1800bc005  test    dil, dil
0x1800bc008  jz      loc_1800BD051
0x1800bc00e  test    al, al
0x1800bc010  jz      loc_1800BD051
0x1800bc016  mov     [rsp+2D8h+var_2A7], r15b
0x1800bc01b  xor     edx, edx; Val
0x1800bc01d  lea     r8d, [rdx+48h]; Size
0x1800bc021  lea     rcx, [rsp+2D8h+var_268]; void *
0x1800bc026  call    memset_0
0x1800bc02b  mov     [rsp+2D8h+var_268], r14d
0x1800bc030  mov     [rsp+2D8h+var_268+2], r14d
0x1800bc035  mov     [rsp+2D8h+var_264], r14d
0x1800bc03a  mov     [rsp+2D8h+var_264+2], r14d
0x1800bc03f  mov     [rsp+2D8h+var_260], r14d
0x1800bc044  mov     [rsp+2D8h+var_260+2], r14d
0x1800bc049  mov     [rsp+2D8h+var_25C], r14w
0x1800bc04f  xor     eax, eax
0x1800bc051  mov     [rsp+2D8h+var_258], rax
0x1800bc059  mov     byte ptr [rsp+2D8h+var_258], r14b
0x1800bc061  mov     byte ptr [rsp+2D8h+var_258+4], r14b
0x1800bc069  mov     [rsp+2D8h+var_250], eax
0x1800bc070  mov     word ptr [rsp+2D8h+var_250], r14w
0x1800bc079  mov     [rsp+2D8h+var_250+2], r14d
0x1800bc081  mov     [rsp+2D8h+var_24C], r14w
0x1800bc08a  mov     [rsp+2D8h+var_248], rax
0x1800bc092  mov     byte ptr [rsp+2D8h+var_248], r14b
0x1800bc09a  mov     byte ptr [rsp+2D8h+var_248+4], r14b
0x1800bc0a2  mov     [rsp+2D8h+var_240], r14b
0x1800bc0aa  xorps   xmm0, xmm0
0x1800bc0ad  movdqa  [rsp+2D8h+var_238], xmm0
0x1800bc0b6  mov     [rsp+2D8h+var_228], r14
0x1800bc0be  call    ?GetTpmVersion@Utils@@SAHXZ; Utils::GetTpmVersion(void)
0x1800bc0c3  test    eax, eax
0x1800bc0c5  jle     loc_1800BC1E0
0x1800bc0cb  mov     word ptr [rsp+2D8h+var_268], 101h
0x1800bc0d2  mov     [rsp+2D8h+var_2A8], r14b
0x1800bc0d7  lea     rcx, [rsp+2D8h+var_2A8]; this
0x1800bc0dc  call    ?IsExcludeTpm12PolicySet@PolicyManager@@YAJPEA_N@Z; PolicyManager::IsExcludeTpm12PolicySet(bool *)
0x1800bc0e1  test    eax, eax
0x1800bc0e3  js      short loc_1800BC0F2
0x1800bc0e5  mov     al, [rsp+2D8h+var_2A8]
0x1800bc0e9  mov     byte ptr [rsp+2D8h+var_264+2], al
0x1800bc0ed  mov     byte ptr [rsp+2D8h+var_264+3], r12b
0x1800bc0f2  mov     [rsp+2D8h+var_2A8], r14b
0x1800bc0f7  lea     rcx, [rsp+2D8h+var_2A8]; this
0x1800bc0fc  call    ?IsInsecureTpm@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsInsecureTpm(bool *)
0x1800bc101  test    eax, eax
0x1800bc103  js      short loc_1800BC112
0x1800bc105  mov     al, [rsp+2D8h+var_2A8]
0x1800bc109  mov     byte ptr [rsp+2D8h+var_264], al
0x1800bc10d  mov     byte ptr [rsp+2D8h+var_264+1], r12b
0x1800bc112  mov     [rsp+2D8h+phProvider], r14
0x1800bc117  xor     r8d, r8d; dwFlags
0x1800bc11a  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800bc121  lea     rcx, [rsp+2D8h+phProvider]; phProvider
0x1800bc126  call    cs:__imp_NCryptOpenStorageProvider
0x1800bc12c  mov     rcx, [rsp+2D8h+phProvider]; hObject
0x1800bc131  test    eax, eax
0x1800bc133  jns     short loc_1800BC142
0x1800bc135  test    rcx, rcx
0x1800bc138  jz      short loc_1800BC198
0x1800bc13a  call    cs:__imp_NCryptFreeObject
0x1800bc140  jmp     short loc_1800BC198
0x1800bc142  mov     dword ptr [rsp+2D8h+pbOutput], r14d
0x1800bc147  mov     [rsp+2D8h+var_290], r14d
0x1800bc14c  mov     [rsp+2D8h+dwFlags], r14d; dwFlags
0x1800bc151  lea     rax, [rsp+2D8h+var_290]
0x1800bc156  mov     [rsp+2D8h+pcbResult], rax; pcbResult
0x1800bc15b  mov     r9d, 4; cbOutput
0x1800bc161  lea     r8, [rsp+2D8h+pbOutput]; pbOutput
0x1800bc166  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED"
0x1800bc16d  call    cs:__imp_NCryptGetProperty
0x1800bc173  mov     rcx, [rsp+2D8h+phProvider]; hObject
0x1800bc178  test    eax, eax
0x1800bc17a  js      short loc_1800BC135
0x1800bc17c  cmp     dword ptr [rsp+2D8h+pbOutput], r14d
0x1800bc181  setnz   bl
0x1800bc184  test    rcx, rcx
0x1800bc187  jz      short loc_1800BC18F
0x1800bc189  call    cs:__imp_NCryptFreeObject
0x1800bc18f  mov     byte ptr [rsp+2D8h+var_260], bl
0x1800bc193  mov     byte ptr [rsp+2D8h+var_260+1], r12b
0x1800bc198  mov     [rsp+2D8h+var_2A8], r14b
0x1800bc19d  lea     rcx, [rsp+2D8h+var_2A8]; this
0x1800bc1a2  call    ?IsInsecureTpmBlockedByWHfBPolicy@PolicyManager@@YAJPEA_N@Z; PolicyManager::IsInsecureTpmBlockedByWHfBPolicy(bool *)
0x1800bc1a7  test    eax, eax
0x1800bc1a9  js      short loc_1800BC1B8
0x1800bc1ab  mov     al, [rsp+2D8h+var_2A8]
0x1800bc1af  mov     byte ptr [rsp+2D8h+var_260+2], al
0x1800bc1b3  mov     byte ptr [rsp+2D8h+var_260+3], r12b
0x1800bc1b8  test    sil, sil
0x1800bc1bb  jz      short loc_1800BC1E0
0x1800bc1bd  mov     [rsp+2D8h+var_2A8], r14b
0x1800bc1c2  lea     rcx, [rsp+2D8h+var_2A8]
0x1800bc1c7  call    cs:__imp_?TpmIsLockedOut@@YAJPEAE@Z; TpmIsLockedOut(uchar *)
0x1800bc1cd  test    eax, eax
0x1800bc1cf  js      short loc_1800BC1E0
0x1800bc1d1  cmp     [rsp+2D8h+var_2A8], r14b
0x1800bc1d6  setnz   byte ptr [rsp+2D8h+var_268+2]
0x1800bc1db  mov     byte ptr [rsp+2D8h+var_268+3], r12b
0x1800bc1e0  test    r15b, r15b
0x1800bc1e3  jz      short loc_1800BC23C
0x1800bc1e5  mov     dword ptr [rsp+2D8h+pbOutput], r14d
0x1800bc1ea  lea     rcx, [rsp+2D8h+pbOutput]
0x1800bc1ef  call    IsDevicePasswordLess
0x1800bc1f4  test    eax, eax
0x1800bc1f6  js      short loc_1800BC207
0x1800bc1f8  cmp     dword ptr [rsp+2D8h+pbOutput], r14d
0x1800bc1fd  setnz   byte ptr [rsp+2D8h+var_25C]
0x1800bc202  mov     byte ptr [rsp+2D8h+var_25C+1], r12b
0x1800bc207  call    GetPasswordLessPolicyValue
0x1800bc20c  mov     dword ptr [rsp+2D8h+var_258], eax
0x1800bc213  mov     byte ptr [rsp+2D8h+var_258+4], r12b
0x1800bc21b  jmp     short loc_1800BC23C
0x1800bc21d  xor     r14d, r14d
0x1800bc220  lea     r12d, [r14+1]
0x1800bc224  mov     al, [rsp+2D8h+var_2A7]
0x1800bc228  mov     byte ptr [rsp+2D8h+var_2A6], al
0x1800bc22c  mov     rax, [rsp+2D8h+var_1E8]
0x1800bc234  mov     [rsp+2D8h+var_1B0], rax
0x1800bc23c  mov     [rsp+2D8h+var_2A8], r14b
0x1800bc241  mov     [rsp+2D8h+var_2A7], r14b
0x1800bc246  lea     rdx, [rsp+2D8h+var_2A8]; bool *
0x1800bc24b  mov     r13d, 2
0x1800bc251  mov     ecx, r13d; unsigned int
0x1800bc254  call    ?isBiometricTypeAvailable@@YAJIPEA_N@Z; isBiometricTypeAvailable(uint,bool *)
0x1800bc259  test    eax, eax
0x1800bc25b  js      short loc_1800BC270
0x1800bc25d  mov     al, [rsp+2D8h+var_2A8]
0x1800bc261  mov     byte ptr [rsp+2D8h+var_250], al
0x1800bc268  mov     byte ptr [rsp+2D8h+var_250+1], r12b
0x1800bc270  lea     rdx, [rsp+2D8h+var_2A7]; bool *
0x1800bc275  mov     ecx, 8; unsigned int
0x1800bc27a  call    ?isBiometricTypeAvailable@@YAJIPEA_N@Z; isBiometricTypeAvailable(uint,bool *)
0x1800bc27f  test    eax, eax
0x1800bc281  js      short loc_1800BC296
0x1800bc283  mov     al, [rsp+2D8h+var_2A7]
0x1800bc287  mov     byte ptr [rsp+2D8h+var_250+2], al
0x1800bc28e  mov     byte ptr [rsp+2D8h+var_250+3], r12b
0x1800bc296  mov     [rsp+2D8h+var_1E0], r14
0x1800bc29e  lea     r9, [rsp+2D8h+var_1E0]; unsigned __int16 **
0x1800bc2a6  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800bc2ad  lea     rcx, aWinbio; "WinBio"
0x1800bc2b4  call    ?GetStateSeparatedRegistryLocation@@YAJPEBG00PEAPEAG@Z; GetStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800bc2b9  mov     rdi, [rsp+2D8h+var_1E0]
0x1800bc2c1  mov     [rsp+2D8h+var_1E8], rdi
0x1800bc2c9  test    eax, eax
0x1800bc2cb  js      short loc_1800BC307
0x1800bc2cd  mov     dword ptr [rsp+2D8h+pbOutput], r14d
0x1800bc2d2  lea     r9, [rsp+2D8h+pbOutput]; unsigned int *
0x1800bc2d7  lea     r8, aSecurebioavail; "SecureBioAvailabilityInCensus"
0x1800bc2de  mov     rdx, rdi; unsigned __int16 *
0x1800bc2e1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800bc2e8  call    ?GetRegistryKeyDWORDEx@Utils@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Utils::GetRegistryKeyDWORDEx(HKEY__ *,ushort const *,ushort const *,ulong &)
0x1800bc2ed  test    eax, eax
0x1800bc2ef  js      short loc_1800BC307
0x1800bc2f1  mov     al, [rsp+2D8h+pbOutput]
0x1800bc2f5  and     al, r12b
0x1800bc2f8  mov     byte ptr [rsp+2D8h+var_24C], al
0x1800bc2ff  mov     byte ptr [rsp+2D8h+var_24C+1], r12b
0x1800bc307  mov     qword ptr [rsp+2D8h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800bc30f  lea     rcx, [rsp+2D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800bc317  call    cs:__imp_GetSystemTimeAsFileTime
0x1800bc31d  mov     rbx, qword ptr [rsp+2D8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800bc325  mov     [rsp+2D8h+var_1C8], r14
0x1800bc32d  mov     [rsp+2D8h+var_1C0], r14
0x1800bc335  lea     r8, [rsp+2D8h+var_1C8]; unsigned __int64 *
0x1800bc33d  lea     rdx, aLasttpmprovisi; "LastTPMProvisionedTime"
0x1800bc344  lea     rcx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\TP"...
0x1800bc34b  call    ?GetRegistryKeyDWORD64@Utils@@SAJPEBG0AEA_K@Z; Utils::GetRegistryKeyDWORD64(ushort const *,ushort const *,unsigned __int64 &)
0x1800bc350  mov     r15d, eax
0x1800bc353  mov     [rsp+2D8h+var_1D8], r14
0x1800bc35b  lea     r9, [rsp+2D8h+var_1D8]; unsigned __int16 **
0x1800bc363  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\TP"...
0x1800bc36a  lea     rcx, aTpmregdrivercl; "TpmRegDriverClearInfo"
0x1800bc371  call    ?GetStateSeparatedRegistryLocation@@YAJPEBG00PEAPEAG@Z; GetStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800bc376  mov     rsi, [rsp+2D8h+var_1D8]
0x1800bc37e  test    eax, eax
0x1800bc380  js      short loc_1800BC39D
0x1800bc382  lea     r8, [rsp+2D8h+var_1C0]; unsigned __int64 *
0x1800bc38a  lea     rdx, aLastclearcomma; "LastClearCommandTimestamp"
0x1800bc391  mov     rcx, rsi; lpSubKey
0x1800bc394  call    ?GetRegistryKeyDWORD64@Utils@@SAJPEBG0AEA_K@Z; Utils::GetRegistryKeyDWORD64(ushort const *,ushort const *,unsigned __int64 &)
0x1800bc399  test    eax, eax
0x1800bc39b  jns     short loc_1800BC3A6
0x1800bc39d  shr     r15d, 1Fh
0x1800bc3a1  xor     r15b, r12b
0x1800bc3a4  jz      short loc_1800BC403
0x1800bc3a6  mov     rcx, r14
0x1800bc3a9  mov     rax, 0C92A69C000h
0x1800bc3b3  cmp     rbx, rax
0x1800bc3b6  jbe     short loc_1800BC3C5
0x1800bc3b8  mov     rcx, 0FFFFFF36D5964000h
  ... truncated ...
```
