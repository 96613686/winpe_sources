# IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::Initialize(Windows::Isolation::Rtl::_COMPONENT_STORE,Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR)

- ea: `0x1800a2090`
- end: `0x1800a235c`
- name: `?Initialize@CEnumSTORE_ASSEMBLY@Com@IsolationImplementation@@IEAAJU_COMPONENT_STORE@Rtl@Isolation@Windows@@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@567@@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a750`

## callees

- `0x180012b1c`
- `0x1800165fc`
- `0x180018acc`
- `0x18004f2dc`
- `0x1800a2090`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a214b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a21aa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a22dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2334`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a214b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a21aa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a22dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2334`

## string_xrefs

- `0x1800a20e8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a21e1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a20d2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassembly.cpp`
- `0x1800a2246`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassembly.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumSTORE_ASSEMBLY::Initialize(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  int v6; // r9d
  signed int v7; // edi
  __int64 v8; // r10
  unsigned int *v9; // r11
  int v10; // ecx
  __int64 v11; // r10
  unsigned int *v12; // r11
  int v13; // ecx
  __int64 v14; // r10
  int v15; // eax
  int v16; // r9d
  __int64 v17; // r10
  __int64 v18; // r11
  unsigned int *v19; // r10
  __int64 v20; // r11
  int v21; // ecx
  __int64 v22; // r10
  unsigned int *v23; // r11
  int v24; // ecx
  __int64 v26; // [rsp+20h] [rbp-28h] BYREF
  const char *v27; // [rsp+28h] [rbp-20h] BYREF
  int v28; // [rsp+30h] [rbp-18h]
  DWORD dwExceptionCode; // [rsp+38h] [rbp-10h]
  __int64 v30; // [rsp+98h] [rbp+50h] BYREF

  v26 = 0;
  v30 = 0;
  v5 = RtlDuplicateComponentStoreHandle(a2, &v26);
  v7 = v5;
  if ( v5 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassembly.cpp",
      (const char *)0x22,
      v5,
      v6);
LABEL_3:
    if ( v30 )
    {
      v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      dwExceptionCode = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v30) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v9 + 4))(*v9, v8);
        v10 = 0;
      }
      else
      {
        v28 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
        v10 = dwExceptionCode;
      }
      if ( v10 < 0 )
        RaiseException(v10, 1u, 0, 0);
      v30 = 0;
    }
    if ( v26 )
    {
      v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      dwExceptionCode = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v26) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v12 + 4))(*v12, v11);
        v13 = 0;
      }
      else
      {
        v28 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
        v13 = dwExceptionCode;
      }
      if ( v13 < 0 )
        RaiseException(v13, 1u, 0, 0);
    }
    return (unsigned int)v7;
  }
  v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
  dwExceptionCode = -1073741595;
  v30 = 0;
  if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
    && (unsigned __int8)RtlIsTypeSafeHandleValid(a3) )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(v14 + 24))(a3, &v30, 0);
    v7 = 0;
    if ( v15 < 0 )
      v7 = v15;
  }
  else
  {
    v28 = 256;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
    v7 = dwExceptionCode;
  }
  if ( v7 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassembly.cpp",
      (const char *)0x23,
      v7,
      v16);
    goto LABEL_3;
  }
  v17 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v26;
  v18 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = v30;
  v26 = v17;
  v30 = v18;
  if ( v18 )
  {
    dwExceptionCode = -1073741595;
    v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v18) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v19 + 4))(*v19, v20);
      v21 = 0;
    }
    else
    {
      v28 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
      v21 = dwExceptionCode;
    }
    if ( v21 < 0 )
      RaiseException(v21, 1u, 0, 0);
    v17 = v26;
    v30 = 0;
  }
  if ( v17 )
  {
    dwExceptionCode = -1073741595;
    v27 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v17) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v23 + 4))(*v23, v22);
      v24 = 0;
    }
    else
    {
      v28 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v27);
      v24 = dwExceptionCode;
    }
    if ( v24 < 0 )
      RaiseException(v24, 1u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a2090  push    rbp
0x1800a2092  push    rbx
0x1800a2093  push    rsi
0x1800a2094  push    rdi
0x1800a2095  push    r14
0x1800a2097  push    r15
0x1800a2099  mov     rbp, rsp
0x1800a209c  sub     rsp, 48h
0x1800a20a0  mov     rax, rdx
0x1800a20a3  mov     [rbp+var_28], 0
0x1800a20ab  mov     r15, rcx
0x1800a20ae  mov     [rbp+arg_18], 0
0x1800a20b6  mov     rcx, rax
0x1800a20b9  lea     rdx, [rbp+var_28]
0x1800a20bd  mov     rbx, r8
0x1800a20c0  call    RtlDuplicateComponentStoreHandle
0x1800a20c5  mov     edi, eax
0x1800a20c7  test    eax, eax
0x1800a20c9  jns     loc_1800A21DA
0x1800a20cf  mov     r8d, eax; int
0x1800a20d2  lea     rcx, aOnecoreComNetf_111; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a20d9  mov     edx, 22h ; '"'; char *
0x1800a20de  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a20e3  mov     esi, 0C00000E5h
0x1800a20e8  lea     r14, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a20ef  mov     r10, [rbp+arg_18]
0x1800a20f3  mov     r15d, 1
0x1800a20f9  mov     ebx, 124h
0x1800a20fe  test    r10, r10
0x1800a2101  jz      short loc_1800A2159
0x1800a2103  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentEnumerator@@VCComponentEnumeratorCD@@VCComponentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
0x1800a210a  mov     [rbp+var_20], r14
0x1800a210e  mov     [rbp+dwExceptionCode], esi
0x1800a2111  test    r11, r11
0x1800a2114  jz      loc_1800A21B5
0x1800a211a  mov     rdx, r11
0x1800a211d  mov     rcx, r10
0x1800a2120  call    RtlIsTypeSafeHandleValid
0x1800a2125  test    al, al
0x1800a2127  jz      loc_1800A21B5
0x1800a212d  mov     ecx, [r11]
0x1800a2130  mov     rdx, r10
0x1800a2133  mov     rax, [r11+20h]
0x1800a2137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a213c  xor     ecx, ecx; dwExceptionCode
0x1800a213e  test    ecx, ecx
0x1800a2140  jns     short loc_1800A2151
0x1800a2142  xor     r9d, r9d; lpArguments
0x1800a2145  xor     r8d, r8d; nNumberOfArguments
0x1800a2148  mov     edx, r15d; dwExceptionFlags
0x1800a214b  call    cs:__imp_RaiseException
0x1800a2151  mov     [rbp+arg_18], 0
0x1800a2159  mov     r10, [rbp+var_28]
0x1800a215d  test    r10, r10
0x1800a2160  jz      loc_1800A233C
0x1800a2166  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a216d  mov     [rbp+var_20], r14
0x1800a2171  mov     [rbp+dwExceptionCode], esi
0x1800a2174  test    r11, r11
0x1800a2177  jz      short loc_1800A21C9
0x1800a2179  mov     rdx, r11
0x1800a217c  mov     rcx, r10
0x1800a217f  call    RtlIsTypeSafeHandleValid
0x1800a2184  test    al, al
0x1800a2186  jz      short loc_1800A21C9
0x1800a2188  mov     ecx, [r11]
0x1800a218b  mov     rdx, r10
0x1800a218e  mov     rax, [r11+20h]
0x1800a2192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2197  xor     ecx, ecx; dwExceptionCode
0x1800a2199  test    ecx, ecx
0x1800a219b  jns     loc_1800A233C
0x1800a21a1  xor     r9d, r9d; lpArguments
0x1800a21a4  xor     r8d, r8d; nNumberOfArguments
0x1800a21a7  mov     edx, r15d; dwExceptionFlags
0x1800a21aa  call    cs:__imp_RaiseException
0x1800a21b0  jmp     loc_1800A233C
0x1800a21b5  mov     [rbp+var_18], ebx
0x1800a21b8  lea     rcx, [rbp+var_20]
0x1800a21bc  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a21c1  mov     ecx, [rbp+dwExceptionCode]
0x1800a21c4  jmp     loc_1800A213E
0x1800a21c9  mov     [rbp+var_18], ebx
0x1800a21cc  lea     rcx, [rbp+var_20]
0x1800a21d0  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a21d5  mov     ecx, [rbp+dwExceptionCode]
0x1800a21d8  jmp     short loc_1800A2199
0x1800a21da  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentEnumerator@@VCComponentEnumeratorCD@@VCComponentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
0x1800a21e1  lea     r14, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a21e8  mov     [rbp+var_20], r14
0x1800a21ec  mov     esi, 0C00000E5h
0x1800a21f1  mov     [rbp+dwExceptionCode], esi
0x1800a21f4  mov     [rbp+arg_18], 0
0x1800a21fc  test    r10, r10
0x1800a21ff  jz      short loc_1800A222C
0x1800a2201  mov     rdx, r10
0x1800a2204  mov     rcx, rbx
0x1800a2207  call    RtlIsTypeSafeHandleValid
0x1800a220c  test    al, al
0x1800a220e  jz      short loc_1800A222C
0x1800a2210  mov     rax, [r10+18h]
0x1800a2214  lea     rdx, [rbp+arg_18]
0x1800a2218  xor     r8d, r8d
0x1800a221b  mov     rcx, rbx
0x1800a221e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2223  xor     edi, edi
0x1800a2225  test    eax, eax
0x1800a2227  cmovs   edi, eax
0x1800a222a  jmp     short loc_1800A223F
0x1800a222c  mov     [rbp+var_18], 100h
0x1800a2233  lea     rcx, [rbp+var_20]
0x1800a2237  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a223c  mov     edi, [rbp+dwExceptionCode]
0x1800a223f  test    edi, edi
0x1800a2241  jns     short loc_1800A225C
0x1800a2243  mov     r8d, edi; int
0x1800a2246  lea     rcx, aOnecoreComNetf_111; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a224d  mov     edx, 23h ; '#'; char *
0x1800a2252  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a2257  jmp     loc_1800A20EF
0x1800a225c  mov     r10, [r15+18h]
0x1800a2260  mov     ebx, 124h
0x1800a2265  mov     rax, [rbp+var_28]
0x1800a2269  mov     [r15+18h], rax
0x1800a226d  mov     r11, [r15+10h]
0x1800a2271  mov     rax, [rbp+arg_18]
0x1800a2275  mov     [r15+10h], rax
0x1800a2279  mov     r15d, 1
0x1800a227f  mov     [rbp+var_28], r10
0x1800a2283  mov     [rbp+arg_18], r11
0x1800a2287  test    r11, r11
0x1800a228a  jz      short loc_1800A22EF
0x1800a228c  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentEnumerator@@VCComponentEnumeratorCD@@VCComponentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
0x1800a2293  mov     [rbp+dwExceptionCode], esi
0x1800a2296  mov     [rbp+var_20], r14
0x1800a229a  test    r10, r10
0x1800a229d  jz      short loc_1800A22C1
0x1800a229f  mov     rdx, r10
0x1800a22a2  mov     rcx, r11
0x1800a22a5  call    RtlIsTypeSafeHandleValid
0x1800a22aa  test    al, al
0x1800a22ac  jz      short loc_1800A22C1
0x1800a22ae  mov     ecx, [r10]
0x1800a22b1  mov     rdx, r11
0x1800a22b4  mov     rax, [r10+20h]
0x1800a22b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a22bd  xor     ecx, ecx
0x1800a22bf  jmp     short loc_1800A22D0
0x1800a22c1  mov     [rbp+var_18], ebx
0x1800a22c4  lea     rcx, [rbp+var_20]
0x1800a22c8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a22cd  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x1800a22d0  test    ecx, ecx
0x1800a22d2  jns     short loc_1800A22E3
0x1800a22d4  xor     r9d, r9d; lpArguments
0x1800a22d7  xor     r8d, r8d; nNumberOfArguments
0x1800a22da  mov     edx, r15d; dwExceptionFlags
0x1800a22dd  call    cs:__imp_RaiseException
0x1800a22e3  mov     r10, [rbp+var_28]
0x1800a22e7  mov     [rbp+arg_18], 0
0x1800a22ef  test    r10, r10
0x1800a22f2  jz      short loc_1800A233A
0x1800a22f4  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a22fb  mov     [rbp+dwExceptionCode], esi
0x1800a22fe  mov     [rbp+var_20], r14
0x1800a2302  test    r11, r11
0x1800a2305  jz      short loc_1800A234B
0x1800a2307  mov     rdx, r11
0x1800a230a  mov     rcx, r10
0x1800a230d  call    RtlIsTypeSafeHandleValid
0x1800a2312  test    al, al
0x1800a2314  jz      short loc_1800A234B
0x1800a2316  mov     ecx, [r11]
0x1800a2319  mov     rdx, r10
0x1800a231c  mov     rax, [r11+20h]
0x1800a2320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2325  xor     ecx, ecx; dwExceptionCode
0x1800a2327  test    ecx, ecx
0x1800a2329  jns     short loc_1800A233A
0x1800a232b  xor     r9d, r9d; lpArguments
0x1800a232e  xor     r8d, r8d; nNumberOfArguments
0x1800a2331  mov     edx, r15d; dwExceptionFlags
0x1800a2334  call    cs:__imp_RaiseException
0x1800a233a  xor     edi, edi
0x1800a233c  mov     eax, edi
0x1800a233e  add     rsp, 48h
0x1800a2342  pop     r15
0x1800a2344  pop     r14
0x1800a2346  pop     rdi
0x1800a2347  pop     rsi
0x1800a2348  pop     rbx
0x1800a2349  pop     rbp
0x1800a234a  retn
0x1800a234b  mov     [rbp+var_18], ebx
0x1800a234e  lea     rcx, [rbp+var_20]
0x1800a2352  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a2357  mov     ecx, [rbp+dwExceptionCode]
0x1800a235a  jmp     short loc_1800A2327
```
