# IsolationImplementation::Com::CDefinitionIdentity_IDefinitionIdentity::EnumAttributes(IEnumIDENTITY_ATTRIBUTE * *)

- ea: `0x1800a5b70`
- end: `0x1800a5d13`
- name: `?EnumAttributes@CDefinitionIdentity_IDefinitionIdentity@Com@IsolationImplementation@@MEAAJPEAPEAUIEnumIDENTITY_ATTRIBUTE@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CDefinitionIdentity_IDefinitionIdentity *__hidden this, struct IEnumIDENTITY_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180012b1c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001ac94`
- `0x1800437f8`
- `0x18004f2dc`
- `0x1800a5b70`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5bbc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5bbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5c44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5ce4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5c44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5ce4`

## string_xrefs

- `0x1800a5bfb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a5c9f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a5bc5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`
- `0x1800a5c79`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CDefinitionIdentity_IDefinitionIdentity::EnumAttributes(
        IsolationImplementation::Com::CDefinitionIdentity_IDefinitionIdentity *this,
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
  v5 = RtlCreateDefinitionIdentityAttributeEnumerator(v4, &v22);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( v5 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
      (const char *)0x90,
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
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
      (const char *)0x92,
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
0x1800a5b70  mov     [rsp-8+arg_8], rbx
0x1800a5b75  mov     [rsp-8+arg_10], rdi
0x1800a5b7a  push    rbp
0x1800a5b7b  mov     rbp, rsp
0x1800a5b7e  sub     rsp, 40h
0x1800a5b82  mov     rcx, [rcx+8]
0x1800a5b86  mov     rbx, rdx
0x1800a5b89  test    rdx, rdx
0x1800a5b8c  jz      short loc_1800A5B95
0x1800a5b8e  mov     qword ptr [rdx], 0
0x1800a5b95  mov     rcx, [rcx+10h]
0x1800a5b99  lea     rdx, [rbp+arg_0]
0x1800a5b9d  mov     [rbp+arg_0], 0
0x1800a5ba5  call    RtlCreateDefinitionIdentityAttributeEnumerator
0x1800a5baa  mov     edi, eax
0x1800a5bac  test    eax, eax
0x1800a5bae  jns     loc_1800A5C64
0x1800a5bb4  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a5bba  jnz     short loc_1800A5BC2
0x1800a5bbc  call    cs:__imp_DebugBreak
0x1800a5bc2  mov     r9d, edi; int
0x1800a5bc5  lea     rdx, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5bcc  mov     r8d, 90h; char *
0x1800a5bd2  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a5bd9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a5bde  mov     ecx, edi; this
0x1800a5be0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a5be5  mov     ebx, eax
0x1800a5be7  mov     r10, [rbp+arg_0]
0x1800a5beb  test    r10, r10
0x1800a5bee  jz      loc_1800A5CEC
0x1800a5bf4  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a5bfb  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5c02  mov     [rbp+var_20], rax
0x1800a5c06  mov     [rbp+var_10], 0C00000E5h
0x1800a5c0d  test    r11, r11
0x1800a5c10  jz      short loc_1800A5C4F
0x1800a5c12  mov     rdx, r11
0x1800a5c15  mov     rcx, r10
0x1800a5c18  call    RtlIsTypeSafeHandleValid
0x1800a5c1d  test    al, al
0x1800a5c1f  jz      short loc_1800A5C4F
0x1800a5c21  mov     ecx, [r11]
0x1800a5c24  mov     rdx, r10
0x1800a5c27  mov     rax, [r11+20h]
0x1800a5c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c30  xor     ecx, ecx; dwExceptionCode
0x1800a5c32  test    ecx, ecx
0x1800a5c34  jns     loc_1800A5CEC
0x1800a5c3a  xor     r9d, r9d; lpArguments
0x1800a5c3d  xor     r8d, r8d; nNumberOfArguments
0x1800a5c40  lea     edx, [r9+1]; dwExceptionFlags
0x1800a5c44  call    cs:__imp_RaiseException
0x1800a5c4a  jmp     loc_1800A5CEC
0x1800a5c4f  mov     [rbp+var_18], 124h
0x1800a5c56  lea     rcx, [rbp+var_20]
0x1800a5c5a  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a5c5f  mov     ecx, [rbp+var_10]
0x1800a5c62  jmp     short loc_1800A5C32
0x1800a5c64  mov     rcx, [rbp+arg_0]
0x1800a5c68  mov     r8, rbx
0x1800a5c6b  call    ?CopyOut@Com@IsolationImplementation@@YAJU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800a5c70  mov     ebx, eax
0x1800a5c72  test    eax, eax
0x1800a5c74  jns     short loc_1800A5C8F
0x1800a5c76  mov     r8d, eax; int
0x1800a5c79  lea     rcx, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5c80  mov     edx, 92h; char *
0x1800a5c85  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a5c8a  jmp     loc_1800A5BE7
0x1800a5c8f  mov     r10, [rbp+arg_0]
0x1800a5c93  test    r10, r10
0x1800a5c96  jz      short loc_1800A5CEA
0x1800a5c98  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a5c9f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5ca6  mov     [rbp+var_10], 0C00000E5h
0x1800a5cad  mov     [rbp+var_20], rax
0x1800a5cb1  test    r11, r11
0x1800a5cb4  jz      short loc_1800A5CFE
0x1800a5cb6  mov     rdx, r11
0x1800a5cb9  mov     rcx, r10
0x1800a5cbc  call    RtlIsTypeSafeHandleValid
0x1800a5cc1  test    al, al
0x1800a5cc3  jz      short loc_1800A5CFE
0x1800a5cc5  mov     ecx, [r11]
0x1800a5cc8  mov     rdx, r10
0x1800a5ccb  mov     rax, [r11+20h]
0x1800a5ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5cd4  xor     ecx, ecx; dwExceptionCode
0x1800a5cd6  test    ecx, ecx
0x1800a5cd8  jns     short loc_1800A5CEA
0x1800a5cda  xor     r9d, r9d; lpArguments
0x1800a5cdd  xor     r8d, r8d; nNumberOfArguments
0x1800a5ce0  lea     edx, [r9+1]; dwExceptionFlags
0x1800a5ce4  call    cs:__imp_RaiseException
0x1800a5cea  xor     ebx, ebx
0x1800a5cec  mov     rdi, [rsp+40h+arg_10]
0x1800a5cf1  mov     eax, ebx
0x1800a5cf3  mov     rbx, [rsp+40h+arg_8]
0x1800a5cf8  add     rsp, 40h
0x1800a5cfc  pop     rbp
0x1800a5cfd  retn
0x1800a5cfe  mov     [rbp+var_18], 124h
0x1800a5d05  lea     rcx, [rbp+var_20]
0x1800a5d09  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a5d0e  mov     ecx, [rbp+var_10]
0x1800a5d11  jmp     short loc_1800A5CD6
```
