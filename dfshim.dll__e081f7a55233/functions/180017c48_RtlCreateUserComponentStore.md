# RtlCreateUserComponentStore

- ea: `0x180017c48`
- end: `0x1800187ea`
- name: `RtlCreateUserComponentStore`
- size: `2978`
- prototype: ``
- caller_count: `4`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013600`
- `0x18001bebc`
- `0x180038398`
- `0x18003940c`

## callees

- `0x1800125c8`
- `0x180012950`
- `0x180012b1c`
- `0x180013de8`
- `0x1800165fc`
- `0x1800172e0`
- `0x180017400`
- `0x180017514`
- `0x180017530`
- `0x180017580`
- `0x18001766c`
- `0x180017868`
- `0x180017908`
- `0x1800179a8`
- `0x180017c48`
- `0x18001d478`
- `0x18001ddec`
- `0x18001ed80`
- `0x18002717c`
- `0x18002dc0c`
- `0x18003fed8`
- `0x18003ff04`
- `0x180040020`
- `0x18004011c`
- `0x180040f70`
- `0x180040f9c`
- `0x1800416a8`
- `0x18004f2dc`
- `0x180053eb8`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017de0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017e4a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017eaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800183ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800184e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800185fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018682`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017de0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017e4a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017eaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800183ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800184e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800185fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018682`

## string_xrefs

- `0x180017d78`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800182ce`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800183a1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18001856c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180018734`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180017c72`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csu_core.cpp`

## pseudocode

```c
__int64 __fastcall RtlCreateUserComponentStore(__int64 a1, void *a2, _QWORD *a3)
{
  int System; // r14d
  __int64 v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // r10
  unsigned int *v10; // r11
  signed int v11; // ecx
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  BOOL v22; // ebx
  __int64 v23; // rbx
  bool v24; // zf
  __int64 *v25; // rax
  int v26; // ecx
  __int64 v27; // r10
  unsigned int *v28; // r11
  signed int v29; // ecx
  __int64 v30; // r10
  __int64 v31; // r10
  unsigned int *v32; // r11
  signed int v33; // ecx
  __int64 v34; // r10
  unsigned int *v35; // r11
  signed int v36; // ecx
  __int64 v37; // r10
  signed int v38; // ecx
  __int64 v39; // r10
  signed int v40; // ecx
  __int64 v41; // r10
  __int128 v43; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+40h] [rbp-C0h]
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h]
  void *lpMem; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h]
  void *v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-60h]
  __int64 *v57; // [rsp+A8h] [rbp-58h]
  int v58; // [rsp+B0h] [rbp-50h]
  __int128 v59; // [rsp+B8h] [rbp-48h]
  _QWORD v60[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h]
  _DWORD v62[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v63[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-8h]
  _QWORD v65[3]; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v66[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v67; // [rsp+140h] [rbp+40h]

  v55 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csu_core.cpp";
  LODWORD(v57) = -1073741595;
  if ( !a3 )
  {
    LODWORD(v56) = 278;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v55);
    return (unsigned int)v57;
  }
  *a3 = 0;
  if ( qword_1801668C0 )
  {
    System = RtlDuplicateComponentStoreHandle(qword_1801668C0, a3);
    if ( System < 0 )
      return (unsigned int)System;
    return 0;
  }
  v47 = 0;
  v67 = 0;
  v45 = 0;
  v48 = 0;
  v60[1] = v62;
  v61 = 0;
  v46 = 0;
  v53 = 0;
  v52 = 0;
  v54 = 0;
  v50 = 0;
  v49 = 0;
  lpMem = 0;
  memset(v66, 0, sizeof(v66));
  v62[0] = -1073741766;
  v62[1] = -1073741772;
  v60[0] = 2;
  System = RtlGetSystem(0, &v47);
  if ( System < 0 )
    goto LABEL_6;
  System = RtlGetSystemIsolatedRegistry(v6, v47, &v45);
  if ( System < 0 )
    goto LABEL_6;
  System = RtlGetSystemIsolatedFilesystem(v18, v47, &v46);
  if ( System < 0 )
    goto LABEL_6;
  System = RtlpGetFullRegistryKeyPathOfUserComponentStoreLocation(a2, (struct _LUNICODE_STRING *)&v52);
  if ( System < 0
    || (System = RtlpGetUserComponentStoreLocationInFilesystem(v45, a2, &v49), System < 0)
    || (v57 = (__int64 *)&v49,
        v56 = 0,
        v55 = 48,
        v58 = 64,
        v59 = 0,
        System = RtlIsolatedFilesystemQueryAttributesFile(v46, &v55, v66, v60),
        System < 0) )
  {
LABEL_6:
    v7 = lpMem;
    if ( lpMem )
    {
      v50 = 0;
      v49 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v7);
    }
    v8 = v54;
    if ( v54 )
    {
      v53 = 0;
      v52 = 0;
      v54 = 0;
      IsolationFreeStringRoutine(v8);
    }
  }
  else
  {
    if ( (int)v61 < 0 )
      goto LABEL_70;
    BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v63);
    *(_QWORD *)&v43 = lpMem;
    *((_QWORD *)&v43 + 1) = v49 >> 1;
    System = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
               v63,
               &v43);
    if ( System >= 0 )
    {
      if ( v63[0] && v64 && *(_WORD *)(v63[0] + 2 * v64 - 2) == 92
        || (System = BCL::Nt::CUnicodeStringBuffer::Append((BCL::Nt::CUnicodeStringBuffer *)v63, 0x5Cu), System >= 0) )
      {
        *(_QWORD *)&v43 = L"manifests";
        *((_QWORD *)&v43 + 1) = 9;
        System = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                   v63,
                   &v43);
        if ( System >= 0 )
        {
          v55 = 48;
          v65[0] = 2 * v64;
          v65[1] = 2 * v64;
          v65[2] = v63[0];
          v57 = v65;
          v56 = 0;
          v58 = 64;
          v59 = 0;
          System = RtlIsolatedFilesystemQueryAttributesFile(v46, &v55, v66, v60);
          if ( System < 0 )
          {
            BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v63);
LABEL_53:
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
            goto LABEL_10;
          }
          v22 = (int)v61 < 0;
          BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v63);
          if ( !v22 )
          {
            v57 = &v52;
            v55 = 48;
            v56 = 0;
            v58 = 64;
            v59 = 0;
            System = RtlIsolatedRegistryOpenKey(v45, (unsigned int)&v48, 131097, (unsigned int)&v55, (__int64)v60);
            if ( System < 0 )
              goto LABEL_53;
            if ( (int)v61 >= 0 )
            {
              v23 = 0;
              while ( 1 )
              {
                v24 = off_1801367E0[v23] == 0;
                v56 = v48;
                *(_QWORD *)&v43 = 0;
                v25 = &g_LUNICODE_STRING__empty_;
                v55 = 48;
                if ( !v24 )
                  v25 = (__int64 *)off_1801367E0[v23];
                v57 = v25;
                v58 = 64;
                v59 = 0;
                System = RtlIsolatedRegistryOpenKey(v45, (unsigned int)&v43, 131097, (unsigned int)&v55, (__int64)v60);
                if ( System < 0 )
                  break;
                if ( (int)v61 < 0 )
                {
                  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v43);
                  goto LABEL_70;
                }
                Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v43);
                if ( (unsigned __int64)++v23 >= 8 )
                  goto LABEL_63;
              }
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v43);
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
              if ( v46 )
              {
                ++g_nRtlCloseIsolatedFilesystemHandle;
                LODWORD(v57) = -1073741595;
                v55 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                  && (unsigned __int8)RtlIsTypeSafeHandleValid(v46) )
                {
                  (*((void (__fastcall **)(_QWORD, __int64))v32 + 4))(*v32, v31);
                  v33 = 0;
                }
                else
                {
                  LODWORD(v56) = 292;
                  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v55);
                  v33 = (int)v57;
                }
                if ( v33 < 0 )
                  RaiseException(v33, 1u, 0, 0);
                v46 = 0;
              }
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
              if ( !v45 )
                goto LABEL_104;
              LODWORD(v57) = -1073741595;
              v55 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v45) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v35 + 4))(*v35, v34);
LABEL_100:
                v36 = 0;
                goto LABEL_101;
              }
              LODWORD(v56) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v55);
              v36 = (int)v57;
              goto LABEL_101;
            }
          }
LABEL_70:
          LODWORD(v61) = 0;
          System = Windows::Isolation::Implementation::Rtl::RtlIsolatedRegistryDeleteKeyRecursively(v19, v45, &v52);
          if ( System < 0 )
          {
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
            if ( v46 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              LODWORD(v57) = -1073741595;
              v55 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v46) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v28 + 4))(*v28, v27);
                v29 = 0;
              }
              else
              {
                LODWORD(v56) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v55);
                v29 = (int)v57;
              }
              if ( v29 < 0 )
                RaiseException(v29, 1u, 0, 0);
              v46 = 0;
            }
            Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
            if ( !v45 )
              goto LABEL_104;
            v44 = -1073741595;
            *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v45) )
            {
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
              {
                (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                                        + 32))(
                  *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
                  v30);
                goto LABEL_100;
              }
              DWORD2(v43) = 293;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v43,
                &v43);
            }
            else
            {
              DWORD2(v43) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
            }
            v36 = v44;
LABEL_101:
            if ( v36 < 0 )
              RaiseException(v36, 1u, 0, 0);
            v45 = 0;
LABEL_104:
            if ( !v47 )
              return (unsigned int)System;
            v55 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            LODWORD(v57) = -1073741595;
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v47) )
            {
              goto LABEL_27;
            }
            LODWORD(v56) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v55);
            v17 = (int)v57;
LABEL_29:
            if ( v17 < 0 )
              RaiseException(v17, 1u, 0, 0);
            return (unsigned int)System;
          }
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
          System = RtlpGetFullRegistryKeyPathOfUserComponentStoreLocation(a2, (struct _LUNICODE_STRING *)&v52);
          if ( System >= 0 )
          {
            System = RtlpGetUserComponentStoreLocationInFilesystem(v45, a2, &v49);
            if ( System >= 0 )
            {
              System = RtlpSetupUserCustomStoreStructure(v46, v45, &v52, &v49);
              if ( System >= 0 )
              {
LABEL_63:
                v43 = xmmword_180141308;
                System = RtlCreateDirectComponentStore(
                           v26,
                           v47,
                           (unsigned int)&v49,
                           (unsigned int)&v52,
                           (__int64)&v43,
                           (__int64)a3);
                if ( System >= 0 )
                {
                  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
                  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
                  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v46);
                  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
                  if ( v45 )
                  {
                    RtlCloseIsolatedRegistryHandle();
                    v45 = 0;
                  }
                  if ( v47 )
                    RtlCloseSystemHandle();
                  return 0;
                }
              }
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
              Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v46);
              Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
              if ( v45 )
              {
                RtlCloseIsolatedRegistryHandle();
                v45 = 0;
              }
              if ( v47 )
                RtlCloseSystemHandle();
              return (unsigned int)System;
            }
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
            Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
            if ( v46 )
            {
              RtlCloseIsolatedFilesystemHandle();
              v46 = 0;
            }
LABEL_119:
            Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
            if ( !v45 )
              goto LABEL_129;
            v44 = -1073741595;
            *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v45) )
            {
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
              {
                (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                                        + 32))(
                  *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
                  v39);
                v40 = 0;
                goto LABEL_126;
              }
              DWORD2(v43) = 293;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v43,
                &v43);
            }
            else
            {
              DWORD2(v43) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
            }
            v40 = v44;
LABEL_126:
            if ( v40 < 0 )
              RaiseException(v40, 1u, 0, 0);
            v45 = 0;
LABEL_129:
            if ( !v47 )
              return (unsigned int)System;
            v44 = -1073741595;
            *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::IsValid(v47) )
            {
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti )
              {
                (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
                                                        + 32))(
                  *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti,
                  v41);
                goto LABEL_28;
              }
              DWORD2(v43) = 293;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v43,
                &v43);
              goto LABEL_34;
            }
LABEL_33:
            DWORD2(v43) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
LABEL_34:
            v17 = v44;
            goto LABEL_29;
          }
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
          Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
          if ( !v46 )
            goto LABEL_119;
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v44 = -1073741595;
          *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v46) )
          {
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
            {
              (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                                      + 32))(
                *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
                v37);
              v38 = 0;
              goto LABEL_116;
            }
            DWORD2(v43) = 293;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
              &v43,
              &v43);
          }
          else
          {
            DWORD2(v43) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
          }
          v38 = v44;
LABEL_116:
          if ( v38 < 0 )
            RaiseException(v38, 1u, 0, 0);
          v46 = 0;
          goto LABEL_119;
        }
      }
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v63);
    v20 = lpMem;
    if ( lpMem )
    {
      v50 = 0;
      v49 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v20);
    }
    v21 = v54;
    if ( v54 )
    {
      v53 = 0;
      v52 = 0;
      v54 = 0;
      IsolationFreeStringRoutine(v21);
    }
  }
LABEL_10:
  if ( v46 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v44 = -1073741595;
    *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v46) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v10 + 4))(*v10, v9);
      v11 = 0;
    }
    else
    {
      DWORD2(v43) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
      v11 = v44;
    }
    if ( v11 < 0 )
      RaiseException(v11, 1u, 0, 0);
    v46 = 0;
  }
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v48);
  if ( v45 )
  {
    v44 = -1073741595;
    *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v45) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
      v14 = 0;
    }
    else
    {
      DWORD2(v43) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
      v14 = v44;
    }
    if ( v14 < 0 )
      RaiseException(v14, 1u, 0, 0);
    v45 = 0;
  }
  if ( v47 )
  {
    v44 = -1073741595;
    *(_QWORD *)&v43 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v47) )
    {
LABEL_27:
      (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
LABEL_28:
      v17 = 0;
      goto LABEL_29;
    }
    goto LABEL_33;
  }
  return (unsigned int)System;
}

```

## disassembly

```asm
0x180017c48  push    rbp
0x180017c4a  push    rbx
0x180017c4b  push    rsi
0x180017c4c  push    rdi
0x180017c4d  push    r12
0x180017c4f  push    r13
0x180017c51  push    r14
0x180017c53  push    r15
0x180017c55  lea     rbp, [rsp-58h]
0x180017c5a  sub     rsp, 158h
0x180017c61  mov     rax, cs:__security_cookie
0x180017c68  xor     rax, rsp
0x180017c6b  mov     [rbp+90h+var_48], rax
0x180017c6f  xor     r12d, r12d
0x180017c72  lea     rax, aOnecoreComNetf_89; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180017c79  mov     [rbp+90h+var_F8], rax
0x180017c7d  mov     r13d, 0C00000E5h
0x180017c83  mov     dword ptr [rbp+90h+var_E8], r13d
0x180017c87  mov     rsi, r8
0x180017c8a  mov     r15, rdx
0x180017c8d  test    r8, r8
0x180017c90  jz      loc_1800187B3
0x180017c96  mov     [r8], r12
0x180017c99  mov     rcx, cs:qword_1801668C0
0x180017ca0  test    rcx, rcx
0x180017ca3  jz      short loc_180017CBD
0x180017ca5  mov     rdx, r8
0x180017ca8  call    RtlDuplicateComponentStoreHandle
0x180017cad  mov     r14d, eax
0x180017cb0  test    eax, eax
0x180017cb2  jns     loc_180018283
0x180017cb8  jmp     loc_1800187C7
0x180017cbd  xor     eax, eax
0x180017cbf  mov     [rsp+190h+var_138], r12
0x180017cc4  mov     [rbp+90h+var_50], rax
0x180017cc8  lea     rdx, [rsp+190h+var_138]
0x180017ccd  xorps   xmm0, xmm0
0x180017cd0  mov     [rsp+190h+var_148], r12
0x180017cd5  lea     rax, [rbp+90h+var_B0]
0x180017cd9  mov     [rsp+190h+var_130], r12
0x180017cde  mov     [rbp+90h+var_C0], rax
0x180017ce2  xor     eax, eax
0x180017ce4  mov     [rbp+90h+var_B8], rax
0x180017ce8  mov     [rsp+190h+var_140], r12
0x180017ced  mov     [rbp+90h+var_108], r12
0x180017cf1  mov     [rbp+90h+var_110], r12
0x180017cf5  mov     [rbp+90h+var_100], r12
0x180017cf9  mov     [rsp+190h+var_120], r12
0x180017cfe  mov     [rsp+190h+var_128], r12
0x180017d03  mov     [rsp+190h+lpMem], r12
0x180017d08  movups  [rbp+90h+var_70], xmm0
0x180017d0c  mov     [rbp+90h+var_B0], 0C000003Ah
0x180017d13  movups  [rbp+90h+var_60], xmm0
0x180017d17  mov     [rbp+90h+var_AC], 0C0000034h
0x180017d1e  mov     [rbp+90h+var_C8], 2
0x180017d26  call    RtlGetSystem
0x180017d2b  mov     r14d, eax
0x180017d2e  test    eax, eax
0x180017d30  jns     loc_180017EF7
0x180017d36  mov     rcx, [rsp+190h+lpMem]; lpMem
0x180017d3b  test    rcx, rcx
0x180017d3e  jz      short loc_180017D54
0x180017d40  mov     [rsp+190h+var_120], r12
0x180017d45  mov     [rsp+190h+var_128], r12
0x180017d4a  mov     [rsp+190h+lpMem], r12
0x180017d4f  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180017d54  mov     rcx, [rbp+90h+var_100]; lpMem
0x180017d58  test    rcx, rcx
0x180017d5b  jz      short loc_180017D6E
0x180017d5d  mov     [rbp+90h+var_108], r12
0x180017d61  mov     [rbp+90h+var_110], r12
0x180017d65  mov     [rbp+90h+var_100], r12
0x180017d69  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180017d6e  mov     edi, 1
0x180017d73  mov     r10, [rsp+190h+var_140]
0x180017d78  lea     rbx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180017d7f  mov     esi, 124h
0x180017d84  test    r10, r10
0x180017d87  jz      short loc_180017DEB
0x180017d89  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180017d90  mov     [rsp+190h+var_150], r13d
0x180017d95  mov     qword ptr [rsp+190h+var_160], rbx
0x180017d9a  test    r10, r10
0x180017d9d  jz      short loc_180017DD1
0x180017d9f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180017da6  test    r11, r11
0x180017da9  jz      loc_180017EB5
0x180017daf  mov     rdx, r11
0x180017db2  mov     rcx, r10
0x180017db5  call    RtlIsTypeSafeHandleValid
0x180017dba  test    al, al
0x180017dbc  jz      loc_180017EB5
0x180017dc2  mov     ecx, [r11]
0x180017dc5  mov     rdx, r10
0x180017dc8  mov     rax, [r11+20h]
0x180017dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dd1  mov     ecx, r12d; dwExceptionCode
0x180017dd4  test    ecx, ecx
0x180017dd6  jns     short loc_180017DE6
0x180017dd8  xor     r9d, r9d; lpArguments
0x180017ddb  xor     r8d, r8d; nNumberOfArguments
0x180017dde  mov     edx, edi; dwExceptionFlags
0x180017de0  call    cs:__imp_RaiseException
0x180017de6  mov     [rsp+190h+var_140], r12
0x180017deb  lea     rcx, [rsp+190h+var_130]
0x180017df0  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x180017df5  mov     r10, [rsp+190h+var_148]
0x180017dfa  test    r10, r10
0x180017dfd  jz      short loc_180017E55
0x180017dff  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x180017e06  mov     [rsp+190h+var_150], r13d
0x180017e0b  mov     qword ptr [rsp+190h+var_160], rbx
0x180017e10  test    r11, r11
0x180017e13  jz      loc_180017ECC
0x180017e19  mov     rdx, r11
0x180017e1c  mov     rcx, r10
0x180017e1f  call    RtlIsTypeSafeHandleValid
0x180017e24  test    al, al
0x180017e26  jz      loc_180017ECC
0x180017e2c  mov     ecx, [r11]
0x180017e2f  mov     rdx, r10
0x180017e32  mov     rax, [r11+20h]
0x180017e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3b  mov     ecx, r12d; dwExceptionCode
0x180017e3e  test    ecx, ecx
0x180017e40  jns     short loc_180017E50
0x180017e42  xor     r9d, r9d; lpArguments
0x180017e45  xor     r8d, r8d; nNumberOfArguments
0x180017e48  mov     edx, edi; dwExceptionFlags
0x180017e4a  call    cs:__imp_RaiseException
0x180017e50  mov     [rsp+190h+var_148], r12
0x180017e55  mov     r10, [rsp+190h+var_138]
0x180017e5a  test    r10, r10
0x180017e5d  jz      loc_1800187C7
0x180017e63  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_SYSTEM@Rtl@Isolation@Windows@@VCSystem@2Implementation@34@VCSystemCD@2634@VCSystemImplTraits@2634@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_SYSTEM,Windows::Isolation::Implementation::Rtl::CSystem,Windows::Isolation::Implementation::Rtl::CSystemCD,Windows::Isolation::Implementation::Rtl::CSystemImplTraits>::ms_ptti
0x180017e6a  mov     [rsp+190h+var_150], r13d
0x180017e6f  mov     qword ptr [rsp+190h+var_160], rbx
0x180017e74  test    r11, r11
0x180017e77  jz      short loc_180017EE3
0x180017e79  mov     rdx, r11
0x180017e7c  mov     rcx, r10
0x180017e7f  call    RtlIsTypeSafeHandleValid
0x180017e84  test    al, al
0x180017e86  jz      short loc_180017EE3
0x180017e88  mov     ecx, [r11]
0x180017e8b  mov     rax, [r11+20h]
0x180017e8f  mov     rdx, r10
0x180017e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e97  mov     ecx, r12d; dwExceptionCode
0x180017e9a  test    ecx, ecx
0x180017e9c  jns     loc_1800187C7
0x180017ea2  xor     r9d, r9d; lpArguments
0x180017ea5  xor     r8d, r8d; nNumberOfArguments
0x180017ea8  mov     edx, edi; dwExceptionFlags
0x180017eaa  call    cs:__imp_RaiseException
0x180017eb0  jmp     loc_1800187C7
0x180017eb5  mov     dword ptr [rsp+190h+var_160+8], esi
0x180017eb9  lea     rcx, [rsp+190h+var_160]
0x180017ebe  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180017ec3  mov     ecx, [rsp+190h+var_150]
0x180017ec7  jmp     loc_180017DD4
0x180017ecc  mov     dword ptr [rsp+190h+var_160+8], esi
0x180017ed0  lea     rcx, [rsp+190h+var_160]
0x180017ed5  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180017eda  mov     ecx, [rsp+190h+var_150]
0x180017ede  jmp     loc_180017E3E
0x180017ee3  mov     dword ptr [rsp+190h+var_160+8], esi
0x180017ee7  lea     rcx, [rsp+190h+var_160]
0x180017eec  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180017ef1  mov     ecx, [rsp+190h+var_150]
0x180017ef5  jmp     short loc_180017E9A
0x180017ef7  mov     rdx, [rsp+190h+var_138]
0x180017efc  lea     r8, [rsp+190h+var_148]
0x180017f01  call    RtlGetSystemIsolatedRegistry
0x180017f06  mov     r14d, eax
0x180017f09  test    eax, eax
0x180017f0b  js      loc_180017D36
0x180017f11  mov     rdx, [rsp+190h+var_138]
0x180017f16  lea     r8, [rsp+190h+var_140]
0x180017f1b  call    RtlGetSystemIsolatedFilesystem
0x180017f20  mov     r14d, eax
0x180017f23  test    eax, eax
0x180017f25  js      loc_180017D36
0x180017f2b  lea     rdx, [rbp+90h+var_110]; struct _LUNICODE_STRING *
0x180017f2f  mov     rcx, r15; void *
0x180017f32  call    ?RtlpGetFullRegistryKeyPathOfUserComponentStoreLocation@@YAJPEAXAEAU_LUNICODE_STRING@@@Z; RtlpGetFullRegistryKeyPathOfUserComponentStoreLocation(void *,_LUNICODE_STRING &)
0x180017f37  mov     r14d, eax
0x180017f3a  test    eax, eax
0x180017f3c  js      loc_180017D36
0x180017f42  mov     rcx, [rsp+190h+var_148]
0x180017f47  lea     r8, [rsp+190h+var_128]
0x180017f4c  mov     rdx, r15
0x180017f4f  call    ?RtlpGetUserComponentStoreLocationInFilesystem@@YAJU_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@PEAXAEAU_LUNICODE_STRING@@@Z; RtlpGetUserComponentStoreLocationInFilesystem(Windows::Isolation::Rtl::_ISOLATED_REGISTRY,void *,_LUNICODE_STRING &)
0x180017f54  mov     r14d, eax
0x180017f57  test    eax, eax
0x180017f59  js      loc_180017D36
0x180017f5f  mov     rcx, [rsp+190h+var_140]
0x180017f64  lea     rax, [rsp+190h+var_128]
0x180017f69  xorps   xmm0, xmm0
0x180017f6c  mov     [rbp+90h+var_E8], rax
0x180017f70  mov     ebx, 30h ; '0'
0x180017f75  mov     [rbp+90h+var_F0], r12
0x180017f79  lea     r9, [rbp+90h+var_C8]
0x180017f7d  mov     [rbp+90h+var_F8], rbx
0x180017f81  lea     r8, [rbp+90h+var_70]
0x180017f85  mov     [rbp+90h+var_E0], 40h ; '@'
0x180017f8c  lea     rdx, [rbp+90h+var_F8]
0x180017f90  movdqu  [rbp+90h+var_D8], xmm0
0x180017f95  call    RtlIsolatedFilesystemQueryAttributesFile
0x180017f9a  mov     r14d, eax
0x180017f9d  test    eax, eax
0x180017f9f  js      loc_180017D36
0x180017fa5  lea     edi, [rbx-2Fh]
0x180017fa8  cmp     dword ptr [rbp+90h+var_B8], r12d
0x180017fac  jl      loc_180018290
0x180017fb2  lea     rcx, [rbp+90h+var_A8]; this
0x180017fb6  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x180017fbb  mov     rcx, [rsp+190h+lpMem]
0x180017fc0  lea     rdx, [rsp+190h+var_160]
0x180017fc5  mov     rax, [rsp+190h+var_128]
0x180017fca  shr     rax, 1
0x180017fcd  mov     qword ptr [rsp+190h+var_160], rcx
0x180017fd2  lea     rcx, [rbp+90h+var_A8]
0x180017fd6  mov     qword ptr [rsp+190h+var_160+8], rax
0x180017fdb  call    ??$public_Assign@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x180017fe0  mov     r14d, eax
0x180017fe3  test    eax, eax
0x180017fe5  jns     short loc_180018031
0x180017fe7  lea     rcx, [rbp+90h+var_A8]; this
0x180017feb  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x180017ff0  mov     rcx, [rsp+190h+lpMem]; lpMem
0x180017ff5  test    rcx, rcx
0x180017ff8  jz      short loc_18001800E
0x180017ffa  mov     [rsp+190h+var_120], r12
0x180017fff  mov     [rsp+190h+var_128], r12
0x180018004  mov     [rsp+190h+lpMem], r12
0x180018009  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18001800e  mov     rcx, [rbp+90h+var_100]; lpMem
0x180018012  test    rcx, rcx
0x180018015  jz      loc_180017D73
0x18001801b  mov     [rbp+90h+var_108], r12
0x18001801f  mov     [rbp+90h+var_110], r12
0x180018023  mov     [rbp+90h+var_100], r12
0x180018027  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18001802c  jmp     loc_180017D73
0x180018031  mov     rax, [rbp+90h+var_A8]
0x180018035  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001803a  test    rax, rax
0x18001803d  jz      short loc_18001804F
0x18001803f  mov     rcx, [rbp+90h+var_98]
0x180018043  test    rcx, rcx
0x180018046  jz      short loc_18001804F
0x180018048  cmp     [rax+rcx*2-2], dx
0x18001804d  jz      short loc_18001805F
0x18001804f  lea     rcx, [rbp+90h+var_A8]; this
0x180018053  call    ?Append@CUnicodeStringBuffer@Nt@BCL@@QEAAJG@Z; BCL::Nt::CUnicodeStringBuffer::Append(ushort)
0x180018058  mov     r14d, eax
0x18001805b  test    eax, eax
0x18001805d  js      short loc_180017FE7
0x18001805f  mov     rax, cs:off_180136D58; "manifests"
0x180018066  lea     rdx, [rsp+190h+var_160]
0x18001806b  lea     rcx, [rbp+90h+var_A8]
0x18001806f  mov     qword ptr [rsp+190h+var_160], rax
0x180018074  mov     qword ptr [rsp+190h+var_160+8], 9
0x18001807d  call    ??$public_Append@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x180018082  mov     r14d, eax
0x180018085  test    eax, eax
0x180018087  js      loc_180017FE7
0x18001808d  mov     rax, [rbp+90h+var_98]
0x180018091  lea     r9, [rbp+90h+var_C8]
0x180018095  mov     rcx, [rsp+190h+var_140]
0x18001809a  lea     r8, [rbp+90h+var_70]
0x18001809e  add     rax, rax
0x1800180a1  mov     [rbp+90h+var_F8], rbx
0x1800180a5  mov     [rbp+90h+var_88], rax
0x1800180a9  lea     rdx, [rbp+90h+var_F8]
0x1800180ad  mov     [rbp+90h+var_80], rax
0x1800180b1  xorps   xmm0, xmm0
0x1800180b4  mov     rax, [rbp+90h+var_A8]
0x1800180b8  mov     [rbp+90h+var_78], rax
0x1800180bc  lea     rax, [rbp+90h+var_88]
0x1800180c0  mov     [rbp+90h+var_E8], rax
0x1800180c4  mov     [rbp+90h+var_F0], r12
0x1800180c8  mov     [rbp+90h+var_E0], 40h ; '@'
0x1800180cf  movdqu  [rbp+90h+var_D8], xmm0
0x1800180d4  call    RtlIsolatedFilesystemQueryAttributesFile
0x1800180d9  lea     rcx, [rbp+90h+var_A8]; this
0x1800180dd  mov     r14d, eax
0x1800180e0  test    eax, eax
0x1800180e2  jns     short loc_180018101
0x1800180e4  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800180e9  lea     rcx, [rsp+190h+var_128]; this
0x1800180ee  call    ??1CLUNICODE_STRING@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING(void)
0x1800180f3  lea     rcx, [rbp+90h+var_110]; this
0x1800180f7  call    ??1CLUNICODE_STRING@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING(void)
0x1800180fc  jmp     loc_180017D73
0x180018101  cmp     dword ptr [rbp+90h+var_B8], r12d
0x180018105  mov     ebx, r12d
0x180018108  cmovl   ebx, edi
0x18001810b  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
  ... truncated ...
```
