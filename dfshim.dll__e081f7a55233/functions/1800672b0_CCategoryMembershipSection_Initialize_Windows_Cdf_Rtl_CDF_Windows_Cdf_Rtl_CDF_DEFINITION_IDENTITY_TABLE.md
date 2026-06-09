# CCategoryMembershipSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE)

- ea: `0x1800672b0`
- end: `0x18006745b`
- name: `?Initialize@CCategoryMembershipSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_DEFINITION_IDENTITY_TABLE@345@@Z`
- size: `427`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18008da20`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18004f2dc`
- `0x1800672b0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006731e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006741d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006731e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006741d`

## string_xrefs

- `0x1800672da`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006737d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180067327`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180067426`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCategoryMembershipSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
{
  bool v4; // zf
  int v6; // edi
  int v7; // eax
  int v8; // edx
  unsigned __int64 v9; // rcx
  int v11; // ebx
  __int64 v12; // r10
  __int64 v13; // r11
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  const char *v17; // [rsp+20h] [rbp-20h] BYREF
  int v18; // [rsp+28h] [rbp-18h]
  Windows::ErrorHandling::COM *v19; // [rsp+30h] [rbp-10h]
  int v20; // [rsp+60h] [rbp+20h] BYREF

  LODWORD(v19) = -1073741595;
  v4 = *(_QWORD *)(a1 + 24) == 0;
  v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
  if ( v4 )
  {
    v7 = CdfDuplicateHandle(a2);
    v6 = 0;
    if ( v7 < 0 )
      v6 = v7;
  }
  else
  {
    v18 = 142;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v17,
      &v17);
    v6 = (int)v19;
  }
  if ( v6 < 0 )
  {
    if ( v6 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x1403,
      v6,
      (unsigned int)v17);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  LODWORD(v19) = -1073741595;
  v4 = *(_QWORD *)(a1 + 32) == 0;
  v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
  if ( !v4 )
  {
    v18 = 142;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v17,
      &v17);
    v11 = (int)v19;
    goto LABEL_24;
  }
  *(_QWORD *)(a1 + 32) = 0;
  LODWORD(v19) = -1073741595;
  v17 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(a3) )
  {
    v18 = 959;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v17);
    v15 = (int)v19;
    goto LABEL_20;
  }
  v20 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(v12 + 24))(a3, v13, &v20);
  v15 = v14;
  if ( v14 == -1073741536 )
  {
    v15 = v20;
    if ( v20 < 0 )
      goto LABEL_20;
    goto LABEL_18;
  }
  if ( v14 >= 0 )
LABEL_18:
    v15 = 0;
LABEL_20:
  v16 = 0;
  if ( v15 < 0 )
    v16 = v15;
  v11 = 0;
  if ( v16 < 0 )
    v11 = v16;
LABEL_24:
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x1404,
      v11,
      (unsigned int)v17);
    v9 = (unsigned int)v11;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800672b0  mov     [rsp-18h+arg_8], rbx
0x1800672b5  mov     [rsp-18h+arg_10], rsi
0x1800672ba  push    rbp
0x1800672bb  push    rdi
0x1800672bc  push    r13
0x1800672be  mov     rbp, rsp
0x1800672c1  sub     rsp, 40h
0x1800672c5  mov     rax, rdx
0x1800672c8  mov     dword ptr [rbp+var_10], 0C00000E5h
0x1800672cf  lea     rdx, [rcx+18h]
0x1800672d3  mov     rbx, r8
0x1800672d6  cmp     qword ptr [rdx], 0
0x1800672da  lea     r13, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800672e1  mov     rsi, rcx
0x1800672e4  mov     [rbp+var_20], r13
0x1800672e8  jz      short loc_180067303
0x1800672ea  mov     [rbp+var_18], 8Eh
0x1800672f1  lea     rdx, [rbp+var_20]
0x1800672f5  lea     rcx, [rbp+var_20]
0x1800672f9  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800672fe  mov     edi, dword ptr [rbp+var_10]
0x180067301  jmp     short loc_180067312
0x180067303  mov     rcx, rax
0x180067306  call    CdfDuplicateHandle
0x18006730b  xor     edi, edi
0x18006730d  test    eax, eax
0x18006730f  cmovs   edi, eax
0x180067312  test    edi, edi
0x180067314  jns     short loc_18006734C
0x180067316  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006731c  jnz     short loc_180067324
0x18006731e  call    cs:__imp_DebugBreak
0x180067324  mov     r9d, edi; int
0x180067327  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006732e  mov     r8d, 1403h; char *
0x180067334  lea     rcx, aStatusPropagat; "Status propagated"
0x18006733b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067340  mov     ecx, edi; this
0x180067342  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180067347  jmp     loc_180067448
0x18006734c  lea     r11, [rsi+20h]
0x180067350  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067357  cmp     qword ptr [r11], 0
0x18006735b  mov     [rbp+var_20], r13
0x18006735f  jz      short loc_18006737D
0x180067361  mov     [rbp+var_18], 8Eh
0x180067368  lea     rdx, [rbp+var_20]
0x18006736c  lea     rcx, [rbp+var_20]
0x180067370  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067375  mov     ebx, dword ptr [rbp+var_10]
0x180067378  jmp     loc_180067411
0x18006737d  lea     rax, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067384  mov     qword ptr [r11], 0
0x18006738b  mov     r10, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_DEFINITION_IDENTITY_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_DEFINITION_IDENTITY_TABLE,_CDF_INTERNAL_DEFINITION_IDENTITY_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180067392  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067399  mov     [rbp+var_20], rax
0x18006739d  mov     dword ptr [rbp+var_10], 0C00000E5h
0x1800673a4  mov     [rbp+var_20], rax
0x1800673a8  test    r10, r10
0x1800673ab  jz      short loc_1800673F0
0x1800673ad  mov     rdx, r10
0x1800673b0  mov     rcx, rbx
0x1800673b3  call    RtlIsTypeSafeHandleValid
0x1800673b8  test    al, al
0x1800673ba  jz      short loc_1800673F0
0x1800673bc  mov     [rbp+arg_0], 0
0x1800673c3  lea     r8, [rbp+arg_0]
0x1800673c7  mov     rax, [r10+18h]
0x1800673cb  mov     rdx, r11
0x1800673ce  mov     rcx, rbx
0x1800673d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673d6  mov     ecx, eax
0x1800673d8  cmp     eax, 0C0000120h
0x1800673dd  jnz     short loc_1800673E8
0x1800673df  mov     ecx, [rbp+arg_0]
0x1800673e2  test    ecx, ecx
0x1800673e4  jns     short loc_1800673EC
0x1800673e6  jmp     short loc_180067403
0x1800673e8  test    eax, eax
0x1800673ea  js      short loc_180067403
0x1800673ec  xor     ecx, ecx
0x1800673ee  jmp     short loc_180067403
0x1800673f0  mov     [rbp+var_18], 3BFh
0x1800673f7  lea     rcx, [rbp+var_20]
0x1800673fb  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180067400  mov     ecx, dword ptr [rbp+var_10]
0x180067403  xor     eax, eax
0x180067405  test    ecx, ecx
0x180067407  cmovs   eax, ecx
0x18006740a  xor     ebx, ebx
0x18006740c  test    eax, eax
0x18006740e  cmovs   ebx, eax
0x180067411  test    ebx, ebx
0x180067413  jns     short loc_180067446
0x180067415  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006741b  jnz     short loc_180067423
0x18006741d  call    cs:__imp_DebugBreak
0x180067423  mov     r9d, ebx; int
0x180067426  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006742d  mov     r8d, 1404h; char *
0x180067433  lea     rcx, aStatusPropagat; "Status propagated"
0x18006743a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006743f  mov     ecx, ebx
0x180067441  jmp     loc_180067342
0x180067446  xor     eax, eax
0x180067448  mov     rbx, [rsp+40h+arg_8]
0x18006744d  mov     rsi, [rsp+40h+arg_10]
0x180067452  add     rsp, 40h
0x180067456  pop     r13
0x180067458  pop     rdi
0x180067459  pop     rbp
0x18006745a  retn
```
