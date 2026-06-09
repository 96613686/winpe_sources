# CCultureSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180067a48`
- end: `0x180067b56`
- name: `?Initialize@CCultureSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800727e0`
- `0x18007d560`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180067a48`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067aaf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067b23`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067aaf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067b23`

## string_xrefs

- `0x180067a6b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180067ab8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180067b2c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCultureSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1958,
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
      (const char *)0x1959,
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
0x180067a48  push    rbp
0x180067a4a  push    rbx
0x180067a4b  push    rsi
0x180067a4c  push    rdi
0x180067a4d  push    r12
0x180067a4f  mov     rbp, rsp
0x180067a52  sub     rsp, 40h
0x180067a56  mov     rax, rdx
0x180067a59  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067a60  lea     rdx, [rcx+18h]
0x180067a64  mov     rbx, r8
0x180067a67  cmp     qword ptr [rdx], 0
0x180067a6b  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067a72  mov     rsi, rcx
0x180067a75  mov     [rbp+var_20], r12
0x180067a79  jz      short loc_180067A94
0x180067a7b  mov     [rbp+var_18], 8Eh
0x180067a82  lea     rdx, [rbp+var_20]
0x180067a86  lea     rcx, [rbp+var_20]
0x180067a8a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067a8f  mov     edi, dword ptr [rbp+var_10]
0x180067a92  jmp     short loc_180067AA3
0x180067a94  mov     rcx, rax
0x180067a97  call    CdfDuplicateHandle
0x180067a9c  xor     edi, edi
0x180067a9e  test    eax, eax
0x180067aa0  cmovs   edi, eax
0x180067aa3  test    edi, edi
0x180067aa5  jns     short loc_180067ADA
0x180067aa7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180067aad  jnz     short loc_180067AB5
0x180067aaf  call    cs:__imp_DebugBreak
0x180067ab5  mov     r9d, edi; int
0x180067ab8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067abf  mov     r8d, 1958h; char *
0x180067ac5  lea     rcx, aStatusPropagat; "Status propagated"
0x180067acc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067ad1  mov     ecx, edi; this
0x180067ad3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180067ad8  jmp     short loc_180067B4B
0x180067ada  lea     rdx, [rsi+20h]
0x180067ade  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067ae5  cmp     qword ptr [rdx], 0
0x180067ae9  mov     [rbp+var_20], r12
0x180067aed  jz      short loc_180067B08
0x180067aef  mov     [rbp+var_18], 8Eh
0x180067af6  lea     rdx, [rbp+var_20]
0x180067afa  lea     rcx, [rbp+var_20]
0x180067afe  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067b03  mov     ebx, dword ptr [rbp+var_10]
0x180067b06  jmp     short loc_180067B17
0x180067b08  mov     rcx, rbx
0x180067b0b  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180067b10  xor     ebx, ebx
0x180067b12  test    eax, eax
0x180067b14  cmovs   ebx, eax
0x180067b17  test    ebx, ebx
0x180067b19  jns     short loc_180067B49
0x180067b1b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180067b21  jnz     short loc_180067B29
0x180067b23  call    cs:__imp_DebugBreak
0x180067b29  mov     r9d, ebx; int
0x180067b2c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067b33  mov     r8d, 1959h; char *
0x180067b39  lea     rcx, aStatusPropagat; "Status propagated"
0x180067b40  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067b45  mov     ecx, ebx
0x180067b47  jmp     short loc_180067AD3
0x180067b49  xor     eax, eax
0x180067b4b  add     rsp, 40h
0x180067b4f  pop     r12
0x180067b51  pop     rdi
0x180067b52  pop     rsi
0x180067b53  pop     rbx
0x180067b54  pop     rbp
0x180067b55  retn
```
