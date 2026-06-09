# CCSDirectTransaction::InstallPrivateComponent(ulong,Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_PRIVATE_COMPONENT_ const *,ulong &)

- ea: `0x1800c13e4`
- end: `0x1800c2ebd`
- name: `?InstallPrivateComponent@CCSDirectTransaction@@IEAAJKPEBU_COMPONENT_STORE_PROVIDER_INSTALL_PRIVATE_COMPONENT_@Rtl@Implementation@Isolation@Windows@@AEAK@Z`
- size: `6873`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, unsigned int, const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_PRIVATE_COMPONENT_ *, unsigned int *)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c9140`

## callees

- `0x18001259c`
- `0x1800125c8`
- `0x180012950`
- `0x180012b1c`
- `0x180013de8`
- `0x18001531c`
- `0x1800153cc`
- `0x18001559c`
- `0x1800157c8`
- `0x1800174d4`
- `0x180018b30`
- `0x180018bb8`
- `0x18001d478`
- `0x18001ddec`
- `0x18001e100`
- `0x18001e608`
- `0x18001eb80`
- `0x18001fc6c`
- `0x180027594`
- `0x180028930`
- `0x180028ce4`
- `0x18002ba70`
- `0x18002f364`
- `0x18003695c`
- `0x18003f260`
- `0x18003f31c`
- `0x180040020`
- `0x180043570`
- `0x180048470`
- `0x18004f2dc`
- `0x1800bae90`
- `0x1800bb178`
- `0x1800bbbc8`
- `0x1800bbe88`
- `0x1800bbf24`
- `0x1800bc2fc`
- `0x1800bc780`
- `0x1800be69c`
- `0x1800bfb4c`
- `0x1800c13e4`
- `0x1800c5bdc`
- `0x1800c628c`
- `0x1800c750c`
- `0x1800c9938`
- `0x1800c9e8c`
- `0x1800d10d8`
- `0x1800d1230`
- `0x1800d28e0`
- `0x1800fe440`
- `0x18010f260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c15c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1981`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1bef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1e06`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1f90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c2473`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c2e45`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c15c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1981`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1bef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1e06`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c1f90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c2473`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c2e45`

## string_xrefs

- `0x1800c157f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c170a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c1931`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c1b9f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c1db7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c1f39`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c2124`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c2289`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c23de`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c2d67`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c2df9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c142d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`
- `0x1800c20ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`
- `0x1800c1757`: `   Install Private Component Data:\n      Definition AppId: {appid}\n      ManifestPath: {mf}\n      DefinitionIdentity: {defid}\n`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::InstallPrivateComponent(
        CCSDirectTransaction *this,
        __int64 a2,
        const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_PRIVATE_COMPONENT_ *a3,
        unsigned int *a4)
{
  __int64 v6; // r10
  void *v7; // r11
  int SystemIsolatedFilesystem; // esi
  __int64 *v9; // r12
  char IsBaseIdentityHandleValidWithType; // al
  signed int v11; // ecx
  _QWORD *v12; // r13
  __int64 v13; // r10
  void *v14; // r11
  __int64 v15; // r10
  unsigned int *v16; // r11
  __int64 v17; // rcx
  void *v18; // rcx
  const char *v19; // r15
  unsigned __int64 *v20; // r9
  unsigned __int64 v21; // r8
  void *v22; // rcx
  __int64 v23; // r10
  unsigned int *v24; // r11
  signed int v25; // ecx
  __int64 v26; // rbx
  const struct CApplicationAccessor *v27; // r12
  __int64 v28; // rcx
  int v29; // edx
  void *v30; // rcx
  __int64 v31; // r10
  unsigned int *v32; // r11
  signed int v33; // ecx
  __int64 v34; // r13
  bool v35; // bl
  __int64 v36; // r10
  unsigned int *v37; // r11
  signed int v38; // ecx
  __int64 v39; // r10
  unsigned int *v40; // r11
  signed int v41; // ecx
  unsigned int i; // r8d
  bool v43; // bl
  __int64 v44; // r8
  int v45; // r9d
  __int64 v46; // r10
  unsigned int *v47; // r11
  signed int v48; // ecx
  bool v49; // r15
  char v50; // r13
  __int64 v51; // r10
  const char *v52; // rbx
  __int64 v53; // r10
  __int64 v54; // rax
  __int64 v55; // rax
  unsigned __int64 v56; // rbx
  int v57; // edx
  unsigned __int64 v58; // rcx
  const struct _LUNICODE_STRING *v59; // r9
  __int64 v60; // rdx
  _QWORD *v61; // r15
  char *v62; // rbx
  __int64 v63; // rdx
  _QWORD *v64; // r15
  _QWORD *v65; // rax
  __int64 v66; // rdx
  _QWORD *v67; // r15
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rbx
  __int128 v71; // xmm0
  __int64 v72; // xmm1_8
  void *v73; // xmm1_8
  __int64 v74; // rdx
  _QWORD *v75; // rbx
  int v76; // r9d
  void *v77; // rcx
  unsigned __int8 v79[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  int v81[2]; // [rsp+80h] [rbp-80h] BYREF
  bool v82; // [rsp+88h] [rbp-78h] BYREF
  char v83; // [rsp+89h] [rbp-77h]
  unsigned __int8 v84[6]; // [rsp+8Ah] [rbp-76h] BYREF
  int v85[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v86; // [rsp+98h] [rbp-68h]
  void *lpMem; // [rsp+A0h] [rbp-60h]
  char v88; // [rsp+A8h] [rbp-58h]
  char v89; // [rsp+A9h] [rbp-57h]
  unsigned __int8 v90; // [rsp+AAh] [rbp-56h] BYREF
  unsigned __int8 v91[5]; // [rsp+ABh] [rbp-55h] BYREF
  unsigned __int64 v92; // [rsp+B0h] [rbp-50h] BYREF
  bool v93; // [rsp+B8h] [rbp-48h] BYREF
  bool v94; // [rsp+B9h] [rbp-47h] BYREF
  bool v95[6]; // [rsp+BAh] [rbp-46h] BYREF
  const char *v96; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v97; // [rsp+C8h] [rbp-38h]
  __int64 v98; // [rsp+D0h] [rbp-30h]
  __int64 v99; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v100; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v101; // [rsp+F0h] [rbp-10h]
  int v102; // [rsp+F8h] [rbp-8h]
  __int128 v103; // [rsp+100h] [rbp+0h]
  const char *v104; // [rsp+110h] [rbp+10h] BYREF
  __int64 v105; // [rsp+118h] [rbp+18h]
  __int64 v106; // [rsp+120h] [rbp+20h]
  __int64 v107; // [rsp+128h] [rbp+28h] BYREF
  __int128 v108; // [rsp+130h] [rbp+30h]
  __int128 v109; // [rsp+140h] [rbp+40h] BYREF
  void *v110; // [rsp+150h] [rbp+50h]
  unsigned __int64 *v111; // [rsp+160h] [rbp+60h] BYREF
  __int128 *v112; // [rsp+168h] [rbp+68h]
  _QWORD v113[4]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v114; // [rsp+190h] [rbp+90h] BYREF
  __int128 v115; // [rsp+198h] [rbp+98h] BYREF
  void *v116; // [rsp+1A8h] [rbp+A8h]
  __int64 v117; // [rsp+1B0h] [rbp+B0h]
  __int64 v118; // [rsp+1B8h] [rbp+B8h]
  __int64 v119; // [rsp+1C0h] [rbp+C0h]
  _QWORD v120[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v121[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _LUNICODE_STRING *v122; // [rsp+1F0h] [rbp+F0h]
  __int64 *v123; // [rsp+1F8h] [rbp+F8h]
  struct _LUNICODE_STRING *v124; // [rsp+200h] [rbp+100h]
  unsigned __int64 v125[10]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int64 v126[2]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v127; // [rsp+270h] [rbp+170h]
  __int128 v128; // [rsp+278h] [rbp+178h]
  const wchar_t *v129; // [rsp+288h] [rbp+188h]
  __int128 v130; // [rsp+290h] [rbp+190h] BYREF
  void *v131; // [rsp+2A0h] [rbp+1A0h]
  __int64 v132; // [rsp+2A8h] [rbp+1A8h]
  __int64 v133; // [rsp+2B0h] [rbp+1B0h]
  __int64 v134; // [rsp+2B8h] [rbp+1B8h]
  __int64 v135; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v136; // [rsp+2C8h] [rbp+1C8h]
  __int64 v137; // [rsp+2D0h] [rbp+1D0h]
  _QWORD v138[16]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int *v139; // [rsp+360h] [rbp+260h]

  v139 = a4;
  *a4 = 0;
  v110 = 0;
  v121[0] = 0;
  v96 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  LODWORD(v98) = -1073741595;
  memset(v125, 0, 72);
  v6 = 0;
  v7 = 0;
  v138[0] = 0;
  memset(&v138[6], 0, 72);
  v114 = 0;
  v115 = 0u;
  v116 = 0;
  v118 = 0;
  v117 = 0;
  v119 = 0;
  memset(v120, 0, sizeof(v120));
  v80 = 0;
  v86 = 0;
  *(_QWORD *)v85 = 0;
  lpMem = 0;
  v95[0] = 0;
  v109 = 0;
  if ( a3 )
  {
    if ( (*((_DWORD *)a3 + 1) & 0xFFFFFFFE) != 0 )
    {
      LODWORD(v97) = 2443;
LABEL_260:
      CComponentAccessor::~CComponentAccessor((CComponentAccessor *)&v114);
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v138);
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v121);
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v96);
      return (unsigned int)v98;
    }
    if ( *(_DWORD *)a3 < 0x20u )
    {
      LODWORD(v97) = 2444;
      goto LABEL_260;
    }
    v9 = (__int64 *)((char *)a3 + 16);
    if ( *((_QWORD *)a3 + 2) )
    {
      if ( !qword_180166950
        || (IsBaseIdentityHandleValidWithType = RtlIsBaseIdentityHandleValidWithType(*(_QWORD *)qword_180166950),
            v6 = v80,
            v7 = lpMem,
            !IsBaseIdentityHandleValidWithType) )
      {
        LODWORD(v97) = 2445;
        goto LABEL_260;
      }
    }
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppId,CDefAppIdCD,CDefAppIdTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)a3 + 1)) )
    {
      LODWORD(v97) = 2446;
      if ( v7 )
      {
        v86 = 0;
        *(_QWORD *)v85 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v7);
        v6 = v80;
      }
      if ( !v6 )
        goto LABEL_260;
      LODWORD(v110) = -1073741595;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      *(_QWORD *)&v109 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v6) )
      {
        DWORD2(v109) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v109);
        v11 = (int)v110;
        goto LABEL_257;
      }
      goto LABEL_255;
    }
    v12 = (_QWORD *)((char *)a3 + 24);
    if ( !(unsigned __int8)RtlIsIsolatedFilesystemObjectHandleValid(*((_QWORD *)a3 + 3)) )
    {
      LODWORD(v97) = 2447;
      if ( v14 )
      {
        v86 = 0;
        *(_QWORD *)v85 = 0;
        lpMem = 0;
        IsolationFreeStringRoutine(v14);
        v13 = v80;
      }
      if ( !v13 )
        goto LABEL_260;
      LODWORD(v101) = -1073741595;
      goto LABEL_19;
    }
    Windows::Isolation::Rtl::RtlTrace(
      0,
      (unsigned int)&Windows::Isolation::Rtl::Facility_IsolationComponentStore,
      (struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *)1,
      (unsigned int)"   Install Private Component Data:\n"
                    "      Definition AppId: {appid}\n"
                    "      ManifestPath: {mf}\n"
                    "      DefinitionIdentity: {defid}\n",
      (const char *const)3,
      (unsigned __int64)"appid",
      Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_APPID,
      (char *)a3 + 8,
      "mf",
      Windows::Isolation::Rtl::RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT,
      (char *)a3 + 24,
      "defid",
      Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_IDENTITY,
      v9);
    SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v17, *((_QWORD *)this + 96), &v80);
    if ( SystemIsolatedFilesystem < 0 )
      goto LABEL_24;
    v19 = 0;
    SystemIsolatedFilesystem = CApplicationAccessor::Attach(v121, *((_QWORD *)a3 + 1));
    if ( SystemIsolatedFilesystem < 0 )
      goto LABEL_33;
    v20 = (unsigned __int64 *)v123;
    v21 = *v123;
    if ( (unsigned __int64)*v123 > 1 )
    {
      v126[0] = 0;
      v130 = 0u;
      v131 = 0;
      v133 = 0;
      v132 = 0;
      v134 = 0;
      v136 = 0;
      v135 = 0;
      v137 = 0;
      SystemIsolatedFilesystem = CApplicationAccessor::Create(
                                   (CApplicationAccessor *)v126,
                                   v122,
                                   v21 - 1,
                                   (struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *const)v123[1],
                                   v124);
      if ( SystemIsolatedFilesystem < 0 )
        goto LABEL_32;
      v92 = v126[0];
      v111 = 0;
      SystemIsolatedFilesystem = BCL::HashTable::CTable<CCSDirectTransaction::CAppidTableTraits>::Find<Windows::Isolation::Rtl::_DEFINITION_APPID>(
                                   (char *)this + 344,
                                   &v92,
                                   &v111);
      if ( SystemIsolatedFilesystem < 0 )
        goto LABEL_32;
      v79[0] = 0;
      if ( !v111 )
      {
        SystemIsolatedFilesystem = CComponentMarkManager::IsApplicationMarked(
                                     (CCSDirectTransaction *)((char *)this + 3152),
                                     (const struct _LUNICODE_STRING *)&v130,
                                     (bool *)v79);
        if ( SystemIsolatedFilesystem < 0 )
        {
LABEL_32:
          CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v126);
          goto LABEL_33;
        }
        if ( !v79[0] )
        {
          LODWORD(v97) = 2519;
          CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v126);
LABEL_66:
          v30 = lpMem;
          if ( lpMem )
          {
            v86 = 0;
            *(_QWORD *)v85 = 0;
            lpMem = 0;
            IsolationFreeStringRoutine(v30);
          }
          if ( v80 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            LODWORD(v101) = -1073741595;
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v32 + 4))(*v32, v31);
              v33 = 0;
            }
            else
            {
              DWORD2(v100) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
              v33 = (int)v101;
            }
            if ( v33 < 0 )
              RaiseException(v33, 1u, 0, 0);
            v80 = 0;
          }
          goto LABEL_260;
        }
      }
      CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v126);
      v20 = (unsigned __int64 *)v123;
    }
    v26 = *v9;
    v89 = 0;
    if ( v26 )
    {
      v88 = 1;
    }
    else
    {
      v88 = 0;
      if ( v20 && *v20 )
        v26 = *(_QWORD *)(v20[1] + 8 * *v20 - 8);
      else
        v26 = 0;
      if ( *v20 > 1 )
      {
        SystemIsolatedFilesystem = CApplicationAccessor::Create(
                                     (CApplicationAccessor *)v138,
                                     v122,
                                     *v20 - 1,
                                     (struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *const)v20[1],
                                     v124);
        if ( SystemIsolatedFilesystem < 0 )
          goto LABEL_33;
        v27 = (const struct CApplicationAccessor *)v138;
        v89 = 1;
        goto LABEL_50;
      }
    }
    v27 = (const struct CApplicationAccessor *)v121;
LABEL_50:
    v28 = *((_QWORD *)this + 97);
    *((_QWORD *)&v100 + 1) = *v12;
    *(_QWORD *)v81 = 0;
    v101 = &g_LUNICODE_STRING__empty_;
    *(_QWORD *)&v100 = 48;
    v102 = 64;
    v103 = 0;
    SystemIsolatedFilesystem = RtlIsolatedFilesystemGetFileContents(v28, &v100, v85, 0);
    if ( SystemIsolatedFilesystem >= 0 )
    {
      SystemIsolatedFilesystem = RtlCompileCdfFromXmlBlob((int)v85, v29, (int)v81, 0, 0);
      if ( SystemIsolatedFilesystem >= 0 )
      {
        SystemIsolatedFilesystem = CComponentAccessor::Attach(&v114, *(_QWORD *)v81);
        if ( SystemIsolatedFilesystem >= 0 )
        {
          v79[0] = 0;
          SystemIsolatedFilesystem = RtlAreDefinitionIdentitiesEqual(0, v114, v26, v79);
          if ( SystemIsolatedFilesystem < 0 )
          {
            if ( *(_QWORD *)v81 )
            {
              CdfCloseHandle();
              *(_QWORD *)v81 = 0;
            }
            v77 = lpMem;
            if ( lpMem )
            {
              v86 = 0;
              *(_QWORD *)v85 = 0;
              lpMem = 0;
              IsolationFreeStringRoutine(v77);
            }
            if ( !v80 )
              goto LABEL_42;
            ++g_nRtlCloseIsolatedFilesystemHandle;
            LODWORD(v110) = -1073741595;
            *(_QWORD *)&v109 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              || !(unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
            {
              DWORD2(v109) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v109);
              v25 = (int)v110;
              goto LABEL_39;
            }
            goto LABEL_38;
          }
          if ( !v79[0] )
          {
            LODWORD(v97) = 2584;
            if ( *(_QWORD *)v81 )
            {
              CdfCloseHandle();
              *(_QWORD *)v81 = 0;
            }
            goto LABEL_66;
          }
          SystemIsolatedFilesystem = Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(
                                       v114,
                                       &g_LUNICODE_STRING_publicKeyToken,
                                       &v109);
          if ( SystemIsolatedFilesystem >= 0 )
          {
            v107 = 0;
            v106 = 0;
            v108 = 0;
            v34 = 0;
            v90 = 0;
            v91[0] = 0;
            v35 = 0;
            v93 = 0;
            v94 = 0;
            v105 = 0;
            v104 = 0;
            SystemIsolatedFilesystem = Windows::Cdf::Rtl::CCdfDataPointer::Attach(&v107, *(_QWORD *)v81);
            if ( SystemIsolatedFilesystem < 0 )
              goto LABEL_78;
            v79[0] = 0;
            v83 = 0;
            if ( !(_QWORD)v109 )
            {
              v49 = 0;
              goto LABEL_155;
            }
            v110 = 0;
            v109 = 0;
            SystemIsolatedFilesystem = Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(
                                         v114,
                                         &g_LUNICODE_STRING_version,
                                         &v109);
            if ( SystemIsolatedFilesystem < 0 )
            {
LABEL_78:
              Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
              if ( *(_QWORD *)v81 )
              {
                CdfCloseHandle();
                *(_QWORD *)v81 = 0;
              }
LABEL_24:
              v18 = lpMem;
              if ( lpMem )
              {
                v86 = 0;
                *(_QWORD *)v85 = 0;
                lpMem = 0;
                IsolationFreeStringRoutine(v18);
              }
              goto LABEL_112;
            }
            if ( !(_QWORD)v109 )
            {
              LODWORD(v97) = 2614;
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
              Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
              if ( *(_QWORD *)v81 )
              {
                CdfCloseHandle();
                *(_QWORD *)v81 = 0;
              }
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
              v13 = v80;
              if ( !v80 )
                goto LABEL_260;
              LODWORD(v101) = -1073741595;
LABEL_19:
              ++g_nRtlCloseIsolatedFilesystemHandle;
              *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( !v13 )
              {
LABEL_256:
                v11 = 0;
                goto LABEL_257;
              }
              if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                || !(unsigned __int8)RtlIsTypeSafeHandleValid(v13) )
              {
                DWORD2(v100) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
                v11 = (int)v101;
LABEL_257:
                if ( v11 < 0 )
                  RaiseException(v11, 1u, 0, 0);
                v80 = 0;
                goto LABEL_260;
              }
LABEL_255:
              (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
              goto LABEL_256;
            }
            if ( v88 || v89 )
            {
              SystemIsolatedFilesystem = CCSDirectTransaction::RetrieveComponentHashFromParentManifest(
                                           this,
                                           (const struct CComponentAccessor *)&v114,
                                           v27,
                                           (struct Windows::Rtl::CLBLOB *)&v104,
                                           &v90,
                                           v91,
                                           &v93);
              if ( SystemIsolatedFilesystem < 0 )
              {
                Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                if ( *(_QWORD *)v81 )
                {
                  CdfCloseHandle();
                  *(_QWORD *)v81 = 0;
                }
                Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                if ( v80 )
                {
                  ++g_nRtlCloseIsolatedFilesystemHandle;
                  LODWORD(v101) = -1073741595;
                  *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                  if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                    && (unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
                  {
                    (*((void (__fastcall **)(_QWORD, __int64))v37 + 4))(*v37, v36);
                    v38 = 0;
                  }
                  else
                  {
                    DWORD2(v100) = 292;
                    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
                    v38 = (int)v101;
                  }
                  if ( v38 < 0 )
                    RaiseException(v38, 1u, 0, 0);
                  v80 = 0;
                }
                goto LABEL_42;
              }
              v34 = v106;
              v19 = v104;
              v35 = v93;
            }
            SystemIsolatedFilesystem = CCSDirectTransaction::IsComponentInstalled(
                                         this,
                                         (const struct CComponentAccessor *)&v114,
                                         &v94);
            if ( SystemIsolatedFilesystem >= 0 )
            {
              if ( !v94 )
              {
                SystemIsolatedFilesystem = IsoWriteManifestAndCdf(
                                             v80,
                                             *((_QWORD *)this + 98),
                                             &v115,
                                             v85,
                                             *(_QWORD *)v81);
                if ( SystemIsolatedFilesystem < 0 )
                {
LABEL_109:
                  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                  Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                  if ( *(_QWORD *)v81 )
                  {
                    CdfCloseHandle();
                    *(_QWORD *)v81 = 0;
                  }
                  goto LABEL_111;
                }
                goto LABEL_152;
              }
              if ( v88 )
              {
                v83 = 1;
                if ( v35 )
                {
                  v97 = 0;
                  v96 = 0;
                  v98 = 0;
                  v84[0] = 0;
                  v82 = 0;
                  v79[0] = 0;
                  SystemIsolatedFilesystem = CCSDirectTransaction::RetrieveComponentHashFromHierarchy(
                                               this,
                                               (const struct CComponentAccessor *)&v114,
                                               (struct Windows::Rtl::CLBLOB *)&v96,
                                               v84,
                                               (unsigned __int8 *)&v82,
                                               (bool *)v79);
                  if ( SystemIsolatedFilesystem < 0 )
                  {
LABEL_108:
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                    goto LABEL_109;
                  }
                  if ( v79[0] && v84[0] == v90 && v82 == v91[0] && v96 && v96 == v19 )
                  {
                    for ( i = 0; i < (unsigned __int64)v96; ++i )
                    {
                      if ( *(_BYTE *)(i + v98) != *(_BYTE *)(i + v34) )
                        break;
                    }
                    v83 = i < (unsigned __int64)v96 ? v83 : 0;
                  }
                  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                }
LABEL_152:
                SystemIsolatedFilesystem = CCSDirectTransaction::HasSubstructureBeenCreated(this, v27, v95);
                if ( SystemIsolatedFilesystem < 0 )
                  goto LABEL_109;
                v49 = 1;
                v79[0] = 1;
LABEL_155:
                v50 = v88;
                if ( v88 )
                {
                  v82 = 0;
                  v99 = 0;
                  v101 = 0;
                  v100 = 0;
                  SystemIsolatedFilesystem = Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(
                                               v114,
                                               &g_LUNICODE_STRING_name,
                                               &v100);
                  if ( SystemIsolatedFilesystem < 0 )
                  {
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                    Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
LABEL_111:
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
LABEL_112:
                    if ( !v80 )
                      goto LABEL_42;
                    ++g_nRtlCloseIsolatedFilesystemHandle;
                    *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                    LODWORD(v101) = -1073741595;
                    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                      && (unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
                    {
                      (*((void (__fastcall **)(_QWORD, __int64))v40 + 4))(*v40, v39);
LABEL_116:
                      v41 = 0;
                      goto LABEL_117;
                    }
                    DWORD2(v100) = 292;
                    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
                    v41 = (int)v101;
                    goto LABEL_117;
                  }
                  SystemIsolatedFilesystem = CCSDirectTransaction::IsPrivateComponentInstalled(
                                               this,
                                               v27,
                                               (const struct CComponentAccessor *)&v114,
                                               &v82);
                  if ( SystemIsolatedFilesystem < 0 )
                  {
LABEL_160:
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                    Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                    if ( !v80 )
                      goto LABEL_42;
                    ++g_nRtlCloseIsolatedFilesystemHandle;
                    v96 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                    LODWORD(v98) = -1073741595;
                    if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v80) )
                    {
                      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
                      {
                        (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                                                + 32))(
                          *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
                          v51);
                        goto LABEL_116;
                      }
                      LODWORD(v97) = 293;
                      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                        &v96,
                        &v96);
                    }
                    else
                    {
                      LODWORD(v97) = 292;
                      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v96);
                    }
                    v41 = v98;
LABEL_117:
                    if ( v41 < 0 )
                      RaiseException(v41, 1u, 0, 0);
LABEL_119:
                    v80 = 0;
                    goto LABEL_42;
                  }
                  if ( !v82 )
                  {
                    SystemIsolatedFilesystem = CCSDirectTransaction::GetPrivateAssemblyInstallDirectory(
                                                 this,
                                                 v27,
                                                 v114,
                                                 &v99);
                    if ( SystemIsolatedFilesystem < 0 )
                      goto LABEL_160;
                    if ( !v49 || v83 )
                    {
                      SystemIsolatedFilesystem = IsoWriteManifestAndCdf(v80, v99, &v100, v85, *(_QWORD *)v81);
                      if ( SystemIsolatedFilesystem < 0 )
                        goto LABEL_196;
                    }
                    else
                    {
                      v97 = 0;
                      v96 = 0;
                      v98 = 0;
                      memset(v113, 0, 24);
                      v52 = (const char *)v100;
                      *((_QWORD *)&v109 + 1) = &v111;
                      v111 = (unsigned __int64 *)0xC0000043C0000035LL;
                      *(_QWORD *)&v109 = 2;
                      v110 = 0;
                      SystemIsolatedFilesystem = RtlAllocateLUnicodeString(v100 + 18, &v96);
                      if ( SystemIsolatedFilesystem < 0
                        || (SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(&v100, &v96),
                            SystemIsolatedFilesystem < 0) )
                      {
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v113);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                        Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                        if ( !v80 )
                          goto LABEL_42;
                        ++g_nRtlCloseIsolatedFilesystemHandle;
                        LODWORD(v106) = -1073741595;
                        v104 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                        if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v80) )
                        {
                          LODWORD(v105) = 292;
                          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v104);
LABEL_178:
                          v48 = v106;
                          goto LABEL_181;
                        }
                        if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
                        {
                          LODWORD(v105) = 293;
                          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                            &v104,
                            &v104);
                          goto LABEL_178;
                        }
                        (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                                                + 32))(
                          *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
                          v53);
LABEL_180:
                        v48 = 0;
LABEL_181:
                        if ( v48 < 0 )
                          RaiseException(v48, 1u, 0, 0);
                        goto LABEL_191;
                      }
                      SystemIsolatedFilesystem = RtlAllocateLUnicodeString(v115 + 18, v113);
                      if ( SystemIsolatedFilesystem < 0
                        || (SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(&v115, v113),
                            SystemIsolatedFilesystem < 0)
                        || (SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(
                                                         &g_LUNICODE_STRING__dot_manifest,
                                                         v113),
                            SystemIsolatedFilesystem < 0)
                        || (SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(
                                                         &g_LUNICODE_STRING__dot_manifest,
                                                         &v96),
                            SystemIsolatedFilesystem < 0)
                        || (Windows::Isolation::Rtl::CIsolatedObjectAttributes::CIsolatedObjectAttributes(
                              &v100,
                              v99,
                              &v96),
                            v54 = Windows::Isolation::Rtl::CIsolatedObjectAttributes::CIsolatedObjectAttributes(
                                    v126,
                                    *((_QWORD *)this + 98),
                                    v113),
                            SystemIsolatedFilesystem = RtlIsolatedFilesystemCreateHardLinkOrCopyFile(&v109, v80, v54),
                            SystemIsolatedFilesystem < 0) )
                      {
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v113);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
LABEL_189:
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                        Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                        if ( !v80 )
                          goto LABEL_42;
                        RtlCloseIsolatedFilesystemHandle();
LABEL_191:
                        v80 = 0;
                        goto LABEL_42;
                      }
                      v113[0] = v115;
                      v96 = v52;
                      SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(
                                                   &g_LUNICODE_STRING__dot_cdf_dash_ms,
                                                   v113);
                      if ( SystemIsolatedFilesystem < 0
                        || (SystemIsolatedFilesystem = RtlAppendLUnicodeStringToLUnicodeString(
                                                         &g_LUNICODE_STRING__dot_cdf_dash_ms,
                                                         &v96),
                            SystemIsolatedFilesystem < 0)
                        || (Windows::Isolation::Rtl::CIsolatedObjectAttributes::CIsolatedObjectAttributes(
                              v126,
                              v99,
                              &v96),
                            v55 = Windows::Isolation::Rtl::CIsolatedObjectAttributes::CIsolatedObjectAttributes(
                                    &v100,
                                    *((_QWORD *)this + 98),
                                    v113),
                            SystemIsolatedFilesystem = RtlIsolatedFilesystemCreateHardLinkOrCopyFile(&v109, v80, v55),
                            SystemIsolatedFilesystem < 0) )
                      {
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v113);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
LABEL_196:
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                        Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                        if ( !v80 )
                          goto LABEL_42;
                        RtlCloseIsolatedFilesystemHandle();
                        goto LABEL_119;
                      }
                      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v113);
                      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                    }
                  }
                  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v99);
                }
                v56 = *(_QWORD *)v85;
                v58 = *(_QWORD *)Windows::Cdf::Rtl::CCdfDataPointer::operator _LBLOB const *(&v107);
                if ( v56 + v58 < v56 || v56 + v58 < v58 )
                {
                  SystemIsolatedFilesystem = -1073741675;
                  goto LABEL_189;
                }
                v111 = (unsigned __int64 *)(v56 + v58);
                if ( !v49 )
                {
                  v73 = (void *)*((_QWORD *)v27 + 8);
                  v109 = *((_OWORD *)v27 + 3);
                  v110 = v73;
                  SystemIsolatedFilesystem = CCSDirectTransaction::UpdateSizeInfoInRecorder(
                                               v58,
                                               v57,
                                               (int)this + 3608,
                                               1,
                                               (__int64)&v109,
                                               (__int64)&v111);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_205;
                  v92 = 0;
                  v111 = v125;
                  v112 = &v115;
                  SystemIsolatedFilesystem = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                          &v92,
                                                          &v99);
                  if ( SystemIsolatedFilesystem >= 0 )
                  {
                    v75 = (_QWORD *)v92;
                    SystemIsolatedFilesystem = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                                 v92,
                                                 v74,
                                                 2,
                                                 &v111,
                                                 g_LUNICODE_STRING_identity,
                                                 v120);
                    if ( SystemIsolatedFilesystem >= 0 )
                    {
                      v92 = 0;
                      v75[12] = *((_QWORD *)this + 85);
                      v75[11] = (char *)this + 672;
                      **((_QWORD **)this + 85) = v75 + 11;
                      *((_QWORD *)this + 85) = v75 + 11;
                      v75[13] = (char *)this + 672;
                      ++*((_QWORD *)this + 88);
                      BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
LABEL_233:
                      v126[0] = 0;
                      v130 = 0u;
                      v131 = 0;
                      v133 = 0;
                      v132 = 0;
                      v134 = 0;
                      v136 = 0;
                      v135 = 0;
                      v137 = 0;
                      v111 = *(unsigned __int64 **)CApplicationAccessor::GetDeploymentIdentity(v121, &v92);
                      SystemIsolatedFilesystem = CApplicationAccessor::Create(
                                                   (CApplicationAccessor *)v126,
                                                   v122,
                                                   1u,
                                                   (struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *const)&v111,
                                                   v124);
                      if ( SystemIsolatedFilesystem < 0
                        || v49
                        && (SystemIsolatedFilesystem = CComponentMarkManager::GenericAddSingleMark<CComponentAccessor>(
                                                         (int)this + 3152,
                                                         6,
                                                         (unsigned int)&v114,
                                                         v76,
                                                         (__int64)&v130,
                                                         (__int64)&v135),
                            SystemIsolatedFilesystem < 0)
                        || *v123 != 1
                        && (SystemIsolatedFilesystem = CComponentMarkManager::GenericAddSingleMark<CApplicationAccessor>(
                                                         (int)this + 3152,
                                                         6,
                                                         (unsigned int)v121,
                                                         v76,
                                                         (__int64)&v130,
                                                         (__int64)&v135),
                            SystemIsolatedFilesystem < 0) )
                      {
                        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v126);
                      }
                      else
                      {
                        CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v126);
                        v111 = (unsigned __int64 *)v121[0];
                        SystemIsolatedFilesystem = BCL::HashTable::CTable<CCSDirectTransaction::CAppidTableTraits>::FindOrInsertIfNotPresent<Windows::Isolation::Rtl::_DEFINITION_APPID,int>(
                                                     (char *)this + 344,
                                                     &v111);
                        if ( SystemIsolatedFilesystem >= 0 )
                        {
                          SystemIsolatedFilesystem = 0;
                          *v139 = 1;
                        }
                      }
                      goto LABEL_205;
                    }
                  }
                  goto LABEL_212;
                }
                v109 = v115;
                v110 = v116;
                SystemIsolatedFilesystem = CCSDirectTransaction::UpdateSizeInfoInRecorder(
                                             v58,
                                             v57,
                                             (int)this + 3280,
                                             0,
                                             (__int64)&v109,
                                             (__int64)&v111);
                if ( SystemIsolatedFilesystem < 0 )
                  goto LABEL_205;
                SystemIsolatedFilesystem = CCSDirectTransaction::WriteAssemblyIdentityIntoHierarchy(
                                             this,
                                             (const struct CComponentAccessor *)&v114);
                if ( SystemIsolatedFilesystem < 0 )
                  goto LABEL_205;
                if ( !v50 && !v89 )
                  goto LABEL_224;
                if ( v93 && !v94 )
                {
                  v92 = 0;
                  v111 = (unsigned __int64 *)&v115;
                  SystemIsolatedFilesystem = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                          &v92,
                                                          &v99);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v61 = (_QWORD *)v92;
                  SystemIsolatedFilesystem = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                               v92,
                                               v60,
                                               1,
                                               &v111,
                                               g_LUNICODE_STRING_DigestValue,
                                               &v104);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v62 = (char *)this + 672;
                  v92 = 0;
                  v61[12] = *((_QWORD *)this + 85);
                  v61[11] = (char *)this + 672;
                  **((_QWORD **)this + 85) = v61 + 11;
                  *((_QWORD *)this + 85) = v61 + 11;
                  v61[13] = (char *)this + 672;
                  ++*((_QWORD *)this + 88);
                  BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
                  v92 = 0;
                  v110 = &v90;
                  *(_QWORD *)&v109 = 1;
                  *((_QWORD *)&v109 + 1) = 1;
                  SystemIsolatedFilesystem = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                          &v92,
                                                          &v99);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v64 = (_QWORD *)v92;
                  SystemIsolatedFilesystem = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                               v92,
                                               v63,
                                               1,
                                               &v111,
                                               g_LUNICODE_STRING_Transform,
                                               &v109);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v64[12] = *((_QWORD *)this + 85);
                  v64[11] = v62;
                  v65 = (_QWORD *)*((_QWORD *)this + 85);
                  v92 = 0;
                  *v65 = v64 + 11;
                  *((_QWORD *)this + 85) = v64 + 11;
                  v64[13] = v62;
                  ++*((_QWORD *)this + 88);
                  BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
                  v92 = 0;
                  v110 = v91;
                  *(_QWORD *)&v109 = 1;
                  *((_QWORD *)&v109 + 1) = 1;
                  SystemIsolatedFilesystem = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                          &v92,
                                                          &v99);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v67 = (_QWORD *)v92;
                  SystemIsolatedFilesystem = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                               v92,
                                               v66,
                                               1,
                                               &v111,
                                               g_LUNICODE_STRING_DigestMethod,
                                               &v109);
                  if ( SystemIsolatedFilesystem < 0 )
                    goto LABEL_212;
                  v67[12] = *((_QWORD *)this + 85);
                  v67[11] = v62;
                  v68 = (_QWORD *)*((_QWORD *)this + 85);
                  v92 = 0;
                  *v68 = v67 + 11;
                  *((_QWORD *)this + 85) = v67 + 11;
                  v67[13] = v62;
                  ++*((_QWORD *)this + 88);
                  BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
                  v49 = v79[0];
                }
                if ( !v50 || !v83 )
                  goto LABEL_224;
                v92 = 0;
                v111 = v125;
                v95[0] = 1;
                v112 = &v115;
                *(_QWORD *)&v109 = 1;
                v110 = v95;
                *((_QWORD *)&v109 + 1) = 1;
                SystemIsolatedFilesystem = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                        &v92,
                                                        &v99);
                if ( SystemIsolatedFilesystem >= 0 )
                {
                  v70 = (_QWORD *)v92;
                  SystemIsolatedFilesystem = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                               v92,
                                               v69,
                                               2,
                                               &v111,
                                               g_LUNICODE_STRING_TreatAsPrivateComponent,
                                               &v109);
                  if ( SystemIsolatedFilesystem >= 0 )
                  {
                    v92 = 0;
                    v70[12] = *((_QWORD *)this + 85);
                    v70[11] = (char *)this + 672;
                    **((_QWORD **)this + 85) = v70 + 11;
                    *((_QWORD *)this + 85) = v70 + 11;
                    v70[13] = (char *)this + 672;
                    ++*((_QWORD *)this + 88);
                    BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
LABEL_224:
                    if ( !*((_QWORD *)this + 89) )
                      goto LABEL_233;
                    v71 = *((_OWORD *)this + 45);
                    v72 = *((_QWORD *)this + 92);
                    v130 = v115;
                    *(_OWORD *)v126 = v71;
                    v127 = v72;
                    v128 = g_LUNICODE_STRING__bslash_;
                    v97 = 0;
                    v96 = 0;
                    v98 = 0;
                    v129 = L"\\";
                    v131 = v116;
                    SystemIsolatedFilesystem = Windows::Rtl::Concatenate(
                                                 (Windows::Rtl *)&v96,
                                                 (struct _LUNICODE_STRING *)3,
                                                 (unsigned __int64)v126,
                                                 v59);
                    if ( SystemIsolatedFilesystem >= 0 )
                    {
                      SystemIsolatedFilesystem = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const char **))(**((_QWORD **)this + 89) + 8LL))(
                                                   *((_QWORD *)this + 89),
                                                   *(_QWORD *)v81,
                                                   &v96);
                      if ( SystemIsolatedFilesystem >= 0 )
                      {
                        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
                        goto LABEL_233;
                      }
                    }
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
LABEL_205:
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
                    Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCDFTraits>::Close(v81);
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
                    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v80);
                    goto LABEL_42;
                  }
                }
LABEL_212:
                BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v92);
                goto LABEL_205;
              }
              if ( !v89 || !v35 )
                goto LABEL_152;
              v43 = 0;
              v97 = 0;
              v96 = 0;
              v98 = 0;
              v84[0] = 0;
              v79[0] = 0;
              v82 = 0;
              SystemIsolatedFilesystem = CCSDirectTransaction::RetrieveComponentHashFromHierarchy(
                                           this,
                                           (const struct CComponentAccessor *)&v114,
                                           (struct Windows::Rtl::CLBLOB *)&v96,
                                           v84,
                                           v79,
                                           &v82);
              if ( SystemIsolatedFilesystem < 0 )
                goto LABEL_108;
              if ( v82 && v84[0] == v90 && v79[0] == v91[0] )
              {
                if ( v96 == v19 )
                {
                  if ( v96 )
                  {
                    v44 = 0;
                    do
                    {
                      if ( *(_BYTE *)(v44 + v98) != *(_BYTE *)(v44 + v34) )
                        break;
                      v44 = (unsigned int)(v44 + 1);
                    }
                    while ( (unsigned int)v44 < (unsigned __int64)v96 );
                    v43 = (unsigned int)v44 < (unsigned __int64)v96;
                  }
                }
                else
                {
                  v43 = 1;
                }
              }
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v96);
              if ( !v43 )
                goto LABEL_152;
              SystemIsolatedFilesystem = -1073741735;
              Windows::ErrorHandling::COM::ReportNtErrorOrigination(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp",
                (const char *)0xAB9,
                -1073741735,
                v45);
            }
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v104);
            Windows::Cdf::Rtl::CCdfDataPointer::~CCdfDataPointer((Windows::Cdf::Rtl::CCdfDataPointer *)&v107);
            if ( *(_QWORD *)v81 )
            {
              CdfCloseHandle();
              *(_QWORD *)v81 = 0;
            }
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)v85);
            if ( !v80 )
              goto LABEL_42;
            ++g_nRtlCloseIsolatedFilesystemHandle;
            *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            LODWORD(v101) = -1073741595;
            if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              || !(unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
            {
              DWORD2(v100) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
              v48 = (int)v101;
              goto LABEL_181;
            }
            (*((void (__fastcall **)(_QWORD, __int64))v47 + 4))(*v47, v46);
            goto LABEL_180;
          }
        }
      }
    }
    if ( *(_QWORD *)v81 )
    {
      CdfCloseHandle();
      *(_QWORD *)v81 = 0;
    }
LABEL_33:
    v22 = lpMem;
    if ( lpMem )
    {
      v86 = 0;
      *(_QWORD *)v85 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v22);
    }
    if ( !v80 )
      goto LABEL_42;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    *(_QWORD *)&v100 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v101) = -1073741595;
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v80) )
    {
      DWORD2(v100) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v100);
      v25 = (int)v101;
      goto LABEL_39;
    }
LABEL_38:
    (*((void (__fastcall **)(_QWORD, __int64))v24 + 4))(*v24, v23);
    v25 = 0;
LABEL_39:
    if ( v25 < 0 )
      RaiseException(v25, 1u, 0, 0);
    v80 = 0;
    goto LABEL_42;
  }
  LODWORD(v97) = 2442;
  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v96);
  SystemIsolatedFilesystem = v98;
LABEL_42:
  CComponentAccessor::~CComponentAccessor((CComponentAccessor *)&v114);
  CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v138);
  CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v121);
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800c13e4  push    rbp
0x1800c13e6  push    rbx
0x1800c13e7  push    rsi
0x1800c13e8  push    rdi
0x1800c13e9  push    r12
0x1800c13eb  push    r13
0x1800c13ed  push    r14
0x1800c13ef  push    r15
0x1800c13f1  lea     rbp, [rsp-278h]
0x1800c13f9  sub     rsp, 378h
0x1800c1400  mov     rax, cs:__security_cookie
0x1800c1407  xor     rax, rsp
0x1800c140a  mov     [rbp+2B0h+var_48], rax
0x1800c1411  xor     esi, esi
0x1800c1413  mov     [rbp+2B0h+var_50], r9
0x1800c141a  xor     eax, eax
0x1800c141c  mov     [r9], esi
0x1800c141f  mov     [rbp+2B0h+var_260], rax
0x1800c1423  mov     r14, rcx
0x1800c1426  mov     [rbp+2B0h+var_1D0], rsi
0x1800c142d  lea     rcx, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c1434  mov     [rbp+2B0h+var_2F0], rcx
0x1800c1438  mov     r15d, 0C00000E5h
0x1800c143e  mov     dword ptr [rbp+2B0h+var_2E0], r15d
0x1800c1442  xorps   xmm0, xmm0
0x1800c1445  mov     [rbp+2B0h+var_198], rsi
0x1800c144c  mov     rbx, r8
0x1800c144f  mov     [rbp+2B0h+var_1A0], rsi
0x1800c1456  mov     r10d, esi
0x1800c1459  mov     [rbp+2B0h+var_190], rsi
0x1800c1460  mov     r11d, esi
0x1800c1463  mov     [rbp+2B0h+var_180], rsi
0x1800c146a  mov     [rbp+2B0h+var_188], rsi
0x1800c1471  mov     [rbp+2B0h+var_178], rsi
0x1800c1478  mov     [rbp+2B0h+var_168], rsi
0x1800c147f  mov     [rbp+2B0h+var_170], rsi
0x1800c1486  mov     [rbp+2B0h+var_160], rsi
0x1800c148d  mov     [rbp+2B0h+var_D0], rsi
0x1800c1494  mov     [rbp+2B0h+var_98], rsi
0x1800c149b  mov     [rbp+2B0h+var_A0], rsi
0x1800c14a2  mov     [rbp+2B0h+var_90], rsi
0x1800c14a9  mov     [rbp+2B0h+var_80], rsi
0x1800c14b0  mov     [rbp+2B0h+var_88], rsi
0x1800c14b7  mov     [rbp+2B0h+var_78], rsi
0x1800c14be  mov     [rbp+2B0h+var_68], rsi
0x1800c14c5  mov     [rbp+2B0h+var_70], rsi
0x1800c14cc  mov     [rbp+2B0h+var_60], rsi
0x1800c14d3  mov     [rbp+2B0h+var_220], rsi
0x1800c14da  mov     qword ptr [rbp+2B0h+var_218+8], rsi
0x1800c14e1  mov     qword ptr [rbp+2B0h+var_218], rsi
0x1800c14e8  mov     [rbp+2B0h+var_208], rsi
0x1800c14ef  mov     [rbp+2B0h+var_1F8], rsi
0x1800c14f6  mov     [rbp+2B0h+var_200], rsi
0x1800c14fd  mov     [rbp+2B0h+var_1F0], rsi
0x1800c1504  mov     [rbp+2B0h+var_1E0], rsi
0x1800c150b  mov     [rbp+2B0h+var_1E8], rsi
0x1800c1512  mov     [rbp+2B0h+var_1D8], rsi
0x1800c1519  mov     [rsp+3B0h+var_338], rsi
0x1800c151e  mov     [rbp+2B0h+var_318], rsi
0x1800c1522  mov     qword ptr [rbp+2B0h+var_320], rsi
0x1800c1526  mov     [rbp+2B0h+lpMem], rsi
0x1800c152a  mov     [rbp+2B0h+var_2F6], sil
0x1800c152e  movups  [rbp+2B0h+var_270], xmm0
0x1800c1532  test    r8, r8
0x1800c1535  jnz     loc_1800C15EF
0x1800c153b  lea     rcx, [rbp+2B0h+var_2F0]
0x1800c153f  mov     dword ptr [rbp+2B0h+var_2E8], 98Ah
0x1800c1546  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c154b  mov     rcx, [rbp+2B0h+lpMem]; lpMem
0x1800c154f  test    rcx, rcx
0x1800c1552  jz      short loc_1800C1565
0x1800c1554  mov     [rbp+2B0h+var_318], rsi
0x1800c1558  mov     qword ptr [rbp+2B0h+var_320], rsi
0x1800c155c  mov     [rbp+2B0h+lpMem], rsi
0x1800c1560  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c1565  mov     r10, [rsp+3B0h+var_338]
0x1800c156a  test    r10, r10
0x1800c156d  jz      short loc_1800C15D2
0x1800c156f  mov     edi, 1
0x1800c1574  mov     dword ptr [rbp+2B0h+var_2C0], r15d
0x1800c1578  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c157f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c1586  mov     qword ptr [rbp+2B0h+var_2D0], rax
0x1800c158a  test    r10, r10
0x1800c158d  jz      short loc_1800C15B9
0x1800c158f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c1596  test    r11, r11
0x1800c1599  jz      short loc_1800C15DA
0x1800c159b  mov     rdx, r11
0x1800c159e  mov     rcx, r10
0x1800c15a1  call    RtlIsTypeSafeHandleValid
0x1800c15a6  test    al, al
0x1800c15a8  jz      short loc_1800C15DA
0x1800c15aa  mov     ecx, [r11]
0x1800c15ad  mov     rdx, r10
0x1800c15b0  mov     rax, [r11+20h]
0x1800c15b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c15b9  mov     ecx, esi; dwExceptionCode
0x1800c15bb  test    ecx, ecx
0x1800c15bd  jns     short loc_1800C15CD
0x1800c15bf  xor     r9d, r9d; lpArguments
0x1800c15c2  xor     r8d, r8d; nNumberOfArguments
0x1800c15c5  mov     edx, edi; dwExceptionFlags
0x1800c15c7  call    cs:__imp_RaiseException
0x1800c15cd  mov     [rsp+3B0h+var_338], rsi
0x1800c15d2  mov     esi, dword ptr [rbp+2B0h+var_2E0]
0x1800c15d5  jmp     loc_1800C198C
0x1800c15da  mov     dword ptr [rbp+2B0h+var_2D0+8], 124h
0x1800c15e1  lea     rcx, [rbp+2B0h+var_2D0]
0x1800c15e5  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c15ea  mov     ecx, dword ptr [rbp+2B0h+var_2C0]
0x1800c15ed  jmp     short loc_1800C15BB
0x1800c15ef  test    dword ptr [r8+4], 0FFFFFFFEh
0x1800c15f7  jz      short loc_1800C1605
0x1800c15f9  mov     dword ptr [rbp+2B0h+var_2E8], 98Bh
0x1800c1600  jmp     loc_1800C2E50
0x1800c1605  cmp     dword ptr [r8], 20h ; ' '
0x1800c1609  jnb     short loc_1800C1617
0x1800c160b  mov     dword ptr [rbp+2B0h+var_2E8], 98Ch
0x1800c1612  jmp     loc_1800C2E50
0x1800c1617  lea     r12, [r8+10h]
0x1800c161b  mov     rdx, [r12]
0x1800c161f  test    rdx, rdx
0x1800c1622  jz      short loc_1800C1694
0x1800c1624  mov     rcx, cs:qword_180166950
0x1800c162b  test    rcx, rcx
0x1800c162e  jz      short loc_1800C1645
0x1800c1630  mov     rcx, [rcx]
0x1800c1633  call    RtlIsBaseIdentityHandleValidWithType
0x1800c1638  mov     r10, [rsp+3B0h+var_338]
0x1800c163d  mov     r11, [rbp+2B0h+lpMem]
0x1800c1641  test    al, al
0x1800c1643  jnz     short loc_1800C1694
0x1800c1645  mov     dword ptr [rbp+2B0h+var_2E8], 98Dh
0x1800c164c  test    r11, r11
0x1800c164f  jz      short loc_1800C166A
0x1800c1651  mov     rcx, r11; lpMem
0x1800c1654  mov     [rbp+2B0h+var_318], rsi
0x1800c1658  mov     qword ptr [rbp+2B0h+var_320], rsi
0x1800c165c  mov     [rbp+2B0h+lpMem], rsi
0x1800c1660  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c1665  mov     r10, [rsp+3B0h+var_338]
0x1800c166a  test    r10, r10
0x1800c166d  jz      loc_1800C2E50
0x1800c1673  mov     dword ptr [rbp+2B0h+var_2C0], r15d
0x1800c1677  jmp     loc_1800C16FE
0x1800c167c  mov     dword ptr [rbp+2B0h+var_2D0+8], 124h
0x1800c1683  lea     rcx, [rbp+2B0h+var_2D0]
0x1800c1687  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c168c  mov     ecx, dword ptr [rbp+2B0h+var_2C0]
0x1800c168f  jmp     loc_1800C2E39
0x1800c1694  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCDefAppId@@VCDefAppIdCD@@VCDefAppIdTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppId,CDefAppIdCD,CDefAppIdTraits>::ms_ptti
0x1800c169b  test    rdx, rdx
0x1800c169e  jz      loc_1800C2DBF
0x1800c16a4  lea     r15, [rbx+8]
0x1800c16a8  mov     rcx, [r15]
0x1800c16ab  call    RtlIsTypeSafeHandleValid
0x1800c16b0  test    al, al
0x1800c16b2  jz      loc_1800C2DB9
0x1800c16b8  lea     r13, [rbx+18h]
0x1800c16bc  mov     rcx, [r13+0]
0x1800c16c0  call    RtlIsIsolatedFilesystemObjectHandleValid
0x1800c16c5  test    al, al
0x1800c16c7  jnz     short loc_1800C1746
0x1800c16c9  mov     dword ptr [rbp+2B0h+var_2E8], 98Fh
0x1800c16d0  test    r11, r11
0x1800c16d3  jz      short loc_1800C16EE
0x1800c16d5  mov     rcx, r11; lpMem
0x1800c16d8  mov     [rbp+2B0h+var_318], rsi
0x1800c16dc  mov     qword ptr [rbp+2B0h+var_320], rsi
0x1800c16e0  mov     [rbp+2B0h+lpMem], rsi
0x1800c16e4  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c16e9  mov     r10, [rsp+3B0h+var_338]
0x1800c16ee  test    r10, r10
0x1800c16f1  jz      loc_1800C2E50
0x1800c16f7  mov     dword ptr [rbp+2B0h+var_2C0], 0C00000E5h
0x1800c16fe  mov     edi, 1
0x1800c1703  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c170a  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c1711  mov     qword ptr [rbp+2B0h+var_2D0], rax
0x1800c1715  test    r10, r10
0x1800c1718  jz      loc_1800C2E37
0x1800c171e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c1725  test    r11, r11
0x1800c1728  jz      loc_1800C167C
0x1800c172e  mov     rdx, r11
0x1800c1731  mov     rcx, r10
0x1800c1734  call    RtlIsTypeSafeHandleValid
0x1800c1739  test    al, al
0x1800c173b  jz      loc_1800C167C
0x1800c1741  jmp     loc_1800C2E28
0x1800c1746  mov     [rsp+3B0h+var_348], r12
0x1800c174b  lea     rax, ?RtlTraceFormat_PCDEFINITION_IDENTITY@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_IDENTITY(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x1800c1752  mov     [rsp+3B0h+var_350], rax
0x1800c1757  lea     r9, aInstallPrivate_0; "   Install Private Component Data:\n   "...
0x1800c175e  lea     rax, aDefid; "defid"
0x1800c1765  mov     edi, 1
0x1800c176a  mov     [rsp+3B0h+var_358], rax
0x1800c176f  lea     rdx, ?Facility_IsolationComponentStore@Rtl@Isolation@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1800c1776  mov     [rsp+3B0h+var_360], r13
0x1800c177b  lea     rax, ?RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x1800c1782  mov     [rsp+3B0h+var_368], rax
0x1800c1787  mov     r8d, edi; struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *
0x1800c178a  lea     rax, aMf; "mf"
0x1800c1791  xor     ecx, ecx; this
0x1800c1793  mov     [rsp+3B0h+var_370], rax
0x1800c1798  lea     rax, ?RtlTraceFormat_PCDEFINITION_APPID@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_APPID(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x1800c179f  mov     [rsp+3B0h+var_378], r15
0x1800c17a4  mov     [rsp+3B0h+var_380], rax
0x1800c17a9  lea     rax, aAppid; "appid"
0x1800c17b0  mov     [rsp+3B0h+var_388], rax; unsigned __int64
0x1800c17b5  mov     [rsp+3B0h+var_390], 3; char *
0x1800c17be  call    ?RtlTrace@Rtl@Isolation@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@KQEBD_KZZ; Windows::Isolation::Rtl::RtlTrace(ulong,Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *,ulong,char const * const,unsigned __int64,...)
0x1800c17c3  mov     rdx, [r14+300h]
0x1800c17ca  lea     r8, [rsp+3B0h+var_338]
0x1800c17cf  call    RtlGetSystemIsolatedFilesystem
0x1800c17d4  xor     ebx, ebx
0x1800c17d6  mov     esi, eax
0x1800c17d8  test    eax, eax
0x1800c17da  jns     short loc_1800C17FF
0x1800c17dc  mov     rcx, [rbp+2B0h+lpMem]; lpMem
0x1800c17e0  test    rcx, rcx
0x1800c17e3  jz      loc_1800C1F24
0x1800c17e9  mov     [rbp+2B0h+var_318], rbx
0x1800c17ed  mov     qword ptr [rbp+2B0h+var_320], rbx
0x1800c17f1  mov     [rbp+2B0h+lpMem], rbx
0x1800c17f5  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c17fa  jmp     loc_1800C1F24
0x1800c17ff  mov     rdx, [r15]
0x1800c1802  lea     rcx, [rbp+2B0h+var_1D0]
0x1800c1809  call    ?Attach@CApplicationAccessor@@QEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; CApplicationAccessor::Attach(Windows::Isolation::Rtl::_DEFINITION_APPID)
0x1800c180e  xor     r15d, r15d
0x1800c1811  mov     esi, eax
0x1800c1813  test    eax, eax
0x1800c1815  js      loc_1800C1906
0x1800c181b  mov     r9, [rbp+2B0h+var_1B8]
0x1800c1822  mov     r8, [r9]
0x1800c1825  cmp     r8, rdi
0x1800c1828  jbe     loc_1800C19FC
0x1800c182e  mov     rax, [rbp+2B0h+var_1B0]
0x1800c1835  lea     rcx, [rbp+2B0h+var_150]; this
0x1800c183c  mov     rdx, [rbp+2B0h+var_1C0]; struct _LUNICODE_STRING *
0x1800c1843  dec     r8; unsigned __int64
0x1800c1846  mov     [rbp+2B0h+var_150], r15
0x1800c184d  mov     qword ptr [rbp+2B0h+var_120+8], r15
0x1800c1854  mov     qword ptr [rbp+2B0h+var_120], r15
0x1800c185b  mov     [rbp+2B0h+var_110], r15
0x1800c1862  mov     [rbp+2B0h+var_100], r15
0x1800c1869  mov     [rbp+2B0h+var_108], r15
0x1800c1870  mov     [rbp+2B0h+var_F8], r15
0x1800c1877  mov     [rbp+2B0h+var_E8], r15
0x1800c187e  mov     [rbp+2B0h+var_F0], r15
0x1800c1885  mov     [rbp+2B0h+var_E0], r15
0x1800c188c  mov     r9, [r9+8]; struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *
0x1800c1890  mov     [rsp+3B0h+var_390], rax; struct _LUNICODE_STRING *
0x1800c1895  call    ?Create@CApplicationAccessor@@QEAAJPEBU_LUNICODE_STRING@@_KQEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@0@Z; CApplicationAccessor::Create(_LUNICODE_STRING const *,unsigned __int64,Windows::Isolation::Rtl::_DEFINITION_IDENTITY * const,_LUNICODE_STRING const *)
0x1800c189a  mov     esi, eax
0x1800c189c  test    eax, eax
0x1800c189e  js      short loc_1800C18FA
0x1800c18a0  mov     rax, [rbp+2B0h+var_150]
0x1800c18a7  lea     rcx, [r14+158h]
0x1800c18ae  lea     r8, [rbp+2B0h+var_250]
0x1800c18b2  mov     [rbp+2B0h+var_300], rax
0x1800c18b6  lea     rdx, [rbp+2B0h+var_300]
0x1800c18ba  mov     [rbp+2B0h+var_250], r15
0x1800c18be  call    ??$Find@U_DEFINITION_APPID@Rtl@Isolation@Windows@@@?$CTable@VCAppidTableTraits@CCSDirectTransaction@@@HashTable@BCL@@QEAAJAEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEAPEAH@Z; BCL::HashTable::CTable<CCSDirectTransaction::CAppidTableTraits>::Find<Windows::Isolation::Rtl::_DEFINITION_APPID>(Windows::Isolation::Rtl::_DEFINITION_APPID &,int * &)
0x1800c18c3  mov     esi, eax
0x1800c18c5  test    eax, eax
0x1800c18c7  js      short loc_1800C18FA
0x1800c18c9  mov     [rsp+3B0h+var_340], r15b
0x1800c18ce  cmp     [rbp+2B0h+var_250], r15
0x1800c18d2  jnz     loc_1800C19E9
0x1800c18d8  lea     rcx, [r14+0C50h]; this
0x1800c18df  lea     r8, [rsp+3B0h+var_340]; bool *
0x1800c18e4  lea     rdx, [rbp+2B0h+var_120]; struct _LUNICODE_STRING *
0x1800c18eb  call    ?IsApplicationMarked@CComponentMarkManager@@QEAAJPEBU_LUNICODE_STRING@@AEA_N@Z; CComponentMarkManager::IsApplicationMarked(_LUNICODE_STRING const *,bool &)
0x1800c18f0  mov     esi, eax
0x1800c18f2  test    eax, eax
0x1800c18f4  jns     loc_1800C19CA
0x1800c18fa  lea     rcx, [rbp+2B0h+var_150]; this
0x1800c1901  call    ??1CApplicationAccessor@@QEAA@XZ; CApplicationAccessor::~CApplicationAccessor(void)
0x1800c1906  mov     rcx, [rbp+2B0h+lpMem]; lpMem
0x1800c190a  test    rcx, rcx
0x1800c190d  jz      short loc_1800C1920
0x1800c190f  mov     [rbp+2B0h+var_318], r15
0x1800c1913  mov     qword ptr [rbp+2B0h+var_320], r15
0x1800c1917  mov     [rbp+2B0h+lpMem], r15
0x1800c191b  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c1920  mov     r10, [rsp+3B0h+var_338]
0x1800c1925  test    r10, r10
0x1800c1928  jz      short loc_1800C198C
0x1800c192a  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c1931  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c1938  mov     qword ptr [rbp+2B0h+var_2D0], rax
0x1800c193c  mov     dword ptr [rbp+2B0h+var_2C0], 0C00000E5h
0x1800c1943  test    r10, r10
0x1800c1946  jz      short loc_1800C1972
0x1800c1948  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c194f  test    r11, r11
0x1800c1952  jz      short loc_1800C19B5
  ... truncated ...
```
