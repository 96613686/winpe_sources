# CStringSection::get_Count(ulong *)

- ea: `0x1800920f0`
- end: `0x180092350`
- name: `?get_Count@CStringSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CStringSection *__hidden this, unsigned int *)`
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
- `0x1800920f0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800921ad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092281`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800921ad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092281`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092237`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092331`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092237`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180092331`

## string_xrefs

- `0x1800921e8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800922e6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18009210a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CStringSection::get_Count(CStringSection *this, unsigned int *a2)
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
    v16 = 6371;
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
    v16 = 6372;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6373;
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
        (const char *)0x18F1,
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
        (const char *)0x18ED,
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
0x1800920f0  mov     [rsp-28h+arg_0], rbx
0x1800920f5  push    rbp
0x1800920f6  push    rsi
0x1800920f7  push    rdi
0x1800920f8  push    r12
0x1800920fa  push    r14
0x1800920fc  mov     rbp, rsp
0x1800920ff  sub     rsp, 50h
0x180092103  mov     [rbp+var_20], 8007054Fh
0x18009210a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180092111  mov     [rbp+var_30], r12
0x180092115  mov     rdi, rdx
0x180092118  mov     [rbp+arg_8], 0
0x180092120  mov     rbx, rcx
0x180092123  mov     [rbp+arg_10], 0
0x18009212b  test    rdx, rdx
0x18009212e  jz      loc_1800922C6
0x180092134  mov     dword ptr [rdx], 0
0x18009213a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180092141  test    rdx, rdx
0x180092144  jz      loc_1800922B0
0x18009214a  mov     rcx, [rcx+18h]
0x18009214e  call    RtlIsTypeSafeHandleValid
0x180092153  test    al, al
0x180092155  jz      loc_1800922B0
0x18009215b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180092162  test    rdx, rdx
0x180092165  jz      loc_1800922A7
0x18009216b  mov     rcx, [rbx+20h]
0x18009216f  call    RtlIsTypeSafeHandleValid
0x180092174  test    al, al
0x180092176  jz      loc_1800922A7
0x18009217c  cmp     byte ptr [rbx+2Ch], 0
0x180092180  jz      short loc_18009218E
0x180092182  mov     eax, [rbx+28h]
0x180092185  xor     ebx, ebx
0x180092187  mov     [rdi], eax
0x180092189  jmp     loc_18009233A
0x18009218e  mov     rcx, [rbx+20h]
0x180092192  lea     rdx, [rbp+arg_8]
0x180092196  call    CdfEnumerateStringTable
0x18009219b  mov     esi, eax
0x18009219d  test    eax, eax
0x18009219f  jns     loc_180092242
0x1800921a5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800921ab  jnz     short loc_1800921B3
0x1800921ad  call    cs:__imp_DebugBreak
0x1800921b3  mov     r9d, esi; int
0x1800921b6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800921bd  mov     r8d, 18EDh; char *
0x1800921c3  mov     rdx, r12; char *
0x1800921c6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800921cb  mov     ecx, esi; this
0x1800921cd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800921d2  mov     ebx, eax
0x1800921d4  mov     rdx, [rbp+arg_8]
0x1800921d8  test    rdx, rdx
0x1800921db  jz      loc_18009233A
0x1800921e1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800921e8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800921ef  mov     [rbp+var_20], 0C00000E5h
0x1800921f6  mov     [rbp+var_30], rcx
0x1800921fa  test    rax, rax
0x1800921fd  jnz     short loc_180092218
0x1800921ff  mov     [rbp+var_28], 401h
0x180092206  lea     rdx, [rbp+var_30]
0x18009220a  lea     rcx, [rbp+var_30]
0x18009220e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092213  mov     ecx, [rbp+var_20]
0x180092216  jmp     short loc_180092225
0x180092218  mov     ecx, [rax]
0x18009221a  mov     rax, [rax+20h]
0x18009221e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092223  xor     ecx, ecx; dwExceptionCode
0x180092225  test    ecx, ecx
0x180092227  jns     loc_18009233A
0x18009222d  xor     r9d, r9d; lpArguments
0x180092230  xor     r8d, r8d; nNumberOfArguments
0x180092233  lea     edx, [r9+1]; dwExceptionFlags
0x180092237  call    cs:__imp_RaiseException
0x18009223d  jmp     loc_18009233A
0x180092242  xor     esi, esi
0x180092244  mov     rcx, [rbp+arg_8]
0x180092248  lea     r8, [rbp+arg_10]
0x18009224c  mov     edx, 1
0x180092251  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180092256  mov     r14d, eax
0x180092259  test    eax, eax
0x18009225b  js      short loc_180092278
0x18009225d  cmp     [rbp+arg_10], 1
0x180092262  jnz     short loc_180092268
0x180092264  inc     esi
0x180092266  jmp     short loc_180092244
0x180092268  mov     [rbx+28h], esi
0x18009226b  mov     byte ptr [rbx+2Ch], 1
0x18009226f  xor     ebx, ebx
0x180092271  mov     [rdi], esi
0x180092273  jmp     loc_1800921D4
0x180092278  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009227f  jnz     short loc_180092287
0x180092281  call    cs:__imp_DebugBreak
0x180092287  mov     r9d, r14d; int
0x18009228a  lea     rcx, aStatusPropagat; "Status propagated"
0x180092291  mov     r8d, 18F1h; char *
0x180092297  mov     rdx, r12; char *
0x18009229a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009229f  mov     ecx, r14d
0x1800922a2  jmp     loc_1800921CD
0x1800922a7  mov     [rbp+var_28], 18E5h
0x1800922ae  jmp     short loc_1800922B7
0x1800922b0  mov     [rbp+var_28], 18E4h
0x1800922b7  lea     rdx, [rbp+var_30]
0x1800922bb  lea     rcx, [rbp+var_30]
0x1800922bf  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800922c4  jmp     short loc_180092337
0x1800922c6  lea     rcx, [rbp+var_30]
0x1800922ca  mov     [rbp+var_28], 18E3h
0x1800922d1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800922d6  mov     rdx, [rbp+arg_8]
0x1800922da  test    rdx, rdx
0x1800922dd  jz      short loc_180092337
0x1800922df  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800922e6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800922ed  mov     [rbp+var_8], 0C00000E5h
0x1800922f4  mov     [rbp+var_18], rcx
0x1800922f8  test    rax, rax
0x1800922fb  jnz     short loc_180092316
0x1800922fd  mov     [rbp+var_10], 401h
0x180092304  lea     rdx, [rbp+var_18]
0x180092308  lea     rcx, [rbp+var_18]
0x18009230c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092311  mov     ecx, [rbp+var_8]
0x180092314  jmp     short loc_180092323
0x180092316  mov     ecx, [rax]
0x180092318  mov     rax, [rax+20h]
0x18009231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092321  xor     ecx, ecx; dwExceptionCode
0x180092323  test    ecx, ecx
0x180092325  jns     short loc_180092337
0x180092327  xor     r9d, r9d; lpArguments
0x18009232a  xor     r8d, r8d; nNumberOfArguments
0x18009232d  lea     edx, [r9+1]; dwExceptionFlags
0x180092331  call    cs:__imp_RaiseException
0x180092337  mov     ebx, [rbp+var_20]
0x18009233a  mov     eax, ebx
0x18009233c  mov     rbx, [rsp+50h+arg_0]
0x180092344  add     rsp, 50h
0x180092348  pop     r14
0x18009234a  pop     r12
0x18009234c  pop     rdi
0x18009234d  pop     rsi
0x18009234e  pop     rbp
0x18009234f  retn
```
