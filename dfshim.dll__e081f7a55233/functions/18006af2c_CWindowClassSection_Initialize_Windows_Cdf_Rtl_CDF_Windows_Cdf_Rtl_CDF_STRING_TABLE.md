# CWindowClassSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006af2c`
- end: `0x18006b03a`
- name: `?Initialize@CWindowClassSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18009e040`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006af2c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006af93`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006b007`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006af93`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006b007`

## string_xrefs

- `0x18006af4f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006af9c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006b010`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CWindowClassSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1824,
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
      (const char *)0x1825,
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
0x18006af2c  push    rbp
0x18006af2e  push    rbx
0x18006af2f  push    rsi
0x18006af30  push    rdi
0x18006af31  push    r12
0x18006af33  mov     rbp, rsp
0x18006af36  sub     rsp, 40h
0x18006af3a  mov     rax, rdx
0x18006af3d  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006af44  lea     rdx, [rcx+18h]
0x18006af48  mov     rbx, r8
0x18006af4b  cmp     qword ptr [rdx], 0
0x18006af4f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006af56  mov     rsi, rcx
0x18006af59  mov     [rbp+var_20], r12
0x18006af5d  jz      short loc_18006AF78
0x18006af5f  mov     [rbp+var_18], 8Eh
0x18006af66  lea     rdx, [rbp+var_20]
0x18006af6a  lea     rcx, [rbp+var_20]
0x18006af6e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006af73  mov     edi, dword ptr [rbp+var_10]
0x18006af76  jmp     short loc_18006AF87
0x18006af78  mov     rcx, rax
0x18006af7b  call    CdfDuplicateHandle
0x18006af80  xor     edi, edi
0x18006af82  test    eax, eax
0x18006af84  cmovs   edi, eax
0x18006af87  test    edi, edi
0x18006af89  jns     short loc_18006AFBE
0x18006af8b  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006af91  jnz     short loc_18006AF99
0x18006af93  call    cs:__imp_DebugBreak
0x18006af99  mov     r9d, edi; int
0x18006af9c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006afa3  mov     r8d, 1824h; char *
0x18006afa9  lea     rcx, aStatusPropagat; "Status propagated"
0x18006afb0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006afb5  mov     ecx, edi; this
0x18006afb7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006afbc  jmp     short loc_18006B02F
0x18006afbe  lea     rdx, [rsi+20h]
0x18006afc2  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006afc9  cmp     qword ptr [rdx], 0
0x18006afcd  mov     [rbp+var_20], r12
0x18006afd1  jz      short loc_18006AFEC
0x18006afd3  mov     [rbp+var_18], 8Eh
0x18006afda  lea     rdx, [rbp+var_20]
0x18006afde  lea     rcx, [rbp+var_20]
0x18006afe2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006afe7  mov     ebx, dword ptr [rbp+var_10]
0x18006afea  jmp     short loc_18006AFFB
0x18006afec  mov     rcx, rbx
0x18006afef  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006aff4  xor     ebx, ebx
0x18006aff6  test    eax, eax
0x18006aff8  cmovs   ebx, eax
0x18006affb  test    ebx, ebx
0x18006affd  jns     short loc_18006B02D
0x18006afff  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006b005  jnz     short loc_18006B00D
0x18006b007  call    cs:__imp_DebugBreak
0x18006b00d  mov     r9d, ebx; int
0x18006b010  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006b017  mov     r8d, 1825h; char *
0x18006b01d  lea     rcx, aStatusPropagat; "Status propagated"
0x18006b024  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006b029  mov     ecx, ebx
0x18006b02b  jmp     short loc_18006AFB7
0x18006b02d  xor     eax, eax
0x18006b02f  add     rsp, 40h
0x18006b033  pop     r12
0x18006b035  pop     rdi
0x18006b036  pop     rsi
0x18006b037  pop     rbx
0x18006b038  pop     rbp
0x18006b039  retn
```
