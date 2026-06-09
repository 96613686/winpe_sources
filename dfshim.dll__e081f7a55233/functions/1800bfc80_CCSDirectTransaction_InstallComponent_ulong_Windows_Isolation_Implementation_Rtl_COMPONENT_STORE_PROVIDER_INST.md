# CCSDirectTransaction::InstallComponent(ulong,Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_ const *,ulong &)

- ea: `0x1800bfc80`
- end: `0x1800c03a0`
- name: `?InstallComponent@CCSDirectTransaction@@IEAAJKPEBU_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_@Rtl@Implementation@Isolation@Windows@@AEAK@Z`
- size: `1824`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, unsigned int, const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_ *, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c9140`

## callees

- `0x180012b1c`
- `0x18001531c`
- `0x1800153cc`
- `0x180018bb8`
- `0x18001eb80`
- `0x180028930`
- `0x180028ce4`
- `0x18002f364`
- `0x18003695c`
- `0x18003eb10`
- `0x180040020`
- `0x180043570`
- `0x180048470`
- `0x18004f2dc`
- `0x1800bfc80`
- `0x1800c6948`
- `0x1800c6ec4`
- `0x1800c8040`
- `0x1800d1230`
- `0x1800d24d0`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfe98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c007c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c023d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c030f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bfe98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c007c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c023d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c030f`

## string_xrefs

- `0x1800bfe49`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bff72`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c002c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c01ed`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c02c7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bfcaf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`
- `0x1800bfda7`: `   Install Component Data:\n      ManifestPath: {mf}\n      Reference: {ref}\n      DefinitionIdentity: {defid}\n`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::InstallComponent(
        CCSDirectTransaction *this,
        int a2,
        const struct Windows::Isolation::Implementation::Rtl::_COMPONENT_STORE_PROVIDER_INSTALL_COMPONENT_ *a3,
        unsigned int *a4)
{
  bool v4; // cf
  __int64 v7; // r8
  __int64 *v8; // r15
  __int64 v9; // r10
  __int64 v10; // rcx
  int SystemIsolatedFilesystem; // edi
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  int v15; // edx
  __int64 v16; // r10
  unsigned int *v17; // r11
  signed int v18; // ecx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r10
  unsigned int *v23; // r11
  signed int v24; // ecx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // r9d
  int v30; // eax
  void *v31; // rcx
  __int64 v32; // r10
  unsigned int *v33; // r11
  signed int v34; // ecx
  int v36[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  void *lpMem; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h]
  unsigned int v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  __int64 *v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+C0h] [rbp-40h]
  __int128 v47; // [rsp+C8h] [rbp-38h]
  _QWORD v48[10]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v49[6]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v50[6]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v51[10]; // [rsp+190h] [rbp+90h] BYREF
  int v52; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v53; // [rsp+200h] [rbp+100h] BYREF
  __int64 v54; // [rsp+208h] [rbp+108h] BYREF

  v52 = a2;
  v42 = -1073741595;
  *a4 = 0;
  v4 = *(_DWORD *)a3 < 0x20u;
  v40 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  memset(v48, 0, sizeof(v48));
  v37 = 0;
  *(_QWORD *)v36 = 0;
  lpMem = 0;
  v53 = 0;
  v54 = 0;
  if ( v4 )
  {
    v41 = 3633;
LABEL_80:
    CComponentAccessor::~CComponentAccessor((CComponentAccessor *)v48);
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
    return v42;
  }
  if ( (*((_DWORD *)a3 + 1) & 0xFFFFFFFE) != 0 )
  {
    v41 = 3636;
    goto LABEL_80;
  }
  if ( !IsValidComponentReference(*((const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **)a3 + 2)) )
  {
    v41 = 3637;
    goto LABEL_80;
  }
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT,Windows::Isolation::Fs::Private::CFsobj,Windows::Isolation::Fs::Private::FSOBJ_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsobjTraits>::ms_ptti
    || (v8 = (__int64 *)(v7 + 8), !(unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)(v7 + 8))) )
  {
    v41 = 3638;
    goto LABEL_80;
  }
  if ( !qword_180166950 )
  {
LABEL_68:
    v41 = 3639;
    if ( v9 )
    {
      LODWORD(v45) = -1073741595;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v43 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v9) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v33 + 4))(*v33, v32);
        v34 = 0;
      }
      else
      {
        LODWORD(v44) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
        v34 = (int)v45;
      }
      if ( v34 < 0 )
        RaiseException(v34, 1u, 0, 0);
      v54 = 0;
    }
    if ( v53 )
    {
      CdfCloseHandle();
      v53 = 0;
    }
    goto LABEL_80;
  }
  if ( !(unsigned __int8)RtlIsBaseIdentityHandleValidWithType(*(_QWORD *)qword_180166950) )
  {
    v9 = v54;
    goto LABEL_68;
  }
  Windows::Isolation::Rtl::RtlTrace(
    0,
    (unsigned int)&Windows::Isolation::Rtl::Facility_IsolationComponentStore,
    (struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *)1,
    (unsigned int)"   Install Component Data:\n"
                  "      ManifestPath: {mf}\n"
                  "      Reference: {ref}\n"
                  "      DefinitionIdentity: {defid}\n",
    (const char *const)3,
    (unsigned __int64)"mf",
    Windows::Isolation::Rtl::RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT,
    v8,
    "ref",
    RtlTraceFormat_PCCOMPONENT_STORE_REFERENCE,
    *((_QWORD *)a3 + 2),
    "defid",
    Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_IDENTITY,
    (char *)a3 + 24,
    *(_QWORD *)v36,
    v37);
  SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v10, *((_QWORD *)this + 96), &v54);
  if ( SystemIsolatedFilesystem >= 0 )
  {
    v44 = *v8;
    v43 = 48;
    v45 = &g_LUNICODE_STRING__empty_;
    v46 = 64;
    v47 = 0;
    SystemIsolatedFilesystem = RtlIsolatedFilesystemGetFileContents(v54, &v43, v36, 0);
    if ( SystemIsolatedFilesystem < 0
      || (SystemIsolatedFilesystem = RtlCompileCdfFromXmlBlob((int)v36, v15, (int)&v53, 0, 0),
          SystemIsolatedFilesystem < 0)
      || (SystemIsolatedFilesystem = CComponentAccessor::Attach(v48, v53), SystemIsolatedFilesystem < 0) )
    {
      if ( !v54 )
      {
LABEL_61:
        if ( v53 )
        {
          CdfCloseHandle();
          v53 = 0;
        }
        v31 = lpMem;
        if ( lpMem )
        {
          lpMem = 0;
          *(_QWORD *)v36 = 0;
          v37 = 0;
          IsolationFreeStringRoutine(v31);
        }
        goto LABEL_65;
      }
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v42 = -1073741595;
      v40 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v54) )
      {
        v41 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
        v18 = v42;
LABEL_58:
        if ( v18 < 0 )
          RaiseException(v18, 1u, 0, 0);
        v54 = 0;
        goto LABEL_61;
      }
    }
    else
    {
      v19 = *((_QWORD *)a3 + 3);
      LOBYTE(v52) = 0;
      SystemIsolatedFilesystem = RtlAreDefinitionIdentitiesEqual(0, v48[0], v19, &v52);
      if ( SystemIsolatedFilesystem >= 0 )
      {
        if ( !(_BYTE)v52 )
        {
          v41 = 3682;
          if ( v54 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            LODWORD(v45) = -1073741595;
            v43 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v54) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v23 + 4))(*v23, v22);
              v24 = 0;
            }
            else
            {
              LODWORD(v44) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
              v24 = (int)v45;
            }
            if ( v24 < 0 )
              RaiseException(v24, 1u, 0, 0);
            v54 = 0;
          }
          if ( v53 )
          {
            CdfCloseHandle();
            v53 = 0;
          }
          v25 = lpMem;
          if ( lpMem )
          {
            v37 = 0;
            *(_QWORD *)v36 = 0;
            lpMem = 0;
            IsolationFreeStringRoutine(v25);
          }
          goto LABEL_80;
        }
        SystemIsolatedFilesystem = CCSDirectTransaction::RealInstallComponent(this, v20, v21, v48, v36, v53);
        if ( SystemIsolatedFilesystem >= 0 )
        {
          v49[0] = 0;
          memset(v50, 0, sizeof(v50));
          memset(v51, 0, 24);
          v39 = 0;
          SystemIsolatedFilesystem = IsoDefinitionAppidFromPieces(v26, v48[0], v27, &v39);
          if ( SystemIsolatedFilesystem < 0
            || (SystemIsolatedFilesystem = CApplicationAccessor::Attach(v49, v39), SystemIsolatedFilesystem < 0)
            || (SystemIsolatedFilesystem = CComponentMarkManager::GenericAddSingleMark(
                                             (char *)this + 3152,
                                             4,
                                             v49,
                                             *((_QWORD *)a3 + 2)),
                SystemIsolatedFilesystem < 0) )
          {
            v28 = v39;
          }
          else
          {
            v30 = CComponentMarkManager::GenericAddSingleMark<CComponentAccessor>(
                    (int)this + 3152,
                    6,
                    (unsigned int)v48,
                    v29,
                    (__int64)v50,
                    (__int64)v51);
            v28 = v39;
            SystemIsolatedFilesystem = v30;
            if ( v30 >= 0 )
              SystemIsolatedFilesystem = 0;
          }
          if ( v28 )
          {
            RtlCloseDefinitionAppIdHandle();
            v39 = 0;
          }
          CApplicationAccessor::~CApplicationAccessor((CApplicationAccessor *)v49);
        }
      }
      if ( !v54 )
        goto LABEL_61;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v43 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      LODWORD(v45) = -1073741595;
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v54) )
      {
        LODWORD(v44) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v43);
        v18 = (int)v45;
        goto LABEL_58;
      }
    }
    (*((void (__fastcall **)(_QWORD, __int64))v17 + 4))(*v17, v16);
    v18 = 0;
    goto LABEL_58;
  }
  if ( v54 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v42 = -1073741595;
    v40 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v54) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
      v14 = 0;
    }
    else
    {
      v41 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v40);
      v14 = v42;
    }
    if ( v14 < 0 )
      RaiseException(v14, 1u, 0, 0);
    v54 = 0;
  }
  if ( v53 )
  {
    CdfCloseHandle();
    v53 = 0;
  }
LABEL_65:
  CComponentAccessor::~CComponentAccessor((CComponentAccessor *)v48);
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800bfc80  mov     [rsp-8+arg_0], rbx
0x1800bfc85  mov     [rsp-8+arg_8], edx
0x1800bfc89  push    rbp
0x1800bfc8a  push    rsi
0x1800bfc8b  push    rdi
0x1800bfc8c  push    r12
0x1800bfc8e  push    r13
0x1800bfc90  push    r14
0x1800bfc92  push    r15
0x1800bfc94  lea     rbp, [rsp-0B0h]
0x1800bfc9c  sub     rsp, 1B0h
0x1800bfca3  xor     edi, edi
0x1800bfca5  mov     [rbp+0E0h+var_140], 0C00000E5h
0x1800bfcac  mov     [r9], edi
0x1800bfcaf  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bfcb6  cmp     dword ptr [r8], 20h ; ' '
0x1800bfcba  mov     r12, r9
0x1800bfcbd  mov     rsi, r8
0x1800bfcc0  mov     [rbp+0E0h+var_150], rax
0x1800bfcc4  mov     r13, rcx
0x1800bfcc7  mov     [rbp+0E0h+var_100], rdi
0x1800bfccb  mov     [rbp+0E0h+var_F0], rdi
0x1800bfccf  mov     r10d, edi
0x1800bfcd2  mov     [rbp+0E0h+var_F8], rdi
0x1800bfcd6  mov     [rbp+0E0h+var_E8], rdi
0x1800bfcda  mov     [rbp+0E0h+var_D8], rdi
0x1800bfcde  mov     [rbp+0E0h+var_E0], rdi
0x1800bfce2  mov     [rbp+0E0h+var_D0], rdi
0x1800bfce6  mov     [rbp+0E0h+var_C0], rdi
0x1800bfcea  mov     [rbp+0E0h+var_C8], rdi
0x1800bfcee  mov     [rbp+0E0h+var_B8], rdi
0x1800bfcf2  mov     [rsp+1E0h+var_168], rdi
0x1800bfcf7  mov     qword ptr [rsp+1E0h+var_170], rdi
0x1800bfcfc  mov     [rbp+0E0h+lpMem], rdi
0x1800bfd00  mov     [rbp+0E0h+arg_10], rdi
0x1800bfd07  mov     [rbp+0E0h+arg_18], rdi
0x1800bfd0e  jnb     short loc_1800BFD1C
0x1800bfd10  mov     [rbp+0E0h+var_148], 0E31h
0x1800bfd17  jmp     loc_1800C036E
0x1800bfd1c  test    dword ptr [r8+4], 0FFFFFFFEh
0x1800bfd24  jz      short loc_1800BFD32
0x1800bfd26  mov     [rbp+0E0h+var_148], 0E34h
0x1800bfd2d  jmp     loc_1800C036E
0x1800bfd32  mov     rcx, [r8+10h]; struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ *
0x1800bfd36  call    ?IsValidComponentReference@@YAEPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsValidComponentReference(Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const *)
0x1800bfd3b  test    al, al
0x1800bfd3d  jnz     short loc_1800BFD4B
0x1800bfd3f  mov     [rbp+0E0h+var_148], 0E35h
0x1800bfd46  jmp     loc_1800C036E
0x1800bfd4b  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@VCFsobj@Private@Fs@34@UFSOBJ_CONSTRUCTOR_DATA@6734@VCFsobjTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT,Windows::Isolation::Fs::Private::CFsobj,Windows::Isolation::Fs::Private::FSOBJ_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsobjTraits>::ms_ptti
0x1800bfd52  test    rdx, rdx
0x1800bfd55  jz      loc_1800C0367
0x1800bfd5b  lea     r15, [r8+8]
0x1800bfd5f  mov     rcx, [r15]
0x1800bfd62  call    RtlIsTypeSafeHandleValid
0x1800bfd67  test    al, al
0x1800bfd69  jz      loc_1800C0367
0x1800bfd6f  mov     rcx, cs:qword_180166950
0x1800bfd76  test    rcx, rcx
0x1800bfd79  jz      loc_1800C02A8
0x1800bfd7f  mov     rcx, [rcx]
0x1800bfd82  lea     r14, [rsi+18h]
0x1800bfd86  mov     rdx, [r14]
0x1800bfd89  call    RtlIsBaseIdentityHandleValidWithType
0x1800bfd8e  test    al, al
0x1800bfd90  jz      loc_1800C02A1
0x1800bfd96  mov     [rsp+1E0h+var_178], r14
0x1800bfd9b  lea     rax, ?RtlTraceFormat_PCDEFINITION_IDENTITY@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCDEFINITION_IDENTITY(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x1800bfda2  mov     [rsp+1E0h+var_180], rax
0x1800bfda7  lea     r9, aInstallCompone; "   Install Component Data:\n      Manif"...
0x1800bfdae  lea     rax, aDefid; "defid"
0x1800bfdb5  mov     ebx, 1
0x1800bfdba  mov     [rsp+1E0h+var_188], rax
0x1800bfdbf  lea     rdx, ?Facility_IsolationComponentStore@Rtl@Isolation@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1800bfdc6  mov     rax, [rsi+10h]
0x1800bfdca  mov     r8d, ebx; struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *
0x1800bfdcd  mov     [rsp+1E0h+var_190], rax
0x1800bfdd2  xor     ecx, ecx; this
0x1800bfdd4  lea     rax, RtlTraceFormat_PCCOMPONENT_STORE_REFERENCE
0x1800bfddb  mov     [rsp+1E0h+var_198], rax
0x1800bfde0  lea     rax, aRef; "ref"
0x1800bfde7  mov     [rsp+1E0h+var_1A0], rax
0x1800bfdec  lea     rax, ?RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z; Windows::Isolation::Rtl::RtlTraceFormat_PCISOLATED_FILESYSTEM_OBJECT(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)
0x1800bfdf3  mov     [rsp+1E0h+var_1A8], r15
0x1800bfdf8  mov     [rsp+1E0h+var_1B0], rax
0x1800bfdfd  lea     rax, aMf; "mf"
0x1800bfe04  mov     [rsp+1E0h+var_1B8], rax; unsigned __int64
0x1800bfe09  mov     [rsp+1E0h+var_1C0], 3; char *
0x1800bfe12  call    ?RtlTrace@Rtl@Isolation@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@KQEBD_KZZ; Windows::Isolation::Rtl::RtlTrace(ulong,Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *,ulong,char const * const,unsigned __int64,...)
0x1800bfe17  mov     rdx, [r13+300h]
0x1800bfe1e  lea     r8, [rbp+0E0h+arg_18]
0x1800bfe25  call    RtlGetSystemIsolatedFilesystem
0x1800bfe2a  mov     edi, eax
0x1800bfe2c  test    eax, eax
0x1800bfe2e  jns     loc_1800BFEF2
0x1800bfe34  mov     r10, [rbp+0E0h+arg_18]
0x1800bfe3b  xor     esi, esi
0x1800bfe3d  test    r10, r10
0x1800bfe40  jz      short loc_1800BFEA5
0x1800bfe42  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rbx; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bfe49  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bfe50  mov     [rbp+0E0h+var_140], 0C00000E5h
0x1800bfe57  mov     [rbp+0E0h+var_150], rax
0x1800bfe5b  test    r10, r10
0x1800bfe5e  jz      short loc_1800BFE8A
0x1800bfe60  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bfe67  test    r11, r11
0x1800bfe6a  jz      short loc_1800BFEDD
0x1800bfe6c  mov     rdx, r11
0x1800bfe6f  mov     rcx, r10
0x1800bfe72  call    RtlIsTypeSafeHandleValid
0x1800bfe77  test    al, al
0x1800bfe79  jz      short loc_1800BFEDD
0x1800bfe7b  mov     ecx, [r11]
0x1800bfe7e  mov     rdx, r10
0x1800bfe81  mov     rax, [r11+20h]
0x1800bfe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe8a  mov     ecx, esi; dwExceptionCode
0x1800bfe8c  test    ecx, ecx
0x1800bfe8e  jns     short loc_1800BFE9E
0x1800bfe90  xor     r9d, r9d; lpArguments
0x1800bfe93  xor     r8d, r8d; nNumberOfArguments
0x1800bfe96  mov     edx, ebx; dwExceptionFlags
0x1800bfe98  call    cs:__imp_RaiseException
0x1800bfe9e  mov     [rbp+0E0h+arg_18], rsi
0x1800bfea5  mov     rcx, [rbp+0E0h+arg_10]
0x1800bfeac  test    rcx, rcx
0x1800bfeaf  jz      short loc_1800BFEBD
0x1800bfeb1  call    CdfCloseHandle
0x1800bfeb6  mov     [rbp+0E0h+arg_10], rsi
0x1800bfebd  mov     rcx, [rbp+0E0h+lpMem]
0x1800bfec1  test    rcx, rcx
0x1800bfec4  jz      loc_1800C027E
0x1800bfeca  mov     [rsp+1E0h+var_168], rsi
0x1800bfecf  mov     qword ptr [rsp+1E0h+var_170], rsi
0x1800bfed4  mov     [rbp+0E0h+lpMem], rsi
0x1800bfed8  jmp     loc_1800C0279
0x1800bfedd  mov     [rbp+0E0h+var_148], 124h
0x1800bfee4  lea     rcx, [rbp+0E0h+var_150]
0x1800bfee8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bfeed  mov     ecx, [rbp+0E0h+var_140]
0x1800bfef0  jmp     short loc_1800BFE8C
0x1800bfef2  mov     rax, [r15]
0x1800bfef5  lea     r8, [rsp+1E0h+var_170]
0x1800bfefa  mov     rcx, [rbp+0E0h+arg_18]
0x1800bff01  lea     rdx, [rbp+0E0h+var_138]
0x1800bff05  mov     [rbp+0E0h+var_130], rax
0x1800bff09  xorps   xmm0, xmm0
0x1800bff0c  lea     rax, g_LUNICODE_STRING__empty_
0x1800bff13  mov     [rbp+0E0h+var_138], 30h ; '0'
0x1800bff1b  xor     r9d, r9d
0x1800bff1e  mov     [rbp+0E0h+var_128], rax
0x1800bff22  mov     [rbp+0E0h+var_120], 40h ; '@'
0x1800bff29  movdqu  [rbp+0E0h+var_118], xmm0
0x1800bff2e  call    RtlIsolatedFilesystemGetFileContents
0x1800bff33  xor     r15d, r15d
0x1800bff36  mov     edi, eax
0x1800bff38  test    eax, eax
0x1800bff3a  js      short loc_1800BFF5B
0x1800bff3c  xor     r9d, r9d; int
0x1800bff3f  mov     [rsp+1E0h+var_1C0], r15; void *
0x1800bff44  lea     r8, [rbp+0E0h+arg_10]; int
0x1800bff4b  lea     rcx, [rsp+1E0h+var_170]; int
0x1800bff50  call    RtlCompileCdfFromXmlBlob
0x1800bff55  mov     edi, eax
0x1800bff57  test    eax, eax
0x1800bff59  jns     short loc_1800BFFC4
0x1800bff5b  mov     r10, [rbp+0E0h+arg_18]
0x1800bff62  test    r10, r10
0x1800bff65  jz      loc_1800C024A
0x1800bff6b  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rbx; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bff72  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bff79  mov     [rbp+0E0h+var_140], 0C00000E5h
0x1800bff80  mov     [rbp+0E0h+var_150], rax
0x1800bff84  test    r10, r10
0x1800bff87  jz      loc_1800C022E
0x1800bff8d  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bff94  test    r11, r11
0x1800bff97  jz      short loc_1800BFFAC
0x1800bff99  mov     rdx, r11
0x1800bff9c  mov     rcx, r10
0x1800bff9f  call    RtlIsTypeSafeHandleValid
0x1800bffa4  test    al, al
0x1800bffa6  jnz     loc_1800C021F
0x1800bffac  mov     [rbp+0E0h+var_148], 124h
0x1800bffb3  lea     rcx, [rbp+0E0h+var_150]
0x1800bffb7  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bffbc  mov     ecx, [rbp+0E0h+var_140]
0x1800bffbf  jmp     loc_1800C0231
0x1800bffc4  mov     rdx, [rbp+0E0h+arg_10]
0x1800bffcb  lea     rcx, [rbp+0E0h+var_100]
0x1800bffcf  call    ?Attach@CComponentAccessor@@QEAAJU_CDF@Rtl@Cdf@Windows@@@Z; CComponentAccessor::Attach(Windows::Cdf::Rtl::_CDF)
0x1800bffd4  mov     edi, eax
0x1800bffd6  test    eax, eax
0x1800bffd8  js      short loc_1800BFF5B
0x1800bffda  mov     r8, [r14]
0x1800bffdd  lea     r9, [rbp+0E0h+arg_8]
0x1800bffe4  mov     rdx, [rbp+0E0h+var_100]
0x1800bffe8  xor     ecx, ecx
0x1800bffea  mov     byte ptr [rbp+0E0h+arg_8], r15b
0x1800bfff1  call    RtlAreDefinitionIdentitiesEqual
0x1800bfff6  mov     edi, eax
0x1800bfff8  test    eax, eax
0x1800bfffa  js      loc_1800C01DA
0x1800c0000  cmp     byte ptr [rbp+0E0h+arg_8], r15b
0x1800c0007  setnz   al
0x1800c000a  test    al, al
0x1800c000c  jnz     loc_1800C00D6
0x1800c0012  mov     r10, [rbp+0E0h+arg_18]
0x1800c0019  mov     [rbp+0E0h+var_148], 0E62h
0x1800c0020  test    r10, r10
0x1800c0023  jz      short loc_1800C0089
0x1800c0025  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rbx; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c002c  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c0033  mov     dword ptr [rbp+0E0h+var_128], 0C00000E5h
0x1800c003a  mov     [rbp+0E0h+var_138], rax
0x1800c003e  test    r10, r10
0x1800c0041  jz      short loc_1800C006D
0x1800c0043  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c004a  test    r11, r11
0x1800c004d  jz      short loc_1800C00C1
0x1800c004f  mov     rdx, r11
0x1800c0052  mov     rcx, r10
0x1800c0055  call    RtlIsTypeSafeHandleValid
0x1800c005a  test    al, al
0x1800c005c  jz      short loc_1800C00C1
0x1800c005e  mov     ecx, [r11]
0x1800c0061  mov     rdx, r10
0x1800c0064  mov     rax, [r11+20h]
0x1800c0068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c006d  mov     ecx, r15d; dwExceptionCode
0x1800c0070  test    ecx, ecx
0x1800c0072  jns     short loc_1800C0082
0x1800c0074  xor     r9d, r9d; lpArguments
0x1800c0077  xor     r8d, r8d; nNumberOfArguments
0x1800c007a  mov     edx, ebx; dwExceptionFlags
0x1800c007c  call    cs:__imp_RaiseException
0x1800c0082  mov     [rbp+0E0h+arg_18], r15
0x1800c0089  mov     rcx, [rbp+0E0h+arg_10]
0x1800c0090  test    rcx, rcx
0x1800c0093  jz      short loc_1800C00A1
0x1800c0095  call    CdfCloseHandle
0x1800c009a  mov     [rbp+0E0h+arg_10], r15
0x1800c00a1  mov     rcx, [rbp+0E0h+lpMem]
0x1800c00a5  test    rcx, rcx
0x1800c00a8  jz      loc_1800C036E
0x1800c00ae  mov     [rsp+1E0h+var_168], r15
0x1800c00b3  mov     qword ptr [rsp+1E0h+var_170], r15
0x1800c00b8  mov     [rbp+0E0h+lpMem], r15
0x1800c00bc  jmp     loc_1800C034B
0x1800c00c1  mov     dword ptr [rbp+0E0h+var_130], 124h
0x1800c00c8  lea     rcx, [rbp+0E0h+var_138]
0x1800c00cc  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c00d1  mov     ecx, dword ptr [rbp+0E0h+var_128]
0x1800c00d4  jmp     short loc_1800C0070
0x1800c00d6  mov     rax, [rbp+0E0h+arg_10]
0x1800c00dd  lea     r9, [rbp+0E0h+var_100]
0x1800c00e1  mov     [rsp+1E0h+var_1A8], r12
0x1800c00e6  mov     rcx, r13
0x1800c00e9  mov     [rsp+1E0h+var_1B8], rax
0x1800c00ee  lea     rax, [rsp+1E0h+var_170]
0x1800c00f3  mov     [rsp+1E0h+var_1C0], rax
0x1800c00f8  call    ?RealInstallComponent@CCSDirectTransaction@@IEAAJKKAEBVCComponentAccessor@@AEBU_LBLOB@@U_CDF@Rtl@Cdf@Windows@@PEBU_ISOLATED_FILESYSTEM_OBJECT@5Isolation@7@AEAK@Z; CCSDirectTransaction::RealInstallComponent(ulong,ulong,CComponentAccessor const &,_LBLOB const &,Windows::Cdf::Rtl::_CDF,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT const *,ulong &)
0x1800c00fd  mov     edi, eax
0x1800c00ff  test    eax, eax
0x1800c0101  js      loc_1800C01DA
0x1800c0107  mov     rdx, [rbp+0E0h+var_100]
0x1800c010b  lea     r9, [rbp+0E0h+var_158]
0x1800c010f  mov     [rbp+0E0h+var_B0], r15
0x1800c0113  mov     [rbp+0E0h+var_78], r15
0x1800c0117  mov     [rbp+0E0h+var_80], r15
0x1800c011b  mov     [rbp+0E0h+var_70], r15
0x1800c011f  mov     [rbp+0E0h+var_60], r15
0x1800c0126  mov     [rbp+0E0h+var_68], r15
0x1800c012a  mov     [rbp+0E0h+var_58], r15
0x1800c0131  mov     [rbp+0E0h+var_48], r15
0x1800c0138  mov     [rbp+0E0h+var_50], r15
0x1800c013f  mov     [rbp+0E0h+var_40], r15
0x1800c0146  mov     [rbp+0E0h+var_158], r15
0x1800c014a  call    ?IsoDefinitionAppidFromPieces@@YAJPEBU_LUNICODE_STRING@@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@0AEAU_DEFINITION_APPID@345@@Z; IsoDefinitionAppidFromPieces(_LUNICODE_STRING const *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_DEFINITION_APPID &)
0x1800c014f  mov     edi, eax
0x1800c0151  test    eax, eax
0x1800c0153  jns     short loc_1800C015B
0x1800c0155  mov     rcx, [rbp+0E0h+var_158]
0x1800c0159  jmp     short loc_1800C01C3
0x1800c015b  mov     rdx, [rbp+0E0h+var_158]
0x1800c015f  lea     rcx, [rbp+0E0h+var_B0]
0x1800c0163  call    ?Attach@CApplicationAccessor@@QEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; CApplicationAccessor::Attach(Windows::Isolation::Rtl::_DEFINITION_APPID)
0x1800c0168  mov     edi, eax
0x1800c016a  test    eax, eax
0x1800c016c  js      short loc_1800C0155
0x1800c016e  mov     r9, [rsi+10h]
0x1800c0172  lea     r14, [r13+0C50h]
0x1800c0179  mov     rcx, r14
0x1800c017c  lea     r8, [rbp+0E0h+var_B0]
0x1800c0180  mov     edx, 4
0x1800c0185  call    ?GenericAddSingleMark@CComponentMarkManager@@AEAAJW4eMarkType@1@AEBVCApplicationAccessor@@AEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; CComponentMarkManager::GenericAddSingleMark(CComponentMarkManager::eMarkType,CApplicationAccessor const &,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const &)
0x1800c018a  mov     edi, eax
0x1800c018c  test    eax, eax
0x1800c018e  js      short loc_1800C0155
  ... truncated ...
```
