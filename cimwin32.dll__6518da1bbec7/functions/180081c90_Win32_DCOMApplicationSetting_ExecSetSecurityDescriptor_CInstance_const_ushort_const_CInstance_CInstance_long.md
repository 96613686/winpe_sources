# Win32_DCOMApplicationSetting::ExecSetSecurityDescriptor(CInstance const &,ushort * const,CInstance *,CInstance *,long)

- ea: `0x180081c90`
- end: `0x180082923`
- name: `?ExecSetSecurityDescriptor@Win32_DCOMApplicationSetting@@IEAAJAEBVCInstance@@QEAGPEAV2@2J@Z`
- size: `3219`
- prototype: `int(Win32_DCOMApplicationSetting *__hidden this, const struct CInstance *, unsigned __int16 *const, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800dc1d0`

## callees

- `0x180013ae0`
- `0x180015c80`
- `0x180032fd8`
- `0x18003d7b0`
- `0x180063df8`
- `0x18006ef28`
- `0x1800802ac`
- `0x180081c90`
- `0x1800896cc`
- `0x180089af4`
- `0x18009bb18`
- `0x1800dbee0`
- `0x1800dbf28`
- `0x1800f65dc`
- `0x1800f7234`
- `0x1800f7310`
- `0x1800f7c4c`
- `0x1800f8d80`
- `0x1800f92c8`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180081df8`
- `msvcrt!_wcsicmp` at `0x180081e0c`
- `msvcrt!_wcsicmp` at `0x180081e20`
- `msvcrt!_wcsicmp` at `0x1800826c5`
- `msvcrt!_wcsicmp` at `0x180082770`
- `msvcrt!_wcsicmp` at `0x1800827e2`
- `msvcrt!_wcsicmp` at `0x18008281e`
- `msvcrt!_wcsicmp` at `0x180081df8`
- `msvcrt!_wcsicmp` at `0x180081e0c`
- `msvcrt!_wcsicmp` at `0x180081e20`
- `msvcrt!_wcsicmp` at `0x1800826c5`
- `msvcrt!_wcsicmp` at `0x180082770`
- `msvcrt!_wcsicmp` at `0x1800827e2`
- `msvcrt!_wcsicmp` at `0x18008281e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800827c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800827c9`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180082840`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180082840`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800826ef`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180082753`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800826ef`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180082753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800820e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800820e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082345`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800820c3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180082173`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800820c3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180082173`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800824c7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800825dc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800824c7`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800825dc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18008249c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18008249c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18008233b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18008233b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008230d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008246a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008230d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008246a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180082188`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180082188`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800824ae`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800824ae`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180081d22`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180081d22`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800820d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800820d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180081cd8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180081cd8`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180081d6a`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180081d6a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180081dbb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180081dbb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082101`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800821b1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082382`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800824e5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008256d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082659`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082689`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008272b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008285f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082101`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800821b1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082382`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800824e5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008256d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082659`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180082689`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008272b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008285f`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081e70`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081f1e`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081fcf`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180082293`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18008240f`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081e70`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081f1e`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180081fcf`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180082293`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x18008240f`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180081ce6`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180081cf4`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180081ce6`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180081cf4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180082891`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008289f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800828d4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800828e2`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180082891`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18008289f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800828d4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800828e2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180081d9a`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180081de4`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180081d9a`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180081de4`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x18008206f`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x18008206f`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x180081dcb`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x1800826da`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18008273d`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x1800827aa`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x180082805`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18008282f`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x180081dcb`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x1800826da`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18008273d`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x1800827aa`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x180082805`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18008282f`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081e42`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081ecb`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081f7c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18008202d`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081e42`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081ecb`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180081f7c`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x18008202d`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081e9a`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081f48`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081ff9`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081e9a`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081f48`
- `framedynos!?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z` at `0x180081ff9`
- `framedynos!?DeleteCurrentKeyValue@CRegistry@@QEAAKPEBG@Z` at `0x18008278d`
- `framedynos!?DeleteCurrentKeyValue@CRegistry@@QEAAKPEBG@Z` at `0x18008278d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800828ab`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800828ee`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800828ab`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800828ee`

## string_xrefs

- `0x180081e38`: `Descriptor`
- `0x180081e90`: `Descriptor`
- `0x1800827f8`: `AccessPermission`
- `0x18008280b`: `AccessPermission`
- `0x180081dee`: `SetLaunchSecurityDescriptor`
- `0x180082766`: `SetLaunchSecurityDescriptor`
- `0x180081e02`: `SetAccessSecurityDescriptor`
- `0x1800827d8`: `SetAccessSecurityDescriptor`
- `0x180081e16`: `SetConfigurationSecurityDescriptor`
- `0x1800826bb`: `SetConfigurationSecurityDescriptor`
- `0x180082814`: `SetConfigurationSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Win32_DCOMApplicationSetting::ExecSetSecurityDescriptor(
        Win32_DCOMApplicationSetting *this,
        const struct CInstance *a2,
        unsigned __int16 *const a3,
        struct CInstance *a4,
        struct CInstance *a5)
{
  char v8; // r14
  __int64 v9; // rdx
  unsigned int v10; // r8d
  signed int KeySecurity; // eax
  bool v12; // cc
  const unsigned __int16 *v13; // rbx
  HKEY v14; // rax
  struct MethodContext *MethodContext; // rbx
  CInstance *v16; // rax
  char v17; // r15
  CInstance *v18; // rdi
  CInstance *v19; // rax
  struct MethodContext *v20; // rbx
  CInstance *v21; // rax
  char v22; // di
  CInstance *v23; // rdi
  CInstance *v24; // rax
  struct MethodContext *v25; // rbx
  CInstance *v26; // rax
  CInstance *v27; // rax
  __int64 v28; // rdx
  BOOL v29; // ebx
  signed int LastError; // eax
  unsigned int v31; // r8d
  unsigned int v32; // ebx
  BOOL v33; // ebx
  signed int v34; // eax
  unsigned int v35; // r8d
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  char v39; // al
  char *v40; // rbx
  CInstance *v41; // rax
  struct MethodContext *v42; // rax
  unsigned int v43; // eax
  DWORD v44; // edi
  struct _ACL *v45; // rax
  struct _ACL *v46; // rbx
  BOOL v47; // edi
  signed int v48; // eax
  unsigned int v49; // r8d
  CSACL *v50; // rax
  CInstance *v51; // rax
  struct MethodContext *v52; // rax
  DWORD v53; // edi
  struct _ACL *v54; // rax
  struct _ACL *v55; // rbx
  BOOL v56; // edi
  BYTE *v57; // rax
  BYTE *lpData; // rdi
  HKEY v59; // rax
  BYTE *v60; // rbx
  HKEY v61; // rax
  const unsigned __int16 *v62; // rdx
  DWORD cbData; // ebx
  HKEY v64; // rax
  const WCHAR *v65; // rdx
  HKEY v66; // rax
  bool v68[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v69[2]; // [rsp+34h] [rbp-CCh] BYREF
  struct CInstance *v70; // [rsp+38h] [rbp-C8h] BYREF
  struct CInstance *v71; // [rsp+40h] [rbp-C0h] BYREF
  struct CInstance *v72; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwBufferLength; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v74; // [rsp+54h] [rbp-ACh] BYREF
  CDACL *v75; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v76; // [rsp+60h] [rbp-A0h] BYREF
  CSACL *v77; // [rsp+68h] [rbp-98h] BYREF
  char v78[8]; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v79; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v80[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v81[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v82[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v83[24]; // [rsp+C8h] [rbp-38h] BYREF
  PSID pSid; // [rsp+E0h] [rbp-20h] BYREF
  int v85; // [rsp+E8h] [rbp-18h]
  __int64 v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]
  __int64 v88; // [rsp+100h] [rbp+0h]
  int v89; // [rsp+108h] [rbp+8h]
  DWORD nAclLength[2]; // [rsp+110h] [rbp+10h] BYREF
  PSID pGroup; // [rsp+118h] [rbp+18h] BYREF
  int v92; // [rsp+120h] [rbp+20h]
  __int64 v93; // [rsp+128h] [rbp+28h]
  __int64 v94; // [rsp+130h] [rbp+30h]
  __int64 v95; // [rsp+138h] [rbp+38h]
  int v96; // [rsp+140h] [rbp+40h]
  struct _ACL *v97; // [rsp+148h] [rbp+48h] BYREF
  struct _ACL *v98; // [rsp+150h] [rbp+50h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v100; // [rsp+178h] [rbp+78h]
  _BYTE v101[24]; // [rsp+188h] [rbp+88h] BYREF
  char *v102; // [rsp+1A0h] [rbp+A0h]
  _BYTE v103[608]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v104[608]; // [rsp+410h] [rbp+310h] BYREF

  CHString::CHString((CHString *)v78);
  CRegistry::CRegistry((CRegistry *)v104);
  CRegistry::CRegistry((CRegistry *)v103);
  v68[0] = 0;
  v8 = 1;
  v69[0] = 1;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v100 = 0;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  v79 = 0;
  dwBufferLength = 0;
  MakeGuard<void (*)(unsigned char *),RefHolder<unsigned char *>>(v101, v9, &v79);
  v72 = 0;
  if ( a4 && a5 )
  {
    if ( !CInstance::GetCHString(a2, L"AppID", (struct CHString *)v78) )
    {
      v10 = -2147217393;
LABEL_129:
      v32 = !CInstance::SetDWORD(a5, L"ReturnValue", v10) ? 0x80041004 : 0;
      goto LABEL_130;
    }
    KeySecurity = CRegistry::Open((CRegistry *)v104, HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0x1020019u);
    v12 = KeySecurity <= 0;
    if ( KeySecurity )
      goto LABEL_6;
    v13 = (const unsigned __int16 *)CHString::operator unsigned short const *(v78);
    v14 = CRegistry::GethKey((CRegistry *)v104);
    KeySecurity = CRegistry::Open((CRegistry *)v103, v14, v13, 0x10F003Fu);
    v12 = KeySecurity <= 0;
    if ( KeySecurity )
      goto LABEL_6;
    if ( _wcsicmp(a3, L"SetLaunchSecurityDescriptor")
      && _wcsicmp(a3, L"SetAccessSecurityDescriptor")
      && _wcsicmp(a3, L"SetConfigurationSecurityDescriptor") )
    {
      goto LABEL_127;
    }
    if ( !CInstance::GetStatus(a4, L"Descriptor", v68, v69) )
      goto LABEL_128;
    if ( v68[0] )
    {
      if ( v69[0] == 13 )
      {
        MethodContext = CInstance::GetMethodContext(a4);
        _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v72);
        v72 = 0;
        if ( CInstance::GetEmbeddedObject(a4, L"Descriptor", &v72, MethodContext) )
        {
          v70 = 0;
          v16 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
          if ( CInstance::GetStatus(v16, L"Owner", v68, v69) && v68[0] && (v69[0] == 13 || v69[0] == 1) )
          {
            if ( v69[0] == 1 )
            {
              v17 = 0;
LABEL_25:
              v71 = 0;
              v21 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
              if ( !CInstance::GetStatus(v21, L"Group", v68, v69) || !v68[0] || v69[0] != 13 && v69[0] != 1 )
                goto LABEL_99;
              if ( v69[0] == 1 )
              {
                v22 = 0;
              }
              else
              {
                v23 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
                v24 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
                v25 = CInstance::GetMethodContext(v24);
                _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v71);
                v71 = 0;
                if ( !CInstance::GetEmbeddedObject(v23, L"Group", &v71, v25) )
                  goto LABEL_99;
                v22 = 1;
              }
              v74 = 0;
              v26 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
              if ( CInstance::GetStatus(v26, L"ControlFlags", v68, v69) && v68[0] && v69[0] == 3 )
              {
                v27 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
                if ( CInstance::GetDWORD(v27, L"ControlFlags", &v74) )
                {
                  pSid = 0;
                  v85 = 8;
                  v86 = 0;
                  v87 = 0;
                  v88 = 0;
                  v89 = 0;
                  if ( v17 )
                  {
                    if ( FillSIDFromTrustee(v70, (struct CSid *)&pSid) )
                    {
                      v31 = -2147217400;
LABEL_45:
                      v32 = !CInstance::SetDWORD(a5, L"ReturnValue", v31) ? 0x80041004 : 0;
LABEL_46:
                      CSid::~CSid(&pSid);
LABEL_100:
                      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v71);
LABEL_102:
                      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v70);
                      goto LABEL_130;
                    }
                    if ( pSid )
                    {
                      v29 = v74 & 1;
                      if ( IsValidSid(pSid) )
                      {
                        if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, v29) )
                        {
                          LastError = GetLastError();
                          if ( LastError > 0 )
                            LastError = (unsigned __int16)LastError | 0x80070000;
                          v31 = LastError;
                          goto LABEL_45;
                        }
                      }
                    }
                  }
                  pGroup = 0;
                  v92 = 8;
                  v93 = 0;
                  v94 = 0;
                  v95 = 0;
                  v96 = 0;
                  if ( v22 )
                  {
                    if ( FillSIDFromTrustee(v71, (struct CSid *)&pGroup) )
                    {
                      v35 = -2147217400;
LABEL_56:
                      v32 = !CInstance::SetDWORD(a5, L"ReturnValue", v35) ? 0x80041004 : 0;
LABEL_57:
                      CSid::~CSid(&pGroup);
                      goto LABEL_46;
                    }
                    v33 = (v74 >> 1) & 1;
                    if ( pGroup && IsValidSid(pGroup) && !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, v33) )
                    {
                      v34 = GetLastError();
                      if ( v34 > 0 )
                        v34 = (unsigned __int16)v34 | 0x80070000;
                      v35 = v34;
                      goto LABEL_56;
                    }
                  }
                  v75 = 0;
                  MakeGuard<void (*)(CDACL const *),RefHolder<CDACL *>>((__int64)v83, v28, (__int64)&v75);
                  nAclLength[0] = 0;
                  v97 = 0;
                  MakeGuard<void (*)(unsigned char *),RefHolder<unsigned char *>>(v82, v36, &v97);
                  v77 = 0;
                  MakeGuard<void (*)(CSACL const *),RefHolder<CSACL *>>((__int64)v81, v37, (__int64)&v77);
                  v76 = 0;
                  v98 = 0;
                  MakeGuard<void (*)(unsigned char *),RefHolder<unsigned char *>>(v80, v38, &v98);
                  v39 = v74;
                  if ( (v74 & 4) != 0 )
                  {
                    v40 = (char *)operator new(0x58u);
                    v102 = v40;
                    if ( v40 )
                    {
                      *(_QWORD *)v40 = &CDACL::`vftable';
                      memset_0(v40 + 8, 0, 0x50u);
                    }
                    else
                    {
                      v40 = 0;
                    }
                    v75 = (CDACL *)v40;
                    if ( !v40 )
                      goto LABEL_95;
                    v41 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
                    v42 = CInstance::GetMethodContext(v41);
                    v43 = FillDACLFromInstance(v72, v75, v42);
                    if ( v43 )
                    {
                      if ( v43 == 0x20000000 )
                      {
                        if ( !CDACL::CreateNullDACL(v75) )
                        {
LABEL_93:
                          CInstance::SetDWORD(a5, L"ReturnValue", 0x80041004);
                          ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v80);
                          ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v81);
                          ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v82);
                          ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v83);
                          CSid::~CSid(&pGroup);
                          CSid::~CSid(&pSid);
                          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v71);
                          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v70);
                          v32 = -2147217404;
LABEL_130:
                          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v72);
                          ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v101);
                          CRegistry::~CRegistry((CRegistry *)v103);
                          CRegistry::~CRegistry((CRegistry *)v104);
                          CHString::~CHString((CHString *)v78);
                          return v32;
                        }
                      }
                      else
                      {
                        if ( v43 != 0x10000000 )
                          goto LABEL_77;
                        CDACL::Clear(v75);
                      }
                    }
                    if ( !CDACL::CalculateDACLSize(v75, nAclLength) )
                    {
LABEL_77:
                      v49 = -2147217400;
LABEL_78:
                      v32 = !CInstance::SetDWORD(a5, L"ReturnValue", v49) ? 0x80041004 : 0;
                      ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v80);
                      ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v81);
                      ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v82);
                      ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v83);
                      goto LABEL_57;
                    }
                    v44 = nAclLength[0];
                    if ( nAclLength[0] >= 8 )
                    {
                      v45 = (struct _ACL *)operator new(nAclLength[0]);
                      v46 = v45;
                      v97 = v45;
                      if ( !v45 )
                        goto LABEL_95;
                      InitializeAcl(v45, v44, 2u);
                      v47 = (v74 >> 3) & 1;
                      if ( CDACL::FillDACL(v75, v46) )
                        goto LABEL_77;
                      if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v46, v47) )
                      {
LABEL_72:
                        v48 = GetLastError();
                        if ( v48 > 0 )
                          v48 = (unsigned __int16)v48 | 0x80070000;
                        v49 = v48;
                        goto LABEL_78;
                      }
                    }
                    v39 = v74;
                  }
                  if ( (v39 & 0x10) == 0 )
                    goto LABEL_91;
                  v50 = (CSACL *)operator new(0x10u);
                  *(_QWORD *)nAclLength = v50;
                  if ( v50 )
                  {
                    *(_QWORD *)v50 = &CSACL::`vftable';
                    *((_QWORD *)v50 + 1) = 0;
                  }
                  else
                  {
                    v50 = 0;
                  }
                  v77 = v50;
                  if ( !v50 )
                    goto LABEL_95;
                  v51 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
                  v52 = CInstance::GetMethodContext(v51);
                  if ( FillSACLFromInstance(v72, v77, v52) )
                    goto LABEL_91;
                  if ( !(unsigned int)CSACL::CalculateSACLSize(v77, &v76) )
                    goto LABEL_77;
                  v53 = v76;
                  if ( v76 <= 8 )
                  {
LABEL_91:
                    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
                      goto LABEL_72;
                    MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
                    if ( !dwBufferLength )
                      goto LABEL_93;
                    v57 = (BYTE *)operator new(dwBufferLength);
                    lpData = v57;
                    v79 = v57;
                    if ( !v57 )
                      goto LABEL_95;
                    if ( !MakeSelfRelativeSD(pSecurityDescriptor, v57, &dwBufferLength) )
                      goto LABEL_72;
                    v8 = 0;
                    ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v80);
                    ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v81);
                    ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v82);
                    ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v83);
                    CSid::~CSid(&pGroup);
                    CSid::~CSid(&pSid);
                    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v71);
                    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v70);
LABEL_112:
                    if ( !_wcsicmp(a3, L"SetLaunchSecurityDescriptor") )
                    {
                      if ( v8 )
                      {
                        v62 = L"LaunchPermission";
                        goto LABEL_115;
                      }
                      cbData = dwBufferLength;
                      v64 = CRegistry::GethKey((CRegistry *)v103);
                      v65 = L"LaunchPermission";
LABEL_118:
                      KeySecurity = RegSetValueExW(v64, v65, 0, 3u, lpData, cbData);
                      goto LABEL_119;
                    }
                    if ( !_wcsicmp(a3, L"SetAccessSecurityDescriptor") )
                    {
                      if ( v8 )
                      {
                        v62 = L"AccessPermission";
LABEL_115:
                        KeySecurity = CRegistry::DeleteCurrentKeyValue((CRegistry *)v103, v62);
                        if ( (KeySecurity & 0xFFFFFFFD) == 0 )
                        {
LABEL_116:
                          v10 = 0;
                          goto LABEL_129;
                        }
                        goto LABEL_107;
                      }
                      cbData = dwBufferLength;
                      v64 = CRegistry::GethKey((CRegistry *)v103);
                      v65 = L"AccessPermission";
                      goto LABEL_118;
                    }
                    if ( !_wcsicmp(a3, L"SetConfigurationSecurityDescriptor") )
                    {
                      v66 = CRegistry::GethKey((CRegistry *)v103);
                      KeySecurity = RegSetKeySecurity(v66, 0xFu, lpData);
LABEL_119:
                      v12 = KeySecurity <= 0;
                      if ( !KeySecurity )
                        goto LABEL_116;
                      goto LABEL_6;
                    }
LABEL_127:
                    v32 = -2147217362;
                    goto LABEL_130;
                  }
                  v54 = (struct _ACL *)operator new(v76);
                  v55 = v54;
                  v98 = v54;
                  if ( v54 )
                  {
                    InitializeAcl(v54, v53, 2u);
                    v56 = (v74 >> 5) & 1;
                    if ( !CSACL::FillSACL(v77, v55) )
                    {
                      if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v55, v56) )
                        goto LABEL_72;
                      goto LABEL_91;
                    }
                    goto LABEL_77;
                  }
LABEL_95:
                  CInstance::SetDWORD(a5, L"ReturnValue", 0x80041006);
                  ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v80);
                  ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v81);
                  ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v82);
                  ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>::~ScopeGuardImpl1<void * (*)(void *),RefHolder<void *>>(v83);
                  CSid::~CSid(&pGroup);
                  CSid::~CSid(&pSid);
                  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v71);
                  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v70);
LABEL_96:
                  v32 = -2147217402;
                  goto LABEL_130;
                }
              }
LABEL_99:
              v32 = !CInstance::SetDWORD(a5, L"ReturnValue", 0x80041008) ? 0x80041004 : 0;
              goto LABEL_100;
            }
            v18 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
            v19 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v72);
            v20 = CInstance::GetMethodContext(v19);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v70);
            v70 = 0;
            if ( CInstance::GetEmbeddedObject(v18, L"Owner", &v70, v20) )
            {
              v17 = 1;
              goto LABEL_25;
            }
          }
          v32 = !CInstance::SetDWORD(a5, L"ReturnValue", 0x80041008) ? 0x80041004 : 0;
          goto LABEL_102;
        }
LABEL_128:
        v10 = -2147217400;
        goto LABEL_129;
      }
      if ( v69[0] != 1 )
        goto LABEL_128;
    }
    lpData = 0;
    if ( !_wcsicmp(a3, L"SetConfigurationSecurityDescriptor") )
    {
      v59 = CRegistry::GethKey((CRegistry *)v104);
      KeySecurity = RegGetKeySecurity(v59, 0xFu, 0, &dwBufferLength);
      if ( KeySecurity && KeySecurity != 122 )
      {
LABEL_107:
        v12 = KeySecurity <= 0;
        goto LABEL_6;
      }
      v60 = (BYTE *)operator new(dwBufferLength);
      v79 = v60;
      if ( !v60 )
      {
        CInstance::SetDWORD(a5, L"ReturnValue", 0x80041006);
        goto LABEL_96;
      }
      v61 = CRegistry::GethKey((CRegistry *)v104);
      KeySecurity = RegGetKeySecurity(v61, 0xFu, v60, &dwBufferLength);
      v12 = KeySecurity <= 0;
      if ( KeySecurity )
      {
LABEL_6:
        if ( !v12 )
          KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
        v10 = KeySecurity;
        goto LABEL_129;
      }
      lpData = v79;
    }
    goto LABEL_112;
  }
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v72);
  ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v101);
  CRegistry::~CRegistry((CRegistry *)v103);
  CRegistry::~CRegistry((CRegistry *)v104);
  CHString::~CHString((CHString *)v78);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180081c90  mov     [rsp-8+arg_0], rbx
0x180081c95  push    rbp
0x180081c96  push    rsi
0x180081c97  push    rdi
0x180081c98  push    r12
0x180081c9a  push    r13
0x180081c9c  push    r14
0x180081c9e  push    r15
0x180081ca0  lea     rbp, [rsp-580h]
0x180081ca8  sub     rsp, 680h
0x180081caf  mov     rax, cs:__security_cookie
0x180081cb6  xor     rax, rsp
0x180081cb9  mov     [rbp+5B0h+var_40], rax
0x180081cc0  mov     rdi, r9
0x180081cc3  mov     r12, r8
0x180081cc6  mov     rbx, rdx
0x180081cc9  mov     rsi, [rbp+5B0h+arg_20]
0x180081cd0  xor     r13d, r13d
0x180081cd3  lea     rcx, [rsp+6B0h+var_640]
0x180081cd8  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180081cde  nop
0x180081cdf  lea     rcx, [rbp+5B0h+var_2A0]
0x180081ce6  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180081cec  nop
0x180081ced  lea     rcx, [rbp+5B0h+var_500]
0x180081cf4  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180081cfa  nop
0x180081cfb  mov     [rsp+6B0h+var_680], r13b
0x180081d00  lea     r14d, [r13+1]
0x180081d04  mov     [rsp+6B0h+var_67C], r14w
0x180081d0a  xorps   xmm0, xmm0
0x180081d0d  xor     eax, eax
0x180081d0f  movups  [rbp+5B0h+pSecurityDescriptor], xmm0
0x180081d13  movups  [rbp+5B0h+var_548], xmm0
0x180081d17  mov     [rbp+5B0h+var_538], rax
0x180081d1b  mov     edx, r14d; dwRevision
0x180081d1e  lea     rcx, [rbp+5B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180081d22  call    cs:__imp_InitializeSecurityDescriptor
0x180081d28  mov     [rsp+6B0h+var_638], r13
0x180081d2d  mov     [rsp+6B0h+dwBufferLength], r13d
0x180081d32  lea     r8, [rsp+6B0h+var_638]
0x180081d37  lea     rcx, [rbp+5B0h+var_528]
0x180081d3e  call    ??$MakeGuard@P6AXPEAE@ZV?$RefHolder@PEAE@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@P6AXPEAE@ZV?$RefHolder@PEAE@@@Z; MakeGuard<void (*)(uchar *),RefHolder<uchar *>>(void (*)(uchar *),RefHolder<uchar *>)
0x180081d43  nop
0x180081d44  mov     [rsp+6B0h+var_668], r13
0x180081d49  test    rdi, rdi
0x180081d4c  jz      loc_1800828B5
0x180081d52  test    rsi, rsi
0x180081d55  jz      loc_1800828B5
0x180081d5b  lea     r8, [rsp+6B0h+var_640]
0x180081d60  lea     rdx, aAppid; "AppID"
0x180081d67  mov     rcx, rbx
0x180081d6a  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180081d70  test    al, al
0x180081d72  jnz     short loc_180081D7F
0x180081d74  mov     r8d, 8004100Fh
0x180081d7a  jmp     loc_180082855
0x180081d7f  mov     r9d, 1020019h
0x180081d85  lea     r8, aSoftwareClasse_2; "Software\\Classes\\AppID"
0x180081d8c  mov     rdx, 0FFFFFFFF80000002h
0x180081d93  lea     rcx, [rbp+5B0h+var_2A0]
0x180081d9a  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180081da0  test    eax, eax
0x180081da2  jz      short loc_180081DB6
0x180081da4  jle     short loc_180081DAE
0x180081da6  movzx   eax, ax
0x180081da9  or      eax, 80070000h
0x180081dae  mov     r8d, eax
0x180081db1  jmp     loc_180082855
0x180081db6  lea     rcx, [rsp+6B0h+var_640]
0x180081dbb  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180081dc1  mov     rbx, rax
0x180081dc4  lea     rcx, [rbp+5B0h+var_2A0]
0x180081dcb  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x180081dd1  mov     r9d, 10F003Fh
0x180081dd7  mov     r8, rbx
0x180081dda  mov     rdx, rax
0x180081ddd  lea     rcx, [rbp+5B0h+var_500]
0x180081de4  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180081dea  test    eax, eax
0x180081dec  jnz     short loc_180081DA4
0x180081dee  lea     rdx, aSetlaunchsecur; "SetLaunchSecurityDescriptor"
0x180081df5  mov     rcx, r12; String1
0x180081df8  call    cs:__imp__wcsicmp
0x180081dfe  test    eax, eax
0x180081e00  jz      short loc_180081E2E
0x180081e02  lea     rdx, aSetaccesssecur; "SetAccessSecurityDescriptor"
0x180081e09  mov     rcx, r12; String1
0x180081e0c  call    cs:__imp__wcsicmp
0x180081e12  test    eax, eax
0x180081e14  jz      short loc_180081E2E
0x180081e16  lea     rdx, aSetconfigurati; "SetConfigurationSecurityDescriptor"
0x180081e1d  mov     rcx, r12; String1
0x180081e20  call    cs:__imp__wcsicmp
0x180081e26  test    eax, eax
0x180081e28  jnz     loc_180082848
0x180081e2e  lea     r9, [rsp+6B0h+var_67C]
0x180081e33  lea     r8, [rsp+6B0h+var_680]
0x180081e38  lea     rdx, aDescriptor; "Descriptor"
0x180081e3f  mov     rcx, rdi
0x180081e42  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180081e48  test    al, al
0x180081e4a  jz      loc_18008284F
0x180081e50  mov     r15d, 3
0x180081e56  cmp     [rsp+6B0h+var_680], r13b
0x180081e5b  jz      loc_1800826B8
0x180081e61  cmp     [rsp+6B0h+var_67C], 0Dh
0x180081e67  jnz     loc_1800826AC
0x180081e6d  mov     rcx, rdi
0x180081e70  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x180081e76  mov     rbx, rax
0x180081e79  lea     rcx, [rsp+6B0h+var_668]
0x180081e7e  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x180081e83  mov     [rsp+6B0h+var_668], r13
0x180081e88  mov     r9, rbx
0x180081e8b  lea     r8, [rsp+6B0h+var_668]
0x180081e90  lea     rdx, aDescriptor; "Descriptor"
0x180081e97  mov     rcx, rdi
0x180081e9a  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x180081ea0  test    al, al
0x180081ea2  jz      loc_18008284F
0x180081ea8  mov     [rsp+6B0h+var_678], r13
0x180081ead  lea     rcx, [rsp+6B0h+var_668]
0x180081eb2  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081eb7  lea     r9, [rsp+6B0h+var_67C]
0x180081ebc  lea     r8, [rsp+6B0h+var_680]
0x180081ec1  lea     rdx, aOwner; "Owner"
0x180081ec8  mov     rcx, rax
0x180081ecb  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180081ed1  test    al, al
0x180081ed3  jz      loc_180082679
0x180081ed9  cmp     [rsp+6B0h+var_680], r13b
0x180081ede  jz      loc_180082679
0x180081ee4  movzx   eax, [rsp+6B0h+var_67C]
0x180081ee9  cmp     ax, 0Dh
0x180081eed  jz      short loc_180081EF9
0x180081eef  cmp     ax, r14w
0x180081ef3  jnz     loc_180082679
0x180081ef9  cmp     ax, r14w
0x180081efd  jnz     short loc_180081F04
0x180081eff  mov     r15b, r13b
0x180081f02  jmp     short loc_180081F59
0x180081f04  lea     rcx, [rsp+6B0h+var_668]
0x180081f09  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081f0e  mov     rdi, rax
0x180081f11  lea     rcx, [rsp+6B0h+var_668]
0x180081f16  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081f1b  mov     rcx, rax
0x180081f1e  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x180081f24  mov     rbx, rax
0x180081f27  lea     rcx, [rsp+6B0h+var_678]
0x180081f2c  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x180081f31  mov     [rsp+6B0h+var_678], r13
0x180081f36  mov     r9, rbx
0x180081f39  lea     r8, [rsp+6B0h+var_678]
0x180081f3e  lea     rdx, aOwner; "Owner"
0x180081f45  mov     rcx, rdi
0x180081f48  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x180081f4e  test    al, al
0x180081f50  jz      loc_180082679
0x180081f56  mov     r15b, r14b
0x180081f59  mov     [rsp+6B0h+var_670], r13
0x180081f5e  lea     rcx, [rsp+6B0h+var_668]
0x180081f63  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081f68  lea     r9, [rsp+6B0h+var_67C]
0x180081f6d  lea     r8, [rsp+6B0h+var_680]
0x180081f72  lea     rdx, aGroup; "Group"
0x180081f79  mov     rcx, rax
0x180081f7c  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180081f82  test    al, al
0x180081f84  jz      loc_180082649
0x180081f8a  cmp     [rsp+6B0h+var_680], r13b
0x180081f8f  jz      loc_180082649
0x180081f95  movzx   eax, [rsp+6B0h+var_67C]
0x180081f9a  cmp     ax, 0Dh
0x180081f9e  jz      short loc_180081FAA
0x180081fa0  cmp     ax, r14w
0x180081fa4  jnz     loc_180082649
0x180081faa  cmp     ax, r14w
0x180081fae  jnz     short loc_180081FB5
0x180081fb0  mov     dil, r13b
0x180081fb3  jmp     short loc_18008200A
0x180081fb5  lea     rcx, [rsp+6B0h+var_668]
0x180081fba  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081fbf  mov     rdi, rax
0x180081fc2  lea     rcx, [rsp+6B0h+var_668]
0x180081fc7  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180081fcc  mov     rcx, rax
0x180081fcf  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x180081fd5  mov     rbx, rax
0x180081fd8  lea     rcx, [rsp+6B0h+var_670]
0x180081fdd  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x180081fe2  mov     [rsp+6B0h+var_670], r13
0x180081fe7  mov     r9, rbx
0x180081fea  lea     r8, [rsp+6B0h+var_670]
0x180081fef  lea     rdx, aGroup; "Group"
0x180081ff6  mov     rcx, rdi
0x180081ff9  call    cs:__imp_?GetEmbeddedObject@CInstance@@QEBA_NPEBGPEAPEAV1@PEAVMethodContext@@@Z; CInstance::GetEmbeddedObject(ushort const *,CInstance * *,MethodContext *)
0x180081fff  test    al, al
0x180082001  jz      loc_180082649
0x180082007  mov     dil, r14b
0x18008200a  mov     [rsp+6B0h+var_65C], r13d
0x18008200f  lea     rcx, [rsp+6B0h+var_668]
0x180082014  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180082019  lea     r9, [rsp+6B0h+var_67C]
0x18008201e  lea     r8, [rsp+6B0h+var_680]
0x180082023  lea     rdx, aControlflags; "ControlFlags"
0x18008202a  mov     rcx, rax
0x18008202d  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180082033  test    al, al
0x180082035  jz      loc_180082649
0x18008203b  cmp     [rsp+6B0h+var_680], r13b
0x180082040  jz      loc_180082649
0x180082046  mov     eax, 3
0x18008204b  cmp     [rsp+6B0h+var_67C], ax
0x180082050  jnz     loc_180082649
0x180082056  lea     rcx, [rsp+6B0h+var_668]
0x18008205b  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180082060  lea     r8, [rsp+6B0h+var_65C]
0x180082065  lea     rdx, aControlflags; "ControlFlags"
0x18008206c  mov     rcx, rax
0x18008206f  call    cs:__imp_?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z; CInstance::GetDWORD(ushort const *,ulong &)
0x180082075  test    al, al
0x180082077  jz      loc_180082649
0x18008207d  mov     [rbp+5B0h+pSid], r13
0x180082081  mov     [rbp+5B0h+var_5C8], 8
0x180082088  mov     [rbp+5B0h+var_5C0], r13
0x18008208c  mov     [rbp+5B0h+var_5B8], r13
0x180082090  mov     [rbp+5B0h+var_5B0], r13
0x180082094  mov     [rbp+5B0h+var_5A8], r13d
0x180082098  test    r15b, r15b
0x18008209b  jz      loc_18008212B
0x1800820a1  lea     rdx, [rbp+5B0h+pSid]; struct CSid *
0x1800820a5  mov     rcx, [rsp+6B0h+var_678]; struct CInstance *
0x1800820aa  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x1800820af  test    eax, eax
0x1800820b1  jnz     short loc_180082123
0x1800820b3  mov     rcx, [rbp+5B0h+pSid]; pSid
0x1800820b7  test    rcx, rcx
0x1800820ba  jz      short loc_18008212B
0x1800820bc  mov     ebx, [rsp+6B0h+var_65C]
0x1800820c0  and     ebx, r14d
0x1800820c3  call    cs:__imp_IsValidSid
0x1800820c9  test    eax, eax
0x1800820cb  jz      short loc_18008212B
0x1800820cd  mov     r8d, ebx; bOwnerDefaulted
0x1800820d0  mov     rdx, [rbp+5B0h+pSid]; pOwner
0x1800820d4  lea     rcx, [rbp+5B0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800820d8  call    cs:__imp_SetSecurityDescriptorOwner
0x1800820de  test    eax, eax
0x1800820e0  jnz     short loc_18008212B
0x1800820e2  call    cs:__imp_GetLastError
0x1800820e8  test    eax, eax
0x1800820ea  jle     short loc_1800820F4
0x1800820ec  movzx   eax, ax
0x1800820ef  or      eax, 80070000h
0x1800820f4  mov     r8d, eax
0x1800820f7  lea     rdx, aReturnvalue; "ReturnValue"
0x1800820fe  mov     rcx, rsi
0x180082101  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180082107  nop
0x180082108  neg     al
0x18008210a  sbb     ebx, ebx
0x18008210c  not     ebx
0x18008210e  and     ebx, 80041004h
0x180082114  lea     rcx, [rbp+5B0h+pSid]; this
0x180082118  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x18008211d  nop
0x18008211e  jmp     loc_18008266C
0x180082123  mov     r8d, 80041008h
0x180082129  jmp     short loc_1800820F7
0x18008212b  mov     [rbp+5B0h+pGroup], r13
0x18008212f  mov     [rbp+5B0h+var_590], 8
0x180082136  mov     [rbp+5B0h+var_588], r13
0x18008213a  mov     [rbp+5B0h+var_580], r13
0x18008213e  mov     [rbp+5B0h+var_578], r13
0x180082142  mov     [rbp+5B0h+var_570], r13d
0x180082146  test    dil, dil
0x180082149  jz      loc_1800821DB
0x18008214f  lea     rdx, [rbp+5B0h+pGroup]; struct CSid *
0x180082153  mov     rcx, [rsp+6B0h+var_670]; struct CInstance *
0x180082158  call    ?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z; FillSIDFromTrustee(CInstance *,CSid &)
0x18008215d  test    eax, eax
0x18008215f  jnz     short loc_1800821D3
0x180082161  mov     ebx, [rsp+6B0h+var_65C]
0x180082165  shr     ebx, 1
0x180082167  and     ebx, r14d
0x18008216a  mov     rcx, [rbp+5B0h+pGroup]; pSid
0x18008216e  test    rcx, rcx
0x180082171  jz      short loc_1800821DB
0x180082173  call    cs:__imp_IsValidSid
0x180082179  test    eax, eax
0x18008217b  jz      short loc_1800821DB
0x18008217d  mov     r8d, ebx; bGroupDefaulted
0x180082180  mov     rdx, [rbp+5B0h+pGroup]; pGroup
0x180082184  lea     rcx, [rbp+5B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180082188  call    cs:__imp_SetSecurityDescriptorGroup
0x18008218e  test    eax, eax
0x180082190  jnz     short loc_1800821DB
0x180082192  call    cs:__imp_GetLastError
  ... truncated ...
```
