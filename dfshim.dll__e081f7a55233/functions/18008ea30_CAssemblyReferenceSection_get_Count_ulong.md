# CAssemblyReferenceSection::get_Count(ulong *)

- ea: `0x18008ea30`
- end: `0x18008ec90`
- name: `?get_Count@CAssemblyReferenceSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CAssemblyReferenceSection *__hidden this, unsigned int *)`
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
- `0x180073258`
- `0x18008ea30`
- `0x18010aa70`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008eaed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ebc1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008eaed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ebc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008eb77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008ec71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008eb77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008ec71`

## string_xrefs

- `0x18008eb28`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008ec26`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008ea4a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CAssemblyReferenceSection::get_Count(CAssemblyReferenceSection *this, unsigned int *a2)
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
    v16 = 6064;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
    v16 = 6065;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6066;
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
    v6 = CdfEnumerateReferenceIdentityTable(*((_QWORD *)this + 4), &v21);
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
        (const char *)0x17BE,
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
        (const char *)0x17BA,
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
0x18008ea30  mov     [rsp-28h+arg_0], rbx
0x18008ea35  push    rbp
0x18008ea36  push    rsi
0x18008ea37  push    rdi
0x18008ea38  push    r12
0x18008ea3a  push    r14
0x18008ea3c  mov     rbp, rsp
0x18008ea3f  sub     rsp, 50h
0x18008ea43  mov     [rbp+var_20], 8007054Fh
0x18008ea4a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ea51  mov     [rbp+var_30], r12
0x18008ea55  mov     rdi, rdx
0x18008ea58  mov     [rbp+arg_8], 0
0x18008ea60  mov     rbx, rcx
0x18008ea63  mov     [rbp+arg_10], 0
0x18008ea6b  test    rdx, rdx
0x18008ea6e  jz      loc_18008EC06
0x18008ea74  mov     dword ptr [rdx], 0
0x18008ea7a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008ea81  test    rdx, rdx
0x18008ea84  jz      loc_18008EBF0
0x18008ea8a  mov     rcx, [rcx+18h]
0x18008ea8e  call    RtlIsTypeSafeHandleValid
0x18008ea93  test    al, al
0x18008ea95  jz      loc_18008EBF0
0x18008ea9b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008eaa2  test    rdx, rdx
0x18008eaa5  jz      loc_18008EBE7
0x18008eaab  mov     rcx, [rbx+20h]
0x18008eaaf  call    RtlIsTypeSafeHandleValid
0x18008eab4  test    al, al
0x18008eab6  jz      loc_18008EBE7
0x18008eabc  cmp     byte ptr [rbx+2Ch], 0
0x18008eac0  jz      short loc_18008EACE
0x18008eac2  mov     eax, [rbx+28h]
0x18008eac5  xor     ebx, ebx
0x18008eac7  mov     [rdi], eax
0x18008eac9  jmp     loc_18008EC7A
0x18008eace  mov     rcx, [rbx+20h]
0x18008ead2  lea     rdx, [rbp+arg_8]
0x18008ead6  call    CdfEnumerateReferenceIdentityTable
0x18008eadb  mov     esi, eax
0x18008eadd  test    eax, eax
0x18008eadf  jns     loc_18008EB82
0x18008eae5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008eaeb  jnz     short loc_18008EAF3
0x18008eaed  call    cs:__imp_DebugBreak
0x18008eaf3  mov     r9d, esi; int
0x18008eaf6  lea     rcx, aStatusPropagat; "Status propagated"
0x18008eafd  mov     r8d, 17BAh; char *
0x18008eb03  mov     rdx, r12; char *
0x18008eb06  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008eb0b  mov     ecx, esi; this
0x18008eb0d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008eb12  mov     ebx, eax
0x18008eb14  mov     rdx, [rbp+arg_8]
0x18008eb18  test    rdx, rdx
0x18008eb1b  jz      loc_18008EC7A
0x18008eb21  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008eb28  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008eb2f  mov     [rbp+var_20], 0C00000E5h
0x18008eb36  mov     [rbp+var_30], rcx
0x18008eb3a  test    rax, rax
0x18008eb3d  jnz     short loc_18008EB58
0x18008eb3f  mov     [rbp+var_28], 401h
0x18008eb46  lea     rdx, [rbp+var_30]
0x18008eb4a  lea     rcx, [rbp+var_30]
0x18008eb4e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008eb53  mov     ecx, [rbp+var_20]
0x18008eb56  jmp     short loc_18008EB65
0x18008eb58  mov     ecx, [rax]
0x18008eb5a  mov     rax, [rax+20h]
0x18008eb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb63  xor     ecx, ecx; dwExceptionCode
0x18008eb65  test    ecx, ecx
0x18008eb67  jns     loc_18008EC7A
0x18008eb6d  xor     r9d, r9d; lpArguments
0x18008eb70  xor     r8d, r8d; nNumberOfArguments
0x18008eb73  lea     edx, [r9+1]; dwExceptionFlags
0x18008eb77  call    cs:__imp_RaiseException
0x18008eb7d  jmp     loc_18008EC7A
0x18008eb82  xor     esi, esi
0x18008eb84  mov     rcx, [rbp+arg_8]
0x18008eb88  lea     r8, [rbp+arg_10]
0x18008eb8c  mov     edx, 1
0x18008eb91  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,__int64,__int64 &)
0x18008eb96  mov     r14d, eax
0x18008eb99  test    eax, eax
0x18008eb9b  js      short loc_18008EBB8
0x18008eb9d  cmp     [rbp+arg_10], 1
0x18008eba2  jnz     short loc_18008EBA8
0x18008eba4  inc     esi
0x18008eba6  jmp     short loc_18008EB84
0x18008eba8  mov     [rbx+28h], esi
0x18008ebab  mov     byte ptr [rbx+2Ch], 1
0x18008ebaf  xor     ebx, ebx
0x18008ebb1  mov     [rdi], esi
0x18008ebb3  jmp     loc_18008EB14
0x18008ebb8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008ebbf  jnz     short loc_18008EBC7
0x18008ebc1  call    cs:__imp_DebugBreak
0x18008ebc7  mov     r9d, r14d; int
0x18008ebca  lea     rcx, aStatusPropagat; "Status propagated"
0x18008ebd1  mov     r8d, 17BEh; char *
0x18008ebd7  mov     rdx, r12; char *
0x18008ebda  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008ebdf  mov     ecx, r14d
0x18008ebe2  jmp     loc_18008EB0D
0x18008ebe7  mov     [rbp+var_28], 17B2h
0x18008ebee  jmp     short loc_18008EBF7
0x18008ebf0  mov     [rbp+var_28], 17B1h
0x18008ebf7  lea     rdx, [rbp+var_30]
0x18008ebfb  lea     rcx, [rbp+var_30]
0x18008ebff  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008ec04  jmp     short loc_18008EC77
0x18008ec06  lea     rcx, [rbp+var_30]
0x18008ec0a  mov     [rbp+var_28], 17B0h
0x18008ec11  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008ec16  mov     rdx, [rbp+arg_8]
0x18008ec1a  test    rdx, rdx
0x18008ec1d  jz      short loc_18008EC77
0x18008ec1f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR@@U_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_REFERENCE_IDENTITY_TABLE_ENUMERATOR,_CDF_REFERENCE_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008ec26  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ec2d  mov     [rbp+var_8], 0C00000E5h
0x18008ec34  mov     [rbp+var_18], rcx
0x18008ec38  test    rax, rax
0x18008ec3b  jnz     short loc_18008EC56
0x18008ec3d  mov     [rbp+var_10], 401h
0x18008ec44  lea     rdx, [rbp+var_18]
0x18008ec48  lea     rcx, [rbp+var_18]
0x18008ec4c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008ec51  mov     ecx, [rbp+var_8]
0x18008ec54  jmp     short loc_18008EC63
0x18008ec56  mov     ecx, [rax]
0x18008ec58  mov     rax, [rax+20h]
0x18008ec5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec61  xor     ecx, ecx; dwExceptionCode
0x18008ec63  test    ecx, ecx
0x18008ec65  jns     short loc_18008EC77
0x18008ec67  xor     r9d, r9d; lpArguments
0x18008ec6a  xor     r8d, r8d; nNumberOfArguments
0x18008ec6d  lea     edx, [r9+1]; dwExceptionFlags
0x18008ec71  call    cs:__imp_RaiseException
0x18008ec77  mov     ebx, [rbp+var_20]
0x18008ec7a  mov     eax, ebx
0x18008ec7c  mov     rbx, [rsp+50h+arg_0]
0x18008ec84  add     rsp, 50h
0x18008ec88  pop     r14
0x18008ec8a  pop     r12
0x18008ec8c  pop     rdi
0x18008ec8d  pop     rsi
0x18008ec8e  pop     rbp
0x18008ec8f  retn
```
