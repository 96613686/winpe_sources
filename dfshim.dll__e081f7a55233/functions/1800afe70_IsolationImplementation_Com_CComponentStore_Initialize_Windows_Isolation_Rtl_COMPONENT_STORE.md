# IsolationImplementation::Com::CComponentStore::Initialize(Windows::Isolation::Rtl::_COMPONENT_STORE)

- ea: `0x1800afe70`
- end: `0x1800b0070`
- name: `?Initialize@CComponentStore@Com@IsolationImplementation@@IEAAJU_COMPONENT_STORE@Rtl@Isolation@Windows@@@Z`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a9a44`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800165fc`
- `0x1800187f0`
- `0x180018940`
- `0x1800237b8`
- `0x18004f2dc`
- `0x1800afe70`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afea5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800affab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afea5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800affab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aff3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b005d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aff3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b005d`

## string_xrefs

- `0x1800afee9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800b0000`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800aff67`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800afeae`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800affb4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::Initialize(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int v6; // edx
  unsigned int v7; // eax
  __int64 v8; // r10
  unsigned int v9; // ebx
  __int64 v10; // r10
  unsigned int *v11; // r11
  int v12; // ecx
  bool v13; // zf
  signed int v14; // ebx
  int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // r10
  unsigned int *v20; // r11
  int v21; // ecx
  const char *v23; // [rsp+20h] [rbp-28h] BYREF
  int v24; // [rsp+28h] [rbp-20h]
  DWORD dwExceptionCode; // [rsp+30h] [rbp-18h]
  __int64 v26; // [rsp+80h] [rbp+38h] BYREF

  v26 = 0;
  v4 = RtlCreateDirectIsolatedFilesystem(a1, &v26);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v13 = *(_QWORD *)(a1 + 16) == 0;
    dwExceptionCode = -1073741595;
    v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
    if ( v13 )
    {
      v15 = RtlDuplicateComponentStoreHandle(a2, a1 + 16);
      v14 = 0;
      if ( v15 < 0 )
        v14 = v15;
    }
    else
    {
      v24 = 142;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v23,
        &v23);
      v14 = dwExceptionCode;
    }
    if ( v14 >= 0 )
    {
      v18 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v26;
      if ( v18 )
      {
        ++g_nRtlCloseIsolatedFilesystemHandle;
        dwExceptionCode = -1073741595;
        v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v18) )
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
      return 0;
    }
    else
    {
      if ( v14 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x101,
        v14,
        (unsigned int)v23);
      v17 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v14, v16);
      v8 = v26;
      v9 = v17;
      if ( v26 )
      {
LABEL_5:
        ++g_nRtlCloseIsolatedFilesystemHandle;
        v23 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        dwExceptionCode = -1073741595;
        if ( v8 )
        {
          if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            || !(unsigned __int8)RtlIsTypeSafeHandleValid(v8) )
          {
            v24 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v23);
            v12 = dwExceptionCode;
LABEL_10:
            if ( v12 < 0 )
              RaiseException(v12, 1u, 0, 0);
            return v9;
          }
          (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
        }
        v12 = 0;
        goto LABEL_10;
      }
    }
  }
  else
  {
    if ( v4 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0xFF,
      v5,
      (unsigned int)v23);
    v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v5, v6);
    v8 = v26;
    v9 = v7;
    if ( v26 )
      goto LABEL_5;
  }
  return v9;
}

```

## disassembly

```asm
0x1800afe70  push    rbp
0x1800afe72  push    rbx
0x1800afe73  push    rsi
0x1800afe74  push    rdi
0x1800afe75  mov     rbp, rsp
0x1800afe78  sub     rsp, 48h
0x1800afe7c  mov     rbx, rdx
0x1800afe7f  mov     [rbp+arg_10], 0
0x1800afe87  lea     rdx, [rbp+arg_10]
0x1800afe8b  mov     rsi, rcx
0x1800afe8e  call    RtlCreateDirectIsolatedFilesystem
0x1800afe93  mov     edi, eax
0x1800afe95  test    eax, eax
0x1800afe97  jns     loc_1800AFF5A
0x1800afe9d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800afea3  jnz     short loc_1800AFEAB
0x1800afea5  call    cs:__imp_DebugBreak
0x1800afeab  mov     r9d, edi; int
0x1800afeae  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800afeb5  mov     r8d, 0FFh; char *
0x1800afebb  lea     rcx, aStatusPropagat; "Status propagated"
0x1800afec2  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800afec7  mov     ecx, edi; this
0x1800afec9  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800afece  mov     r10, [rbp+arg_10]
0x1800afed2  mov     ebx, eax
0x1800afed4  test    r10, r10
0x1800afed7  jz      loc_1800B0065
0x1800afedd  mov     edi, 0C00000E5h
0x1800afee2  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800afee9  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800afef0  mov     [rbp+var_28], rcx
0x1800afef4  mov     [rbp+dwExceptionCode], edi
0x1800afef7  test    r10, r10
0x1800afefa  jz      short loc_1800AFF26
0x1800afefc  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800aff03  test    r11, r11
0x1800aff06  jz      short loc_1800AFF45
0x1800aff08  mov     rdx, r11
0x1800aff0b  mov     rcx, r10
0x1800aff0e  call    RtlIsTypeSafeHandleValid
0x1800aff13  test    al, al
0x1800aff15  jz      short loc_1800AFF45
0x1800aff17  mov     ecx, [r11]
0x1800aff1a  mov     rdx, r10
0x1800aff1d  mov     rax, [r11+20h]
0x1800aff21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff26  xor     ecx, ecx; dwExceptionCode
0x1800aff28  test    ecx, ecx
0x1800aff2a  jns     loc_1800B0065
0x1800aff30  xor     r9d, r9d; lpArguments
0x1800aff33  xor     r8d, r8d; nNumberOfArguments
0x1800aff36  lea     edx, [r9+1]; dwExceptionFlags
0x1800aff3a  call    cs:__imp_RaiseException
0x1800aff40  jmp     loc_1800B0065
0x1800aff45  mov     [rbp+var_20], 124h
0x1800aff4c  lea     rcx, [rbp+var_28]
0x1800aff50  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800aff55  mov     ecx, [rbp+dwExceptionCode]
0x1800aff58  jmp     short loc_1800AFF28
0x1800aff5a  lea     rdx, [rsi+10h]
0x1800aff5e  mov     edi, 0C00000E5h
0x1800aff63  cmp     qword ptr [rdx], 0
0x1800aff67  lea     rax, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aff6e  mov     [rbp+dwExceptionCode], edi
0x1800aff71  mov     [rbp+var_28], rax
0x1800aff75  jz      short loc_1800AFF90
0x1800aff77  mov     [rbp+var_20], 8Eh
0x1800aff7e  lea     rdx, [rbp+var_28]
0x1800aff82  lea     rcx, [rbp+var_28]
0x1800aff86  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800aff8b  mov     ebx, [rbp+dwExceptionCode]
0x1800aff8e  jmp     short loc_1800AFF9F
0x1800aff90  mov     rcx, rbx
0x1800aff93  call    RtlDuplicateComponentStoreHandle
0x1800aff98  xor     ebx, ebx
0x1800aff9a  test    eax, eax
0x1800aff9c  cmovs   ebx, eax
0x1800aff9f  test    ebx, ebx
0x1800affa1  jns     short loc_1800AFFE8
0x1800affa3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800affa9  jnz     short loc_1800AFFB1
0x1800affab  call    cs:__imp_DebugBreak
0x1800affb1  mov     r9d, ebx; int
0x1800affb4  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800affbb  mov     r8d, 101h; char *
0x1800affc1  lea     rcx, aStatusPropagat; "Status propagated"
0x1800affc8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800affcd  mov     ecx, ebx; this
0x1800affcf  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800affd4  mov     r10, [rbp+arg_10]
0x1800affd8  mov     ebx, eax
0x1800affda  test    r10, r10
0x1800affdd  jz      loc_1800B0065
0x1800affe3  jmp     loc_1800AFEE2
0x1800affe8  mov     r10, [rsi+18h]
0x1800affec  mov     rax, [rbp+arg_10]
0x1800afff0  mov     [rsi+18h], rax
0x1800afff4  test    r10, r10
0x1800afff7  jz      short loc_1800B0063
0x1800afff9  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800b0000  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800b0007  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800b000e  mov     [rbp+dwExceptionCode], edi
0x1800b0011  mov     [rbp+var_28], rcx
0x1800b0015  test    r11, r11
0x1800b0018  jz      short loc_1800B003C
0x1800b001a  mov     rdx, r11
0x1800b001d  mov     rcx, r10
0x1800b0020  call    RtlIsTypeSafeHandleValid
0x1800b0025  test    al, al
0x1800b0027  jz      short loc_1800B003C
0x1800b0029  mov     ecx, [r11]
0x1800b002c  mov     rdx, r10
0x1800b002f  mov     rax, [r11+20h]
0x1800b0033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0038  xor     ecx, ecx
0x1800b003a  jmp     short loc_1800B004F
0x1800b003c  mov     [rbp+var_20], 124h
0x1800b0043  lea     rcx, [rbp+var_28]
0x1800b0047  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800b004c  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x1800b004f  test    ecx, ecx
0x1800b0051  jns     short loc_1800B0063
0x1800b0053  xor     r9d, r9d; lpArguments
0x1800b0056  xor     r8d, r8d; nNumberOfArguments
0x1800b0059  lea     edx, [r9+1]; dwExceptionFlags
0x1800b005d  call    cs:__imp_RaiseException
0x1800b0063  xor     ebx, ebx
0x1800b0065  mov     eax, ebx
0x1800b0067  add     rsp, 48h
0x1800b006b  pop     rdi
0x1800b006c  pop     rsi
0x1800b006d  pop     rbx
0x1800b006e  pop     rbp
0x1800b006f  retn
```
