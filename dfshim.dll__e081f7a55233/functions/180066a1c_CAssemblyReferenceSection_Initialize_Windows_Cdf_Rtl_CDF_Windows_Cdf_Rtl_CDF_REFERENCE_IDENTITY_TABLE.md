# CAssemblyReferenceSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE)

- ea: `0x180066a1c`
- end: `0x180066b2a`
- name: `?Initialize@CAssemblyReferenceSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_REFERENCE_IDENTITY_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18008ca40`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dc64`
- `0x180066a1c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066a83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066af7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066a83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066af7`

## string_xrefs

- `0x180066a3f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180066a8c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180066b00`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CAssemblyReferenceSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x178C,
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
      (const char *)0x178D,
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
0x180066a1c  push    rbp
0x180066a1e  push    rbx
0x180066a1f  push    rsi
0x180066a20  push    rdi
0x180066a21  push    r12
0x180066a23  mov     rbp, rsp
0x180066a26  sub     rsp, 40h
0x180066a2a  mov     rax, rdx
0x180066a2d  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180066a34  lea     rdx, [rcx+18h]
0x180066a38  mov     rbx, r8
0x180066a3b  cmp     qword ptr [rdx], 0
0x180066a3f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066a46  mov     rsi, rcx
0x180066a49  mov     [rbp+var_20], r12
0x180066a4d  jz      short loc_180066A68
0x180066a4f  mov     [rbp+var_18], 8Eh
0x180066a56  lea     rdx, [rbp+var_20]
0x180066a5a  lea     rcx, [rbp+var_20]
0x180066a5e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180066a63  mov     edi, dword ptr [rbp+var_10]
0x180066a66  jmp     short loc_180066A77
0x180066a68  mov     rcx, rax
0x180066a6b  call    CdfDuplicateHandle
0x180066a70  xor     edi, edi
0x180066a72  test    eax, eax
0x180066a74  cmovs   edi, eax
0x180066a77  test    edi, edi
0x180066a79  jns     short loc_180066AAE
0x180066a7b  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180066a81  jnz     short loc_180066A89
0x180066a83  call    cs:__imp_DebugBreak
0x180066a89  mov     r9d, edi; int
0x180066a8c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066a93  mov     r8d, 178Ch; char *
0x180066a99  lea     rcx, aStatusPropagat; "Status propagated"
0x180066aa0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066aa5  mov     ecx, edi; this
0x180066aa7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180066aac  jmp     short loc_180066B1F
0x180066aae  lea     rdx, [rsi+20h]
0x180066ab2  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180066ab9  cmp     qword ptr [rdx], 0
0x180066abd  mov     [rbp+var_20], r12
0x180066ac1  jz      short loc_180066ADC
0x180066ac3  mov     [rbp+var_18], 8Eh
0x180066aca  lea     rdx, [rbp+var_20]
0x180066ace  lea     rcx, [rbp+var_20]
0x180066ad2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180066ad7  mov     ebx, dword ptr [rbp+var_10]
0x180066ada  jmp     short loc_180066AEB
0x180066adc  mov     rcx, rbx
0x180066adf  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_REFERENCE_IDENTITY_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE,Windows::Cdf::Rtl::_CDF_REFERENCE_IDENTITY_TABLE &)
0x180066ae4  xor     ebx, ebx
0x180066ae6  test    eax, eax
0x180066ae8  cmovs   ebx, eax
0x180066aeb  test    ebx, ebx
0x180066aed  jns     short loc_180066B1D
0x180066aef  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180066af5  jnz     short loc_180066AFD
0x180066af7  call    cs:__imp_DebugBreak
0x180066afd  mov     r9d, ebx; int
0x180066b00  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066b07  mov     r8d, 178Dh; char *
0x180066b0d  lea     rcx, aStatusPropagat; "Status propagated"
0x180066b14  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066b19  mov     ecx, ebx
0x180066b1b  jmp     short loc_180066AA7
0x180066b1d  xor     eax, eax
0x180066b1f  add     rsp, 40h
0x180066b23  pop     r12
0x180066b25  pop     rdi
0x180066b26  pop     rsi
0x180066b27  pop     rbx
0x180066b28  pop     rbp
0x180066b29  retn
```
