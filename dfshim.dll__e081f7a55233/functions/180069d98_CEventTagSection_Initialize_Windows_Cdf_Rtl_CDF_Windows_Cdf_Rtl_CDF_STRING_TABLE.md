# CEventTagSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180069d98`
- end: `0x180069ea6`
- name: `?Initialize@CEventTagSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180095120`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180069d98`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069dff`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069e73`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069dff`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069e73`

## string_xrefs

- `0x180069dbb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180069e08`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180069e7c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventTagSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1E1B,
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
      (const char *)0x1E1C,
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
0x180069d98  push    rbp
0x180069d9a  push    rbx
0x180069d9b  push    rsi
0x180069d9c  push    rdi
0x180069d9d  push    r12
0x180069d9f  mov     rbp, rsp
0x180069da2  sub     rsp, 40h
0x180069da6  mov     rax, rdx
0x180069da9  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069db0  lea     rdx, [rcx+18h]
0x180069db4  mov     rbx, r8
0x180069db7  cmp     qword ptr [rdx], 0
0x180069dbb  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069dc2  mov     rsi, rcx
0x180069dc5  mov     [rbp+var_20], r12
0x180069dc9  jz      short loc_180069DE4
0x180069dcb  mov     [rbp+var_18], 8Eh
0x180069dd2  lea     rdx, [rbp+var_20]
0x180069dd6  lea     rcx, [rbp+var_20]
0x180069dda  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069ddf  mov     edi, dword ptr [rbp+var_10]
0x180069de2  jmp     short loc_180069DF3
0x180069de4  mov     rcx, rax
0x180069de7  call    CdfDuplicateHandle
0x180069dec  xor     edi, edi
0x180069dee  test    eax, eax
0x180069df0  cmovs   edi, eax
0x180069df3  test    edi, edi
0x180069df5  jns     short loc_180069E2A
0x180069df7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180069dfd  jnz     short loc_180069E05
0x180069dff  call    cs:__imp_DebugBreak
0x180069e05  mov     r9d, edi; int
0x180069e08  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069e0f  mov     r8d, 1E1Bh; char *
0x180069e15  lea     rcx, aStatusPropagat; "Status propagated"
0x180069e1c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069e21  mov     ecx, edi; this
0x180069e23  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180069e28  jmp     short loc_180069E9B
0x180069e2a  lea     rdx, [rsi+20h]
0x180069e2e  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069e35  cmp     qword ptr [rdx], 0
0x180069e39  mov     [rbp+var_20], r12
0x180069e3d  jz      short loc_180069E58
0x180069e3f  mov     [rbp+var_18], 8Eh
0x180069e46  lea     rdx, [rbp+var_20]
0x180069e4a  lea     rcx, [rbp+var_20]
0x180069e4e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069e53  mov     ebx, dword ptr [rbp+var_10]
0x180069e56  jmp     short loc_180069E67
0x180069e58  mov     rcx, rbx
0x180069e5b  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180069e60  xor     ebx, ebx
0x180069e62  test    eax, eax
0x180069e64  cmovs   ebx, eax
0x180069e67  test    ebx, ebx
0x180069e69  jns     short loc_180069E99
0x180069e6b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180069e71  jnz     short loc_180069E79
0x180069e73  call    cs:__imp_DebugBreak
0x180069e79  mov     r9d, ebx; int
0x180069e7c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069e83  mov     r8d, 1E1Ch; char *
0x180069e89  lea     rcx, aStatusPropagat; "Status propagated"
0x180069e90  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069e95  mov     ecx, ebx
0x180069e97  jmp     short loc_180069E23
0x180069e99  xor     eax, eax
0x180069e9b  add     rsp, 40h
0x180069e9f  pop     r12
0x180069ea1  pop     rdi
0x180069ea2  pop     rsi
0x180069ea3  pop     rbx
0x180069ea4  pop     rbp
0x180069ea5  retn
```
