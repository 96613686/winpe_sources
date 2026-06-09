# Win32_DCOMApplicationSetting::ExecGetSecurityDescriptor(CInstance const &,ushort * const,CInstance *,CInstance *,long)

- ea: `0x18007f9c8`
- end: `0x1800802a4`
- name: `?ExecGetSecurityDescriptor@Win32_DCOMApplicationSetting@@IEAAJAEBVCInstance@@QEAGPEAV2@2J@Z`
- size: `2268`
- prototype: `int(Win32_DCOMApplicationSetting *__hidden this, const struct CInstance *, unsigned __int16 *const, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800dc1d0`

## callees

- `0x180013ae0`
- `0x180015c80`
- `0x180032fd8`
- `0x180035e70`
- `0x18003d7b0`
- `0x180063df8`
- `0x180067674`
- `0x18007f074`
- `0x18007f4bc`
- `0x18007f500`
- `0x18007f9c8`
- `0x1800802ac`
- `0x1800896cc`
- `0x180089784`
- `0x18009bb18`
- `0x1800dbea0`
- `0x1800f353c`
- `0x1800f3570`
- `0x1800f85b4`
- `0x1800f8998`
- `0x1800f9700`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18007fb28`
- `msvcrt!_wcsicmp` at `0x18007fbe4`
- `msvcrt!_wcsicmp` at `0x18007fc41`
- `msvcrt!_wcsicmp` at `0x18007fb28`
- `msvcrt!_wcsicmp` at `0x18007fbe4`
- `msvcrt!_wcsicmp` at `0x18007fc41`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18007fc6d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18007fcd0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18007fc6d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18007fcd0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007fdc0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007ff11`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007fdc0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007ff11`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18007fb99`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18007fb99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007fa51`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18007fe7e`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18007ffd9`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080090`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18007fe7e`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18007ffd9`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080090`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007fd1f`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007fe12`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007ff63`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007fd1f`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007fe12`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x18007ff63`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18007fa0b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18007fa0b`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18007fa80`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18007fa80`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007faeb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007fcec`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007fddf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007ff30`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007faeb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007fcec`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007fddf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18007ff30`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fa9a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fca6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fd36`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fd83`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fe29`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fe98`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007ff7a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fff3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800800aa`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800800d6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008019d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800801c5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fa9a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fca6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fd36`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fd83`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fe29`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fe98`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007ff7a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18007fff3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800800aa`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800800d6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008019d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800801c5`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007fd07`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007fdfa`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007ff4b`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007fd07`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007fdfa`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18007ff4b`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007fce3`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007fdd6`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007ff27`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007fce3`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007fdd6`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x18007ff27`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18007fa19`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18007fa27`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18007fa19`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18007fa27`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180080166`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180080174`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008021f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008022d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008025e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008026c`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180080166`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180080174`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008021f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008022d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008025e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008026c`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007facd`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007fb14`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007facd`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007fb14`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fafb`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fc56`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fcbd`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fafb`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fc56`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18007fcbd`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fb4c`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fb83`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fc04`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fb4c`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fb83`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18007fc04`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080180`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080239`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080278`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080180`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080239`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080278`
- `api-ms-win-core-com-private-l1-1-0!CoGetSystemSecurityPermissions` at `0x18007fbbe`
- `api-ms-win-core-com-private-l1-1-0!CoGetSystemSecurityPermissions` at `0x18007fbbe`

## string_xrefs

- `0x18007fd15`: `Win32_SecurityDescriptor`
- `0x180080086`: `Descriptor`
- `0x18007fbf6`: `AccessPermission`
- `0x18007fc21`: `AccessPermission`
- `0x18007fb1e`: `GetLaunchSecurityDescriptor`
- `0x18007fbda`: `GetAccessSecurityDescriptor`
- `0x18007fc37`: `GetConfigurationSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Win32_DCOMApplicationSetting::ExecGetSecurityDescriptor(
        Win32_DCOMApplicationSetting *this,
        const struct CInstance *a2,
        unsigned __int16 *const a3,
        struct CInstance *a4,
        struct CInstance *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  int CurrentBinaryKeyValue; // eax
  bool v12; // cc
  const unsigned __int16 *v13; // rbx
  HKEY v14; // rax
  void *v15; // rax
  const unsigned __int16 *v16; // rdx
  PSECURITY_DESCRIPTOR v17; // rsi
  COMSD v18; // ecx
  HKEY v19; // rax
  void *v20; // rbx
  HKEY v21; // rax
  const struct CHString *Namespace; // rax
  const unsigned __int16 *v23; // rbx
  struct MethodContext *MethodContext; // rax
  signed int EmptyInstance; // eax
  CInstance *v26; // rax
  const struct CHString *v27; // rax
  const unsigned __int16 *v28; // rbx
  struct MethodContext *v29; // rax
  signed int v30; // eax
  CInstance *v31; // rbx
  struct CInstance *v32; // rax
  const struct CHString *v33; // rax
  const unsigned __int16 *v34; // rbx
  struct MethodContext *v35; // rax
  signed int v36; // eax
  CInstance *v37; // rbx
  struct CInstance *v38; // rax
  struct CInstance *v39; // rax
  bool v40; // al
  DWORD cbSecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  struct CInstance *v43; // [rsp+28h] [rbp-D8h] BYREF
  struct CInstance *v44; // [rsp+30h] [rbp-D0h] BYREF
  struct CInstance *v45; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+48h] [rbp-B8h]
  PSECURITY_DESCRIPTOR ppSD; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v49[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v51[6]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v52; // [rsp+A0h] [rbp-60h]
  PSID pSid; // [rsp+A8h] [rbp-58h] BYREF
  int v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  __int64 v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+D0h] [rbp-30h]
  PSID v59; // [rsp+D8h] [rbp-28h] BYREF
  int v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  int v64; // [rsp+100h] [rbp+0h]
  _BYTE v65[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v66[24]; // [rsp+128h] [rbp+28h] BYREF
  void **v67; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v68[88]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v69[608]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v70[608]; // [rsp+400h] [rbp+300h] BYREF

  CHString::CHString((CHString *)v49);
  CRegistry::CRegistry((CRegistry *)v70);
  CRegistry::CRegistry((CRegistry *)v69);
  pSecurityDescriptor = 0;
  MakeGuard<void (*)(unsigned char *),RefHolder<unsigned char *>>(v66, v8, &pSecurityDescriptor);
  cbSecurityDescriptor = 0;
  ppSD = 0;
  MakeGuard<void * (*)(void *),RefHolder<void *>>(v65, LocalFree, &ppSD);
  if ( !a5 )
  {
    v9 = -2147217400;
LABEL_64:
    ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v65);
    ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v66);
    CRegistry::~CRegistry((CRegistry *)v69);
    CRegistry::~CRegistry((CRegistry *)v70);
    CHString::~CHString((CHString *)v49);
    return v9;
  }
  if ( !CInstance::GetCHString(a2, L"AppID", (struct CHString *)v49) )
  {
    v10 = -2147217393;
LABEL_5:
    v9 = !CInstance::SetDWORD(a5, L"ReturnValue", v10) ? 0x80041004 : 0;
    goto LABEL_64;
  }
  CurrentBinaryKeyValue = CRegistry::Open((CRegistry *)v70, HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0x20019u);
  v12 = CurrentBinaryKeyValue <= 0;
  if ( CurrentBinaryKeyValue )
    goto LABEL_7;
  v13 = (const unsigned __int16 *)CHString::operator unsigned short const *(v49);
  v14 = CRegistry::GethKey((CRegistry *)v70);
  CurrentBinaryKeyValue = CRegistry::Open((CRegistry *)v69, v14, v13, 0x1020019u);
  v12 = CurrentBinaryKeyValue <= 0;
  if ( CurrentBinaryKeyValue )
    goto LABEL_7;
  if ( !_wcsicmp(a3, L"GetLaunchSecurityDescriptor") )
  {
    CurrentBinaryKeyValue = CRegistry::GetCurrentBinaryKeyValue(
                              (CRegistry *)v69,
                              L"LaunchPermission",
                              0,
                              &cbSecurityDescriptor);
    if ( !CurrentBinaryKeyValue )
    {
      v15 = operator new(cbSecurityDescriptor);
      pSecurityDescriptor = v15;
      if ( v15 )
      {
        v16 = L"LaunchPermission";
LABEL_15:
        CurrentBinaryKeyValue = CRegistry::GetCurrentBinaryKeyValue(
                                  (CRegistry *)v69,
                                  v16,
                                  (unsigned __int8 *)v15,
                                  &cbSecurityDescriptor);
        goto LABEL_16;
      }
      goto LABEL_35;
    }
    if ( CurrentBinaryKeyValue == 2 )
    {
      v18 = SD_LAUNCHPERMISSIONS;
      goto LABEL_22;
    }
    goto LABEL_24;
  }
  if ( !_wcsicmp(a3, L"GetAccessSecurityDescriptor") )
  {
    CurrentBinaryKeyValue = CRegistry::GetCurrentBinaryKeyValue(
                              (CRegistry *)v69,
                              L"AccessPermission",
                              0,
                              &cbSecurityDescriptor);
    if ( !CurrentBinaryKeyValue )
    {
      v15 = operator new(cbSecurityDescriptor);
      pSecurityDescriptor = v15;
      if ( v15 )
      {
        v16 = L"AccessPermission";
        goto LABEL_15;
      }
LABEL_35:
      CInstance::SetDWORD(a5, L"ReturnValue", 0x80041006);
      v9 = -2147217402;
      goto LABEL_64;
    }
    if ( CurrentBinaryKeyValue == 2 )
    {
      v18 = SD_ACCESSRESTRICTIONS;
LABEL_22:
      CurrentBinaryKeyValue = CoGetSystemSecurityPermissions(v18, &ppSD);
      if ( CurrentBinaryKeyValue >= 0 )
      {
        v17 = ppSD;
LABEL_18:
        if ( !IsValidSecurityDescriptor(v17) )
        {
          v10 = -2147023558;
          goto LABEL_5;
        }
        v43 = 0;
        Namespace = Provider::GetNamespace(this);
        v23 = (const unsigned __int16 *)CHString::operator unsigned short const *(Namespace);
        _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v43);
        v43 = 0;
        MethodContext = CInstance::GetMethodContext(a2);
        EmptyInstance = CWbemProviderGlue::GetEmptyInstance(MethodContext, L"Win32_SecurityDescriptor", &v43, v23);
        if ( EmptyInstance < 0 )
        {
          v9 = !CInstance::SetDWORD(a5, L"ReturnValue", EmptyInstance) ? 0x80041004 : 0;
LABEL_63:
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v43);
          goto LABEL_64;
        }
        CSecurityDescriptor::CSecurityDescriptor((CSecurityDescriptor *)v51, v17);
        v47 = v52;
        v26 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v43);
        CInstance::SetDWORD(v26, L"ControlFlags", v47);
        pSid = 0;
        v54 = 8;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        CSecurityDescriptor::GetOwner((CSecurityDescriptor *)v51, (struct CSid *)&pSid);
        if ( !pSid || !IsValidSid(pSid) )
        {
          v9 = !CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004) ? 0x80041004 : 0;
          goto LABEL_62;
        }
        v44 = 0;
        v27 = Provider::GetNamespace(this);
        v28 = (const unsigned __int16 *)CHString::operator unsigned short const *(v27);
        _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v44);
        v44 = 0;
        v29 = CInstance::GetMethodContext(a2);
        v30 = CWbemProviderGlue::GetEmptyInstance(v29, L"Win32_Trustee", &v44, v28);
        if ( v30 < 0 )
        {
          v9 = !CInstance::SetDWORD(a5, L"ReturnValue", v30) ? 0x80041004 : 0;
LABEL_43:
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v44);
LABEL_62:
          CSid::~CSid(&pSid);
          v51[0] = &CSecurityDescriptor::`vftable';
          CSecurityDescriptor::Clear((CSecurityDescriptor *)v51);
          goto LABEL_63;
        }
        FillTrusteeFromSid(v44, (struct CSid *)&pSid);
        v31 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v43);
        v32 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v44);
        if ( !CInstance::SetEmbeddedObject(v31, L"Owner", v32) )
        {
          CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004);
LABEL_46:
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v44);
          CSid::~CSid(&pSid);
          v51[0] = &CSecurityDescriptor::`vftable';
          CSecurityDescriptor::Clear((CSecurityDescriptor *)v51);
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v43);
          v9 = -2147217404;
          goto LABEL_64;
        }
        v59 = 0;
        v60 = 8;
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        CSecurityDescriptor::GetGroup((CSecurityDescriptor *)v51, (struct CSid *)&v59);
        if ( v59 && IsValidSid(v59) )
        {
          v45 = 0;
          v33 = Provider::GetNamespace(this);
          v34 = (const unsigned __int16 *)CHString::operator unsigned short const *(v33);
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v45);
          v45 = 0;
          v35 = CInstance::GetMethodContext(a2);
          v36 = CWbemProviderGlue::GetEmptyInstance(v35, L"Win32_Trustee", &v45, v34);
          if ( v36 >= 0 )
          {
            FillTrusteeFromSid(v45, (struct CSid *)&v59);
            v37 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v43);
            v38 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v45);
            if ( CInstance::SetEmbeddedObject(v37, L"Group", v38) )
            {
              v67 = &CDACL::`vftable';
              memset_0(v68, 0, 0x50u);
              CSecurityDescriptor::GetDACL((CSecurityDescriptor *)v51, (struct CDACL *)&v67);
              FillInstanceDACL(v43, (struct CDACL *)&v67);
              v50[0] = &CSACL::`vftable';
              v50[1] = 0;
              CSecurityDescriptor::GetSACL((CSecurityDescriptor *)v51, (struct CSACL *)v50);
              FillInstanceSACL(v43, (struct CSACL *)v50);
              v39 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v43);
              if ( CInstance::SetEmbeddedObject(a5, L"Descriptor", v39) )
              {
                v40 = CInstance::SetDWORD(a5, L"ReturnValue", 0);
                v50[0] = &CSACL::`vftable';
                if ( v40 )
                {
                  CSACL::Clear((CSACL *)v50);
                  v67 = &CDACL::`vftable';
                  CDACL::Clear((CDACL *)&v67);
                  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v45);
                  CSid::~CSid(&v59);
                  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v44);
                  CSid::~CSid(&pSid);
                  v51[0] = &CSecurityDescriptor::`vftable';
                  CSecurityDescriptor::Clear((CSecurityDescriptor *)v51);
                  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v43);
                  ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v65);
                  ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v66);
                  CRegistry::~CRegistry((CRegistry *)v69);
                  CRegistry::~CRegistry((CRegistry *)v70);
                  CHString::~CHString((CHString *)v49);
                  return 0;
                }
              }
              else
              {
                CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004);
                v50[0] = &CSACL::`vftable';
              }
              CSACL::Clear((CSACL *)v50);
              v67 = &CDACL::`vftable';
              CDACL::Clear((CDACL *)&v67);
            }
            else
            {
              CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004);
            }
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v45);
            CSid::~CSid(&v59);
            goto LABEL_46;
          }
          v9 = !CInstance::SetDWORD(a5, L"ReturnValue", v36) ? 0x80041004 : 0;
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v45);
        }
        else
        {
          v9 = !CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004) ? 0x80041004 : 0;
        }
        CSid::~CSid(&v59);
        goto LABEL_43;
      }
LABEL_9:
      v10 = CurrentBinaryKeyValue;
      goto LABEL_5;
    }
    goto LABEL_24;
  }
  if ( !_wcsicmp(a3, L"GetConfigurationSecurityDescriptor") )
  {
    v19 = CRegistry::GethKey((CRegistry *)v69);
    CurrentBinaryKeyValue = RegGetKeySecurity(v19, 0xFu, 0, &cbSecurityDescriptor);
    if ( !CurrentBinaryKeyValue || CurrentBinaryKeyValue == 122 )
    {
      v20 = operator new(cbSecurityDescriptor);
      pSecurityDescriptor = v20;
      if ( v20 )
      {
        v21 = CRegistry::GethKey((CRegistry *)v69);
        CurrentBinaryKeyValue = RegGetKeySecurity(v21, 0xFu, v20, &cbSecurityDescriptor);
LABEL_16:
        v12 = CurrentBinaryKeyValue <= 0;
        if ( !CurrentBinaryKeyValue )
        {
          v17 = pSecurityDescriptor;
          goto LABEL_18;
        }
        goto LABEL_7;
      }
      goto LABEL_35;
    }
LABEL_24:
    v12 = CurrentBinaryKeyValue <= 0;
LABEL_7:
    if ( !v12 )
      CurrentBinaryKeyValue = (unsigned __int16)CurrentBinaryKeyValue | 0x80070000;
    goto LABEL_9;
  }
  ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v65);
  ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v66);
  CRegistry::~CRegistry((CRegistry *)v69);
  CRegistry::~CRegistry((CRegistry *)v70);
  CHString::~CHString((CHString *)v49);
  return 2147749934LL;
}

```

## disassembly

```asm
0x18007f9c8  push    rbp
0x18007f9ca  push    rbx
0x18007f9cb  push    rsi
0x18007f9cc  push    rdi
0x18007f9cd  push    r12
0x18007f9cf  push    r14
0x18007f9d1  push    r15
0x18007f9d3  lea     rbp, [rsp-570h]
0x18007f9db  sub     rsp, 670h
0x18007f9e2  mov     rax, cs:__security_cookie
0x18007f9e9  xor     rax, rsp
0x18007f9ec  mov     [rbp+5A0h+var_40], rax
0x18007f9f3  mov     rsi, r8
0x18007f9f6  mov     r14, rdx
0x18007f9f9  mov     r15, rcx
0x18007f9fc  mov     rdi, [rbp+5A0h+arg_20]
0x18007fa03  xor     r12d, r12d
0x18007fa06  lea     rcx, [rsp+6A0h+var_648]
0x18007fa0b  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18007fa11  nop
0x18007fa12  lea     rcx, [rbp+5A0h+var_2A0]
0x18007fa19  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18007fa1f  nop
0x18007fa20  lea     rcx, [rbp+5A0h+var_500]
0x18007fa27  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18007fa2d  nop
0x18007fa2e  mov     [rsp+6A0h+pSecurityDescriptor], r12
0x18007fa33  lea     r8, [rsp+6A0h+pSecurityDescriptor]
0x18007fa38  lea     rcx, [rbp+5A0h+var_578]
0x18007fa3c  call    ??$MakeGuard@P6AXPEAE@ZV?$RefHolder@PEAE@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@P6AXPEAE@ZV?$RefHolder@PEAE@@@Z; MakeGuard<void (*)(uchar *),RefHolder<uchar *>>(void (*)(uchar *),RefHolder<uchar *>)
0x18007fa41  nop
0x18007fa42  mov     [rsp+6A0h+cbSecurityDescriptor], r12d
0x18007fa47  mov     [rsp+6A0h+ppSD], r12
0x18007fa4c  lea     r8, [rsp+6A0h+ppSD]
0x18007fa51  mov     rdx, cs:__imp_LocalFree
0x18007fa58  lea     rcx, [rbp+5A0h+var_590]
0x18007fa5c  call    ??$MakeGuard@P6APEAXPEAX@ZV?$RefHolder@PEAX@@@@YA?AV?$ScopeGuardImpl1@P6APEAXPEAX@ZV?$RefHolder@PEAX@@@@P6APEAXPEAX@ZV?$RefHolder@PEAX@@@Z; MakeGuard<void * (*)(void *),RefHolder<void *>>(void * (*)(void *),RefHolder<void *>)
0x18007fa61  nop
0x18007fa62  test    rdi, rdi
0x18007fa65  jnz     short loc_18007FA71
0x18007fa67  mov     ebx, 80041008h
0x18007fa6c  jmp     loc_180080204
0x18007fa71  lea     r8, [rsp+6A0h+var_648]
0x18007fa76  lea     rdx, aAppid; "AppID"
0x18007fa7d  mov     rcx, r14
0x18007fa80  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x18007fa86  test    al, al
0x18007fa88  jnz     short loc_18007FAB2
0x18007fa8a  mov     r8d, 8004100Fh
0x18007fa90  lea     rdx, aReturnvalue; "ReturnValue"
0x18007fa97  mov     rcx, rdi
0x18007fa9a  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007faa0  nop
0x18007faa1  neg     al
0x18007faa3  sbb     ebx, ebx
0x18007faa5  not     ebx
0x18007faa7  and     ebx, 80041004h
0x18007faad  jmp     loc_180080204
0x18007fab2  mov     r9d, 20019h
0x18007fab8  lea     r8, aSoftwareClasse_2; "Software\\Classes\\AppID"
0x18007fabf  mov     rdx, 0FFFFFFFF80000002h
0x18007fac6  lea     rcx, [rbp+5A0h+var_2A0]
0x18007facd  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18007fad3  test    eax, eax
0x18007fad5  jz      short loc_18007FAE6
0x18007fad7  jle     short loc_18007FAE1
0x18007fad9  movzx   eax, ax
0x18007fadc  or      eax, 80070000h
0x18007fae1  mov     r8d, eax
0x18007fae4  jmp     short loc_18007FA90
0x18007fae6  lea     rcx, [rsp+6A0h+var_648]
0x18007faeb  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18007faf1  mov     rbx, rax
0x18007faf4  lea     rcx, [rbp+5A0h+var_2A0]
0x18007fafb  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x18007fb01  mov     r9d, 1020019h
0x18007fb07  mov     r8, rbx
0x18007fb0a  mov     rdx, rax
0x18007fb0d  lea     rcx, [rbp+5A0h+var_500]
0x18007fb14  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18007fb1a  test    eax, eax
0x18007fb1c  jnz     short loc_18007FAD7
0x18007fb1e  lea     rdx, aGetlaunchsecur; "GetLaunchSecurityDescriptor"
0x18007fb25  mov     rcx, rsi; String1
0x18007fb28  call    cs:__imp__wcsicmp
0x18007fb2e  test    eax, eax
0x18007fb30  jnz     loc_18007FBDA
0x18007fb36  lea     r9, [rsp+6A0h+cbSecurityDescriptor]
0x18007fb3b  xor     r8d, r8d
0x18007fb3e  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x18007fb45  lea     rcx, [rbp+5A0h+var_500]
0x18007fb4c  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18007fb52  test    eax, eax
0x18007fb54  jnz     short loc_18007FBB2
0x18007fb56  mov     ecx, [rsp+6A0h+cbSecurityDescriptor]; unsigned __int64
0x18007fb5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007fb5f  mov     [rsp+6A0h+pSecurityDescriptor], rax
0x18007fb64  test    rax, rax
0x18007fb67  jz      loc_18007FC96
0x18007fb6d  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x18007fb74  mov     r8, rax
0x18007fb77  lea     r9, [rsp+6A0h+cbSecurityDescriptor]
0x18007fb7c  lea     rcx, [rbp+5A0h+var_500]
0x18007fb83  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18007fb89  test    eax, eax
0x18007fb8b  jnz     loc_18007FAD7
0x18007fb91  mov     rsi, [rsp+6A0h+pSecurityDescriptor]
0x18007fb96  mov     rcx, rsi; pSecurityDescriptor
0x18007fb99  call    cs:__imp_IsValidSecurityDescriptor
0x18007fb9f  test    eax, eax
0x18007fba1  jnz     loc_18007FCDB
0x18007fba7  mov     r8d, 8007053Ah
0x18007fbad  jmp     loc_18007FA90
0x18007fbb2  cmp     eax, 2
0x18007fbb5  jnz     short loc_18007FBD3
0x18007fbb7  xor     ecx, ecx; comSDType
0x18007fbb9  lea     rdx, [rsp+6A0h+ppSD]; ppSD
0x18007fbbe  call    cs:__imp_CoGetSystemSecurityPermissions
0x18007fbc4  test    eax, eax
0x18007fbc6  js      loc_18007FAE1
0x18007fbcc  mov     rsi, [rsp+6A0h+ppSD]
0x18007fbd1  jmp     short loc_18007FB96
0x18007fbd3  test    eax, eax
0x18007fbd5  jmp     loc_18007FAD7
0x18007fbda  lea     rdx, aGetaccesssecur; "GetAccessSecurityDescriptor"
0x18007fbe1  mov     rcx, rsi; String1
0x18007fbe4  call    cs:__imp__wcsicmp
0x18007fbea  test    eax, eax
0x18007fbec  jnz     short loc_18007FC37
0x18007fbee  lea     r9, [rsp+6A0h+cbSecurityDescriptor]
0x18007fbf3  xor     r8d, r8d
0x18007fbf6  lea     rdx, aAccesspermissi; "AccessPermission"
0x18007fbfd  lea     rcx, [rbp+5A0h+var_500]
0x18007fc04  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18007fc0a  test    eax, eax
0x18007fc0c  jnz     short loc_18007FC2D
0x18007fc0e  mov     ecx, [rsp+6A0h+cbSecurityDescriptor]; unsigned __int64
0x18007fc12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007fc17  mov     [rsp+6A0h+pSecurityDescriptor], rax
0x18007fc1c  test    rax, rax
0x18007fc1f  jz      short loc_18007FC96
0x18007fc21  lea     rdx, aAccesspermissi; "AccessPermission"
0x18007fc28  jmp     loc_18007FB74
0x18007fc2d  cmp     eax, 2
0x18007fc30  jnz     short loc_18007FBD3
0x18007fc32  lea     ecx, [rax+1]
0x18007fc35  jmp     short loc_18007FBB9
0x18007fc37  lea     rdx, aGetconfigurati; "GetConfigurationSecurityDescriptor"
0x18007fc3e  mov     rcx, rsi; String1
0x18007fc41  call    cs:__imp__wcsicmp
0x18007fc47  test    eax, eax
0x18007fc49  jnz     loc_180080243
0x18007fc4f  lea     rcx, [rbp+5A0h+var_500]
0x18007fc56  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x18007fc5c  mov     rcx, rax; hKey
0x18007fc5f  lea     r9, [rsp+6A0h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18007fc64  xor     r8d, r8d; pSecurityDescriptor
0x18007fc67  lea     esi, [r8+0Fh]
0x18007fc6b  mov     edx, esi; SecurityInformation
0x18007fc6d  call    cs:__imp_RegGetKeySecurity
0x18007fc73  test    eax, eax
0x18007fc75  jz      short loc_18007FC80
0x18007fc77  cmp     eax, 7Ah ; 'z'
0x18007fc7a  jnz     loc_18007FBD3
0x18007fc80  mov     ecx, [rsp+6A0h+cbSecurityDescriptor]; unsigned __int64
0x18007fc84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007fc89  mov     rbx, rax
0x18007fc8c  mov     [rsp+6A0h+pSecurityDescriptor], rax
0x18007fc91  test    rax, rax
0x18007fc94  jnz     short loc_18007FCB6
0x18007fc96  mov     r8d, 80041006h
0x18007fc9c  lea     rdx, aReturnvalue; "ReturnValue"
0x18007fca3  mov     rcx, rdi
0x18007fca6  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007fcac  mov     ebx, 80041006h
0x18007fcb1  jmp     loc_180080204
0x18007fcb6  lea     rcx, [rbp+5A0h+var_500]
0x18007fcbd  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x18007fcc3  lea     r9, [rsp+6A0h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18007fcc8  mov     r8, rbx; pSecurityDescriptor
0x18007fccb  mov     edx, esi; SecurityInformation
0x18007fccd  mov     rcx, rax; hKey
0x18007fcd0  call    cs:__imp_RegGetKeySecurity
0x18007fcd6  jmp     loc_18007FB89
0x18007fcdb  mov     [rsp+6A0h+var_678], r12
0x18007fce0  mov     rcx, r15
0x18007fce3  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x18007fce9  mov     rcx, rax
0x18007fcec  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18007fcf2  mov     rbx, rax
0x18007fcf5  lea     rcx, [rsp+6A0h+var_678]
0x18007fcfa  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18007fcff  mov     [rsp+6A0h+var_678], r12
0x18007fd04  mov     rcx, r14
0x18007fd07  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x18007fd0d  mov     r9, rbx
0x18007fd10  lea     r8, [rsp+6A0h+var_678]
0x18007fd15  lea     rdx, aWin32Securityd; "Win32_SecurityDescriptor"
0x18007fd1c  mov     rcx, rax
0x18007fd1f  call    cs:__imp_?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z; CWbemProviderGlue::GetEmptyInstance(MethodContext *,ushort const *,CInstance * *,ushort const *)
0x18007fd25  test    eax, eax
0x18007fd27  jns     short loc_18007FD4E
0x18007fd29  mov     r8d, eax
0x18007fd2c  lea     rdx, aReturnvalue; "ReturnValue"
0x18007fd33  mov     rcx, rdi
0x18007fd36  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007fd3c  nop
0x18007fd3d  neg     al
0x18007fd3f  sbb     ebx, ebx
0x18007fd41  not     ebx
0x18007fd43  and     ebx, 80041004h
0x18007fd49  jmp     loc_1800801F9
0x18007fd4e  mov     rdx, rsi; void *
0x18007fd51  lea     rcx, [rsp+6A0h+var_630]; this
0x18007fd56  call    ??0CSecurityDescriptor@@QEAA@PEAX@Z; CSecurityDescriptor::CSecurityDescriptor(void *)
0x18007fd5b  nop
0x18007fd5c  mov     [rsp+6A0h+var_658], r12d
0x18007fd61  movzx   eax, [rbp+5A0h+var_600]
0x18007fd65  mov     word ptr [rsp+6A0h+var_658], ax
0x18007fd6a  lea     rcx, [rsp+6A0h+var_678]
0x18007fd6f  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18007fd74  mov     r8d, [rsp+6A0h+var_658]
0x18007fd79  lea     rdx, aControlflags; "ControlFlags"
0x18007fd80  mov     rcx, rax
0x18007fd83  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007fd89  mov     [rbp+5A0h+pSid], r12
0x18007fd8d  mov     esi, 8
0x18007fd92  mov     [rbp+5A0h+var_5F0], esi
0x18007fd95  mov     [rbp+5A0h+var_5E8], r12
0x18007fd99  mov     [rbp+5A0h+var_5E0], r12
0x18007fd9d  mov     [rbp+5A0h+var_5D8], r12
0x18007fda1  mov     [rbp+5A0h+var_5D0], r12d
0x18007fda5  lea     rdx, [rbp+5A0h+pSid]; struct CSid *
0x18007fda9  lea     rcx, [rsp+6A0h+var_630]; this
0x18007fdae  call    ?GetOwner@CSecurityDescriptor@@QEAAXAEAVCSid@@@Z; CSecurityDescriptor::GetOwner(CSid &)
0x18007fdb3  mov     rcx, [rbp+5A0h+pSid]; pSid
0x18007fdb7  test    rcx, rcx
0x18007fdba  jz      loc_1800801B5
0x18007fdc0  call    cs:__imp_IsValidSid
0x18007fdc6  test    eax, eax
0x18007fdc8  jz      loc_1800801B5
0x18007fdce  mov     [rsp+6A0h+var_670], r12
0x18007fdd3  mov     rcx, r15
0x18007fdd6  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x18007fddc  mov     rcx, rax
0x18007fddf  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18007fde5  mov     rbx, rax
0x18007fde8  lea     rcx, [rsp+6A0h+var_670]
0x18007fded  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18007fdf2  mov     [rsp+6A0h+var_670], r12
0x18007fdf7  mov     rcx, r14
0x18007fdfa  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x18007fe00  mov     r9, rbx
0x18007fe03  lea     r8, [rsp+6A0h+var_670]
0x18007fe08  lea     rdx, aWin32Trustee; "Win32_Trustee"
0x18007fe0f  mov     rcx, rax
0x18007fe12  call    cs:__imp_?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z; CWbemProviderGlue::GetEmptyInstance(MethodContext *,ushort const *,CInstance * *,ushort const *)
0x18007fe18  test    eax, eax
0x18007fe1a  jns     short loc_18007FE4C
0x18007fe1c  mov     r8d, eax
0x18007fe1f  lea     rdx, aReturnvalue; "ReturnValue"
0x18007fe26  mov     rcx, rdi
0x18007fe29  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007fe2f  nop
0x18007fe30  neg     al
0x18007fe32  sbb     ebx, ebx
0x18007fe34  not     ebx
0x18007fe36  and     ebx, 80041004h
0x18007fe3c  lea     rcx, [rsp+6A0h+var_670]
0x18007fe41  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18007fe46  nop
0x18007fe47  jmp     loc_1800801D8
0x18007fe4c  lea     rdx, [rbp+5A0h+pSid]; struct CSid *
0x18007fe50  mov     rcx, [rsp+6A0h+var_670]; struct CInstance *
0x18007fe55  call    ?FillTrusteeFromSid@@YAXPEAVCInstance@@AEAVCSid@@@Z; FillTrusteeFromSid(CInstance *,CSid &)
0x18007fe5a  lea     rcx, [rsp+6A0h+var_678]
0x18007fe5f  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18007fe64  mov     rbx, rax
0x18007fe67  lea     rcx, [rsp+6A0h+var_670]
0x18007fe6c  call    ??C?$_com_ptr_t@V?$_com_IIID@VCIRQDescriptor@@$1?_GUID_cb0e0537_d375_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCIRQDescriptor@@XZ; _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(void)
0x18007fe71  mov     r8, rax
0x18007fe74  lea     rdx, aOwner; "Owner"
0x18007fe7b  mov     rcx, rbx
0x18007fe7e  call    cs:__imp_?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z; CInstance::SetEmbeddedObject(ushort const *,CInstance &)
0x18007fe84  test    al, al
0x18007fe86  jnz     short loc_18007FEDF
0x18007fe88  mov     r8d, 80041004h
0x18007fe8e  lea     rdx, aReturnvalue; "ReturnValue"
0x18007fe95  mov     rcx, rdi
0x18007fe98  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18007fe9e  nop
0x18007fe9f  lea     rcx, [rsp+6A0h+var_670]
0x18007fea4  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18007fea9  nop
0x18007feaa  lea     rcx, [rbp+5A0h+pSid]; this
0x18007feae  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x18007feb3  nop
0x18007feb4  lea     rax, ??_7CSecurityDescriptor@@6B@; const CSecurityDescriptor::`vftable'
0x18007febb  mov     [rsp+6A0h+var_630], rax
0x18007fec0  lea     rcx, [rsp+6A0h+var_630]; this
  ... truncated ...
```
