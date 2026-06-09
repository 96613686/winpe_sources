# CCSDirectTransaction::InstallComponentFile(ulong,Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_ const *,ulong &)

- ea: `0x1800c03a8`
- end: `0x1800c0e31`
- name: `?InstallComponentFile@CCSDirectTransaction@@IEAAJKPEBU_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_@Rtl@Implementation@Isolation@Windows@@AEAK@Z`
- size: `2697`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, unsigned int, const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_ *, unsigned int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c9140`

## callees

- `0x180012b1c`
- `0x180013de8`
- `0x180013fd4`
- `0x180015418`
- `0x180018b30`
- `0x18001de74`
- `0x180028ce4`
- `0x18002f954`
- `0x18003f260`
- `0x18003f904`
- `0x18003fae0`
- `0x180040020`
- `0x180048470`
- `0x18004f2dc`
- `0x180050f7c`
- `0x180052364`
- `0x1800bbbc8`
- `0x1800bc2fc`
- `0x1800bdf30`
- `0x1800be06c`
- `0x1800bfb4c`
- `0x1800c03a8`
- `0x1800c5ee0`
- `0x1800c8b40`
- `0x1800c8c08`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0654`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c06a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0ab7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0b90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0dc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0654`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c06a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0ab7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0b90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c0dc4`

## string_xrefs

- `0x1800c060b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c0853`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c0a5d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c0b3f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c0c86`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c0d77`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c03da`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`
- `0x1800c09dd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::InstallComponentFile(
        CCSDirectTransaction *this,
        __int64 a2,
        const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_ *a3,
        unsigned int *a4)
{
  const struct _LUNICODE_STRING *v7; // r12
  int ComponentManifest; // esi
  _QWORD *v9; // rbx
  __int64 v10; // r10
  __int64 v11; // r10
  unsigned int *v12; // r11
  signed int v13; // ecx
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // r8
  __int64 v17; // r10
  unsigned int *v18; // r11
  signed int v19; // ecx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // r10
  unsigned int *v26; // r11
  signed int v27; // ecx
  _QWORD *v28; // r14
  __int64 v29; // r10
  unsigned int *v30; // r11
  signed int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // r10
  unsigned int *v34; // r11
  signed int v35; // ecx
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  bool v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h]
  void *lpMem; // [rsp+68h] [rbp-98h]
  int v43; // [rsp+70h] [rbp-90h]
  __int128 v44; // [rsp+78h] [rbp-88h]
  _QWORD *v45; // [rsp+88h] [rbp-78h] BYREF
  const char *v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v47; // [rsp+98h] [rbp-68h]
  unsigned int v48; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h]
  bool *v52; // [rsp+C0h] [rbp-40h]
  int v53; // [rsp+C8h] [rbp-38h]
  __int128 v54; // [rsp+D0h] [rbp-30h]
  __int128 v55; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-10h]
  __int128 v57; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v58; // [rsp+108h] [rbp+8h]
  _QWORD *v59; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v60[9]; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v61[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v62; // [rsp+168h] [rbp+68h]
  __int128 v63; // [rsp+178h] [rbp+78h] BYREF

  v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  v48 = -1073741595;
  v49 = 0;
  v59 = 0;
  memset(v60, 0, sizeof(v60));
  v39 = 0;
  v45 = 0;
  v38 = 0;
  v37 = 0;
  v63 = 0;
  if ( !a3 )
  {
    LODWORD(v47) = 4011;
LABEL_122:
    Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v63);
    CComponentAccessor::~CComponentAccessor((CComponentAccessor *)&v59);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
    return v48;
  }
  if ( *(_DWORD *)a3 < 0x30u )
  {
    LODWORD(v47) = 4012;
    goto LABEL_122;
  }
  if ( (*((_DWORD *)a3 + 1) & 0xFFFFFFFE) != 0 )
  {
    LODWORD(v47) = 4013;
    goto LABEL_122;
  }
  if ( !qword_180166950 || !(unsigned __int8)RtlIsBaseIdentityHandleValidWithType(*(_QWORD *)qword_180166950) )
  {
    LODWORD(v47) = 4014;
    goto LABEL_122;
  }
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT,Windows::Isolation::Fs::Private::CFsobj,Windows::Isolation::Fs::Private::FSOBJ_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsobjTraits>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)a3 + 2)) )
  {
    LODWORD(v47) = 4015;
    goto LABEL_122;
  }
  v7 = (const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_ *)((char *)a3 + 24);
  if ( !(unsigned __int8)RtlIsLUnicodeStringValid((char *)a3 + 24) )
  {
    LODWORD(v47) = 4016;
    goto LABEL_122;
  }
  ComponentManifest = CComponentAccessor::Attach(&v59, *((_QWORD *)a3 + 1));
  if ( ComponentManifest >= 0 )
  {
    ComponentManifest = CCSDirectTransaction::GetComponentManifest(
                          this,
                          (const struct CComponentAccessor *)&v59,
                          (struct Windows::Cdf::Rtl::_CDF *)&v45);
    if ( ComponentManifest >= 0 )
    {
      v9 = v45;
      if ( !v45 )
      {
        LODWORD(v47) = 4020;
        goto LABEL_122;
      }
      *a4 = 0;
      ComponentManifest = CCSDirectTransaction::IsFileInstalled(
                            this,
                            (const struct CComponentAccessor *)&v59,
                            (const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_FILE_ *)((char *)a3 + 24),
                            &v39);
      if ( ComponentManifest < 0 )
      {
        if ( v37 )
        {
          RtlCloseIsolatedFilesystemObjectHandle(v37);
          v37 = 0;
        }
        v10 = v38;
        if ( !v38 )
          goto LABEL_62;
LABEL_91:
        ++g_nRtlCloseIsolatedFilesystemHandle;
        v40 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        LODWORD(lpMem) = -1073741595;
        if ( v10 )
        {
          if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            || !(unsigned __int8)RtlIsTypeSafeHandleValid(v10) )
          {
            LODWORD(v41) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
            v31 = (int)lpMem;
            goto LABEL_96;
          }
          (*((void (__fastcall **)(_QWORD, __int64))v30 + 4))(*v30, v29);
        }
        v31 = 0;
LABEL_96:
        if ( v31 < 0 )
          RaiseException(v31, 1u, 0, 0);
        v38 = 0;
        goto LABEL_62;
      }
      if ( v39 )
      {
        ComponentManifest = 0;
        if ( v37 )
        {
          RtlCloseIsolatedFilesystemObjectHandle(v37);
          v37 = 0;
        }
        if ( v38 )
        {
          LODWORD(lpMem) = -1073741595;
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v40 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v12 + 4))(*v12, v11);
            v13 = 0;
          }
          else
          {
            LODWORD(v41) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
            v13 = (int)lpMem;
          }
          if ( v13 < 0 )
            RaiseException(v13, 1u, 0, 0);
          v38 = 0;
        }
        goto LABEL_62;
      }
      v61[0] = 0;
      v62 = (unsigned __int64)v7;
      v61[1] = 2;
      if ( (_DWORD)v63 )
        RaiseException(0xC00000E5, 1u, 0, 0);
      ComponentManifest = CdfFollowKeyPath(v9, 1, 1, v61, &v63, &v49);
      if ( ComponentManifest >= 0 )
      {
        if ( v49 != 1 )
        {
          LODWORD(v47) = 4052;
          if ( v37 )
          {
            RtlCloseIsolatedFilesystemObjectHandle(v37);
            v37 = 0;
          }
          if ( v38 )
          {
            LODWORD(lpMem) = -1073741595;
            ++g_nRtlCloseIsolatedFilesystemHandle;
            v40 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v34 + 4))(*v34, v33);
              v35 = 0;
            }
            else
            {
              LODWORD(v41) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
              v35 = (int)lpMem;
            }
            if ( v35 < 0 )
              RaiseException(v35, 1u, 0, 0);
            v38 = 0;
          }
          goto LABEL_122;
        }
        ComponentManifest = CCSDirectTransaction::GetComponentDirectory(
                              this,
                              (const struct CComponentAccessor *)&v59,
                              (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)&v37);
        if ( ComponentManifest >= 0 )
        {
          ComponentManifest = RtlGetSystemIsolatedFilesystem(v14, *((_QWORD *)this + 96), &v38);
          if ( ComponentManifest >= 0 )
          {
            v56 = 0;
            v58 = 0;
            v55 = 0;
            v57 = 0;
            ComponentManifest = RtlSplitLUnicodeString(2, (int)a3 + 24, v15, 0, 92, (__int64)&v55, (__int64)&v57);
            if ( ComponentManifest >= 0 )
            {
              if ( (_QWORD)v57 )
              {
                if ( (_QWORD)v55 )
                {
                  v45 = 0;
                  v51 = v37;
                  v50 = 48;
                  v52 = (bool *)&v55;
                  v53 = 64;
                  v54 = 0;
                  ComponentManifest = Windows::Isolation::Implementation::Rtl::CreateDirectories(
                                        0,
                                        v38,
                                        &v45,
                                        2032127,
                                        &v50);
                  if ( ComponentManifest < 0 )
                  {
                    if ( v45 )
                    {
                      RtlCloseIsolatedFilesystemObjectHandle(v45);
                      v45 = 0;
                    }
                    if ( v37 )
                    {
                      RtlCloseIsolatedFilesystemObjectHandle(v37);
                      v37 = 0;
                    }
                    if ( v38 )
                    {
                      ++g_nRtlCloseIsolatedFilesystemHandle;
                      LODWORD(lpMem) = -1073741595;
                      v40 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                        && (unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
                      {
                        (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v17);
                        v19 = 0;
                      }
                      else
                      {
                        LODWORD(v41) = 292;
                        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
                        v19 = (int)lpMem;
                      }
                      if ( v19 < 0 )
                        RaiseException(v19, 1u, 0, 0);
                      v38 = 0;
                    }
                    goto LABEL_62;
                  }
                  v20 = (_QWORD *)v37;
                  v37 = (__int64)v45;
                  v45 = v20;
                  if ( v20 )
                    RtlCloseIsolatedFilesystemObjectHandle(v20);
                }
              }
              else
              {
                v57 = v55;
                v58 = v56;
              }
              v21 = *((_QWORD *)this + 109);
              v51 = v37;
              v50 = 48;
              v52 = (bool *)&v57;
              v41 = *((_QWORD *)a3 + 2);
              lpMem = &g_LUNICODE_STRING__empty_;
              v40 = 48;
              v53 = 64;
              v54 = 0;
              v43 = 64;
              v44 = 0;
              ComponentManifest = Windows::Isolation::Implementation::Rtl::IsolationDuplicateFile(
                                    0,
                                    v21,
                                    v16,
                                    &v40,
                                    &v50);
              if ( ComponentManifest >= 0 )
              {
                v45 = 0;
                v52 = &v39;
                v39 = 1;
                v46 = (const char *)v60;
                v50 = 1;
                v47 = g_LUNICODE_STRING_Files;
                v51 = 1;
                v41 = 0;
                v40 = 0;
                lpMem = 0;
                v49 = 0;
                ComponentManifest = RtlpLUnicodeStringSanitizedLength(v7, &v49);
                if ( ComponentManifest < 0 )
                {
LABEL_74:
                  BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v45);
                  goto LABEL_75;
                }
                v22 = RtlAllocateLUnicodeString(v49, &v40);
                ComponentManifest = v22;
                if ( v22 < 0 )
                {
                  Windows::ErrorHandling::COM::ReportNtErrorOrigination(
                    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp",
                    (const char *)0x1012,
                    v22,
                    v23);
                  goto LABEL_72;
                }
                ComponentManifest = RtlpSanitizeLUnicodeString(1u, v7, (struct _LUNICODE_STRING *)&v40);
                if ( ComponentManifest < 0
                  || (ComponentManifest = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                                       &v45,
                                                       &v49),
                      ComponentManifest < 0) )
                {
LABEL_72:
                  if ( lpMem )
                    IsolationFreeStringRoutine(lpMem);
                  goto LABEL_74;
                }
                v28 = v45;
                ComponentManifest = CCSDirectTransaction::CPendingRegistryWrite::Initialize(
                                      v45,
                                      v24,
                                      2,
                                      &v46,
                                      &v40,
                                      &v50);
                if ( ComponentManifest < 0 )
                {
                  if ( lpMem )
                    IsolationFreeStringRoutine(lpMem);
                  BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v45);
                  goto LABEL_88;
                }
                v45 = 0;
                v28[12] = *((_QWORD *)this + 85);
                v28[11] = (char *)this + 672;
                **((_QWORD **)this + 85) = v28 + 11;
                *((_QWORD *)this + 85) = v28 + 11;
                v28[13] = (char *)this + 672;
                ++*((_QWORD *)this + 88);
                Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v40);
                BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v45);
                if ( *((_QWORD *)this + 89) )
                {
                  v45 = v59;
                  v32 = *((_QWORD *)this + 113);
                  v41 = 0;
                  v40 = 0;
                  lpMem = 0;
                  ComponentManifest = (*(__int64 (__fastcall **)(char *, __int64, _QWORD **, __int64 *))(v32 + 136))(
                                        (char *)this + 904,
                                        1,
                                        &v45,
                                        &v40);
                  if ( ComponentManifest < 0
                    || (ComponentManifest = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64 *, const struct _LUNICODE_STRING *))(**((_QWORD **)this + 89) + 16LL))(
                                              *((_QWORD *)this + 89),
                                              v9,
                                              &v40,
                                              v7),
                        ComponentManifest < 0) )
                  {
                    Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v40);
                    if ( v37 )
                    {
                      RtlCloseIsolatedFilesystemObjectHandle(v37);
                      v37 = 0;
                    }
                    if ( !v38 )
                      goto LABEL_62;
                    ++g_nRtlCloseIsolatedFilesystemHandle;
                    v46 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                    v48 = -1073741595;
                    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
                    {
                      LODWORD(v47) = 292;
                      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v46);
                      v27 = v48;
                      goto LABEL_81;
                    }
LABEL_80:
                    (*((void (__fastcall **)(_QWORD, __int64))v26 + 4))(*v26, v25);
                    v27 = 0;
LABEL_81:
                    if ( v27 < 0 )
                      RaiseException(v27, 1u, 0, 0);
                    v38 = 0;
                    goto LABEL_62;
                  }
                  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v40);
                }
                *a4 = 1;
                ComponentManifest = 0;
              }
LABEL_75:
              if ( v37 )
              {
                RtlCloseIsolatedFilesystemObjectHandle(v37);
                v37 = 0;
              }
              if ( !v38 )
                goto LABEL_62;
              ++g_nRtlCloseIsolatedFilesystemHandle;
              LODWORD(lpMem) = -1073741595;
              v40 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                || !(unsigned __int8)RtlIsTypeSafeHandleValid(v38) )
              {
                LODWORD(v41) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
                v27 = (int)lpMem;
                goto LABEL_81;
              }
              goto LABEL_80;
            }
          }
        }
      }
LABEL_88:
      if ( v37 )
      {
        RtlCloseIsolatedFilesystemObjectHandle(v37);
        v37 = 0;
      }
      v10 = v38;
      if ( !v38 )
        goto LABEL_62;
      goto LABEL_91;
    }
  }
LABEL_62:
  Windows::Cdf::Rtl::CCDF_VALUE::~CCDF_VALUE((Windows::Cdf::Rtl::CCDF_VALUE *)&v63);
  CComponentAccessor::~CComponentAccessor((CComponentAccessor *)&v59);
  return (unsigned int)ComponentManifest;
}

```

## disassembly

```asm
0x1800c03a8  mov     [rsp-8+arg_8], rbx
0x1800c03ad  push    rbp
0x1800c03ae  push    rsi
0x1800c03af  push    rdi
0x1800c03b0  push    r12
0x1800c03b2  push    r13
0x1800c03b4  push    r14
0x1800c03b6  push    r15
0x1800c03b8  lea     rbp, [rsp-90h]
0x1800c03c0  sub     rsp, 190h
0x1800c03c7  mov     rax, cs:__security_cookie
0x1800c03ce  xor     rax, rsp
0x1800c03d1  mov     [rbp+0C0h+var_38], rax
0x1800c03d8  xor     ebx, ebx
0x1800c03da  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c03e1  mov     [rbp+0C0h+var_130], rax
0x1800c03e5  mov     esi, 0C00000E5h
0x1800c03ea  mov     [rbp+0C0h+var_120], esi
0x1800c03ed  xorps   xmm0, xmm0
0x1800c03f0  mov     [rbp+0C0h+var_118], rbx
0x1800c03f4  mov     r15, rcx
0x1800c03f7  mov     [rbp+0C0h+var_B0], rbx
0x1800c03fb  mov     r13, r9
0x1800c03fe  mov     [rbp+0C0h+var_A0], rbx
0x1800c0402  mov     r14, r8
0x1800c0405  mov     [rbp+0C0h+var_A8], rbx
0x1800c0409  mov     r10d, ebx
0x1800c040c  mov     [rbp+0C0h+var_98], rbx
0x1800c0410  mov     ecx, ebx
0x1800c0412  mov     [rbp+0C0h+var_88], rbx
0x1800c0416  mov     [rbp+0C0h+var_90], rbx
0x1800c041a  mov     [rbp+0C0h+var_80], rbx
0x1800c041e  mov     [rbp+0C0h+var_70], rbx
0x1800c0422  mov     [rbp+0C0h+var_78], rbx
0x1800c0426  mov     [rbp+0C0h+var_68], rbx
0x1800c042a  mov     [rsp+1C0h+var_170], bl
0x1800c042e  mov     [rbp+0C0h+var_138], rbx
0x1800c0432  mov     [rsp+1C0h+var_178], rbx
0x1800c0437  mov     [rsp+1C0h+var_180], rbx
0x1800c043c  movups  [rbp+0C0h+var_48], xmm0
0x1800c0440  test    r8, r8
0x1800c0443  jnz     short loc_1800C0451
0x1800c0445  mov     dword ptr [rbp+0C0h+var_128], 0FABh
0x1800c044c  jmp     loc_1800C0DCF
0x1800c0451  cmp     dword ptr [r8], 30h ; '0'
0x1800c0455  jnb     short loc_1800C0463
0x1800c0457  mov     dword ptr [rbp+0C0h+var_128], 0FACh
0x1800c045e  jmp     loc_1800C0DCF
0x1800c0463  test    dword ptr [r8+4], 0FFFFFFFEh
0x1800c046b  jz      short loc_1800C0479
0x1800c046d  mov     dword ptr [rbp+0C0h+var_128], 0FADh
0x1800c0474  jmp     loc_1800C0DCF
0x1800c0479  mov     rax, cs:qword_180166950
0x1800c0480  test    rax, rax
0x1800c0483  jz      loc_1800C0D47
0x1800c0489  mov     rdx, [r8+8]
0x1800c048d  mov     rcx, [rax]
0x1800c0490  call    RtlIsBaseIdentityHandleValidWithType
0x1800c0495  test    al, al
0x1800c0497  jz      loc_1800C0D3D
0x1800c049d  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@VCFsobj@Private@Fs@34@UFSOBJ_CONSTRUCTOR_DATA@6734@VCFsobjTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT,Windows::Isolation::Fs::Private::CFsobj,Windows::Isolation::Fs::Private::FSOBJ_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsobjTraits>::ms_ptti
0x1800c04a4  test    rdx, rdx
0x1800c04a7  jz      loc_1800C0D31
0x1800c04ad  mov     rcx, [r14+10h]
0x1800c04b1  call    RtlIsTypeSafeHandleValid
0x1800c04b6  test    al, al
0x1800c04b8  jz      loc_1800C0D31
0x1800c04be  lea     r12, [r14+18h]
0x1800c04c2  mov     rcx, r12
0x1800c04c5  call    RtlIsLUnicodeStringValid
0x1800c04ca  test    al, al
0x1800c04cc  jnz     short loc_1800C04E8
0x1800c04ce  mov     dword ptr [rbp+0C0h+var_128], 0FB0h
0x1800c04d5  mov     rcx, [rsp+1C0h+var_180]
0x1800c04da  test    rcx, rcx
0x1800c04dd  jz      loc_1800C0D5D
0x1800c04e3  jmp     loc_1800C0D53
0x1800c04e8  mov     rdx, [r14+8]
0x1800c04ec  lea     rcx, [rbp+0C0h+var_B0]
0x1800c04f0  call    ?Attach@CComponentAccessor@@QEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; CComponentAccessor::Attach(Windows::Isolation::Rtl::_DEFINITION_IDENTITY)
0x1800c04f5  mov     esi, eax
0x1800c04f7  test    eax, eax
0x1800c04f9  jns     short loc_1800C0527
0x1800c04fb  mov     rcx, [rsp+1C0h+var_180]
0x1800c0500  test    rcx, rcx
0x1800c0503  jz      short loc_1800C050F
0x1800c0505  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c050a  mov     [rsp+1C0h+var_180], rbx
0x1800c050f  mov     r10, [rsp+1C0h+var_178]
0x1800c0514  test    r10, r10
0x1800c0517  jz      loc_1800C08AF
0x1800c051d  mov     edi, 1
0x1800c0522  jmp     loc_1800C084C
0x1800c0527  lea     r8, [rbp+0C0h+var_138]; struct Windows::Cdf::Rtl::_CDF *
0x1800c052b  mov     rcx, r15; this
0x1800c052e  lea     rdx, [rbp+0C0h+var_B0]; struct CComponentAccessor *
0x1800c0532  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_CDF@Rtl@Cdf@Windows@@@Z; CCSDirectTransaction::GetComponentManifest(CComponentAccessor const &,Windows::Cdf::Rtl::_CDF &)
0x1800c0537  mov     esi, eax
0x1800c0539  test    eax, eax
0x1800c053b  js      short loc_1800C04FB
0x1800c053d  mov     rbx, [rbp+0C0h+var_138]
0x1800c0541  xor     edi, edi
0x1800c0543  test    rbx, rbx
0x1800c0546  jnz     short loc_1800C057E
0x1800c0548  mov     rcx, [rsp+1C0h+var_180]
0x1800c054d  mov     dword ptr [rbp+0C0h+var_128], 0FB4h
0x1800c0554  test    rcx, rcx
0x1800c0557  jz      short loc_1800C0563
0x1800c0559  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c055e  mov     [rsp+1C0h+var_180], rbx
0x1800c0563  mov     r10, [rsp+1C0h+var_178]
0x1800c0568  test    r10, r10
0x1800c056b  jz      loc_1800C0DCF
0x1800c0571  mov     dword ptr [rsp+1C0h+lpMem], 0C00000E5h
0x1800c0579  jmp     loc_1800C0D6B
0x1800c057e  lea     r9, [rsp+1C0h+var_170]; bool *
0x1800c0583  mov     [r13+0], edi
0x1800c0587  mov     r8, r12; struct _LUNICODE_STRING *
0x1800c058a  lea     rdx, [rbp+0C0h+var_B0]; struct CComponentAccessor *
0x1800c058e  mov     rcx, r15; this
0x1800c0591  call    ?IsFileInstalled@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@PEBU_LUNICODE_STRING@@AEA_N@Z; CCSDirectTransaction::IsFileInstalled(CComponentAccessor const &,_LUNICODE_STRING const *,bool &)
0x1800c0596  mov     esi, eax
0x1800c0598  test    eax, eax
0x1800c059a  jns     short loc_1800C05C8
0x1800c059c  mov     rcx, [rsp+1C0h+var_180]
0x1800c05a1  test    rcx, rcx
0x1800c05a4  jz      short loc_1800C05B0
0x1800c05a6  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c05ab  mov     [rsp+1C0h+var_180], rdi
0x1800c05b0  mov     r10, [rsp+1C0h+var_178]
0x1800c05b5  test    r10, r10
0x1800c05b8  jz      loc_1800C08AF
0x1800c05be  mov     edi, 1
0x1800c05c3  jmp     loc_1800C0B38
0x1800c05c8  cmp     [rsp+1C0h+var_170], dil
0x1800c05cd  jz      loc_1800C067C
0x1800c05d3  mov     rcx, [rsp+1C0h+var_180]
0x1800c05d8  mov     esi, edi
0x1800c05da  test    rcx, rcx
0x1800c05dd  jz      short loc_1800C05E9
0x1800c05df  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c05e4  mov     [rsp+1C0h+var_180], rdi
0x1800c05e9  mov     r10, [rsp+1C0h+var_178]
0x1800c05ee  test    r10, r10
0x1800c05f1  jz      loc_1800C08AF
0x1800c05f7  mov     edi, 1
0x1800c05fc  mov     dword ptr [rsp+1C0h+lpMem], 0C00000E5h
0x1800c0604  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c060b  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c0612  mov     [rsp+1C0h+var_168], rax
0x1800c0617  test    r10, r10
0x1800c061a  jz      short loc_1800C0646
0x1800c061c  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c0623  test    r11, r11
0x1800c0626  jz      short loc_1800C0664
0x1800c0628  mov     rdx, r11
0x1800c062b  mov     rcx, r10
0x1800c062e  call    RtlIsTypeSafeHandleValid
0x1800c0633  test    al, al
0x1800c0635  jz      short loc_1800C0664
0x1800c0637  mov     ecx, [r11]
0x1800c063a  mov     rdx, r10
0x1800c063d  mov     rax, [r11+20h]
0x1800c0641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0646  xor     ecx, ecx; dwExceptionCode
0x1800c0648  test    ecx, ecx
0x1800c064a  jns     short loc_1800C065A
0x1800c064c  xor     r9d, r9d; lpArguments
0x1800c064f  xor     r8d, r8d; nNumberOfArguments
0x1800c0652  mov     edx, edi; dwExceptionFlags
0x1800c0654  call    cs:__imp_RaiseException
0x1800c065a  mov     [rsp+1C0h+var_178], rsi
0x1800c065f  jmp     loc_1800C08AF
0x1800c0664  mov     dword ptr [rsp+1C0h+var_160], 124h
0x1800c066c  lea     rcx, [rsp+1C0h+var_168]
0x1800c0671  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c0676  mov     ecx, dword ptr [rsp+1C0h+lpMem]
0x1800c067a  jmp     short loc_1800C0648
0x1800c067c  cmp     dword ptr [rbp+0C0h+var_48], 0
0x1800c0680  xorps   xmm0, xmm0
0x1800c0683  movups  [rbp+0C0h+var_58], xmm0
0x1800c0687  mov     [rbp+0C0h+var_60], edi
0x1800c068a  mov     edi, 1
0x1800c068f  mov     qword ptr [rbp+0C0h+var_58], r12
0x1800c0693  mov     [rbp+0C0h+var_5C], 2
0x1800c069a  jz      short loc_1800C06AF
0x1800c069c  xor     r9d, r9d; lpArguments
0x1800c069f  xor     r8d, r8d; nNumberOfArguments
0x1800c06a2  mov     edx, edi; dwExceptionFlags
0x1800c06a4  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800c06a9  call    cs:__imp_RaiseException
0x1800c06af  lea     rax, [rbp+0C0h+var_118]
0x1800c06b3  mov     r8, rdi
0x1800c06b6  mov     [rsp+1C0h+var_198], rax
0x1800c06bb  lea     r9, [rbp+0C0h+var_60]
0x1800c06bf  lea     rax, [rbp+0C0h+var_48]
0x1800c06c3  mov     edx, edi
0x1800c06c5  mov     rcx, rbx
0x1800c06c8  mov     [rsp+1C0h+var_1A0], rax
0x1800c06cd  call    CdfFollowKeyPath
0x1800c06d2  mov     esi, eax
0x1800c06d4  test    eax, eax
0x1800c06d6  js      loc_1800C0B12
0x1800c06dc  cmp     [rbp+0C0h+var_118], rdi
0x1800c06e0  jz      short loc_1800C071A
0x1800c06e2  mov     rcx, [rsp+1C0h+var_180]
0x1800c06e7  xor     ebx, ebx
0x1800c06e9  mov     dword ptr [rbp+0C0h+var_128], 0FD4h
0x1800c06f0  test    rcx, rcx
0x1800c06f3  jz      short loc_1800C06FF
0x1800c06f5  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c06fa  mov     [rsp+1C0h+var_180], rbx
0x1800c06ff  mov     r10, [rsp+1C0h+var_178]
0x1800c0704  test    r10, r10
0x1800c0707  jz      loc_1800C0DCF
0x1800c070d  mov     dword ptr [rsp+1C0h+lpMem], 0C00000E5h
0x1800c0715  jmp     loc_1800C0D70
0x1800c071a  lea     r8, [rsp+1C0h+var_180]; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *
0x1800c071f  mov     rcx, r15; this
0x1800c0722  lea     rdx, [rbp+0C0h+var_B0]; struct CComponentAccessor *
0x1800c0726  call    ?GetComponentDirectory@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@@Z; CCSDirectTransaction::GetComponentDirectory(CComponentAccessor const &,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x1800c072b  mov     esi, eax
0x1800c072d  test    eax, eax
0x1800c072f  js      loc_1800C0B12
0x1800c0735  mov     rdx, [r15+300h]
0x1800c073c  lea     r8, [rsp+1C0h+var_178]
0x1800c0741  call    RtlGetSystemIsolatedFilesystem
0x1800c0746  mov     esi, eax
0x1800c0748  test    eax, eax
0x1800c074a  js      loc_1800C0B12
0x1800c0750  xor     eax, eax
0x1800c0752  xor     r9d, r9d
0x1800c0755  mov     [rbp+0C0h+var_D0], rax
0x1800c0759  xorps   xmm0, xmm0
0x1800c075c  mov     [rbp+0C0h+var_B8], rax
0x1800c0760  xorps   xmm1, xmm1
0x1800c0763  lea     rax, [rbp+0C0h+var_C8]
0x1800c0767  mov     rdx, r12
0x1800c076a  mov     [rsp+1C0h+var_190], rax
0x1800c076f  lea     ecx, [r9+2]
0x1800c0773  lea     rax, [rbp+0C0h+var_E0]
0x1800c0777  mov     [rsp+1C0h+var_198], rax
0x1800c077c  mov     [rsp+1C0h+var_1A0], 5Ch ; '\'
0x1800c0785  movups  [rbp+0C0h+var_E0], xmm0
0x1800c0789  movups  [rbp+0C0h+var_C8], xmm1
0x1800c078d  call    RtlSplitLUnicodeString
0x1800c0792  mov     esi, eax
0x1800c0794  xor     eax, eax
0x1800c0796  test    esi, esi
0x1800c0798  js      loc_1800C0B12
0x1800c079e  cmp     qword ptr [rbp+0C0h+var_C8], rax
0x1800c07a2  jnz     short loc_1800C07BB
0x1800c07a4  movups  xmm0, [rbp+0C0h+var_E0]
0x1800c07a8  movsd   xmm1, [rbp+0C0h+var_D0]
0x1800c07ad  movups  [rbp+0C0h+var_C8], xmm0
0x1800c07b1  movsd   [rbp+0C0h+var_B8], xmm1
0x1800c07b6  jmp     loc_1800C08FA
0x1800c07bb  cmp     qword ptr [rbp+0C0h+var_E0], rax
0x1800c07bf  jz      loc_1800C08FA
0x1800c07c5  mov     rdx, [rsp+1C0h+var_178]
0x1800c07ca  lea     r8, [rbp+0C0h+var_138]
0x1800c07ce  mov     [rbp+0C0h+var_138], rax
0x1800c07d2  xorps   xmm0, xmm0
0x1800c07d5  mov     rax, [rsp+1C0h+var_180]
0x1800c07da  mov     r9d, 1F01FFh
0x1800c07e0  mov     [rbp+0C0h+var_108], rax
0x1800c07e4  xor     ecx, ecx
0x1800c07e6  lea     rax, [rbp+0C0h+var_E0]
0x1800c07ea  mov     [rbp+0C0h+var_110], 30h ; '0'
0x1800c07f2  mov     [rbp+0C0h+var_100], rax
0x1800c07f6  lea     rax, [rbp+0C0h+var_110]
0x1800c07fa  mov     [rsp+1C0h+var_1A0], rax
0x1800c07ff  mov     [rbp+0C0h+var_F8], 40h ; '@'
0x1800c0806  movdqu  [rbp+0C0h+var_F0], xmm0
0x1800c080b  call    ?CreateDirectories@Rtl@Implementation@Isolation@Windows@@YAJKU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@KPEBU_ISOLATED_OBJECT_ATTRIBUTES@134@@Z; Windows::Isolation::Implementation::Rtl::CreateDirectories(ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *,ulong,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *)
0x1800c0810  mov     esi, eax
0x1800c0812  test    eax, eax
0x1800c0814  jns     loc_1800C08DE
0x1800c081a  mov     rcx, [rbp+0C0h+var_138]
0x1800c081e  xor     ebx, ebx
0x1800c0820  test    rcx, rcx
0x1800c0823  jz      short loc_1800C082E
0x1800c0825  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c082a  mov     [rbp+0C0h+var_138], rbx
0x1800c082e  mov     rcx, [rsp+1C0h+var_180]
0x1800c0833  test    rcx, rcx
0x1800c0836  jz      short loc_1800C0842
0x1800c0838  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c083d  mov     [rsp+1C0h+var_180], rbx
0x1800c0842  mov     r10, [rsp+1C0h+var_178]
0x1800c0847  test    r10, r10
0x1800c084a  jz      short loc_1800C08AF
0x1800c084c  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rdi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c0853  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c085a  mov     dword ptr [rsp+1C0h+lpMem], 0C00000E5h
0x1800c0862  mov     [rsp+1C0h+var_168], rax
0x1800c0867  test    r10, r10
0x1800c086a  jz      short loc_1800C0896
0x1800c086c  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c0873  test    r11, r11
  ... truncated ...
```
