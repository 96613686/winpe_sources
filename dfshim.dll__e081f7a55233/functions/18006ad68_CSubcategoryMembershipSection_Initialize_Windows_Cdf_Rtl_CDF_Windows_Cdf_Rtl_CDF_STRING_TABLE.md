# CSubcategoryMembershipSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006ad68`
- end: `0x18006ae76`
- name: `?Initialize@CSubcategoryMembershipSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005c6d8`
- `0x18005f900`
- `0x18009cd40`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006ad68`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006adcf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ae43`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006adcf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ae43`

## string_xrefs

- `0x18006ad8b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006add8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006ae4c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CSubcategoryMembershipSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
{
  bool v4; // zf
  int v6; // edi
  int v7; // eax
  int v8; // edx
  unsigned __int64 v9; // rcx
  int v11; // ebx
  int v12; // eax
  const char *v13; // [rsp+20h] [rbp-20h] BYREF
  int v14; // [rsp+28h] [rbp-18h]
  Windows::ErrorHandling::COM *v15; // [rsp+30h] [rbp-10h]

  LODWORD(v15) = -1073741595;
  v4 = *(_QWORD *)(a1 + 24) == 0;
  v13 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
  if ( v4 )
  {
    v7 = CdfDuplicateHandle(a2);
    v6 = 0;
    if ( v7 < 0 )
      v6 = v7;
  }
  else
  {
    v14 = 142;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v13,
      &v13);
    v6 = (int)v15;
  }
  if ( v6 < 0 )
  {
    if ( v6 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x149B,
      v6,
      (unsigned int)v13);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  LODWORD(v15) = -1073741595;
  v4 = *(_QWORD *)(a1 + 32) == 0;
  v13 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
  if ( v4 )
  {
    v12 = Windows::Cdf::Rtl::Duplicate(a3);
    v11 = 0;
    if ( v12 < 0 )
      v11 = v12;
  }
  else
  {
    v14 = 142;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v13,
      &v13);
    v11 = (int)v15;
  }
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x149C,
      v11,
      (unsigned int)v13);
    v9 = (unsigned int)v11;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18006ad68  push    rbp
0x18006ad6a  push    rbx
0x18006ad6b  push    rsi
0x18006ad6c  push    rdi
0x18006ad6d  push    r12
0x18006ad6f  mov     rbp, rsp
0x18006ad72  sub     rsp, 40h
0x18006ad76  mov     rax, rdx
0x18006ad79  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006ad80  lea     rdx, [rcx+18h]
0x18006ad84  mov     rbx, r8
0x18006ad87  cmp     qword ptr [rdx], 0
0x18006ad8b  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006ad92  mov     rsi, rcx
0x18006ad95  mov     [rbp+var_20], r12
0x18006ad99  jz      short loc_18006ADB4
0x18006ad9b  mov     [rbp+var_18], 8Eh
0x18006ada2  lea     rdx, [rbp+var_20]
0x18006ada6  lea     rcx, [rbp+var_20]
0x18006adaa  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006adaf  mov     edi, dword ptr [rbp+var_10]
0x18006adb2  jmp     short loc_18006ADC3
0x18006adb4  mov     rcx, rax
0x18006adb7  call    CdfDuplicateHandle
0x18006adbc  xor     edi, edi
0x18006adbe  test    eax, eax
0x18006adc0  cmovs   edi, eax
0x18006adc3  test    edi, edi
0x18006adc5  jns     short loc_18006ADFA
0x18006adc7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006adcd  jnz     short loc_18006ADD5
0x18006adcf  call    cs:__imp_DebugBreak
0x18006add5  mov     r9d, edi; int
0x18006add8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006addf  mov     r8d, 149Bh; char *
0x18006ade5  lea     rcx, aStatusPropagat; "Status propagated"
0x18006adec  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006adf1  mov     ecx, edi; this
0x18006adf3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006adf8  jmp     short loc_18006AE6B
0x18006adfa  lea     rdx, [rsi+20h]
0x18006adfe  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006ae05  cmp     qword ptr [rdx], 0
0x18006ae09  mov     [rbp+var_20], r12
0x18006ae0d  jz      short loc_18006AE28
0x18006ae0f  mov     [rbp+var_18], 8Eh
0x18006ae16  lea     rdx, [rbp+var_20]
0x18006ae1a  lea     rcx, [rbp+var_20]
0x18006ae1e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006ae23  mov     ebx, dword ptr [rbp+var_10]
0x18006ae26  jmp     short loc_18006AE37
0x18006ae28  mov     rcx, rbx
0x18006ae2b  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006ae30  xor     ebx, ebx
0x18006ae32  test    eax, eax
0x18006ae34  cmovs   ebx, eax
0x18006ae37  test    ebx, ebx
0x18006ae39  jns     short loc_18006AE69
0x18006ae3b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006ae41  jnz     short loc_18006AE49
0x18006ae43  call    cs:__imp_DebugBreak
0x18006ae49  mov     r9d, ebx; int
0x18006ae4c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006ae53  mov     r8d, 149Ch; char *
0x18006ae59  lea     rcx, aStatusPropagat; "Status propagated"
0x18006ae60  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006ae65  mov     ecx, ebx
0x18006ae67  jmp     short loc_18006ADF3
0x18006ae69  xor     eax, eax
0x18006ae6b  add     rsp, 40h
0x18006ae6f  pop     r12
0x18006ae71  pop     rdi
0x18006ae72  pop     rsi
0x18006ae73  pop     rbx
0x18006ae74  pop     rbp
0x18006ae75  retn
```
