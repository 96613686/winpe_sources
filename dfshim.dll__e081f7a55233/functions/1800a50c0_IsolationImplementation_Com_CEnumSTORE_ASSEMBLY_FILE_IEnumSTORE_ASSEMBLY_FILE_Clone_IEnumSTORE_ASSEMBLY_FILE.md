# IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::IEnumSTORE_ASSEMBLY_FILE_Clone(IEnumSTORE_ASSEMBLY_FILE * *)

- ea: `0x1800a50c0`
- end: `0x1800a529c`
- name: `?IEnumSTORE_ASSEMBLY_FILE_Clone@CEnumSTORE_ASSEMBLY_FILE@Com@IsolationImplementation@@IEAAJPEAPEAUIEnumSTORE_ASSEMBLY_FILE@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *__hidden this, struct IEnumSTORE_ASSEMBLY_FILE **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a50b0`

## callees

- `0x180012b1c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001a8d8`
- `0x18004c0ac`
- `0x18004f2dc`
- `0x1800a50c0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a50fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a50fe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5186`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5282`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5186`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5282`

## string_xrefs

- `0x1800a513d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a51e7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a5228`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a5107`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassemblyfile.cpp`
- `0x1800a51c6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumstoreassemblyfile.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE::IEnumSTORE_ASSEMBLY_FILE_Clone(
        IsolationImplementation::Com::CEnumSTORE_ASSEMBLY_FILE *this,
        struct IEnumSTORE_ASSEMBLY_FILE **a2)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // edx
  unsigned int v6; // edi
  __int64 v7; // r10
  unsigned int *v8; // r11
  int v9; // ecx
  __int64 v10; // rbx
  int v11; // eax
  int v12; // r9d
  unsigned int *v13; // r10
  unsigned int *v14; // r10
  int v15; // ecx
  const char *v17; // [rsp+20h] [rbp-20h] BYREF
  int v18; // [rsp+28h] [rbp-18h]
  DWORD dwExceptionCode; // [rsp+30h] [rbp-10h]
  __int64 v20; // [rsp+50h] [rbp+10h] BYREF
  struct IEnumSTORE_ASSEMBLY_FILE **v21; // [rsp+58h] [rbp+18h] BYREF

  v21 = a2;
  v2 = *((_QWORD *)this + 2);
  v20 = 0;
  v3 = RtlCloneComponentStoreFileEnumerator(v2, &v20);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v10 = v20;
    v11 = IsolationImplementation::Com::CopyOut(v20, &GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f, &v21);
    v6 = v11;
    if ( v11 < 0 )
    {
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassemblyfile.cpp",
        (const char *)0x92,
        v11,
        v12);
      if ( !v10 )
        return v6;
      dwExceptionCode = -1073741595;
      v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v10) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v10);
        goto LABEL_8;
      }
LABEL_11:
      v18 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v17);
      v9 = dwExceptionCode;
LABEL_9:
      if ( v9 < 0 )
        RaiseException(v9, 1u, 0, 0);
      return v6;
    }
    if ( v10 )
    {
      dwExceptionCode = -1073741595;
      v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v10) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v14 + 4))(*v14, v10);
        v15 = 0;
      }
      else
      {
        v18 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v17);
        v15 = dwExceptionCode;
      }
      if ( v15 < 0 )
        RaiseException(v15, 1u, 0, 0);
    }
    return 0;
  }
  else
  {
    if ( v3 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumstoreassemblyfile.cpp",
      (const char *)0x91,
      v4,
      (unsigned int)v17);
    v6 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v4, v5);
    if ( v20 )
    {
      dwExceptionCode = -1073741595;
      v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v20) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v8 + 4))(*v8, v7);
LABEL_8:
        v9 = 0;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800a50c0  mov     [rsp-8+arg_10], rbx
0x1800a50c5  mov     [rsp-8+arg_18], rdi
0x1800a50ca  mov     [rsp-8+arg_8], rdx
0x1800a50cf  push    rbp
0x1800a50d0  mov     rbp, rsp
0x1800a50d3  sub     rsp, 40h
0x1800a50d7  mov     rcx, [rcx+10h]
0x1800a50db  lea     rdx, [rbp+arg_0]
0x1800a50df  mov     [rbp+arg_0], 0
0x1800a50e7  call    RtlCloneComponentStoreFileEnumerator
0x1800a50ec  mov     ebx, eax
0x1800a50ee  test    eax, eax
0x1800a50f0  jns     loc_1800A51A6
0x1800a50f6  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a50fc  jnz     short loc_1800A5104
0x1800a50fe  call    cs:__imp_DebugBreak
0x1800a5104  mov     r9d, ebx; int
0x1800a5107  lea     rdx, aOnecoreComNetf_66; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a510e  mov     r8d, 91h; char *
0x1800a5114  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a511b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a5120  mov     ecx, ebx; this
0x1800a5122  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a5127  mov     r10, [rbp+arg_0]
0x1800a512b  mov     edi, eax
0x1800a512d  test    r10, r10
0x1800a5130  jz      loc_1800A528A
0x1800a5136  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@VCFileEnumerator@@VCFileEnumeratorCD@@VCFileEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
0x1800a513d  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5144  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800a514b  mov     [rbp+var_20], rax
0x1800a514f  test    r11, r11
0x1800a5152  jz      short loc_1800A5191
0x1800a5154  mov     rdx, r11
0x1800a5157  mov     rcx, r10
0x1800a515a  call    RtlIsTypeSafeHandleValid
0x1800a515f  test    al, al
0x1800a5161  jz      short loc_1800A5191
0x1800a5163  mov     ecx, [r11]
0x1800a5166  mov     rdx, r10
0x1800a5169  mov     rax, [r11+20h]
0x1800a516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5172  xor     ecx, ecx; dwExceptionCode
0x1800a5174  test    ecx, ecx
0x1800a5176  jns     loc_1800A528A
0x1800a517c  xor     r9d, r9d; lpArguments
0x1800a517f  xor     r8d, r8d; nNumberOfArguments
0x1800a5182  lea     edx, [r9+1]; dwExceptionFlags
0x1800a5186  call    cs:__imp_RaiseException
0x1800a518c  jmp     loc_1800A528A
0x1800a5191  mov     [rbp+var_18], 124h
0x1800a5198  lea     rcx, [rbp+var_20]
0x1800a519c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a51a1  mov     ecx, [rbp+dwExceptionCode]
0x1800a51a4  jmp     short loc_1800A5174
0x1800a51a6  mov     rbx, [rbp+arg_0]
0x1800a51aa  lea     r8, [rbp+arg_8]
0x1800a51ae  mov     rcx, rbx
0x1800a51b1  lea     rdx, _GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f
0x1800a51b8  call    ?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800a51bd  mov     edi, eax
0x1800a51bf  test    eax, eax
0x1800a51c1  jns     short loc_1800A521C
0x1800a51c3  mov     r8d, eax; int
0x1800a51c6  lea     rcx, aOnecoreComNetf_66; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a51cd  mov     edx, 92h; char *
0x1800a51d2  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a51d7  test    rbx, rbx
0x1800a51da  jz      loc_1800A528A
0x1800a51e0  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@VCFileEnumerator@@VCFileEnumeratorCD@@VCFileEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
0x1800a51e7  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a51ee  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800a51f5  mov     [rbp+var_20], rax
0x1800a51f9  test    r10, r10
0x1800a51fc  jz      short loc_1800A5191
0x1800a51fe  mov     rdx, r10
0x1800a5201  mov     rcx, rbx
0x1800a5204  call    RtlIsTypeSafeHandleValid
0x1800a5209  test    al, al
0x1800a520b  jz      short loc_1800A5191
0x1800a520d  mov     ecx, [r10]
0x1800a5210  mov     rdx, rbx
0x1800a5213  mov     rax, [r10+20h]
0x1800a5217  jmp     loc_1800A516D
0x1800a521c  test    rbx, rbx
0x1800a521f  jz      short loc_1800A5288
0x1800a5221  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@VCFileEnumerator@@VCFileEnumeratorCD@@VCFileEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
0x1800a5228  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a522f  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800a5236  mov     [rbp+var_20], rax
0x1800a523a  test    r10, r10
0x1800a523d  jz      short loc_1800A5261
0x1800a523f  mov     rdx, r10
0x1800a5242  mov     rcx, rbx
0x1800a5245  call    RtlIsTypeSafeHandleValid
0x1800a524a  test    al, al
0x1800a524c  jz      short loc_1800A5261
0x1800a524e  mov     ecx, [r10]
0x1800a5251  mov     rdx, rbx
0x1800a5254  mov     rax, [r10+20h]
0x1800a5258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a525d  xor     ecx, ecx
0x1800a525f  jmp     short loc_1800A5274
0x1800a5261  mov     [rbp+var_18], 124h
0x1800a5268  lea     rcx, [rbp+var_20]
0x1800a526c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a5271  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x1800a5274  test    ecx, ecx
0x1800a5276  jns     short loc_1800A5288
0x1800a5278  xor     r9d, r9d; lpArguments
0x1800a527b  xor     r8d, r8d; nNumberOfArguments
0x1800a527e  lea     edx, [r9+1]; dwExceptionFlags
0x1800a5282  call    cs:__imp_RaiseException
0x1800a5288  xor     edi, edi
0x1800a528a  mov     rbx, [rsp+40h+arg_10]
0x1800a528f  mov     eax, edi
0x1800a5291  mov     rdi, [rsp+40h+arg_18]
0x1800a5296  add     rsp, 40h
0x1800a529a  pop     rbp
0x1800a529b  retn
```
