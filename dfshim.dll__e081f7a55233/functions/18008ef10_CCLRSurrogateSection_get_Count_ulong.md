# CCLRSurrogateSection::get_Count(ulong *)

- ea: `0x18008ef10`
- end: `0x18008f170`
- name: `?get_Count@CCLRSurrogateSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCLRSurrogateSection *__hidden this, unsigned int *)`
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
- `0x18008ef10`
- `0x1800d537c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008efcd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f0a1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008efcd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f0a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f057`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f151`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f057`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f151`

## string_xrefs

- `0x18008f008`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f106`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008ef2a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCLRSurrogateSection::get_Count(CCLRSurrogateSection *this, unsigned int *a2)
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
    v16 = 5914;
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
    v16 = 5915;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5916;
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
        (const char *)0x1728,
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
        (const char *)0x1724,
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
0x18008ef10  mov     [rsp-28h+arg_0], rbx
0x18008ef15  push    rbp
0x18008ef16  push    rsi
0x18008ef17  push    rdi
0x18008ef18  push    r12
0x18008ef1a  push    r14
0x18008ef1c  mov     rbp, rsp
0x18008ef1f  sub     rsp, 50h
0x18008ef23  mov     [rbp+var_20], 8007054Fh
0x18008ef2a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008ef31  mov     [rbp+var_30], r12
0x18008ef35  mov     rdi, rdx
0x18008ef38  mov     [rbp+arg_8], 0
0x18008ef40  mov     rbx, rcx
0x18008ef43  mov     [rbp+arg_10], 0
0x18008ef4b  test    rdx, rdx
0x18008ef4e  jz      loc_18008F0E6
0x18008ef54  mov     dword ptr [rdx], 0
0x18008ef5a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008ef61  test    rdx, rdx
0x18008ef64  jz      loc_18008F0D0
0x18008ef6a  mov     rcx, [rcx+18h]
0x18008ef6e  call    RtlIsTypeSafeHandleValid
0x18008ef73  test    al, al
0x18008ef75  jz      loc_18008F0D0
0x18008ef7b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008ef82  test    rdx, rdx
0x18008ef85  jz      loc_18008F0C7
0x18008ef8b  mov     rcx, [rbx+20h]
0x18008ef8f  call    RtlIsTypeSafeHandleValid
0x18008ef94  test    al, al
0x18008ef96  jz      loc_18008F0C7
0x18008ef9c  cmp     byte ptr [rbx+2Ch], 0
0x18008efa0  jz      short loc_18008EFAE
0x18008efa2  mov     eax, [rbx+28h]
0x18008efa5  xor     ebx, ebx
0x18008efa7  mov     [rdi], eax
0x18008efa9  jmp     loc_18008F15A
0x18008efae  mov     rcx, [rbx+20h]
0x18008efb2  lea     rdx, [rbp+arg_8]
0x18008efb6  call    CdfEnumerateGuidTable
0x18008efbb  mov     esi, eax
0x18008efbd  test    eax, eax
0x18008efbf  jns     loc_18008F062
0x18008efc5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008efcb  jnz     short loc_18008EFD3
0x18008efcd  call    cs:__imp_DebugBreak
0x18008efd3  mov     r9d, esi; int
0x18008efd6  lea     rcx, aStatusPropagat; "Status propagated"
0x18008efdd  mov     r8d, 1724h; char *
0x18008efe3  mov     rdx, r12; char *
0x18008efe6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008efeb  mov     ecx, esi; this
0x18008efed  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008eff2  mov     ebx, eax
0x18008eff4  mov     rdx, [rbp+arg_8]
0x18008eff8  test    rdx, rdx
0x18008effb  jz      loc_18008F15A
0x18008f001  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f008  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f00f  mov     [rbp+var_20], 0C00000E5h
0x18008f016  mov     [rbp+var_30], rcx
0x18008f01a  test    rax, rax
0x18008f01d  jnz     short loc_18008F038
0x18008f01f  mov     [rbp+var_28], 401h
0x18008f026  lea     rdx, [rbp+var_30]
0x18008f02a  lea     rcx, [rbp+var_30]
0x18008f02e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f033  mov     ecx, [rbp+var_20]
0x18008f036  jmp     short loc_18008F045
0x18008f038  mov     ecx, [rax]
0x18008f03a  mov     rax, [rax+20h]
0x18008f03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f043  xor     ecx, ecx; dwExceptionCode
0x18008f045  test    ecx, ecx
0x18008f047  jns     loc_18008F15A
0x18008f04d  xor     r9d, r9d; lpArguments
0x18008f050  xor     r8d, r8d; nNumberOfArguments
0x18008f053  lea     edx, [r9+1]; dwExceptionFlags
0x18008f057  call    cs:__imp_RaiseException
0x18008f05d  jmp     loc_18008F15A
0x18008f062  xor     esi, esi
0x18008f064  mov     rcx, [rbp+arg_8]
0x18008f068  lea     r8, [rbp+arg_10]
0x18008f06c  mov     edx, 1
0x18008f071  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_GUID_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,__int64,__int64 &)
0x18008f076  mov     r14d, eax
0x18008f079  test    eax, eax
0x18008f07b  js      short loc_18008F098
0x18008f07d  cmp     [rbp+arg_10], 1
0x18008f082  jnz     short loc_18008F088
0x18008f084  inc     esi
0x18008f086  jmp     short loc_18008F064
0x18008f088  mov     [rbx+28h], esi
0x18008f08b  mov     byte ptr [rbx+2Ch], 1
0x18008f08f  xor     ebx, ebx
0x18008f091  mov     [rdi], esi
0x18008f093  jmp     loc_18008EFF4
0x18008f098  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008f09f  jnz     short loc_18008F0A7
0x18008f0a1  call    cs:__imp_DebugBreak
0x18008f0a7  mov     r9d, r14d; int
0x18008f0aa  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f0b1  mov     r8d, 1728h; char *
0x18008f0b7  mov     rdx, r12; char *
0x18008f0ba  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f0bf  mov     ecx, r14d
0x18008f0c2  jmp     loc_18008EFED
0x18008f0c7  mov     [rbp+var_28], 171Ch
0x18008f0ce  jmp     short loc_18008F0D7
0x18008f0d0  mov     [rbp+var_28], 171Bh
0x18008f0d7  lea     rdx, [rbp+var_30]
0x18008f0db  lea     rcx, [rbp+var_30]
0x18008f0df  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f0e4  jmp     short loc_18008F157
0x18008f0e6  lea     rcx, [rbp+var_30]
0x18008f0ea  mov     [rbp+var_28], 171Ah
0x18008f0f1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008f0f6  mov     rdx, [rbp+arg_8]
0x18008f0fa  test    rdx, rdx
0x18008f0fd  jz      short loc_18008F157
0x18008f0ff  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f106  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f10d  mov     [rbp+var_8], 0C00000E5h
0x18008f114  mov     [rbp+var_18], rcx
0x18008f118  test    rax, rax
0x18008f11b  jnz     short loc_18008F136
0x18008f11d  mov     [rbp+var_10], 401h
0x18008f124  lea     rdx, [rbp+var_18]
0x18008f128  lea     rcx, [rbp+var_18]
0x18008f12c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f131  mov     ecx, [rbp+var_8]
0x18008f134  jmp     short loc_18008F143
0x18008f136  mov     ecx, [rax]
0x18008f138  mov     rax, [rax+20h]
0x18008f13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f141  xor     ecx, ecx; dwExceptionCode
0x18008f143  test    ecx, ecx
0x18008f145  jns     short loc_18008F157
0x18008f147  xor     r9d, r9d; lpArguments
0x18008f14a  xor     r8d, r8d; nNumberOfArguments
0x18008f14d  lea     edx, [r9+1]; dwExceptionFlags
0x18008f151  call    cs:__imp_RaiseException
0x18008f157  mov     ebx, [rbp+var_20]
0x18008f15a  mov     eax, ebx
0x18008f15c  mov     rbx, [rsp+50h+arg_0]
0x18008f164  add     rsp, 50h
0x18008f168  pop     r14
0x18008f16a  pop     r12
0x18008f16c  pop     rdi
0x18008f16d  pop     rsi
0x18008f16e  pop     rbp
0x18008f16f  retn
```
