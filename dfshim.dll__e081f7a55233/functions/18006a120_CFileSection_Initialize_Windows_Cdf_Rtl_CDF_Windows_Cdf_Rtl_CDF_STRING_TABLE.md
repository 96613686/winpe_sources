# CFileSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006a120`
- end: `0x18006a22e`
- name: `?Initialize@CFileSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180095620`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006a120`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a187`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a1fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a187`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a1fb`

## string_xrefs

- `0x18006a143`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006a190`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006a204`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CFileSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x12CD,
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
      (const char *)0x12CE,
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
0x18006a120  push    rbp
0x18006a122  push    rbx
0x18006a123  push    rsi
0x18006a124  push    rdi
0x18006a125  push    r12
0x18006a127  mov     rbp, rsp
0x18006a12a  sub     rsp, 40h
0x18006a12e  mov     rax, rdx
0x18006a131  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a138  lea     rdx, [rcx+18h]
0x18006a13c  mov     rbx, r8
0x18006a13f  cmp     qword ptr [rdx], 0
0x18006a143  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a14a  mov     rsi, rcx
0x18006a14d  mov     [rbp+var_20], r12
0x18006a151  jz      short loc_18006A16C
0x18006a153  mov     [rbp+var_18], 8Eh
0x18006a15a  lea     rdx, [rbp+var_20]
0x18006a15e  lea     rcx, [rbp+var_20]
0x18006a162  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a167  mov     edi, dword ptr [rbp+var_10]
0x18006a16a  jmp     short loc_18006A17B
0x18006a16c  mov     rcx, rax
0x18006a16f  call    CdfDuplicateHandle
0x18006a174  xor     edi, edi
0x18006a176  test    eax, eax
0x18006a178  cmovs   edi, eax
0x18006a17b  test    edi, edi
0x18006a17d  jns     short loc_18006A1B2
0x18006a17f  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006a185  jnz     short loc_18006A18D
0x18006a187  call    cs:__imp_DebugBreak
0x18006a18d  mov     r9d, edi; int
0x18006a190  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a197  mov     r8d, 12CDh; char *
0x18006a19d  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a1a4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a1a9  mov     ecx, edi; this
0x18006a1ab  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006a1b0  jmp     short loc_18006A223
0x18006a1b2  lea     rdx, [rsi+20h]
0x18006a1b6  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a1bd  cmp     qword ptr [rdx], 0
0x18006a1c1  mov     [rbp+var_20], r12
0x18006a1c5  jz      short loc_18006A1E0
0x18006a1c7  mov     [rbp+var_18], 8Eh
0x18006a1ce  lea     rdx, [rbp+var_20]
0x18006a1d2  lea     rcx, [rbp+var_20]
0x18006a1d6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a1db  mov     ebx, dword ptr [rbp+var_10]
0x18006a1de  jmp     short loc_18006A1EF
0x18006a1e0  mov     rcx, rbx
0x18006a1e3  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006a1e8  xor     ebx, ebx
0x18006a1ea  test    eax, eax
0x18006a1ec  cmovs   ebx, eax
0x18006a1ef  test    ebx, ebx
0x18006a1f1  jns     short loc_18006A221
0x18006a1f3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006a1f9  jnz     short loc_18006A201
0x18006a1fb  call    cs:__imp_DebugBreak
0x18006a201  mov     r9d, ebx; int
0x18006a204  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a20b  mov     r8d, 12CEh; char *
0x18006a211  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a218  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a21d  mov     ecx, ebx
0x18006a21f  jmp     short loc_18006A1AB
0x18006a221  xor     eax, eax
0x18006a223  add     rsp, 40h
0x18006a227  pop     r12
0x18006a229  pop     rdi
0x18006a22a  pop     rsi
0x18006a22b  pop     rbx
0x18006a22c  pop     rbp
0x18006a22d  retn
```
