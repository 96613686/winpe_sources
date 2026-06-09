# CCSDirectTransaction::GetAppDirectoryForAppId(Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)

- ea: `0x1800bdbe4`
- end: `0x1800bdf28`
- name: `?GetAppDirectoryForAppId@CCSDirectTransaction@@AEAAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEAU_ISOLATED_FILESYSTEM_OBJECT@345@@Z`
- size: `836`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800be69c`
- `0x18010e7a4`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x18001504c`
- `0x18001de74`
- `0x180040020`
- `0x18004f2dc`
- `0x180050f7c`
- `0x1800bdbe4`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdcf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bddc0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdcf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bddc0`

## string_xrefs

- `0x1800bdcaa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bdd71`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bdea0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bdc05`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::GetAppDirectoryForAppId(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  int SystemIsolatedFilesystem; // edi
  __int64 v9; // r10
  unsigned int *v10; // r11
  signed int v11; // ecx
  void *v12; // rcx
  __int64 v13; // r14
  __int64 v14; // r10
  unsigned int *v15; // r11
  signed int v16; // ecx
  __int64 v17; // r10
  int v18; // eax
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-49h] BYREF
  __int64 v22; // [rsp+38h] [rbp-41h]
  void *lpMem; // [rsp+40h] [rbp-39h]
  const char *v24; // [rsp+48h] [rbp-31h] BYREF
  int v25; // [rsp+50h] [rbp-29h]
  int v26; // [rsp+58h] [rbp-21h]
  const char *v27; // [rsp+60h] [rbp-19h] BYREF
  int v28; // [rsp+68h] [rbp-11h]
  unsigned int v29; // [rsp+70h] [rbp-9h]
  __int64 v30; // [rsp+78h] [rbp-1h] BYREF
  __int64 v31; // [rsp+80h] [rbp+7h]
  __int64 *v32; // [rsp+88h] [rbp+Fh]
  int v33; // [rsp+90h] [rbp+17h]
  __int128 v34; // [rsp+98h] [rbp+1Fh]
  __int64 v35; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v36; // [rsp+F0h] [rbp+77h] BYREF

  *a3 = 0;
  v29 = -1073741595;
  v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppId,CDefAppIdCD,CDefAppIdTraits>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(a2) )
  {
    v28 = 2141;
    goto LABEL_38;
  }
  v7 = *(_QWORD *)(a1 + 768);
  v32 = &g_LUNICODE_STRING__empty_;
  v30 = 48;
  v34 = 0;
  v31 = 0;
  v33 = 64;
  v22 = 0;
  v21 = 0;
  lpMem = 0;
  v35 = 0;
  v36 = 0;
  SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v6, v7, &v36);
  if ( SystemIsolatedFilesystem >= 0 )
  {
    v13 = a1 + 1072;
    if ( v13 )
    {
      SystemIsolatedFilesystem = IdentityToKeyFormWithLessStack<Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Rtl::CLUNICODE_STRING>(
                                   a2,
                                   &v21);
      if ( SystemIsolatedFilesystem >= 0 )
      {
        v31 = *(_QWORD *)(v13 + 40);
        v30 = 48;
        v32 = &v21;
        v33 = 64;
        v34 = 0;
        v18 = Windows::Isolation::Implementation::Rtl::CreateDirectories(0, v36, &v35, 0, &v30);
        v17 = v36;
        SystemIsolatedFilesystem = v18;
        if ( v18 >= 0 )
        {
          v19 = v35;
          SystemIsolatedFilesystem = 0;
          v35 = *a3;
          *a3 = v19;
        }
      }
      else
      {
        v17 = v36;
      }
      if ( !v17 )
        goto LABEL_11;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v26 = -1073741595;
      v24 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v17) )
      {
        v25 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v24);
        v11 = v26;
        goto LABEL_8;
      }
      goto LABEL_7;
    }
    v28 = 2158;
    if ( v36 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v26 = -1073741595;
      v24 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v36) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v14);
        v16 = 0;
      }
      else
      {
        v25 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v24);
        v16 = v26;
      }
      if ( v16 < 0 )
        RaiseException(v16, 1u, 0, 0);
      v36 = 0;
    }
    if ( v35 )
    {
      RtlCloseIsolatedFilesystemObjectHandle(v35);
      v35 = 0;
    }
LABEL_38:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v27,
      &v27);
    return v29;
  }
  if ( v36 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v29 = -1073741595;
    v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v36) )
    {
      v28 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
      v11 = v29;
      goto LABEL_8;
    }
LABEL_7:
    (*((void (__fastcall **)(_QWORD, __int64))v10 + 4))(*v10, v9);
    v11 = 0;
LABEL_8:
    if ( v11 < 0 )
      RaiseException(v11, 1u, 0, 0);
    v36 = 0;
  }
LABEL_11:
  if ( v35 )
  {
    RtlCloseIsolatedFilesystemObjectHandle(v35);
    v35 = 0;
  }
  v12 = lpMem;
  if ( lpMem )
  {
    v22 = 0;
    v21 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v12);
  }
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800bdbe4  mov     [rsp-8+arg_0], rbx
0x1800bdbe9  mov     [rsp-8+arg_18], rsi
0x1800bdbee  push    rbp
0x1800bdbef  push    rdi
0x1800bdbf0  push    r12
0x1800bdbf2  push    r14
0x1800bdbf4  push    r15
0x1800bdbf6  lea     rbp, [rsp-37h]
0x1800bdbfb  sub     rsp, 0B0h
0x1800bdc02  xor     r15d, r15d
0x1800bdc05  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bdc0c  mov     [r8], r15
0x1800bdc0f  mov     rbx, rdx
0x1800bdc12  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCDefAppId@@VCDefAppIdCD@@VCDefAppIdTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,CDefAppId,CDefAppIdCD,CDefAppIdTraits>::ms_ptti
0x1800bdc19  mov     r12d, 0C00000E5h
0x1800bdc1f  mov     [rbp+57h+var_60], r12d
0x1800bdc23  mov     rsi, r8
0x1800bdc26  mov     [rbp+57h+var_70], rax
0x1800bdc2a  mov     r14, rcx
0x1800bdc2d  test    rdx, rdx
0x1800bdc30  jz      loc_1800BDEF3
0x1800bdc36  mov     rcx, rbx
0x1800bdc39  call    RtlIsTypeSafeHandleValid
0x1800bdc3e  test    al, al
0x1800bdc40  jz      loc_1800BDEF3
0x1800bdc46  mov     rdx, [r14+300h]
0x1800bdc4d  lea     rax, g_LUNICODE_STRING__empty_
0x1800bdc54  xorps   xmm0, xmm0
0x1800bdc57  mov     [rbp+57h+var_48], rax
0x1800bdc5b  lea     r8, [rbp+57h+arg_10]
0x1800bdc5f  mov     [rbp+57h+var_58], 30h ; '0'
0x1800bdc67  movdqu  [rbp+57h+var_38], xmm0
0x1800bdc6c  mov     [rbp+57h+var_50], r15
0x1800bdc70  mov     [rbp+57h+var_40], 40h ; '@'
0x1800bdc77  mov     [rbp+57h+var_98], r15
0x1800bdc7b  mov     [rbp+57h+var_A0], r15
0x1800bdc7f  mov     [rbp+57h+lpMem], r15
0x1800bdc83  mov     [rbp+57h+arg_8], r15
0x1800bdc87  mov     [rbp+57h+arg_10], r15
0x1800bdc8b  call    RtlGetSystemIsolatedFilesystem
0x1800bdc90  mov     edi, eax
0x1800bdc92  test    eax, eax
0x1800bdc94  jns     loc_1800BDD4D
0x1800bdc9a  mov     r10, [rbp+57h+arg_10]
0x1800bdc9e  test    r10, r10
0x1800bdca1  jz      short loc_1800BDD03
0x1800bdca3  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bdcaa  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bdcb1  mov     [rbp+57h+var_60], r12d
0x1800bdcb5  mov     [rbp+57h+var_70], rax
0x1800bdcb9  test    r10, r10
0x1800bdcbc  jz      short loc_1800BDCE8
0x1800bdcbe  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bdcc5  test    r11, r11
0x1800bdcc8  jz      short loc_1800BDD38
0x1800bdcca  mov     rdx, r11
0x1800bdccd  mov     rcx, r10
0x1800bdcd0  call    RtlIsTypeSafeHandleValid
0x1800bdcd5  test    al, al
0x1800bdcd7  jz      short loc_1800BDD38
0x1800bdcd9  mov     ecx, [r11]
0x1800bdcdc  mov     rdx, r10
0x1800bdcdf  mov     rax, [r11+20h]
0x1800bdce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdce8  mov     ecx, r15d; dwExceptionCode
0x1800bdceb  test    ecx, ecx
0x1800bdced  jns     short loc_1800BDCFF
0x1800bdcef  xor     r9d, r9d; lpArguments
0x1800bdcf2  xor     r8d, r8d; nNumberOfArguments
0x1800bdcf5  lea     edx, [r9+1]; dwExceptionFlags
0x1800bdcf9  call    cs:__imp_RaiseException
0x1800bdcff  mov     [rbp+57h+arg_10], r15
0x1800bdd03  mov     rcx, [rbp+57h+arg_8]
0x1800bdd07  test    rcx, rcx
0x1800bdd0a  jz      short loc_1800BDD15
0x1800bdd0c  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800bdd11  mov     [rbp+57h+arg_8], r15
0x1800bdd15  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800bdd19  test    rcx, rcx
0x1800bdd1c  jz      loc_1800BDF0A
0x1800bdd22  mov     [rbp+57h+var_98], r15
0x1800bdd26  mov     [rbp+57h+var_A0], r15
0x1800bdd2a  mov     [rbp+57h+lpMem], r15
0x1800bdd2e  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800bdd33  jmp     loc_1800BDF0A
0x1800bdd38  mov     [rbp+57h+var_68], 124h
0x1800bdd3f  lea     rcx, [rbp+57h+var_70]
0x1800bdd43  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bdd48  mov     ecx, [rbp+57h+var_60]
0x1800bdd4b  jmp     short loc_1800BDCEB
0x1800bdd4d  add     r14, 430h
0x1800bdd54  jnz     loc_1800BDE14
0x1800bdd5a  mov     r10, [rbp+57h+arg_10]
0x1800bdd5e  mov     [rbp+57h+var_68], 86Eh
0x1800bdd65  test    r10, r10
0x1800bdd68  jz      short loc_1800BDDCA
0x1800bdd6a  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bdd71  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bdd78  mov     [rbp+57h+var_78], r12d
0x1800bdd7c  mov     [rbp+57h+var_88], rax
0x1800bdd80  test    r10, r10
0x1800bdd83  jz      short loc_1800BDDAF
0x1800bdd85  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bdd8c  test    r11, r11
0x1800bdd8f  jz      short loc_1800BDDFF
0x1800bdd91  mov     rdx, r11
0x1800bdd94  mov     rcx, r10
0x1800bdd97  call    RtlIsTypeSafeHandleValid
0x1800bdd9c  test    al, al
0x1800bdd9e  jz      short loc_1800BDDFF
0x1800bdda0  mov     ecx, [r11]
0x1800bdda3  mov     rdx, r10
0x1800bdda6  mov     rax, [r11+20h]
0x1800bddaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bddaf  mov     ecx, r15d; dwExceptionCode
0x1800bddb2  test    ecx, ecx
0x1800bddb4  jns     short loc_1800BDDC6
0x1800bddb6  xor     r9d, r9d; lpArguments
0x1800bddb9  xor     r8d, r8d; nNumberOfArguments
0x1800bddbc  lea     edx, [r9+1]; dwExceptionFlags
0x1800bddc0  call    cs:__imp_RaiseException
0x1800bddc6  mov     [rbp+57h+arg_10], r15
0x1800bddca  mov     rcx, [rbp+57h+arg_8]
0x1800bddce  test    rcx, rcx
0x1800bddd1  jz      short loc_1800BDDDC
0x1800bddd3  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800bddd8  mov     [rbp+57h+arg_8], r15
0x1800bdddc  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800bdde0  test    rcx, rcx
0x1800bdde3  jz      loc_1800BDEFA
0x1800bdde9  mov     [rbp+57h+var_98], r15
0x1800bdded  mov     [rbp+57h+var_A0], r15
0x1800bddf1  mov     [rbp+57h+lpMem], r15
0x1800bddf5  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800bddfa  jmp     loc_1800BDEFA
0x1800bddff  mov     [rbp+57h+var_80], 124h
0x1800bde06  lea     rcx, [rbp+57h+var_88]
0x1800bde0a  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bde0f  mov     ecx, [rbp+57h+var_78]
0x1800bde12  jmp     short loc_1800BDDB2
0x1800bde14  lea     rdx, [rbp+57h+var_A0]
0x1800bde18  mov     rcx, rbx
0x1800bde1b  call    ??$IdentityToKeyFormWithLessStack@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCLUNICODE_STRING@24@@@YAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEAVCLUNICODE_STRING@13@@Z; IdentityToKeyFormWithLessStack<Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Rtl::CLUNICODE_STRING>(Windows::Isolation::Rtl::_DEFINITION_APPID,Windows::Rtl::CLUNICODE_STRING &)
0x1800bde20  mov     edi, eax
0x1800bde22  test    eax, eax
0x1800bde24  jns     short loc_1800BDE44
0x1800bde26  mov     r10, [rbp+57h+arg_10]
0x1800bde2a  jmp     short loc_1800BDE90
0x1800bde2c  mov     [rbp+57h+var_80], 124h
0x1800bde33  lea     rcx, [rbp+57h+var_88]
0x1800bde37  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bde3c  mov     ecx, [rbp+57h+var_78]
0x1800bde3f  jmp     loc_1800BDCEB
0x1800bde44  mov     rax, [r14+28h]
0x1800bde48  lea     r8, [rbp+57h+arg_8]
0x1800bde4c  mov     rdx, [rbp+57h+arg_10]
0x1800bde50  xorps   xmm0, xmm0
0x1800bde53  mov     [rbp+57h+var_50], rax
0x1800bde57  xor     r9d, r9d
0x1800bde5a  lea     rax, [rbp+57h+var_A0]
0x1800bde5e  mov     [rbp+57h+var_58], 30h ; '0'
0x1800bde66  mov     [rbp+57h+var_48], rax
0x1800bde6a  xor     ecx, ecx
0x1800bde6c  lea     rax, [rbp+57h+var_58]
0x1800bde70  mov     [rbp+57h+var_40], 40h ; '@'
0x1800bde77  mov     [rsp+0D0h+var_B0], rax
0x1800bde7c  movdqu  [rbp+57h+var_38], xmm0
0x1800bde81  call    ?CreateDirectories@Rtl@Implementation@Isolation@Windows@@YAJKU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@KPEBU_ISOLATED_OBJECT_ATTRIBUTES@134@@Z; Windows::Isolation::Implementation::Rtl::CreateDirectories(ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *,ulong,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *)
0x1800bde86  mov     r10, [rbp+57h+arg_10]
0x1800bde8a  mov     edi, eax
0x1800bde8c  test    eax, eax
0x1800bde8e  jns     short loc_1800BDEE0
0x1800bde90  test    r10, r10
0x1800bde93  jz      loc_1800BDD03
0x1800bde99  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bdea0  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bdea7  mov     [rbp+57h+var_78], r12d
0x1800bdeab  mov     [rbp+57h+var_88], rax
0x1800bdeaf  test    r10, r10
0x1800bdeb2  jz      loc_1800BDCE8
0x1800bdeb8  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bdebf  test    r11, r11
0x1800bdec2  jz      loc_1800BDE2C
0x1800bdec8  mov     rdx, r11
0x1800bdecb  mov     rcx, r10
0x1800bdece  call    RtlIsTypeSafeHandleValid
0x1800bded3  test    al, al
0x1800bded5  jz      loc_1800BDE2C
0x1800bdedb  jmp     loc_1800BDCD9
0x1800bdee0  mov     rax, [rbp+57h+arg_8]
0x1800bdee4  mov     edi, r15d
0x1800bdee7  mov     rcx, [rsi]
0x1800bdeea  mov     [rbp+57h+arg_8], rcx
0x1800bdeee  mov     [rsi], rax
0x1800bdef1  jmp     short loc_1800BDE90
0x1800bdef3  mov     [rbp+57h+var_68], 85Dh
0x1800bdefa  lea     rdx, [rbp+57h+var_70]
0x1800bdefe  lea     rcx, [rbp+57h+var_70]
0x1800bdf02  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800bdf07  mov     edi, [rbp+57h+var_60]
0x1800bdf0a  lea     r11, [rsp+0D0h+var_20]
0x1800bdf12  mov     eax, edi
0x1800bdf14  mov     rbx, [r11+30h]
0x1800bdf18  mov     rsi, [r11+48h]
0x1800bdf1c  mov     rsp, r11
0x1800bdf1f  pop     r15
0x1800bdf21  pop     r14
0x1800bdf23  pop     r12
0x1800bdf25  pop     rdi
0x1800bdf26  pop     rbp
0x1800bdf27  retn
```
