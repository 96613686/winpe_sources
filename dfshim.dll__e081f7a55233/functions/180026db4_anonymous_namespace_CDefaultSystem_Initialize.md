# _anonymous_namespace_::CDefaultSystem::Initialize

- ea: `0x180026db4`
- end: `0x180027021`
- name: `_anonymous_namespace_::CDefaultSystem::Initialize`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026b50`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x18001defc`
- `0x1800237b8`
- `0x1800264c8`
- `0x180026db4`
- `0x18004101c`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026e68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026ff0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026e68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026ff0`

## string_xrefs

- `0x180026e19`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180026f2a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180026eb1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CDefaultSystem::Initialize(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v4; // rcx
  int v6; // eax
  int v7; // r15d
  bool v8; // sf
  __int64 v9; // r10
  unsigned int *v10; // r11
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r10
  __int64 v15; // r11
  unsigned int *v16; // r10
  __int64 v17; // r11
  int v18; // ecx
  __int64 v19; // r10
  unsigned int *v20; // r11
  int v21; // ecx
  const char *v23; // [rsp+20h] [rbp-20h] BYREF
  int v24; // [rsp+28h] [rbp-18h]
  DWORD dwExceptionCode; // [rsp+30h] [rbp-10h]
  __int64 v26; // [rsp+68h] [rbp+28h] BYREF
  __int64 v27; // [rsp+70h] [rbp+30h] BYREF

  v27 = 0;
  v4 = *a2;
  v26 = 0;
  if ( (*(_BYTE *)(v4 + 8) & 2) != 0 )
  {
    v6 = RtlDuplicateIsolatedFilesystemHandle(*(_QWORD *)(v4 + 24));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v8 = v7 < 0;
  }
  else
  {
    v7 = RtlCreateDirectIsolatedFilesystem((Windows::Isolation::FsProv::Rtl *)v4, &v27, a3);
    v8 = v7 < 0;
  }
  if ( v8 )
    goto LABEL_6;
  v12 = *a2;
  if ( (*(_BYTE *)(*a2 + 8) & 1) != 0 )
  {
    v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
    dwExceptionCode = -1073741595;
    if ( v26 )
    {
      v24 = 142;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v23,
        &v23);
      v7 = dwExceptionCode;
    }
    else
    {
      v13 = RtlDuplicateIsolatedRegistryHandle(*(_QWORD *)(v12 + 16), &v26);
      v7 = 0;
      if ( v13 < 0 )
        v7 = v13;
    }
    if ( v7 < 0 )
      goto LABEL_6;
  }
  else
  {
    v7 = RtlCreateDirectIsolatedRegistry(v12, &v26);
    if ( v7 < 0 )
    {
LABEL_6:
      if ( v26 )
      {
        v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        dwExceptionCode = -1073741595;
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v26) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v10 + 4))(*v10, v9);
          v11 = 0;
        }
        else
        {
          v24 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v23);
          v11 = dwExceptionCode;
        }
        if ( v11 < 0 )
          RaiseException(v11, 1u, 0, 0);
        v26 = 0;
      }
      goto LABEL_31;
    }
  }
  v14 = *(_QWORD *)(a1 + 80);
  v7 = 0;
  *(_QWORD *)(a1 + 80) = v27;
  v15 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = v26;
  v27 = v14;
  v26 = v15;
  if ( !v15 )
    goto LABEL_32;
  dwExceptionCode = -1073741595;
  v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
  if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
    && (unsigned __int8)RtlIsTypeSafeHandleValid(v15) )
  {
    (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v17);
    v18 = 0;
  }
  else
  {
    v24 = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v23);
    v18 = dwExceptionCode;
  }
  if ( v18 < 0 )
    RaiseException(v18, 1u, 0, 0);
  v26 = 0;
LABEL_31:
  v14 = v27;
LABEL_32:
  if ( v14 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    dwExceptionCode = -1073741595;
    v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v14) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v20 + 4))(*v20, v19);
      v21 = 0;
    }
    else
    {
      v24 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v23);
      v21 = dwExceptionCode;
    }
    if ( v21 < 0 )
      RaiseException(v21, 1u, 0, 0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026db4  mov     [rsp-18h+arg_0], rbx
0x180026db9  mov     [rsp-18h+arg_18], rsi
0x180026dbe  push    rbp
0x180026dbf  push    rdi
0x180026dc0  push    r15
0x180026dc2  mov     rbp, rsp
0x180026dc5  sub     rsp, 40h
0x180026dc9  mov     rsi, rcx
0x180026dcc  mov     [rbp+arg_10], 0
0x180026dd4  mov     rcx, [rdx]
0x180026dd7  mov     rbx, rdx
0x180026dda  mov     [rbp+arg_8], 0
0x180026de2  lea     rdx, [rbp+arg_10]
0x180026de6  test    byte ptr [rcx+8], 2
0x180026dea  jz      loc_180026E90
0x180026df0  mov     rcx, [rcx+18h]
0x180026df4  call    RtlDuplicateIsolatedFilesystemHandle
0x180026df9  xor     r15d, r15d
0x180026dfc  test    eax, eax
0x180026dfe  cmovs   r15d, eax
0x180026e02  test    r15d, r15d
0x180026e05  mov     edi, 0C00000E5h
0x180026e0a  jns     loc_180026E9F
0x180026e10  mov     ebx, 1
0x180026e15  mov     r10, [rbp+arg_8]
0x180026e19  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180026e20  test    r10, r10
0x180026e23  jz      loc_180026F9C
0x180026e29  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x180026e30  mov     [rbp+var_20], rsi
0x180026e34  mov     [rbp+dwExceptionCode], edi
0x180026e37  test    r11, r11
0x180026e3a  jz      short loc_180026E7B
0x180026e3c  mov     rdx, r11
0x180026e3f  mov     rcx, r10
0x180026e42  call    RtlIsTypeSafeHandleValid
0x180026e47  test    al, al
0x180026e49  jz      short loc_180026E7B
0x180026e4b  mov     ecx, [r11]
0x180026e4e  mov     rdx, r10
0x180026e51  mov     rax, [r11+20h]
0x180026e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e5a  xor     ecx, ecx; dwExceptionCode
0x180026e5c  test    ecx, ecx
0x180026e5e  jns     short loc_180026E6E
0x180026e60  xor     r9d, r9d; lpArguments
0x180026e63  xor     r8d, r8d; nNumberOfArguments
0x180026e66  mov     edx, ebx; dwExceptionFlags
0x180026e68  call    cs:__imp_RaiseException
0x180026e6e  mov     [rbp+arg_8], 0
0x180026e76  jmp     loc_180026F9C
0x180026e7b  mov     [rbp+var_18], 124h
0x180026e82  lea     rcx, [rbp+var_20]
0x180026e86  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180026e8b  mov     ecx, [rbp+dwExceptionCode]
0x180026e8e  jmp     short loc_180026E5C
0x180026e90  call    RtlCreateDirectIsolatedFilesystem
0x180026e95  mov     r15d, eax
0x180026e98  test    eax, eax
0x180026e9a  jmp     loc_180026E05
0x180026e9f  mov     rcx, [rbx]
0x180026ea2  mov     ebx, 1
0x180026ea7  test    [rcx+8], bl
0x180026eaa  jz      short loc_180026EFB
0x180026eac  cmp     [rbp+arg_8], 0
0x180026eb1  lea     rax, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180026eb8  mov     [rbp+var_20], rax
0x180026ebc  mov     [rbp+dwExceptionCode], edi
0x180026ebf  jz      short loc_180026EDB
0x180026ec1  mov     [rbp+var_18], 8Eh
0x180026ec8  lea     rdx, [rbp+var_20]
0x180026ecc  lea     rcx, [rbp+var_20]
0x180026ed0  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180026ed5  mov     r15d, [rbp+dwExceptionCode]
0x180026ed9  jmp     short loc_180026EF1
0x180026edb  mov     rcx, [rcx+10h]
0x180026edf  lea     rdx, [rbp+arg_8]
0x180026ee3  call    RtlDuplicateIsolatedRegistryHandle
0x180026ee8  xor     r15d, r15d
0x180026eeb  test    eax, eax
0x180026eed  cmovs   r15d, eax
0x180026ef1  test    r15d, r15d
0x180026ef4  jns     short loc_180026F0F
0x180026ef6  jmp     loc_180026E15
0x180026efb  lea     rdx, [rbp+arg_8]
0x180026eff  call    RtlCreateDirectIsolatedRegistry
0x180026f04  mov     r15d, eax
0x180026f07  test    eax, eax
0x180026f09  js      loc_180026E15
0x180026f0f  mov     r10, [rsi+50h]
0x180026f13  xor     r15d, r15d
0x180026f16  mov     rax, [rbp+arg_10]
0x180026f1a  mov     [rsi+50h], rax
0x180026f1e  mov     r11, [rsi+58h]
0x180026f22  mov     rax, [rbp+arg_8]
0x180026f26  mov     [rsi+58h], rax
0x180026f2a  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180026f31  mov     [rbp+arg_10], r10
0x180026f35  mov     [rbp+arg_8], r11
0x180026f39  test    r11, r11
0x180026f3c  jz      short loc_180026FA0
0x180026f3e  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x180026f45  mov     [rbp+dwExceptionCode], edi
0x180026f48  mov     [rbp+var_20], rsi
0x180026f4c  test    r10, r10
0x180026f4f  jz      short loc_180026F73
0x180026f51  mov     rdx, r10
0x180026f54  mov     rcx, r11
0x180026f57  call    RtlIsTypeSafeHandleValid
0x180026f5c  test    al, al
0x180026f5e  jz      short loc_180026F73
0x180026f60  mov     ecx, [r10]
0x180026f63  mov     rdx, r11
0x180026f66  mov     rax, [r10+20h]
0x180026f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f6f  xor     ecx, ecx
0x180026f71  jmp     short loc_180026F86
0x180026f73  mov     [rbp+var_18], 124h
0x180026f7a  lea     rcx, [rbp+var_20]
0x180026f7e  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180026f83  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x180026f86  test    ecx, ecx
0x180026f88  jns     short loc_180026F98
0x180026f8a  xor     r9d, r9d; lpArguments
0x180026f8d  xor     r8d, r8d; nNumberOfArguments
0x180026f90  mov     edx, ebx; dwExceptionFlags
0x180026f92  call    cs:__imp_RaiseException
0x180026f98  mov     [rbp+arg_8], r15
0x180026f9c  mov     r10, [rbp+arg_10]
0x180026fa0  test    r10, r10
0x180026fa3  jz      short loc_180026FF6
0x180026fa5  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, rbx; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180026fac  mov     [rbp+dwExceptionCode], edi
0x180026faf  mov     [rbp+var_20], rsi
0x180026fb3  test    r10, r10
0x180026fb6  jz      short loc_180026FE2
0x180026fb8  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180026fbf  test    r11, r11
0x180026fc2  jz      short loc_18002700C
0x180026fc4  mov     rdx, r11
0x180026fc7  mov     rcx, r10
0x180026fca  call    RtlIsTypeSafeHandleValid
0x180026fcf  test    al, al
0x180026fd1  jz      short loc_18002700C
0x180026fd3  mov     ecx, [r11]
0x180026fd6  mov     rdx, r10
0x180026fd9  mov     rax, [r11+20h]
0x180026fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fe2  xor     ecx, ecx; dwExceptionCode
0x180026fe4  test    ecx, ecx
0x180026fe6  jns     short loc_180026FF6
0x180026fe8  xor     r9d, r9d; lpArguments
0x180026feb  xor     r8d, r8d; nNumberOfArguments
0x180026fee  mov     edx, ebx; dwExceptionFlags
0x180026ff0  call    cs:__imp_RaiseException
0x180026ff6  mov     rbx, [rsp+40h+arg_0]
0x180026ffb  mov     eax, r15d
0x180026ffe  mov     rsi, [rsp+40h+arg_18]
0x180027003  add     rsp, 40h
0x180027007  pop     r15
0x180027009  pop     rdi
0x18002700a  pop     rbp
0x18002700b  retn
0x18002700c  mov     [rbp+var_18], 124h
0x180027013  lea     rcx, [rbp+var_20]
0x180027017  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18002701c  mov     ecx, [rbp+dwExceptionCode]
0x18002701f  jmp     short loc_180026FE4
```
