# CSubcategoryMembershipSection::get_Count(ulong *)

- ea: `0x180092360`
- end: `0x1800925c0`
- name: `?get_Count@CSubcategoryMembershipSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CSubcategoryMembershipSection *__hidden this, unsigned int *)`
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
- `0x180092360`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009241d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800924f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009241d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800924f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800924a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800925a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800924a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800925a1`

## string_xrefs

- `0x180092458`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180092556`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18009237a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CSubcategoryMembershipSection::get_Count(CSubcategoryMembershipSection *this, unsigned int *a2)
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
    v16 = 5311;
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
    v16 = 5312;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5313;
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
        (const char *)0x14CD,
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
        (const char *)0x14C9,
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
0x180092360  mov     [rsp-28h+arg_0], rbx
0x180092365  push    rbp
0x180092366  push    rsi
0x180092367  push    rdi
0x180092368  push    r12
0x18009236a  push    r14
0x18009236c  mov     rbp, rsp
0x18009236f  sub     rsp, 50h
0x180092373  mov     [rbp+var_20], 8007054Fh
0x18009237a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180092381  mov     [rbp+var_30], r12
0x180092385  mov     rdi, rdx
0x180092388  mov     [rbp+arg_8], 0
0x180092390  mov     rbx, rcx
0x180092393  mov     [rbp+arg_10], 0
0x18009239b  test    rdx, rdx
0x18009239e  jz      loc_180092536
0x1800923a4  mov     dword ptr [rdx], 0
0x1800923aa  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x1800923b1  test    rdx, rdx
0x1800923b4  jz      loc_180092520
0x1800923ba  mov     rcx, [rcx+18h]
0x1800923be  call    RtlIsTypeSafeHandleValid
0x1800923c3  test    al, al
0x1800923c5  jz      loc_180092520
0x1800923cb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x1800923d2  test    rdx, rdx
0x1800923d5  jz      loc_180092517
0x1800923db  mov     rcx, [rbx+20h]
0x1800923df  call    RtlIsTypeSafeHandleValid
0x1800923e4  test    al, al
0x1800923e6  jz      loc_180092517
0x1800923ec  cmp     byte ptr [rbx+2Ch], 0
0x1800923f0  jz      short loc_1800923FE
0x1800923f2  mov     eax, [rbx+28h]
0x1800923f5  xor     ebx, ebx
0x1800923f7  mov     [rdi], eax
0x1800923f9  jmp     loc_1800925AA
0x1800923fe  mov     rcx, [rbx+20h]
0x180092402  lea     rdx, [rbp+arg_8]
0x180092406  call    CdfEnumerateStringTable
0x18009240b  mov     esi, eax
0x18009240d  test    eax, eax
0x18009240f  jns     loc_1800924B2
0x180092415  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18009241b  jnz     short loc_180092423
0x18009241d  call    cs:__imp_DebugBreak
0x180092423  mov     r9d, esi; int
0x180092426  lea     rcx, aStatusPropagat; "Status propagated"
0x18009242d  mov     r8d, 14C9h; char *
0x180092433  mov     rdx, r12; char *
0x180092436  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009243b  mov     ecx, esi; this
0x18009243d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180092442  mov     ebx, eax
0x180092444  mov     rdx, [rbp+arg_8]
0x180092448  test    rdx, rdx
0x18009244b  jz      loc_1800925AA
0x180092451  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180092458  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009245f  mov     [rbp+var_20], 0C00000E5h
0x180092466  mov     [rbp+var_30], rcx
0x18009246a  test    rax, rax
0x18009246d  jnz     short loc_180092488
0x18009246f  mov     [rbp+var_28], 401h
0x180092476  lea     rdx, [rbp+var_30]
0x18009247a  lea     rcx, [rbp+var_30]
0x18009247e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092483  mov     ecx, [rbp+var_20]
0x180092486  jmp     short loc_180092495
0x180092488  mov     ecx, [rax]
0x18009248a  mov     rax, [rax+20h]
0x18009248e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092493  xor     ecx, ecx; dwExceptionCode
0x180092495  test    ecx, ecx
0x180092497  jns     loc_1800925AA
0x18009249d  xor     r9d, r9d; lpArguments
0x1800924a0  xor     r8d, r8d; nNumberOfArguments
0x1800924a3  lea     edx, [r9+1]; dwExceptionFlags
0x1800924a7  call    cs:__imp_RaiseException
0x1800924ad  jmp     loc_1800925AA
0x1800924b2  xor     esi, esi
0x1800924b4  mov     rcx, [rbp+arg_8]
0x1800924b8  lea     r8, [rbp+arg_10]
0x1800924bc  mov     edx, 1
0x1800924c1  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x1800924c6  mov     r14d, eax
0x1800924c9  test    eax, eax
0x1800924cb  js      short loc_1800924E8
0x1800924cd  cmp     [rbp+arg_10], 1
0x1800924d2  jnz     short loc_1800924D8
0x1800924d4  inc     esi
0x1800924d6  jmp     short loc_1800924B4
0x1800924d8  mov     [rbx+28h], esi
0x1800924db  mov     byte ptr [rbx+2Ch], 1
0x1800924df  xor     ebx, ebx
0x1800924e1  mov     [rdi], esi
0x1800924e3  jmp     loc_180092444
0x1800924e8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x1800924ef  jnz     short loc_1800924F7
0x1800924f1  call    cs:__imp_DebugBreak
0x1800924f7  mov     r9d, r14d; int
0x1800924fa  lea     rcx, aStatusPropagat; "Status propagated"
0x180092501  mov     r8d, 14CDh; char *
0x180092507  mov     rdx, r12; char *
0x18009250a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009250f  mov     ecx, r14d
0x180092512  jmp     loc_18009243D
0x180092517  mov     [rbp+var_28], 14C1h
0x18009251e  jmp     short loc_180092527
0x180092520  mov     [rbp+var_28], 14C0h
0x180092527  lea     rdx, [rbp+var_30]
0x18009252b  lea     rcx, [rbp+var_30]
0x18009252f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092534  jmp     short loc_1800925A7
0x180092536  lea     rcx, [rbp+var_30]
0x18009253a  mov     [rbp+var_28], 14BFh
0x180092541  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180092546  mov     rdx, [rbp+arg_8]
0x18009254a  test    rdx, rdx
0x18009254d  jz      short loc_1800925A7
0x18009254f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180092556  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009255d  mov     [rbp+var_8], 0C00000E5h
0x180092564  mov     [rbp+var_18], rcx
0x180092568  test    rax, rax
0x18009256b  jnz     short loc_180092586
0x18009256d  mov     [rbp+var_10], 401h
0x180092574  lea     rdx, [rbp+var_18]
0x180092578  lea     rcx, [rbp+var_18]
0x18009257c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092581  mov     ecx, [rbp+var_8]
0x180092584  jmp     short loc_180092593
0x180092586  mov     ecx, [rax]
0x180092588  mov     rax, [rax+20h]
0x18009258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092591  xor     ecx, ecx; dwExceptionCode
0x180092593  test    ecx, ecx
0x180092595  jns     short loc_1800925A7
0x180092597  xor     r9d, r9d; lpArguments
0x18009259a  xor     r8d, r8d; nNumberOfArguments
0x18009259d  lea     edx, [r9+1]; dwExceptionFlags
0x1800925a1  call    cs:__imp_RaiseException
0x1800925a7  mov     ebx, [rbp+var_20]
0x1800925aa  mov     eax, ebx
0x1800925ac  mov     rbx, [rsp+50h+arg_0]
0x1800925b4  add     rsp, 50h
0x1800925b8  pop     r14
0x1800925ba  pop     r12
0x1800925bc  pop     rdi
0x1800925bd  pop     rsi
0x1800925be  pop     rbp
0x1800925bf  retn
```
