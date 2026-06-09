# CHashElementSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_ULONG_TABLE)

- ea: `0x18006a2e4`
- end: `0x18006a3f2`
- name: `?Initialize@CHashElementSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_ULONG_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005c384`
- `0x18005cf18`
- `0x18005eb50`
- `0x180061480`
- `0x180096620`
- `0x180096870`

## callees

- `0x180012950`
- `0x180014588`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18006a2e4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a34b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a3bf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a34b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a3bf`

## string_xrefs

- `0x18006a307`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006a354`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006a3c8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CHashElementSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x123B,
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
      (const char *)0x123C,
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
0x18006a2e4  push    rbp
0x18006a2e6  push    rbx
0x18006a2e7  push    rsi
0x18006a2e8  push    rdi
0x18006a2e9  push    r12
0x18006a2eb  mov     rbp, rsp
0x18006a2ee  sub     rsp, 40h
0x18006a2f2  mov     rax, rdx
0x18006a2f5  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a2fc  lea     rdx, [rcx+18h]
0x18006a300  mov     rbx, r8
0x18006a303  cmp     qword ptr [rdx], 0
0x18006a307  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a30e  mov     rsi, rcx
0x18006a311  mov     [rbp+var_20], r12
0x18006a315  jz      short loc_18006A330
0x18006a317  mov     [rbp+var_18], 8Eh
0x18006a31e  lea     rdx, [rbp+var_20]
0x18006a322  lea     rcx, [rbp+var_20]
0x18006a326  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a32b  mov     edi, dword ptr [rbp+var_10]
0x18006a32e  jmp     short loc_18006A33F
0x18006a330  mov     rcx, rax
0x18006a333  call    CdfDuplicateHandle
0x18006a338  xor     edi, edi
0x18006a33a  test    eax, eax
0x18006a33c  cmovs   edi, eax
0x18006a33f  test    edi, edi
0x18006a341  jns     short loc_18006A376
0x18006a343  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006a349  jnz     short loc_18006A351
0x18006a34b  call    cs:__imp_DebugBreak
0x18006a351  mov     r9d, edi; int
0x18006a354  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a35b  mov     r8d, 123Bh; char *
0x18006a361  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a368  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a36d  mov     ecx, edi; this
0x18006a36f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006a374  jmp     short loc_18006A3E7
0x18006a376  lea     rdx, [rsi+20h]
0x18006a37a  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a381  cmp     qword ptr [rdx], 0
0x18006a385  mov     [rbp+var_20], r12
0x18006a389  jz      short loc_18006A3A4
0x18006a38b  mov     [rbp+var_18], 8Eh
0x18006a392  lea     rdx, [rbp+var_20]
0x18006a396  lea     rcx, [rbp+var_20]
0x18006a39a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a39f  mov     ebx, dword ptr [rbp+var_10]
0x18006a3a2  jmp     short loc_18006A3B3
0x18006a3a4  mov     rcx, rbx
0x18006a3a7  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_ULONG_TABLE,Windows::Cdf::Rtl::_CDF_ULONG_TABLE &)
0x18006a3ac  xor     ebx, ebx
0x18006a3ae  test    eax, eax
0x18006a3b0  cmovs   ebx, eax
0x18006a3b3  test    ebx, ebx
0x18006a3b5  jns     short loc_18006A3E5
0x18006a3b7  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006a3bd  jnz     short loc_18006A3C5
0x18006a3bf  call    cs:__imp_DebugBreak
0x18006a3c5  mov     r9d, ebx; int
0x18006a3c8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a3cf  mov     r8d, 123Ch; char *
0x18006a3d5  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a3dc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a3e1  mov     ecx, ebx
0x18006a3e3  jmp     short loc_18006A36F
0x18006a3e5  xor     eax, eax
0x18006a3e7  add     rsp, 40h
0x18006a3eb  pop     r12
0x18006a3ed  pop     rdi
0x18006a3ee  pop     rsi
0x18006a3ef  pop     rbx
0x18006a3f0  pop     rbp
0x18006a3f1  retn
```
