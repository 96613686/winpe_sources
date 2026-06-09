# CWindowClassSection::get_Count(ulong *)

- ea: `0x1800925d0`
- end: `0x180092830`
- name: `?get_Count@CWindowClassSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CWindowClassSection *__hidden this, unsigned int *)`
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
- `0x1800925d0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009268d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092761`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009268d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092761`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092717`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092811`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092717`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092811`

## string_xrefs

- `0x1800926c8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800927c6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800925ea`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CWindowClassSection::get_Count(CWindowClassSection *this, unsigned int *a2)
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
    v16 = 6216;
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
    v16 = 6217;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6218;
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
        (const char *)0x1856,
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
        (const char *)0x1852,
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
0x1800925d0  mov     [rsp-28h+arg_0], rbx
0x1800925d5  push    rbp
0x1800925d6  push    rsi
0x1800925d7  push    rdi
0x1800925d8  push    r12
0x1800925da  push    r14
0x1800925dc  mov     rbp, rsp
0x1800925df  sub     rsp, 50h
0x1800925e3  mov     [rbp+var_20], 8007054Fh
0x1800925ea  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800925f1  mov     [rbp+var_30], r12
0x1800925f5  mov     rdi, rdx
0x1800925f8  mov     [rbp+arg_8], 0
0x180092600  mov     rbx, rcx
0x180092603  mov     [rbp+arg_10], 0
0x18009260b  test    rdx, rdx
0x18009260e  jz      loc_1800927A6
0x180092614  mov     dword ptr [rdx], 0
0x18009261a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180092621  test    rdx, rdx
0x180092624  jz      loc_180092790
0x18009262a  mov     rcx, [rcx+18h]
0x18009262e  call    RtlIsTypeSafeHandleValid
0x180092633  test    al, al
0x180092635  jz      loc_180092790
0x18009263b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180092642  test    rdx, rdx
0x180092645  jz      loc_180092787
0x18009264b  mov     rcx, [rbx+20h]
0x18009264f  call    RtlIsTypeSafeHandleValid
0x180092654  test    al, al
0x180092656  jz      loc_180092787
0x18009265c  cmp     byte ptr [rbx+2Ch], 0
0x180092660  jz      short loc_18009266E
0x180092662  mov     eax, [rbx+28h]
0x180092665  xor     ebx, ebx
0x180092667  mov     [rdi], eax
0x180092669  jmp     loc_18009281A
0x18009266e  mov     rcx, [rbx+20h]
0x180092672  lea     rdx, [rbp+arg_8]
0x180092676  call    CdfEnumerateStringTable
0x18009267b  mov     esi, eax
0x18009267d  test    eax, eax
0x18009267f  jns     loc_180092722
0x180092685  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18009268b  jnz     short loc_180092693
0x18009268d  call    cs:__imp_DebugBreak
0x180092693  mov     r9d, esi; int
0x180092696  lea     rcx, aStatusPropagat; "Status propagated"
0x18009269d  mov     r8d, 1852h; char *
0x1800926a3  mov     rdx, r12; char *
0x1800926a6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800926ab  mov     ecx, esi; this
0x1800926ad  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800926b2  mov     ebx, eax
0x1800926b4  mov     rdx, [rbp+arg_8]
0x1800926b8  test    rdx, rdx
0x1800926bb  jz      loc_18009281A
0x1800926c1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800926c8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800926cf  mov     [rbp+var_20], 0C00000E5h
0x1800926d6  mov     [rbp+var_30], rcx
0x1800926da  test    rax, rax
0x1800926dd  jnz     short loc_1800926F8
0x1800926df  mov     [rbp+var_28], 401h
0x1800926e6  lea     rdx, [rbp+var_30]
0x1800926ea  lea     rcx, [rbp+var_30]
0x1800926ee  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800926f3  mov     ecx, [rbp+var_20]
0x1800926f6  jmp     short loc_180092705
0x1800926f8  mov     ecx, [rax]
0x1800926fa  mov     rax, [rax+20h]
0x1800926fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092703  xor     ecx, ecx; dwExceptionCode
0x180092705  test    ecx, ecx
0x180092707  jns     loc_18009281A
0x18009270d  xor     r9d, r9d; lpArguments
0x180092710  xor     r8d, r8d; nNumberOfArguments
0x180092713  lea     edx, [r9+1]; dwExceptionFlags
0x180092717  call    cs:__imp_RaiseException
0x18009271d  jmp     loc_18009281A
0x180092722  xor     esi, esi
0x180092724  mov     rcx, [rbp+arg_8]
0x180092728  lea     r8, [rbp+arg_10]
0x18009272c  mov     edx, 1
0x180092731  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180092736  mov     r14d, eax
0x180092739  test    eax, eax
0x18009273b  js      short loc_180092758
0x18009273d  cmp     [rbp+arg_10], 1
0x180092742  jnz     short loc_180092748
0x180092744  inc     esi
0x180092746  jmp     short loc_180092724
0x180092748  mov     [rbx+28h], esi
0x18009274b  mov     byte ptr [rbx+2Ch], 1
0x18009274f  xor     ebx, ebx
0x180092751  mov     [rdi], esi
0x180092753  jmp     loc_1800926B4
0x180092758  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009275f  jnz     short loc_180092767
0x180092761  call    cs:__imp_DebugBreak
0x180092767  mov     r9d, r14d; int
0x18009276a  lea     rcx, aStatusPropagat; "Status propagated"
0x180092771  mov     r8d, 1856h; char *
0x180092777  mov     rdx, r12; char *
0x18009277a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009277f  mov     ecx, r14d
0x180092782  jmp     loc_1800926AD
0x180092787  mov     [rbp+var_28], 184Ah
0x18009278e  jmp     short loc_180092797
0x180092790  mov     [rbp+var_28], 1849h
0x180092797  lea     rdx, [rbp+var_30]
0x18009279b  lea     rcx, [rbp+var_30]
0x18009279f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800927a4  jmp     short loc_180092817
0x1800927a6  lea     rcx, [rbp+var_30]
0x1800927aa  mov     [rbp+var_28], 1848h
0x1800927b1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800927b6  mov     rdx, [rbp+arg_8]
0x1800927ba  test    rdx, rdx
0x1800927bd  jz      short loc_180092817
0x1800927bf  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800927c6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800927cd  mov     [rbp+var_8], 0C00000E5h
0x1800927d4  mov     [rbp+var_18], rcx
0x1800927d8  test    rax, rax
0x1800927db  jnz     short loc_1800927F6
0x1800927dd  mov     [rbp+var_10], 401h
0x1800927e4  lea     rdx, [rbp+var_18]
0x1800927e8  lea     rcx, [rbp+var_18]
0x1800927ec  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800927f1  mov     ecx, [rbp+var_8]
0x1800927f4  jmp     short loc_180092803
0x1800927f6  mov     ecx, [rax]
0x1800927f8  mov     rax, [rax+20h]
0x1800927fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092801  xor     ecx, ecx; dwExceptionCode
0x180092803  test    ecx, ecx
0x180092805  jns     short loc_180092817
0x180092807  xor     r9d, r9d; lpArguments
0x18009280a  xor     r8d, r8d; nNumberOfArguments
0x18009280d  lea     edx, [r9+1]; dwExceptionFlags
0x180092811  call    cs:__imp_RaiseException
0x180092817  mov     ebx, [rbp+var_20]
0x18009281a  mov     eax, ebx
0x18009281c  mov     rbx, [rsp+50h+arg_0]
0x180092824  add     rsp, 50h
0x180092828  pop     r14
0x18009282a  pop     r12
0x18009282c  pop     rdi
0x18009282d  pop     rsi
0x18009282e  pop     rbp
0x18009282f  retn
```
