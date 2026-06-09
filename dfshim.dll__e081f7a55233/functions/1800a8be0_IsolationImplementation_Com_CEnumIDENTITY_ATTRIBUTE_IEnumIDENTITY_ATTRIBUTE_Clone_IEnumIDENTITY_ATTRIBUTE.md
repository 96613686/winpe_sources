# IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE_IEnumIDENTITY_ATTRIBUTE::Clone(IEnumIDENTITY_ATTRIBUTE * *)

- ea: `0x1800a8be0`
- end: `0x1800a8d77`
- name: `?Clone@CEnumIDENTITY_ATTRIBUTE_IEnumIDENTITY_ATTRIBUTE@Com@IsolationImplementation@@MEAAJPEAPEAUIEnumIDENTITY_ATTRIBUTE@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE_IEnumIDENTITY_ATTRIBUTE *__hidden this, struct IEnumIDENTITY_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180012b1c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001ac94`
- `0x18004f2dc`
- `0x1800a8be0`
- `0x180107504`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8c20`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8c20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8ca8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8d48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8ca8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8d48`

## string_xrefs

- `0x1800a8c5f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a8d03`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a8c29`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x1800a8cdd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE_IEnumIDENTITY_ATTRIBUTE::Clone(
        IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE_IEnumIDENTITY_ATTRIBUTE *this,
        struct IEnumIDENTITY_ATTRIBUTE **a2)
{
  __int64 v2; // rcx
  int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // edx
  unsigned int v8; // ebx
  __int64 v9; // r10
  unsigned int *v10; // r11
  signed int v11; // ecx
  int v12; // eax
  int v13; // r9d
  __int64 v14; // r10
  unsigned int *v15; // r11
  signed int v16; // ecx
  const char *v18; // [rsp+20h] [rbp-20h] BYREF
  int v19; // [rsp+28h] [rbp-18h]
  int v20; // [rsp+30h] [rbp-10h]
  __int64 v21; // [rsp+50h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 1);
  v21 = 0;
  v4 = RtlCloneIdentityAttributeEnumerator(*(_QWORD *)(v2 + 16), &v21);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
      (const char *)0xC0,
      v6,
      (unsigned int)v18);
    v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v6, v7);
    goto LABEL_5;
  }
  v12 = IsolationImplementation::Com::CopyOut(v21, v5, a2);
  v8 = v12;
  if ( v12 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
      (const char *)0xC1,
      v12,
      v13);
LABEL_5:
    if ( v21 )
    {
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      v20 = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v21) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v10 + 4))(*v10, v9);
        v11 = 0;
      }
      else
      {
        v19 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v18);
        v11 = v20;
      }
      if ( v11 < 0 )
        RaiseException(v11, 1u, 0, 0);
    }
    return v8;
  }
  if ( v21 )
  {
    v20 = -1073741595;
    v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v21) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v14);
      v16 = 0;
    }
    else
    {
      v19 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v18);
      v16 = v20;
    }
    if ( v16 < 0 )
      RaiseException(v16, 1u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a8be0  mov     [rsp-8+arg_8], rbx
0x1800a8be5  mov     [rsp-8+arg_10], rdi
0x1800a8bea  push    rbp
0x1800a8beb  mov     rbp, rsp
0x1800a8bee  sub     rsp, 40h
0x1800a8bf2  mov     rcx, [rcx+8]
0x1800a8bf6  mov     rdi, rdx
0x1800a8bf9  lea     rdx, [rbp+arg_0]
0x1800a8bfd  mov     [rbp+arg_0], 0
0x1800a8c05  mov     rcx, [rcx+10h]
0x1800a8c09  call    RtlCloneIdentityAttributeEnumerator
0x1800a8c0e  mov     ebx, eax
0x1800a8c10  test    eax, eax
0x1800a8c12  jns     loc_1800A8CC8
0x1800a8c18  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a8c1e  jnz     short loc_1800A8C26
0x1800a8c20  call    cs:__imp_DebugBreak
0x1800a8c26  mov     r9d, ebx; int
0x1800a8c29  lea     rdx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8c30  mov     r8d, 0C0h; char *
0x1800a8c36  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a8c3d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a8c42  mov     ecx, ebx; this
0x1800a8c44  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a8c49  mov     ebx, eax
0x1800a8c4b  mov     r10, [rbp+arg_0]
0x1800a8c4f  test    r10, r10
0x1800a8c52  jz      loc_1800A8D50
0x1800a8c58  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a8c5f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8c66  mov     [rbp+var_20], rax
0x1800a8c6a  mov     [rbp+var_10], 0C00000E5h
0x1800a8c71  test    r11, r11
0x1800a8c74  jz      short loc_1800A8CB3
0x1800a8c76  mov     rdx, r11
0x1800a8c79  mov     rcx, r10
0x1800a8c7c  call    RtlIsTypeSafeHandleValid
0x1800a8c81  test    al, al
0x1800a8c83  jz      short loc_1800A8CB3
0x1800a8c85  mov     ecx, [r11]
0x1800a8c88  mov     rdx, r10
0x1800a8c8b  mov     rax, [r11+20h]
0x1800a8c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8c94  xor     ecx, ecx; dwExceptionCode
0x1800a8c96  test    ecx, ecx
0x1800a8c98  jns     loc_1800A8D50
0x1800a8c9e  xor     r9d, r9d; lpArguments
0x1800a8ca1  xor     r8d, r8d; nNumberOfArguments
0x1800a8ca4  lea     edx, [r9+1]; dwExceptionFlags
0x1800a8ca8  call    cs:__imp_RaiseException
0x1800a8cae  jmp     loc_1800A8D50
0x1800a8cb3  mov     [rbp+var_18], 124h
0x1800a8cba  lea     rcx, [rbp+var_20]
0x1800a8cbe  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a8cc3  mov     ecx, [rbp+var_10]
0x1800a8cc6  jmp     short loc_1800A8C96
0x1800a8cc8  mov     rcx, [rbp+arg_0]
0x1800a8ccc  mov     r8, rdi
0x1800a8ccf  call    ?CopyOut@Com@IsolationImplementation@@YAJU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800a8cd4  mov     ebx, eax
0x1800a8cd6  test    eax, eax
0x1800a8cd8  jns     short loc_1800A8CF3
0x1800a8cda  mov     r8d, eax; int
0x1800a8cdd  lea     rcx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8ce4  mov     edx, 0C1h; char *
0x1800a8ce9  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a8cee  jmp     loc_1800A8C4B
0x1800a8cf3  mov     r10, [rbp+arg_0]
0x1800a8cf7  test    r10, r10
0x1800a8cfa  jz      short loc_1800A8D4E
0x1800a8cfc  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800a8d03  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8d0a  mov     [rbp+var_10], 0C00000E5h
0x1800a8d11  mov     [rbp+var_20], rax
0x1800a8d15  test    r11, r11
0x1800a8d18  jz      short loc_1800A8D62
0x1800a8d1a  mov     rdx, r11
0x1800a8d1d  mov     rcx, r10
0x1800a8d20  call    RtlIsTypeSafeHandleValid
0x1800a8d25  test    al, al
0x1800a8d27  jz      short loc_1800A8D62
0x1800a8d29  mov     ecx, [r11]
0x1800a8d2c  mov     rdx, r10
0x1800a8d2f  mov     rax, [r11+20h]
0x1800a8d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8d38  xor     ecx, ecx; dwExceptionCode
0x1800a8d3a  test    ecx, ecx
0x1800a8d3c  jns     short loc_1800A8D4E
0x1800a8d3e  xor     r9d, r9d; lpArguments
0x1800a8d41  xor     r8d, r8d; nNumberOfArguments
0x1800a8d44  lea     edx, [r9+1]; dwExceptionFlags
0x1800a8d48  call    cs:__imp_RaiseException
0x1800a8d4e  xor     ebx, ebx
0x1800a8d50  mov     rdi, [rsp+40h+arg_10]
0x1800a8d55  mov     eax, ebx
0x1800a8d57  mov     rbx, [rsp+40h+arg_8]
0x1800a8d5c  add     rsp, 40h
0x1800a8d60  pop     rbp
0x1800a8d61  retn
0x1800a8d62  mov     [rbp+var_18], 124h
0x1800a8d69  lea     rcx, [rbp+var_20]
0x1800a8d6d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a8d72  mov     ecx, [rbp+var_10]
0x1800a8d75  jmp     short loc_1800A8D3A
```
