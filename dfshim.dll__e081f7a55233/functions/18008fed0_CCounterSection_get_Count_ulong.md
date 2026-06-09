# CCounterSection::get_Count(ulong *)

- ea: `0x18008fed0`
- end: `0x180090130`
- name: `?get_Count@CCounterSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCounterSection *__hidden this, unsigned int *)`
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
- `0x180073124`
- `0x18008fed0`
- `0x1800d537c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ff8d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090061`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008ff8d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090061`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090017`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090111`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090017`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090111`

## string_xrefs

- `0x18008ffc8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800900c6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008feea`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCounterSection::get_Count(CCounterSection *this, unsigned int *a2)
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
    v16 = 8510;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
    v16 = 8511;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 8512;
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
    v6 = CdfEnumerateGuidTable(*((_QWORD *)this + 4), &v21);
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
        (const char *)0x214C,
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
        (const char *)0x2148,
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
0x18008fed0  mov     [rsp-28h+arg_0], rbx
0x18008fed5  push    rbp
0x18008fed6  push    rsi
0x18008fed7  push    rdi
0x18008fed8  push    r12
0x18008feda  push    r14
0x18008fedc  mov     rbp, rsp
0x18008fedf  sub     rsp, 50h
0x18008fee3  mov     [rbp+var_20], 8007054Fh
0x18008feea  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fef1  mov     [rbp+var_30], r12
0x18008fef5  mov     rdi, rdx
0x18008fef8  mov     [rbp+arg_8], 0
0x18008ff00  mov     rbx, rcx
0x18008ff03  mov     [rbp+arg_10], 0
0x18008ff0b  test    rdx, rdx
0x18008ff0e  jz      loc_1800900A6
0x18008ff14  mov     dword ptr [rdx], 0
0x18008ff1a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008ff21  test    rdx, rdx
0x18008ff24  jz      loc_180090090
0x18008ff2a  mov     rcx, [rcx+18h]
0x18008ff2e  call    RtlIsTypeSafeHandleValid
0x18008ff33  test    al, al
0x18008ff35  jz      loc_180090090
0x18008ff3b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008ff42  test    rdx, rdx
0x18008ff45  jz      loc_180090087
0x18008ff4b  mov     rcx, [rbx+20h]
0x18008ff4f  call    RtlIsTypeSafeHandleValid
0x18008ff54  test    al, al
0x18008ff56  jz      loc_180090087
0x18008ff5c  cmp     byte ptr [rbx+2Ch], 0
0x18008ff60  jz      short loc_18008FF6E
0x18008ff62  mov     eax, [rbx+28h]
0x18008ff65  xor     ebx, ebx
0x18008ff67  mov     [rdi], eax
0x18008ff69  jmp     loc_18009011A
0x18008ff6e  mov     rcx, [rbx+20h]
0x18008ff72  lea     rdx, [rbp+arg_8]
0x18008ff76  call    CdfEnumerateGuidTable
0x18008ff7b  mov     esi, eax
0x18008ff7d  test    eax, eax
0x18008ff7f  jns     loc_180090022
0x18008ff85  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008ff8b  jnz     short loc_18008FF93
0x18008ff8d  call    cs:__imp_DebugBreak
0x18008ff93  mov     r9d, esi; int
0x18008ff96  lea     rcx, aStatusPropagat; "Status propagated"
0x18008ff9d  mov     r8d, 2148h; char *
0x18008ffa3  mov     rdx, r12; char *
0x18008ffa6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008ffab  mov     ecx, esi; this
0x18008ffad  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008ffb2  mov     ebx, eax
0x18008ffb4  mov     rdx, [rbp+arg_8]
0x18008ffb8  test    rdx, rdx
0x18008ffbb  jz      loc_18009011A
0x18008ffc1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008ffc8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ffcf  mov     [rbp+var_20], 0C00000E5h
0x18008ffd6  mov     [rbp+var_30], rcx
0x18008ffda  test    rax, rax
0x18008ffdd  jnz     short loc_18008FFF8
0x18008ffdf  mov     [rbp+var_28], 401h
0x18008ffe6  lea     rdx, [rbp+var_30]
0x18008ffea  lea     rcx, [rbp+var_30]
0x18008ffee  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fff3  mov     ecx, [rbp+var_20]
0x18008fff6  jmp     short loc_180090005
0x18008fff8  mov     ecx, [rax]
0x18008fffa  mov     rax, [rax+20h]
0x18008fffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090003  xor     ecx, ecx; dwExceptionCode
0x180090005  test    ecx, ecx
0x180090007  jns     loc_18009011A
0x18009000d  xor     r9d, r9d; lpArguments
0x180090010  xor     r8d, r8d; nNumberOfArguments
0x180090013  lea     edx, [r9+1]; dwExceptionFlags
0x180090017  call    cs:__imp_RaiseException
0x18009001d  jmp     loc_18009011A
0x180090022  xor     esi, esi
0x180090024  mov     rcx, [rbp+arg_8]
0x180090028  lea     r8, [rbp+arg_10]
0x18009002c  mov     edx, 1
0x180090031  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_GUID_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,__int64,__int64 &)
0x180090036  mov     r14d, eax
0x180090039  test    eax, eax
0x18009003b  js      short loc_180090058
0x18009003d  cmp     [rbp+arg_10], 1
0x180090042  jnz     short loc_180090048
0x180090044  inc     esi
0x180090046  jmp     short loc_180090024
0x180090048  mov     [rbx+28h], esi
0x18009004b  mov     byte ptr [rbx+2Ch], 1
0x18009004f  xor     ebx, ebx
0x180090051  mov     [rdi], esi
0x180090053  jmp     loc_18008FFB4
0x180090058  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009005f  jnz     short loc_180090067
0x180090061  call    cs:__imp_DebugBreak
0x180090067  mov     r9d, r14d; int
0x18009006a  lea     rcx, aStatusPropagat; "Status propagated"
0x180090071  mov     r8d, 214Ch; char *
0x180090077  mov     rdx, r12; char *
0x18009007a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009007f  mov     ecx, r14d
0x180090082  jmp     loc_18008FFAD
0x180090087  mov     [rbp+var_28], 2140h
0x18009008e  jmp     short loc_180090097
0x180090090  mov     [rbp+var_28], 213Fh
0x180090097  lea     rdx, [rbp+var_30]
0x18009009b  lea     rcx, [rbp+var_30]
0x18009009f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800900a4  jmp     short loc_180090117
0x1800900a6  lea     rcx, [rbp+var_30]
0x1800900aa  mov     [rbp+var_28], 213Eh
0x1800900b1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800900b6  mov     rdx, [rbp+arg_8]
0x1800900ba  test    rdx, rdx
0x1800900bd  jz      short loc_180090117
0x1800900bf  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800900c6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800900cd  mov     [rbp+var_8], 0C00000E5h
0x1800900d4  mov     [rbp+var_18], rcx
0x1800900d8  test    rax, rax
0x1800900db  jnz     short loc_1800900F6
0x1800900dd  mov     [rbp+var_10], 401h
0x1800900e4  lea     rdx, [rbp+var_18]
0x1800900e8  lea     rcx, [rbp+var_18]
0x1800900ec  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800900f1  mov     ecx, [rbp+var_8]
0x1800900f4  jmp     short loc_180090103
0x1800900f6  mov     ecx, [rax]
0x1800900f8  mov     rax, [rax+20h]
0x1800900fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090101  xor     ecx, ecx; dwExceptionCode
0x180090103  test    ecx, ecx
0x180090105  jns     short loc_180090117
0x180090107  xor     r9d, r9d; lpArguments
0x18009010a  xor     r8d, r8d; nNumberOfArguments
0x18009010d  lea     edx, [r9+1]; dwExceptionFlags
0x180090111  call    cs:__imp_RaiseException
0x180090117  mov     ebx, [rbp+var_20]
0x18009011a  mov     eax, ebx
0x18009011c  mov     rbx, [rsp+50h+arg_0]
0x180090124  add     rsp, 50h
0x180090128  pop     r14
0x18009012a  pop     r12
0x18009012c  pop     rdi
0x18009012d  pop     rsi
0x18009012e  pop     rbp
0x18009012f  retn
```
