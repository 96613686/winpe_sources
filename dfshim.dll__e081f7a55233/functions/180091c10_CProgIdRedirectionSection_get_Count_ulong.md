# CProgIdRedirectionSection::get_Count(ulong *)

- ea: `0x180091c10`
- end: `0x180091e70`
- name: `?get_Count@CProgIdRedirectionSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CProgIdRedirectionSection *__hidden this, unsigned int *)`
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
- `0x180091c10`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091ccd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091da1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091ccd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091da1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091e51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d57`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091e51`

## string_xrefs

- `0x180091d08`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091e06`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091c2a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CProgIdRedirectionSection::get_Count(CProgIdRedirectionSection *this, unsigned int *a2)
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
    v16 = 5759;
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
    v16 = 5760;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5761;
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
        (const char *)0x168D,
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
        (const char *)0x1689,
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
0x180091c10  mov     [rsp-28h+arg_0], rbx
0x180091c15  push    rbp
0x180091c16  push    rsi
0x180091c17  push    rdi
0x180091c18  push    r12
0x180091c1a  push    r14
0x180091c1c  mov     rbp, rsp
0x180091c1f  sub     rsp, 50h
0x180091c23  mov     [rbp+var_20], 8007054Fh
0x180091c2a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091c31  mov     [rbp+var_30], r12
0x180091c35  mov     rdi, rdx
0x180091c38  mov     [rbp+arg_8], 0
0x180091c40  mov     rbx, rcx
0x180091c43  mov     [rbp+arg_10], 0
0x180091c4b  test    rdx, rdx
0x180091c4e  jz      loc_180091DE6
0x180091c54  mov     dword ptr [rdx], 0
0x180091c5a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180091c61  test    rdx, rdx
0x180091c64  jz      loc_180091DD0
0x180091c6a  mov     rcx, [rcx+18h]
0x180091c6e  call    RtlIsTypeSafeHandleValid
0x180091c73  test    al, al
0x180091c75  jz      loc_180091DD0
0x180091c7b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180091c82  test    rdx, rdx
0x180091c85  jz      loc_180091DC7
0x180091c8b  mov     rcx, [rbx+20h]
0x180091c8f  call    RtlIsTypeSafeHandleValid
0x180091c94  test    al, al
0x180091c96  jz      loc_180091DC7
0x180091c9c  cmp     byte ptr [rbx+2Ch], 0
0x180091ca0  jz      short loc_180091CAE
0x180091ca2  mov     eax, [rbx+28h]
0x180091ca5  xor     ebx, ebx
0x180091ca7  mov     [rdi], eax
0x180091ca9  jmp     loc_180091E5A
0x180091cae  mov     rcx, [rbx+20h]
0x180091cb2  lea     rdx, [rbp+arg_8]
0x180091cb6  call    CdfEnumerateStringTable
0x180091cbb  mov     esi, eax
0x180091cbd  test    eax, eax
0x180091cbf  jns     loc_180091D62
0x180091cc5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180091ccb  jnz     short loc_180091CD3
0x180091ccd  call    cs:__imp_DebugBreak
0x180091cd3  mov     r9d, esi; int
0x180091cd6  lea     rcx, aStatusPropagat; "Status propagated"
0x180091cdd  mov     r8d, 1689h; char *
0x180091ce3  mov     rdx, r12; char *
0x180091ce6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180091ceb  mov     ecx, esi; this
0x180091ced  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180091cf2  mov     ebx, eax
0x180091cf4  mov     rdx, [rbp+arg_8]
0x180091cf8  test    rdx, rdx
0x180091cfb  jz      loc_180091E5A
0x180091d01  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091d08  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091d0f  mov     [rbp+var_20], 0C00000E5h
0x180091d16  mov     [rbp+var_30], rcx
0x180091d1a  test    rax, rax
0x180091d1d  jnz     short loc_180091D38
0x180091d1f  mov     [rbp+var_28], 401h
0x180091d26  lea     rdx, [rbp+var_30]
0x180091d2a  lea     rcx, [rbp+var_30]
0x180091d2e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091d33  mov     ecx, [rbp+var_20]
0x180091d36  jmp     short loc_180091D45
0x180091d38  mov     ecx, [rax]
0x180091d3a  mov     rax, [rax+20h]
0x180091d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091d43  xor     ecx, ecx; dwExceptionCode
0x180091d45  test    ecx, ecx
0x180091d47  jns     loc_180091E5A
0x180091d4d  xor     r9d, r9d; lpArguments
0x180091d50  xor     r8d, r8d; nNumberOfArguments
0x180091d53  lea     edx, [r9+1]; dwExceptionFlags
0x180091d57  call    cs:__imp_RaiseException
0x180091d5d  jmp     loc_180091E5A
0x180091d62  xor     esi, esi
0x180091d64  mov     rcx, [rbp+arg_8]
0x180091d68  lea     r8, [rbp+arg_10]
0x180091d6c  mov     edx, 1
0x180091d71  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180091d76  mov     r14d, eax
0x180091d79  test    eax, eax
0x180091d7b  js      short loc_180091D98
0x180091d7d  cmp     [rbp+arg_10], 1
0x180091d82  jnz     short loc_180091D88
0x180091d84  inc     esi
0x180091d86  jmp     short loc_180091D64
0x180091d88  mov     [rbx+28h], esi
0x180091d8b  mov     byte ptr [rbx+2Ch], 1
0x180091d8f  xor     ebx, ebx
0x180091d91  mov     [rdi], esi
0x180091d93  jmp     loc_180091CF4
0x180091d98  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x180091d9f  jnz     short loc_180091DA7
0x180091da1  call    cs:__imp_DebugBreak
0x180091da7  mov     r9d, r14d; int
0x180091daa  lea     rcx, aStatusPropagat; "Status propagated"
0x180091db1  mov     r8d, 168Dh; char *
0x180091db7  mov     rdx, r12; char *
0x180091dba  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180091dbf  mov     ecx, r14d
0x180091dc2  jmp     loc_180091CED
0x180091dc7  mov     [rbp+var_28], 1681h
0x180091dce  jmp     short loc_180091DD7
0x180091dd0  mov     [rbp+var_28], 1680h
0x180091dd7  lea     rdx, [rbp+var_30]
0x180091ddb  lea     rcx, [rbp+var_30]
0x180091ddf  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091de4  jmp     short loc_180091E57
0x180091de6  lea     rcx, [rbp+var_30]
0x180091dea  mov     [rbp+var_28], 167Fh
0x180091df1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180091df6  mov     rdx, [rbp+arg_8]
0x180091dfa  test    rdx, rdx
0x180091dfd  jz      short loc_180091E57
0x180091dff  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091e06  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091e0d  mov     [rbp+var_8], 0C00000E5h
0x180091e14  mov     [rbp+var_18], rcx
0x180091e18  test    rax, rax
0x180091e1b  jnz     short loc_180091E36
0x180091e1d  mov     [rbp+var_10], 401h
0x180091e24  lea     rdx, [rbp+var_18]
0x180091e28  lea     rcx, [rbp+var_18]
0x180091e2c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091e31  mov     ecx, [rbp+var_8]
0x180091e34  jmp     short loc_180091E43
0x180091e36  mov     ecx, [rax]
0x180091e38  mov     rax, [rax+20h]
0x180091e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e41  xor     ecx, ecx; dwExceptionCode
0x180091e43  test    ecx, ecx
0x180091e45  jns     short loc_180091E57
0x180091e47  xor     r9d, r9d; lpArguments
0x180091e4a  xor     r8d, r8d; nNumberOfArguments
0x180091e4d  lea     edx, [r9+1]; dwExceptionFlags
0x180091e51  call    cs:__imp_RaiseException
0x180091e57  mov     ebx, [rbp+var_20]
0x180091e5a  mov     eax, ebx
0x180091e5c  mov     rbx, [rsp+50h+arg_0]
0x180091e64  add     rsp, 50h
0x180091e68  pop     r14
0x180091e6a  pop     r12
0x180091e6c  pop     rdi
0x180091e6d  pop     rsi
0x180091e6e  pop     rbp
0x180091e6f  retn
```
