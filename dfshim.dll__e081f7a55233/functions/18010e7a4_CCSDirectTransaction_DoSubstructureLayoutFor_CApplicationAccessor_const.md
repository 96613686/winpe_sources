# CCSDirectTransaction::DoSubstructureLayoutFor(CApplicationAccessor const &)

- ea: `0x18010e7a4`
- end: `0x18010f171`
- name: `?DoSubstructureLayoutFor@CCSDirectTransaction@@IEAAJAEBVCApplicationAccessor@@@Z`
- size: `2509`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, const struct CApplicationAccessor *)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180111a90`

## callees

- `0x180012b1c`
- `0x180013e18`
- `0x180015418`
- `0x1800155c8`
- `0x180017514`
- `0x180017530`
- `0x180018bb8`
- `0x18001de74`
- `0x180027594`
- `0x180028ce4`
- `0x180029628`
- `0x18002d588`
- `0x18002e204`
- `0x18003fae0`
- `0x180040020`
- `0x180043644`
- `0x18004f2dc`
- `0x180050f7c`
- `0x1800a77cc`
- `0x1800bbc04`
- `0x1800bbf88`
- `0x1800bc3a0`
- `0x1800bdbe4`
- `0x1800be198`
- `0x1800c6a10`
- `0x1800c7904`
- `0x1800c8e90`
- `0x1800d4a04`
- `0x18010e614`
- `0x18010e7a4`
- `0x18010f178`
- `0x18010f348`
- `0x18010fb14`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010ef31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010f049`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010ef31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010f049`

## string_xrefs

- `0x18010e98a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010eed9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010eff9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010f0ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::DoSubstructureLayoutFor(
        CCSDirectTransaction *this,
        const struct CApplicationAccessor *a2)
{
  CCSDirectTransaction *v2; // rdi
  const struct CApplicationAccessor *v4; // rdx
  int DoesApplicationNeedSubstructure; // r12d
  signed int v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // r10
  unsigned int *v9; // r11
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // r9d
  int v22; // r8d
  __int64 v23; // rsi
  __int64 v25; // r10
  unsigned int *v26; // r11
  signed int v27; // ecx
  __int64 v28; // rcx
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  bool v31[8]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+88h] [rbp-78h]
  _BYTE v35[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+98h] [rbp-68h] BYREF
  __int128 *v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+B8h] [rbp-48h]
  __int128 v40; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-28h]
  _QWORD v42[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v43; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v45; // [rsp+100h] [rbp+0h]
  _OWORD v46[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+140h] [rbp+40h] BYREF
  __int64 v49; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v50[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v51; // [rsp+160h] [rbp+60h]
  _QWORD v52[4]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v53[10]; // [rsp+190h] [rbp+90h] BYREF
  char *v54; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v55; // [rsp+1E8h] [rbp+E8h] BYREF
  CCSDirectTransaction *v56; // [rsp+1F0h] [rbp+F0h]
  __int64 v57; // [rsp+1F8h] [rbp+F8h]
  _QWORD v58[2]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v59; // [rsp+210h] [rbp+110h] BYREF
  __int64 v60; // [rsp+220h] [rbp+120h]
  _QWORD v61[9]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v62; // [rsp+278h] [rbp+178h]
  __int64 v63; // [rsp+280h] [rbp+180h]
  __int64 v64; // [rsp+288h] [rbp+188h]
  char v65; // [rsp+290h] [rbp+190h]

  v56 = this;
  memset(v53, 0, sizeof(v53));
  v2 = this;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v48 = 0;
  v29 = 0;
  v30 = 0;
  v61[0] = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
  v31[0] = 0;
  DoesApplicationNeedSubstructure = CCSDirectTransaction::DoesApplicationNeedSubstructure(v2, v4, v31);
  if ( DoesApplicationNeedSubstructure < 0 )
  {
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
    Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
    goto LABEL_73;
  }
  v49 = *(_QWORD *)a2;
  Windows::Isolation::Rtl::RtlTrace(
    0,
    (unsigned int)&Windows::Isolation::Rtl::Facility_IsolationComponentStore,
    (struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *)1,
    (unsigned int)" Creating application substructure:\n   App: {app}\n   Needs it: {need}\n",
    (const char *const)2,
    (unsigned __int64)"app",
    Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_APPID,
    &v49,
    "need",
    Windows::Isolation::Rtl::RtlTraceFormat_PCBOOLEAN,
    v31);
  if ( !v31[0] )
  {
    DoesApplicationNeedSubstructure = 0;
LABEL_6:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
    Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
LABEL_7:
    if ( !v29 )
      goto LABEL_73;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v34 = -1073741595;
    v32 = (const wchar_t *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v29) )
    {
      goto LABEL_68;
    }
    LODWORD(v33) = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
    v6 = v34;
    goto LABEL_70;
  }
  DoesApplicationNeedSubstructure = RtlGetSystemIsolatedFilesystem(v7, *((_QWORD *)v2 + 96), &v29);
  if ( DoesApplicationNeedSubstructure < 0 )
    goto LABEL_6;
  DoesApplicationNeedSubstructure = CCSDirectTransaction::GetAppDirectoryForAppId(v2, *(_QWORD *)a2, &v30);
  if ( DoesApplicationNeedSubstructure < 0 )
    goto LABEL_14;
  v11 = **((_QWORD **)a2 + 3);
  while ( 1 )
  {
    v13 = (_QWORD *)*((_QWORD *)a2 + 3);
    if ( !v11 )
      break;
    v12 = v13[1];
    --v11;
    v42[0] = 0;
    DoesApplicationNeedSubstructure = CCSDirectTransaction::GetComponentManifest(v2, *(_QWORD *)(v12 + 8 * v11), v42);
    if ( DoesApplicationNeedSubstructure >= 0 )
    {
      DoesApplicationNeedSubstructure = CBulkReferenceStrengthener::AddStrongerCdf(&v43, v42[0]);
      if ( DoesApplicationNeedSubstructure >= 0 )
        continue;
    }
    goto LABEL_14;
  }
  v14 = v13 && *v13 ? *(_QWORD *)(v13[1] + 8LL * *v13 - 8) : 0LL;
  DoesApplicationNeedSubstructure = CComponentAccessor::Attach(v53, v14);
  if ( DoesApplicationNeedSubstructure < 0 )
  {
LABEL_14:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
    Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
    v10 = v30;
    if ( !v30 )
      goto LABEL_7;
LABEL_15:
    RtlCloseIsolatedFilesystemObjectHandle(v10);
    goto LABEL_7;
  }
  v15 = v30;
  v57 = (__int64)v2 + 904;
  DoesApplicationNeedSubstructure = CCSDirectTransaction::SubstructureCopyComponent(
                                      v2,
                                      (__int64)v2 + 904,
                                      (__int64)a2,
                                      (const struct CComponentAccessor *)v53,
                                      0,
                                      v30);
  if ( DoesApplicationNeedSubstructure < 0
    || ((v16 = (_QWORD *)*((_QWORD *)a2 + 3)) == 0 || !*v16 ? (v17 = 0) : (v17 = *(_QWORD *)(v16[1] + 8LL * *v16 - 8)),
        (DoesApplicationNeedSubstructure = CCSDirectTransaction::GetComponentManifest(v2, v17, &v48),
         DoesApplicationNeedSubstructure < 0)
     || (v65 = 0,
         DoesApplicationNeedSubstructure = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Attach(
                                             v61,
                                             v48),
         DoesApplicationNeedSubstructure < 0)) )
  {
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
    Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
    if ( !v15 )
      goto LABEL_7;
    v10 = v15;
    goto LABEL_15;
  }
  if ( v65 )
  {
    while ( 1 )
    {
      v54 = 0;
      CComponentAccessor::Close((CComponentAccessor *)v53);
      DoesApplicationNeedSubstructure = Windows::Cdf::Rtl::BindValue<Windows::Cms::Rtl::_CMS_ASSEMBLY_REFERENCE>(
                                          v48,
                                          HIDWORD(v61[v62 + 1]),
                                          &v54);
      if ( DoesApplicationNeedSubstructure < 0 )
        goto LABEL_63;
      if ( *v54 >= 0 )
      {
        v55 = 0;
        v49 = 0;
        v18 = LODWORD(v61[v62 + 1]);
        v42[0] = 0;
        v30 = 0;
        v40 = 0;
        v41 = 0;
        v36 = 0;
        v37 = 0;
        DoesApplicationNeedSubstructure = CdfpGetIdentityCommon_Windows::Isolation::Rtl::_REFERENCE_IDENTITY_(
                                            v48,
                                            v18,
                                            &v55);
        if ( DoesApplicationNeedSubstructure < 0
          || (DoesApplicationNeedSubstructure = CBulkReferenceStrengthener::Strengthen(&v43, v19, v55, &v49),
              DoesApplicationNeedSubstructure < 0) )
        {
          if ( v30 )
          {
            RtlCloseIsolatedFilesystemObjectHandle(v30);
            v30 = 0;
          }
          goto LABEL_94;
        }
        DoesApplicationNeedSubstructure = IsoConvertReferenceToDefinition(v49, v42);
        if ( DoesApplicationNeedSubstructure < 0 )
        {
          if ( v30 )
          {
            RtlCloseIsolatedFilesystemObjectHandle(v30);
            v30 = 0;
          }
          v28 = v42[0];
          if ( v42[0] )
LABEL_93:
            RtlCloseDefinitionIdentityHandle(v28);
LABEL_94:
          BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
          Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
          if ( v15 )
            RtlCloseIsolatedFilesystemObjectHandle(v15);
          if ( !v29 )
            goto LABEL_73;
          ++g_nRtlCloseIsolatedFilesystemHandle;
          LODWORD(v37) = -1073741595;
          *(_QWORD *)&v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            || !(unsigned __int8)RtlIsTypeSafeHandleValid(v29) )
          {
            DWORD2(v36) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
            v6 = (int)v37;
            goto LABEL_70;
          }
          goto LABEL_68;
        }
        v20 = v42[0];
        DoesApplicationNeedSubstructure = Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(
                                            v42[0],
                                            &g_LUNICODE_STRING_publicKeyToken,
                                            &v36);
        if ( DoesApplicationNeedSubstructure < 0 )
          goto LABEL_89;
        DoesApplicationNeedSubstructure = Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(
                                            v20,
                                            &g_LUNICODE_STRING_publicKeyToken,
                                            &v36);
        if ( DoesApplicationNeedSubstructure < 0 )
          goto LABEL_89;
        if ( (_QWORD)v36 )
        {
          DoesApplicationNeedSubstructure = Windows::Isolation::Rtl::CmsFindCodebaseForAssemblyReference(
                                              v48,
                                              HIDWORD(v61[v62 + 1]),
                                              &v40);
          if ( DoesApplicationNeedSubstructure < 0 )
            goto LABEL_89;
          if ( !(_QWORD)v40 )
            goto LABEL_49;
          v35[0] = 0;
          v60 = 0;
          v37 = 0;
          v59 = 0;
          v36 = 0;
          DoesApplicationNeedSubstructure = BCL::Nt::CUnicodeStringBuffer::Assign(
                                              (BCL::Nt::CUnicodeStringBuffer *)v50,
                                              (const struct _LUTF8_STRING *)&v40);
          if ( DoesApplicationNeedSubstructure < 0 )
            goto LABEL_89;
          v58[1] = 1;
          v58[0] = L"\\";
          v33 = 1;
          v32 = L"/";
          DoesApplicationNeedSubstructure = BCL::Nt::CUnicodeStringBuffer::Replace(
                                              (unsigned int)v50,
                                              (unsigned int)&v32,
                                              (unsigned int)v58,
                                              v21,
                                              (__int64)v35);
          if ( DoesApplicationNeedSubstructure < 0 )
            goto LABEL_89;
          v52[0] = 2 * v51;
          v52[1] = 2 * v51;
          v52[2] = v50[0];
          DoesApplicationNeedSubstructure = RtlSplitLUnicodeString(
                                              2,
                                              (unsigned int)v52,
                                              v22,
                                              0,
                                              92,
                                              (__int64)&v59,
                                              (__int64)&v36);
          if ( DoesApplicationNeedSubstructure < 0 )
            goto LABEL_89;
          if ( (_QWORD)v36 )
          {
            v37 = &v59;
            *(_QWORD *)&v36 = 48;
            *((_QWORD *)&v36 + 1) = v15;
            v38 = 64;
            v39 = 0;
            DoesApplicationNeedSubstructure = Windows::Isolation::Implementation::Rtl::CreateDirectories(
                                                0,
                                                v29,
                                                &v30,
                                                0,
                                                &v36);
            if ( DoesApplicationNeedSubstructure < 0 )
              goto LABEL_89;
            v23 = v30;
          }
          else
          {
LABEL_49:
            v23 = v15;
          }
          DoesApplicationNeedSubstructure = CComponentAccessor::Attach(v53, v20);
          if ( DoesApplicationNeedSubstructure < 0 )
          {
            if ( v30 )
            {
              RtlCloseIsolatedFilesystemObjectHandle(v30);
              v30 = 0;
            }
            if ( v20 )
              RtlCloseDefinitionIdentityHandle(v20);
            BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
            Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
            if ( v15 )
              RtlCloseIsolatedFilesystemObjectHandle(v15);
            if ( v29 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              LODWORD(v37) = -1073741595;
              *(_QWORD *)&v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v29) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v26 + 4))(*v26, v25);
                v27 = 0;
              }
              else
              {
                DWORD2(v36) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
                v27 = (int)v37;
              }
              if ( v27 < 0 )
                RaiseException(v27, 1u, 0, 0);
              v29 = 0;
            }
            goto LABEL_73;
          }
          DoesApplicationNeedSubstructure = CCSDirectTransaction::SubstructureCopyComponent(
                                              v56,
                                              v57,
                                              (__int64)a2,
                                              (const struct CComponentAccessor *)v53,
                                              *(_DWORD *)v54,
                                              v23);
          if ( DoesApplicationNeedSubstructure < 0 )
          {
LABEL_89:
            if ( v30 )
            {
              RtlCloseIsolatedFilesystemObjectHandle(v30);
              v30 = 0;
            }
            if ( v20 )
            {
              v28 = v20;
              goto LABEL_93;
            }
            goto LABEL_94;
          }
        }
        if ( v30 )
        {
          RtlCloseIsolatedFilesystemObjectHandle(v30);
          v30 = 0;
        }
        if ( v20 )
          RtlCloseDefinitionIdentityHandle(v20);
      }
      DoesApplicationNeedSubstructure = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Next(v61);
      if ( DoesApplicationNeedSubstructure < 0 )
        goto LABEL_63;
      if ( !v65 )
      {
        v2 = v56;
        break;
      }
    }
  }
  DoesApplicationNeedSubstructure = CCSDirectTransaction::MarkSubstructureConstructed(v2, a2);
  if ( DoesApplicationNeedSubstructure >= 0 )
    DoesApplicationNeedSubstructure = 0;
LABEL_63:
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v50);
  Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v61);
  if ( v15 )
    RtlCloseIsolatedFilesystemObjectHandle(v15);
  if ( v29 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    *(_QWORD *)&v40 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    LODWORD(v41) = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v29) )
    {
LABEL_68:
      (*((void (__fastcall **)(_QWORD, __int64))v9 + 4))(*v9, v8);
      v6 = 0;
      goto LABEL_70;
    }
    DWORD2(v40) = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
    v6 = v41;
LABEL_70:
    if ( v6 < 0 )
      RaiseException(v6, 1u, 0, 0);
    v29 = 0;
  }
LABEL_73:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CReferenceIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CReferenceIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>((char *)v46 + 8);
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v44);
  CComponentAccessor::~CComponentAccessor((CComponentAccessor *)v53);
  return (unsigned int)DoesApplicationNeedSubstructure;
}

```

## disassembly

```asm
0x18010e7a4  mov     [rsp-8+arg_10], rbx
0x18010e7a9  mov     [rsp-8+arg_18], rsi
0x18010e7ae  push    rbp
0x18010e7af  push    rdi
0x18010e7b0  push    r12
0x18010e7b2  push    r13
0x18010e7b4  push    r15
0x18010e7b6  lea     rbp, [rsp-1B0h]
0x18010e7be  sub     rsp, 2B0h
0x18010e7c5  mov     rax, cs:__security_cookie
0x18010e7cc  xor     rax, rsp
0x18010e7cf  mov     [rbp+1D0h+var_30], rax
0x18010e7d6  xor     esi, esi
0x18010e7d8  mov     [rbp+1D0h+var_E0], rcx
0x18010e7df  xorps   xmm0, xmm0
0x18010e7e2  mov     [rbp+1D0h+var_140], rsi
0x18010e7e9  mov     rdi, rcx
0x18010e7ec  mov     [rbp+1D0h+var_130], rsi
0x18010e7f3  xorps   xmm1, xmm1
0x18010e7f6  mov     [rbp+1D0h+var_138], rsi
0x18010e7fd  lea     rcx, [rbp+1D0h+var_180]; this
0x18010e801  mov     [rbp+1D0h+var_128], rsi
0x18010e808  mov     [rbp+1D0h+var_118], rsi
0x18010e80f  mov     r13, rdx
0x18010e812  mov     [rbp+1D0h+var_120], rsi
0x18010e819  mov     [rbp+1D0h+var_110], rsi
0x18010e820  mov     [rbp+1D0h+var_100], rsi
0x18010e827  mov     [rbp+1D0h+var_108], rsi
0x18010e82e  mov     [rbp+1D0h+var_F8], rsi
0x18010e835  mov     [rbp+1D0h+var_1E0], rsi
0x18010e839  mov     [rbp+1D0h+var_1D8], rsi
0x18010e83d  movdqa  [rbp+1D0h+var_1D0], xmm0
0x18010e842  movdqa  [rbp+1D0h+var_1C0], xmm1
0x18010e847  movdqa  [rbp+1D0h+var_1B0], xmm0
0x18010e84c  mov     [rbp+1D0h+var_1A0], rsi
0x18010e850  mov     [rbp+1D0h+var_190], rsi
0x18010e854  mov     [rsp+2D0h+var_270], rsi
0x18010e859  mov     [rsp+2D0h+var_268], rsi
0x18010e85e  mov     [rbp+1D0h+var_A0], rsi
0x18010e865  mov     [rbp+1D0h+var_58], rsi
0x18010e86c  mov     [rbp+1D0h+var_50], rsi
0x18010e873  mov     [rbp+1D0h+var_48], rsi
0x18010e87a  mov     [rbp+1D0h+var_40], sil
0x18010e881  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x18010e886  lea     r8, [rsp+2D0h+var_260]; bool *
0x18010e88b  mov     [rsp+2D0h+var_260], sil
0x18010e890  mov     rcx, rdi; this
0x18010e893  call    ?DoesApplicationNeedSubstructure@CCSDirectTransaction@@IEAAJAEBVCApplicationAccessor@@AEA_N@Z; CCSDirectTransaction::DoesApplicationNeedSubstructure(CApplicationAccessor const &,bool &)
0x18010e898  mov     r12d, eax
0x18010e89b  test    eax, eax
0x18010e89d  jns     short loc_18010E8E4
0x18010e89f  lea     rcx, [rbp+1D0h+var_180]; this
0x18010e8a3  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010e8a8  lea     rcx, [rbp+1D0h+var_A0]
0x18010e8af  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(void)
0x18010e8b4  mov     r10, [rsp+2D0h+var_270]
0x18010e8b9  test    r10, r10
0x18010e8bc  jz      loc_18010EF3C
0x18010e8c2  lea     r15d, [rsi+1]
0x18010e8c6  jmp     loc_18010E983
0x18010e8cb  mov     dword ptr [rbp+1D0h+var_250], 124h
0x18010e8d2  lea     rcx, [rsp+2D0h+var_258]
0x18010e8d7  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18010e8dc  mov     ecx, [rbp+1D0h+var_248]
0x18010e8df  jmp     loc_18010EF24
0x18010e8e4  mov     rax, [r13+0]
0x18010e8e8  lea     r9, aCreatingApplic; " Creating application substructure:\n  "...
0x18010e8ef  mov     [rbp+1D0h+var_188], rax
0x18010e8f3  lea     rdx, ?Facility_IsolationComponentStore@Rtl@Isolation@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x18010e8fa  lea     rax, [rsp+2D0h+var_260]
0x18010e8ff  mov     r15d, 1
0x18010e905  mov     [rsp+2D0h+var_280], rax
0x18010e90a  mov     r8d, r15d; struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *
0x18010e90d  lea     rax, ?RtlTraceFormat_PCBOOLEAN@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCBOOLEAN(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x18010e914  xor     ecx, ecx; this
0x18010e916  mov     [rsp+2D0h+var_288], rax
0x18010e91b  lea     rax, aNeed; "need"
0x18010e922  mov     [rsp+2D0h+var_290], rax
0x18010e927  lea     rax, [rbp+1D0h+var_188]
0x18010e92b  mov     [rsp+2D0h+var_298], rax
0x18010e930  lea     rax, ?RtlTraceFormat_PCDEFINITION_APPID@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_APPID(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x18010e937  mov     [rsp+2D0h+var_2A0], rax
0x18010e93c  lea     rax, aApp; "app"
0x18010e943  mov     [rsp+2D0h+var_2A8], rax; unsigned __int64
0x18010e948  mov     [rsp+2D0h+var_2B0], 2; char *
0x18010e951  call    ?RtlTrace@Rtl@Isolation@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@KQEBD_KZZ; Windows::Isolation::Rtl::RtlTrace(ulong,Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *,ulong,char const * const,unsigned __int64,...)
0x18010e956  cmp     [rsp+2D0h+var_260], sil
0x18010e95b  jnz     short loc_18010E9CE
0x18010e95d  mov     r12d, esi
0x18010e960  lea     rcx, [rbp+1D0h+var_180]; this
0x18010e964  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010e969  lea     rcx, [rbp+1D0h+var_A0]
0x18010e970  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(void)
0x18010e975  mov     r10, [rsp+2D0h+var_270]
0x18010e97a  test    r10, r10
0x18010e97d  jz      loc_18010EF3C
0x18010e983  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r15; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18010e98a  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010e991  mov     [rbp+1D0h+var_248], 0C00000E5h
0x18010e998  mov     [rsp+2D0h+var_258], rax
0x18010e99d  test    r10, r10
0x18010e9a0  jz      loc_18010EF22
0x18010e9a6  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18010e9ad  test    r11, r11
0x18010e9b0  jz      loc_18010E8CB
0x18010e9b6  mov     rdx, r11
0x18010e9b9  mov     rcx, r10
0x18010e9bc  call    RtlIsTypeSafeHandleValid
0x18010e9c1  test    al, al
0x18010e9c3  jz      loc_18010E8CB
0x18010e9c9  jmp     loc_18010EF13
0x18010e9ce  mov     rdx, [rdi+300h]
0x18010e9d5  lea     r8, [rsp+2D0h+var_270]
0x18010e9da  call    RtlGetSystemIsolatedFilesystem
0x18010e9df  mov     r12d, eax
0x18010e9e2  test    eax, eax
0x18010e9e4  js      loc_18010E960
0x18010e9ea  mov     rdx, [r13+0]
0x18010e9ee  lea     r8, [rsp+2D0h+var_268]
0x18010e9f3  mov     rcx, rdi
0x18010e9f6  call    ?GetAppDirectoryForAppId@CCSDirectTransaction@@AEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEAU_ISOLATED_FILESYSTEM_OBJECT@345@@Z; CCSDirectTransaction::GetAppDirectoryForAppId(Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x18010e9fb  mov     r12d, eax
0x18010e9fe  test    eax, eax
0x18010ea00  jns     short loc_18010EA2F
0x18010ea02  lea     rcx, [rbp+1D0h+var_180]; this
0x18010ea06  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010ea0b  lea     rcx, [rbp+1D0h+var_A0]
0x18010ea12  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(void)
0x18010ea17  mov     rcx, [rsp+2D0h+var_268]
0x18010ea1c  test    rcx, rcx
0x18010ea1f  jz      loc_18010E975
0x18010ea25  call    RtlCloseIsolatedFilesystemObjectHandle
0x18010ea2a  jmp     loc_18010E975
0x18010ea2f  mov     rax, [r13+18h]
0x18010ea33  mov     rbx, [rax]
0x18010ea36  jmp     short loc_18010EA6E
0x18010ea38  mov     rdx, [rax+8]
0x18010ea3c  lea     r8, [rbp+1D0h+var_1F0]
0x18010ea40  sub     rbx, r15
0x18010ea43  mov     [rbp+1D0h+var_1F0], rsi
0x18010ea47  mov     rcx, rdi
0x18010ea4a  mov     rdx, [rdx+rbx*8]
0x18010ea4e  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_CDF@3Cdf@5@@Z; CCSDirectTransaction::GetComponentManifest(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Cdf::Rtl::_CDF &)
0x18010ea53  mov     r12d, eax
0x18010ea56  test    eax, eax
0x18010ea58  js      short loc_18010EA02
0x18010ea5a  mov     rdx, [rbp+1D0h+var_1F0]
0x18010ea5e  lea     rcx, [rbp+1D0h+var_1E0]
0x18010ea62  call    ?AddStrongerCdf@CBulkReferenceStrengthener@@QEAAJU_CDF@Rtl@Cdf@Windows@@@Z; CBulkReferenceStrengthener::AddStrongerCdf(Windows::Cdf::Rtl::_CDF)
0x18010ea67  mov     r12d, eax
0x18010ea6a  test    eax, eax
0x18010ea6c  js      short loc_18010EA02
0x18010ea6e  mov     rax, [r13+18h]
0x18010ea72  test    rbx, rbx
0x18010ea75  jnz     short loc_18010EA38
0x18010ea77  test    rax, rax
0x18010ea7a  jz      short loc_18010EA8F
0x18010ea7c  mov     rcx, [rax]
0x18010ea7f  test    rcx, rcx
0x18010ea82  jz      short loc_18010EA8F
0x18010ea84  mov     rax, [rax+8]
0x18010ea88  mov     rdx, [rax+rcx*8-8]
0x18010ea8d  jmp     short loc_18010EA92
0x18010ea8f  mov     rdx, rsi
0x18010ea92  lea     rcx, [rbp+1D0h+var_140]
0x18010ea99  call    ?Attach@CComponentAccessor@@QEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; CComponentAccessor::Attach(Windows::Isolation::Rtl::_DEFINITION_IDENTITY)
0x18010ea9e  mov     r12d, eax
0x18010eaa1  test    eax, eax
0x18010eaa3  js      loc_18010EA02
0x18010eaa9  mov     rbx, [rsp+2D0h+var_268]
0x18010eaae  lea     rax, [rdi+388h]
0x18010eab5  mov     [rsp+2D0h+var_2A8], rbx
0x18010eaba  lea     r9, [rbp+1D0h+var_140]
0x18010eac1  mov     rdx, rax
0x18010eac4  mov     dword ptr [rsp+2D0h+var_2B0], esi
0x18010eac8  mov     r8, r13
0x18010eacb  mov     [rbp+1D0h+var_D8], rax
0x18010ead2  mov     rcx, rdi
0x18010ead5  call    ?SubstructureCopyComponent@CCSDirectTransaction@@IEAAJPEAVCCSDirect@@AEBVCApplicationAccessor@@AEBVCComponentAccessor@@KU_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@@Z; CCSDirectTransaction::SubstructureCopyComponent(CCSDirect *,CApplicationAccessor const &,CComponentAccessor const &,ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT)
0x18010eada  mov     r12d, eax
0x18010eadd  test    eax, eax
0x18010eadf  jns     short loc_18010EB07
0x18010eae1  lea     rcx, [rbp+1D0h+var_180]; this
0x18010eae5  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010eaea  lea     rcx, [rbp+1D0h+var_A0]
0x18010eaf1  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(void)
0x18010eaf6  test    rbx, rbx
0x18010eaf9  jz      loc_18010E975
0x18010eaff  mov     rcx, rbx
0x18010eb02  jmp     loc_18010EA25
0x18010eb07  mov     rax, [r13+18h]
0x18010eb0b  test    rax, rax
0x18010eb0e  jz      short loc_18010EB23
0x18010eb10  mov     rcx, [rax]
0x18010eb13  test    rcx, rcx
0x18010eb16  jz      short loc_18010EB23
0x18010eb18  mov     rax, [rax+8]
0x18010eb1c  mov     rdx, [rax+rcx*8-8]
0x18010eb21  jmp     short loc_18010EB26
0x18010eb23  mov     rdx, rsi
0x18010eb26  lea     r8, [rbp+1D0h+var_190]
0x18010eb2a  mov     rcx, rdi
0x18010eb2d  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_CDF@3Cdf@5@@Z; CCSDirectTransaction::GetComponentManifest(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Cdf::Rtl::_CDF &)
0x18010eb32  mov     r12d, eax
0x18010eb35  test    eax, eax
0x18010eb37  js      short loc_18010EAE1
0x18010eb39  mov     rdx, [rbp+1D0h+var_190]
0x18010eb3d  lea     rcx, [rbp+1D0h+var_A0]
0x18010eb44  mov     [rbp+1D0h+var_40], sil
0x18010eb4b  call    ?Attach@?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAAJU_CDF@234@K_KPEBU_CDF_TABLE_AND_KEY@234@@Z; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Attach(Windows::Cdf::Rtl::_CDF,ulong,unsigned __int64,Windows::Cdf::Rtl::_CDF_TABLE_AND_KEY const *)
0x18010eb50  mov     r12d, eax
0x18010eb53  test    eax, eax
0x18010eb55  js      short loc_18010EAE1
0x18010eb57  cmp     [rbp+1D0h+var_40], sil
0x18010eb5e  jz      loc_18010EE91
0x18010eb64  lea     rcx, [rbp+1D0h+var_140]; this
0x18010eb6b  mov     [rbp+1D0h+var_F0], rsi
0x18010eb72  call    ?Close@CComponentAccessor@@QEAAXXZ; CComponentAccessor::Close(void)
0x18010eb77  mov     rdx, [rbp+1D0h+var_58]
0x18010eb7e  lea     r8, [rbp+1D0h+var_F0]
0x18010eb85  mov     rcx, [rbp+1D0h+var_190]
0x18010eb89  mov     edx, [rbp+rdx*8+1D0h+var_94]
0x18010eb90  call    ??$BindValue@U_CMS_ASSEMBLY_REFERENCE@Rtl@Cms@Windows@@@Rtl@Cdf@Windows@@YAJU_CDF@012@U_CDF_BLOBID@012@AEAPEBU_CMS_ASSEMBLY_REFERENCE@0Cms@2@@Z; Windows::Cdf::Rtl::BindValue<Windows::Cms::Rtl::_CMS_ASSEMBLY_REFERENCE>(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,Windows::Cms::Rtl::_CMS_ASSEMBLY_REFERENCE const * &)
0x18010eb95  mov     r12d, eax
0x18010eb98  test    eax, eax
0x18010eb9a  js      loc_18010F150
0x18010eba0  mov     rax, [rbp+1D0h+var_F0]
0x18010eba7  test    byte ptr [rax], 80h
0x18010ebaa  jnz     loc_18010EE66
0x18010ebb0  mov     rdx, [rbp+1D0h+var_58]
0x18010ebb7  lea     r8, [rbp+1D0h+var_E8]
0x18010ebbe  mov     rcx, [rbp+1D0h+var_190]
0x18010ebc2  xor     eax, eax
0x18010ebc4  xorps   xmm0, xmm0
0x18010ebc7  mov     [rbp+1D0h+var_E8], rsi
0x18010ebce  xorps   xmm1, xmm1
0x18010ebd1  mov     [rbp+1D0h+var_188], rsi
0x18010ebd5  mov     edx, [rbp+rdx*8+1D0h+var_98]
0x18010ebdc  mov     [rbp+1D0h+var_1F0], rsi
0x18010ebe0  mov     [rsp+2D0h+var_268], rsi
0x18010ebe5  movups  [rbp+1D0h+var_208], xmm0
0x18010ebe9  mov     [rbp+1D0h+var_1F8], rax
0x18010ebed  movups  [rbp+1D0h+var_238], xmm1
0x18010ebf1  mov     [rbp+1D0h+var_228], rax
0x18010ebf5  call    CdfpGetIdentityCommon_Windows__Isolation__Rtl___REFERENCE_IDENTITY_
0x18010ebfa  mov     r12d, eax
0x18010ebfd  test    eax, eax
0x18010ebff  js      loc_18010F133
0x18010ec05  mov     r8, [rbp+1D0h+var_E8]
0x18010ec0c  lea     r9, [rbp+1D0h+var_188]
0x18010ec10  lea     rcx, [rbp+1D0h+var_1E0]
0x18010ec14  call    ?Strengthen@CBulkReferenceStrengthener@@QEAAJKU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEAU2345@@Z; CBulkReferenceStrengthener::Strengthen(ulong,Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::Isolation::Rtl::_REFERENCE_IDENTITY &)
0x18010ec19  mov     r12d, eax
0x18010ec1c  test    eax, eax
0x18010ec1e  js      loc_18010F133
0x18010ec24  mov     rcx, [rbp+1D0h+var_188]
0x18010ec28  lea     rdx, [rbp+1D0h+var_1F0]
0x18010ec2c  call    ?IsoConvertReferenceToDefinition@@YAJU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEAU_DEFINITION_IDENTITY@234@@Z; IsoConvertReferenceToDefinition(Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::Isolation::Rtl::_DEFINITION_IDENTITY &)
0x18010ec31  mov     r12d, eax
0x18010ec34  test    eax, eax
0x18010ec36  js      loc_18010F10D
0x18010ec3c  mov     rdi, [rbp+1D0h+var_1F0]
0x18010ec40  lea     r8, [rbp+1D0h+var_238]
0x18010ec44  mov     rcx, rdi
0x18010ec47  lea     rdx, g_LUNICODE_STRING_publicKeyToken
0x18010ec4e  call    ??$GetAttribute@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@U_LUNICODE_STRING@@@Rtl@Isolation@Windows@@YAJU_DEFINITION_IDENTITY@012@AEBU_LUNICODE_STRING@@AEAU4@@Z; Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING const &,_LUNICODE_STRING &)
0x18010ec53  mov     r12d, eax
0x18010ec56  test    eax, eax
0x18010ec58  js      loc_18010F072
0x18010ec5e  lea     r8, [rbp+1D0h+var_238]
0x18010ec62  mov     rcx, rdi
0x18010ec65  lea     rdx, g_LUNICODE_STRING_publicKeyToken
0x18010ec6c  call    ??$GetAttribute@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@U_LUNICODE_STRING@@@Rtl@Isolation@Windows@@YAJU_DEFINITION_IDENTITY@012@AEBU_LUNICODE_STRING@@AEAU4@@Z; Windows::Isolation::Rtl::GetAttribute<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING>(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING const &,_LUNICODE_STRING &)
0x18010ec71  mov     r12d, eax
0x18010ec74  test    eax, eax
0x18010ec76  js      loc_18010F072
0x18010ec7c  cmp     qword ptr [rbp+1D0h+var_238], rsi
0x18010ec80  jz      loc_18010EE45
0x18010ec86  mov     rdx, [rbp+1D0h+var_58]
0x18010ec8d  lea     r8, [rbp+1D0h+var_208]
0x18010ec91  mov     rcx, [rbp+1D0h+var_190]
0x18010ec95  mov     edx, [rbp+rdx*8+1D0h+var_94]
0x18010ec9c  call    ?CmsFindCodebaseForAssemblyReference@Rtl@Isolation@Windows@@YAJU_CDF@1Cdf@3@U_CDF_BLOBID@153@PEAU_LUTF8_STRING@@@Z; Windows::Isolation::Rtl::CmsFindCodebaseForAssemblyReference(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_LUTF8_STRING *)
0x18010eca1  mov     r12d, eax
0x18010eca4  test    eax, eax
0x18010eca6  js      loc_18010F072
0x18010ecac  cmp     qword ptr [rbp+1D0h+var_208], rsi
0x18010ecb0  jz      loc_18010ED97
0x18010ecb6  xor     eax, eax
0x18010ecb8  mov     [rbp+1D0h+var_240], sil
0x18010ecbc  xorps   xmm0, xmm0
0x18010ecbf  mov     [rbp+1D0h+var_B0], rax
0x18010ecc6  xorps   xmm1, xmm1
0x18010ecc9  mov     [rbp+1D0h+var_228], rax
0x18010eccd  lea     rdx, [rbp+1D0h+var_208]; struct _LUTF8_STRING *
0x18010ecd1  lea     rcx, [rbp+1D0h+var_180]; this
0x18010ecd5  movups  [rbp+1D0h+var_C0], xmm0
0x18010ecdc  movups  [rbp+1D0h+var_238], xmm1
0x18010ece0  call    ?Assign@CUnicodeStringBuffer@Nt@BCL@@QEAAJPEBU_LUTF8_STRING@@@Z; BCL::Nt::CUnicodeStringBuffer::Assign(_LUTF8_STRING const *)
0x18010ece5  mov     r12d, eax
  ... truncated ...
```
