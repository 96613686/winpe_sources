# CCMS::get_Count(ulong *)

- ea: `0x18008f180`
- end: `0x18008f4fc`
- name: `?get_Count@CCMS@@UEAAJPEAK@Z`
- size: `892`
- prototype: `__int64 __fastcall(CCMS *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001b7e0`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x18002ff64`
- `0x180048d00`
- `0x180048d70`
- `0x180048f4c`
- `0x18004f2dc`
- `0x18008f180`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f223`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f2ed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f43b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f223`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f2ed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008f43b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f2a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f370`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f423`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f4e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f2a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f370`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f423`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008f4e2`

## string_xrefs

- `0x18008f25a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f325`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f3d8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f497`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008f199`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCMS::get_Count(CCMS *this, unsigned int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  int TOC; // eax
  unsigned int v7; // ebx
  int v8; // edx
  signed int v9; // ecx
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // r14d
  int v13; // edx
  unsigned __int64 v14; // rcx
  signed int v15; // ecx
  unsigned int i; // r14d
  int v17; // r15d
  __int64 v18; // rdx
  signed int v19; // ecx
  signed int v20; // ecx
  const char *v22; // [rsp+20h] [rbp-30h] BYREF
  int v23; // [rsp+28h] [rbp-28h]
  unsigned int v24; // [rsp+30h] [rbp-20h]
  const char *v25; // [rsp+38h] [rbp-18h] BYREF
  int v26; // [rsp+40h] [rbp-10h]
  int v27; // [rsp+48h] [rbp-8h]
  __int64 v28; // [rsp+98h] [rbp+48h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+58h] BYREF

  v24 = -2147023537;
  v22 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v29 = 0;
  v28 = 0;
  v30 = 0;
  if ( !a2 )
  {
    v23 = 3850;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v22);
    if ( v28 )
    {
      v27 = -1073741595;
      v25 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v20 = 0;
      }
      else
      {
        v26 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v25,
          &v25);
        v20 = v27;
      }
      if ( v20 < 0 )
        RaiseException(v20, 1u, 0, 0);
    }
    return v24;
  }
  *a2 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 5)) )
  {
    v23 = 3851;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v22,
      &v22);
    return v24;
  }
  if ( *((_BYTE *)this + 52) )
  {
    v4 = *((_DWORD *)this + 12);
    v5 = 0;
    *a2 = v4;
    return v5;
  }
  TOC = CdfGetTOC(*((_QWORD *)this + 5), &v29);
  v7 = TOC;
  if ( TOC >= 0 )
  {
    v10 = v29;
    v11 = CdfEnumerateUlongTable(v29, &v28);
    v12 = v11;
    if ( v11 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v17 = CdfMoveUlongTableEnumeratorPosition(v28, 1, &v30);
        if ( v17 < 0 )
          break;
        if ( v30 != 1 )
        {
          v18 = v28;
          *((_DWORD *)this + 12) = i;
          *((_BYTE *)this + 52) = 1;
          v5 = 0;
          *a2 = i;
          if ( v18 )
          {
            v24 = -1073741595;
            v22 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
            if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
            {
              (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                             + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
              v19 = 0;
            }
            else
            {
              v23 = 1025;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
                &v22,
                &v22);
              v19 = v24;
            }
            if ( v19 < 0 )
              RaiseException(v19, 1u, 0, 0);
            v28 = 0;
          }
          goto LABEL_29;
        }
      }
      if ( v17 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0xF1C,
        v17,
        (unsigned int)v22);
      v14 = (unsigned int)v17;
    }
    else
    {
      if ( v11 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0xF14,
        v12,
        (unsigned int)v22);
      v14 = v12;
    }
    v5 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v14, v13);
    if ( v28 )
    {
      v24 = -1073741595;
      v22 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v15 = 0;
      }
      else
      {
        v23 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v22,
          &v22);
        v15 = v24;
      }
      if ( v15 < 0 )
        RaiseException(v15, 1u, 0, 0);
      v28 = 0;
    }
LABEL_29:
    if ( v10 )
      goto LABEL_17;
  }
  else
  {
    if ( TOC == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0xF13,
      v7,
      (unsigned int)v22);
    v5 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v7, v8);
    if ( v28 )
    {
      v24 = -1073741595;
      v22 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v9 = 0;
      }
      else
      {
        v23 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v22,
          &v22);
        v9 = v24;
      }
      if ( v9 < 0 )
        RaiseException(v9, 1u, 0, 0);
      v28 = 0;
    }
    if ( v29 )
LABEL_17:
      CdfCloseUlongTableHandle();
  }
  return v5;
}

```

## disassembly

```asm
0x18008f180  push    rbp
0x18008f182  push    rbx
0x18008f183  push    rsi
0x18008f184  push    rdi
0x18008f185  push    r13
0x18008f187  push    r14
0x18008f189  push    r15
0x18008f18b  mov     rbp, rsp
0x18008f18e  sub     rsp, 50h
0x18008f192  mov     [rbp+var_20], 8007054Fh
0x18008f199  lea     r13, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f1a0  mov     [rbp+var_30], r13
0x18008f1a4  mov     rsi, rdx
0x18008f1a7  mov     [rbp+arg_10], 0
0x18008f1af  mov     rdi, rcx
0x18008f1b2  mov     [rbp+arg_8], 0
0x18008f1ba  mov     [rbp+arg_18], 0
0x18008f1c2  test    rdx, rdx
0x18008f1c5  jz      loc_18008F477
0x18008f1cb  mov     dword ptr [rdx], 0
0x18008f1d1  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008f1d8  test    rdx, rdx
0x18008f1db  jz      loc_18008F461
0x18008f1e1  mov     rcx, [rcx+28h]
0x18008f1e5  call    RtlIsTypeSafeHandleValid
0x18008f1ea  test    al, al
0x18008f1ec  jz      loc_18008F461
0x18008f1f2  cmp     byte ptr [rdi+34h], 0
0x18008f1f6  jz      short loc_18008F204
0x18008f1f8  mov     eax, [rdi+30h]
0x18008f1fb  xor     edi, edi
0x18008f1fd  mov     [rsi], eax
0x18008f1ff  jmp     loc_18008F4EB
0x18008f204  mov     rcx, [rdi+28h]
0x18008f208  lea     rdx, [rbp+arg_10]
0x18008f20c  call    CdfGetTOC
0x18008f211  mov     ebx, eax
0x18008f213  test    eax, eax
0x18008f215  jns     loc_18008F2CA
0x18008f21b  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008f221  jnz     short loc_18008F229
0x18008f223  call    cs:__imp_DebugBreak
0x18008f229  mov     r9d, ebx; int
0x18008f22c  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f233  mov     r8d, 0F13h; char *
0x18008f239  mov     rdx, r13; char *
0x18008f23c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f241  mov     ecx, ebx; this
0x18008f243  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008f248  mov     rdx, [rbp+arg_8]
0x18008f24c  mov     edi, eax
0x18008f24e  test    rdx, rdx
0x18008f251  jz      short loc_18008F2B3
0x18008f253  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f25a  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f261  mov     [rbp+var_20], 0C00000E5h
0x18008f268  mov     [rbp+var_30], rcx
0x18008f26c  test    rax, rax
0x18008f26f  jnz     short loc_18008F28A
0x18008f271  mov     [rbp+var_28], 401h
0x18008f278  lea     rdx, [rbp+var_30]
0x18008f27c  lea     rcx, [rbp+var_30]
0x18008f280  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f285  mov     ecx, [rbp+var_20]
0x18008f288  jmp     short loc_18008F297
0x18008f28a  mov     ecx, [rax]
0x18008f28c  mov     rax, [rax+20h]
0x18008f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f295  xor     ecx, ecx; dwExceptionCode
0x18008f297  test    ecx, ecx
0x18008f299  jns     short loc_18008F2AB
0x18008f29b  xor     r9d, r9d; lpArguments
0x18008f29e  xor     r8d, r8d; nNumberOfArguments
0x18008f2a1  lea     edx, [r9+1]; dwExceptionFlags
0x18008f2a5  call    cs:__imp_RaiseException
0x18008f2ab  mov     [rbp+arg_8], 0
0x18008f2b3  mov     rcx, [rbp+arg_10]
0x18008f2b7  test    rcx, rcx
0x18008f2ba  jz      loc_18008F4EB
0x18008f2c0  call    CdfCloseUlongTableHandle
0x18008f2c5  jmp     loc_18008F4EB
0x18008f2ca  mov     rbx, [rbp+arg_10]
0x18008f2ce  lea     rdx, [rbp+arg_8]
0x18008f2d2  mov     rcx, rbx
0x18008f2d5  call    CdfEnumerateUlongTable
0x18008f2da  mov     r14d, eax
0x18008f2dd  test    eax, eax
0x18008f2df  jns     loc_18008F38F
0x18008f2e5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008f2eb  jnz     short loc_18008F2F3
0x18008f2ed  call    cs:__imp_DebugBreak
0x18008f2f3  mov     r9d, r14d; int
0x18008f2f6  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f2fd  mov     r8d, 0F14h; char *
0x18008f303  mov     rdx, r13; char *
0x18008f306  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f30b  mov     ecx, r14d; this
0x18008f30e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008f313  mov     rdx, [rbp+arg_8]
0x18008f317  mov     edi, eax
0x18008f319  test    rdx, rdx
0x18008f31c  jz      short loc_18008F37E
0x18008f31e  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f325  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f32c  mov     [rbp+var_20], 0C00000E5h
0x18008f333  mov     [rbp+var_30], rcx
0x18008f337  test    rax, rax
0x18008f33a  jnz     short loc_18008F355
0x18008f33c  mov     [rbp+var_28], 401h
0x18008f343  lea     rdx, [rbp+var_30]
0x18008f347  lea     rcx, [rbp+var_30]
0x18008f34b  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f350  mov     ecx, [rbp+var_20]
0x18008f353  jmp     short loc_18008F362
0x18008f355  mov     ecx, [rax]
0x18008f357  mov     rax, [rax+20h]
0x18008f35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f360  xor     ecx, ecx; dwExceptionCode
0x18008f362  test    ecx, ecx
0x18008f364  jns     short loc_18008F376
0x18008f366  xor     r9d, r9d; lpArguments
0x18008f369  xor     r8d, r8d; nNumberOfArguments
0x18008f36c  lea     edx, [r9+1]; dwExceptionFlags
0x18008f370  call    cs:__imp_RaiseException
0x18008f376  mov     [rbp+arg_8], 0
0x18008f37e  test    rbx, rbx
0x18008f381  jz      loc_18008F4EB
0x18008f387  mov     rcx, rbx
0x18008f38a  jmp     loc_18008F2C0
0x18008f38f  xor     r14d, r14d
0x18008f392  mov     rcx, [rbp+arg_8]
0x18008f396  lea     r8, [rbp+arg_18]
0x18008f39a  mov     edx, 1
0x18008f39f  call    CdfMoveUlongTableEnumeratorPosition
0x18008f3a4  mov     r15d, eax
0x18008f3a7  test    eax, eax
0x18008f3a9  js      loc_18008F432
0x18008f3af  cmp     [rbp+arg_18], 1
0x18008f3b4  jnz     short loc_18008F3BB
0x18008f3b6  inc     r14d
0x18008f3b9  jmp     short loc_18008F392
0x18008f3bb  mov     rdx, [rbp+arg_8]
0x18008f3bf  mov     [rdi+30h], r14d
0x18008f3c3  mov     byte ptr [rdi+34h], 1
0x18008f3c7  xor     edi, edi
0x18008f3c9  mov     [rsi], r14d
0x18008f3cc  test    rdx, rdx
0x18008f3cf  jz      short loc_18008F37E
0x18008f3d1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f3d8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f3df  mov     [rbp+var_20], 0C00000E5h
0x18008f3e6  mov     [rbp+var_30], rcx
0x18008f3ea  test    rax, rax
0x18008f3ed  jnz     short loc_18008F408
0x18008f3ef  mov     [rbp+var_28], 401h
0x18008f3f6  lea     rdx, [rbp+var_30]
0x18008f3fa  lea     rcx, [rbp+var_30]
0x18008f3fe  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f403  mov     ecx, [rbp+var_20]
0x18008f406  jmp     short loc_18008F415
0x18008f408  mov     ecx, [rax]
0x18008f40a  mov     rax, [rax+20h]
0x18008f40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f413  xor     ecx, ecx; dwExceptionCode
0x18008f415  test    ecx, ecx
0x18008f417  jns     short loc_18008F429
0x18008f419  xor     r9d, r9d; lpArguments
0x18008f41c  xor     r8d, r8d; nNumberOfArguments
0x18008f41f  lea     edx, [r9+1]; dwExceptionFlags
0x18008f423  call    cs:__imp_RaiseException
0x18008f429  mov     [rbp+arg_8], rdi
0x18008f42d  jmp     loc_18008F37E
0x18008f432  cmp     r15d, cs:g_NTSTATUS_to_break_on_propagate
0x18008f439  jnz     short loc_18008F441
0x18008f43b  call    cs:__imp_DebugBreak
0x18008f441  mov     r9d, r15d; int
0x18008f444  lea     rcx, aStatusPropagat; "Status propagated"
0x18008f44b  mov     r8d, 0F1Ch; char *
0x18008f451  mov     rdx, r13; char *
0x18008f454  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008f459  mov     ecx, r15d
0x18008f45c  jmp     loc_18008F30E
0x18008f461  mov     [rbp+var_28], 0F0Bh
0x18008f468  lea     rdx, [rbp+var_30]
0x18008f46c  lea     rcx, [rbp+var_30]
0x18008f470  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f475  jmp     short loc_18008F4E8
0x18008f477  lea     rcx, [rbp+var_30]
0x18008f47b  mov     [rbp+var_28], 0F0Ah
0x18008f482  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008f487  mov     rdx, [rbp+arg_8]
0x18008f48b  test    rdx, rdx
0x18008f48e  jz      short loc_18008F4E8
0x18008f490  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008f497  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008f49e  mov     [rbp+var_8], 0C00000E5h
0x18008f4a5  mov     [rbp+var_18], rcx
0x18008f4a9  test    rax, rax
0x18008f4ac  jnz     short loc_18008F4C7
0x18008f4ae  mov     [rbp+var_10], 401h
0x18008f4b5  lea     rdx, [rbp+var_18]
0x18008f4b9  lea     rcx, [rbp+var_18]
0x18008f4bd  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008f4c2  mov     ecx, [rbp+var_8]
0x18008f4c5  jmp     short loc_18008F4D4
0x18008f4c7  mov     ecx, [rax]
0x18008f4c9  mov     rax, [rax+20h]
0x18008f4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4d2  xor     ecx, ecx; dwExceptionCode
0x18008f4d4  test    ecx, ecx
0x18008f4d6  jns     short loc_18008F4E8
0x18008f4d8  xor     r9d, r9d; lpArguments
0x18008f4db  xor     r8d, r8d; nNumberOfArguments
0x18008f4de  lea     edx, [r9+1]; dwExceptionFlags
0x18008f4e2  call    cs:__imp_RaiseException
0x18008f4e8  mov     edi, [rbp+var_20]
0x18008f4eb  mov     eax, edi
0x18008f4ed  add     rsp, 50h
0x18008f4f1  pop     r15
0x18008f4f3  pop     r14
0x18008f4f5  pop     r13
0x18008f4f7  pop     rdi
0x18008f4f8  pop     rsi
0x18008f4f9  pop     rbx
0x18008f4fa  pop     rbp
0x18008f4fb  retn
```
