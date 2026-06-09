# CStringSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006aba4`
- end: `0x18006acb2`
- name: `?Initialize@CStringSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18009c850`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006aba4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ac0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ac7f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ac0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006ac7f`

## string_xrefs

- `0x18006abc7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006ac14`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006ac88`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CStringSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x18BF,
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
      (const char *)0x18C0,
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
0x18006aba4  push    rbp
0x18006aba6  push    rbx
0x18006aba7  push    rsi
0x18006aba8  push    rdi
0x18006aba9  push    r12
0x18006abab  mov     rbp, rsp
0x18006abae  sub     rsp, 40h
0x18006abb2  mov     rax, rdx
0x18006abb5  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006abbc  lea     rdx, [rcx+18h]
0x18006abc0  mov     rbx, r8
0x18006abc3  cmp     qword ptr [rdx], 0
0x18006abc7  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006abce  mov     rsi, rcx
0x18006abd1  mov     [rbp+var_20], r12
0x18006abd5  jz      short loc_18006ABF0
0x18006abd7  mov     [rbp+var_18], 8Eh
0x18006abde  lea     rdx, [rbp+var_20]
0x18006abe2  lea     rcx, [rbp+var_20]
0x18006abe6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006abeb  mov     edi, dword ptr [rbp+var_10]
0x18006abee  jmp     short loc_18006ABFF
0x18006abf0  mov     rcx, rax
0x18006abf3  call    CdfDuplicateHandle
0x18006abf8  xor     edi, edi
0x18006abfa  test    eax, eax
0x18006abfc  cmovs   edi, eax
0x18006abff  test    edi, edi
0x18006ac01  jns     short loc_18006AC36
0x18006ac03  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006ac09  jnz     short loc_18006AC11
0x18006ac0b  call    cs:__imp_DebugBreak
0x18006ac11  mov     r9d, edi; int
0x18006ac14  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006ac1b  mov     r8d, 18BFh; char *
0x18006ac21  lea     rcx, aStatusPropagat; "Status propagated"
0x18006ac28  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006ac2d  mov     ecx, edi; this
0x18006ac2f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006ac34  jmp     short loc_18006ACA7
0x18006ac36  lea     rdx, [rsi+20h]
0x18006ac3a  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006ac41  cmp     qword ptr [rdx], 0
0x18006ac45  mov     [rbp+var_20], r12
0x18006ac49  jz      short loc_18006AC64
0x18006ac4b  mov     [rbp+var_18], 8Eh
0x18006ac52  lea     rdx, [rbp+var_20]
0x18006ac56  lea     rcx, [rbp+var_20]
0x18006ac5a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006ac5f  mov     ebx, dword ptr [rbp+var_10]
0x18006ac62  jmp     short loc_18006AC73
0x18006ac64  mov     rcx, rbx
0x18006ac67  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006ac6c  xor     ebx, ebx
0x18006ac6e  test    eax, eax
0x18006ac70  cmovs   ebx, eax
0x18006ac73  test    ebx, ebx
0x18006ac75  jns     short loc_18006ACA5
0x18006ac77  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006ac7d  jnz     short loc_18006AC85
0x18006ac7f  call    cs:__imp_DebugBreak
0x18006ac85  mov     r9d, ebx; int
0x18006ac88  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006ac8f  mov     r8d, 18C0h; char *
0x18006ac95  lea     rcx, aStatusPropagat; "Status propagated"
0x18006ac9c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006aca1  mov     ecx, ebx
0x18006aca3  jmp     short loc_18006AC2F
0x18006aca5  xor     eax, eax
0x18006aca7  add     rsp, 40h
0x18006acab  pop     r12
0x18006acad  pop     rdi
0x18006acae  pop     rsi
0x18006acaf  pop     rbx
0x18006acb0  pop     rbp
0x18006acb1  retn
```
