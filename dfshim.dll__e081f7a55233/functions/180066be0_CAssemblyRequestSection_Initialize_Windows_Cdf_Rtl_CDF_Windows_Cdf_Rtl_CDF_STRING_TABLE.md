# CAssemblyRequestSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180066be0`
- end: `0x180066cee`
- name: `?Initialize@CAssemblyRequestSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18008cc60`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180066be0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066c47`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066cbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066c47`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066cbb`

## string_xrefs

- `0x180066c03`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180066c50`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180066cc4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CAssemblyRequestSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1B26,
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
      (const char *)0x1B27,
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
0x180066be0  push    rbp
0x180066be2  push    rbx
0x180066be3  push    rsi
0x180066be4  push    rdi
0x180066be5  push    r12
0x180066be7  mov     rbp, rsp
0x180066bea  sub     rsp, 40h
0x180066bee  mov     rax, rdx
0x180066bf1  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180066bf8  lea     rdx, [rcx+18h]
0x180066bfc  mov     rbx, r8
0x180066bff  cmp     qword ptr [rdx], 0
0x180066c03  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066c0a  mov     rsi, rcx
0x180066c0d  mov     [rbp+var_20], r12
0x180066c11  jz      short loc_180066C2C
0x180066c13  mov     [rbp+var_18], 8Eh
0x180066c1a  lea     rdx, [rbp+var_20]
0x180066c1e  lea     rcx, [rbp+var_20]
0x180066c22  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180066c27  mov     edi, dword ptr [rbp+var_10]
0x180066c2a  jmp     short loc_180066C3B
0x180066c2c  mov     rcx, rax
0x180066c2f  call    CdfDuplicateHandle
0x180066c34  xor     edi, edi
0x180066c36  test    eax, eax
0x180066c38  cmovs   edi, eax
0x180066c3b  test    edi, edi
0x180066c3d  jns     short loc_180066C72
0x180066c3f  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180066c45  jnz     short loc_180066C4D
0x180066c47  call    cs:__imp_DebugBreak
0x180066c4d  mov     r9d, edi; int
0x180066c50  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066c57  mov     r8d, 1B26h; char *
0x180066c5d  lea     rcx, aStatusPropagat; "Status propagated"
0x180066c64  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066c69  mov     ecx, edi; this
0x180066c6b  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180066c70  jmp     short loc_180066CE3
0x180066c72  lea     rdx, [rsi+20h]
0x180066c76  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180066c7d  cmp     qword ptr [rdx], 0
0x180066c81  mov     [rbp+var_20], r12
0x180066c85  jz      short loc_180066CA0
0x180066c87  mov     [rbp+var_18], 8Eh
0x180066c8e  lea     rdx, [rbp+var_20]
0x180066c92  lea     rcx, [rbp+var_20]
0x180066c96  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180066c9b  mov     ebx, dword ptr [rbp+var_10]
0x180066c9e  jmp     short loc_180066CAF
0x180066ca0  mov     rcx, rbx
0x180066ca3  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180066ca8  xor     ebx, ebx
0x180066caa  test    eax, eax
0x180066cac  cmovs   ebx, eax
0x180066caf  test    ebx, ebx
0x180066cb1  jns     short loc_180066CE1
0x180066cb3  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180066cb9  jnz     short loc_180066CC1
0x180066cbb  call    cs:__imp_DebugBreak
0x180066cc1  mov     r9d, ebx; int
0x180066cc4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066ccb  mov     r8d, 1B27h; char *
0x180066cd1  lea     rcx, aStatusPropagat; "Status propagated"
0x180066cd8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066cdd  mov     ecx, ebx
0x180066cdf  jmp     short loc_180066C6B
0x180066ce1  xor     eax, eax
0x180066ce3  add     rsp, 40h
0x180066ce7  pop     r12
0x180066ce9  pop     rdi
0x180066cea  pop     rsi
0x180066ceb  pop     rbx
0x180066cec  pop     rbp
0x180066ced  retn
```
