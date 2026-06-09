# CDirectorySection::get_Count(ulong *)

- ea: `0x180090620`
- end: `0x180090880`
- name: `?get_Count@CDirectorySection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CDirectorySection *__hidden this, unsigned int *)`
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
- `0x180090620`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800906dd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800907b1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800906dd`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800907b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090767`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090861`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090767`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180090861`

## string_xrefs

- `0x180090718`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090816`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18009063a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CDirectorySection::get_Count(CDirectorySection *this, unsigned int *a2)
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
    v16 = 8205;
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
    v16 = 8206;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 8207;
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
        (const char *)0x201B,
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
        (const char *)0x2017,
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
0x180090620  mov     [rsp-28h+arg_0], rbx
0x180090625  push    rbp
0x180090626  push    rsi
0x180090627  push    rdi
0x180090628  push    r12
0x18009062a  push    r14
0x18009062c  mov     rbp, rsp
0x18009062f  sub     rsp, 50h
0x180090633  mov     [rbp+var_20], 8007054Fh
0x18009063a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180090641  mov     [rbp+var_30], r12
0x180090645  mov     rdi, rdx
0x180090648  mov     [rbp+arg_8], 0
0x180090650  mov     rbx, rcx
0x180090653  mov     [rbp+arg_10], 0
0x18009065b  test    rdx, rdx
0x18009065e  jz      loc_1800907F6
0x180090664  mov     dword ptr [rdx], 0
0x18009066a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180090671  test    rdx, rdx
0x180090674  jz      loc_1800907E0
0x18009067a  mov     rcx, [rcx+18h]
0x18009067e  call    RtlIsTypeSafeHandleValid
0x180090683  test    al, al
0x180090685  jz      loc_1800907E0
0x18009068b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180090692  test    rdx, rdx
0x180090695  jz      loc_1800907D7
0x18009069b  mov     rcx, [rbx+20h]
0x18009069f  call    RtlIsTypeSafeHandleValid
0x1800906a4  test    al, al
0x1800906a6  jz      loc_1800907D7
0x1800906ac  cmp     byte ptr [rbx+2Ch], 0
0x1800906b0  jz      short loc_1800906BE
0x1800906b2  mov     eax, [rbx+28h]
0x1800906b5  xor     ebx, ebx
0x1800906b7  mov     [rdi], eax
0x1800906b9  jmp     loc_18009086A
0x1800906be  mov     rcx, [rbx+20h]
0x1800906c2  lea     rdx, [rbp+arg_8]
0x1800906c6  call    CdfEnumerateStringTable
0x1800906cb  mov     esi, eax
0x1800906cd  test    eax, eax
0x1800906cf  jns     loc_180090772
0x1800906d5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800906db  jnz     short loc_1800906E3
0x1800906dd  call    cs:__imp_DebugBreak
0x1800906e3  mov     r9d, esi; int
0x1800906e6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800906ed  mov     r8d, 2017h; char *
0x1800906f3  mov     rdx, r12; char *
0x1800906f6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800906fb  mov     ecx, esi; this
0x1800906fd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180090702  mov     ebx, eax
0x180090704  mov     rdx, [rbp+arg_8]
0x180090708  test    rdx, rdx
0x18009070b  jz      loc_18009086A
0x180090711  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090718  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009071f  mov     [rbp+var_20], 0C00000E5h
0x180090726  mov     [rbp+var_30], rcx
0x18009072a  test    rax, rax
0x18009072d  jnz     short loc_180090748
0x18009072f  mov     [rbp+var_28], 401h
0x180090736  lea     rdx, [rbp+var_30]
0x18009073a  lea     rcx, [rbp+var_30]
0x18009073e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090743  mov     ecx, [rbp+var_20]
0x180090746  jmp     short loc_180090755
0x180090748  mov     ecx, [rax]
0x18009074a  mov     rax, [rax+20h]
0x18009074e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090753  xor     ecx, ecx; dwExceptionCode
0x180090755  test    ecx, ecx
0x180090757  jns     loc_18009086A
0x18009075d  xor     r9d, r9d; lpArguments
0x180090760  xor     r8d, r8d; nNumberOfArguments
0x180090763  lea     edx, [r9+1]; dwExceptionFlags
0x180090767  call    cs:__imp_RaiseException
0x18009076d  jmp     loc_18009086A
0x180090772  xor     esi, esi
0x180090774  mov     rcx, [rbp+arg_8]
0x180090778  lea     r8, [rbp+arg_10]
0x18009077c  mov     edx, 1
0x180090781  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180090786  mov     r14d, eax
0x180090789  test    eax, eax
0x18009078b  js      short loc_1800907A8
0x18009078d  cmp     [rbp+arg_10], 1
0x180090792  jnz     short loc_180090798
0x180090794  inc     esi
0x180090796  jmp     short loc_180090774
0x180090798  mov     [rbx+28h], esi
0x18009079b  mov     byte ptr [rbx+2Ch], 1
0x18009079f  xor     ebx, ebx
0x1800907a1  mov     [rdi], esi
0x1800907a3  jmp     loc_180090704
0x1800907a8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x1800907af  jnz     short loc_1800907B7
0x1800907b1  call    cs:__imp_DebugBreak
0x1800907b7  mov     r9d, r14d; int
0x1800907ba  lea     rcx, aStatusPropagat; "Status propagated"
0x1800907c1  mov     r8d, 201Bh; char *
0x1800907c7  mov     rdx, r12; char *
0x1800907ca  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800907cf  mov     ecx, r14d
0x1800907d2  jmp     loc_1800906FD
0x1800907d7  mov     [rbp+var_28], 200Fh
0x1800907de  jmp     short loc_1800907E7
0x1800907e0  mov     [rbp+var_28], 200Eh
0x1800907e7  lea     rdx, [rbp+var_30]
0x1800907eb  lea     rcx, [rbp+var_30]
0x1800907ef  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800907f4  jmp     short loc_180090867
0x1800907f6  lea     rcx, [rbp+var_30]
0x1800907fa  mov     [rbp+var_28], 200Dh
0x180090801  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180090806  mov     rdx, [rbp+arg_8]
0x18009080a  test    rdx, rdx
0x18009080d  jz      short loc_180090867
0x18009080f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180090816  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009081d  mov     [rbp+var_8], 0C00000E5h
0x180090824  mov     [rbp+var_18], rcx
0x180090828  test    rax, rax
0x18009082b  jnz     short loc_180090846
0x18009082d  mov     [rbp+var_10], 401h
0x180090834  lea     rdx, [rbp+var_18]
0x180090838  lea     rcx, [rbp+var_18]
0x18009083c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180090841  mov     ecx, [rbp+var_8]
0x180090844  jmp     short loc_180090853
0x180090846  mov     ecx, [rax]
0x180090848  mov     rax, [rax+20h]
0x18009084c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090851  xor     ecx, ecx; dwExceptionCode
0x180090853  test    ecx, ecx
0x180090855  jns     short loc_180090867
0x180090857  xor     r9d, r9d; lpArguments
0x18009085a  xor     r8d, r8d; nNumberOfArguments
0x18009085d  lea     edx, [r9+1]; dwExceptionFlags
0x180090861  call    cs:__imp_RaiseException
0x180090867  mov     ebx, [rbp+var_20]
0x18009086a  mov     eax, ebx
0x18009086c  mov     rbx, [rsp+50h+arg_0]
0x180090874  add     rsp, 50h
0x180090878  pop     r14
0x18009087a  pop     r12
0x18009087c  pop     rdi
0x18009087d  pop     rsi
0x18009087e  pop     rbp
0x18009087f  retn
```
