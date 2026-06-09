# CCSDirectTransaction::SubstructureCopyComponent(CCSDirect *,CApplicationAccessor const &,CComponentAccessor const &,ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT)

- ea: `0x18010fb14`
- end: `0x18011095d`
- name: `?SubstructureCopyComponent@CCSDirectTransaction@@IEAAJPEAVCCSDirect@@AEBVCApplicationAccessor@@AEBVCComponentAccessor@@KU_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@@Z`
- size: `3657`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18010e7a4`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x180013de8`
- `0x180013e18`
- `0x18001559c`
- `0x180017514`
- `0x180017530`
- `0x180018b30`
- `0x18001d478`
- `0x18001de74`
- `0x18001e608`
- `0x180023cb8`
- `0x180029628`
- `0x18002d588`
- `0x18003f260`
- `0x18003f31c`
- `0x18003fae0`
- `0x180040020`
- `0x180043cc0`
- `0x18004f2dc`
- `0x180050f7c`
- `0x1800b1a64`
- `0x1800b2058`
- `0x1800b2338`
- `0x1800b4584`
- `0x1800bbbc8`
- `0x1800bc2fc`
- `0x1800bdf30`
- `0x1800be06c`
- `0x1800bfb4c`
- `0x1800c8de4`
- `0x1800fe440`
- `0x18010fb14`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010fd26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110036`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110674`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801108fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18010fd26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110036`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110674`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801108fb`

## string_xrefs

- `0x18010fc2f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010fcd4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010ffe5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1801105fe`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1801107fa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1801108a5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18010fb4c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_substructure.cpp`
- `0x180110722`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_substructure.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::SubstructureCopyComponent(
        CCSDirectTransaction *a1,
        __int64 a2,
        __int64 a3,
        const struct CComponentAccessor *a4,
        char a5,
        __int64 a6)
{
  const struct CComponentAccessor *v8; // r9
  int ComponentManifest; // r14d
  __int64 v10; // r10
  unsigned int *v11; // r11
  signed int v12; // ecx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r15
  __int64 *v18; // r12
  void *v19; // rcx
  void *v20; // rcx
  __int64 v21; // r10
  unsigned int *v22; // r11
  signed int v23; // ecx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // r9d
  int v28; // r8d
  __int64 v29; // rcx
  __int128 *v30; // rax
  __int64 v31; // rdx
  _QWORD *v32; // r15
  int v33; // r9d
  __int64 v34; // r10
  signed int v35; // ecx
  void *v36; // rcx
  void *v37; // rcx
  __int64 v38; // r10
  void *v39; // rcx
  void *v40; // rcx
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+48h] [rbp-B8h] BYREF
  const char *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h]
  char v47[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h]
  void *lpMem; // [rsp+88h] [rbp-78h]
  __int64 v52; // [rsp+90h] [rbp-70h] BYREF
  __int64 v53; // [rsp+98h] [rbp-68h]
  void *v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v57[56]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v58; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v59; // [rsp+F8h] [rbp-8h]
  int v60; // [rsp+108h] [rbp+8h]
  __int128 v61; // [rsp+110h] [rbp+10h]
  __int128 v62; // [rsp+120h] [rbp+20h] BYREF
  __int64 v63; // [rsp+130h] [rbp+30h]
  const wchar_t *v64; // [rsp+138h] [rbp+38h] BYREF
  __int64 v65; // [rsp+140h] [rbp+40h]
  int v66; // [rsp+148h] [rbp+48h]
  __int128 v67; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v68; // [rsp+160h] [rbp+60h]
  _BYTE v69[24]; // [rsp+168h] [rbp+68h]
  _OWORD v70[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v71; // [rsp+1A0h] [rbp+A0h]
  __m128i *v72; // [rsp+1A8h] [rbp+A8h]
  int v73[2]; // [rsp+1B0h] [rbp+B0h]
  __int128 v74; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v75; // [rsp+1C8h] [rbp+C8h]
  __int64 v76; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v77; // [rsp+1D8h] [rbp+D8h]
  char *v78; // [rsp+1E0h] [rbp+E0h]
  int v79; // [rsp+1E8h] [rbp+E8h]
  __int128 v80; // [rsp+1F0h] [rbp+F0h]
  _BYTE v81[8]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v82; // [rsp+208h] [rbp+108h]
  __int128 v83; // [rsp+210h] [rbp+110h] BYREF
  __int64 v84; // [rsp+220h] [rbp+120h]
  _QWORD v85[3]; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v86[33]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v87; // [rsp+348h] [rbp+248h]
  __int64 v88; // [rsp+350h] [rbp+250h]
  __int64 v89; // [rsp+358h] [rbp+258h]
  char v90; // [rsp+360h] [rbp+260h]
  __m128i si128; // [rsp+370h] [rbp+270h] BYREF

  *(_QWORD *)&v62 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_substructure.cpp";
  v82 = a3;
  v72 = &si128;
  v71 = 4;
  *(_QWORD *)v73 = 0;
  LODWORD(v63) = -1073741595;
  si128 = _mm_load_si128((const __m128i *)&_xmm_c0000043c0000034c000003ac0000035);
  v56 = 0;
  v86[0] = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v42 = 0;
  v43 = 0;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
  ComponentManifest = CCSDirectTransaction::GetComponentManifest(a1, v8, (struct Windows::Cdf::Rtl::_CDF *)&v56);
  if ( ComponentManifest < 0 )
  {
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
    goto LABEL_116;
  }
  v13 = v56;
  if ( !v56 )
  {
    if ( (a5 & 1) != 0 )
    {
      ComponentManifest = 0;
      goto LABEL_93;
    }
    DWORD2(v62) = 350;
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
    Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>(v86);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v62);
    return (unsigned int)v63;
  }
  ComponentManifest = CCSDirectTransaction::GetComponentDirectory(
                        a1,
                        a4,
                        (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)&v43);
  if ( ComponentManifest < 0 )
  {
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
    if ( v43 )
    {
      RtlCloseIsolatedFilesystemObjectHandle(v43);
      v43 = 0;
    }
    goto LABEL_116;
  }
  v90 = 0;
  ComponentManifest = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::Attach(
                        v86,
                        v13,
                        1);
  if ( ComponentManifest < 0 )
    goto LABEL_93;
  ComponentManifest = RtlGetSystemIsolatedFilesystem(v14, *((_QWORD *)a1 + 96), &v42);
  if ( ComponentManifest < 0 )
    goto LABEL_93;
  v16 = *(_QWORD *)a4;
  v53 = 0;
  v67 = 0;
  *(_OWORD *)v69 = g_LUNICODE_STRING_name;
  v52 = 0;
  v54 = 0;
  memset(v70, 0, 24);
  v50 = 0;
  v49 = 0;
  lpMem = 0;
  v68 = 0;
  *(_QWORD *)&v69[16] = L"name";
  ComponentManifest = RtlGetDefinitionIdentityAttributeValue(v15, v16, &v67);
  if ( ComponentManifest < 0 )
  {
    v39 = lpMem;
    if ( lpMem )
    {
      v50 = 0;
      v49 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v39);
    }
    v40 = v54;
    if ( v54 )
    {
      v53 = 0;
      v52 = 0;
      v54 = 0;
      IsolationFreeStringRoutine(v40);
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
    if ( v43 )
    {
      ((void (*)(void))RtlCloseIsolatedFilesystemObjectHandle)();
      v43 = 0;
    }
    if ( v42 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      LODWORD(v75) = -1073741595;
      *(_QWORD *)&v74 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v42) )
      {
        goto LABEL_111;
      }
      DWORD2(v74) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v74);
      v12 = v75;
      goto LABEL_113;
    }
    goto LABEL_116;
  }
  v17 = *(_QWORD *)&v70[0];
  v58 = *(_QWORD *)&v70[0];
  v59 = *(_OWORD *)((char *)v70 + 8);
  ComponentManifest = RtlAllocateLUnicodeString(*(_QWORD *)&v70[0] + 18LL, &v52);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(&v58, &v52);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  v18 = (__int64 *)((char *)a4 + 8);
  ComponentManifest = RtlAllocateLUnicodeString(*v18 + 18, &v49);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(v18, &v49);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(&g_LUNICODE_STRING__dot_manifest, &v49);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(&g_LUNICODE_STRING__dot_manifest, &v52);
  if ( ComponentManifest < 0 )
    goto LABEL_26;
  *((_QWORD *)&v67 + 1) = a6;
  *(_DWORD *)v69 = 64;
  v60 = 64;
  v68 = &v52;
  *(_QWORD *)&v59 = *((_QWORD *)a1 + 98);
  *((_QWORD *)&v59 + 1) = &v49;
  *(_QWORD *)&v67 = 48;
  *(_OWORD *)&v69[8] = 0;
  v58 = 48;
  v61 = 0;
  ComponentManifest = RtlIsolatedFilesystemCreateHardLinkOrCopyFile(48, v42, &v58);
  if ( ComponentManifest < 0 )
  {
LABEL_26:
    v19 = lpMem;
    if ( lpMem )
    {
      v50 = 0;
      v49 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v19);
    }
    v20 = v54;
    if ( v54 )
    {
      v53 = 0;
      v52 = 0;
      v54 = 0;
      IsolationFreeStringRoutine(v20);
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
    if ( v43 )
    {
      RtlCloseIsolatedFilesystemObjectHandle(v43);
      v43 = 0;
    }
    if ( v42 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      LODWORD(v46) = -1073741595;
      v44 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v42) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v22 + 4))(*v22, v21);
        v23 = 0;
      }
      else
      {
        LODWORD(v45) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v44);
        v23 = v46;
      }
      if ( v23 < 0 )
        RaiseException(v23, 1u, 0, 0);
      v42 = 0;
    }
    goto LABEL_116;
  }
  v49 = *v18;
  v52 = v17;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(&g_LUNICODE_STRING__dot_cdf_dash_ms, &v49);
  if ( ComponentManifest < 0 )
    goto LABEL_89;
  ComponentManifest = RtlAppendLUnicodeStringToLUnicodeString(&g_LUNICODE_STRING__dot_cdf_dash_ms, &v52);
  if ( ComponentManifest < 0 )
    goto LABEL_89;
  *((_QWORD *)&v67 + 1) = a6;
  *(_QWORD *)&v67 = 48;
  *(_DWORD *)v69 = 64;
  v60 = 64;
  v68 = &v52;
  *(_QWORD *)&v59 = *((_QWORD *)a1 + 98);
  *((_QWORD *)&v59 + 1) = &v49;
  *(_OWORD *)&v69[8] = 0;
  v58 = 48;
  v61 = 0;
  ComponentManifest = RtlIsolatedFilesystemCreateHardLinkOrCopyFile(48, v42, &v58);
  if ( ComponentManifest < 0 )
  {
LABEL_89:
    v36 = lpMem;
    if ( lpMem )
    {
      v50 = 0;
      v49 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v36);
    }
    v37 = v54;
    if ( v54 )
    {
      v53 = 0;
      v52 = 0;
      v54 = 0;
      IsolationFreeStringRoutine(v37);
    }
    goto LABEL_93;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v90 )
      {
        ComponentManifest = 0;
LABEL_98:
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
        BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v43);
        if ( !v42 )
          goto LABEL_116;
        ++g_nRtlCloseIsolatedFilesystemHandle;
        v44 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        LODWORD(v46) = -1073741595;
        if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v42) )
        {
          if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
          {
            LODWORD(v45) = 293;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
              &v44,
              &v44);
            goto LABEL_7;
          }
          (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                                  + 32))(
            *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
            v38);
          goto LABEL_112;
        }
LABEL_6:
        LODWORD(v45) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v44);
LABEL_7:
        v12 = v46;
LABEL_113:
        if ( v12 < 0 )
          RaiseException(v12, 1u, 0, 0);
        v42 = 0;
        goto LABEL_116;
      }
      v56 = 0;
      v47[0] = 0;
      v48 = 0;
      v24 = LODWORD(v86[4 * v87 + 4]);
      v58 = 48;
      *(_QWORD *)&v59 = 0;
      *((_QWORD *)&v59 + 1) = &g_LUNICODE_STRING__empty_;
      v60 = 64;
      v61 = 0;
      v55 = 0;
      ComponentManifest = Windows::Cdf::Rtl::BindValue<Windows::Cms::Rtl::_CMS_ASSEMBLY_REFERENCE>(v13, v24, &v55);
      if ( ComponentManifest < 0 )
        goto LABEL_86;
      if ( *(_DWORD *)(v55 + 52) != 2 )
        break;
      v25 = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::Next(v86);
      v26 = v48;
      ComponentManifest = v25;
      if ( v25 < 0 )
        goto LABEL_87;
      if ( v48 )
        RtlCloseIsolatedFilesystemObjectHandle(v48);
    }
    ComponentManifest = BCL::Nt::CUnicodeStringBuffer::Assign(
                          (BCL::Nt::CUnicodeStringBuffer *)v57,
                          (const struct _LUTF8_STRING *)&v86[4 * v87 + 1]);
    if ( ComponentManifest < 0 )
    {
LABEL_86:
      v26 = v48;
LABEL_87:
      if ( v26 )
      {
        ((void (*)(void))RtlCloseIsolatedFilesystemObjectHandle)();
        v48 = 0;
      }
      goto LABEL_89;
    }
    v85[1] = 1;
    v85[0] = L"\\";
    v65 = 1;
    v64 = L"/";
    ComponentManifest = BCL::Nt::CUnicodeStringBuffer::Replace(
                          (unsigned int)v57,
                          (unsigned int)&v64,
                          (unsigned int)v85,
                          v27,
                          (__int64)v47);
    if ( ComponentManifest < 0 )
      goto LABEL_69;
    *(_QWORD *)&v67 = 0;
    BCL::CConstPureStringAccessor<BCL::Nt::CUnicodeStringBufferTraits>::Attach(&v67, v57);
    v63 = 0;
    v62 = 0;
    *(_QWORD *)&v62 = 2LL * *(_QWORD *)(v67 + 16);
    *((_QWORD *)&v62 + 1) = 2LL * *(_QWORD *)(v67 + 8) - 2;
    v63 = *(_QWORD *)v67;
    v84 = 0;
    v75 = 0;
    v83 = 0;
    v74 = 0;
    ComponentManifest = RtlSplitLUnicodeString(2, (unsigned int)&v62, v28, 0, 92, (__int64)&v83, (__int64)&v74);
    if ( ComponentManifest < 0 )
      goto LABEL_68;
    if ( (_QWORD)v74 && (_QWORD)v83 )
    {
      v78 = (char *)&v83;
      v76 = 48;
      v77 = a6;
      v79 = 64;
      v80 = 0;
      ComponentManifest = Windows::Isolation::Implementation::Rtl::CreateDirectories(0, v42, &v48, 2032127, &v76);
      if ( ComponentManifest < 0 )
        goto LABEL_68;
      *(_QWORD *)&v59 = v48;
      v30 = &v74;
    }
    else
    {
      *(_QWORD *)&v59 = a6;
      v30 = &v62;
    }
    *((_QWORD *)&v59 + 1) = v30;
    v77 = v43;
    v78 = (char *)&v62;
    v73[0] = 0;
    v76 = 48;
    v79 = 64;
    v80 = 0;
    ComponentManifest = RtlIsolatedFilesystemCreateHardLinkOrCopyFile(v29, v42, &v76);
    if ( ComponentManifest < 0 )
      goto LABEL_68;
    if ( v73[0] != -1073741772 && v73[0] != -1073741766 )
    {
      *(_QWORD *)&v59 = v18;
      v58 = v82 + 48;
      v45 = 0;
      *((_QWORD *)&v59 + 1) = g_LUNICODE_STRING_Files;
      v78 = v47;
      v44 = 0;
      v46 = 0;
      v55 = 0;
      v47[0] = 1;
      v76 = 1;
      v77 = 1;
      ComponentManifest = SanitizeString((const struct _LUNICODE_STRING *)&v62, (struct _LUNICODE_STRING *)&v44);
      if ( ComponentManifest < 0
        || (ComponentManifest = *(_DWORD *)BCL::CSmartPtr<BCL::Nt::CSmartPtrTraits<CCSDirectTransaction::CPendingRegistryWrite>>::Allocate(
                                             &v55,
                                             v81),
            ComponentManifest < 0) )
      {
        BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v55);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v44);
        BCL::Nt::CConstUnicodeStringBufferAccessor::~CConstUnicodeStringBufferAccessor((BCL::Nt::CConstUnicodeStringBufferAccessor *)&v67);
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v48);
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v56);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
        BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v43);
        goto LABEL_95;
      }
      v32 = (_QWORD *)v55;
      ComponentManifest = CCSDirectTransaction::CPendingRegistryWrite::Initialize(v55, v31, 3, &v58, &v44, &v76);
      if ( ComponentManifest >= 0 )
      {
        v55 = 0;
        v32[12] = *((_QWORD *)a1 + 85);
        v32[11] = (char *)a1 + 672;
        **((_QWORD **)a1 + 85) = v32 + 11;
        *((_QWORD *)a1 + 85) = v32 + 11;
        v32[13] = (char *)a1 + 672;
        ++*((_QWORD *)a1 + 88);
        BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v55);
        Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v44);
        goto LABEL_66;
      }
      BCL::Nt::CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>::~CSmartPtr<CCSDirectTransaction::CPendingRegistryWrite>(&v55);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v44);
      BCL::Nt::CConstUnicodeStringBufferAccessor::~CConstUnicodeStringBufferAccessor((BCL::Nt::CConstUnicodeStringBufferAccessor *)&v67);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v48);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v56);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
      Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v43);
      if ( !v42 )
        goto LABEL_116;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v66 = -1073741595;
      v64 = (const wchar_t *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( (unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(v42) )
      {
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                                                  + 32))(
            *(unsigned int *)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti,
            v34);
          v35 = 0;
          goto LABEL_79;
        }
        LODWORD(v65) = 293;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v64,
          &v64);
      }
      else
      {
        LODWORD(v65) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v64);
      }
      v35 = v66;
LABEL_79:
      if ( v35 < 0 )
        RaiseException(v35, 1u, 0, 0);
      v42 = 0;
      goto LABEL_116;
    }
    v55 = 0;
    ComponentManifest = Windows::Cdf::Rtl::BindValue<Windows::Cms::Rtl::_CMS_ASSEMBLY_REFERENCE>(
                          v13,
                          LODWORD(v86[4 * v87 + 4]),
                          &v55);
    if ( ComponentManifest < 0 )
      goto LABEL_68;
    if ( (*(_BYTE *)(v55 + 44) & 1) == 0 )
      break;
LABEL_66:
    ComponentManifest = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::Next(v86);
    if ( ComponentManifest < 0 )
    {
      BCL::Nt::CConstUnicodeStringBufferAccessor::~CConstUnicodeStringBufferAccessor((BCL::Nt::CConstUnicodeStringBufferAccessor *)&v67);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v48);
      Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v56);
      goto LABEL_98;
    }
    BCL::Nt::CConstUnicodeStringBufferAccessor::~CConstUnicodeStringBufferAccessor((BCL::Nt::CConstUnicodeStringBufferAccessor *)&v67);
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v48);
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_FILESYSTEM_OBJECT_Traits>::Close(&v56);
  }
  ComponentManifest = v73[0];
  Windows::ErrorHandling::COM::ReportNtErrorOrigination(
    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_substructure.cpp",
    (const char *)0x1DA,
    v73[0],
    v33);
LABEL_68:
  BCL::Nt::CConstUnicodeStringBufferAccessor::~CConstUnicodeStringBufferAccessor((BCL::Nt::CConstUnicodeStringBufferAccessor *)&v67);
LABEL_69:
  if ( v48 )
  {
    ((void (*)(void))RtlCloseIsolatedFilesystemObjectHandle)();
    v48 = 0;
  }
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v49);
  Windows::Rtl::CLUNICODE_STRING::~CLUNICODE_STRING((Windows::Rtl::CLUNICODE_STRING *)&v52);
LABEL_93:
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v57);
  if ( v43 )
  {
    RtlCloseIsolatedFilesystemObjectHandle(v43);
    v43 = 0;
  }
LABEL_95:
  if ( v42 )
  {
    LODWORD(v46) = -1073741595;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v44 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v42) )
    {
      goto LABEL_6;
    }
LABEL_111:
    (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
LABEL_112:
    v12 = 0;
    goto LABEL_113;
  }
LABEL_116:
  Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>(v86);
  return (unsigned int)ComponentManifest;
}

```

## disassembly

```asm
0x18010fb14  mov     [rsp-8+arg_8], rbx
0x18010fb19  push    rbp
0x18010fb1a  push    rsi
0x18010fb1b  push    rdi
0x18010fb1c  push    r12
0x18010fb1e  push    r13
0x18010fb20  push    r14
0x18010fb22  push    r15
0x18010fb24  lea     rbp, [rsp-290h]
0x18010fb2c  sub     rsp, 390h
0x18010fb33  mov     rax, cs:__security_cookie
0x18010fb3a  xor     rax, rsp
0x18010fb3d  mov     [rbp+2C0h+var_40], rax
0x18010fb44  movdqa  xmm0, cs:__xmm@c0000043c0000034c000003ac0000035
0x18010fb4c  lea     rax, aOnecoreComNetf_46; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010fb53  mov     rdi, [rbp+2C0h+arg_28]
0x18010fb5a  xor     r15d, r15d
0x18010fb5d  mov     qword ptr [rbp+2C0h+var_2A0], rax
0x18010fb61  mov     r13, rcx
0x18010fb64  lea     rax, [rbp+2C0h+var_50]
0x18010fb6b  mov     [rbp+2C0h+var_1B8], r8
0x18010fb72  mov     [rbp+2C0h+var_218], rax
0x18010fb79  lea     rcx, [rbp+2C0h+var_308]; this
0x18010fb7d  xor     eax, eax
0x18010fb7f  mov     [rbp+2C0h+var_220], 4
0x18010fb8a  mov     ebx, 0C00000E5h
0x18010fb8f  mov     qword ptr [rbp+2C0h+var_210], rax
0x18010fb96  mov     r12, r9
0x18010fb99  mov     dword ptr [rbp+2C0h+var_290], ebx
0x18010fb9c  movdqu  [rbp+2C0h+var_50], xmm0
0x18010fba4  mov     [rbp+2C0h+var_310], r15
0x18010fba8  mov     [rbp+2C0h+var_180], r15
0x18010fbaf  mov     [rbp+2C0h+var_78], r15
0x18010fbb6  mov     [rbp+2C0h+var_70], r15
0x18010fbbd  mov     [rbp+2C0h+var_68], r15
0x18010fbc4  mov     [rbp+2C0h+var_60], r15b
0x18010fbcb  mov     [rsp+3C0h+var_380], r15
0x18010fbd0  mov     [rsp+3C0h+var_378], r15
0x18010fbd5  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x18010fbda  lea     r8, [rbp+2C0h+var_310]; struct Windows::Cdf::Rtl::_CDF *
0x18010fbde  mov     rdx, r9; struct CComponentAccessor *
0x18010fbe1  mov     rcx, r13; this
0x18010fbe4  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_CDF@Rtl@Cdf@Windows@@@Z; CCSDirectTransaction::GetComponentManifest(CComponentAccessor const &,Windows::Cdf::Rtl::_CDF &)
0x18010fbe9  mov     r14d, eax
0x18010fbec  test    eax, eax
0x18010fbee  jns     loc_18010FC7E
0x18010fbf4  lea     rcx, [rbp+2C0h+var_308]; this
0x18010fbf8  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010fbfd  mov     rcx, [rsp+3C0h+var_378]
0x18010fc02  test    rcx, rcx
0x18010fc05  jz      short loc_18010FC11
0x18010fc07  call    RtlCloseIsolatedFilesystemObjectHandle
0x18010fc0c  mov     [rsp+3C0h+var_378], r15
0x18010fc11  mov     r10, [rsp+3C0h+var_380]
0x18010fc16  test    r10, r10
0x18010fc19  jz      loc_180110906
0x18010fc1f  mov     esi, 1
0x18010fc24  mov     dword ptr [rsp+3C0h+var_360], ebx
0x18010fc28  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rsi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18010fc2f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010fc36  mov     [rsp+3C0h+var_370], rax
0x18010fc3b  test    r10, r10
0x18010fc3e  jz      loc_1801108EC
0x18010fc44  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18010fc4b  test    r11, r11
0x18010fc4e  jz      short loc_18010FC63
0x18010fc50  mov     rdx, r11
0x18010fc53  mov     rcx, r10
0x18010fc56  call    RtlIsTypeSafeHandleValid
0x18010fc5b  test    al, al
0x18010fc5d  jnz     loc_1801108DD
0x18010fc63  mov     dword ptr [rsp+3C0h+var_368], 124h
0x18010fc6b  lea     rcx, [rsp+3C0h+var_370]
0x18010fc70  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18010fc75  mov     ecx, dword ptr [rsp+3C0h+var_360]
0x18010fc79  jmp     loc_1801108EF
0x18010fc7e  mov     rbx, [rbp+2C0h+var_310]
0x18010fc82  test    rbx, rbx
0x18010fc85  jnz     loc_18010FD67
0x18010fc8b  lea     esi, [rbx+1]
0x18010fc8e  lea     rcx, [rbp+2C0h+var_308]; this
0x18010fc92  test    [rbp+2C0h+arg_20], sil
0x18010fc99  jz      short loc_18010FCA3
0x18010fc9b  mov     r14d, r15d
0x18010fc9e  jmp     loc_180110788
0x18010fca3  mov     dword ptr [rbp+2C0h+var_2A0+8], 15Eh
0x18010fcaa  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010fcaf  mov     rcx, [rsp+3C0h+var_378]
0x18010fcb4  test    rcx, rcx
0x18010fcb7  jz      short loc_18010FCC3
0x18010fcb9  call    RtlCloseIsolatedFilesystemObjectHandle
0x18010fcbe  mov     [rsp+3C0h+var_378], r15
0x18010fcc3  mov     r10, [rsp+3C0h+var_380]
0x18010fcc8  test    r10, r10
0x18010fccb  jz      short loc_18010FD31
0x18010fccd  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rsi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18010fcd4  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010fcdb  mov     dword ptr [rsp+3C0h+var_360], 0C00000E5h
0x18010fce3  mov     [rsp+3C0h+var_370], rax
0x18010fce8  test    r10, r10
0x18010fceb  jz      short loc_18010FD17
0x18010fced  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18010fcf4  test    r11, r11
0x18010fcf7  jz      short loc_18010FD4F
0x18010fcf9  mov     rdx, r11
0x18010fcfc  mov     rcx, r10
0x18010fcff  call    RtlIsTypeSafeHandleValid
0x18010fd04  test    al, al
0x18010fd06  jz      short loc_18010FD4F
0x18010fd08  mov     ecx, [r11]
0x18010fd0b  mov     rdx, r10
0x18010fd0e  mov     rax, [r11+20h]
0x18010fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fd17  mov     ecx, r15d; dwExceptionCode
0x18010fd1a  test    ecx, ecx
0x18010fd1c  jns     short loc_18010FD2C
0x18010fd1e  xor     r9d, r9d; lpArguments
0x18010fd21  xor     r8d, r8d; nNumberOfArguments
0x18010fd24  mov     edx, esi; dwExceptionFlags
0x18010fd26  call    cs:__imp_RaiseException
0x18010fd2c  mov     [rsp+3C0h+var_380], r15
0x18010fd31  lea     rcx, [rbp+2C0h+var_180]
0x18010fd38  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE_ENUMERATOR@234@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>(void)
0x18010fd3d  lea     rcx, [rbp+2C0h+var_2A0]
0x18010fd41  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18010fd46  mov     r14d, dword ptr [rbp+2C0h+var_290]
0x18010fd4a  jmp     loc_180110912
0x18010fd4f  mov     dword ptr [rsp+3C0h+var_368], 124h
0x18010fd57  lea     rcx, [rsp+3C0h+var_370]
0x18010fd5c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18010fd61  mov     ecx, dword ptr [rsp+3C0h+var_360]
0x18010fd65  jmp     short loc_18010FD1A
0x18010fd67  lea     r8, [rsp+3C0h+var_378]; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *
0x18010fd6c  mov     rdx, r12; struct CComponentAccessor *
0x18010fd6f  mov     rcx, r13; this
0x18010fd72  call    ?GetComponentDirectory@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@@Z; CCSDirectTransaction::GetComponentDirectory(CComponentAccessor const &,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x18010fd77  mov     r14d, eax
0x18010fd7a  test    eax, eax
0x18010fd7c  jns     short loc_18010FDB3
0x18010fd7e  lea     rcx, [rbp+2C0h+var_308]; this
0x18010fd82  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010fd87  mov     rcx, [rsp+3C0h+var_378]
0x18010fd8c  test    rcx, rcx
0x18010fd8f  jz      short loc_18010FD9B
0x18010fd91  call    RtlCloseIsolatedFilesystemObjectHandle
0x18010fd96  mov     [rsp+3C0h+var_378], r15
0x18010fd9b  mov     r10, [rsp+3C0h+var_380]
0x18010fda0  test    r10, r10
0x18010fda3  jz      loc_180110906
0x18010fda9  mov     esi, 1
0x18010fdae  jmp     loc_1801107AF
0x18010fdb3  mov     esi, 1
0x18010fdb8  mov     [rbp+2C0h+var_60], r15b
0x18010fdbf  mov     r8d, esi
0x18010fdc2  lea     rcx, [rbp+2C0h+var_180]
0x18010fdc9  mov     rdx, rbx
0x18010fdcc  call    ?Attach@?$CTableIterator@V?$CTableTraits@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE_ENUMERATOR@234@U_CDF_STRING_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAAJU_CDF@234@K_KPEBU_CDF_TABLE_AND_KEY@234@@Z; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR_ITEM>,8>::Attach(Windows::Cdf::Rtl::_CDF,ulong,unsigned __int64,Windows::Cdf::Rtl::_CDF_TABLE_AND_KEY const *)
0x18010fdd1  mov     r14d, eax
0x18010fdd4  test    eax, eax
0x18010fdd6  js      loc_180110784
0x18010fddc  mov     rdx, [r13+300h]
0x18010fde3  lea     r8, [rsp+3C0h+var_380]
0x18010fde8  call    RtlGetSystemIsolatedFilesystem
0x18010fded  mov     r14d, eax
0x18010fdf0  test    eax, eax
0x18010fdf2  js      loc_180110784
0x18010fdf8  movups  xmm1, cs:g_LUNICODE_STRING_name
0x18010fdff  mov     rdx, [r12]
0x18010fe03  lea     r8, [rbp+2C0h+var_270]
0x18010fe07  xorps   xmm0, xmm0
0x18010fe0a  mov     [rbp+2C0h+var_328], r15
0x18010fe0e  xor     eax, eax
0x18010fe10  movaps  [rbp+2C0h+var_270], xmm0
0x18010fe14  movsd   xmm0, cs:off_180138A30; "name"
0x18010fe1c  movups  [rbp+2C0h+var_258], xmm1
0x18010fe20  mov     [rbp+2C0h+var_330], r15
0x18010fe24  xorps   xmm1, xmm1
0x18010fe27  mov     [rbp+2C0h+var_320], r15
0x18010fe2b  movups  [rbp+2C0h+var_240], xmm1
0x18010fe32  mov     [rbp+2C0h+var_340], r15
0x18010fe36  mov     [rsp+3C0h+var_348], r15
0x18010fe3b  mov     [rbp+2C0h+lpMem], r15
0x18010fe3f  mov     [rbp+2C0h+var_260], rax
0x18010fe43  movsd   [rbp+2C0h+var_248], xmm0
0x18010fe48  mov     [rbp+2C0h+var_230], rax
0x18010fe4f  call    RtlGetDefinitionIdentityAttributeValue
0x18010fe54  mov     r14d, eax
0x18010fe57  test    eax, eax
0x18010fe59  js      loc_180110842
0x18010fe5f  mov     r15, qword ptr [rbp+2C0h+var_240]
0x18010fe66  lea     rdx, [rbp+2C0h+var_330]
0x18010fe6a  movups  xmm0, [rbp+2C0h+var_240+8]
0x18010fe71  mov     [rbp+2C0h+var_2D0], r15
0x18010fe75  lea     rcx, [r15+12h]
0x18010fe79  movdqu  [rbp+2C0h+var_2C8], xmm0
0x18010fe7e  call    RtlAllocateLUnicodeString
0x18010fe83  mov     r14d, eax
0x18010fe86  test    eax, eax
0x18010fe88  js      loc_18010FF7C
0x18010fe8e  lea     rdx, [rbp+2C0h+var_330]
0x18010fe92  lea     rcx, [rbp+2C0h+var_2D0]
0x18010fe96  call    RtlAppendLUnicodeStringToLUnicodeString
0x18010fe9b  mov     r14d, eax
0x18010fe9e  test    eax, eax
0x18010fea0  js      loc_18010FF7C
0x18010fea6  add     r12, 8
0x18010feaa  lea     rdx, [rsp+3C0h+var_348]
0x18010feaf  mov     rcx, [r12]
0x18010feb3  add     rcx, 12h
0x18010feb7  call    RtlAllocateLUnicodeString
0x18010febc  mov     r14d, eax
0x18010febf  test    eax, eax
0x18010fec1  js      loc_18010FF7C
0x18010fec7  lea     rdx, [rsp+3C0h+var_348]
0x18010fecc  mov     rcx, r12
0x18010fecf  call    RtlAppendLUnicodeStringToLUnicodeString
0x18010fed4  mov     r14d, eax
0x18010fed7  test    eax, eax
0x18010fed9  js      loc_18010FF7C
0x18010fedf  lea     rdx, [rsp+3C0h+var_348]
0x18010fee4  lea     rcx, g_LUNICODE_STRING__dot_manifest
0x18010feeb  call    RtlAppendLUnicodeStringToLUnicodeString
0x18010fef0  mov     r14d, eax
0x18010fef3  test    eax, eax
0x18010fef5  js      loc_18010FF7C
0x18010fefb  lea     rdx, [rbp+2C0h+var_330]
0x18010feff  lea     rcx, g_LUNICODE_STRING__dot_manifest
0x18010ff06  call    RtlAppendLUnicodeStringToLUnicodeString
0x18010ff0b  mov     r14d, eax
0x18010ff0e  test    eax, eax
0x18010ff10  js      short loc_18010FF7C
0x18010ff12  lea     edx, [rsi+3Fh]
0x18010ff15  mov     qword ptr [rbp+2C0h+var_270+8], rdi
0x18010ff19  lea     ecx, [rsi+2Fh]
0x18010ff1c  mov     dword ptr [rbp+2C0h+var_258], edx
0x18010ff1f  xorps   xmm0, xmm0
0x18010ff22  mov     [rbp+2C0h+var_2B8], edx
0x18010ff25  mov     rdx, [rsp+3C0h+var_380]
0x18010ff2a  lea     rax, [rbp+2C0h+var_330]
0x18010ff2e  mov     [rbp+2C0h+var_260], rax
0x18010ff32  lea     r9, [rbp+2C0h+var_270]
0x18010ff36  mov     rax, [r13+310h]
0x18010ff3d  lea     r8, [rbp+2C0h+var_2D0]
0x18010ff41  mov     qword ptr [rbp+2C0h+var_2C8], rax
0x18010ff45  lea     rax, [rsp+3C0h+var_348]
0x18010ff4a  mov     qword ptr [rbp+2C0h+var_2C8+8], rax
0x18010ff4e  lea     rax, [rbp+2C0h+var_220]
0x18010ff55  mov     [rsp+3C0h+var_398], rax
0x18010ff5a  mov     qword ptr [rbp+2C0h+var_270], rcx
0x18010ff5e  movdqu  [rbp+2C0h+var_258+8], xmm0
0x18010ff63  mov     [rbp+2C0h+var_2D0], rcx
0x18010ff67  movdqu  [rbp+2C0h+var_2B0], xmm0
0x18010ff6c  call    RtlIsolatedFilesystemCreateHardLinkOrCopyFile
0x18010ff71  mov     r14d, eax
0x18010ff74  test    eax, eax
0x18010ff76  jns     loc_18011005E
0x18010ff7c  mov     rcx, [rbp+2C0h+lpMem]; lpMem
0x18010ff80  xor     ebx, ebx
0x18010ff82  test    rcx, rcx
0x18010ff85  jz      short loc_18010FF99
0x18010ff87  mov     [rbp+2C0h+var_340], rbx
0x18010ff8b  mov     [rsp+3C0h+var_348], rbx
0x18010ff90  mov     [rbp+2C0h+lpMem], rbx
0x18010ff94  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18010ff99  mov     rcx, [rbp+2C0h+var_320]; lpMem
0x18010ff9d  test    rcx, rcx
0x18010ffa0  jz      short loc_18010FFB3
0x18010ffa2  mov     [rbp+2C0h+var_328], rbx
0x18010ffa6  mov     [rbp+2C0h+var_330], rbx
0x18010ffaa  mov     [rbp+2C0h+var_320], rbx
0x18010ffae  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18010ffb3  lea     rcx, [rbp+2C0h+var_308]; this
0x18010ffb7  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x18010ffbc  mov     rcx, [rsp+3C0h+var_378]
0x18010ffc1  test    rcx, rcx
0x18010ffc4  jz      short loc_18010FFD0
0x18010ffc6  call    RtlCloseIsolatedFilesystemObjectHandle
0x18010ffcb  mov     [rsp+3C0h+var_378], rbx
0x18010ffd0  mov     r10, [rsp+3C0h+var_380]
0x18010ffd5  test    r10, r10
0x18010ffd8  jz      loc_180110906
0x18010ffde  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rsi; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18010ffe5  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010ffec  mov     dword ptr [rsp+3C0h+var_360], 0C00000E5h
0x18010fff4  mov     [rsp+3C0h+var_370], rax
0x18010fff9  test    r10, r10
0x18010fffc  jz      short loc_180110028
0x18010fffe  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180110005  test    r11, r11
0x180110008  jz      short loc_180110046
0x18011000a  mov     rdx, r11
0x18011000d  mov     rcx, r10
0x180110010  call    RtlIsTypeSafeHandleValid
0x180110015  test    al, al
0x180110017  jz      short loc_180110046
0x180110019  mov     ecx, [r11]
0x18011001c  mov     rdx, r10
0x18011001f  mov     rax, [r11+20h]
0x180110023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110028  mov     ecx, ebx; dwExceptionCode
  ... truncated ...
```
