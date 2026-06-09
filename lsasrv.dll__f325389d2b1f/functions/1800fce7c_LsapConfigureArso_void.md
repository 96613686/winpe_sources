# LsapConfigureArso(void *)

- ea: `0x1800fce7c`
- end: `0x1800fd9dc`
- name: `?LsapConfigureArso@@YAJPEAX@Z`
- size: `2912`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ff230`
- `0x1800ff320`

## callees

- `0x180001db4`
- `0x1800093b0`
- `0x180011278`
- `0x1800293c0`
- `0x18005eda0`
- `0x18009a064`
- `0x18009e2c4`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800fb870`
- `0x1800fbf54`
- `0x1800fce7c`
- `0x1800fd9e4`
- `0x1800fdc24`
- `0x1800fe36c`
- `0x1800fe88c`
- `0x1800fef20`
- `0x18014a710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd868`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd580`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd5d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd631`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd710`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd782`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd580`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd5d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd631`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd710`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800fd782`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd052`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800fd7d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800fd7d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd0d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd0d5`
- `ntdll!RtlEqualSid` at `0x1800fcfec`
- `ntdll!RtlEqualSid` at `0x1800fcfec`
- `ntdll!RtlLeaveCriticalSection` at `0x1800fd890`
- `ntdll!RtlLeaveCriticalSection` at `0x1800fd890`
- `ntdll!RtlEnterCriticalSection` at `0x1800fcf5d`
- `ntdll!RtlEnterCriticalSection` at `0x1800fcf5d`
- `ntdll!RtlInitUnicodeString` at `0x1800fd4a9`
- `ntdll!RtlInitUnicodeString` at `0x1800fd672`
- `ntdll!RtlInitUnicodeString` at `0x1800fd689`
- `ntdll!RtlInitUnicodeString` at `0x1800fd4a9`
- `ntdll!RtlInitUnicodeString` at `0x1800fd672`
- `ntdll!RtlInitUnicodeString` at `0x1800fd689`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800fd2e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800fd2e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800fd6a1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800fd805`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800fd6a1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800fd805`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800fd87d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800fd87d`

## pseudocode

```c
__int64 __fastcall LsapConfigureArso(PSID Sid1)
{
  int v2; // edi
  int v3; // r13d
  LsaHandleCache *v4; // rcx
  __int64 v5; // rdx
  LSTATUS IsSystemArsoAllowed; // ebx
  char v7; // r15
  struct _LSAP_LOGON_SESSION *LogonSessionWithSid; // r14
  LsaHandleCache *v9; // rcx
  __int64 v10; // rdx
  bool v11; // sf
  LsaHandleCache *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  LsaHandleCache *v15; // rcx
  __int64 v16; // rdx
  int IsUserArsoEnabled; // eax
  unsigned int SystemArsoConsentValue; // eax
  unsigned int v19; // ebx
  NTSTATUS v20; // eax
  void *v21; // rcx
  int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // r12d
  int v25; // eax
  LsaHandleCache *v26; // rcx
  __int64 v27; // rdx
  struct _LUID v28; // rcx
  NTSTATUS v29; // eax
  LSTATUS v30; // esi
  __int64 v31; // rcx
  int v32; // r8d
  int v34; // [rsp+84h] [rbp-7Ch]
  int v35; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v37; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+94h] [rbp-6Ch] BYREF
  int v39; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp-58h] BYREF
  int v42[2]; // [rsp+ACh] [rbp-54h] BYREF
  DWORD Type; // [rsp+B4h] [rbp-4Ch] BYREF
  wchar_t String2[4]; // [rsp+B8h] [rbp-48h] BYREF
  PVOID PolicyHandle; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v46[4]; // [rsp+C8h] [rbp-38h] BYREF
  BYTE v47[4]; // [rsp+CCh] [rbp-34h] BYREF
  int v48; // [rsp+D0h] [rbp-30h]
  LSTATUS v49; // [rsp+D4h] [rbp-2Ch]
  int v50; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  BYTE *lpData[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING v54; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING v55; // [rsp+118h] [rbp+18h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+128h] [rbp+28h] BYREF
  wchar_t Data[136]; // [rsp+160h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
  wcscpy(String2, L"1");
  hKey = 0;
  v38 = 0;
  v39 = 0;
  v2 = 1;
  v37 = 0;
  *(_DWORD *)v46 = 1;
  *(_DWORD *)v47 = 1;
  v54 = 0;
  PolicyHandle = 0;
  v55 = 0;
  *(_OWORD *)lpData = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(Data, 0, 0x104u);
  cbData = 0;
  Type = 0;
  v35 = 1;
  v34 = 0;
  v42[1] = Sid1 != 0;
  v3 = 1;
  v36 = 0;
  v42[0] = 0;
  RtlEnterCriticalSection(&g_autoLogonCritSec);
  if ( byte_1801A0D38 )
  {
    v2 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_9;
    v5 = 62;
LABEL_8:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
LABEL_9:
    IsSystemArsoAllowed = -1073282889;
    goto LABEL_154;
  }
  if ( !Sid2 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
    IsSystemArsoAllowed = -1073740943;
    goto LABEL_154;
  }
  if ( Sid1 && !RtlEqualSid(Sid1, Sid2) )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
    v2 = 0;
    IsSystemArsoAllowed = -1073741790;
    goto LABEL_154;
  }
  v7 = 0;
  IsSystemArsoAllowed = RegOpenKeyExW(
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                          0,
                          0x2001Fu,
                          &hKey);
  if ( IsSystemArsoAllowed )
  {
    LogonSessionWithSid = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 65;
LABEL_26:
      WPP_SF_d(
        *((_QWORD *)v9 + 2),
        v10,
        &WPP_1def5822bda638f577b76ed976884066_Traceguids,
        (unsigned int)IsSystemArsoAllowed);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"AutoAdminLogon", 0, &Type, (LPBYTE)Data, &cbData)
    && (Type == 4 && cbData == 4 && *(_DWORD *)Data || !wcsncmp_0(Data, String2, 2u)) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_9;
    v5 = 66;
    goto LABEL_8;
  }
  IsSystemArsoAllowed = LsapIsSystemArsoAllowed(1u, &v38, &v39);
  if ( IsSystemArsoAllowed < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_154;
    v13 = 67;
    v14 = (unsigned int)IsSystemArsoAllowed;
    goto LABEL_72;
  }
  if ( !v38 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_46;
    v16 = 68;
LABEL_45:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
LABEL_46:
    IsSystemArsoAllowed = -1073741790;
    goto LABEL_154;
  }
  if ( Sid1 )
  {
    IsUserArsoEnabled = LsapIsUserArsoEnabled(Sid1, &v35, &v36);
    if ( IsUserArsoEnabled >= 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v3 = v35;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          &WPP_1def5822bda638f577b76ed976884066_Traceguids,
          (unsigned int)v35);
        goto LABEL_55;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_1def5822bda638f577b76ed976884066_Traceguids,
          (unsigned int)IsUserArsoEnabled);
        v3 = v35;
LABEL_55:
        v15 = WPP_GLOBAL_Control;
        v34 = v36;
        goto LABEL_64;
      }
    }
    v3 = v35;
    v34 = v36;
LABEL_64:
    if ( !v3 )
    {
LABEL_65:
      if ( v15 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 4) == 0 )
        goto LABEL_46;
      v16 = 72;
      goto LABEL_45;
    }
    goto LABEL_68;
  }
  SystemArsoConsentValue = GetSystemArsoConsentValue();
  v19 = SystemArsoConsentValue;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      &WPP_1def5822bda638f577b76ed976884066_Traceguids,
      SystemArsoConsentValue);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v19 == 2 )
  {
    v3 = 0;
    v34 = 1;
    goto LABEL_65;
  }
  if ( v19 == 1 )
  {
    v34 = 1;
    goto LABEL_64;
  }
LABEL_68:
  v20 = LsaOpenPolicy(0, &ObjectAttributes, 0x21u, &PolicyHandle);
  IsSystemArsoAllowed = v20;
  if ( v20 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_154;
    v13 = 73;
    v14 = (unsigned int)v20;
LABEL_72:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_1def5822bda638f577b76ed976884066_Traceguids, v14);
    goto LABEL_154;
  }
  LogonSessionWithSid = LsapLocateLogonSessionWithSid(v21);
  if ( !LogonSessionWithSid )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
    IsSystemArsoAllowed = -1073741729;
    goto LABEL_154;
  }
  v22 = LsapLookupUserAccountType(0, (struct _LSAPR_SID *)Sid2, (enum _LSA_USER_ACCOUNT_TYPE *)&v37);
  IsSystemArsoAllowed = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_1def5822bda638f577b76ed976884066_Traceguids,
        (unsigned int)v22);
    goto LABEL_151;
  }
  v24 = v37;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_1def5822bda638f577b76ed976884066_Traceguids, v37);
  if ( v24 == 1 || v24 == 4 )
  {
    v25 = BlankPasswordCheck(Sid2, v42, v23);
    IsSystemArsoAllowed = v25;
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_151;
      v27 = 77;
      goto LABEL_93;
    }
    if ( v42[0] )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_1def5822bda638f577b76ed976884066_Traceguids);
      IsSystemArsoAllowed = -1073741714;
      goto LABEL_151;
    }
    *(_OWORD *)lpData = *((_OWORD *)LogonSessionWithSid + 10);
    RtlInitUnicodeString(&DestinationString, L".");
  }
  else
  {
    *(_OWORD *)lpData = *((_OWORD *)LogonSessionWithSid + 10);
    DestinationString = (struct _UNICODE_STRING)*((_OWORD *)LogonSessionWithSid + 11);
  }
  if ( v39 )
  {
    v25 = PreventBitLockerSuspension();
    IsSystemArsoAllowed = v25;
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_151;
      v27 = 79;
      goto LABEL_93;
    }
  }
  v28 = (struct _LUID)*((_QWORD *)LogonSessionWithSid + 14);
  if ( v24 != 1 )
  {
    v25 = LsapConfigureCloudCache(v28);
    IsSystemArsoAllowed = v25;
    if ( v25 >= 0 )
      goto LABEL_114;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_151;
    v27 = 81;
LABEL_93:
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_1def5822bda638f577b76ed976884066_Traceguids, (unsigned int)v25);
LABEL_151:
    LsapReleaseLogonSession(LogonSessionWithSid);
    goto LABEL_152;
  }
  v25 = LsapConfigureLocalAccount(v28);
  IsSystemArsoAllowed = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_151;
    v27 = 80;
    goto LABEL_93;
  }
LABEL_114:
  if ( LsapPlatformId != 3 )
    goto LABEL_150;
  IsSystemArsoAllowed = RegSetValueExW(hKey, L"DefaultUserName", 0, 1u, lpData[1], LOWORD(lpData[0]));
  if ( !IsSystemArsoAllowed )
  {
    IsSystemArsoAllowed = RegSetValueExW(
                            hKey,
                            L"DefaultDomainName",
                            0,
                            1u,
                            (const BYTE *)DestinationString.Buffer,
                            DestinationString.Length);
    if ( IsSystemArsoAllowed )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 83;
        goto LABEL_26;
      }
      goto LABEL_27;
    }
    IsSystemArsoAllowed = RegSetValueExW(hKey, L"AutoLogonCount", 0, 4u, v46, 4u);
    if ( IsSystemArsoAllowed )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 84;
        goto LABEL_26;
      }
      goto LABEL_27;
    }
    RtlInitUnicodeString(&v54, L"DefaultPassword");
    RtlInitUnicodeString(&v55, L"_TBAL_{68EDDCF5-0AEB-4C28-A770-AF5302ECA3C9}");
    v29 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v54, (PLSA_UNICODE_STRING)&v55);
    IsSystemArsoAllowed = v29;
    if ( v29 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_1def5822bda638f577b76ed976884066_Traceguids,
          (unsigned int)v29);
      goto LABEL_151;
    }
    v7 = 1;
    v30 = RegSetValueExW(hKey, L"ForceAutoLockOnLogon", 0, 4u, v47, 4u);
    if ( v30 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          &WPP_1def5822bda638f577b76ed976884066_Traceguids,
          (unsigned int)v30);
LABEL_140:
      if ( v30 <= 0 )
      {
        IsSystemArsoAllowed = v30;
LABEL_144:
        v11 = IsSystemArsoAllowed < 0;
        goto LABEL_145;
      }
      IsSystemArsoAllowed = (unsigned __int16)v30;
LABEL_143:
      IsSystemArsoAllowed |= 0xC0070000;
      goto LABEL_144;
    }
    v30 = RegSetValueExW(hKey, L"AutoAdminLogon", 0, 1u, (const BYTE *)String2, 4u);
    if ( v30 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_1def5822bda638f577b76ed976884066_Traceguids,
          (unsigned int)v30);
      RegDeleteValueW(hKey, L"ForceAutoLockOnLogon");
      goto LABEL_140;
    }
LABEL_150:
    byte_1801A0D38 = 1;
    goto LABEL_151;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 82;
    goto LABEL_26;
  }
LABEL_27:
  v11 = IsSystemArsoAllowed < 0;
  if ( IsSystemArsoAllowed > 0 )
  {
    IsSystemArsoAllowed = (unsigned __int16)IsSystemArsoAllowed;
    goto LABEL_143;
  }
LABEL_145:
  if ( v11 && v7 )
    LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v54, 0);
  if ( LogonSessionWithSid )
    goto LABEL_151;
LABEL_152:
  if ( IsSystemArsoAllowed >= 0 )
  {
    SpmpEventWrite(&LSA_CONFIGURE_AUTOLOGON_CREDENTIALS_SUCCESS, L"uu", lpData, &DestinationString);
    goto LABEL_155;
  }
LABEL_154:
  SpmpEventWrite(&LSA_CONFIGURE_AUTOLOGON_CREDENTIALS_FAILURE, L"e", (unsigned int)IsSystemArsoAllowed);
LABEL_155:
  RegCloseKey(hKey);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  RtlLeaveCriticalSection(&g_autoLogonCritSec);
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x800000000000LL) )
  {
    v37 = v42[0];
    v36 = v34;
    v39 = v32;
    v35 = v3;
    v48 = v2;
    v49 = IsSystemArsoAllowed;
    v50 = 3;
    v53 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v31,
      (__int64)byte_18017FBF3);
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      &WPP_1def5822bda638f577b76ed976884066_Traceguids,
      (unsigned int)IsSystemArsoAllowed);
  return (unsigned int)IsSystemArsoAllowed;
}

```

## disassembly

```asm
0x1800fce7c  push    rbp
0x1800fce7e  push    rbx
0x1800fce7f  push    rsi
0x1800fce80  push    rdi
0x1800fce81  push    r12
0x1800fce83  push    r13
0x1800fce85  push    r14
0x1800fce87  push    r15
0x1800fce89  lea     rbp, [rsp-188h]
0x1800fce91  sub     rsp, 288h
0x1800fce98  mov     rax, cs:__security_cookie
0x1800fce9f  xor     rax, rsp
0x1800fcea2  mov     [rbp+1C0h+var_50], rax
0x1800fcea9  mov     rsi, rcx
0x1800fceac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fceb3  lea     r15, WPP_GLOBAL_Control
0x1800fceba  cmp     rcx, r15
0x1800fcebd  jz      short loc_1800FCEDA
0x1800fcebf  test    byte ptr [rcx+1Ch], 4
0x1800fcec3  jz      short loc_1800FCEDA
0x1800fcec5  mov     rcx, [rcx+10h]
0x1800fcec9  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fced0  mov     edx, 3Dh ; '='
0x1800fced5  call    WPP_SF_
0x1800fceda  xor     ebx, ebx
0x1800fcedc  mov     dword ptr [rbp+1C0h+String2], 31h ; '1'
0x1800fcee3  xorps   xmm0, xmm0
0x1800fcee6  mov     [rbp+1C0h+hKey], rbx
0x1800fceea  xorps   xmm1, xmm1
0x1800fceed  mov     [rbp+1C0h+var_22C], ebx
0x1800fcef0  xor     edx, edx; Val
0x1800fcef2  mov     [rbp+1C0h+var_228], ebx
0x1800fcef5  lea     edi, [rbx+1]
0x1800fcef8  mov     [rbp+1C0h+var_230], ebx
0x1800fcefb  mov     r8d, 104h; Size
0x1800fcf01  mov     dword ptr [rbp+1C0h+var_1F8], edi
0x1800fcf04  lea     rcx, [rbp+1C0h+Data]; void *
0x1800fcf08  mov     dword ptr [rbp+1C0h+var_1F4], edi
0x1800fcf0b  movups  xmmword ptr [rbp+1C0h+var_1B8.Length], xmm0
0x1800fcf0f  mov     r12d, ebx
0x1800fcf12  mov     [rbp+1C0h+PolicyHandle], rbx
0x1800fcf16  movups  xmmword ptr [rbp+1C0h+var_1A8.Length], xmm1
0x1800fcf1a  movups  xmmword ptr [rbp+1C0h+lpData], xmm0
0x1800fcf1e  movups  xmmword ptr [rbp+1C0h+DestinationString.Length], xmm1
0x1800fcf22  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.Length], xmm0
0x1800fcf26  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.ObjectName], xmm0
0x1800fcf2a  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fcf2e  call    memset_0
0x1800fcf33  xor     eax, eax
0x1800fcf35  mov     [rbp+1C0h+cbData], ebx
0x1800fcf38  test    rsi, rsi
0x1800fcf3b  mov     [rbp+1C0h+Type], ebx
0x1800fcf3e  lea     rcx, ?g_autoLogonCritSec@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800fcf45  mov     [rbp+1C0h+var_238], edi
0x1800fcf48  setnz   al
0x1800fcf4b  mov     [rbp+1C0h+var_23C], ebx
0x1800fcf4e  mov     [rbp+1C0h+var_210], eax
0x1800fcf51  mov     r13d, edi
0x1800fcf54  mov     [rbp+1C0h+var_234], ebx
0x1800fcf57  mov     [rbp+1C0h+var_240], ebx
0x1800fcf5a  mov     [rbp+1C0h+var_214], ebx
0x1800fcf5d  call    cs:__imp_RtlEnterCriticalSection
0x1800fcf64  nop     dword ptr [rax+rax+00h]
0x1800fcf69  cmp     cs:byte_1801A0D38, bl
0x1800fcf6f  jz      short loc_1800FCFA4
0x1800fcf71  xor     edi, edi
0x1800fcf73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fcf7a  cmp     rcx, r15
0x1800fcf7d  jz      short loc_1800FCF98
0x1800fcf7f  test    byte ptr [rcx+1Ch], 4
0x1800fcf83  jz      short loc_1800FCF98
0x1800fcf85  lea     edx, [rbx+3Eh]
0x1800fcf88  mov     rcx, [rcx+10h]
0x1800fcf8c  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fcf93  call    WPP_SF_
0x1800fcf98  mov     ebx, 0C00700B7h
0x1800fcf9d  mov     esi, edi
0x1800fcf9f  jmp     loc_1800FD84E
0x1800fcfa4  mov     rdx, cs:Sid2; Sid2
0x1800fcfab  test    rdx, rdx
0x1800fcfae  jnz     short loc_1800FCFE4
0x1800fcfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fcfb7  cmp     rcx, r15
0x1800fcfba  jz      short loc_1800FCFD7
0x1800fcfbc  test    byte ptr [rcx+1Ch], 4
0x1800fcfc0  jz      short loc_1800FCFD7
0x1800fcfc2  mov     rcx, [rcx+10h]
0x1800fcfc6  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fcfcd  mov     edx, 3Fh ; '?'
0x1800fcfd2  call    WPP_SF_
0x1800fcfd7  mov     ebx, 0C0000371h
0x1800fcfdc  mov     esi, r12d
0x1800fcfdf  jmp     loc_1800FD84E
0x1800fcfe4  test    rsi, rsi
0x1800fcfe7  jz      short loc_1800FD02F
0x1800fcfe9  mov     rcx, rsi; Sid1
0x1800fcfec  call    cs:__imp_RtlEqualSid
0x1800fcff3  nop     dword ptr [rax+rax+00h]
0x1800fcff8  test    al, al
0x1800fcffa  jnz     short loc_1800FD02F
0x1800fcffc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd003  cmp     rcx, r15
0x1800fd006  jz      short loc_1800FD023
0x1800fd008  test    byte ptr [rcx+1Ch], 4
0x1800fd00c  jz      short loc_1800FD023
0x1800fd00e  mov     rcx, [rcx+10h]
0x1800fd012  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd019  mov     edx, 40h ; '@'
0x1800fd01e  call    WPP_SF_
0x1800fd023  xor     edi, edi
0x1800fd025  mov     ebx, 0C0000022h
0x1800fd02a  jmp     loc_1800FCF9D
0x1800fd02f  lea     rax, [rbp+1C0h+hKey]
0x1800fd033  mov     r9d, 2001Fh; samDesired
0x1800fd039  xor     r8d, r8d; ulOptions
0x1800fd03c  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800fd041  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800fd048  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fd04f  xor     r15b, r15b
0x1800fd052  call    cs:__imp_RegOpenKeyExW
0x1800fd059  nop     dword ptr [rax+rax+00h]
0x1800fd05e  mov     ebx, eax
0x1800fd060  test    eax, eax
0x1800fd062  jz      short loc_1800FD0A7
0x1800fd064  xor     r14d, r14d
0x1800fd067  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd06e  lea     rsi, WPP_GLOBAL_Control
0x1800fd075  cmp     rcx, rsi
0x1800fd078  jz      short loc_1800FD097
0x1800fd07a  test    [rcx+1Ch], dil
0x1800fd07e  jz      short loc_1800FD097
0x1800fd080  lea     edx, [r14+41h]
0x1800fd084  mov     rcx, [rcx+10h]
0x1800fd088  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd08f  mov     r9d, ebx
0x1800fd092  call    WPP_SF_d
0x1800fd097  test    ebx, ebx
0x1800fd099  jle     loc_1800FD7F3
0x1800fd09f  movzx   ebx, bx
0x1800fd0a2  jmp     loc_1800FD7EB
0x1800fd0a7  mov     rcx, [rbp+1C0h+hKey]; hKey
0x1800fd0ab  lea     rax, [rbp+1C0h+cbData]
0x1800fd0af  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1800fd0b4  lea     r9, [rbp+1C0h+Type]; lpType
0x1800fd0b8  lea     rax, [rbp+1C0h+Data]
0x1800fd0bc  mov     r14d, 4
0x1800fd0c2  xor     r8d, r8d; lpReserved
0x1800fd0c5  mov     [rsp+2C0h+phkResult], rax; lpData
0x1800fd0ca  lea     rdx, aAutoadminlogon; "AutoAdminLogon"
0x1800fd0d1  mov     [rbp+1C0h+cbData], r14d
0x1800fd0d5  call    cs:__imp_RegQueryValueExW
0x1800fd0dc  nop     dword ptr [rax+rax+00h]
0x1800fd0e1  test    eax, eax
0x1800fd0e3  jnz     short loc_1800FD139
0x1800fd0e5  cmp     [rbp+1C0h+Type], r14d
0x1800fd0e9  jnz     short loc_1800FD0F7
0x1800fd0eb  cmp     [rbp+1C0h+cbData], r14d
0x1800fd0ef  jnz     short loc_1800FD0F7
0x1800fd0f1  cmp     dword ptr [rbp+1C0h+Data], r12d
0x1800fd0f5  jnz     short loc_1800FD10E
0x1800fd0f7  mov     r8d, 2; MaxCount
0x1800fd0fd  lea     rdx, [rbp+1C0h+String2]; String2
0x1800fd101  lea     rcx, [rbp+1C0h+Data]; String1
0x1800fd105  call    wcsncmp_0
0x1800fd10a  test    eax, eax
0x1800fd10c  jnz     short loc_1800FD139
0x1800fd10e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd115  lea     rax, WPP_GLOBAL_Control
0x1800fd11c  cmp     rcx, rax
0x1800fd11f  jz      loc_1800FCF98
0x1800fd125  test    [rcx+1Ch], r14b
0x1800fd129  jz      loc_1800FCF98
0x1800fd12f  mov     edx, 42h ; 'B'
0x1800fd134  jmp     loc_1800FCF88
0x1800fd139  lea     r8, [rbp+1C0h+var_228]; int *
0x1800fd13d  mov     cl, dil; unsigned __int8
0x1800fd140  lea     rdx, [rbp+1C0h+var_22C]; int *
0x1800fd144  call    ?LsapIsSystemArsoAllowed@@YAJEPEAH0@Z; LsapIsSystemArsoAllowed(uchar,int *,int *)
0x1800fd149  mov     ebx, eax
0x1800fd14b  test    eax, eax
0x1800fd14d  jns     short loc_1800FD17D
0x1800fd14f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd156  lea     rax, WPP_GLOBAL_Control
0x1800fd15d  cmp     rcx, rax
0x1800fd160  jz      loc_1800FCFDC
0x1800fd166  test    [rcx+1Ch], dil
0x1800fd16a  jz      loc_1800FCFDC
0x1800fd170  mov     edx, 43h ; 'C'
0x1800fd175  mov     r9d, ebx
0x1800fd178  jmp     loc_1800FD318
0x1800fd17d  cmp     [rbp+1C0h+var_22C], r12d
0x1800fd181  jnz     short loc_1800FD1BB
0x1800fd183  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd18a  lea     rax, WPP_GLOBAL_Control
0x1800fd191  cmp     rcx, rax
0x1800fd194  jz      short loc_1800FD1B1
0x1800fd196  test    [rcx+1Ch], r14b
0x1800fd19a  jz      short loc_1800FD1B1
0x1800fd19c  mov     edx, 44h ; 'D'
0x1800fd1a1  mov     rcx, [rcx+10h]
0x1800fd1a5  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd1ac  call    WPP_SF_
0x1800fd1b1  mov     ebx, 0C0000022h
0x1800fd1b6  jmp     loc_1800FCFDC
0x1800fd1bb  test    rsi, rsi
0x1800fd1be  jz      loc_1800FD25F
0x1800fd1c4  lea     r8, [rbp+1C0h+var_234]; int *
0x1800fd1c8  mov     rcx, rsi; Sid
0x1800fd1cb  lea     rdx, [rbp+1C0h+var_238]; int *
0x1800fd1cf  call    ?LsapIsUserArsoEnabled@@YAJPEAU_SID@@PEAH1@Z; LsapIsUserArsoEnabled(_SID *,int *,int *)
0x1800fd1d4  test    eax, eax
0x1800fd1d6  jns     short loc_1800FD20F
0x1800fd1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd1df  lea     rsi, WPP_GLOBAL_Control
0x1800fd1e6  cmp     rcx, rsi
0x1800fd1e9  jz      short loc_1800FD253
0x1800fd1eb  test    [rcx+1Ch], dil
0x1800fd1ef  jz      short loc_1800FD253
0x1800fd1f1  mov     rcx, [rcx+10h]
0x1800fd1f5  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd1fc  mov     edx, 45h ; 'E'
0x1800fd201  mov     r9d, eax
0x1800fd204  call    WPP_SF_d
0x1800fd209  mov     r13d, [rbp+1C0h+var_238]
0x1800fd20d  jmp     short loc_1800FD244
0x1800fd20f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd216  lea     rsi, WPP_GLOBAL_Control
0x1800fd21d  cmp     rcx, rsi
0x1800fd220  jz      short loc_1800FD253
0x1800fd222  test    [rcx+1Ch], r14b
0x1800fd226  jz      short loc_1800FD253
0x1800fd228  mov     r13d, [rbp+1C0h+var_238]
0x1800fd22c  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd233  mov     rcx, [rcx+10h]
0x1800fd237  mov     r9d, r13d
0x1800fd23a  mov     edx, 46h ; 'F'
0x1800fd23f  call    WPP_SF_d
0x1800fd244  mov     eax, [rbp+1C0h+var_234]
0x1800fd247  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd24e  mov     [rbp+1C0h+var_23C], eax
0x1800fd251  jmp     short loc_1800FD2B2
0x1800fd253  mov     eax, [rbp+1C0h+var_234]
0x1800fd256  mov     r13d, [rbp+1C0h+var_238]
0x1800fd25a  mov     [rbp+1C0h+var_23C], eax
0x1800fd25d  jmp     short loc_1800FD2B2
0x1800fd25f  call    ?GetSystemArsoConsentValue@@YAKXZ; GetSystemArsoConsentValue(void)
0x1800fd264  mov     ebx, eax
0x1800fd266  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd26d  lea     rsi, WPP_GLOBAL_Control
0x1800fd274  cmp     rcx, rsi
0x1800fd277  jz      short loc_1800FD29E
0x1800fd279  test    [rcx+1Ch], r14b
0x1800fd27d  jz      short loc_1800FD29E
0x1800fd27f  mov     rcx, [rcx+10h]
0x1800fd283  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd28a  mov     edx, 47h ; 'G'
0x1800fd28f  mov     r9d, eax
0x1800fd292  call    WPP_SF_d
0x1800fd297  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd29e  cmp     ebx, 2
0x1800fd2a1  jnz     short loc_1800FD2AB
0x1800fd2a3  xor     r13d, r13d
0x1800fd2a6  mov     [rbp+1C0h+var_23C], edi
0x1800fd2a9  jmp     short loc_1800FD2B7
0x1800fd2ab  cmp     ebx, edi
0x1800fd2ad  jnz     short loc_1800FD2D4
0x1800fd2af  mov     [rbp+1C0h+var_23C], edi
0x1800fd2b2  test    r13d, r13d
0x1800fd2b5  jnz     short loc_1800FD2D4
0x1800fd2b7  cmp     rcx, rsi
0x1800fd2ba  jz      loc_1800FD1B1
0x1800fd2c0  test    [rcx+1Ch], r14b
0x1800fd2c4  jz      loc_1800FD1B1
0x1800fd2ca  mov     edx, 48h ; 'H'
0x1800fd2cf  jmp     loc_1800FD1A1
0x1800fd2d4  lea     r9, [rbp+1C0h+PolicyHandle]; PolicyHandle
0x1800fd2d8  mov     r8d, 21h ; '!'; DesiredAccess
0x1800fd2de  lea     rdx, [rbp+1C0h+ObjectAttributes]; ObjectAttributes
0x1800fd2e2  xor     ecx, ecx; SystemName
0x1800fd2e4  call    cs:__imp_LsaOpenPolicy
0x1800fd2eb  nop     dword ptr [rax+rax+00h]
0x1800fd2f0  mov     ebx, eax
0x1800fd2f2  test    eax, eax
0x1800fd2f4  jns     short loc_1800FD32D
0x1800fd2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fd2fd  cmp     rcx, rsi
0x1800fd300  jz      loc_1800FCFDC
0x1800fd306  test    [rcx+1Ch], dil
0x1800fd30a  jz      loc_1800FCFDC
0x1800fd310  mov     edx, 49h ; 'I'
0x1800fd315  mov     r9d, eax
0x1800fd318  mov     rcx, [rcx+10h]
0x1800fd31c  lea     r8, WPP_1def5822bda638f577b76ed976884066_Traceguids
0x1800fd323  call    WPP_SF_d
0x1800fd328  jmp     loc_1800FCFDC
0x1800fd32d  call    ?LsapLocateLogonSessionWithSid@@YAPEAU_LSAP_LOGON_SESSION@@PEAX@Z; LsapLocateLogonSessionWithSid(void *)
0x1800fd332  mov     r14, rax
0x1800fd335  test    rax, rax
0x1800fd338  jnz     short loc_1800FD369
0x1800fd33a  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
