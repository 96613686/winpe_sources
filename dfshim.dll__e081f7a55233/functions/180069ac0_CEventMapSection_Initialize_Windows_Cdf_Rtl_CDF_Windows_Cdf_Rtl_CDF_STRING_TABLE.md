# CEventMapSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180069ac0`
- end: `0x180069bce`
- name: `?Initialize@CEventMapSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180094bf0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180069ac0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069b27`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069b9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069b27`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069b9b`

## string_xrefs

- `0x180069ae3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180069b30`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180069ba4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventMapSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1D80,
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
      (const char *)0x1D81,
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
0x180069ac0  push    rbp
0x180069ac2  push    rbx
0x180069ac3  push    rsi
0x180069ac4  push    rdi
0x180069ac5  push    r12
0x180069ac7  mov     rbp, rsp
0x180069aca  sub     rsp, 40h
0x180069ace  mov     rax, rdx
0x180069ad1  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069ad8  lea     rdx, [rcx+18h]
0x180069adc  mov     rbx, r8
0x180069adf  cmp     qword ptr [rdx], 0
0x180069ae3  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069aea  mov     rsi, rcx
0x180069aed  mov     [rbp+var_20], r12
0x180069af1  jz      short loc_180069B0C
0x180069af3  mov     [rbp+var_18], 8Eh
0x180069afa  lea     rdx, [rbp+var_20]
0x180069afe  lea     rcx, [rbp+var_20]
0x180069b02  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069b07  mov     edi, dword ptr [rbp+var_10]
0x180069b0a  jmp     short loc_180069B1B
0x180069b0c  mov     rcx, rax
0x180069b0f  call    CdfDuplicateHandle
0x180069b14  xor     edi, edi
0x180069b16  test    eax, eax
0x180069b18  cmovs   edi, eax
0x180069b1b  test    edi, edi
0x180069b1d  jns     short loc_180069B52
0x180069b1f  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180069b25  jnz     short loc_180069B2D
0x180069b27  call    cs:__imp_DebugBreak
0x180069b2d  mov     r9d, edi; int
0x180069b30  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069b37  mov     r8d, 1D80h; char *
0x180069b3d  lea     rcx, aStatusPropagat; "Status propagated"
0x180069b44  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069b49  mov     ecx, edi; this
0x180069b4b  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180069b50  jmp     short loc_180069BC3
0x180069b52  lea     rdx, [rsi+20h]
0x180069b56  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069b5d  cmp     qword ptr [rdx], 0
0x180069b61  mov     [rbp+var_20], r12
0x180069b65  jz      short loc_180069B80
0x180069b67  mov     [rbp+var_18], 8Eh
0x180069b6e  lea     rdx, [rbp+var_20]
0x180069b72  lea     rcx, [rbp+var_20]
0x180069b76  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069b7b  mov     ebx, dword ptr [rbp+var_10]
0x180069b7e  jmp     short loc_180069B8F
0x180069b80  mov     rcx, rbx
0x180069b83  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180069b88  xor     ebx, ebx
0x180069b8a  test    eax, eax
0x180069b8c  cmovs   ebx, eax
0x180069b8f  test    ebx, ebx
0x180069b91  jns     short loc_180069BC1
0x180069b93  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180069b99  jnz     short loc_180069BA1
0x180069b9b  call    cs:__imp_DebugBreak
0x180069ba1  mov     r9d, ebx; int
0x180069ba4  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069bab  mov     r8d, 1D81h; char *
0x180069bb1  lea     rcx, aStatusPropagat; "Status propagated"
0x180069bb8  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069bbd  mov     ecx, ebx
0x180069bbf  jmp     short loc_180069B4B
0x180069bc1  xor     eax, eax
0x180069bc3  add     rsp, 40h
0x180069bc7  pop     r12
0x180069bc9  pop     rdi
0x180069bca  pop     rsi
0x180069bcb  pop     rbx
0x180069bcc  pop     rbp
0x180069bcd  retn
```
