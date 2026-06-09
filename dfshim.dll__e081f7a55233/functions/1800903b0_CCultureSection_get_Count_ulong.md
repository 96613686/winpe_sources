# CCultureSection::get_Count(ulong *)

- ea: `0x1800903b0`
- end: `0x180090610`
- name: `?get_Count@CCultureSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCultureSection *__hidden this, unsigned int *)`
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
- `0x1800903b0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009046d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090541`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009046d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180090541`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800904f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800905f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800904f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800905f1`

## string_xrefs

- `0x1800904a8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800905a6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800903ca`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCultureSection::get_Count(CCultureSection *this, unsigned int *a2)
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
    v16 = 6524;
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
    v16 = 6525;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6526;
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
        (const char *)0x198A,
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
        (const char *)0x1986,
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
0x1800903b0  mov     [rsp-28h+arg_0], rbx
0x1800903b5  push    rbp
0x1800903b6  push    rsi
0x1800903b7  push    rdi
0x1800903b8  push    r12
0x1800903ba  push    r14
0x1800903bc  mov     rbp, rsp
0x1800903bf  sub     rsp, 50h
0x1800903c3  mov     [rbp+var_20], 8007054Fh
0x1800903ca  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800903d1  mov     [rbp+var_30], r12
0x1800903d5  mov     rdi, rdx
0x1800903d8  mov     [rbp+arg_8], 0
0x1800903e0  mov     rbx, rcx
0x1800903e3  mov     [rbp+arg_10], 0
0x1800903eb  test    rdx, rdx
0x1800903ee  jz      loc_180090586
0x1800903f4  mov     dword ptr [rdx], 0
0x1800903fa  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180090401  test    rdx, rdx
0x180090404  jz      loc_180090570
0x18009040a  mov     rcx, [rcx+18h]
0x18009040e  call    RtlIsTypeSafeHandleValid
0x180090413  test    al, al
0x180090415  jz      loc_180090570
0x18009041b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180090422  test    rdx, rdx
0x180090425  jz      loc_180090567
0x18009042b  mov     rcx, [rbx+20h]
0x18009042f  call    RtlIsTypeSafeHandleValid
0x180090434  test    al, al
0x180090436  jz      loc_180090567
0x18009043c  cmp     byte ptr [rbx+2Ch], 0
0x180090440  jz      short loc_18009044E
0x180090442  mov     eax, [rbx+28h]
0x180090445  xor     ebx, ebx
0x180090447  mov     [rdi], eax
0x180090449  jmp     loc_1800905FA
0x18009044e  mov     rcx, [rbx+20h]
0x180090452  lea     rdx, [rbp+arg_8]
0x180090456  call    CdfEnumerateStringTable
0x18009045b  mov     esi, eax
0x18009045d  test    eax, eax
0x18009045f  jns     loc_180090502
0x180090465  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18009046b  jnz     short loc_180090473
0x18009046d  call    cs:__imp_DebugBreak
0x180090473  mov     r9d, esi; int
0x180090476  lea     rcx, aStatusPropagat; "Status propagated"
0x18009047d  mov     r8d, 1986h; char *
0x180090483  mov     rdx, r12; char *
0x180090486  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009048b  mov     ecx, esi; this
0x18009048d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180090492  mov     ebx, eax
0x180090494  mov     rdx, [rbp+arg_8]
0x180090498  test    rdx, rdx
0x18009049b  jz      loc_1800905FA
0x1800904a1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800904a8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800904af  mov     [rbp+var_20], 0C00000E5h
0x1800904b6  mov     [rbp+var_30], rcx
0x1800904ba  test    rax, rax
0x1800904bd  jnz     short loc_1800904D8
0x1800904bf  mov     [rbp+var_28], 401h
0x1800904c6  lea     rdx, [rbp+var_30]
0x1800904ca  lea     rcx, [rbp+var_30]
0x1800904ce  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800904d3  mov     ecx, [rbp+var_20]
0x1800904d6  jmp     short loc_1800904E5
0x1800904d8  mov     ecx, [rax]
0x1800904da  mov     rax, [rax+20h]
0x1800904de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904e3  xor     ecx, ecx; dwExceptionCode
0x1800904e5  test    ecx, ecx
0x1800904e7  jns     loc_1800905FA
0x1800904ed  xor     r9d, r9d; lpArguments
0x1800904f0  xor     r8d, r8d; nNumberOfArguments
0x1800904f3  lea     edx, [r9+1]; dwExceptionFlags
0x1800904f7  call    cs:__imp_RaiseException
0x1800904fd  jmp     loc_1800905FA
0x180090502  xor     esi, esi
0x180090504  mov     rcx, [rbp+arg_8]
0x180090508  lea     r8, [rbp+arg_10]
0x18009050c  mov     edx, 1
0x180090511  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180090516  mov     r14d, eax
0x180090519  test    eax, eax
0x18009051b  js      short loc_180090538
0x18009051d  cmp     [rbp+arg_10], 1
0x180090522  jnz     short loc_180090528
0x180090524  inc     esi
0x180090526  jmp     short loc_180090504
0x180090528  mov     [rbx+28h], esi
0x18009052b  mov     byte ptr [rbx+2Ch], 1
0x18009052f  xor     ebx, ebx
0x180090531  mov     [rdi], esi
0x180090533  jmp     loc_180090494
0x180090538  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009053f  jnz     short loc_180090547
0x180090541  call    cs:__imp_DebugBreak
0x180090547  mov     r9d, r14d; int
0x18009054a  lea     rcx, aStatusPropagat; "Status propagated"
0x180090551  mov     r8d, 198Ah; char *
0x180090557  mov     rdx, r12; char *
0x18009055a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009055f  mov     ecx, r14d
0x180090562  jmp     loc_18009048D
0x180090567  mov     [rbp+var_28], 197Eh
0x18009056e  jmp     short loc_180090577
0x180090570  mov     [rbp+var_28], 197Dh
0x180090577  lea     rdx, [rbp+var_30]
0x18009057b  lea     rcx, [rbp+var_30]
0x18009057f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090584  jmp     short loc_1800905F7
0x180090586  lea     rcx, [rbp+var_30]
0x18009058a  mov     [rbp+var_28], 197Ch
0x180090591  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180090596  mov     rdx, [rbp+arg_8]
0x18009059a  test    rdx, rdx
0x18009059d  jz      short loc_1800905F7
0x18009059f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800905a6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800905ad  mov     [rbp+var_8], 0C00000E5h
0x1800905b4  mov     [rbp+var_18], rcx
0x1800905b8  test    rax, rax
0x1800905bb  jnz     short loc_1800905D6
0x1800905bd  mov     [rbp+var_10], 401h
0x1800905c4  lea     rdx, [rbp+var_18]
0x1800905c8  lea     rcx, [rbp+var_18]
0x1800905cc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800905d1  mov     ecx, [rbp+var_8]
0x1800905d4  jmp     short loc_1800905E3
0x1800905d6  mov     ecx, [rax]
0x1800905d8  mov     rax, [rax+20h]
0x1800905dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905e1  xor     ecx, ecx; dwExceptionCode
0x1800905e3  test    ecx, ecx
0x1800905e5  jns     short loc_1800905F7
0x1800905e7  xor     r9d, r9d; lpArguments
0x1800905ea  xor     r8d, r8d; nNumberOfArguments
0x1800905ed  lea     edx, [r9+1]; dwExceptionFlags
0x1800905f1  call    cs:__imp_RaiseException
0x1800905f7  mov     ebx, [rbp+var_20]
0x1800905fa  mov     eax, ebx
0x1800905fc  mov     rbx, [rsp+50h+arg_0]
0x180090604  add     rsp, 50h
0x180090608  pop     r14
0x18009060a  pop     r12
0x18009060c  pop     rdi
0x18009060d  pop     rsi
0x18009060e  pop     rbp
0x18009060f  retn
```
