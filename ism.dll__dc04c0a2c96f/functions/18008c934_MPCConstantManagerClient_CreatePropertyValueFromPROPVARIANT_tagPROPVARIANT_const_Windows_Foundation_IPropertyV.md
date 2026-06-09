# MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(tagPROPVARIANT const &,Windows::Foundation::IPropertyValue * *)

- ea: `0x18008c934`
- end: `0x18008cc92`
- name: `?CreatePropertyValueFromPROPVARIANT@MPCConstantManagerClient@@CAJAEBUtagPROPVARIANT@@PEAPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, struct Windows::Foundation::IPropertyValue **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008b794`
- `0x18008bbe0`

## callees

- `0x180069f90`
- `0x18006e260`
- `0x18008bb8c`
- `0x18008c934`
- `0x18008dcac`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008c996`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008c996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008ca31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008ca31`
- `PROPSYS!PropVariantToStringAlloc` at `0x18008c9f8`
- `PROPSYS!PropVariantToStringAlloc` at `0x18008c9f8`
- `PROPSYS!PropVariantToUInt64` at `0x18008cab7`
- `PROPSYS!PropVariantToUInt64` at `0x18008cab7`
- `PROPSYS!PropVariantToDouble` at `0x18008cbcf`
- `PROPSYS!PropVariantToDouble` at `0x18008cbcf`
- `PROPSYS!PropVariantToBoolean` at `0x18008cb3e`
- `PROPSYS!PropVariantToBoolean` at `0x18008cb3e`

## string_xrefs

- `0x18008c9a7`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008ca09`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008ca7d`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cac8`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cb21`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cb4f`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cbae`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cbe0`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008cc3a`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(
        PROPVARIANT *propvarIn,
        struct Windows::Foundation::IPropertyValue **a2)
{
  int ActivationFactory; // eax
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rdi
  int v8; // eax
  HRESULT v10; // eax
  __int64 (__fastcall *v11)(__int64, ULONGLONG, __int64 *); // rdi
  int v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rdi
  int v16; // eax
  HRESULT v17; // eax
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rdi
  int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-60h] BYREF
  __int64 v22; // [rsp+28h] [rbp-58h] BYREF
  BOOL pfRet; // [rsp+30h] [rbp-50h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  ULONGLONG pullRet; // [rsp+48h] [rbp-38h] BYREF
  DOUBLE pdblRet; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21 = 0;
  v22 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.PropertyValue",
    0x21u,
    0x20u);
  ActivationFactory = RoGetActivationFactory(v29, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v22);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v21);
  switch ( *(_WORD *)propvarIn )
  {
    case 4:
    case 5:
      pdblRet = 0.0;
      v17 = PropVariantToDouble(propvarIn, &pdblRet);
      if ( v17 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v17,
          v21);
      v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 112LL);
      v21 = 0;
      v20 = v19(v22, v18, &v21);
      if ( v20 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v20,
          v21);
      goto LABEL_27;
    case 0xB:
      pfRet = 0;
      v13 = PropVariantToBoolean(propvarIn, &pfRet);
      if ( v13 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x164,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v13,
          v21);
      v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 136LL);
      v21 = 0;
      LOBYTE(v14) = pfRet;
      v16 = v15(v22, v14, &v21);
      if ( v16 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x165,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v16,
          v21);
      goto LABEL_27;
    case 0x15:
      pullRet = 0;
      v10 = PropVariantToUInt64(propvarIn, &pullRet);
      if ( v10 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v10,
          v21);
      v11 = *(__int64 (__fastcall **)(__int64, ULONGLONG, __int64 *))(*(_QWORD *)v22 + 104LL);
      v21 = 0;
      v12 = v11(v22, pullRet, &v21);
      if ( v12 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v12,
          v21);
LABEL_27:
      wil::com_ptr_t<IInspectable,wil::err_exception_policy>::copy_to<Windows::Foundation::IPropertyValue>(&v21, a2);
      wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v22);
      wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v21);
      return 0;
    case 0x1F:
      ppszOut = 0;
      string = 0;
      v5 = PropVariantToStringAlloc(propvarIn, &ppszOut);
      if ( v5 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v5,
          v21);
      v6 = -1;
      do
        ++v6;
      while ( ppszOut[v6] );
      WindowsCreateString(ppszOut, v6, &string);
      v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v22 + 144LL);
      v21 = 0;
      v8 = v7(v22, string, &v21);
      if ( v8 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
          (const char *)(unsigned int)v8,
          v21);
      break;
  }
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v21);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18008c934  mov     [rsp-18h+arg_10], rbx
0x18008c939  mov     [rsp-18h+arg_18], rsi
0x18008c93e  push    rbp
0x18008c93f  push    rdi
0x18008c940  push    r14
0x18008c942  mov     rbp, rsp
0x18008c945  sub     rsp, 80h
0x18008c94c  mov     rax, cs:__security_cookie
0x18008c953  xor     rax, rsp
0x18008c956  mov     [rbp+var_8], rax
0x18008c95a  mov     rsi, rdx
0x18008c95d  mov     rbx, rcx
0x18008c960  xor     r14d, r14d
0x18008c963  mov     [rbp+var_60], r14
0x18008c967  mov     [rbp+var_58], r14
0x18008c96b  mov     [rbp+var_10], r14
0x18008c96f  lea     r9d, [r14+20h]; unsigned int
0x18008c973  lea     r8d, [r14+21h]; unsigned int
0x18008c977  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18008c97e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18008c982  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008c987  lea     r8, [rbp+var_58]
0x18008c98b  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18008c992  mov     rcx, [rbp+var_10]
0x18008c996  call    cs:__imp_RoGetActivationFactory
0x18008c99c  mov     rcx, [rbp+18h]; this
0x18008c9a0  test    eax, eax
0x18008c9a2  jns     short loc_18008C9B9
0x18008c9a4  mov     r9d, eax; char *
0x18008c9a7  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008c9ae  mov     edx, 15Eh; void *
0x18008c9b3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008c9b9  movzx   edx, word ptr [rbx]
0x18008c9bc  sub     edx, 4
0x18008c9bf  jz      loc_18008CBC0
0x18008c9c5  sub     edx, 1
0x18008c9c8  jz      loc_18008CBC0
0x18008c9ce  sub     edx, 6
0x18008c9d1  jz      loc_18008CB33
0x18008c9d7  sub     edx, 0Ah
0x18008c9da  jz      loc_18008CAAC
0x18008c9e0  cmp     edx, 0Ah
0x18008c9e3  jnz     loc_18008CA8F
0x18008c9e9  mov     [rbp+ppszOut], r14
0x18008c9ed  mov     [rbp+string], r14
0x18008c9f1  lea     rdx, [rbp+ppszOut]; ppszOut
0x18008c9f5  mov     rcx, rbx; propvar
0x18008c9f8  call    cs:__imp_PropVariantToStringAlloc
0x18008c9fe  mov     rcx, [rbp+18h]; this
0x18008ca02  test    eax, eax
0x18008ca04  jns     short loc_18008CA1B
0x18008ca06  mov     r9d, eax; char *
0x18008ca09  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008ca10  mov     edx, 175h; void *
0x18008ca15  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008ca1b  mov     rcx, [rbp+ppszOut]; sourceString
0x18008ca1f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008ca23  inc     rdx; length
0x18008ca26  cmp     [rcx+rdx*2], r14w
0x18008ca2b  jnz     short loc_18008CA23
0x18008ca2d  lea     r8, [rbp+string]; string
0x18008ca31  call    cs:__imp_WindowsCreateString
0x18008ca37  mov     rbx, [rbp+var_58]
0x18008ca3b  mov     rax, [rbx]
0x18008ca3e  mov     rdi, [rax+90h]
0x18008ca45  mov     rcx, [rbp+var_60]
0x18008ca49  mov     [rbp+var_60], r14
0x18008ca4d  test    rcx, rcx
0x18008ca50  jz      short loc_18008CA5F
0x18008ca52  mov     rdx, [rcx]
0x18008ca55  mov     rax, [rdx+10h]
0x18008ca59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ca5e  nop
0x18008ca5f  lea     r8, [rbp+var_60]
0x18008ca63  mov     rdx, [rbp+string]
0x18008ca67  mov     rcx, rbx
0x18008ca6a  mov     rax, rdi
0x18008ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ca72  mov     rcx, [rbp+18h]; this
0x18008ca76  test    eax, eax
0x18008ca78  jns     short loc_18008CA8F
0x18008ca7a  mov     r9d, eax; char *
0x18008ca7d  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008ca84  mov     edx, 177h; void *
0x18008ca89  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008ca8f  lea     rcx, [rbp+var_58]
0x18008ca93  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008ca98  nop
0x18008ca99  lea     rcx, [rbp+var_60]
0x18008ca9d  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008caa2  mov     eax, 80070057h
0x18008caa7  jmp     loc_18008CC6E
0x18008caac  mov     [rbp+pullRet], r14
0x18008cab0  lea     rdx, [rbp+pullRet]; pullRet
0x18008cab4  mov     rcx, rbx; propvarIn
0x18008cab7  call    cs:__imp_PropVariantToUInt64
0x18008cabd  mov     rcx, [rbp+18h]; this
0x18008cac1  test    eax, eax
0x18008cac3  jns     short loc_18008CADA
0x18008cac5  mov     r9d, eax; char *
0x18008cac8  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cacf  mov     edx, 169h; void *
0x18008cad4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cada  mov     rbx, [rbp+var_58]
0x18008cade  mov     rax, [rbx]
0x18008cae1  mov     rdi, [rax+68h]
0x18008cae5  mov     rcx, [rbp+var_60]
0x18008cae9  mov     [rbp+var_60], r14
0x18008caed  test    rcx, rcx
0x18008caf0  jz      short loc_18008CAFF
0x18008caf2  mov     rdx, [rcx]
0x18008caf5  mov     rax, [rdx+10h]
0x18008caf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cafe  nop
0x18008caff  lea     r8, [rbp+var_60]
0x18008cb03  mov     rdx, [rbp+pullRet]
0x18008cb07  mov     rcx, rbx
0x18008cb0a  mov     rax, rdi
0x18008cb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb12  mov     rcx, [rbp+18h]; this
0x18008cb16  test    eax, eax
0x18008cb18  jns     loc_18008CC4C
0x18008cb1e  mov     r9d, eax; char *
0x18008cb21  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cb28  mov     edx, 16Ah; void *
0x18008cb2d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cb33  mov     [rbp+pfRet], r14d
0x18008cb37  lea     rdx, [rbp+pfRet]; pfRet
0x18008cb3b  mov     rcx, rbx; propvarIn
0x18008cb3e  call    cs:__imp_PropVariantToBoolean
0x18008cb44  mov     rcx, [rbp+18h]; this
0x18008cb48  test    eax, eax
0x18008cb4a  jns     short loc_18008CB61
0x18008cb4c  mov     r9d, eax; char *
0x18008cb4f  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cb56  mov     edx, 164h; void *
0x18008cb5b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cb61  mov     rbx, [rbp+var_58]
0x18008cb65  mov     rax, [rbx]
0x18008cb68  mov     rdi, [rax+88h]
0x18008cb6f  mov     rcx, [rbp+var_60]
0x18008cb73  mov     [rbp+var_60], r14
0x18008cb77  test    rcx, rcx
0x18008cb7a  jz      short loc_18008CB89
0x18008cb7c  mov     rax, [rcx]
0x18008cb7f  mov     rax, [rax+10h]
0x18008cb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb88  nop
0x18008cb89  cmp     [rbp+pfRet], r14d
0x18008cb8d  setnz   dl
0x18008cb90  lea     r8, [rbp+var_60]
0x18008cb94  mov     rcx, rbx
0x18008cb97  mov     rax, rdi
0x18008cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb9f  mov     rcx, [rbp+18h]; this
0x18008cba3  test    eax, eax
0x18008cba5  jns     loc_18008CC4C
0x18008cbab  mov     r9d, eax; char *
0x18008cbae  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cbb5  mov     edx, 165h; void *
0x18008cbba  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cbc0  xorps   xmm0, xmm0
0x18008cbc3  movsd   [rbp+pdblRet], xmm0
0x18008cbc8  lea     rdx, [rbp+pdblRet]; pdblRet
0x18008cbcc  mov     rcx, rbx; propvarIn
0x18008cbcf  call    cs:__imp_PropVariantToDouble
0x18008cbd5  mov     rcx, [rbp+18h]; this
0x18008cbd9  test    eax, eax
0x18008cbdb  jns     short loc_18008CBF2
0x18008cbdd  mov     r9d, eax; char *
0x18008cbe0  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cbe7  mov     edx, 16Fh; void *
0x18008cbec  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cbf2  mov     rbx, [rbp+var_58]
0x18008cbf6  mov     rax, [rbx]
0x18008cbf9  mov     rdi, [rax+70h]
0x18008cbfd  mov     rcx, [rbp+var_60]
0x18008cc01  mov     [rbp+var_60], r14
0x18008cc05  test    rcx, rcx
0x18008cc08  jz      short loc_18008CC17
0x18008cc0a  mov     rdx, [rcx]
0x18008cc0d  mov     rax, [rdx+10h]
0x18008cc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc16  nop
0x18008cc17  movsd   xmm1, [rbp+pdblRet]
0x18008cc1c  cvtpd2ps xmm1, xmm1
0x18008cc20  lea     r8, [rbp+var_60]
0x18008cc24  mov     rcx, rbx
0x18008cc27  mov     rax, rdi
0x18008cc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc2f  mov     rcx, [rbp+18h]; this
0x18008cc33  test    eax, eax
0x18008cc35  jns     short loc_18008CC4C
0x18008cc37  mov     r9d, eax; char *
0x18008cc3a  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008cc41  mov     edx, 170h; void *
0x18008cc46  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008cc4c  mov     rdx, rsi
0x18008cc4f  lea     rcx, [rbp+var_60]
0x18008cc53  call    ??$copy_to@UIPropertyValue@Foundation@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIPropertyValue@Foundation@Windows@@@Z; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::copy_to<Windows::Foundation::IPropertyValue>(Windows::Foundation::IPropertyValue * *)
0x18008cc58  nop
0x18008cc59  lea     rcx, [rbp+var_58]
0x18008cc5d  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008cc62  nop
0x18008cc63  lea     rcx, [rbp+var_60]
0x18008cc67  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008cc6c  xor     eax, eax
0x18008cc6e  mov     rcx, [rbp+var_8]
0x18008cc72  xor     rcx, rsp; StackCookie
0x18008cc75  call    __security_check_cookie
0x18008cc7a  lea     r11, [rsp+80h+var_s0]
0x18008cc82  mov     rbx, [r11+30h]
0x18008cc86  mov     rsi, [r11+38h]
0x18008cc8a  mov     rsp, r11
0x18008cc8d  pop     r14
0x18008cc8f  pop     rdi
0x18008cc90  pop     rbp
0x18008cc91  retn
```
