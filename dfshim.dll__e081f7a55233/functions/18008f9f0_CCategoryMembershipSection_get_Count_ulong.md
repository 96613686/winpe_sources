# CCategoryMembershipSection::get_Count(ulong *)

- ea: `0x18008f9f0`
- end: `0x18008fc50`
- name: `?get_Count@CCategoryMembershipSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCategoryMembershipSection *__hidden this, unsigned int *)`
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
- `0x180072ff0`
- `0x18008f9f0`
- `0x18010a7ec`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008faad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fb81`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008faad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fb81`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fb37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fc31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fb37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fc31`

## string_xrefs

- `0x18008fae8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008fbe6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008fa0a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCategoryMembershipSection::get_Count(CCategoryMembershipSection *this, unsigned int *a2)
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
    v16 = 5159;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
    v16 = 5160;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5161;
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
    v6 = CdfEnumerateDefinitionIdentityTable(*((_QWORD *)this + 4), &v21);
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
        (const char *)0x1435,
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
        (const char *)0x1431,
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
0x18008f9f0  mov     [rsp-28h+arg_0], rbx
0x18008f9f5  push    rbp
0x18008f9f6  push    rsi
0x18008f9f7  push    rdi
0x18008f9f8  push    r12
0x18008f9fa  push    r14
0x18008f9fc  mov     rbp, rsp
0x18008f9ff  sub     rsp, 50h
0x18008fa03  mov     [rbp+var_20], 8007054Fh
0x18008fa0a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fa11  mov     [rbp+var_30], r12
0x18008fa15  mov     rdi, rdx
0x18008fa18  mov     [rbp+arg_8], 0
0x18008fa20  mov     rbx, rcx
0x18008fa23  mov     [rbp+arg_10], 0
0x18008fa2b  test    rdx, rdx
0x18008fa2e  jz      loc_18008FBC6
0x18008fa34  mov     dword ptr [rdx], 0
0x18008fa3a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008fa41  test    rdx, rdx
0x18008fa44  jz      loc_18008FBB0
0x18008fa4a  mov     rcx, [rcx+18h]
0x18008fa4e  call    RtlIsTypeSafeHandleValid
0x18008fa53  test    al, al
0x18008fa55  jz      loc_18008FBB0
0x18008fa5b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008fa62  test    rdx, rdx
0x18008fa65  jz      loc_18008FBA7
0x18008fa6b  mov     rcx, [rbx+20h]
0x18008fa6f  call    RtlIsTypeSafeHandleValid
0x18008fa74  test    al, al
0x18008fa76  jz      loc_18008FBA7
0x18008fa7c  cmp     byte ptr [rbx+2Ch], 0
0x18008fa80  jz      short loc_18008FA8E
0x18008fa82  mov     eax, [rbx+28h]
0x18008fa85  xor     ebx, ebx
0x18008fa87  mov     [rdi], eax
0x18008fa89  jmp     loc_18008FC3A
0x18008fa8e  mov     rcx, [rbx+20h]
0x18008fa92  lea     rdx, [rbp+arg_8]
0x18008fa96  call    CdfEnumerateDefinitionIdentityTable
0x18008fa9b  mov     esi, eax
0x18008fa9d  test    eax, eax
0x18008fa9f  jns     loc_18008FB42
0x18008faa5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008faab  jnz     short loc_18008FAB3
0x18008faad  call    cs:__imp_DebugBreak
0x18008fab3  mov     r9d, esi; int
0x18008fab6  lea     rcx, aStatusPropagat; "Status propagated"
0x18008fabd  mov     r8d, 1431h; char *
0x18008fac3  mov     rdx, r12; char *
0x18008fac6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008facb  mov     ecx, esi; this
0x18008facd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008fad2  mov     ebx, eax
0x18008fad4  mov     rdx, [rbp+arg_8]
0x18008fad8  test    rdx, rdx
0x18008fadb  jz      loc_18008FC3A
0x18008fae1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR@@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008fae8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008faef  mov     [rbp+var_20], 0C00000E5h
0x18008faf6  mov     [rbp+var_30], rcx
0x18008fafa  test    rax, rax
0x18008fafd  jnz     short loc_18008FB18
0x18008faff  mov     [rbp+var_28], 401h
0x18008fb06  lea     rdx, [rbp+var_30]
0x18008fb0a  lea     rcx, [rbp+var_30]
0x18008fb0e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fb13  mov     ecx, [rbp+var_20]
0x18008fb16  jmp     short loc_18008FB25
0x18008fb18  mov     ecx, [rax]
0x18008fb1a  mov     rax, [rax+20h]
0x18008fb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb23  xor     ecx, ecx; dwExceptionCode
0x18008fb25  test    ecx, ecx
0x18008fb27  jns     loc_18008FC3A
0x18008fb2d  xor     r9d, r9d; lpArguments
0x18008fb30  xor     r8d, r8d; nNumberOfArguments
0x18008fb33  lea     edx, [r9+1]; dwExceptionFlags
0x18008fb37  call    cs:__imp_RaiseException
0x18008fb3d  jmp     loc_18008FC3A
0x18008fb42  xor     esi, esi
0x18008fb44  mov     rcx, [rbp+arg_8]
0x18008fb48  lea     r8, [rbp+arg_10]
0x18008fb4c  mov     edx, 1
0x18008fb51  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,__int64,__int64 &)
0x18008fb56  mov     r14d, eax
0x18008fb59  test    eax, eax
0x18008fb5b  js      short loc_18008FB78
0x18008fb5d  cmp     [rbp+arg_10], 1
0x18008fb62  jnz     short loc_18008FB68
0x18008fb64  inc     esi
0x18008fb66  jmp     short loc_18008FB44
0x18008fb68  mov     [rbx+28h], esi
0x18008fb6b  mov     byte ptr [rbx+2Ch], 1
0x18008fb6f  xor     ebx, ebx
0x18008fb71  mov     [rdi], esi
0x18008fb73  jmp     loc_18008FAD4
0x18008fb78  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008fb7f  jnz     short loc_18008FB87
0x18008fb81  call    cs:__imp_DebugBreak
0x18008fb87  mov     r9d, r14d; int
0x18008fb8a  lea     rcx, aStatusPropagat; "Status propagated"
0x18008fb91  mov     r8d, 1435h; char *
0x18008fb97  mov     rdx, r12; char *
0x18008fb9a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008fb9f  mov     ecx, r14d
0x18008fba2  jmp     loc_18008FACD
0x18008fba7  mov     [rbp+var_28], 1429h
0x18008fbae  jmp     short loc_18008FBB7
0x18008fbb0  mov     [rbp+var_28], 1428h
0x18008fbb7  lea     rdx, [rbp+var_30]
0x18008fbbb  lea     rcx, [rbp+var_30]
0x18008fbbf  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fbc4  jmp     short loc_18008FC37
0x18008fbc6  lea     rcx, [rbp+var_30]
0x18008fbca  mov     [rbp+var_28], 1427h
0x18008fbd1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008fbd6  mov     rdx, [rbp+arg_8]
0x18008fbda  test    rdx, rdx
0x18008fbdd  jz      short loc_18008FC37
0x18008fbdf  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR@@U_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE_ENUMERATOR,_CDF_DEFINITION_IDENTITY_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008fbe6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fbed  mov     [rbp+var_8], 0C00000E5h
0x18008fbf4  mov     [rbp+var_18], rcx
0x18008fbf8  test    rax, rax
0x18008fbfb  jnz     short loc_18008FC16
0x18008fbfd  mov     [rbp+var_10], 401h
0x18008fc04  lea     rdx, [rbp+var_18]
0x18008fc08  lea     rcx, [rbp+var_18]
0x18008fc0c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fc11  mov     ecx, [rbp+var_8]
0x18008fc14  jmp     short loc_18008FC23
0x18008fc16  mov     ecx, [rax]
0x18008fc18  mov     rax, [rax+20h]
0x18008fc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fc21  xor     ecx, ecx; dwExceptionCode
0x18008fc23  test    ecx, ecx
0x18008fc25  jns     short loc_18008FC37
0x18008fc27  xor     r9d, r9d; lpArguments
0x18008fc2a  xor     r8d, r8d; nNumberOfArguments
0x18008fc2d  lea     edx, [r9+1]; dwExceptionFlags
0x18008fc31  call    cs:__imp_RaiseException
0x18008fc37  mov     ebx, [rbp+var_20]
0x18008fc3a  mov     eax, ebx
0x18008fc3c  mov     rbx, [rsp+50h+arg_0]
0x18008fc44  add     rsp, 50h
0x18008fc48  pop     r14
0x18008fc4a  pop     r12
0x18008fc4c  pop     rdi
0x18008fc4d  pop     rsi
0x18008fc4e  pop     rbp
0x18008fc4f  retn
```
