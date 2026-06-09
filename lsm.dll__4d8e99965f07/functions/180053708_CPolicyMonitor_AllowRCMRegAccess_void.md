# CPolicyMonitor::AllowRCMRegAccess(void)

- ea: `0x180053708`
- end: `0x180053e64`
- name: `?AllowRCMRegAccess@CPolicyMonitor@@AEAAJXZ`
- size: `1884`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180054be4`

## callees

- `0x180001b90`
- `0x18005312c`
- `0x180053150`
- `0x180053174`
- `0x180053648`
- `0x180053708`
- `0x180055a94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005398a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005398a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ce9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800537a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800537a7`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180053833`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800538f0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180053833`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800538f0`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180053d68`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180053d68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005385a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053bba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005385a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053bba`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180053b2e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180053b2e`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180053a99`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180053a99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180053976`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180053976`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180053c48`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180053c48`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180053cd9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180053cd9`

## string_xrefs

- `0x1800537d8`: `AllowRCMRegAccess`
- `0x180053891`: `AllowRCMRegAccess`
- `0x18005391b`: `AllowRCMRegAccess`
- `0x1800539ad`: `AllowRCMRegAccess`
- `0x180053a48`: `AllowRCMRegAccess`
- `0x180053ac4`: `AllowRCMRegAccess`
- `0x180053b66`: `AllowRCMRegAccess`
- `0x180053bf1`: `AllowRCMRegAccess`
- `0x180053c7f`: `AllowRCMRegAccess`
- `0x180053d10`: `AllowRCMRegAccess`
- `0x180053d97`: `AllowRCMRegAccess`
- `0x180053dd2`: `AllowRCMRegAccess`
- `0x1800537ea`: `RegCreateKeyExW`
- `0x18005392d`: `RegGetKeySecurity`
- `0x180053de4`: `RegGetKeySecurity`
- `0x1800539bf`: `GetSecurityDescriptorDacl`
- `0x180053a5a`: `AllocateAndInitializeServiceSid`
- `0x180053ad6`: `GetEffectiveRightsFromAcl`
- `0x180053b78`: `SetEntriesInAcl`
- `0x180053c91`: `InitializeSecurityDescriptor`
- `0x180053d22`: `SetSecurityDescriptorDacl`
- `0x180053da9`: `RegSetKeySecurity`

## pseudocode

```c
__int64 __fastcall CPolicyMonitor::AllowRCMRegAccess(CPolicyMonitor *this)
{
  LSTATUS v1; // eax
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  int KeySecurity; // edi
  char *v6; // rdx
  const char **v7; // rax
  HLOCAL v8; // rax
  int v9; // r8d
  int v10; // r9d
  PSECURITY_DESCRIPTOR v11; // rbx
  LSTATUS v12; // eax
  signed int LastError; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  char *v17; // rdx
  const char *v18; // rax
  PACL *p_NewAcl; // rax
  WCHAR *v20; // rax
  signed int v21; // eax
  signed int EffectiveRightsFromAclW; // eax
  signed int v23; // eax
  HLOCAL v24; // rax
  int v25; // r8d
  int v26; // r9d
  PSECURITY_DESCRIPTOR v27; // rbx
  signed int v28; // eax
  signed int v29; // eax
  LSTATUS v30; // eax
  const char *v31; // rax
  const char **samDesired; // [rsp+28h] [rbp-91h]
  const char **samDesireda; // [rsp+28h] [rbp-91h]
  const char **phkResult; // [rsp+38h] [rbp-81h]
  const char **phkResulta; // [rsp+38h] [rbp-81h]
  const char *v37; // [rsp+50h] [rbp-69h] BYREF
  const char *v38; // [rsp+58h] [rbp-61h] BYREF
  PACL NewAcl; // [rsp+60h] [rbp-59h] BYREF
  const char *v40; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  WINBOOL bDaclPresent; // [rsp+78h] [rbp-41h] BYREF
  PACL pDacl; // [rsp+80h] [rbp-39h] BYREF
  PACL v44; // [rsp+88h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR v45; // [rsp+90h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp-21h] BYREF
  WCHAR *v47; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int v48[6]; // [rsp+A8h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C0h] [rbp+7h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+120h] [rbp+67h] BYREF
  int v51; // [rsp+124h] [rbp+6Bh]
  DWORD pAccessRights; // [rsp+128h] [rbp+6Fh] BYREF
  int v53; // [rsp+130h] [rbp+77h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+138h] [rbp+7Fh] BYREF

  v51 = HIDWORD(this);
  v48[0] = 446051430;
  v48[1] = 1559341753;
  v48[2] = -133025767;
  v48[3] = 1950928533;
  v48[4] = 810483104;
  v47 = 0;
  pSecurityDescriptor = 0;
  v45 = 0;
  v44 = 0;
  pDacl = 0;
  cbSecurityDescriptor = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStationsStartError",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  KeySecurity = v1;
  if ( v1 > 0 )
    KeySecurity = (unsigned __int16)v1 | 0x80070000;
  if ( KeySecurity < 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      NewAcl = (PACL)"AllowRCMRegAccess";
      v6 = byte_1800C5DE5;
      v37 = "RegCreateKeyExW";
      v38 = "Warning HResult failed";
      phkResult = (const char **)&NewAcl;
      samDesired = &v37;
      v7 = &v38;
LABEL_64:
      v53 = KeySecurity;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v2,
        (_DWORD)v6,
        v3,
        v4,
        (__int64)v7,
        (__int64)samDesired,
        (__int64)&v53,
        (__int64)phkResult);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
  {
    if ( KeySecurity <= 0 )
    {
LABEL_61:
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_65;
      v40 = "AllowRCMRegAccess";
      v6 = byte_1800C5DA3;
      v38 = "RegGetKeySecurity";
      v31 = "Error condition failed";
      goto LABEL_63;
    }
LABEL_60:
    KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
    goto LABEL_61;
  }
  if ( !cbSecurityDescriptor )
    goto LABEL_60;
  v8 = LocalAlloc(KeySecurity - 58, cbSecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &pSecurityDescriptor,
    v8);
  v11 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
  {
    KeySecurity = -2147024882;
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v53 = -2147024882;
      v38 = "AllowRCMRegAccess";
      v37 = "LocalAlloc";
      NewAcl = (PACL)"Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)byte_1800C5D61,
        v9,
        v10,
        (__int64)&NewAcl,
        (__int64)&v37,
        (__int64)&v53,
        (__int64)&v38);
    }
    goto LABEL_65;
  }
  v12 = RegGetKeySecurity(hKey, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
  KeySecurity = v12;
  if ( v12 > 0 )
    KeySecurity = (unsigned __int16)v12 | 0x80070000;
  if ( KeySecurity >= 0 )
  {
    if ( !GetSecurityDescriptorDacl(v11, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      KeySecurity = LastError;
      if ( LastError > 0 )
        KeySecurity = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_23;
      v38 = "AllowRCMRegAccess";
      v17 = byte_1800C5CDD;
      v18 = "GetSecurityDescriptorDacl";
      goto LABEL_21;
    }
    v20 = (WCHAR *)AllocateAndInitializeServiceSid(v48);
    v47 = v20;
    if ( !v20 )
    {
      v21 = GetLastError();
      KeySecurity = v21;
      if ( v21 > 0 )
        KeySecurity = (unsigned __int16)v21 | 0x80070000;
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_23;
      v38 = "AllowRCMRegAccess";
      v17 = byte_1800C5C9B;
      v18 = "AllocateAndInitializeServiceSid";
LABEL_21:
      v37 = v18;
      NewAcl = (PACL)"Error condition failed";
      phkResulta = &v38;
      samDesireda = &v37;
      p_NewAcl = &NewAcl;
LABEL_22:
      v53 = KeySecurity;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v14,
        (_DWORD)v17,
        v15,
        v16,
        (__int64)p_NewAcl,
        (__int64)samDesireda,
        (__int64)&v53,
        (__int64)phkResulta);
LABEL_23:
      if ( KeySecurity >= 0 )
        KeySecurity = -2147467259;
      goto LABEL_65;
    }
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.grfAccessPermissions = 131078;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    pListOfExplicitEntries.Trustee.ptstrName = v20;
    pAccessRights = 0;
    EffectiveRightsFromAclW = GetEffectiveRightsFromAclW(pDacl, &pListOfExplicitEntries.Trustee, &pAccessRights);
    KeySecurity = EffectiveRightsFromAclW;
    if ( EffectiveRightsFromAclW > 0 )
      KeySecurity = (unsigned __int16)EffectiveRightsFromAclW | 0x80070000;
    if ( KeySecurity < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v38 = "AllowRCMRegAccess";
        v6 = byte_1800C5C59;
        v37 = "GetEffectiveRightsFromAcl";
        NewAcl = (PACL)"Warning HResult failed";
        phkResult = &v38;
        samDesired = &v37;
        v7 = (const char **)&NewAcl;
        goto LABEL_64;
      }
      goto LABEL_65;
    }
    if ( (pAccessRights & 0x20006) != 0 )
      goto LABEL_65;
    NewAcl = 0;
    v23 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
    KeySecurity = v23;
    if ( v23 > 0 )
      KeySecurity = (unsigned __int16)v23 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v44,
      NewAcl);
    if ( KeySecurity < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v38 = "AllowRCMRegAccess";
        v6 = &byte_1800C5C17;
        v37 = "SetEntriesInAcl";
        v40 = "Warning HResult failed";
        phkResult = &v38;
        samDesired = &v37;
        v7 = &v40;
        goto LABEL_64;
      }
      goto LABEL_65;
    }
    v24 = LocalAlloc(0x40u, 0x28u);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v45,
      v24);
    v27 = v45;
    if ( !v45 )
    {
      KeySecurity = -2147024882;
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v53 = -2147024882;
        v40 = "AllowRCMRegAccess";
        v38 = "LocalAlloc";
        v37 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147024882,
          (unsigned int)byte_1800C5BD5,
          v25,
          v26,
          (__int64)&v37,
          (__int64)&v38,
          (__int64)&v53,
          (__int64)&v40);
      }
      goto LABEL_65;
    }
    if ( !InitializeSecurityDescriptor(v45, 1u) )
    {
      v28 = GetLastError();
      KeySecurity = v28;
      if ( v28 > 0 )
        KeySecurity = (unsigned __int16)v28 | 0x80070000;
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_23;
      v40 = "AllowRCMRegAccess";
      v17 = byte_1800C5B93;
      v38 = "InitializeSecurityDescriptor";
      v37 = "Error condition failed";
      phkResulta = &v40;
      samDesireda = &v38;
      p_NewAcl = (PACL *)&v37;
      goto LABEL_22;
    }
    if ( !SetSecurityDescriptorDacl(v27, 1, v44, 0) )
    {
      v29 = GetLastError();
      KeySecurity = v29;
      if ( v29 > 0 )
        KeySecurity = (unsigned __int16)v29 | 0x80070000;
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_23;
      v40 = "AllowRCMRegAccess";
      v17 = byte_1800C5B51;
      v38 = "SetSecurityDescriptorDacl";
      v37 = "Error condition failed";
      phkResulta = &v40;
      samDesireda = &v38;
      p_NewAcl = (PACL *)&v37;
      goto LABEL_22;
    }
    v30 = RegSetKeySecurity(hKey, 4u, v27);
    KeySecurity = v30;
    if ( v30 > 0 )
      KeySecurity = (unsigned __int16)v30 | 0x80070000;
    if ( KeySecurity >= 0 || (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_65;
    v40 = "AllowRCMRegAccess";
    v6 = &byte_1800C5B0F;
    v38 = "RegSetKeySecurity";
    v31 = "Warning HResult failed";
LABEL_63:
    v37 = v31;
    phkResult = &v40;
    samDesired = &v38;
    v7 = &v37;
    goto LABEL_64;
  }
  if ( (unsigned int)dword_1800DF020 > 3 )
  {
    v38 = "AllowRCMRegAccess";
    v6 = &byte_1800C5D1F;
    v37 = "RegGetKeySecurity";
    NewAcl = (PACL)"Warning HResult failed";
    phkResult = &v38;
    samDesired = &v37;
    v7 = (const char **)&NewAcl;
    goto LABEL_64;
  }
LABEL_65:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)KeySecurity;
}

```

## disassembly

```asm
0x180053708  mov     qword ptr [rsp-8+cbSecurityDescriptor], rcx
0x18005370d  push    rbp
0x18005370e  push    rbx
0x18005370f  push    rsi
0x180053710  push    rdi
0x180053711  push    r14
0x180053713  lea     rbp, [rsp-37h]
0x180053718  sub     rsp, 0F0h
0x18005371f  xor     esi, esi
0x180053721  mov     [rbp+57h+var_68], 1A963466h
0x180053728  mov     [rsp+110h+lpdwDisposition], rsi; lpdwDisposition
0x18005372d  lea     rax, [rbp+57h+hKey]
0x180053731  mov     [rsp+110h+phkResult], rax; phkResult
0x180053736  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Control\\Ter"...
0x18005373d  xorps   xmm0, xmm0
0x180053740  mov     [rsp+110h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180053745  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x18005374d  xor     r9d, r9d; lpClass
0x180053750  xor     r8d, r8d; Reserved
0x180053753  mov     [rsp+110h+dwOptions], esi; dwOptions
0x180053757  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005375e  mov     [rbp+57h+var_64], 5CF1AAB9h
0x180053765  mov     [rbp+57h+var_60], 0F8123019h
0x18005376c  mov     [rbp+57h+var_5C], 7448CE95h
0x180053773  mov     [rbp+57h+var_58], 304EFDA0h
0x18005377a  mov     [rbp+57h+var_70], rsi
0x18005377e  mov     [rbp+57h+pSecurityDescriptor], rsi
0x180053782  mov     [rbp+57h+var_80], rsi
0x180053786  mov     [rbp+57h+var_88], rsi
0x18005378a  mov     [rbp+57h+pDacl], rsi
0x18005378e  mov     [rbp+57h+cbSecurityDescriptor], esi
0x180053791  mov     [rbp+57h+bDaclPresent], esi
0x180053794  mov     [rbp+57h+bDaclDefaulted], esi
0x180053797  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18005379b  mov     [rbp+57h+hKey], rsi
0x18005379f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800537a3  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800537a7  call    cs:__imp_RegCreateKeyExW
0x1800537ae  nop     dword ptr [rax+rax+00h]
0x1800537b3  mov     edi, eax
0x1800537b5  mov     r14d, 80070000h
0x1800537bb  test    eax, eax
0x1800537bd  jle     short loc_1800537C5
0x1800537bf  movzx   edi, ax
0x1800537c2  or      edi, r14d
0x1800537c5  test    edi, edi
0x1800537c7  jns     short loc_180053824
0x1800537c9  mov     eax, cs:dword_1800DF020
0x1800537cf  cmp     eax, 3
0x1800537d2  jbe     loc_180053E26
0x1800537d8  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x1800537df  mov     [rbp+57h+NewAcl], rax
0x1800537e3  lea     rdx, byte_1800C5DE5
0x1800537ea  lea     rax, aRegcreatekeyex; "RegCreateKeyExW"
0x1800537f1  mov     [rbp+57h+var_C0], rax
0x1800537f5  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800537fc  mov     [rbp+57h+var_B8], rax
0x180053800  lea     rax, [rbp+57h+NewAcl]
0x180053804  mov     [rsp+110h+phkResult], rax
0x180053809  lea     rax, [rbp+57h+arg_10]
0x18005380d  mov     [rsp+110h+lpSecurityAttributes], rax
0x180053812  lea     rax, [rbp+57h+var_C0]
0x180053816  mov     qword ptr [rsp+110h+samDesired], rax
0x18005381b  lea     rax, [rbp+57h+var_B8]
0x18005381f  jmp     loc_180053E19
0x180053824  mov     rcx, [rbp+57h+hKey]; hKey
0x180053828  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18005382c  xor     r8d, r8d; pSecurityDescriptor
0x18005382f  lea     edx, [r8+4]; SecurityInformation
0x180053833  call    cs:__imp_RegGetKeySecurity
0x18005383a  nop     dword ptr [rax+rax+00h]
0x18005383f  mov     edi, eax
0x180053841  cmp     eax, 7Ah ; 'z'
0x180053844  jnz     loc_180053DBD
0x18005384a  mov     eax, [rbp+57h+cbSecurityDescriptor]
0x18005384d  test    eax, eax
0x18005384f  jz      loc_180053DC1
0x180053855  mov     edx, eax; uBytes
0x180053857  lea     ecx, [rdi-3Ah]; uFlags
0x18005385a  call    cs:__imp_LocalAlloc
0x180053861  nop     dword ptr [rax+rax+00h]
0x180053866  mov     rdx, rax
0x180053869  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18005386d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180053872  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180053876  test    rbx, rbx
0x180053879  jnz     short loc_1800538E0
0x18005387b  mov     eax, cs:dword_1800DF020
0x180053881  mov     ecx, 8007000Eh
0x180053886  mov     edi, ecx
0x180053888  cmp     eax, 3
0x18005388b  jbe     loc_180053E26
0x180053891  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053898  mov     [rbp+57h+arg_10], ecx
0x18005389b  mov     [rbp+57h+var_B8], rax
0x18005389f  lea     rdx, byte_1800C5D61
0x1800538a6  lea     rax, aLocalalloc; "LocalAlloc"
0x1800538ad  mov     [rbp+57h+var_C0], rax
0x1800538b1  lea     rax, aErrorCondition; "Error condition failed"
0x1800538b8  mov     [rbp+57h+NewAcl], rax
0x1800538bc  lea     rax, [rbp+57h+var_B8]
0x1800538c0  mov     [rsp+110h+phkResult], rax
0x1800538c5  lea     rax, [rbp+57h+arg_10]
0x1800538c9  mov     [rsp+110h+lpSecurityAttributes], rax
0x1800538ce  lea     rax, [rbp+57h+var_C0]
0x1800538d2  mov     qword ptr [rsp+110h+samDesired], rax
0x1800538d7  lea     rax, [rbp+57h+NewAcl]
0x1800538db  jmp     loc_180053E1C
0x1800538e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800538e4  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800538e8  mov     r8, rbx; pSecurityDescriptor
0x1800538eb  mov     edx, 4; SecurityInformation
0x1800538f0  call    cs:__imp_RegGetKeySecurity
0x1800538f7  nop     dword ptr [rax+rax+00h]
0x1800538fc  mov     edi, eax
0x1800538fe  test    eax, eax
0x180053900  jle     short loc_180053908
0x180053902  movzx   edi, ax
0x180053905  or      edi, r14d
0x180053908  test    edi, edi
0x18005390a  jns     short loc_180053967
0x18005390c  mov     eax, cs:dword_1800DF020
0x180053912  cmp     eax, 3
0x180053915  jbe     loc_180053E26
0x18005391b  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053922  mov     [rbp+57h+var_B8], rax
0x180053926  lea     rdx, byte_1800C5D1F
0x18005392d  lea     rax, aReggetkeysecur; "RegGetKeySecurity"
0x180053934  mov     [rbp+57h+var_C0], rax
0x180053938  lea     rax, aWarningHresult; "Warning HResult failed"
0x18005393f  mov     [rbp+57h+NewAcl], rax
0x180053943  lea     rax, [rbp+57h+var_B8]
0x180053947  mov     [rsp+110h+phkResult], rax
0x18005394c  lea     rax, [rbp+57h+arg_10]
0x180053950  mov     [rsp+110h+lpSecurityAttributes], rax
0x180053955  lea     rax, [rbp+57h+var_C0]
0x180053959  mov     qword ptr [rsp+110h+samDesired], rax
0x18005395e  lea     rax, [rbp+57h+NewAcl]
0x180053962  jmp     loc_180053E19
0x180053967  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18005396b  mov     rcx, rbx; pSecurityDescriptor
0x18005396e  lea     r8, [rbp+57h+pDacl]; pDacl
0x180053972  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180053976  call    cs:__imp_GetSecurityDescriptorDacl
0x18005397d  nop     dword ptr [rax+rax+00h]
0x180053982  test    eax, eax
0x180053984  jnz     loc_180053A13
0x18005398a  call    cs:__imp_GetLastError
0x180053991  nop     dword ptr [rax+rax+00h]
0x180053996  mov     edi, eax
0x180053998  test    eax, eax
0x18005399a  jle     short loc_1800539A2
0x18005399c  movzx   edi, ax
0x18005399f  or      edi, r14d
0x1800539a2  mov     eax, cs:dword_1800DF020
0x1800539a8  cmp     eax, 3
0x1800539ab  jbe     short loc_180053A01
0x1800539ad  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x1800539b4  mov     [rbp+57h+var_B8], rax
0x1800539b8  lea     rdx, byte_1800C5CDD
0x1800539bf  lea     rax, aGetsecuritydes_3; "GetSecurityDescriptorDacl"
0x1800539c6  mov     [rbp+57h+var_C0], rax
0x1800539ca  lea     rax, aErrorCondition; "Error condition failed"
0x1800539d1  mov     [rbp+57h+NewAcl], rax
0x1800539d5  lea     rax, [rbp+57h+var_B8]
0x1800539d9  mov     [rsp+110h+phkResult], rax
0x1800539de  lea     rax, [rbp+57h+arg_10]
0x1800539e2  mov     [rsp+110h+lpSecurityAttributes], rax
0x1800539e7  lea     rax, [rbp+57h+var_C0]
0x1800539eb  mov     qword ptr [rsp+110h+samDesired], rax
0x1800539f0  lea     rax, [rbp+57h+NewAcl]
0x1800539f4  mov     qword ptr [rsp+110h+dwOptions], rax
0x1800539f9  mov     [rbp+57h+arg_10], edi
0x1800539fc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180053a01  test    edi, edi
0x180053a03  js      loc_180053E26
0x180053a09  mov     edi, 80004005h
0x180053a0e  jmp     loc_180053E26
0x180053a13  lea     rcx, [rbp+57h+var_68]; unsigned int *
0x180053a17  call    ?AllocateAndInitializeServiceSid@@YAPEAXQEAK@Z; AllocateAndInitializeServiceSid(ulong * const)
0x180053a1c  mov     [rbp+57h+var_70], rax
0x180053a20  test    rax, rax
0x180053a23  jnz     short loc_180053A66
0x180053a25  call    cs:__imp_GetLastError
0x180053a2c  nop     dword ptr [rax+rax+00h]
0x180053a31  mov     edi, eax
0x180053a33  test    eax, eax
0x180053a35  jle     short loc_180053A3D
0x180053a37  movzx   edi, ax
0x180053a3a  or      edi, r14d
0x180053a3d  mov     eax, cs:dword_1800DF020
0x180053a43  cmp     eax, 3
0x180053a46  jbe     short loc_180053A01
0x180053a48  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053a4f  mov     [rbp+57h+var_B8], rax
0x180053a53  lea     rdx, byte_1800C5C9B
0x180053a5a  lea     rax, aAllocateandini_0; "AllocateAndInitializeServiceSid"
0x180053a61  jmp     loc_1800539C6
0x180053a66  mov     rcx, [rbp+57h+pDacl]; pacl
0x180053a6a  lea     r8, [rbp+57h+pAccessRights]; pAccessRights
0x180053a6e  mov     ebx, 20006h
0x180053a73  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180053a7a  lea     rdx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x180053a7e  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], ebx
0x180053a81  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x180053a88  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180053a8b  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180053a92  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180053a96  mov     [rbp+57h+pAccessRights], esi
0x180053a99  call    cs:__imp_GetEffectiveRightsFromAclW
0x180053aa0  nop     dword ptr [rax+rax+00h]
0x180053aa5  mov     edi, eax
0x180053aa7  test    eax, eax
0x180053aa9  jle     short loc_180053AB1
0x180053aab  movzx   edi, ax
0x180053aae  or      edi, r14d
0x180053ab1  test    edi, edi
0x180053ab3  jns     short loc_180053B10
0x180053ab5  mov     eax, cs:dword_1800DF020
0x180053abb  cmp     eax, 3
0x180053abe  jbe     loc_180053E26
0x180053ac4  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053acb  mov     [rbp+57h+var_B8], rax
0x180053acf  lea     rdx, byte_1800C5C59
0x180053ad6  lea     rax, aGeteffectiveri; "GetEffectiveRightsFromAcl"
0x180053add  mov     [rbp+57h+var_C0], rax
0x180053ae1  lea     rax, aWarningHresult; "Warning HResult failed"
0x180053ae8  mov     [rbp+57h+NewAcl], rax
0x180053aec  lea     rax, [rbp+57h+var_B8]
0x180053af0  mov     [rsp+110h+phkResult], rax
0x180053af5  lea     rax, [rbp+57h+arg_10]
0x180053af9  mov     [rsp+110h+lpSecurityAttributes], rax
0x180053afe  lea     rax, [rbp+57h+var_C0]
0x180053b02  mov     qword ptr [rsp+110h+samDesired], rax
0x180053b07  lea     rax, [rbp+57h+NewAcl]
0x180053b0b  jmp     loc_180053E19
0x180053b10  test    [rbp+57h+pAccessRights], ebx
0x180053b13  jnz     loc_180053E26
0x180053b19  mov     r8, [rbp+57h+pDacl]; OldAcl
0x180053b1d  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180053b21  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180053b25  mov     [rbp+57h+NewAcl], rsi
0x180053b29  mov     ecx, 1; cCountOfExplicitEntries
0x180053b2e  call    cs:__imp_SetEntriesInAclW
0x180053b35  nop     dword ptr [rax+rax+00h]
0x180053b3a  mov     edi, eax
0x180053b3c  test    eax, eax
0x180053b3e  jle     short loc_180053B46
0x180053b40  movzx   edi, ax
0x180053b43  or      edi, r14d
0x180053b46  mov     rdx, [rbp+57h+NewAcl]
0x180053b4a  lea     rcx, [rbp+57h+var_88]
0x180053b4e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180053b53  test    edi, edi
0x180053b55  jns     short loc_180053BB2
0x180053b57  mov     eax, cs:dword_1800DF020
0x180053b5d  cmp     eax, 3
0x180053b60  jbe     loc_180053E26
0x180053b66  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053b6d  mov     [rbp+57h+var_B8], rax
0x180053b71  lea     rdx, byte_1800C5C17
0x180053b78  lea     rax, aSetentriesinac; "SetEntriesInAcl"
0x180053b7f  mov     [rbp+57h+var_C0], rax
0x180053b83  lea     rax, aWarningHresult; "Warning HResult failed"
0x180053b8a  mov     [rbp+57h+var_A8], rax
0x180053b8e  lea     rax, [rbp+57h+var_B8]
0x180053b92  mov     [rsp+110h+phkResult], rax
0x180053b97  lea     rax, [rbp+57h+arg_10]
0x180053b9b  mov     [rsp+110h+lpSecurityAttributes], rax
0x180053ba0  lea     rax, [rbp+57h+var_C0]
0x180053ba4  mov     qword ptr [rsp+110h+samDesired], rax
0x180053ba9  lea     rax, [rbp+57h+var_A8]
0x180053bad  jmp     loc_180053E19
0x180053bb2  mov     edx, 28h ; '('; uBytes
0x180053bb7  lea     ecx, [rdx+18h]; uFlags
0x180053bba  call    cs:__imp_LocalAlloc
0x180053bc1  nop     dword ptr [rax+rax+00h]
0x180053bc6  mov     rdx, rax
0x180053bc9  lea     rcx, [rbp+57h+var_80]
0x180053bcd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180053bd2  mov     rbx, [rbp+57h+var_80]
0x180053bd6  test    rbx, rbx
0x180053bd9  jnz     short loc_180053C40
0x180053bdb  mov     eax, cs:dword_1800DF020
0x180053be1  mov     ecx, 8007000Eh
0x180053be6  mov     edi, ecx
0x180053be8  cmp     eax, 3
0x180053beb  jbe     loc_180053E26
0x180053bf1  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180053bf8  mov     [rbp+57h+arg_10], ecx
0x180053bfb  mov     [rbp+57h+var_A8], rax
0x180053bff  lea     rdx, byte_1800C5BD5
0x180053c06  lea     rax, aLocalalloc; "LocalAlloc"
0x180053c0d  mov     [rbp+57h+var_B8], rax
0x180053c11  lea     rax, aErrorCondition; "Error condition failed"
0x180053c18  mov     [rbp+57h+var_C0], rax
0x180053c1c  lea     rax, [rbp+57h+var_A8]
0x180053c20  mov     [rsp+110h+phkResult], rax
0x180053c25  lea     rax, [rbp+57h+arg_10]
0x180053c29  mov     [rsp+110h+lpSecurityAttributes], rax
  ... truncated ...
```
