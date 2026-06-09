# CEventTagSection::get_Count(ulong *)

- ea: `0x180090fe0`
- end: `0x180091240`
- name: `?get_Count@CEventTagSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CEventTagSection *__hidden this, unsigned int *)`
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
- `0x180090fe0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009109d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091171`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18009109d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091171`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091127`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091221`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091127`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091221`

## string_xrefs

- `0x1800910d8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800911d6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180090ffa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventTagSection::get_Count(CEventTagSection *this, unsigned int *a2)
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
    v16 = 7743;
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
    v16 = 7744;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 7745;
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
        (const char *)0x1E4D,
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
        (const char *)0x1E49,
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
0x180090fe0  mov     [rsp-28h+arg_0], rbx
0x180090fe5  push    rbp
0x180090fe6  push    rsi
0x180090fe7  push    rdi
0x180090fe8  push    r12
0x180090fea  push    r14
0x180090fec  mov     rbp, rsp
0x180090fef  sub     rsp, 50h
0x180090ff3  mov     [rbp+var_20], 8007054Fh
0x180090ffa  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091001  mov     [rbp+var_30], r12
0x180091005  mov     rdi, rdx
0x180091008  mov     [rbp+arg_8], 0
0x180091010  mov     rbx, rcx
0x180091013  mov     [rbp+arg_10], 0
0x18009101b  test    rdx, rdx
0x18009101e  jz      loc_1800911B6
0x180091024  mov     dword ptr [rdx], 0
0x18009102a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180091031  test    rdx, rdx
0x180091034  jz      loc_1800911A0
0x18009103a  mov     rcx, [rcx+18h]
0x18009103e  call    RtlIsTypeSafeHandleValid
0x180091043  test    al, al
0x180091045  jz      loc_1800911A0
0x18009104b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180091052  test    rdx, rdx
0x180091055  jz      loc_180091197
0x18009105b  mov     rcx, [rbx+20h]
0x18009105f  call    RtlIsTypeSafeHandleValid
0x180091064  test    al, al
0x180091066  jz      loc_180091197
0x18009106c  cmp     byte ptr [rbx+2Ch], 0
0x180091070  jz      short loc_18009107E
0x180091072  mov     eax, [rbx+28h]
0x180091075  xor     ebx, ebx
0x180091077  mov     [rdi], eax
0x180091079  jmp     loc_18009122A
0x18009107e  mov     rcx, [rbx+20h]
0x180091082  lea     rdx, [rbp+arg_8]
0x180091086  call    CdfEnumerateStringTable
0x18009108b  mov     esi, eax
0x18009108d  test    eax, eax
0x18009108f  jns     loc_180091132
0x180091095  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18009109b  jnz     short loc_1800910A3
0x18009109d  call    cs:__imp_DebugBreak
0x1800910a3  mov     r9d, esi; int
0x1800910a6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800910ad  mov     r8d, 1E49h; char *
0x1800910b3  mov     rdx, r12; char *
0x1800910b6  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800910bb  mov     ecx, esi; this
0x1800910bd  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800910c2  mov     ebx, eax
0x1800910c4  mov     rdx, [rbp+arg_8]
0x1800910c8  test    rdx, rdx
0x1800910cb  jz      loc_18009122A
0x1800910d1  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800910d8  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800910df  mov     [rbp+var_20], 0C00000E5h
0x1800910e6  mov     [rbp+var_30], rcx
0x1800910ea  test    rax, rax
0x1800910ed  jnz     short loc_180091108
0x1800910ef  mov     [rbp+var_28], 401h
0x1800910f6  lea     rdx, [rbp+var_30]
0x1800910fa  lea     rcx, [rbp+var_30]
0x1800910fe  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091103  mov     ecx, [rbp+var_20]
0x180091106  jmp     short loc_180091115
0x180091108  mov     ecx, [rax]
0x18009110a  mov     rax, [rax+20h]
0x18009110e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091113  xor     ecx, ecx; dwExceptionCode
0x180091115  test    ecx, ecx
0x180091117  jns     loc_18009122A
0x18009111d  xor     r9d, r9d; lpArguments
0x180091120  xor     r8d, r8d; nNumberOfArguments
0x180091123  lea     edx, [r9+1]; dwExceptionFlags
0x180091127  call    cs:__imp_RaiseException
0x18009112d  jmp     loc_18009122A
0x180091132  xor     esi, esi
0x180091134  mov     rcx, [rbp+arg_8]
0x180091138  lea     r8, [rbp+arg_10]
0x18009113c  mov     edx, 1
0x180091141  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180091146  mov     r14d, eax
0x180091149  test    eax, eax
0x18009114b  js      short loc_180091168
0x18009114d  cmp     [rbp+arg_10], 1
0x180091152  jnz     short loc_180091158
0x180091154  inc     esi
0x180091156  jmp     short loc_180091134
0x180091158  mov     [rbx+28h], esi
0x18009115b  mov     byte ptr [rbx+2Ch], 1
0x18009115f  xor     ebx, ebx
0x180091161  mov     [rdi], esi
0x180091163  jmp     loc_1800910C4
0x180091168  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18009116f  jnz     short loc_180091177
0x180091171  call    cs:__imp_DebugBreak
0x180091177  mov     r9d, r14d; int
0x18009117a  lea     rcx, aStatusPropagat; "Status propagated"
0x180091181  mov     r8d, 1E4Dh; char *
0x180091187  mov     rdx, r12; char *
0x18009118a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009118f  mov     ecx, r14d
0x180091192  jmp     loc_1800910BD
0x180091197  mov     [rbp+var_28], 1E41h
0x18009119e  jmp     short loc_1800911A7
0x1800911a0  mov     [rbp+var_28], 1E40h
0x1800911a7  lea     rdx, [rbp+var_30]
0x1800911ab  lea     rcx, [rbp+var_30]
0x1800911af  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800911b4  jmp     short loc_180091227
0x1800911b6  lea     rcx, [rbp+var_30]
0x1800911ba  mov     [rbp+var_28], 1E3Fh
0x1800911c1  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800911c6  mov     rdx, [rbp+arg_8]
0x1800911ca  test    rdx, rdx
0x1800911cd  jz      short loc_180091227
0x1800911cf  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x1800911d6  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800911dd  mov     [rbp+var_8], 0C00000E5h
0x1800911e4  mov     [rbp+var_18], rcx
0x1800911e8  test    rax, rax
0x1800911eb  jnz     short loc_180091206
0x1800911ed  mov     [rbp+var_10], 401h
0x1800911f4  lea     rdx, [rbp+var_18]
0x1800911f8  lea     rcx, [rbp+var_18]
0x1800911fc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091201  mov     ecx, [rbp+var_8]
0x180091204  jmp     short loc_180091213
0x180091206  mov     ecx, [rax]
0x180091208  mov     rax, [rax+20h]
0x18009120c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091211  xor     ecx, ecx; dwExceptionCode
0x180091213  test    ecx, ecx
0x180091215  jns     short loc_180091227
0x180091217  xor     r9d, r9d; lpArguments
0x18009121a  xor     r8d, r8d; nNumberOfArguments
0x18009121d  lea     edx, [r9+1]; dwExceptionFlags
0x180091221  call    cs:__imp_RaiseException
0x180091227  mov     ebx, [rbp+var_20]
0x18009122a  mov     eax, ebx
0x18009122c  mov     rbx, [rsp+50h+arg_0]
0x180091234  add     rsp, 50h
0x180091238  pop     r14
0x18009123a  pop     r12
0x18009123c  pop     rdi
0x18009123d  pop     rsi
0x18009123e  pop     rbp
0x18009123f  retn
```
