# CCategoryMembershipDataSection::get_Count(ulong *)

- ea: `0x18008f780`
- end: `0x18008f9e0`
- name: `?get_Count@CCategoryMembershipDataSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCategoryMembershipDataSection *__hidden this, unsigned int *)`
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
- `0x18008f780`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f83d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f911`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f83d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f911`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f8c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f9c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f8c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f9c1`

## string_xrefs

- `0x18008f878`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f976`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f79a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCategoryMembershipDataSection::get_Count(CCategoryMembershipDataSection *this, unsigned int *a2)
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
    v16 = 5463;
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
    v16 = 5464;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5465;
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
        (const char *)0x1565,
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
        (const char *)0x1561,
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
0x18008f780  mov     [rsp-28h+arg_0], rbx
0x18008f785  push    rbp
0x18008f786  push    rsi
0x18008f787  push    rdi
0x18008f788  push    r12
0x18008f78a  push    r14
0x18008f78c  mov     rbp, rsp
0x18008f78f  sub     rsp, 50h
0x18008f793  mov     [rbp+var_20], 8007054Fh
0x18008f79a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f7a1  mov     [rbp+var_30], r12
0x18008f7a5  mov     rdi, rdx
0x18008f7a8  mov     [rbp+arg_8], 0
0x18008f7b0  mov     rbx, rcx
0x18008f7b3  mov     [rbp+arg_10], 0
0x18008f7bb  test    rdx, rdx
0x18008f7be  jz      loc_18008F956
0x18008f7c4  mov     dword ptr [rdx], 0
0x18008f7ca  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008f7d1  test    rdx, rdx
0x18008f7d4  jz      loc_18008F940
0x18008f7da  mov     rcx, [rcx+18h]
0x18008f7de  call    RtlIsTypeSafeHandleValid
0x18008f7e3  test    al, al
0x18008f7e5  jz      loc_18008F940
0x18008f7eb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008f7f2  test    rdx, rdx
0x18008f7f5  jz      loc_18008F937
0x18008f7fb  mov     rcx, [rbx+20h]
0x18008f7ff  call    RtlIsTypeSafeHandleValid
0x18008f804  test    al, al
0x18008f806  jz      loc_18008F937
0x18008f80c  cmp     byte ptr [rbx+2Ch], 0
0x18008f810  jz      short loc_18008F81E
0x18008f812  mov     eax, [rbx+28h]
0x18008f815  xor     ebx, ebx
0x18008f817  mov     [rdi], eax
0x18008f819  jmp     loc_18008F9CA
0x18008f81e  mov     rcx, [rbx+20h]
0x18008f822  lea     rdx, [rbp+arg_8]
0x18008f826  call    CdfEnumerateUlongTable
0x18008f82b  mov     esi, eax
0x18008f82d  test    eax, eax
0x18008f82f  jns     loc_18008F8D2
0x18008f835  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008f83b  jnz     short loc_18008F843
0x18008f83d  call    cs:__imp_DebugBreak
0x18008f843  mov     r9d, esi; int
0x18008f846  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f84d  mov     r8d, 1561h; char *
0x18008f853  mov     rdx, r12; char *
0x18008f856  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f85b  mov     ecx, esi; this
0x18008f85d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008f862  mov     ebx, eax
0x18008f864  mov     rdx, [rbp+arg_8]
0x18008f868  test    rdx, rdx
0x18008f86b  jz      loc_18008F9CA
0x18008f871  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f878  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f87f  mov     [rbp+var_20], 0C00000E5h
0x18008f886  mov     [rbp+var_30], rcx
0x18008f88a  test    rax, rax
0x18008f88d  jnz     short loc_18008F8A8
0x18008f88f  mov     [rbp+var_28], 401h
0x18008f896  lea     rdx, [rbp+var_30]
0x18008f89a  lea     rcx, [rbp+var_30]
0x18008f89e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f8a3  mov     ecx, [rbp+var_20]
0x18008f8a6  jmp     short loc_18008F8B5
0x18008f8a8  mov     ecx, [rax]
0x18008f8aa  mov     rax, [rax+20h]
0x18008f8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f8b3  xor     ecx, ecx; dwExceptionCode
0x18008f8b5  test    ecx, ecx
0x18008f8b7  jns     loc_18008F9CA
0x18008f8bd  xor     r9d, r9d; lpArguments
0x18008f8c0  xor     r8d, r8d; nNumberOfArguments
0x18008f8c3  lea     edx, [r9+1]; dwExceptionFlags
0x18008f8c7  call    cs:__imp_RaiseException
0x18008f8cd  jmp     loc_18008F9CA
0x18008f8d2  xor     esi, esi
0x18008f8d4  mov     rcx, [rbp+arg_8]
0x18008f8d8  lea     r8, [rbp+arg_10]
0x18008f8dc  mov     edx, 1
0x18008f8e1  call    CdfMoveUlongTableEnumeratorPosition
0x18008f8e6  mov     r14d, eax
0x18008f8e9  test    eax, eax
0x18008f8eb  js      short loc_18008F908
0x18008f8ed  cmp     [rbp+arg_10], 1
0x18008f8f2  jnz     short loc_18008F8F8
0x18008f8f4  inc     esi
0x18008f8f6  jmp     short loc_18008F8D4
0x18008f8f8  mov     [rbx+28h], esi
0x18008f8fb  mov     byte ptr [rbx+2Ch], 1
0x18008f8ff  xor     ebx, ebx
0x18008f901  mov     [rdi], esi
0x18008f903  jmp     loc_18008F864
0x18008f908  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008f90f  jnz     short loc_18008F917
0x18008f911  call    cs:__imp_DebugBreak
0x18008f917  mov     r9d, r14d; int
0x18008f91a  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f921  mov     r8d, 1565h; char *
0x18008f927  mov     rdx, r12; char *
0x18008f92a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f92f  mov     ecx, r14d
0x18008f932  jmp     loc_18008F85D
0x18008f937  mov     [rbp+var_28], 1559h
0x18008f93e  jmp     short loc_18008F947
0x18008f940  mov     [rbp+var_28], 1558h
0x18008f947  lea     rdx, [rbp+var_30]
0x18008f94b  lea     rcx, [rbp+var_30]
0x18008f94f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f954  jmp     short loc_18008F9C7
0x18008f956  lea     rcx, [rbp+var_30]
0x18008f95a  mov     [rbp+var_28], 1557h
0x18008f961  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008f966  mov     rdx, [rbp+arg_8]
0x18008f96a  test    rdx, rdx
0x18008f96d  jz      short loc_18008F9C7
0x18008f96f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f976  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f97d  mov     [rbp+var_8], 0C00000E5h
0x18008f984  mov     [rbp+var_18], rcx
0x18008f988  test    rax, rax
0x18008f98b  jnz     short loc_18008F9A6
0x18008f98d  mov     [rbp+var_10], 401h
0x18008f994  lea     rdx, [rbp+var_18]
0x18008f998  lea     rcx, [rbp+var_18]
0x18008f99c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f9a1  mov     ecx, [rbp+var_8]
0x18008f9a4  jmp     short loc_18008F9B3
0x18008f9a6  mov     ecx, [rax]
0x18008f9a8  mov     rax, [rax+20h]
0x18008f9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f9b1  xor     ecx, ecx; dwExceptionCode
0x18008f9b3  test    ecx, ecx
0x18008f9b5  jns     short loc_18008F9C7
0x18008f9b7  xor     r9d, r9d; lpArguments
0x18008f9ba  xor     r8d, r8d; nNumberOfArguments
0x18008f9bd  lea     edx, [r9+1]; dwExceptionFlags
0x18008f9c1  call    cs:__imp_RaiseException
0x18008f9c7  mov     ebx, [rbp+var_20]
0x18008f9ca  mov     eax, ebx
0x18008f9cc  mov     rbx, [rsp+50h+arg_0]
0x18008f9d4  add     rsp, 50h
0x18008f9d8  pop     r14
0x18008f9da  pop     r12
0x18008f9dc  pop     rdi
0x18008f9dd  pop     rsi
0x18008f9de  pop     rbp
0x18008f9df  retn
```
