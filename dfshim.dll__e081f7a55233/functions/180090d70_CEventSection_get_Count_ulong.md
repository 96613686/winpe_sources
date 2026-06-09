# CEventSection::get_Count(ulong *)

- ea: `0x180090d70`
- end: `0x180090fd0`
- name: `?get_Count@CEventSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CEventSection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180048d70`
- `0x180048f4c`
- `0x18004f2dc`
- `0x180090d70`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090e2d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090f01`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090e2d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090f01`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090eb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090fb1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090eb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090fb1`

## string_xrefs

- `0x180090e68`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090f66`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090d8a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventSection::get_Count(CEventSection *this, unsigned int *a2)
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
    v16 = 7439;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
    v16 = 7440;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 7441;
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
    v6 = CdfEnumerateUlongTable(*((_QWORD *)this + 4), &v21);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v12 = CdfMoveUlongTableEnumeratorPosition(v21, 1, &v22);
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
        (const char *)0x1D1D,
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
        (const char *)0x1D19,
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
0x180090d70  mov     [rsp-28h+arg_0], rbx
0x180090d75  push    rbp
0x180090d76  push    rsi
0x180090d77  push    rdi
0x180090d78  push    r12
0x180090d7a  push    r14
0x180090d7c  mov     rbp, rsp
0x180090d7f  sub     rsp, 50h
0x180090d83  mov     [rbp+var_20], 8007054Fh
0x180090d8a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090d91  mov     [rbp+var_30], r12
0x180090d95  mov     rdi, rdx
0x180090d98  mov     [rbp+arg_8], 0
0x180090da0  mov     rbx, rcx
0x180090da3  mov     [rbp+arg_10], 0
0x180090dab  test    rdx, rdx
0x180090dae  jz      loc_180090F46
0x180090db4  mov     dword ptr [rdx], 0
0x180090dba  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180090dc1  test    rdx, rdx
0x180090dc4  jz      loc_180090F30
0x180090dca  mov     rcx, [rcx+18h]
0x180090dce  call    RtlIsTypeSafeHandleValid
0x180090dd3  test    al, al
0x180090dd5  jz      loc_180090F30
0x180090ddb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180090de2  test    rdx, rdx
0x180090de5  jz      loc_180090F27
0x180090deb  mov     rcx, [rbx+20h]
0x180090def  call    RtlIsTypeSafeHandleValid
0x180090df4  test    al, al
0x180090df6  jz      loc_180090F27
0x180090dfc  cmp     byte ptr [rbx+2Ch], 0
0x180090e00  jz      short loc_180090E0E
0x180090e02  mov     eax, [rbx+28h]
0x180090e05  xor     ebx, ebx
0x180090e07  mov     [rdi], eax
0x180090e09  jmp     loc_180090FBA
0x180090e0e  mov     rcx, [rbx+20h]
0x180090e12  lea     rdx, [rbp+arg_8]
0x180090e16  call    CdfEnumerateUlongTable
0x180090e1b  mov     esi, eax
0x180090e1d  test    eax, eax
0x180090e1f  jns     loc_180090EC2
0x180090e25  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180090e2b  jnz     short loc_180090E33
0x180090e2d  call    cs:__imp_DebugBreak
0x180090e33  mov     r9d, esi; int
0x180090e36  lea     rcx, aStatusPropagat; "Status propagated"
0x180090e3d  mov     r8d, 1D19h; char *
0x180090e43  mov     rdx, r12; char *
0x180090e46  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180090e4b  mov     ecx, esi; this
0x180090e4d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180090e52  mov     ebx, eax
0x180090e54  mov     rdx, [rbp+arg_8]
0x180090e58  test    rdx, rdx
0x180090e5b  jz      loc_180090FBA
0x180090e61  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090e68  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090e6f  mov     [rbp+var_20], 0C00000E5h
0x180090e76  mov     [rbp+var_30], rcx
0x180090e7a  test    rax, rax
0x180090e7d  jnz     short loc_180090E98
0x180090e7f  mov     [rbp+var_28], 401h
0x180090e86  lea     rdx, [rbp+var_30]
0x180090e8a  lea     rcx, [rbp+var_30]
0x180090e8e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090e93  mov     ecx, [rbp+var_20]
0x180090e96  jmp     short loc_180090EA5
0x180090e98  mov     ecx, [rax]
0x180090e9a  mov     rax, [rax+20h]
0x180090e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090ea3  xor     ecx, ecx; dwExceptionCode
0x180090ea5  test    ecx, ecx
0x180090ea7  jns     loc_180090FBA
0x180090ead  xor     r9d, r9d; lpArguments
0x180090eb0  xor     r8d, r8d; nNumberOfArguments
0x180090eb3  lea     edx, [r9+1]; dwExceptionFlags
0x180090eb7  call    cs:__imp_RaiseException
0x180090ebd  jmp     loc_180090FBA
0x180090ec2  xor     esi, esi
0x180090ec4  mov     rcx, [rbp+arg_8]
0x180090ec8  lea     r8, [rbp+arg_10]
0x180090ecc  mov     edx, 1
0x180090ed1  call    CdfMoveUlongTableEnumeratorPosition
0x180090ed6  mov     r14d, eax
0x180090ed9  test    eax, eax
0x180090edb  js      short loc_180090EF8
0x180090edd  cmp     [rbp+arg_10], 1
0x180090ee2  jnz     short loc_180090EE8
0x180090ee4  inc     esi
0x180090ee6  jmp     short loc_180090EC4
0x180090ee8  mov     [rbx+28h], esi
0x180090eeb  mov     byte ptr [rbx+2Ch], 1
0x180090eef  xor     ebx, ebx
0x180090ef1  mov     [rdi], esi
0x180090ef3  jmp     loc_180090E54
0x180090ef8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x180090eff  jnz     short loc_180090F07
0x180090f01  call    cs:__imp_DebugBreak
0x180090f07  mov     r9d, r14d; int
0x180090f0a  lea     rcx, aStatusPropagat; "Status propagated"
0x180090f11  mov     r8d, 1D1Dh; char *
0x180090f17  mov     rdx, r12; char *
0x180090f1a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180090f1f  mov     ecx, r14d
0x180090f22  jmp     loc_180090E4D
0x180090f27  mov     [rbp+var_28], 1D11h
0x180090f2e  jmp     short loc_180090F37
0x180090f30  mov     [rbp+var_28], 1D10h
0x180090f37  lea     rdx, [rbp+var_30]
0x180090f3b  lea     rcx, [rbp+var_30]
0x180090f3f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090f44  jmp     short loc_180090FB7
0x180090f46  lea     rcx, [rbp+var_30]
0x180090f4a  mov     [rbp+var_28], 1D0Fh
0x180090f51  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180090f56  mov     rdx, [rbp+arg_8]
0x180090f5a  test    rdx, rdx
0x180090f5d  jz      short loc_180090FB7
0x180090f5f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090f66  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090f6d  mov     [rbp+var_8], 0C00000E5h
0x180090f74  mov     [rbp+var_18], rcx
0x180090f78  test    rax, rax
0x180090f7b  jnz     short loc_180090F96
0x180090f7d  mov     [rbp+var_10], 401h
0x180090f84  lea     rdx, [rbp+var_18]
0x180090f88  lea     rcx, [rbp+var_18]
0x180090f8c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090f91  mov     ecx, [rbp+var_8]
0x180090f94  jmp     short loc_180090FA3
0x180090f96  mov     ecx, [rax]
0x180090f98  mov     rax, [rax+20h]
0x180090f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090fa1  xor     ecx, ecx; dwExceptionCode
0x180090fa3  test    ecx, ecx
0x180090fa5  jns     short loc_180090FB7
0x180090fa7  xor     r9d, r9d; lpArguments
0x180090faa  xor     r8d, r8d; nNumberOfArguments
0x180090fad  lea     edx, [r9+1]; dwExceptionFlags
0x180090fb1  call    cs:__imp_RaiseException
0x180090fb7  mov     ebx, [rbp+var_20]
0x180090fba  mov     eax, ebx
0x180090fbc  mov     rbx, [rsp+50h+arg_0]
0x180090fc4  add     rsp, 50h
0x180090fc8  pop     r14
0x180090fca  pop     r12
0x180090fcc  pop     rdi
0x180090fcd  pop     rsi
0x180090fce  pop     rbp
0x180090fcf  retn
```
