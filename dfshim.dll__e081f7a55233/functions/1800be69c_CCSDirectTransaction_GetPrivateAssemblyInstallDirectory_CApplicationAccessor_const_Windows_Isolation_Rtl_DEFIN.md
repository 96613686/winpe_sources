# CCSDirectTransaction::GetPrivateAssemblyInstallDirectory(CApplicationAccessor const &,Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)

- ea: `0x1800be69c`
- end: `0x1800bed87`
- name: `?GetPrivateAssemblyInstallDirectory@CCSDirectTransaction@@AEAAJAEBVCApplicationAccessor@@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_ISOLATED_FILESYSTEM_OBJECT@456@@Z`
- size: `1771`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c13e4`
- `0x1800c2ec4`
- `0x1800c628c`
- `0x1800c6584`

## callees

- `0x180012b1c`
- `0x180017514`
- `0x180017530`
- `0x18001de74`
- `0x180029628`
- `0x18002d588`
- `0x18002e204`
- `0x18003fae0`
- `0x180040020`
- `0x180043cc0`
- `0x180047fbc`
- `0x18004f2dc`
- `0x180050f7c`
- `0x1800bbc04`
- `0x1800bc3a0`
- `0x1800bdbe4`
- `0x1800be198`
- `0x1800be69c`
- `0x1800c7904`
- `0x1800d4a04`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be777`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be884`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be977`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bed1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be777`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be884`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be977`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bed1e`

## string_xrefs

- `0x1800be72d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800be832`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800be925`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bec4a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800beccc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800be6d6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::GetPrivateAssemblyInstallDirectory(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        const char **a4)
{
  __int64 v6; // rdx
  __int64 v9; // rcx
  int AppDirectoryForAppId; // r12d
  const char *v11; // rcx
  const char *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r10
  unsigned int *v15; // r11
  signed int v16; // ecx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r10
  unsigned int *v20; // r11
  signed int v21; // ecx
  const char *v22; // rsi
  unsigned int v23; // edi
  int v24; // r9d
  int v25; // r8d
  const char *v26; // rax
  __int64 v27; // r10
  unsigned int *v28; // r11
  signed int v29; // ecx
  char v31[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  const char *v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  unsigned int v35; // [rsp+60h] [rbp-A0h]
  const char *v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+78h] [rbp-88h]
  __int128 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int128 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int128 v43; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v44; // [rsp+C8h] [rbp-38h]
  __int128 v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+E0h] [rbp-20h]
  __int128 v47; // [rsp+F0h] [rbp-10h] BYREF
  __int128 *v48; // [rsp+100h] [rbp+0h]
  int v49; // [rsp+108h] [rbp+8h]
  __int128 v50; // [rsp+110h] [rbp+10h]
  __int128 v51; // [rsp+120h] [rbp+20h] BYREF
  __int64 v52; // [rsp+130h] [rbp+30h]
  _QWORD v53[9]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v54; // [rsp+188h] [rbp+88h]
  __int64 v55; // [rsp+190h] [rbp+90h]
  __int64 v56; // [rsp+198h] [rbp+98h]
  char v57; // [rsp+1A0h] [rbp+A0h]

  v35 = -1073741595;
  *a4 = 0;
  v33 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  v36 = 0;
  v6 = *a2;
  v32 = 0;
  AppDirectoryForAppId = CCSDirectTransaction::GetAppDirectoryForAppId(a1, v6, &v36);
  if ( AppDirectoryForAppId >= 0 )
  {
    v12 = v36;
    if ( a3 )
    {
      v36 = 0;
      v40 = 0;
      v43 = g_LUNICODE_STRING_publicKeyToken;
      v39 = 0;
      v42 = 0;
      v41 = 0;
      v45 = 0;
      v46 = 0;
      v44 = L"publicKeyToken";
      AppDirectoryForAppId = RtlGetDefinitionIdentityAttributeValue(v9, a3, &v41);
      if ( AppDirectoryForAppId < 0
        || (AppDirectoryForAppId = RtlGetSystemIsolatedFilesystem(v13, *(_QWORD *)(a1 + 768), &v32),
            AppDirectoryForAppId < 0) )
      {
LABEL_6:
        if ( v32 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v33 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          v35 = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v32) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v14);
            v16 = 0;
          }
          else
          {
            LODWORD(v34) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v33);
            v16 = v35;
          }
          if ( v16 < 0 )
            RaiseException(v16, 1u, 0, 0);
          v32 = 0;
        }
        goto LABEL_13;
      }
      v17 = (_QWORD *)a2[3];
      if ( v17 && *v17 )
        v18 = *(_QWORD *)(v17[1] + 8LL * *v17 - 8);
      else
        v18 = 0;
      AppDirectoryForAppId = CCSDirectTransaction::GetComponentManifest(a1, v18, &v36);
      if ( AppDirectoryForAppId < 0 )
      {
LABEL_22:
        if ( !v32 )
        {
LABEL_13:
          if ( !v12 )
            return (unsigned int)AppDirectoryForAppId;
          v11 = v12;
          goto LABEL_3;
        }
        ++g_nRtlCloseIsolatedFilesystemHandle;
        v35 = -1073741595;
        v33 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
          || !(unsigned __int8)RtlIsTypeSafeHandleValid(v32) )
        {
          LODWORD(v34) = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v33);
          v21 = v35;
          goto LABEL_26;
        }
LABEL_25:
        (*((void (__fastcall **)(_QWORD, __int64))v20 + 4))(*v20, v19);
        v21 = 0;
LABEL_26:
        if ( v21 < 0 )
          RaiseException(v21, 1u, 0, 0);
        v32 = 0;
        goto LABEL_13;
      }
      v22 = v36;
      v53[0] = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      AppDirectoryForAppId = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Attach(
                               v53,
                               v36);
      if ( AppDirectoryForAppId < 0 )
        goto LABEL_31;
      v23 = -1;
      if ( !v57 )
      {
LABEL_63:
        LODWORD(v34) = 2260;
LABEL_64:
        Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v53);
        if ( v32 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          v38 = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v32) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v28 + 4))(*v28, v27);
            v29 = 0;
          }
          else
          {
            LODWORD(v37) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
            v29 = v38;
          }
          if ( v29 < 0 )
            RaiseException(v29, 1u, 0, 0);
          v32 = 0;
        }
        if ( v12 )
          RtlCloseIsolatedFilesystemObjectHandle(v12);
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v33);
        return v35;
      }
      do
      {
        v36 = 0;
        AppDirectoryForAppId = CdfpGetIdentityCommon_Windows::Isolation::Rtl::_REFERENCE_IDENTITY_(
                                 v22,
                                 LODWORD(v53[v54 + 1]),
                                 &v36);
        if ( AppDirectoryForAppId < 0
          || (v31[0] = 0,
              AppDirectoryForAppId = RtlDoesDefinitionIdentityMatchReferenceIdentity(8, a3, v36, v31),
              AppDirectoryForAppId < 0) )
        {
LABEL_62:
          Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v53);
          goto LABEL_6;
        }
        if ( v31[0] )
        {
          if ( v23 != -1 )
          {
            LODWORD(v34) = 2250;
            goto LABEL_64;
          }
          v23 = HIDWORD(v53[v54 + 1]);
        }
        AppDirectoryForAppId = Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Next(v53);
        if ( AppDirectoryForAppId < 0 )
          goto LABEL_62;
      }
      while ( v57 );
      if ( v23 == -1 )
        goto LABEL_63;
      AppDirectoryForAppId = Windows::Isolation::Rtl::CmsFindCodebaseForAssemblyReference(v22, v23, &v39);
      if ( AppDirectoryForAppId < 0 )
      {
LABEL_31:
        Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v53);
        goto LABEL_22;
      }
      if ( (_QWORD)v39 )
      {
        v31[0] = 0;
        BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)&v41);
        v52 = 0;
        v48 = 0;
        v51 = 0;
        v47 = 0;
        AppDirectoryForAppId = BCL::Nt::CUnicodeStringBuffer::Assign(
                                 (BCL::Nt::CUnicodeStringBuffer *)&v41,
                                 (const struct _LUTF8_STRING *)&v39);
        if ( AppDirectoryForAppId < 0 )
          goto LABEL_44;
        v37 = 1;
        v36 = (const char *)L"\\";
        v34 = 1;
        v33 = (const char *)L"/";
        AppDirectoryForAppId = BCL::Nt::CUnicodeStringBuffer::Replace(
                                 (unsigned int)&v41,
                                 (unsigned int)&v33,
                                 (unsigned int)&v36,
                                 v24,
                                 (__int64)v31);
        if ( AppDirectoryForAppId < 0
          || (*((_QWORD *)&v43 + 1) = 2 * v42,
              v44 = (const wchar_t *)(2 * v42),
              *(_QWORD *)&v45 = v41,
              AppDirectoryForAppId = RtlSplitLUnicodeString(
                                       2,
                                       (unsigned int)&v43 + 8,
                                       v25,
                                       0,
                                       92,
                                       (__int64)&v51,
                                       (__int64)&v47),
              AppDirectoryForAppId < 0) )
        {
LABEL_44:
          BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)&v41);
          goto LABEL_31;
        }
        if ( (_QWORD)v47 )
        {
          v48 = &v51;
          v36 = 0;
          *(_QWORD *)&v47 = 48;
          *((_QWORD *)&v47 + 1) = v12;
          v49 = 64;
          v50 = 0;
          AppDirectoryForAppId = Windows::Isolation::Implementation::Rtl::CreateDirectories(0, v32, &v36, 0, &v47);
          if ( AppDirectoryForAppId < 0 )
          {
            if ( v36 )
            {
              RtlCloseIsolatedFilesystemObjectHandle(v36);
              v36 = 0;
            }
            goto LABEL_44;
          }
          *a4 = v36;
        }
        BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)&v41);
      }
      Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(v53);
    }
    if ( !*a4 )
    {
      v26 = v12;
      v12 = 0;
      *a4 = v26;
    }
    AppDirectoryForAppId = 0;
    if ( !v32 )
      goto LABEL_13;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    LODWORD(v40) = -1073741595;
    *(_QWORD *)&v39 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v32) )
    {
      DWORD2(v39) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v39);
      v21 = v40;
      goto LABEL_26;
    }
    goto LABEL_25;
  }
  v11 = v36;
  if ( v36 )
LABEL_3:
    RtlCloseIsolatedFilesystemObjectHandle(v11);
  return (unsigned int)AppDirectoryForAppId;
}

```

## disassembly

```asm
0x1800be69c  push    rbp
0x1800be69e  push    rbx
0x1800be69f  push    rsi
0x1800be6a0  push    rdi
0x1800be6a1  push    r12
0x1800be6a3  push    r13
0x1800be6a5  push    r14
0x1800be6a7  push    r15
0x1800be6a9  lea     rbp, [rsp-0C8h]
0x1800be6b1  sub     rsp, 1C8h
0x1800be6b8  mov     rax, cs:__security_cookie
0x1800be6bf  xor     rax, rsp
0x1800be6c2  mov     [rbp+100h+var_50], rax
0x1800be6c9  xor     ebx, ebx
0x1800be6cb  mov     [rsp+200h+var_1A0], 0C00000E5h
0x1800be6d3  mov     [r9], rbx
0x1800be6d6  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800be6dd  mov     r14, r8
0x1800be6e0  mov     [rsp+200h+var_1B0], rax
0x1800be6e5  mov     rsi, rdx
0x1800be6e8  mov     [rsp+200h+var_198], rbx
0x1800be6ed  mov     rdx, [rdx]
0x1800be6f0  lea     r8, [rsp+200h+var_198]
0x1800be6f5  mov     r13, r9
0x1800be6f8  mov     [rsp+200h+var_1B8], rbx
0x1800be6fd  mov     rdi, rcx
0x1800be700  call    ?GetAppDirectoryForAppId@CCSDirectTransaction@@AEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEAU_ISOLATED_FILESYSTEM_OBJECT@345@@Z; CCSDirectTransaction::GetAppDirectoryForAppId(Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x1800be705  mov     r12d, eax
0x1800be708  test    eax, eax
0x1800be70a  jns     loc_1800BE7B2
0x1800be710  mov     r10, [rsp+200h+var_1B8]
0x1800be715  test    r10, r10
0x1800be718  jz      short loc_1800BE782
0x1800be71a  lea     r15d, [rbx+1]
0x1800be71e  mov     [rsp+200h+var_1A0], 0C00000E5h
0x1800be726  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r15; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800be72d  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800be734  mov     [rsp+200h+var_1B0], rax
0x1800be739  test    r10, r10
0x1800be73c  jz      short loc_1800BE768
0x1800be73e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800be745  test    r11, r11
0x1800be748  jz      short loc_1800BE79A
0x1800be74a  mov     rdx, r11
0x1800be74d  mov     rcx, r10
0x1800be750  call    RtlIsTypeSafeHandleValid
0x1800be755  test    al, al
0x1800be757  jz      short loc_1800BE79A
0x1800be759  mov     ecx, [r11]
0x1800be75c  mov     rdx, r10
0x1800be75f  mov     rax, [r11+20h]
0x1800be763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be768  mov     ecx, ebx; dwExceptionCode
0x1800be76a  test    ecx, ecx
0x1800be76c  jns     short loc_1800BE77D
0x1800be76e  xor     r9d, r9d; lpArguments
0x1800be771  xor     r8d, r8d; nNumberOfArguments
0x1800be774  mov     edx, r15d; dwExceptionFlags
0x1800be777  call    cs:__imp_RaiseException
0x1800be77d  mov     [rsp+200h+var_1B8], rbx
0x1800be782  mov     rcx, [rsp+200h+var_198]
0x1800be787  test    rcx, rcx
0x1800be78a  jz      loc_1800BED49
0x1800be790  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800be795  jmp     loc_1800BED49
0x1800be79a  mov     dword ptr [rsp+200h+var_1A8], 124h
0x1800be7a2  lea     rcx, [rsp+200h+var_1B0]
0x1800be7a7  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800be7ac  mov     ecx, [rsp+200h+var_1A0]
0x1800be7b0  jmp     short loc_1800BE76A
0x1800be7b2  mov     rbx, [rsp+200h+var_198]
0x1800be7b7  mov     r15d, 1
0x1800be7bd  test    r14, r14
0x1800be7c0  jnz     short loc_1800BE7C9
0x1800be7c2  xor     edi, edi
0x1800be7c4  jmp     loc_1800BEC22
0x1800be7c9  movups  xmm1, cs:g_LUNICODE_STRING_publicKeyToken
0x1800be7d0  mov     [rsp+200h+var_198], 0
0x1800be7d9  xor     eax, eax
0x1800be7db  xorps   xmm0, xmm0
0x1800be7de  mov     [rbp+100h+var_170], rax
0x1800be7e2  movups  [rbp+100h+var_148], xmm1
0x1800be7e6  lea     r8, [rbp+100h+var_160]
0x1800be7ea  mov     rdx, r14
0x1800be7ed  movups  [rbp+100h+var_180], xmm0
0x1800be7f1  mov     [rbp+100h+var_150], rax
0x1800be7f5  movaps  [rbp+100h+var_160], xmm0
0x1800be7f9  xorps   xmm1, xmm1
0x1800be7fc  movsd   xmm0, cs:off_180136F38; "publicKeyToken"
0x1800be804  movups  [rbp+100h+var_130], xmm1
0x1800be808  mov     [rbp+100h+var_120], rax
0x1800be80c  movsd   [rbp+100h+var_138], xmm0
0x1800be811  call    RtlGetDefinitionIdentityAttributeValue
0x1800be816  mov     r12d, eax
0x1800be819  test    eax, eax
0x1800be81b  jns     loc_1800BE8BC
0x1800be821  mov     r10, [rsp+200h+var_1B8]
0x1800be826  test    r10, r10
0x1800be829  jz      short loc_1800BE893
0x1800be82b  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r15; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800be832  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800be839  mov     [rsp+200h+var_1B0], rax
0x1800be83e  mov     [rsp+200h+var_1A0], 0C00000E5h
0x1800be846  test    r10, r10
0x1800be849  jz      short loc_1800BE875
0x1800be84b  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800be852  test    r11, r11
0x1800be855  jz      short loc_1800BE8A4
0x1800be857  mov     rdx, r11
0x1800be85a  mov     rcx, r10
0x1800be85d  call    RtlIsTypeSafeHandleValid
0x1800be862  test    al, al
0x1800be864  jz      short loc_1800BE8A4
0x1800be866  mov     ecx, [r11]
0x1800be869  mov     rdx, r10
0x1800be86c  mov     rax, [r11+20h]
0x1800be870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be875  xor     ecx, ecx; dwExceptionCode
0x1800be877  test    ecx, ecx
0x1800be879  jns     short loc_1800BE88A
0x1800be87b  xor     r9d, r9d; lpArguments
0x1800be87e  xor     r8d, r8d; nNumberOfArguments
0x1800be881  mov     edx, r15d; dwExceptionFlags
0x1800be884  call    cs:__imp_RaiseException
0x1800be88a  mov     [rsp+200h+var_1B8], 0
0x1800be893  test    rbx, rbx
0x1800be896  jz      loc_1800BED49
0x1800be89c  mov     rcx, rbx
0x1800be89f  jmp     loc_1800BE790
0x1800be8a4  mov     dword ptr [rsp+200h+var_1A8], 124h
0x1800be8ac  lea     rcx, [rsp+200h+var_1B0]
0x1800be8b1  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800be8b6  mov     ecx, [rsp+200h+var_1A0]
0x1800be8ba  jmp     short loc_1800BE877
0x1800be8bc  mov     rdx, [rdi+300h]
0x1800be8c3  lea     r8, [rsp+200h+var_1B8]
0x1800be8c8  call    RtlGetSystemIsolatedFilesystem
0x1800be8cd  mov     r12d, eax
0x1800be8d0  test    eax, eax
0x1800be8d2  js      loc_1800BE821
0x1800be8d8  mov     rax, [rsi+18h]
0x1800be8dc  test    rax, rax
0x1800be8df  jz      short loc_1800BE8F4
0x1800be8e1  mov     rcx, [rax]
0x1800be8e4  test    rcx, rcx
0x1800be8e7  jz      short loc_1800BE8F4
0x1800be8e9  mov     rax, [rax+8]
0x1800be8ed  mov     rdx, [rax+rcx*8-8]
0x1800be8f2  jmp     short loc_1800BE8F6
0x1800be8f4  xor     edx, edx
0x1800be8f6  lea     r8, [rsp+200h+var_198]
0x1800be8fb  mov     rcx, rdi
0x1800be8fe  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_CDF@3Cdf@5@@Z; CCSDirectTransaction::GetComponentManifest(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Cdf::Rtl::_CDF &)
0x1800be903  xor     edi, edi
0x1800be905  mov     r12d, eax
0x1800be908  test    eax, eax
0x1800be90a  jns     loc_1800BE99F
0x1800be910  mov     r10, [rsp+200h+var_1B8]
0x1800be915  test    r10, r10
0x1800be918  jz      loc_1800BE893
0x1800be91e  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r15; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800be925  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800be92c  mov     [rsp+200h+var_1A0], 0C00000E5h
0x1800be934  mov     [rsp+200h+var_1B0], rax
0x1800be939  test    r10, r10
0x1800be93c  jz      short loc_1800BE968
0x1800be93e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800be945  test    r11, r11
0x1800be948  jz      short loc_1800BE987
0x1800be94a  mov     rdx, r11
0x1800be94d  mov     rcx, r10
0x1800be950  call    RtlIsTypeSafeHandleValid
0x1800be955  test    al, al
0x1800be957  jz      short loc_1800BE987
0x1800be959  mov     ecx, [r11]
0x1800be95c  mov     rdx, r10
0x1800be95f  mov     rax, [r11+20h]
0x1800be963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be968  mov     ecx, edi; dwExceptionCode
0x1800be96a  test    ecx, ecx
0x1800be96c  jns     short loc_1800BE97D
0x1800be96e  xor     r9d, r9d; lpArguments
0x1800be971  xor     r8d, r8d; nNumberOfArguments
0x1800be974  mov     edx, r15d; dwExceptionFlags
0x1800be977  call    cs:__imp_RaiseException
0x1800be97d  mov     [rsp+200h+var_1B8], rdi
0x1800be982  jmp     loc_1800BE893
0x1800be987  mov     dword ptr [rsp+200h+var_1A8], 124h
0x1800be98f  lea     rcx, [rsp+200h+var_1B0]
0x1800be994  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800be999  mov     ecx, [rsp+200h+var_1A0]
0x1800be99d  jmp     short loc_1800BE96A
0x1800be99f  mov     rsi, [rsp+200h+var_198]
0x1800be9a4  lea     rcx, [rbp+100h+var_C0]
0x1800be9a8  mov     rdx, rsi
0x1800be9ab  mov     [rbp+100h+var_C0], rdi
0x1800be9af  mov     [rbp+100h+var_78], rdi
0x1800be9b6  mov     [rbp+100h+var_70], rdi
0x1800be9bd  mov     [rbp+100h+var_68], rdi
0x1800be9c4  mov     [rbp+100h+var_60], dil
0x1800be9cb  call    ?Attach@?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAAJU_CDF@234@K_KPEBU_CDF_TABLE_AND_KEY@234@@Z; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Attach(Windows::Cdf::Rtl::_CDF,ulong,unsigned __int64,Windows::Cdf::Rtl::_CDF_TABLE_AND_KEY const *)
0x1800be9d0  mov     r12d, eax
0x1800be9d3  test    eax, eax
0x1800be9d5  jns     short loc_1800BE9E5
0x1800be9d7  lea     rcx, [rbp+100h+var_C0]
0x1800be9db  call    ??1?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAA@XZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::~CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>(void)
0x1800be9e0  jmp     loc_1800BE910
0x1800be9e5  or      edi, 0FFFFFFFFh
0x1800be9e8  cmp     [rbp+100h+var_60], 0
0x1800be9ef  jz      loc_1800BECAA
0x1800be9f5  mov     rdx, [rbp+100h+var_78]
0x1800be9fc  lea     r8, [rsp+200h+var_198]
0x1800bea01  mov     rcx, rsi
0x1800bea04  mov     [rsp+200h+var_198], 0
0x1800bea0d  mov     edx, [rbp+rdx*8+100h+var_B8]
0x1800bea11  call    CdfpGetIdentityCommon_Windows__Isolation__Rtl___REFERENCE_IDENTITY_
0x1800bea16  mov     r12d, eax
0x1800bea19  test    eax, eax
0x1800bea1b  js      loc_1800BEC9C
0x1800bea21  mov     r8, [rsp+200h+var_198]
0x1800bea26  lea     r9, [rsp+200h+var_1C0]
0x1800bea2b  mov     rdx, r14
0x1800bea2e  mov     [rsp+200h+var_1C0], 0
0x1800bea33  mov     ecx, 8
0x1800bea38  call    RtlDoesDefinitionIdentityMatchReferenceIdentity
0x1800bea3d  mov     r12d, eax
0x1800bea40  test    eax, eax
0x1800bea42  js      loc_1800BEC9C
0x1800bea48  cmp     [rsp+200h+var_1C0], 0
0x1800bea4d  jz      short loc_1800BEA63
0x1800bea4f  cmp     edi, 0FFFFFFFFh
0x1800bea52  jnz     loc_1800BEAFA
0x1800bea58  mov     rdi, [rbp+100h+var_78]
0x1800bea5f  mov     edi, [rbp+rdi*8+100h+var_B4]
0x1800bea63  lea     rcx, [rbp+100h+var_C0]
0x1800bea67  call    ?Next@?$CTableIterator@V?$CTableTraits@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@234@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@$07@Rtl@Cdf@Windows@@QEAAJXZ; Windows::Cdf::Rtl::CTableIterator<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_ITEM>,8>::Next(void)
0x1800bea6c  mov     r12d, eax
0x1800bea6f  test    eax, eax
0x1800bea71  js      loc_1800BEC9C
0x1800bea77  cmp     [rbp+100h+var_60], 0
0x1800bea7e  jnz     loc_1800BE9F5
0x1800bea84  cmp     edi, 0FFFFFFFFh
0x1800bea87  jz      loc_1800BECAA
0x1800bea8d  lea     r8, [rbp+100h+var_180]
0x1800bea91  mov     edx, edi
0x1800bea93  mov     rcx, rsi
0x1800bea96  call    ?CmsFindCodebaseForAssemblyReference@Rtl@Isolation@Windows@@YAJU_CDF@1Cdf@3@U_CDF_BLOBID@153@PEAU_LUTF8_STRING@@@Z; Windows::Isolation::Rtl::CmsFindCodebaseForAssemblyReference(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_BLOBID,_LUTF8_STRING *)
0x1800bea9b  xor     edi, edi
0x1800bea9d  mov     r12d, eax
0x1800beaa0  test    eax, eax
0x1800beaa2  js      loc_1800BE9D7
0x1800beaa8  cmp     qword ptr [rbp+100h+var_180], rdi
0x1800beaac  jz      loc_1800BEC19
0x1800beab2  lea     rcx, [rbp+100h+var_160]; this
0x1800beab6  mov     [rsp+200h+var_1C0], dil
0x1800beabb  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800beac0  xor     eax, eax
0x1800beac2  lea     rdx, [rbp+100h+var_180]; struct _LUTF8_STRING *
0x1800beac6  xorps   xmm0, xmm0
0x1800beac9  mov     [rbp+100h+var_D0], rax
0x1800beacd  xorps   xmm1, xmm1
0x1800bead0  mov     [rbp+100h+var_100], rax
0x1800bead4  lea     rcx, [rbp+100h+var_160]; this
0x1800bead8  movups  [rbp+100h+var_E0], xmm0
0x1800beadc  movups  [rbp+100h+var_110], xmm1
0x1800beae0  call    ?Assign@CUnicodeStringBuffer@Nt@BCL@@QEAAJPEBU_LUTF8_STRING@@@Z; BCL::Nt::CUnicodeStringBuffer::Assign(_LUTF8_STRING const *)
0x1800beae5  lea     rcx, [rbp+100h+var_160]; this
0x1800beae9  mov     r12d, eax
0x1800beaec  test    eax, eax
0x1800beaee  jns     short loc_1800BEB07
0x1800beaf0  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800beaf5  jmp     loc_1800BE9D7
0x1800beafa  mov     dword ptr [rsp+200h+var_1A8], 8CAh
0x1800beb02  jmp     loc_1800BECB2
0x1800beb07  lea     rax, SubBlock; "\\"
0x1800beb0e  mov     [rsp+200h+var_190], r15
0x1800beb13  mov     [rsp+200h+var_198], rax
0x1800beb18  lea     r8, [rsp+200h+var_198]
0x1800beb1d  lea     rax, asc_180140D5C; "/"
0x1800beb24  mov     [rsp+200h+var_1A8], r15
0x1800beb29  mov     [rsp+200h+var_1B0], rax
0x1800beb2e  lea     rdx, [rsp+200h+var_1B0]
0x1800beb33  lea     rax, [rsp+200h+var_1C0]
0x1800beb38  mov     [rsp+200h+var_1E0], rax
0x1800beb3d  call    ?Replace@CUnicodeStringBuffer@Nt@BCL@@QEAAJAEAV?$CConstantPointerAndCountPair@G_K@3@0_NAEA_N@Z; BCL::Nt::CUnicodeStringBuffer::Replace(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> &,BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> &,bool,bool &)
0x1800beb42  mov     r12d, eax
0x1800beb45  test    eax, eax
0x1800beb47  jns     short loc_1800BEB4F
0x1800beb49  lea     rcx, [rbp+100h+var_160]
0x1800beb4d  jmp     short loc_1800BEAF0
0x1800beb4f  mov     rax, [rbp+100h+var_150]
0x1800beb53  lea     rdx, [rbp+100h+var_148+8]
0x1800beb57  add     rax, rax
0x1800beb5a  xor     r9d, r9d
0x1800beb5d  mov     qword ptr [rbp+100h+var_148+8], rax
0x1800beb61  mov     [rbp+100h+var_138], rax
0x1800beb65  mov     rax, qword ptr [rbp+100h+var_160]
0x1800beb69  mov     qword ptr [rbp+100h+var_130], rax
0x1800beb6d  lea     ecx, [r9+2]
0x1800beb71  lea     rax, [rbp+100h+var_110]
  ... truncated ...
```
