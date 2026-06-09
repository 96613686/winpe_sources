# CCompatibleFrameworksSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_ULONG_TABLE)

- ea: `0x1800675ec`
- end: `0x1800676fa`
- name: `?Initialize@CCompatibleFrameworksSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_ULONG_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18008e5d0`

## callees

- `0x180012950`
- `0x180014588`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x1800675ec`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067653`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800676c7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067653`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800676c7`

## string_xrefs

- `0x18006760f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006765c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800676d0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCompatibleFrameworksSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x21B0,
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
      (const char *)0x21B1,
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
0x1800675ec  push    rbp
0x1800675ee  push    rbx
0x1800675ef  push    rsi
0x1800675f0  push    rdi
0x1800675f1  push    r12
0x1800675f3  mov     rbp, rsp
0x1800675f6  sub     rsp, 40h
0x1800675fa  mov     rax, rdx
0x1800675fd  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067604  lea     rdx, [rcx+18h]
0x180067608  mov     rbx, r8
0x18006760b  cmp     qword ptr [rdx], 0
0x18006760f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067616  mov     rsi, rcx
0x180067619  mov     [rbp+var_20], r12
0x18006761d  jz      short loc_180067638
0x18006761f  mov     [rbp+var_18], 8Eh
0x180067626  lea     rdx, [rbp+var_20]
0x18006762a  lea     rcx, [rbp+var_20]
0x18006762e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067633  mov     edi, dword ptr [rbp+var_10]
0x180067636  jmp     short loc_180067647
0x180067638  mov     rcx, rax
0x18006763b  call    CdfDuplicateHandle
0x180067640  xor     edi, edi
0x180067642  test    eax, eax
0x180067644  cmovs   edi, eax
0x180067647  test    edi, edi
0x180067649  jns     short loc_18006767E
0x18006764b  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180067651  jnz     short loc_180067659
0x180067653  call    cs:__imp_DebugBreak
0x180067659  mov     r9d, edi; int
0x18006765c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067663  mov     r8d, 21B0h; char *
0x180067669  lea     rcx, aStatusPropagat; "Status propagated"
0x180067670  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067675  mov     ecx, edi; this
0x180067677  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006767c  jmp     short loc_1800676EF
0x18006767e  lea     rdx, [rsi+20h]
0x180067682  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067689  cmp     qword ptr [rdx], 0
0x18006768d  mov     [rbp+var_20], r12
0x180067691  jz      short loc_1800676AC
0x180067693  mov     [rbp+var_18], 8Eh
0x18006769a  lea     rdx, [rbp+var_20]
0x18006769e  lea     rcx, [rbp+var_20]
0x1800676a2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800676a7  mov     ebx, dword ptr [rbp+var_10]
0x1800676aa  jmp     short loc_1800676BB
0x1800676ac  mov     rcx, rbx
0x1800676af  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_ULONG_TABLE,Windows::Cdf::Rtl::_CDF_ULONG_TABLE &)
0x1800676b4  xor     ebx, ebx
0x1800676b6  test    eax, eax
0x1800676b8  cmovs   ebx, eax
0x1800676bb  test    ebx, ebx
0x1800676bd  jns     short loc_1800676ED
0x1800676bf  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800676c5  jnz     short loc_1800676CD
0x1800676c7  call    cs:__imp_DebugBreak
0x1800676cd  mov     r9d, ebx; int
0x1800676d0  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800676d7  mov     r8d, 21B1h; char *
0x1800676dd  lea     rcx, aStatusPropagat; "Status propagated"
0x1800676e4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800676e9  mov     ecx, ebx
0x1800676eb  jmp     short loc_180067677
0x1800676ed  xor     eax, eax
0x1800676ef  add     rsp, 40h
0x1800676f3  pop     r12
0x1800676f5  pop     rdi
0x1800676f6  pop     rsi
0x1800676f7  pop     rbx
0x1800676f8  pop     rbp
0x1800676f9  retn
```
