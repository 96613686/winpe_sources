# CPolicyMonitor::AllowRCMRegAccess(void)

- ea: `0x1800500dc`
- end: `0x1800507dd`
- name: `?AllowRCMRegAccess@CPolicyMonitor@@AEAAJXZ`
- size: `1793`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180051464`

## callees

- `0x180001b80`
- `0x18004fb80`
- `0x18004fba0`
- `0x18004fbc0`
- `0x180050028`
- `0x1800500dc`
- `0x18005232c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005066f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005066f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005017b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005017b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180050201`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800502b2`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180050201`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800502b2`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800506e8`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800506e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050558`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800504d2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800504d2`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180050443`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x180050443`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180050332`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180050332`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800505e0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800505e0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180050665`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180050665`

## string_xrefs

- `0x1800501a6`: `AllowRCMRegAccess`
- `0x180050253`: `AllowRCMRegAccess`
- `0x1800502d7`: `AllowRCMRegAccess`
- `0x18005035d`: `AllowRCMRegAccess`
- `0x1800503f2`: `AllowRCMRegAccess`
- `0x180050468`: `AllowRCMRegAccess`
- `0x180050504`: `AllowRCMRegAccess`
- `0x180050589`: `AllowRCMRegAccess`
- `0x18005060b`: `AllowRCMRegAccess`
- `0x180050690`: `AllowRCMRegAccess`
- `0x180050711`: `AllowRCMRegAccess`
- `0x18005074c`: `AllowRCMRegAccess`
- `0x1800501b8`: `RegCreateKeyExW`
- `0x1800502e9`: `RegGetKeySecurity`
- `0x18005075e`: `RegGetKeySecurity`
- `0x18005036f`: `GetSecurityDescriptorDacl`
- `0x180050404`: `AllocateAndInitializeServiceSid`
- `0x18005047a`: `GetEffectiveRightsFromAcl`
- `0x180050516`: `SetEntriesInAcl`
- `0x18005061d`: `InitializeSecurityDescriptor`
- `0x1800506a2`: `SetSecurityDescriptorDacl`
- `0x180050723`: `RegSetKeySecurity`

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
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      NewAcl = (PACL)"AllowRCMRegAccess";
      v6 = byte_1800C0C5D;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_65;
      v40 = "AllowRCMRegAccess";
      v6 = byte_1800C0C1B;
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
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v53 = -2147024882;
      v38 = "AllowRCMRegAccess";
      v37 = "LocalAlloc";
      NewAcl = (PACL)"Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)byte_1800C0BD9,
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_23;
      v38 = "AllowRCMRegAccess";
      v17 = byte_1800C0B55;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_23;
      v38 = "AllowRCMRegAccess";
      v17 = byte_1800C0B13;
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v38 = "AllowRCMRegAccess";
        v6 = byte_1800C0AD1;
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v38 = "AllowRCMRegAccess";
        v6 = &byte_1800C0A8F;
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v53 = -2147024882;
        v40 = "AllowRCMRegAccess";
        v38 = "LocalAlloc";
        v37 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147024882,
          (unsigned int)byte_1800C0A4D,
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_23;
      v40 = "AllowRCMRegAccess";
      v17 = byte_1800C0A0B;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_23;
      v40 = "AllowRCMRegAccess";
      v17 = byte_1800C09C9;
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
    if ( KeySecurity >= 0 || (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_65;
    v40 = "AllowRCMRegAccess";
    v6 = &byte_1800C0987;
    v38 = "RegSetKeySecurity";
    v31 = "Warning HResult failed";
LABEL_63:
    v37 = v31;
    phkResult = &v40;
    samDesired = &v38;
    v7 = &v37;
    goto LABEL_64;
  }
  if ( (unsigned int)dword_1800DA020 > 3 )
  {
    v38 = "AllowRCMRegAccess";
    v6 = &byte_1800C0B97;
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
0x1800500dc  mov     qword ptr [rsp-8+cbSecurityDescriptor], rcx
0x1800500e1  push    rbp
0x1800500e2  push    rbx
0x1800500e3  push    rsi
0x1800500e4  push    rdi
0x1800500e5  push    r14
0x1800500e7  lea     rbp, [rsp-37h]
0x1800500ec  sub     rsp, 0F0h
0x1800500f3  xor     esi, esi
0x1800500f5  mov     [rbp+57h+var_68], 1A963466h
0x1800500fc  mov     [rsp+110h+lpdwDisposition], rsi; lpdwDisposition
0x180050101  lea     rax, [rbp+57h+hKey]
0x180050105  mov     [rsp+110h+phkResult], rax; phkResult
0x18005010a  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Control\\Ter"...
0x180050111  xorps   xmm0, xmm0
0x180050114  mov     [rsp+110h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180050119  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x180050121  xor     r9d, r9d; lpClass
0x180050124  xor     r8d, r8d; Reserved
0x180050127  mov     [rsp+110h+dwOptions], esi; dwOptions
0x18005012b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050132  mov     [rbp+57h+var_64], 5CF1AAB9h
0x180050139  mov     [rbp+57h+var_60], 0F8123019h
0x180050140  mov     [rbp+57h+var_5C], 7448CE95h
0x180050147  mov     [rbp+57h+var_58], 304EFDA0h
0x18005014e  mov     [rbp+57h+var_70], rsi
0x180050152  mov     [rbp+57h+pSecurityDescriptor], rsi
0x180050156  mov     [rbp+57h+var_80], rsi
0x18005015a  mov     [rbp+57h+var_88], rsi
0x18005015e  mov     [rbp+57h+pDacl], rsi
0x180050162  mov     [rbp+57h+cbSecurityDescriptor], esi
0x180050165  mov     [rbp+57h+bDaclPresent], esi
0x180050168  mov     [rbp+57h+bDaclDefaulted], esi
0x18005016b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18005016f  mov     [rbp+57h+hKey], rsi
0x180050173  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180050177  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18005017b  call    cs:__imp_RegCreateKeyExW
0x180050181  mov     edi, eax
0x180050183  mov     r14d, 80070000h
0x180050189  test    eax, eax
0x18005018b  jle     short loc_180050193
0x18005018d  movzx   edi, ax
0x180050190  or      edi, r14d
0x180050193  test    edi, edi
0x180050195  jns     short loc_1800501F2
0x180050197  mov     eax, cs:dword_1800DA020
0x18005019d  cmp     eax, 3
0x1800501a0  jbe     loc_1800507A0
0x1800501a6  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x1800501ad  mov     [rbp+57h+NewAcl], rax
0x1800501b1  lea     rdx, byte_1800C0C5D
0x1800501b8  lea     rax, aRegcreatekeyex; "RegCreateKeyExW"
0x1800501bf  mov     [rbp+57h+var_C0], rax
0x1800501c3  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800501ca  mov     [rbp+57h+var_B8], rax
0x1800501ce  lea     rax, [rbp+57h+NewAcl]
0x1800501d2  mov     [rsp+110h+phkResult], rax
0x1800501d7  lea     rax, [rbp+57h+arg_10]
0x1800501db  mov     [rsp+110h+lpSecurityAttributes], rax
0x1800501e0  lea     rax, [rbp+57h+var_C0]
0x1800501e4  mov     qword ptr [rsp+110h+samDesired], rax
0x1800501e9  lea     rax, [rbp+57h+var_B8]
0x1800501ed  jmp     loc_180050793
0x1800501f2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800501f6  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800501fa  xor     r8d, r8d; pSecurityDescriptor
0x1800501fd  lea     edx, [r8+4]; SecurityInformation
0x180050201  call    cs:__imp_RegGetKeySecurity
0x180050207  mov     edi, eax
0x180050209  cmp     eax, 7Ah ; 'z'
0x18005020c  jnz     loc_180050737
0x180050212  mov     eax, [rbp+57h+cbSecurityDescriptor]
0x180050215  test    eax, eax
0x180050217  jz      loc_18005073B
0x18005021d  mov     edx, eax; uBytes
0x18005021f  lea     ecx, [rdi-3Ah]; uFlags
0x180050222  call    cs:__imp_LocalAlloc
0x180050228  mov     rdx, rax
0x18005022b  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18005022f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180050234  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180050238  test    rbx, rbx
0x18005023b  jnz     short loc_1800502A2
0x18005023d  mov     eax, cs:dword_1800DA020
0x180050243  mov     ecx, 8007000Eh
0x180050248  mov     edi, ecx
0x18005024a  cmp     eax, 3
0x18005024d  jbe     loc_1800507A0
0x180050253  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x18005025a  mov     [rbp+57h+arg_10], ecx
0x18005025d  mov     [rbp+57h+var_B8], rax
0x180050261  lea     rdx, byte_1800C0BD9
0x180050268  lea     rax, aLocalalloc; "LocalAlloc"
0x18005026f  mov     [rbp+57h+var_C0], rax
0x180050273  lea     rax, aErrorCondition; "Error condition failed"
0x18005027a  mov     [rbp+57h+NewAcl], rax
0x18005027e  lea     rax, [rbp+57h+var_B8]
0x180050282  mov     [rsp+110h+phkResult], rax
0x180050287  lea     rax, [rbp+57h+arg_10]
0x18005028b  mov     [rsp+110h+lpSecurityAttributes], rax
0x180050290  lea     rax, [rbp+57h+var_C0]
0x180050294  mov     qword ptr [rsp+110h+samDesired], rax
0x180050299  lea     rax, [rbp+57h+NewAcl]
0x18005029d  jmp     loc_180050796
0x1800502a2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800502a6  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800502aa  mov     r8, rbx; pSecurityDescriptor
0x1800502ad  mov     edx, 4; SecurityInformation
0x1800502b2  call    cs:__imp_RegGetKeySecurity
0x1800502b8  mov     edi, eax
0x1800502ba  test    eax, eax
0x1800502bc  jle     short loc_1800502C4
0x1800502be  movzx   edi, ax
0x1800502c1  or      edi, r14d
0x1800502c4  test    edi, edi
0x1800502c6  jns     short loc_180050323
0x1800502c8  mov     eax, cs:dword_1800DA020
0x1800502ce  cmp     eax, 3
0x1800502d1  jbe     loc_1800507A0
0x1800502d7  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x1800502de  mov     [rbp+57h+var_B8], rax
0x1800502e2  lea     rdx, byte_1800C0B97
0x1800502e9  lea     rax, aReggetkeysecur; "RegGetKeySecurity"
0x1800502f0  mov     [rbp+57h+var_C0], rax
0x1800502f4  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800502fb  mov     [rbp+57h+NewAcl], rax
0x1800502ff  lea     rax, [rbp+57h+var_B8]
0x180050303  mov     [rsp+110h+phkResult], rax
0x180050308  lea     rax, [rbp+57h+arg_10]
0x18005030c  mov     [rsp+110h+lpSecurityAttributes], rax
0x180050311  lea     rax, [rbp+57h+var_C0]
0x180050315  mov     qword ptr [rsp+110h+samDesired], rax
0x18005031a  lea     rax, [rbp+57h+NewAcl]
0x18005031e  jmp     loc_180050793
0x180050323  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180050327  mov     rcx, rbx; pSecurityDescriptor
0x18005032a  lea     r8, [rbp+57h+pDacl]; pDacl
0x18005032e  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180050332  call    cs:__imp_GetSecurityDescriptorDacl
0x180050338  test    eax, eax
0x18005033a  jnz     loc_1800503C3
0x180050340  call    cs:__imp_GetLastError
0x180050346  mov     edi, eax
0x180050348  test    eax, eax
0x18005034a  jle     short loc_180050352
0x18005034c  movzx   edi, ax
0x18005034f  or      edi, r14d
0x180050352  mov     eax, cs:dword_1800DA020
0x180050358  cmp     eax, 3
0x18005035b  jbe     short loc_1800503B1
0x18005035d  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180050364  mov     [rbp+57h+var_B8], rax
0x180050368  lea     rdx, byte_1800C0B55
0x18005036f  lea     rax, aGetsecuritydes_3; "GetSecurityDescriptorDacl"
0x180050376  mov     [rbp+57h+var_C0], rax
0x18005037a  lea     rax, aErrorCondition; "Error condition failed"
0x180050381  mov     [rbp+57h+NewAcl], rax
0x180050385  lea     rax, [rbp+57h+var_B8]
0x180050389  mov     [rsp+110h+phkResult], rax
0x18005038e  lea     rax, [rbp+57h+arg_10]
0x180050392  mov     [rsp+110h+lpSecurityAttributes], rax
0x180050397  lea     rax, [rbp+57h+var_C0]
0x18005039b  mov     qword ptr [rsp+110h+samDesired], rax
0x1800503a0  lea     rax, [rbp+57h+NewAcl]
0x1800503a4  mov     qword ptr [rsp+110h+dwOptions], rax
0x1800503a9  mov     [rbp+57h+arg_10], edi
0x1800503ac  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800503b1  test    edi, edi
0x1800503b3  js      loc_1800507A0
0x1800503b9  mov     edi, 80004005h
0x1800503be  jmp     loc_1800507A0
0x1800503c3  lea     rcx, [rbp+57h+var_68]; unsigned int *
0x1800503c7  call    ?AllocateAndInitializeServiceSid@@YAPEAXQEAK@Z; AllocateAndInitializeServiceSid(ulong * const)
0x1800503cc  mov     [rbp+57h+var_70], rax
0x1800503d0  test    rax, rax
0x1800503d3  jnz     short loc_180050410
0x1800503d5  call    cs:__imp_GetLastError
0x1800503db  mov     edi, eax
0x1800503dd  test    eax, eax
0x1800503df  jle     short loc_1800503E7
0x1800503e1  movzx   edi, ax
0x1800503e4  or      edi, r14d
0x1800503e7  mov     eax, cs:dword_1800DA020
0x1800503ed  cmp     eax, 3
0x1800503f0  jbe     short loc_1800503B1
0x1800503f2  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x1800503f9  mov     [rbp+57h+var_B8], rax
0x1800503fd  lea     rdx, byte_1800C0B13
0x180050404  lea     rax, aAllocateandini_0; "AllocateAndInitializeServiceSid"
0x18005040b  jmp     loc_180050376
0x180050410  mov     rcx, [rbp+57h+pDacl]; pacl
0x180050414  lea     r8, [rbp+57h+pAccessRights]; pAccessRights
0x180050418  mov     ebx, 20006h
0x18005041d  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180050424  lea     rdx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x180050428  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], ebx
0x18005042b  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x180050432  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180050435  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18005043c  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180050440  mov     [rbp+57h+pAccessRights], esi
0x180050443  call    cs:__imp_GetEffectiveRightsFromAclW
0x180050449  mov     edi, eax
0x18005044b  test    eax, eax
0x18005044d  jle     short loc_180050455
0x18005044f  movzx   edi, ax
0x180050452  or      edi, r14d
0x180050455  test    edi, edi
0x180050457  jns     short loc_1800504B4
0x180050459  mov     eax, cs:dword_1800DA020
0x18005045f  cmp     eax, 3
0x180050462  jbe     loc_1800507A0
0x180050468  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x18005046f  mov     [rbp+57h+var_B8], rax
0x180050473  lea     rdx, byte_1800C0AD1
0x18005047a  lea     rax, aGeteffectiveri; "GetEffectiveRightsFromAcl"
0x180050481  mov     [rbp+57h+var_C0], rax
0x180050485  lea     rax, aWarningHresult; "Warning HResult failed"
0x18005048c  mov     [rbp+57h+NewAcl], rax
0x180050490  lea     rax, [rbp+57h+var_B8]
0x180050494  mov     [rsp+110h+phkResult], rax
0x180050499  lea     rax, [rbp+57h+arg_10]
0x18005049d  mov     [rsp+110h+lpSecurityAttributes], rax
0x1800504a2  lea     rax, [rbp+57h+var_C0]
0x1800504a6  mov     qword ptr [rsp+110h+samDesired], rax
0x1800504ab  lea     rax, [rbp+57h+NewAcl]
0x1800504af  jmp     loc_180050793
0x1800504b4  test    [rbp+57h+pAccessRights], ebx
0x1800504b7  jnz     loc_1800507A0
0x1800504bd  mov     r8, [rbp+57h+pDacl]; OldAcl
0x1800504c1  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800504c5  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800504c9  mov     [rbp+57h+NewAcl], rsi
0x1800504cd  mov     ecx, 1; cCountOfExplicitEntries
0x1800504d2  call    cs:__imp_SetEntriesInAclW
0x1800504d8  mov     edi, eax
0x1800504da  test    eax, eax
0x1800504dc  jle     short loc_1800504E4
0x1800504de  movzx   edi, ax
0x1800504e1  or      edi, r14d
0x1800504e4  mov     rdx, [rbp+57h+NewAcl]
0x1800504e8  lea     rcx, [rbp+57h+var_88]
0x1800504ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800504f1  test    edi, edi
0x1800504f3  jns     short loc_180050550
0x1800504f5  mov     eax, cs:dword_1800DA020
0x1800504fb  cmp     eax, 3
0x1800504fe  jbe     loc_1800507A0
0x180050504  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x18005050b  mov     [rbp+57h+var_B8], rax
0x18005050f  lea     rdx, byte_1800C0A8F
0x180050516  lea     rax, aSetentriesinac; "SetEntriesInAcl"
0x18005051d  mov     [rbp+57h+var_C0], rax
0x180050521  lea     rax, aWarningHresult; "Warning HResult failed"
0x180050528  mov     [rbp+57h+var_A8], rax
0x18005052c  lea     rax, [rbp+57h+var_B8]
0x180050530  mov     [rsp+110h+phkResult], rax
0x180050535  lea     rax, [rbp+57h+arg_10]
0x180050539  mov     [rsp+110h+lpSecurityAttributes], rax
0x18005053e  lea     rax, [rbp+57h+var_C0]
0x180050542  mov     qword ptr [rsp+110h+samDesired], rax
0x180050547  lea     rax, [rbp+57h+var_A8]
0x18005054b  jmp     loc_180050793
0x180050550  mov     edx, 28h ; '('; uBytes
0x180050555  lea     ecx, [rdx+18h]; uFlags
0x180050558  call    cs:__imp_LocalAlloc
0x18005055e  mov     rdx, rax
0x180050561  lea     rcx, [rbp+57h+var_80]
0x180050565  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005056a  mov     rbx, [rbp+57h+var_80]
0x18005056e  test    rbx, rbx
0x180050571  jnz     short loc_1800505D8
0x180050573  mov     eax, cs:dword_1800DA020
0x180050579  mov     ecx, 8007000Eh
0x18005057e  mov     edi, ecx
0x180050580  cmp     eax, 3
0x180050583  jbe     loc_1800507A0
0x180050589  lea     rax, aAllowrcmregacc; "AllowRCMRegAccess"
0x180050590  mov     [rbp+57h+arg_10], ecx
0x180050593  mov     [rbp+57h+var_A8], rax
0x180050597  lea     rdx, byte_1800C0A4D
0x18005059e  lea     rax, aLocalalloc; "LocalAlloc"
0x1800505a5  mov     [rbp+57h+var_B8], rax
0x1800505a9  lea     rax, aErrorCondition; "Error condition failed"
0x1800505b0  mov     [rbp+57h+var_C0], rax
0x1800505b4  lea     rax, [rbp+57h+var_A8]
0x1800505b8  mov     [rsp+110h+phkResult], rax
0x1800505bd  lea     rax, [rbp+57h+arg_10]
0x1800505c1  mov     [rsp+110h+lpSecurityAttributes], rax
0x1800505c6  lea     rax, [rbp+57h+var_B8]
0x1800505ca  mov     qword ptr [rsp+110h+samDesired], rax
0x1800505cf  lea     rax, [rbp+57h+var_C0]
0x1800505d3  jmp     loc_180050796
0x1800505d8  mov     edx, 1; dwRevision
0x1800505dd  mov     rcx, rbx; pSecurityDescriptor
0x1800505e0  call    cs:__imp_InitializeSecurityDescriptor
0x1800505e6  test    eax, eax
0x1800505e8  jnz     short loc_180050657
0x1800505ea  call    cs:__imp_GetLastError
  ... truncated ...
```
