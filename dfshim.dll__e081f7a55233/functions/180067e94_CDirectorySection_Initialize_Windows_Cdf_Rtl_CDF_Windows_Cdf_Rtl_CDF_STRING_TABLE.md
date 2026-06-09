# CDirectorySection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180067e94`
- end: `0x180067fa2`
- name: `?Initialize@CDirectorySection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x1800943f0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180067e94`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067efb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067f6f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067efb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067f6f`

## string_xrefs

- `0x180067eb7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180067f04`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180067f78`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CDirectorySection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1FE9,
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
      (const char *)0x1FEA,
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
0x180067e94  push    rbp
0x180067e96  push    rbx
0x180067e97  push    rsi
0x180067e98  push    rdi
0x180067e99  push    r12
0x180067e9b  mov     rbp, rsp
0x180067e9e  sub     rsp, 40h
0x180067ea2  mov     rax, rdx
0x180067ea5  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067eac  lea     rdx, [rcx+18h]
0x180067eb0  mov     rbx, r8
0x180067eb3  cmp     qword ptr [rdx], 0
0x180067eb7  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067ebe  mov     rsi, rcx
0x180067ec1  mov     [rbp+var_20], r12
0x180067ec5  jz      short loc_180067EE0
0x180067ec7  mov     [rbp+var_18], 8Eh
0x180067ece  lea     rdx, [rbp+var_20]
0x180067ed2  lea     rcx, [rbp+var_20]
0x180067ed6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067edb  mov     edi, dword ptr [rbp+var_10]
0x180067ede  jmp     short loc_180067EEF
0x180067ee0  mov     rcx, rax
0x180067ee3  call    CdfDuplicateHandle
0x180067ee8  xor     edi, edi
0x180067eea  test    eax, eax
0x180067eec  cmovs   edi, eax
0x180067eef  test    edi, edi
0x180067ef1  jns     short loc_180067F26
0x180067ef3  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180067ef9  jnz     short loc_180067F01
0x180067efb  call    cs:__imp_DebugBreak
0x180067f01  mov     r9d, edi; int
0x180067f04  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067f0b  mov     r8d, 1FE9h; char *
0x180067f11  lea     rcx, aStatusPropagat; "Status propagated"
0x180067f18  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067f1d  mov     ecx, edi; this
0x180067f1f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180067f24  jmp     short loc_180067F97
0x180067f26  lea     rdx, [rsi+20h]
0x180067f2a  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067f31  cmp     qword ptr [rdx], 0
0x180067f35  mov     [rbp+var_20], r12
0x180067f39  jz      short loc_180067F54
0x180067f3b  mov     [rbp+var_18], 8Eh
0x180067f42  lea     rdx, [rbp+var_20]
0x180067f46  lea     rcx, [rbp+var_20]
0x180067f4a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067f4f  mov     ebx, dword ptr [rbp+var_10]
0x180067f52  jmp     short loc_180067F63
0x180067f54  mov     rcx, rbx
0x180067f57  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180067f5c  xor     ebx, ebx
0x180067f5e  test    eax, eax
0x180067f60  cmovs   ebx, eax
0x180067f63  test    ebx, ebx
0x180067f65  jns     short loc_180067F95
0x180067f67  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180067f6d  jnz     short loc_180067F75
0x180067f6f  call    cs:__imp_DebugBreak
0x180067f75  mov     r9d, ebx; int
0x180067f78  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067f7f  mov     r8d, 1FEAh; char *
0x180067f85  lea     rcx, aStatusPropagat; "Status propagated"
0x180067f8c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067f91  mov     ecx, ebx
0x180067f93  jmp     short loc_180067F1F
0x180067f95  xor     eax, eax
0x180067f97  add     rsp, 40h
0x180067f9b  pop     r12
0x180067f9d  pop     rdi
0x180067f9e  pop     rsi
0x180067f9f  pop     rbx
0x180067fa0  pop     rbp
0x180067fa1  retn
```
