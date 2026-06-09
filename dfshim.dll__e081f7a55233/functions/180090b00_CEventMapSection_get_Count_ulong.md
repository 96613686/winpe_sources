# CEventMapSection::get_Count(ulong *)

- ea: `0x180090b00`
- end: `0x180090d60`
- name: `?get_Count@CEventMapSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CEventMapSection *__hidden this, unsigned int *)`
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
- `0x180090b00`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090bbd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090c91`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090bbd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090c91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090c47`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090d41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090c47`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090d41`

## string_xrefs

- `0x180090bf8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090cf6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090b1a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventMapSection::get_Count(CEventMapSection *this, unsigned int *a2)
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
    v16 = 7588;
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
    v16 = 7589;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 7590;
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
        (const char *)0x1DB2,
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
        (const char *)0x1DAE,
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
0x180090b00  mov     [rsp-28h+arg_0], rbx
0x180090b05  push    rbp
0x180090b06  push    rsi
0x180090b07  push    rdi
0x180090b08  push    r12
0x180090b0a  push    r14
0x180090b0c  mov     rbp, rsp
0x180090b0f  sub     rsp, 50h
0x180090b13  mov     [rbp+var_20], 8007054Fh
0x180090b1a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090b21  mov     [rbp+var_30], r12
0x180090b25  mov     rdi, rdx
0x180090b28  mov     [rbp+arg_8], 0
0x180090b30  mov     rbx, rcx
0x180090b33  mov     [rbp+arg_10], 0
0x180090b3b  test    rdx, rdx
0x180090b3e  jz      loc_180090CD6
0x180090b44  mov     dword ptr [rdx], 0
0x180090b4a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180090b51  test    rdx, rdx
0x180090b54  jz      loc_180090CC0
0x180090b5a  mov     rcx, [rcx+18h]
0x180090b5e  call    RtlIsTypeSafeHandleValid
0x180090b63  test    al, al
0x180090b65  jz      loc_180090CC0
0x180090b6b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180090b72  test    rdx, rdx
0x180090b75  jz      loc_180090CB7
0x180090b7b  mov     rcx, [rbx+20h]
0x180090b7f  call    RtlIsTypeSafeHandleValid
0x180090b84  test    al, al
0x180090b86  jz      loc_180090CB7
0x180090b8c  cmp     byte ptr [rbx+2Ch], 0
0x180090b90  jz      short loc_180090B9E
0x180090b92  mov     eax, [rbx+28h]
0x180090b95  xor     ebx, ebx
0x180090b97  mov     [rdi], eax
0x180090b99  jmp     loc_180090D4A
0x180090b9e  mov     rcx, [rbx+20h]
0x180090ba2  lea     rdx, [rbp+arg_8]
0x180090ba6  call    CdfEnumerateStringTable
0x180090bab  mov     esi, eax
0x180090bad  test    eax, eax
0x180090baf  jns     loc_180090C52
0x180090bb5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180090bbb  jnz     short loc_180090BC3
0x180090bbd  call    cs:__imp_DebugBreak
0x180090bc3  mov     r9d, esi; int
0x180090bc6  lea     rcx, aStatusPropagat; "Status propagated"
0x180090bcd  mov     r8d, 1DAEh; char *
0x180090bd3  mov     rdx, r12; char *
0x180090bd6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180090bdb  mov     ecx, esi; this
0x180090bdd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180090be2  mov     ebx, eax
0x180090be4  mov     rdx, [rbp+arg_8]
0x180090be8  test    rdx, rdx
0x180090beb  jz      loc_180090D4A
0x180090bf1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090bf8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090bff  mov     [rbp+var_20], 0C00000E5h
0x180090c06  mov     [rbp+var_30], rcx
0x180090c0a  test    rax, rax
0x180090c0d  jnz     short loc_180090C28
0x180090c0f  mov     [rbp+var_28], 401h
0x180090c16  lea     rdx, [rbp+var_30]
0x180090c1a  lea     rcx, [rbp+var_30]
0x180090c1e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090c23  mov     ecx, [rbp+var_20]
0x180090c26  jmp     short loc_180090C35
0x180090c28  mov     ecx, [rax]
0x180090c2a  mov     rax, [rax+20h]
0x180090c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090c33  xor     ecx, ecx; dwExceptionCode
0x180090c35  test    ecx, ecx
0x180090c37  jns     loc_180090D4A
0x180090c3d  xor     r9d, r9d; lpArguments
0x180090c40  xor     r8d, r8d; nNumberOfArguments
0x180090c43  lea     edx, [r9+1]; dwExceptionFlags
0x180090c47  call    cs:__imp_RaiseException
0x180090c4d  jmp     loc_180090D4A
0x180090c52  xor     esi, esi
0x180090c54  mov     rcx, [rbp+arg_8]
0x180090c58  lea     r8, [rbp+arg_10]
0x180090c5c  mov     edx, 1
0x180090c61  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180090c66  mov     r14d, eax
0x180090c69  test    eax, eax
0x180090c6b  js      short loc_180090C88
0x180090c6d  cmp     [rbp+arg_10], 1
0x180090c72  jnz     short loc_180090C78
0x180090c74  inc     esi
0x180090c76  jmp     short loc_180090C54
0x180090c78  mov     [rbx+28h], esi
0x180090c7b  mov     byte ptr [rbx+2Ch], 1
0x180090c7f  xor     ebx, ebx
0x180090c81  mov     [rdi], esi
0x180090c83  jmp     loc_180090BE4
0x180090c88  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x180090c8f  jnz     short loc_180090C97
0x180090c91  call    cs:__imp_DebugBreak
0x180090c97  mov     r9d, r14d; int
0x180090c9a  lea     rcx, aStatusPropagat; "Status propagated"
0x180090ca1  mov     r8d, 1DB2h; char *
0x180090ca7  mov     rdx, r12; char *
0x180090caa  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180090caf  mov     ecx, r14d
0x180090cb2  jmp     loc_180090BDD
0x180090cb7  mov     [rbp+var_28], 1DA6h
0x180090cbe  jmp     short loc_180090CC7
0x180090cc0  mov     [rbp+var_28], 1DA5h
0x180090cc7  lea     rdx, [rbp+var_30]
0x180090ccb  lea     rcx, [rbp+var_30]
0x180090ccf  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090cd4  jmp     short loc_180090D47
0x180090cd6  lea     rcx, [rbp+var_30]
0x180090cda  mov     [rbp+var_28], 1DA4h
0x180090ce1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180090ce6  mov     rdx, [rbp+arg_8]
0x180090cea  test    rdx, rdx
0x180090ced  jz      short loc_180090D47
0x180090cef  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090cf6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090cfd  mov     [rbp+var_8], 0C00000E5h
0x180090d04  mov     [rbp+var_18], rcx
0x180090d08  test    rax, rax
0x180090d0b  jnz     short loc_180090D26
0x180090d0d  mov     [rbp+var_10], 401h
0x180090d14  lea     rdx, [rbp+var_18]
0x180090d18  lea     rcx, [rbp+var_18]
0x180090d1c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090d21  mov     ecx, [rbp+var_8]
0x180090d24  jmp     short loc_180090D33
0x180090d26  mov     ecx, [rax]
0x180090d28  mov     rax, [rax+20h]
0x180090d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d31  xor     ecx, ecx; dwExceptionCode
0x180090d33  test    ecx, ecx
0x180090d35  jns     short loc_180090D47
0x180090d37  xor     r9d, r9d; lpArguments
0x180090d3a  xor     r8d, r8d; nNumberOfArguments
0x180090d3d  lea     edx, [r9+1]; dwExceptionFlags
0x180090d41  call    cs:__imp_RaiseException
0x180090d47  mov     ebx, [rbp+var_20]
0x180090d4a  mov     eax, ebx
0x180090d4c  mov     rbx, [rsp+50h+arg_0]
0x180090d54  add     rsp, 50h
0x180090d58  pop     r14
0x180090d5a  pop     r12
0x180090d5c  pop     rdi
0x180090d5d  pop     rsi
0x180090d5e  pop     rbp
0x180090d5f  retn
```
