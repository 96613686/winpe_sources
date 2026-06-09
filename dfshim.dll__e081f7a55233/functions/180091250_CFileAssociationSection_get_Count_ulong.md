# CFileAssociationSection::get_Count(ulong *)

- ea: `0x180091250`
- end: `0x1800914b0`
- name: `?get_Count@CFileAssociationSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CFileAssociationSection *__hidden this, unsigned int *)`
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
- `0x180091250`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009130d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800913e1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009130d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800913e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091397`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091491`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091397`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091491`

## string_xrefs

- `0x180091348`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091446`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18009126a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CFileAssociationSection::get_Count(CFileAssociationSection *this, unsigned int *a2)
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
    v16 = 5004;
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
    v16 = 5005;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 5006;
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
        (const char *)0x139A,
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
        (const char *)0x1396,
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
0x180091250  mov     [rsp-28h+arg_0], rbx
0x180091255  push    rbp
0x180091256  push    rsi
0x180091257  push    rdi
0x180091258  push    r12
0x18009125a  push    r14
0x18009125c  mov     rbp, rsp
0x18009125f  sub     rsp, 50h
0x180091263  mov     [rbp+var_20], 8007054Fh
0x18009126a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091271  mov     [rbp+var_30], r12
0x180091275  mov     rdi, rdx
0x180091278  mov     [rbp+arg_8], 0
0x180091280  mov     rbx, rcx
0x180091283  mov     [rbp+arg_10], 0
0x18009128b  test    rdx, rdx
0x18009128e  jz      loc_180091426
0x180091294  mov     dword ptr [rdx], 0
0x18009129a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x1800912a1  test    rdx, rdx
0x1800912a4  jz      loc_180091410
0x1800912aa  mov     rcx, [rcx+18h]
0x1800912ae  call    RtlIsTypeSafeHandleValid
0x1800912b3  test    al, al
0x1800912b5  jz      loc_180091410
0x1800912bb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x1800912c2  test    rdx, rdx
0x1800912c5  jz      loc_180091407
0x1800912cb  mov     rcx, [rbx+20h]
0x1800912cf  call    RtlIsTypeSafeHandleValid
0x1800912d4  test    al, al
0x1800912d6  jz      loc_180091407
0x1800912dc  cmp     byte ptr [rbx+2Ch], 0
0x1800912e0  jz      short loc_1800912EE
0x1800912e2  mov     eax, [rbx+28h]
0x1800912e5  xor     ebx, ebx
0x1800912e7  mov     [rdi], eax
0x1800912e9  jmp     loc_18009149A
0x1800912ee  mov     rcx, [rbx+20h]
0x1800912f2  lea     rdx, [rbp+arg_8]
0x1800912f6  call    CdfEnumerateStringTable
0x1800912fb  mov     esi, eax
0x1800912fd  test    eax, eax
0x1800912ff  jns     loc_1800913A2
0x180091305  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18009130b  jnz     short loc_180091313
0x18009130d  call    cs:__imp_DebugBreak
0x180091313  mov     r9d, esi; int
0x180091316  lea     rcx, aStatusPropagat; "Status propagated"
0x18009131d  mov     r8d, 1396h; char *
0x180091323  mov     rdx, r12; char *
0x180091326  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009132b  mov     ecx, esi; this
0x18009132d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180091332  mov     ebx, eax
0x180091334  mov     rdx, [rbp+arg_8]
0x180091338  test    rdx, rdx
0x18009133b  jz      loc_18009149A
0x180091341  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091348  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009134f  mov     [rbp+var_20], 0C00000E5h
0x180091356  mov     [rbp+var_30], rcx
0x18009135a  test    rax, rax
0x18009135d  jnz     short loc_180091378
0x18009135f  mov     [rbp+var_28], 401h
0x180091366  lea     rdx, [rbp+var_30]
0x18009136a  lea     rcx, [rbp+var_30]
0x18009136e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091373  mov     ecx, [rbp+var_20]
0x180091376  jmp     short loc_180091385
0x180091378  mov     ecx, [rax]
0x18009137a  mov     rax, [rax+20h]
0x18009137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091383  xor     ecx, ecx; dwExceptionCode
0x180091385  test    ecx, ecx
0x180091387  jns     loc_18009149A
0x18009138d  xor     r9d, r9d; lpArguments
0x180091390  xor     r8d, r8d; nNumberOfArguments
0x180091393  lea     edx, [r9+1]; dwExceptionFlags
0x180091397  call    cs:__imp_RaiseException
0x18009139d  jmp     loc_18009149A
0x1800913a2  xor     esi, esi
0x1800913a4  mov     rcx, [rbp+arg_8]
0x1800913a8  lea     r8, [rbp+arg_10]
0x1800913ac  mov     edx, 1
0x1800913b1  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x1800913b6  mov     r14d, eax
0x1800913b9  test    eax, eax
0x1800913bb  js      short loc_1800913D8
0x1800913bd  cmp     [rbp+arg_10], 1
0x1800913c2  jnz     short loc_1800913C8
0x1800913c4  inc     esi
0x1800913c6  jmp     short loc_1800913A4
0x1800913c8  mov     [rbx+28h], esi
0x1800913cb  mov     byte ptr [rbx+2Ch], 1
0x1800913cf  xor     ebx, ebx
0x1800913d1  mov     [rdi], esi
0x1800913d3  jmp     loc_180091334
0x1800913d8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x1800913df  jnz     short loc_1800913E7
0x1800913e1  call    cs:__imp_DebugBreak
0x1800913e7  mov     r9d, r14d; int
0x1800913ea  lea     rcx, aStatusPropagat; "Status propagated"
0x1800913f1  mov     r8d, 139Ah; char *
0x1800913f7  mov     rdx, r12; char *
0x1800913fa  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800913ff  mov     ecx, r14d
0x180091402  jmp     loc_18009132D
0x180091407  mov     [rbp+var_28], 138Eh
0x18009140e  jmp     short loc_180091417
0x180091410  mov     [rbp+var_28], 138Dh
0x180091417  lea     rdx, [rbp+var_30]
0x18009141b  lea     rcx, [rbp+var_30]
0x18009141f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091424  jmp     short loc_180091497
0x180091426  lea     rcx, [rbp+var_30]
0x18009142a  mov     [rbp+var_28], 138Ch
0x180091431  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180091436  mov     rdx, [rbp+arg_8]
0x18009143a  test    rdx, rdx
0x18009143d  jz      short loc_180091497
0x18009143f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091446  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009144d  mov     [rbp+var_8], 0C00000E5h
0x180091454  mov     [rbp+var_18], rcx
0x180091458  test    rax, rax
0x18009145b  jnz     short loc_180091476
0x18009145d  mov     [rbp+var_10], 401h
0x180091464  lea     rdx, [rbp+var_18]
0x180091468  lea     rcx, [rbp+var_18]
0x18009146c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091471  mov     ecx, [rbp+var_8]
0x180091474  jmp     short loc_180091483
0x180091476  mov     ecx, [rax]
0x180091478  mov     rax, [rax+20h]
0x18009147c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091481  xor     ecx, ecx; dwExceptionCode
0x180091483  test    ecx, ecx
0x180091485  jns     short loc_180091497
0x180091487  xor     r9d, r9d; lpArguments
0x18009148a  xor     r8d, r8d; nNumberOfArguments
0x18009148d  lea     edx, [r9+1]; dwExceptionFlags
0x180091491  call    cs:__imp_RaiseException
0x180091497  mov     ebx, [rbp+var_20]
0x18009149a  mov     eax, ebx
0x18009149c  mov     rbx, [rsp+50h+arg_0]
0x1800914a4  add     rsp, 50h
0x1800914a8  pop     r14
0x1800914aa  pop     r12
0x1800914ac  pop     rdi
0x1800914ad  pop     rsi
0x1800914ae  pop     rbp
0x1800914af  retn
```
