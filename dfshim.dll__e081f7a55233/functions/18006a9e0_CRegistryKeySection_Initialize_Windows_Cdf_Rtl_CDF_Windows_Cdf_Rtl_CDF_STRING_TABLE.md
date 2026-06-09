# CRegistryKeySection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006a9e0`
- end: `0x18006aaee`
- name: `?Initialize@CRegistryKeySection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18009a2f0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006a9e0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006aa47`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006aabb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006aa47`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006aabb`

## string_xrefs

- `0x18006aa03`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006aa50`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006aac4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CRegistryKeySection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1F4E,
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
      (const char *)0x1F4F,
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
0x18006a9e0  push    rbp
0x18006a9e2  push    rbx
0x18006a9e3  push    rsi
0x18006a9e4  push    rdi
0x18006a9e5  push    r12
0x18006a9e7  mov     rbp, rsp
0x18006a9ea  sub     rsp, 40h
0x18006a9ee  mov     rax, rdx
0x18006a9f1  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a9f8  lea     rdx, [rcx+18h]
0x18006a9fc  mov     rbx, r8
0x18006a9ff  cmp     qword ptr [rdx], 0
0x18006aa03  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006aa0a  mov     rsi, rcx
0x18006aa0d  mov     [rbp+var_20], r12
0x18006aa11  jz      short loc_18006AA2C
0x18006aa13  mov     [rbp+var_18], 8Eh
0x18006aa1a  lea     rdx, [rbp+var_20]
0x18006aa1e  lea     rcx, [rbp+var_20]
0x18006aa22  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006aa27  mov     edi, dword ptr [rbp+var_10]
0x18006aa2a  jmp     short loc_18006AA3B
0x18006aa2c  mov     rcx, rax
0x18006aa2f  call    CdfDuplicateHandle
0x18006aa34  xor     edi, edi
0x18006aa36  test    eax, eax
0x18006aa38  cmovs   edi, eax
0x18006aa3b  test    edi, edi
0x18006aa3d  jns     short loc_18006AA72
0x18006aa3f  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006aa45  jnz     short loc_18006AA4D
0x18006aa47  call    cs:__imp_DebugBreak
0x18006aa4d  mov     r9d, edi; int
0x18006aa50  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006aa57  mov     r8d, 1F4Eh; char *
0x18006aa5d  lea     rcx, aStatusPropagat; "Status propagated"
0x18006aa64  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006aa69  mov     ecx, edi; this
0x18006aa6b  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006aa70  jmp     short loc_18006AAE3
0x18006aa72  lea     rdx, [rsi+20h]
0x18006aa76  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006aa7d  cmp     qword ptr [rdx], 0
0x18006aa81  mov     [rbp+var_20], r12
0x18006aa85  jz      short loc_18006AAA0
0x18006aa87  mov     [rbp+var_18], 8Eh
0x18006aa8e  lea     rdx, [rbp+var_20]
0x18006aa92  lea     rcx, [rbp+var_20]
0x18006aa96  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006aa9b  mov     ebx, dword ptr [rbp+var_10]
0x18006aa9e  jmp     short loc_18006AAAF
0x18006aaa0  mov     rcx, rbx
0x18006aaa3  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006aaa8  xor     ebx, ebx
0x18006aaaa  test    eax, eax
0x18006aaac  cmovs   ebx, eax
0x18006aaaf  test    ebx, ebx
0x18006aab1  jns     short loc_18006AAE1
0x18006aab3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006aab9  jnz     short loc_18006AAC1
0x18006aabb  call    cs:__imp_DebugBreak
0x18006aac1  mov     r9d, ebx; int
0x18006aac4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006aacb  mov     r8d, 1F4Fh; char *
0x18006aad1  lea     rcx, aStatusPropagat; "Status propagated"
0x18006aad8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006aadd  mov     ecx, ebx
0x18006aadf  jmp     short loc_18006AA6B
0x18006aae1  xor     eax, eax
0x18006aae3  add     rsp, 40h
0x18006aae7  pop     r12
0x18006aae9  pop     rdi
0x18006aaea  pop     rsi
0x18006aaeb  pop     rbx
0x18006aaec  pop     rbp
0x18006aaed  retn
```
