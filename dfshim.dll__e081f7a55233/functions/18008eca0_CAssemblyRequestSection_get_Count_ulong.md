# CAssemblyRequestSection::get_Count(ulong *)

- ea: `0x18008eca0`
- end: `0x18008ef00`
- name: `?get_Count@CAssemblyRequestSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CAssemblyRequestSection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x18004f2dc`
- `0x18007338c`
- `0x18008eca0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ed5d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ee31`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ed5d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ee31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008ede7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008eee1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008ede7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008eee1`

## string_xrefs

- `0x18008ed98`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008ee96`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008ecba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CAssemblyRequestSection::get_Count(CAssemblyRequestSection *this, unsigned int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // esi
  int v8; // edx
  unsigned __int64 v9; // rcx
  signed int v10; // ecx
  unsigned int i; // esi
  int v12; // r14d
  signed int v13; // ecx
  const char *v15; // [rsp+20h] [rbp-30h] BYREF
  int v16; // [rsp+28h] [rbp-28h]
  unsigned int v17; // [rsp+30h] [rbp-20h]
  const char *v18; // [rsp+38h] [rbp-18h] BYREF
  int v19; // [rsp+40h] [rbp-10h]
  int v20; // [rsp+48h] [rbp-8h]
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF

  v17 = -2147023537;
  v15 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v21 = 0;
  v22 = 0;
  if ( !a2 )
  {
    v16 = 6986;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v13 = 0;
      }
      else
      {
        v19 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v18,
          &v18);
        v13 = v20;
      }
      if ( v13 < 0 )
        RaiseException(v13, 1u, 0, 0);
    }
    return v17;
  }
  *a2 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v16 = 6987;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6988;
LABEL_29:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v15,
      &v15);
    return v17;
  }
  if ( *((_BYTE *)this + 44) )
  {
    v4 = *((_DWORD *)this + 10);
    v5 = 0;
    *a2 = v4;
  }
  else
  {
    v6 = CdfEnumerateStringTable(*((_QWORD *)this + 4), &v21);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v12 = Windows::Cdf::Rtl::MovePosition(v21, 1, &v22);
        if ( v12 < 0 )
          break;
        if ( v22 != 1 )
        {
          *((_DWORD *)this + 10) = i;
          *((_BYTE *)this + 44) = 1;
          v5 = 0;
          *a2 = i;
          goto LABEL_13;
        }
      }
      if ( v12 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x1B58,
        v12,
        (unsigned int)v15);
      v9 = (unsigned int)v12;
    }
    else
    {
      if ( v6 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x1B54,
        v7,
        (unsigned int)v15);
      v9 = v7;
    }
    v5 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
LABEL_13:
    if ( v21 )
    {
      v17 = -1073741595;
      v15 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v10 = 0;
      }
      else
      {
        v16 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v15,
          &v15);
        v10 = v17;
      }
      if ( v10 < 0 )
        RaiseException(v10, 1u, 0, 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18008eca0  mov     [rsp-28h+arg_0], rbx
0x18008eca5  push    rbp
0x18008eca6  push    rsi
0x18008eca7  push    rdi
0x18008eca8  push    r12
0x18008ecaa  push    r14
0x18008ecac  mov     rbp, rsp
0x18008ecaf  sub     rsp, 50h
0x18008ecb3  mov     [rbp+var_20], 8007054Fh
0x18008ecba  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ecc1  mov     [rbp+var_30], r12
0x18008ecc5  mov     rdi, rdx
0x18008ecc8  mov     [rbp+arg_8], 0
0x18008ecd0  mov     rbx, rcx
0x18008ecd3  mov     [rbp+arg_10], 0
0x18008ecdb  test    rdx, rdx
0x18008ecde  jz      loc_18008EE76
0x18008ece4  mov     dword ptr [rdx], 0
0x18008ecea  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008ecf1  test    rdx, rdx
0x18008ecf4  jz      loc_18008EE60
0x18008ecfa  mov     rcx, [rcx+18h]
0x18008ecfe  call    RtlIsTypeSafeHandleValid
0x18008ed03  test    al, al
0x18008ed05  jz      loc_18008EE60
0x18008ed0b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008ed12  test    rdx, rdx
0x18008ed15  jz      loc_18008EE57
0x18008ed1b  mov     rcx, [rbx+20h]
0x18008ed1f  call    RtlIsTypeSafeHandleValid
0x18008ed24  test    al, al
0x18008ed26  jz      loc_18008EE57
0x18008ed2c  cmp     byte ptr [rbx+2Ch], 0
0x18008ed30  jz      short loc_18008ED3E
0x18008ed32  mov     eax, [rbx+28h]
0x18008ed35  xor     ebx, ebx
0x18008ed37  mov     [rdi], eax
0x18008ed39  jmp     loc_18008EEEA
0x18008ed3e  mov     rcx, [rbx+20h]
0x18008ed42  lea     rdx, [rbp+arg_8]
0x18008ed46  call    CdfEnumerateStringTable
0x18008ed4b  mov     esi, eax
0x18008ed4d  test    eax, eax
0x18008ed4f  jns     loc_18008EDF2
0x18008ed55  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008ed5b  jnz     short loc_18008ED63
0x18008ed5d  call    cs:__imp_DebugBreak
0x18008ed63  mov     r9d, esi; int
0x18008ed66  lea     rcx, aStatusPropagat; "Status propagated"
0x18008ed6d  mov     r8d, 1B54h; char *
0x18008ed73  mov     rdx, r12; char *
0x18008ed76  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008ed7b  mov     ecx, esi; this
0x18008ed7d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008ed82  mov     ebx, eax
0x18008ed84  mov     rdx, [rbp+arg_8]
0x18008ed88  test    rdx, rdx
0x18008ed8b  jz      loc_18008EEEA
0x18008ed91  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008ed98  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ed9f  mov     [rbp+var_20], 0C00000E5h
0x18008eda6  mov     [rbp+var_30], rcx
0x18008edaa  test    rax, rax
0x18008edad  jnz     short loc_18008EDC8
0x18008edaf  mov     [rbp+var_28], 401h
0x18008edb6  lea     rdx, [rbp+var_30]
0x18008edba  lea     rcx, [rbp+var_30]
0x18008edbe  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008edc3  mov     ecx, [rbp+var_20]
0x18008edc6  jmp     short loc_18008EDD5
0x18008edc8  mov     ecx, [rax]
0x18008edca  mov     rax, [rax+20h]
0x18008edce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008edd3  xor     ecx, ecx; dwExceptionCode
0x18008edd5  test    ecx, ecx
0x18008edd7  jns     loc_18008EEEA
0x18008eddd  xor     r9d, r9d; lpArguments
0x18008ede0  xor     r8d, r8d; nNumberOfArguments
0x18008ede3  lea     edx, [r9+1]; dwExceptionFlags
0x18008ede7  call    cs:__imp_RaiseException
0x18008eded  jmp     loc_18008EEEA
0x18008edf2  xor     esi, esi
0x18008edf4  mov     rcx, [rbp+arg_8]
0x18008edf8  lea     r8, [rbp+arg_10]
0x18008edfc  mov     edx, 1
0x18008ee01  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x18008ee06  mov     r14d, eax
0x18008ee09  test    eax, eax
0x18008ee0b  js      short loc_18008EE28
0x18008ee0d  cmp     [rbp+arg_10], 1
0x18008ee12  jnz     short loc_18008EE18
0x18008ee14  inc     esi
0x18008ee16  jmp     short loc_18008EDF4
0x18008ee18  mov     [rbx+28h], esi
0x18008ee1b  mov     byte ptr [rbx+2Ch], 1
0x18008ee1f  xor     ebx, ebx
0x18008ee21  mov     [rdi], esi
0x18008ee23  jmp     loc_18008ED84
0x18008ee28  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008ee2f  jnz     short loc_18008EE37
0x18008ee31  call    cs:__imp_DebugBreak
0x18008ee37  mov     r9d, r14d; int
0x18008ee3a  lea     rcx, aStatusPropagat; "Status propagated"
0x18008ee41  mov     r8d, 1B58h; char *
0x18008ee47  mov     rdx, r12; char *
0x18008ee4a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008ee4f  mov     ecx, r14d
0x18008ee52  jmp     loc_18008ED7D
0x18008ee57  mov     [rbp+var_28], 1B4Ch
0x18008ee5e  jmp     short loc_18008EE67
0x18008ee60  mov     [rbp+var_28], 1B4Bh
0x18008ee67  lea     rdx, [rbp+var_30]
0x18008ee6b  lea     rcx, [rbp+var_30]
0x18008ee6f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008ee74  jmp     short loc_18008EEE7
0x18008ee76  lea     rcx, [rbp+var_30]
0x18008ee7a  mov     [rbp+var_28], 1B4Ah
0x18008ee81  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008ee86  mov     rdx, [rbp+arg_8]
0x18008ee8a  test    rdx, rdx
0x18008ee8d  jz      short loc_18008EEE7
0x18008ee8f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008ee96  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ee9d  mov     [rbp+var_8], 0C00000E5h
0x18008eea4  mov     [rbp+var_18], rcx
0x18008eea8  test    rax, rax
0x18008eeab  jnz     short loc_18008EEC6
0x18008eead  mov     [rbp+var_10], 401h
0x18008eeb4  lea     rdx, [rbp+var_18]
0x18008eeb8  lea     rcx, [rbp+var_18]
0x18008eebc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008eec1  mov     ecx, [rbp+var_8]
0x18008eec4  jmp     short loc_18008EED3
0x18008eec6  mov     ecx, [rax]
0x18008eec8  mov     rax, [rax+20h]
0x18008eecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eed1  xor     ecx, ecx; dwExceptionCode
0x18008eed3  test    ecx, ecx
0x18008eed5  jns     short loc_18008EEE7
0x18008eed7  xor     r9d, r9d; lpArguments
0x18008eeda  xor     r8d, r8d; nNumberOfArguments
0x18008eedd  lea     edx, [r9+1]; dwExceptionFlags
0x18008eee1  call    cs:__imp_RaiseException
0x18008eee7  mov     ebx, [rbp+var_20]
0x18008eeea  mov     eax, ebx
0x18008eeec  mov     rbx, [rsp+50h+arg_0]
0x18008eef4  add     rsp, 50h
0x18008eef8  pop     r14
0x18008eefa  pop     r12
0x18008eefc  pop     rdi
0x18008eefd  pop     rsi
0x18008eefe  pop     rbp
0x18008eeff  retn
```
