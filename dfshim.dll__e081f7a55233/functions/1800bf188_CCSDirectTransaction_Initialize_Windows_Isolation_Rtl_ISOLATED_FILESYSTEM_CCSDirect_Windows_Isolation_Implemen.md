# CCSDirectTransaction::Initialize(Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,CCSDirect *,Windows::Isolation::Implementation::Rtl::ITransactionHook *)

- ea: `0x1800bf188`
- end: `0x1800bfb43`
- name: `?Initialize@CCSDirectTransaction@@IEAAJU_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@PEAVCCSDirect@@PEAUITransactionHook@3Implementation@45@@Z`
- size: `2491`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002a910`

## callees

- `0x1800125c8`
- `0x180012950`
- `0x180012b1c`
- `0x1800172e0`
- `0x180017400`
- `0x180017514`
- `0x180017530`
- `0x180017580`
- `0x18001766c`
- `0x18001d478`
- `0x18001ddec`
- `0x18001defc`
- `0x18002a844`
- `0x18002c8d8`
- `0x18003f5c0`
- `0x18003ff84`
- `0x180040020`
- `0x18004011c`
- `0x180040f70`
- `0x180041188`
- `0x18004f2dc`
- `0x1800bf188`
- `0x1800c7694`
- `0x1800cb7c8`
- `0x1800cc2ac`
- `0x1800d282c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf2f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf406`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf931`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfa36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfab9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf2f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf406`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf931`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfa36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfab9`

## string_xrefs

- `0x1800bf292`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bf3aa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bf759`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bf8b6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bf9bb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bfa5e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bf1b2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::Initialize(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 (__fastcall ***a4)(_QWORD, __int64))
{
  __int64 v8; // r8
  int SystemIsolatedFilesystem; // r14d
  __int64 v10; // r10
  unsigned int *v11; // r11
  signed int v12; // ecx
  __int64 v13; // r10
  __int64 v14; // r10
  unsigned int *v15; // r11
  __int64 v16; // rcx
  __int64 v17; // r10
  unsigned int *v18; // r11
  signed int v19; // ecx
  __int64 v20; // rcx
  __int64 *v21; // rax
  unsigned __int64 v22; // rsi
  __int64 v23; // r10
  signed int v24; // ecx
  __int64 v26; // r10
  signed int v27; // ecx
  __int64 v28; // r10
  signed int v29; // ecx
  __int64 v30; // r10
  unsigned int *v31; // r11
  signed int v32; // ecx
  __int64 v33; // r10
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  const char *v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int64 *v38; // [rsp+70h] [rbp-90h]
  _QWORD *v39; // [rsp+78h] [rbp-88h]
  __int64 *v40; // [rsp+80h] [rbp-80h]
  _QWORD *v41; // [rsp+88h] [rbp-78h]
  __int64 *v42; // [rsp+90h] [rbp-70h]
  _QWORD *v43; // [rsp+98h] [rbp-68h]
  __int64 *v44; // [rsp+A0h] [rbp-60h]
  _QWORD *v45; // [rsp+A8h] [rbp-58h]
  __int64 *v46; // [rsp+B0h] [rbp-50h]
  _QWORD *v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  int v50; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v51[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-18h]
  __int64 v53; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h]
  __int64 v55; // [rsp+108h] [rbp+8h]
  _QWORD v56[3]; // [rsp+110h] [rbp+10h] BYREF
  int v57; // [rsp+128h] [rbp+28h]
  __int128 v58; // [rsp+130h] [rbp+30h]
  _QWORD v59[3]; // [rsp+140h] [rbp+40h] BYREF
  int v60; // [rsp+158h] [rbp+58h]
  __int128 v61; // [rsp+160h] [rbp+60h]

  v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  LODWORD(v38) = -1073741595;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v51);
  v49 = 0;
  v35 = 0;
  v34 = 0;
  if ( !v8 )
  {
    LODWORD(v37) = 1451;
LABEL_9:
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v49);
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v51);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v36,
      &v36);
    return (unsigned int)v38;
  }
  if ( a1[89] )
  {
    LODWORD(v37) = 1453;
    goto LABEL_9;
  }
  if ( a1[112] )
  {
    LODWORD(v37) = 1454;
    goto LABEL_9;
  }
  if ( a1[109] )
  {
    LODWORD(v37) = 1456;
    goto LABEL_9;
  }
  a1[112] = (__int64)a3;
  a1[89] = (__int64)a4;
  if ( a2 )
  {
    SystemIsolatedFilesystem = RtlDuplicateIsolatedFilesystemHandle(a2);
    if ( SystemIsolatedFilesystem < 0
      || (SystemIsolatedFilesystem = RtlDuplicateIsolatedFilesystemHandle(a2), SystemIsolatedFilesystem < 0) )
    {
      if ( v34 )
      {
        v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        LODWORD(v38) = -1073741595;
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v34) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
          v12 = 0;
        }
        else
        {
          LODWORD(v37) = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
          v12 = (int)v38;
        }
        if ( v12 < 0 )
          RaiseException(v12, 1u, 0, 0);
        v34 = 0;
      }
      v13 = v35;
      if ( !v35 )
        goto LABEL_71;
      LODWORD(v38) = -1073741595;
      goto LABEL_21;
    }
  }
  SystemIsolatedFilesystem = RtlDuplicateSystemHandle(a3[6], a1 + 96);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v16, a1[96], &v35);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  SystemIsolatedFilesystem = RtlGetSystemIsolatedRegistry(v20, a1[96], &v34);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  if ( a4 )
  {
    SystemIsolatedFilesystem = (**a4)(a4, a1[96]);
    if ( SystemIsolatedFilesystem < 0 )
      goto LABEL_28;
  }
  SystemIsolatedFilesystem = RtlDuplicateLUnicodeString(a3 + 14, a1 + 93);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  SystemIsolatedFilesystem = RtlDuplicateLUnicodeString(a3 + 11, a1 + 90);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  v36 = (const char *)a3[13];
  v37 = a3[11] >> 1;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v51,
                               &v36);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  v53 = 2 * v52;
  v54 = 2 * v52;
  v55 = v51[0];
  SystemIsolatedFilesystem = Isolation_OpenDirectory(v35, a1 + 99, 3221225472LL, &v53);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_28;
  if ( !v51[0] || !v52 || *(_WORD *)(v51[0] + 2 * v52 - 2) != 92 )
  {
    SystemIsolatedFilesystem = BCL::Nt::CUnicodeStringBuffer::Append((BCL::Nt::CUnicodeStringBuffer *)v51, 0x5Cu);
    if ( SystemIsolatedFilesystem < 0 )
      goto LABEL_28;
  }
  v36 = (const char *)L"manifests";
  v37 = 9;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v51,
                               &v36);
  if ( SystemIsolatedFilesystem < 0
    || (v53 = 2 * v52,
        v54 = 2 * v52,
        v55 = v51[0],
        SystemIsolatedFilesystem = Isolation_OpenDirectory(v35, a1 + 98, 1180063, &v53),
        SystemIsolatedFilesystem < 0) )
  {
LABEL_28:
    if ( v34 )
    {
      v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      LODWORD(v38) = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v34) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v17);
        v19 = 0;
      }
      else
      {
        LODWORD(v37) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
        v19 = (int)v38;
      }
      if ( v19 < 0 )
        RaiseException(v19, 1u, 0, 0);
      v34 = 0;
    }
    v13 = v35;
    if ( !v35 )
      goto LABEL_71;
    LODWORD(v38) = -1073741595;
LABEL_21:
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( v13 )
    {
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v13) )
      {
LABEL_110:
        LODWORD(v37) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
        goto LABEL_114;
      }
      (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v14);
    }
LABEL_67:
    v24 = 0;
LABEL_68:
    if ( v24 < 0 )
      RaiseException(v24, 1u, 0, 0);
    goto LABEL_70;
  }
  v21 = &g_LUNICODE_STRING__empty_;
  v56[0] = 48;
  v56[1] = 0;
  v57 = 64;
  if ( a3 != (_QWORD *)-112LL )
    v21 = a3 + 14;
  v48 = 0;
  v56[2] = v21;
  v58 = 0;
  SystemIsolatedFilesystem = isoreghierarchy_CreateFromRegistryAndObjAttributes(4, 3221225472LL, v34, v56, 0, &v48);
  if ( SystemIsolatedFilesystem < 0 )
  {
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v48);
    goto LABEL_28;
  }
  v22 = 0;
  v36 = (const char *)g_LUNICODE_STRING_Assemblies;
  v37 = (__int64)(a1 + 101);
  v38 = g_LUNICODE_STRING_Components;
  v39 = a1 + 102;
  v40 = g_LUNICODE_STRING_Installations;
  v41 = a1 + 103;
  v42 = g_LUNICODE_STRING_Visibility;
  v43 = a1 + 104;
  v44 = g_LUNICODE_STRING_VisibilityRoots;
  v45 = a1 + 105;
  v46 = g_LUNICODE_STRING_PackageMetadata;
  v47 = a1 + 106;
  do
  {
    v50 = 0;
    SystemIsolatedFilesystem = Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(
                                 1,
                                 v48,
                                 3221225472LL,
                                 (&v36)[2 * v22],
                                 *(&v37 + 2 * v22),
                                 &v50);
    if ( SystemIsolatedFilesystem < 0 )
    {
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v48);
      if ( !v34 )
        goto LABEL_108;
      LODWORD(v38) = -1073741595;
      v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v34) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v30);
        goto LABEL_104;
      }
LABEL_111:
      LODWORD(v37) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
LABEL_112:
      v32 = (int)v38;
      goto LABEL_105;
    }
    ++v22;
  }
  while ( v22 < 6 );
  SystemIsolatedFilesystem = RtlIsolatedRegistryCreateKey(v34, (int)a1 + 856, 131103, (unsigned int)v56);
  if ( SystemIsolatedFilesystem >= 0 )
  {
    v59[1] = a1[107];
    v59[2] = g_LUNICODE_STRING_Marks;
    v59[0] = 48;
    v60 = 64;
    v61 = 0;
    SystemIsolatedFilesystem = RtlIsolatedRegistryCreateKey(v34, (int)a1 + 864, 131103, (unsigned int)v59);
    if ( SystemIsolatedFilesystem < 0
      || (SystemIsolatedFilesystem = CComponentMarkManager::Initialize(a1 + 394, a1[108], v34),
          SystemIsolatedFilesystem < 0) )
    {
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v48);
      if ( !v34 )
      {
LABEL_85:
        if ( !v35 )
          goto LABEL_71;
        RtlCloseIsolatedFilesystemHandle();
LABEL_70:
        v35 = 0;
        goto LABEL_71;
      }
      LODWORD(v38) = -1073741595;
      v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v34) )
      {
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                                  + 32))(
            *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
            v26);
          v27 = 0;
          goto LABEL_82;
        }
        LODWORD(v37) = 293;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v36,
          &v36);
      }
      else
      {
        LODWORD(v37) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
      }
      v27 = (int)v38;
LABEL_82:
      if ( v27 < 0 )
        RaiseException(v27, 1u, 0, 0);
      v34 = 0;
      goto LABEL_85;
    }
    v37 = a1[96];
    v38 = a1 + 90;
    v39 = a1 + 93;
    LODWORD(v36) = *(_BYTE *)(a1[112] + 260) != 0;
    SystemIsolatedFilesystem = CCSDirect::Initialize((CCSDirect *)(a1 + 113), (struct CCSDirectProviderCD *)&v36);
    if ( SystemIsolatedFilesystem >= 0 )
      SystemIsolatedFilesystem = 0;
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v48);
    if ( !v34 )
    {
LABEL_99:
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_Traits>::Close(&v35);
      goto LABEL_71;
    }
    LODWORD(v38) = -1073741595;
    v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v34) )
    {
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                                + 32))(
          *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
          v28);
        v29 = 0;
        goto LABEL_96;
      }
      LODWORD(v37) = 293;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v36,
        &v36);
    }
    else
    {
      LODWORD(v37) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
    }
    v29 = (int)v38;
LABEL_96:
    if ( v29 < 0 )
      RaiseException(v29, 1u, 0, 0);
    v34 = 0;
    goto LABEL_99;
  }
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v48);
  if ( !v34 )
    goto LABEL_108;
  LODWORD(v38) = -1073741595;
  v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
  if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::IsValid(v34) )
    goto LABEL_111;
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti )
  {
    LODWORD(v37) = 293;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v36,
      &v36);
    goto LABEL_112;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
                                          + 32))(
    *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti,
    v23);
LABEL_104:
  v32 = 0;
LABEL_105:
  if ( v32 < 0 )
    RaiseException(v32, 1u, 0, 0);
  v34 = 0;
LABEL_108:
  if ( v35 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v38) = -1073741595;
    if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v35) )
      goto LABEL_110;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                              + 32))(
        *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
        v33);
      goto LABEL_67;
    }
    LODWORD(v37) = 293;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v36,
      &v36);
LABEL_114:
    v24 = (int)v38;
    goto LABEL_68;
  }
LABEL_71:
  Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v49);
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v51);
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800bf188  push    rbp
0x1800bf18a  push    rbx
0x1800bf18b  push    rsi
0x1800bf18c  push    rdi
0x1800bf18d  push    r12
0x1800bf18f  push    r13
0x1800bf191  push    r14
0x1800bf193  push    r15
0x1800bf195  lea     rbp, [rsp-88h]
0x1800bf19d  sub     rsp, 188h
0x1800bf1a4  mov     rax, cs:__security_cookie
0x1800bf1ab  xor     rax, rsp
0x1800bf1ae  mov     [rbp+0C0h+var_50], rax
0x1800bf1b2  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bf1b9  mov     rdi, rcx
0x1800bf1bc  mov     r13d, 0C00000E5h
0x1800bf1c2  mov     [rsp+1C0h+var_160], rax
0x1800bf1c7  lea     rcx, [rbp+0C0h+var_E8]; this
0x1800bf1cb  mov     dword ptr [rsp+1C0h+var_150], r13d
0x1800bf1d0  mov     r15, r9
0x1800bf1d3  mov     rsi, r8
0x1800bf1d6  mov     rbx, rdx
0x1800bf1d9  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800bf1de  xor     r12d, r12d
0x1800bf1e1  mov     [rbp+0C0h+var_F8], r12
0x1800bf1e5  mov     [rsp+1C0h+var_168], r12
0x1800bf1ea  mov     [rsp+1C0h+var_170], r12
0x1800bf1ef  test    r8, r8
0x1800bf1f2  jnz     short loc_1800BF1FE
0x1800bf1f4  mov     dword ptr [rsp+1C0h+var_158], 5ABh
0x1800bf1fc  jmp     short loc_1800BF238
0x1800bf1fe  cmp     [rdi+2C8h], r12
0x1800bf205  jz      short loc_1800BF211
0x1800bf207  mov     dword ptr [rsp+1C0h+var_158], 5ADh
0x1800bf20f  jmp     short loc_1800BF238
0x1800bf211  cmp     [rdi+380h], r12
0x1800bf218  jz      short loc_1800BF224
0x1800bf21a  mov     dword ptr [rsp+1C0h+var_158], 5AEh
0x1800bf222  jmp     short loc_1800BF238
0x1800bf224  lea     rdx, [rdi+368h]
0x1800bf22b  cmp     [rdx], r12
0x1800bf22e  jz      short loc_1800BF263
0x1800bf230  mov     dword ptr [rsp+1C0h+var_158], 5B0h
0x1800bf238  lea     rcx, [rbp+0C0h+var_F8]
0x1800bf23c  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800bf241  lea     rcx, [rbp+0C0h+var_E8]; this
0x1800bf245  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800bf24a  lea     rdx, [rsp+1C0h+var_160]
0x1800bf24f  lea     rcx, [rsp+1C0h+var_160]
0x1800bf254  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800bf259  mov     r14d, dword ptr [rsp+1C0h+var_150]
0x1800bf25e  jmp     loc_1800BF808
0x1800bf263  mov     [rdi+380h], rsi
0x1800bf26a  mov     [rdi+2C8h], r15
0x1800bf271  test    rbx, rbx
0x1800bf274  jz      loc_1800BF386
0x1800bf27a  mov     rcx, rbx
0x1800bf27d  call    RtlDuplicateIsolatedFilesystemHandle
0x1800bf282  mov     r14d, eax
0x1800bf285  test    eax, eax
0x1800bf287  jns     loc_1800BF36C
0x1800bf28d  mov     r10, [rsp+1C0h+var_170]
0x1800bf292  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bf299  mov     ebx, 1
0x1800bf29e  mov     esi, 124h
0x1800bf2a3  test    r10, r10
0x1800bf2a6  jz      short loc_1800BF2FE
0x1800bf2a8  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x1800bf2af  mov     [rsp+1C0h+var_160], rdi
0x1800bf2b4  mov     dword ptr [rsp+1C0h+var_150], r13d
0x1800bf2b9  test    r11, r11
0x1800bf2bc  jz      loc_1800BF355
0x1800bf2c2  mov     rdx, r11
0x1800bf2c5  mov     rcx, r10
0x1800bf2c8  call    RtlIsTypeSafeHandleValid
0x1800bf2cd  test    al, al
0x1800bf2cf  jz      loc_1800BF355
0x1800bf2d5  mov     ecx, [r11]
0x1800bf2d8  mov     rdx, r10
0x1800bf2db  mov     rax, [r11+20h]
0x1800bf2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf2e4  mov     ecx, r12d; dwExceptionCode
0x1800bf2e7  test    ecx, ecx
0x1800bf2e9  jns     short loc_1800BF2F9
0x1800bf2eb  xor     r9d, r9d; lpArguments
0x1800bf2ee  xor     r8d, r8d; nNumberOfArguments
0x1800bf2f1  mov     edx, ebx; dwExceptionFlags
0x1800bf2f3  call    cs:__imp_RaiseException
0x1800bf2f9  mov     [rsp+1C0h+var_170], r12
0x1800bf2fe  mov     r10, [rsp+1C0h+var_168]
0x1800bf303  test    r10, r10
0x1800bf306  jz      loc_1800BF7F6
0x1800bf30c  mov     dword ptr [rsp+1C0h+var_150], r13d
0x1800bf311  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rbx; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bf318  mov     [rsp+1C0h+var_160], rdi
0x1800bf31d  test    r10, r10
0x1800bf320  jz      loc_1800BF7DC
0x1800bf326  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bf32d  test    r11, r11
0x1800bf330  jz      loc_1800BFAFF
0x1800bf336  mov     rdx, r11
0x1800bf339  mov     rcx, r10
0x1800bf33c  call    RtlIsTypeSafeHandleValid
0x1800bf341  test    al, al
0x1800bf343  jz      loc_1800BFAFF
0x1800bf349  mov     ecx, [r11]
0x1800bf34c  mov     rax, [r11+20h]
0x1800bf350  jmp     loc_1800BF7D4
0x1800bf355  mov     dword ptr [rsp+1C0h+var_158], esi
0x1800bf359  lea     rcx, [rsp+1C0h+var_160]
0x1800bf35e  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bf363  mov     ecx, dword ptr [rsp+1C0h+var_150]
0x1800bf367  jmp     loc_1800BF2E7
0x1800bf36c  lea     rdx, [rdi+308h]
0x1800bf373  mov     rcx, rbx
0x1800bf376  call    RtlDuplicateIsolatedFilesystemHandle
0x1800bf37b  mov     r14d, eax
0x1800bf37e  test    eax, eax
0x1800bf380  js      loc_1800BF28D
0x1800bf386  mov     rcx, [rsi+30h]
0x1800bf38a  lea     r13, [rdi+2D0h]
0x1800bf391  lea     rdx, [r13+30h]
0x1800bf395  call    RtlDuplicateSystemHandle
0x1800bf39a  mov     r14d, eax
0x1800bf39d  test    eax, eax
0x1800bf39f  jns     loc_1800BF440
0x1800bf3a5  mov     r10, [rsp+1C0h+var_170]
0x1800bf3aa  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bf3b1  mov     ebx, 1
0x1800bf3b6  mov     esi, 124h
0x1800bf3bb  test    r10, r10
0x1800bf3be  jz      short loc_1800BF411
0x1800bf3c0  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x1800bf3c7  mov     [rsp+1C0h+var_160], rdi
0x1800bf3cc  mov     dword ptr [rsp+1C0h+var_150], 0C00000E5h
0x1800bf3d4  test    r11, r11
0x1800bf3d7  jz      short loc_1800BF42C
0x1800bf3d9  mov     rdx, r11
0x1800bf3dc  mov     rcx, r10
0x1800bf3df  call    RtlIsTypeSafeHandleValid
0x1800bf3e4  test    al, al
0x1800bf3e6  jz      short loc_1800BF42C
0x1800bf3e8  mov     ecx, [r11]
0x1800bf3eb  mov     rdx, r10
0x1800bf3ee  mov     rax, [r11+20h]
0x1800bf3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf3f7  mov     ecx, r12d; dwExceptionCode
0x1800bf3fa  test    ecx, ecx
0x1800bf3fc  jns     short loc_1800BF40C
0x1800bf3fe  xor     r9d, r9d; lpArguments
0x1800bf401  xor     r8d, r8d; nNumberOfArguments
0x1800bf404  mov     edx, ebx; dwExceptionFlags
0x1800bf406  call    cs:__imp_RaiseException
0x1800bf40c  mov     [rsp+1C0h+var_170], r12
0x1800bf411  mov     r10, [rsp+1C0h+var_168]
0x1800bf416  test    r10, r10
0x1800bf419  jz      loc_1800BF7F6
0x1800bf41f  mov     dword ptr [rsp+1C0h+var_150], 0C00000E5h
0x1800bf427  jmp     loc_1800BF311
0x1800bf42c  mov     dword ptr [rsp+1C0h+var_158], esi
0x1800bf430  lea     rcx, [rsp+1C0h+var_160]
0x1800bf435  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bf43a  mov     ecx, dword ptr [rsp+1C0h+var_150]
0x1800bf43e  jmp     short loc_1800BF3FA
0x1800bf440  mov     rdx, [rdi+300h]
0x1800bf447  lea     r8, [rsp+1C0h+var_168]
0x1800bf44c  call    RtlGetSystemIsolatedFilesystem
0x1800bf451  mov     r14d, eax
0x1800bf454  test    eax, eax
0x1800bf456  js      loc_1800BF3A5
0x1800bf45c  mov     rdx, [rdi+300h]
0x1800bf463  lea     r8, [rsp+1C0h+var_170]
0x1800bf468  call    RtlGetSystemIsolatedRegistry
0x1800bf46d  mov     r14d, eax
0x1800bf470  test    eax, eax
0x1800bf472  js      loc_1800BF3A5
0x1800bf478  test    r15, r15
0x1800bf47b  jz      short loc_1800BF49D
0x1800bf47d  mov     rax, [r15]
0x1800bf480  mov     rcx, r15
0x1800bf483  mov     rdx, [rdi+300h]
0x1800bf48a  mov     rax, [rax]
0x1800bf48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf492  mov     r14d, eax
0x1800bf495  test    eax, eax
0x1800bf497  js      loc_1800BF3A5
0x1800bf49d  lea     rbx, [rsi+70h]
0x1800bf4a1  mov     rcx, rbx
0x1800bf4a4  lea     rdx, [r13+18h]
0x1800bf4a8  call    RtlDuplicateLUnicodeString
0x1800bf4ad  mov     r14d, eax
0x1800bf4b0  test    eax, eax
0x1800bf4b2  js      loc_1800BF3A5
0x1800bf4b8  mov     rdx, r13
0x1800bf4bb  lea     rcx, [rsi+58h]
0x1800bf4bf  call    RtlDuplicateLUnicodeString
0x1800bf4c4  mov     r14d, eax
0x1800bf4c7  test    eax, eax
0x1800bf4c9  js      loc_1800BF3A5
0x1800bf4cf  mov     rax, [rsi+68h]
0x1800bf4d3  lea     rdx, [rsp+1C0h+var_160]
0x1800bf4d8  mov     [rsp+1C0h+var_160], rax
0x1800bf4dd  lea     rcx, [rbp+0C0h+var_E8]
0x1800bf4e1  mov     rax, [rsi+58h]
0x1800bf4e5  shr     rax, 1
0x1800bf4e8  mov     [rsp+1C0h+var_158], rax
0x1800bf4ed  call    ??$public_Assign@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800bf4f2  mov     r14d, eax
0x1800bf4f5  test    eax, eax
0x1800bf4f7  js      loc_1800BF3A5
0x1800bf4fd  mov     rax, [rbp+0C0h+var_D8]
0x1800bf501  lea     rdx, [r13+48h]
0x1800bf505  mov     rcx, [rsp+1C0h+var_168]
0x1800bf50a  lea     r9, [rbp+0C0h+var_C8]
0x1800bf50e  add     rax, rax
0x1800bf511  mov     r15d, 0C0000000h
0x1800bf517  mov     [rbp+0C0h+var_C8], rax
0x1800bf51b  mov     r8d, r15d
0x1800bf51e  mov     [rbp+0C0h+var_C0], rax
0x1800bf522  mov     rax, [rbp+0C0h+var_E8]
0x1800bf526  mov     [rbp+0C0h+var_B8], rax
0x1800bf52a  call    ?Isolation_OpenDirectory@@YAJU_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@PEAU_ISOLATED_FILESYSTEM_OBJECT@234@KPEBU_LUNICODE_STRING@@@Z; Isolation_OpenDirectory(Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *,ulong,_LUNICODE_STRING const *)
0x1800bf52f  mov     r14d, eax
0x1800bf532  test    eax, eax
0x1800bf534  js      loc_1800BF3A5
0x1800bf53a  mov     rax, [rbp+0C0h+var_E8]
0x1800bf53e  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800bf543  test    rax, rax
0x1800bf546  jz      short loc_1800BF558
0x1800bf548  mov     rcx, [rbp+0C0h+var_D8]
0x1800bf54c  test    rcx, rcx
0x1800bf54f  jz      short loc_1800BF558
0x1800bf551  cmp     [rax+rcx*2-2], dx
0x1800bf556  jz      short loc_1800BF56C
0x1800bf558  lea     rcx, [rbp+0C0h+var_E8]; this
0x1800bf55c  call    ?Append@CUnicodeStringBuffer@Nt@BCL@@QEAAJG@Z; BCL::Nt::CUnicodeStringBuffer::Append(ushort)
0x1800bf561  mov     r14d, eax
0x1800bf564  test    eax, eax
0x1800bf566  js      loc_1800BF3A5
0x1800bf56c  mov     rax, cs:off_180136D58; "manifests"
0x1800bf573  lea     rdx, [rsp+1C0h+var_160]
0x1800bf578  lea     rcx, [rbp+0C0h+var_E8]
0x1800bf57c  mov     [rsp+1C0h+var_160], rax
0x1800bf581  mov     [rsp+1C0h+var_158], 9
0x1800bf58a  call    ??$public_Append@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800bf58f  mov     r14d, eax
0x1800bf592  test    eax, eax
0x1800bf594  js      loc_1800BF3A5
0x1800bf59a  mov     rax, [rbp+0C0h+var_D8]
0x1800bf59e  lea     rdx, [rdi+310h]
0x1800bf5a5  mov     rcx, [rsp+1C0h+var_168]
0x1800bf5aa  lea     r9, [rbp+0C0h+var_C8]
0x1800bf5ae  add     rax, rax
0x1800bf5b1  mov     r8d, 12019Fh
0x1800bf5b7  mov     [rbp+0C0h+var_C8], rax
0x1800bf5bb  mov     [rbp+0C0h+var_C0], rax
0x1800bf5bf  mov     rax, [rbp+0C0h+var_E8]
0x1800bf5c3  mov     [rbp+0C0h+var_B8], rax
0x1800bf5c7  call    ?Isolation_OpenDirectory@@YAJU_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@PEAU_ISOLATED_FILESYSTEM_OBJECT@234@KPEBU_LUNICODE_STRING@@@Z; Isolation_OpenDirectory(Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *,ulong,_LUNICODE_STRING const *)
0x1800bf5cc  mov     r14d, eax
0x1800bf5cf  test    eax, eax
0x1800bf5d1  js      loc_1800BF3A5
0x1800bf5d7  mov     r8, [rsp+1C0h+var_170]
0x1800bf5dc  lea     rax, g_LUNICODE_STRING__empty_
0x1800bf5e3  xorps   xmm0, xmm0
0x1800bf5e6  mov     [rbp+0C0h+var_B0], 30h ; '0'
0x1800bf5ee  test    rbx, rbx
0x1800bf5f1  mov     [rbp+0C0h+var_A8], r12
0x1800bf5f5  lea     r9, [rbp+0C0h+var_B0]
0x1800bf5f9  mov     [rbp+0C0h+var_98], 40h ; '@'
0x1800bf600  cmovnz  rax, rbx
0x1800bf604  mov     [rbp+0C0h+var_100], r12
0x1800bf608  mov     [rbp+0C0h+var_A0], rax
0x1800bf60c  mov     edx, r15d
0x1800bf60f  lea     rax, [rbp+0C0h+var_100]
0x1800bf613  mov     ecx, 4
0x1800bf618  mov     [rsp+1C0h+var_198], rax
0x1800bf61d  mov     [rsp+1C0h+var_1A0], r12
0x1800bf622  movdqu  [rbp+0C0h+var_90], xmm0
0x1800bf627  call    ?isoreghierarchy_CreateFromRegistryAndObjAttributes@@YAJKKU_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@PEBU_ISOLATED_OBJECT_ATTRIBUTES@234@PEAKPEAU_HIERARCHY@234@@Z; isoreghierarchy_CreateFromRegistryAndObjAttributes(ulong,ulong,Windows::Isolation::Rtl::_ISOLATED_REGISTRY,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,ulong *,Windows::Isolation::Rtl::_HIERARCHY *)
0x1800bf62c  mov     r14d, eax
0x1800bf62f  test    eax, eax
0x1800bf631  jns     short loc_1800BF641
0x1800bf633  lea     rcx, [rbp+0C0h+var_100]
0x1800bf637  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800bf63c  jmp     loc_1800BF3A5
0x1800bf641  lea     rax, g_LUNICODE_STRING_Assemblies
0x1800bf648  mov     rsi, r12
0x1800bf64b  mov     [rsp+1C0h+var_160], rax
0x1800bf650  mov     ebx, 1
0x1800bf655  lea     rax, [rdi+328h]
0x1800bf65c  mov     [rsp+1C0h+var_158], rax
0x1800bf661  lea     rax, g_LUNICODE_STRING_Components
0x1800bf668  mov     [rsp+1C0h+var_150], rax
0x1800bf66d  lea     rax, [rdi+330h]
0x1800bf674  mov     [rsp+1C0h+var_148], rax
0x1800bf679  lea     rax, g_LUNICODE_STRING_Installations
0x1800bf680  mov     [rbp+0C0h+var_140], rax
0x1800bf684  lea     rax, [rdi+338h]
0x1800bf68b  mov     [rbp+0C0h+var_138], rax
  ... truncated ...
```
