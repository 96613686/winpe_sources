# CRegistryKeySection::get_Count(ulong *)

- ea: `0x180091e80`
- end: `0x1800920e0`
- name: `?get_Count@CRegistryKeySection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CRegistryKeySection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x18004f2dc`
- `0x18007338c`
- `0x180091e80`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091f3d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092011`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091f3d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180092011`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091fc7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800920c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091fc7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800920c1`

## string_xrefs

- `0x180091f78`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180092076`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091e9a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CRegistryKeySection::get_Count(CRegistryKeySection *this, unsigned int *a2)
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
    v16 = 8050;
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
    v16 = 8051;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 8052;
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
        (const char *)0x1F80,
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
        (const char *)0x1F7C,
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
0x180091e80  mov     [rsp-28h+arg_0], rbx
0x180091e85  push    rbp
0x180091e86  push    rsi
0x180091e87  push    rdi
0x180091e88  push    r12
0x180091e8a  push    r14
0x180091e8c  mov     rbp, rsp
0x180091e8f  sub     rsp, 50h
0x180091e93  mov     [rbp+var_20], 8007054Fh
0x180091e9a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091ea1  mov     [rbp+var_30], r12
0x180091ea5  mov     rdi, rdx
0x180091ea8  mov     [rbp+arg_8], 0
0x180091eb0  mov     rbx, rcx
0x180091eb3  mov     [rbp+arg_10], 0
0x180091ebb  test    rdx, rdx
0x180091ebe  jz      loc_180092056
0x180091ec4  mov     dword ptr [rdx], 0
0x180091eca  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180091ed1  test    rdx, rdx
0x180091ed4  jz      loc_180092040
0x180091eda  mov     rcx, [rcx+18h]
0x180091ede  call    RtlIsTypeSafeHandleValid
0x180091ee3  test    al, al
0x180091ee5  jz      loc_180092040
0x180091eeb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180091ef2  test    rdx, rdx
0x180091ef5  jz      loc_180092037
0x180091efb  mov     rcx, [rbx+20h]
0x180091eff  call    RtlIsTypeSafeHandleValid
0x180091f04  test    al, al
0x180091f06  jz      loc_180092037
0x180091f0c  cmp     byte ptr [rbx+2Ch], 0
0x180091f10  jz      short loc_180091F1E
0x180091f12  mov     eax, [rbx+28h]
0x180091f15  xor     ebx, ebx
0x180091f17  mov     [rdi], eax
0x180091f19  jmp     loc_1800920CA
0x180091f1e  mov     rcx, [rbx+20h]
0x180091f22  lea     rdx, [rbp+arg_8]
0x180091f26  call    CdfEnumerateStringTable
0x180091f2b  mov     esi, eax
0x180091f2d  test    eax, eax
0x180091f2f  jns     loc_180091FD2
0x180091f35  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180091f3b  jnz     short loc_180091F43
0x180091f3d  call    cs:__imp_DebugBreak
0x180091f43  mov     r9d, esi; int
0x180091f46  lea     rcx, aStatusPropagat; "Status propagated"
0x180091f4d  mov     r8d, 1F7Ch; char *
0x180091f53  mov     rdx, r12; char *
0x180091f56  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180091f5b  mov     ecx, esi; this
0x180091f5d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180091f62  mov     ebx, eax
0x180091f64  mov     rdx, [rbp+arg_8]
0x180091f68  test    rdx, rdx
0x180091f6b  jz      loc_1800920CA
0x180091f71  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091f78  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091f7f  mov     [rbp+var_20], 0C00000E5h
0x180091f86  mov     [rbp+var_30], rcx
0x180091f8a  test    rax, rax
0x180091f8d  jnz     short loc_180091FA8
0x180091f8f  mov     [rbp+var_28], 401h
0x180091f96  lea     rdx, [rbp+var_30]
0x180091f9a  lea     rcx, [rbp+var_30]
0x180091f9e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091fa3  mov     ecx, [rbp+var_20]
0x180091fa6  jmp     short loc_180091FB5
0x180091fa8  mov     ecx, [rax]
0x180091faa  mov     rax, [rax+20h]
0x180091fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091fb3  xor     ecx, ecx; dwExceptionCode
0x180091fb5  test    ecx, ecx
0x180091fb7  jns     loc_1800920CA
0x180091fbd  xor     r9d, r9d; lpArguments
0x180091fc0  xor     r8d, r8d; nNumberOfArguments
0x180091fc3  lea     edx, [r9+1]; dwExceptionFlags
0x180091fc7  call    cs:__imp_RaiseException
0x180091fcd  jmp     loc_1800920CA
0x180091fd2  xor     esi, esi
0x180091fd4  mov     rcx, [rbp+arg_8]
0x180091fd8  lea     r8, [rbp+arg_10]
0x180091fdc  mov     edx, 1
0x180091fe1  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180091fe6  mov     r14d, eax
0x180091fe9  test    eax, eax
0x180091feb  js      short loc_180092008
0x180091fed  cmp     [rbp+arg_10], 1
0x180091ff2  jnz     short loc_180091FF8
0x180091ff4  inc     esi
0x180091ff6  jmp     short loc_180091FD4
0x180091ff8  mov     [rbx+28h], esi
0x180091ffb  mov     byte ptr [rbx+2Ch], 1
0x180091fff  xor     ebx, ebx
0x180092001  mov     [rdi], esi
0x180092003  jmp     loc_180091F64
0x180092008  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009200f  jnz     short loc_180092017
0x180092011  call    cs:__imp_DebugBreak
0x180092017  mov     r9d, r14d; int
0x18009201a  lea     rcx, aStatusPropagat; "Status propagated"
0x180092021  mov     r8d, 1F80h; char *
0x180092027  mov     rdx, r12; char *
0x18009202a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009202f  mov     ecx, r14d
0x180092032  jmp     loc_180091F5D
0x180092037  mov     [rbp+var_28], 1F74h
0x18009203e  jmp     short loc_180092047
0x180092040  mov     [rbp+var_28], 1F73h
0x180092047  lea     rdx, [rbp+var_30]
0x18009204b  lea     rcx, [rbp+var_30]
0x18009204f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180092054  jmp     short loc_1800920C7
0x180092056  lea     rcx, [rbp+var_30]
0x18009205a  mov     [rbp+var_28], 1F72h
0x180092061  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180092066  mov     rdx, [rbp+arg_8]
0x18009206a  test    rdx, rdx
0x18009206d  jz      short loc_1800920C7
0x18009206f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180092076  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009207d  mov     [rbp+var_8], 0C00000E5h
0x180092084  mov     [rbp+var_18], rcx
0x180092088  test    rax, rax
0x18009208b  jnz     short loc_1800920A6
0x18009208d  mov     [rbp+var_10], 401h
0x180092094  lea     rdx, [rbp+var_18]
0x180092098  lea     rcx, [rbp+var_18]
0x18009209c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800920a1  mov     ecx, [rbp+var_8]
0x1800920a4  jmp     short loc_1800920B3
0x1800920a6  mov     ecx, [rax]
0x1800920a8  mov     rax, [rax+20h]
0x1800920ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800920b1  xor     ecx, ecx; dwExceptionCode
0x1800920b3  test    ecx, ecx
0x1800920b5  jns     short loc_1800920C7
0x1800920b7  xor     r9d, r9d; lpArguments
0x1800920ba  xor     r8d, r8d; nNumberOfArguments
0x1800920bd  lea     edx, [r9+1]; dwExceptionFlags
0x1800920c1  call    cs:__imp_RaiseException
0x1800920c7  mov     ebx, [rbp+var_20]
0x1800920ca  mov     eax, ebx
0x1800920cc  mov     rbx, [rsp+50h+arg_0]
0x1800920d4  add     rsp, 50h
0x1800920d8  pop     r14
0x1800920da  pop     r12
0x1800920dc  pop     rdi
0x1800920dd  pop     rsi
0x1800920de  pop     rbp
0x1800920df  retn
```
