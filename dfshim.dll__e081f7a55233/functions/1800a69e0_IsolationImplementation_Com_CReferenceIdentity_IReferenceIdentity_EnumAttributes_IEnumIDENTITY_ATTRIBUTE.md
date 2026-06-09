# IsolationImplementation::Com::CReferenceIdentity_IReferenceIdentity::EnumAttributes(IEnumIDENTITY_ATTRIBUTE * *)

- ea: `0x1800a69e0`
- end: `0x1800a6b83`
- name: `?EnumAttributes@CReferenceIdentity_IReferenceIdentity@Com@IsolationImplementation@@MEAAJPEAPEAUIEnumIDENTITY_ATTRIBUTE@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CReferenceIdentity_IReferenceIdentity *__hidden this, struct IEnumIDENTITY_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180012b1c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001ac94`
- `0x1800448bc`
- `0x18004f2dc`
- `0x1800a69e0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6a2c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6a2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6ab4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6b54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6ab4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6b54`

## string_xrefs

- `0x1800a6a6b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a6b0f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a6a35`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`
- `0x1800a6ae9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CReferenceIdentity_IReferenceIdentity::EnumAttributes(
        IsolationImplementation::Com::CReferenceIdentity_IReferenceIdentity *this,
        struct IEnumIDENTITY_ATTRIBUTE **a2)
{
  __int64 v2; // rcx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // edi
  int v8; // edx
  unsigned int v9; // ebx
  __int64 v10; // r10
  unsigned int *v11; // r11
  signed int v12; // ecx
  int v13; // eax
  int v14; // r9d
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  const char *v19; // [rsp+20h] [rbp-20h] BYREF
  int v20; // [rsp+28h] [rbp-18h]
  int v21; // [rsp+30h] [rbp-10h]
  __int64 v22; // [rsp+50h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 1);
  if ( a2 )
    *a2 = 0;
  v4 = *(_QWORD *)(v2 + 16);
  v22 = 0;
  v5 = RtlCreateReferenceIdentityAttributeEnumerator(v4, &v22);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( v5 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
      (const char *)0x8E,
      v7,
      (unsigned int)v19);
    v9 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v7, v8);
    goto LABEL_7;
  }
  v13 = IsolationImplementation::Com::CopyOut(v22, v6, a2);
  v9 = v13;
  if ( v13 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
      (const char *)0x90,
      v13,
      v14);
LABEL_7:
    if ( v22 )
    {
      v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      v21 = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
        v12 = 0;
      }
      else
      {
        v20 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
        v12 = v21;
      }
      if ( v12 < 0 )
        RaiseException(v12, 1u, 0, 0);
    }
    return v9;
  }
  if ( v22 )
  {
    v21 = -1073741595;
    v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
      v17 = 0;
    }
    else
    {
      v20 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
      v17 = v21;
    }
    if ( v17 < 0 )
      RaiseException(v17, 1u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a69e0  mov     [rsp-8+arg_8], rbx
0x1800a69e5  mov     [rsp-8+arg_10], rdi
0x1800a69ea  push    rbp
0x1800a69eb  mov     rbp, rsp
0x1800a69ee  sub     rsp, 40h
0x1800a69f2  mov     rcx, [rcx+8]
0x1800a69f6  mov     rbx, rdx
0x1800a69f9  test    rdx, rdx
0x1800a69fc  jz      short loc_1800A6A05
0x1800a69fe  mov     qword ptr [rdx], 0
0x1800a6a05  mov     rcx, [rcx+10h]
0x1800a6a09  lea     rdx, [rbp+arg_0]
0x1800a6a0d  mov     [rbp+arg_0], 0
0x1800a6a15  call    RtlCreateReferenceIdentityAttributeEnumerator
0x1800a6a1a  mov     edi, eax
0x1800a6a1c  test    eax, eax
0x1800a6a1e  jns     loc_1800A6AD4
0x1800a6a24  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a6a2a  jnz     short loc_1800A6A32
0x1800a6a2c  call    cs:__imp_DebugBreak
0x1800a6a32  mov     r9d, edi; int
0x1800a6a35  lea     rdx, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6a3c  mov     r8d, 8Eh; char *
0x1800a6a42  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a6a49  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a6a4e  mov     ecx, edi; this
0x1800a6a50  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a6a55  mov     ebx, eax
0x1800a6a57  mov     r10, [rbp+arg_0]
0x1800a6a5b  test    r10, r10
0x1800a6a5e  jz      loc_1800A6B5C
0x1800a6a64  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a6a6b  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6a72  mov     [rbp+var_20], rax
0x1800a6a76  mov     [rbp+var_10], 0C00000E5h
0x1800a6a7d  test    r11, r11
0x1800a6a80  jz      short loc_1800A6ABF
0x1800a6a82  mov     rdx, r11
0x1800a6a85  mov     rcx, r10
0x1800a6a88  call    RtlIsTypeSafeHandleValid
0x1800a6a8d  test    al, al
0x1800a6a8f  jz      short loc_1800A6ABF
0x1800a6a91  mov     ecx, [r11]
0x1800a6a94  mov     rdx, r10
0x1800a6a97  mov     rax, [r11+20h]
0x1800a6a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6aa0  xor     ecx, ecx; dwExceptionCode
0x1800a6aa2  test    ecx, ecx
0x1800a6aa4  jns     loc_1800A6B5C
0x1800a6aaa  xor     r9d, r9d; lpArguments
0x1800a6aad  xor     r8d, r8d; nNumberOfArguments
0x1800a6ab0  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6ab4  call    cs:__imp_RaiseException
0x1800a6aba  jmp     loc_1800A6B5C
0x1800a6abf  mov     [rbp+var_18], 124h
0x1800a6ac6  lea     rcx, [rbp+var_20]
0x1800a6aca  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a6acf  mov     ecx, [rbp+var_10]
0x1800a6ad2  jmp     short loc_1800A6AA2
0x1800a6ad4  mov     rcx, [rbp+arg_0]
0x1800a6ad8  mov     r8, rbx
0x1800a6adb  call    ?CopyOut@Com@IsolationImplementation@@YAJU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800a6ae0  mov     ebx, eax
0x1800a6ae2  test    eax, eax
0x1800a6ae4  jns     short loc_1800A6AFF
0x1800a6ae6  mov     r8d, eax; int
0x1800a6ae9  lea     rcx, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6af0  mov     edx, 90h; char *
0x1800a6af5  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a6afa  jmp     loc_1800A6A57
0x1800a6aff  mov     r10, [rbp+arg_0]
0x1800a6b03  test    r10, r10
0x1800a6b06  jz      short loc_1800A6B5A
0x1800a6b08  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a6b0f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6b16  mov     [rbp+var_10], 0C00000E5h
0x1800a6b1d  mov     [rbp+var_20], rax
0x1800a6b21  test    r11, r11
0x1800a6b24  jz      short loc_1800A6B6E
0x1800a6b26  mov     rdx, r11
0x1800a6b29  mov     rcx, r10
0x1800a6b2c  call    RtlIsTypeSafeHandleValid
0x1800a6b31  test    al, al
0x1800a6b33  jz      short loc_1800A6B6E
0x1800a6b35  mov     ecx, [r11]
0x1800a6b38  mov     rdx, r10
0x1800a6b3b  mov     rax, [r11+20h]
0x1800a6b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6b44  xor     ecx, ecx; dwExceptionCode
0x1800a6b46  test    ecx, ecx
0x1800a6b48  jns     short loc_1800A6B5A
0x1800a6b4a  xor     r9d, r9d; lpArguments
0x1800a6b4d  xor     r8d, r8d; nNumberOfArguments
0x1800a6b50  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6b54  call    cs:__imp_RaiseException
0x1800a6b5a  xor     ebx, ebx
0x1800a6b5c  mov     rdi, [rsp+40h+arg_10]
0x1800a6b61  mov     eax, ebx
0x1800a6b63  mov     rbx, [rsp+40h+arg_8]
0x1800a6b68  add     rsp, 40h
0x1800a6b6c  pop     rbp
0x1800a6b6d  retn
0x1800a6b6e  mov     [rbp+var_18], 124h
0x1800a6b75  lea     rcx, [rbp+var_20]
0x1800a6b79  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a6b7e  mov     ecx, [rbp+var_10]
0x1800a6b81  jmp     short loc_1800A6B46
```
