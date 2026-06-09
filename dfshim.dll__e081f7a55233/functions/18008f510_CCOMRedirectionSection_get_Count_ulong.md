# CCOMRedirectionSection::get_Count(ulong *)

- ea: `0x18008f510`
- end: `0x18008f770`
- name: `?get_Count@CCOMRedirectionSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCOMRedirectionSection *__hidden this, unsigned int *)`
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
- `0x18008f510`
- `0x1800d537c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f5cd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f6a1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f5cd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f6a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f657`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f751`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f657`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f751`

## string_xrefs

- `0x18008f608`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f706`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f52a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCOMRedirectionSection::get_Count(CCOMRedirectionSection *this, unsigned int *a2)
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
    v16 = 5609;
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
    v16 = 5610;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5611;
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
        (const char *)0x15F7,
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
        (const char *)0x15F3,
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
0x18008f510  mov     [rsp-28h+arg_0], rbx
0x18008f515  push    rbp
0x18008f516  push    rsi
0x18008f517  push    rdi
0x18008f518  push    r12
0x18008f51a  push    r14
0x18008f51c  mov     rbp, rsp
0x18008f51f  sub     rsp, 50h
0x18008f523  mov     [rbp+var_20], 8007054Fh
0x18008f52a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f531  mov     [rbp+var_30], r12
0x18008f535  mov     rdi, rdx
0x18008f538  mov     [rbp+arg_8], 0
0x18008f540  mov     rbx, rcx
0x18008f543  mov     [rbp+arg_10], 0
0x18008f54b  test    rdx, rdx
0x18008f54e  jz      loc_18008F6E6
0x18008f554  mov     dword ptr [rdx], 0
0x18008f55a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008f561  test    rdx, rdx
0x18008f564  jz      loc_18008F6D0
0x18008f56a  mov     rcx, [rcx+18h]
0x18008f56e  call    RtlIsTypeSafeHandleValid
0x18008f573  test    al, al
0x18008f575  jz      loc_18008F6D0
0x18008f57b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE,_CDF_INTERNAL_GUID_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008f582  test    rdx, rdx
0x18008f585  jz      loc_18008F6C7
0x18008f58b  mov     rcx, [rbx+20h]
0x18008f58f  call    RtlIsTypeSafeHandleValid
0x18008f594  test    al, al
0x18008f596  jz      loc_18008F6C7
0x18008f59c  cmp     byte ptr [rbx+2Ch], 0
0x18008f5a0  jz      short loc_18008F5AE
0x18008f5a2  mov     eax, [rbx+28h]
0x18008f5a5  xor     ebx, ebx
0x18008f5a7  mov     [rdi], eax
0x18008f5a9  jmp     loc_18008F75A
0x18008f5ae  mov     rcx, [rbx+20h]
0x18008f5b2  lea     rdx, [rbp+arg_8]
0x18008f5b6  call    CdfEnumerateGuidTable
0x18008f5bb  mov     esi, eax
0x18008f5bd  test    eax, eax
0x18008f5bf  jns     loc_18008F662
0x18008f5c5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008f5cb  jnz     short loc_18008F5D3
0x18008f5cd  call    cs:__imp_DebugBreak
0x18008f5d3  mov     r9d, esi; int
0x18008f5d6  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f5dd  mov     r8d, 15F3h; char *
0x18008f5e3  mov     rdx, r12; char *
0x18008f5e6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f5eb  mov     ecx, esi; this
0x18008f5ed  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008f5f2  mov     ebx, eax
0x18008f5f4  mov     rdx, [rbp+arg_8]
0x18008f5f8  test    rdx, rdx
0x18008f5fb  jz      loc_18008F75A
0x18008f601  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f608  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f60f  mov     [rbp+var_20], 0C00000E5h
0x18008f616  mov     [rbp+var_30], rcx
0x18008f61a  test    rax, rax
0x18008f61d  jnz     short loc_18008F638
0x18008f61f  mov     [rbp+var_28], 401h
0x18008f626  lea     rdx, [rbp+var_30]
0x18008f62a  lea     rcx, [rbp+var_30]
0x18008f62e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f633  mov     ecx, [rbp+var_20]
0x18008f636  jmp     short loc_18008F645
0x18008f638  mov     ecx, [rax]
0x18008f63a  mov     rax, [rax+20h]
0x18008f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f643  xor     ecx, ecx; dwExceptionCode
0x18008f645  test    ecx, ecx
0x18008f647  jns     loc_18008F75A
0x18008f64d  xor     r9d, r9d; lpArguments
0x18008f650  xor     r8d, r8d; nNumberOfArguments
0x18008f653  lea     edx, [r9+1]; dwExceptionFlags
0x18008f657  call    cs:__imp_RaiseException
0x18008f65d  jmp     loc_18008F75A
0x18008f662  xor     esi, esi
0x18008f664  mov     rcx, [rbp+arg_8]
0x18008f668  lea     r8, [rbp+arg_10]
0x18008f66c  mov     edx, 1
0x18008f671  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_GUID_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,__int64,__int64 &)
0x18008f676  mov     r14d, eax
0x18008f679  test    eax, eax
0x18008f67b  js      short loc_18008F698
0x18008f67d  cmp     [rbp+arg_10], 1
0x18008f682  jnz     short loc_18008F688
0x18008f684  inc     esi
0x18008f686  jmp     short loc_18008F664
0x18008f688  mov     [rbx+28h], esi
0x18008f68b  mov     byte ptr [rbx+2Ch], 1
0x18008f68f  xor     ebx, ebx
0x18008f691  mov     [rdi], esi
0x18008f693  jmp     loc_18008F5F4
0x18008f698  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008f69f  jnz     short loc_18008F6A7
0x18008f6a1  call    cs:__imp_DebugBreak
0x18008f6a7  mov     r9d, r14d; int
0x18008f6aa  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f6b1  mov     r8d, 15F7h; char *
0x18008f6b7  mov     rdx, r12; char *
0x18008f6ba  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f6bf  mov     ecx, r14d
0x18008f6c2  jmp     loc_18008F5ED
0x18008f6c7  mov     [rbp+var_28], 15EBh
0x18008f6ce  jmp     short loc_18008F6D7
0x18008f6d0  mov     [rbp+var_28], 15EAh
0x18008f6d7  lea     rdx, [rbp+var_30]
0x18008f6db  lea     rcx, [rbp+var_30]
0x18008f6df  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f6e4  jmp     short loc_18008F757
0x18008f6e6  lea     rcx, [rbp+var_30]
0x18008f6ea  mov     [rbp+var_28], 15E9h
0x18008f6f1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008f6f6  mov     rdx, [rbp+arg_8]
0x18008f6fa  test    rdx, rdx
0x18008f6fd  jz      short loc_18008F757
0x18008f6ff  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_GUID_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_GUID_TABLE_ENUMERATOR@@U_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,_CDF_INTERNAL_GUID_TABLE_ENUMERATOR,_CDF_GUID_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f706  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f70d  mov     [rbp+var_8], 0C00000E5h
0x18008f714  mov     [rbp+var_18], rcx
0x18008f718  test    rax, rax
0x18008f71b  jnz     short loc_18008F736
0x18008f71d  mov     [rbp+var_10], 401h
0x18008f724  lea     rdx, [rbp+var_18]
0x18008f728  lea     rcx, [rbp+var_18]
0x18008f72c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f731  mov     ecx, [rbp+var_8]
0x18008f734  jmp     short loc_18008F743
0x18008f736  mov     ecx, [rax]
0x18008f738  mov     rax, [rax+20h]
0x18008f73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f741  xor     ecx, ecx; dwExceptionCode
0x18008f743  test    ecx, ecx
0x18008f745  jns     short loc_18008F757
0x18008f747  xor     r9d, r9d; lpArguments
0x18008f74a  xor     r8d, r8d; nNumberOfArguments
0x18008f74d  lea     edx, [r9+1]; dwExceptionFlags
0x18008f751  call    cs:__imp_RaiseException
0x18008f757  mov     ebx, [rbp+var_20]
0x18008f75a  mov     eax, ebx
0x18008f75c  mov     rbx, [rsp+50h+arg_0]
0x18008f764  add     rsp, 50h
0x18008f768  pop     r14
0x18008f76a  pop     r12
0x18008f76c  pop     rdi
0x18008f76d  pop     rsi
0x18008f76e  pop     rbp
0x18008f76f  retn
```
