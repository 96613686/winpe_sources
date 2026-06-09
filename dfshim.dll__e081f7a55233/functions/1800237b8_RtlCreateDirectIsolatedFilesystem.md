# RtlCreateDirectIsolatedFilesystem

- ea: `0x1800237b8`
- end: `0x180023a4a`
- name: `RtlCreateDirectIsolatedFilesystem`
- size: `658`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180013770`
- `0x180026db4`
- `0x1800a29f0`
- `0x1800a33fc`
- `0x1800ae5d8`
- `0x1800af0d8`
- `0x1800afe70`

## callees

- `0x180012b1c`
- `0x18001ccac`
- `0x1800237b8`
- `0x18004f2dc`
- `0x18005429c`
- `0x1800bab38`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023881`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023951`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800239cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023881`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023951`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800239cc`

## string_xrefs

- `0x180023828`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800238b2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800238e7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800237cd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall RtlCreateDirectIsolatedFilesystem(Windows::Isolation::FsProv::Rtl *a1, __int64 *a2, __int64 a3)
{
  unsigned int v4; // r8d
  int IsolatedFilesystemFromProvider; // r14d
  __int64 v6; // r10
  __int64 v7; // r10
  unsigned int *v8; // r11
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int *v13; // r10
  int v14; // ecx
  unsigned int *v15; // r10
  int v16; // ecx
  __int64 v17; // r11
  unsigned int *v18; // r10
  __int64 v19; // r11
  struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *v21; // [rsp+20h] [rbp-28h] BYREF
  int v22; // [rsp+28h] [rbp-20h]
  DWORD dwExceptionCode; // [rsp+30h] [rbp-18h]
  __int64 v24; // [rsp+90h] [rbp+48h] BYREF

  v24 = a3;
  dwExceptionCode = -1073741595;
  v21 = (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\ba"
                                                                       "se\\isolation\\win32\\isofs_direct.cpp";
  if ( !a2 )
  {
    v22 = 2301;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
    return dwExceptionCode;
  }
  *a2 = 0;
  v24 = 0;
  IsolatedFilesystemFromProvider = Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(
                                     a1,
                                     (unsigned int)&Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem,
                                     (struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *)&v24,
                                     0,
                                     v21);
  if ( IsolatedFilesystemFromProvider < 0 )
  {
    v6 = v24;
    if ( !v24 )
      return (unsigned int)IsolatedFilesystemFromProvider;
    goto LABEL_4;
  }
  if ( !Windows::Isolation::Rtl::RtlIsTracingEnabled(
          (Windows::Isolation::Rtl *)&Windows::Isolation::Rtl::Facility_IsolationIsolatedFilesystem,
          (struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *)1,
          v4) )
  {
LABEL_30:
    v17 = *a2;
    IsolatedFilesystemFromProvider = 0;
    *a2 = v24;
    if ( !v17 )
      return (unsigned int)IsolatedFilesystemFromProvider;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    dwExceptionCode = -1073741595;
    v21 = (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\"
                                                                         "base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v17) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v19);
      goto LABEL_8;
    }
    goto LABEL_11;
  }
  v11 = v24;
  v12 = v24;
  v24 = 0;
  IsolatedFilesystemFromProvider = RtlCreateTracingFilesystem(v10, v12, &v24, 0);
  if ( IsolatedFilesystemFromProvider >= 0 )
  {
    if ( v11 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      dwExceptionCode = -1073741595;
      v21 = (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy"
                                                                           "\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v11) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v11);
        v16 = 0;
      }
      else
      {
        v22 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
        v16 = dwExceptionCode;
      }
      if ( v16 < 0 )
        RaiseException(v16, 1u, 0, 0);
    }
    goto LABEL_30;
  }
  if ( v11 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    dwExceptionCode = -1073741595;
    v21 = (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\"
                                                                         "base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v11) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v11);
      v14 = 0;
    }
    else
    {
      v22 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
      v14 = dwExceptionCode;
    }
    if ( v14 < 0 )
      RaiseException(v14, 1u, 0, 0);
  }
  v6 = v24;
  if ( v24 )
  {
LABEL_4:
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v21 = (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\"
                                                                         "base\\isolation\\inc\\tsh_provider.h";
    dwExceptionCode = -1073741595;
    if ( !v6 )
    {
LABEL_8:
      v9 = 0;
      goto LABEL_9;
    }
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v6) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v8 + 4))(*v8, v7);
      goto LABEL_8;
    }
LABEL_11:
    v22 = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
    v9 = dwExceptionCode;
LABEL_9:
    if ( v9 < 0 )
      RaiseException(v9, 1u, 0, 0);
  }
  return (unsigned int)IsolatedFilesystemFromProvider;
}

```

## disassembly

```asm
0x1800237b8  mov     [rsp-30h+arg_10], r8
0x1800237bd  push    rbp
0x1800237be  push    rbx
0x1800237bf  push    rsi
0x1800237c0  push    r13
0x1800237c2  push    r14
0x1800237c4  push    r15
0x1800237c6  mov     rbp, rsp
0x1800237c9  sub     rsp, 48h
0x1800237cd  lea     rax, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800237d4  mov     r13d, 0C00000E5h
0x1800237da  mov     [rbp+dwExceptionCode], r13d
0x1800237de  mov     r15, rdx
0x1800237e1  mov     [rbp+var_28], rax
0x1800237e5  test    rdx, rdx
0x1800237e8  jz      loc_180023A25
0x1800237ee  mov     qword ptr [rdx], 0
0x1800237f5  lea     r8, [rbp+arg_10]; struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *
0x1800237f9  lea     rdx, ?RtlpDirectWin32IsolatedFilesystem@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@B; unsigned int
0x180023800  mov     [rbp+arg_10], 0
0x180023808  xor     r9d, r9d; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *
0x18002380b  call    ?CreateIsolatedFilesystemFromProvider@Rtl@FsProv@Isolation@Windows@@YAJKPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1234@PEAU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@@Z; Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(ulong,Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)
0x180023810  mov     r14d, eax
0x180023813  test    eax, eax
0x180023815  jns     loc_1800238A1
0x18002381b  mov     r10, [rbp+arg_10]
0x18002381f  test    r10, r10
0x180023822  jz      loc_180023A39
0x180023828  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18002382f  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180023836  mov     [rbp+var_28], rsi
0x18002383a  mov     [rbp+dwExceptionCode], r13d
0x18002383e  test    r10, r10
0x180023841  jz      short loc_18002386D
0x180023843  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18002384a  test    r11, r11
0x18002384d  jz      short loc_18002388C
0x18002384f  mov     rdx, r11
0x180023852  mov     rcx, r10
0x180023855  call    RtlIsTypeSafeHandleValid
0x18002385a  test    al, al
0x18002385c  jz      short loc_18002388C
0x18002385e  mov     ecx, [r11]
0x180023861  mov     rdx, r10
0x180023864  mov     rax, [r11+20h]
0x180023868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002386d  xor     ecx, ecx; dwExceptionCode
0x18002386f  test    ecx, ecx
0x180023871  jns     loc_180023A39
0x180023877  xor     r9d, r9d; lpArguments
0x18002387a  xor     r8d, r8d; nNumberOfArguments
0x18002387d  lea     edx, [r9+1]; dwExceptionFlags
0x180023881  call    cs:__imp_RaiseException
0x180023887  jmp     loc_180023A39
0x18002388c  mov     [rbp+var_20], 124h
0x180023893  lea     rcx, [rbp+var_28]
0x180023897  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18002389c  mov     ecx, [rbp+dwExceptionCode]
0x18002389f  jmp     short loc_18002386F
0x1800238a1  mov     edx, 1; struct Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *
0x1800238a6  lea     rcx, ?Facility_IsolationIsolatedFilesystem@Rtl@Isolation@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x1800238ad  call    ?RtlIsTracingEnabled@Rtl@Isolation@Windows@@YA_NPEAU_RTL_TRACING_FACILITY@123@K@Z; Windows::Isolation::Rtl::RtlIsTracingEnabled(Windows::Isolation::Rtl::_RTL_TRACING_FACILITY *,ulong)
0x1800238b2  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800238b9  test    al, al
0x1800238bb  jz      loc_1800239D2
0x1800238c1  mov     rbx, [rbp+arg_10]
0x1800238c5  lea     r8, [rbp+arg_10]
0x1800238c9  mov     rdx, rbx
0x1800238cc  mov     [rbp+arg_10], 0
0x1800238d4  xor     r9d, r9d
0x1800238d7  call    RtlCreateTracingFilesystem
0x1800238dc  mov     r14d, eax
0x1800238df  test    eax, eax
0x1800238e1  jns     loc_180023969
0x1800238e7  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800238ee  test    rbx, rbx
0x1800238f1  jz      short loc_180023957
0x1800238f3  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800238fa  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180023901  mov     [rbp+dwExceptionCode], r13d
0x180023905  mov     [rbp+var_28], rsi
0x180023909  test    r10, r10
0x18002390c  jz      short loc_180023930
0x18002390e  mov     rdx, r10
0x180023911  mov     rcx, rbx
0x180023914  call    RtlIsTypeSafeHandleValid
0x180023919  test    al, al
0x18002391b  jz      short loc_180023930
0x18002391d  mov     ecx, [r10]
0x180023920  mov     rdx, rbx
0x180023923  mov     rax, [r10+20h]
0x180023927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002392c  xor     ecx, ecx
0x18002392e  jmp     short loc_180023943
0x180023930  mov     [rbp+var_20], 124h
0x180023937  lea     rcx, [rbp+var_28]
0x18002393b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180023940  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x180023943  test    ecx, ecx
0x180023945  jns     short loc_180023957
0x180023947  xor     r9d, r9d; lpArguments
0x18002394a  xor     r8d, r8d; nNumberOfArguments
0x18002394d  lea     edx, [r9+1]; dwExceptionFlags
0x180023951  call    cs:__imp_RaiseException
0x180023957  mov     r10, [rbp+arg_10]
0x18002395b  test    r10, r10
0x18002395e  jz      loc_180023A39
0x180023964  jmp     loc_18002382F
0x180023969  test    rbx, rbx
0x18002396c  jz      short loc_1800239D2
0x18002396e  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180023975  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18002397c  mov     [rbp+dwExceptionCode], r13d
0x180023980  mov     [rbp+var_28], rsi
0x180023984  test    r10, r10
0x180023987  jz      short loc_1800239AB
0x180023989  mov     rdx, r10
0x18002398c  mov     rcx, rbx
0x18002398f  call    RtlIsTypeSafeHandleValid
0x180023994  test    al, al
0x180023996  jz      short loc_1800239AB
0x180023998  mov     ecx, [r10]
0x18002399b  mov     rdx, rbx
0x18002399e  mov     rax, [r10+20h]
0x1800239a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239a7  xor     ecx, ecx
0x1800239a9  jmp     short loc_1800239BE
0x1800239ab  mov     [rbp+var_20], 124h
0x1800239b2  lea     rcx, [rbp+var_28]
0x1800239b6  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800239bb  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x1800239be  test    ecx, ecx
0x1800239c0  jns     short loc_1800239D2
0x1800239c2  xor     r9d, r9d; lpArguments
0x1800239c5  xor     r8d, r8d; nNumberOfArguments
0x1800239c8  lea     edx, [r9+1]; dwExceptionFlags
0x1800239cc  call    cs:__imp_RaiseException
0x1800239d2  mov     r11, [r15]
0x1800239d5  xor     r14d, r14d
0x1800239d8  mov     rax, [rbp+arg_10]
0x1800239dc  mov     [r15], rax
0x1800239df  test    r11, r11
0x1800239e2  jz      short loc_180023A39
0x1800239e4  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800239eb  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800239f2  mov     [rbp+dwExceptionCode], r13d
0x1800239f6  mov     [rbp+var_28], rsi
0x1800239fa  test    r10, r10
0x1800239fd  jz      loc_18002388C
0x180023a03  mov     rdx, r10
0x180023a06  mov     rcx, r11
0x180023a09  call    RtlIsTypeSafeHandleValid
0x180023a0e  test    al, al
0x180023a10  jz      loc_18002388C
0x180023a16  mov     ecx, [r10]
0x180023a19  mov     rdx, r11
0x180023a1c  mov     rax, [r10+20h]
0x180023a20  jmp     loc_180023868
0x180023a25  lea     rcx, [rbp+var_28]
0x180023a29  mov     [rbp+var_20], 8FDh
0x180023a30  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180023a35  mov     r14d, [rbp+dwExceptionCode]
0x180023a39  mov     eax, r14d
0x180023a3c  add     rsp, 48h
0x180023a40  pop     r15
0x180023a42  pop     r14
0x180023a44  pop     r13
0x180023a46  pop     rsi
0x180023a47  pop     rbx
0x180023a48  pop     rbp
0x180023a49  retn
```
