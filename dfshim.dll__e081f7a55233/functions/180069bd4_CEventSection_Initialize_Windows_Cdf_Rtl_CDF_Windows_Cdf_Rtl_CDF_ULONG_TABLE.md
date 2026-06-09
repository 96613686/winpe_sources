# CEventSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_ULONG_TABLE)

- ea: `0x180069bd4`
- end: `0x180069ce2`
- name: `?Initialize@CEventSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_ULONG_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180094f00`

## callees

- `0x180012950`
- `0x180014588`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x180069bd4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069c3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069caf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069c3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069caf`

## string_xrefs

- `0x180069bf7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180069c44`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180069cb8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEventSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1CEB,
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
      (const char *)0x1CEC,
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
0x180069bd4  push    rbp
0x180069bd6  push    rbx
0x180069bd7  push    rsi
0x180069bd8  push    rdi
0x180069bd9  push    r12
0x180069bdb  mov     rbp, rsp
0x180069bde  sub     rsp, 40h
0x180069be2  mov     rax, rdx
0x180069be5  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069bec  lea     rdx, [rcx+18h]
0x180069bf0  mov     rbx, r8
0x180069bf3  cmp     qword ptr [rdx], 0
0x180069bf7  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069bfe  mov     rsi, rcx
0x180069c01  mov     [rbp+var_20], r12
0x180069c05  jz      short loc_180069C20
0x180069c07  mov     [rbp+var_18], 8Eh
0x180069c0e  lea     rdx, [rbp+var_20]
0x180069c12  lea     rcx, [rbp+var_20]
0x180069c16  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069c1b  mov     edi, dword ptr [rbp+var_10]
0x180069c1e  jmp     short loc_180069C2F
0x180069c20  mov     rcx, rax
0x180069c23  call    CdfDuplicateHandle
0x180069c28  xor     edi, edi
0x180069c2a  test    eax, eax
0x180069c2c  cmovs   edi, eax
0x180069c2f  test    edi, edi
0x180069c31  jns     short loc_180069C66
0x180069c33  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180069c39  jnz     short loc_180069C41
0x180069c3b  call    cs:__imp_DebugBreak
0x180069c41  mov     r9d, edi; int
0x180069c44  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069c4b  mov     r8d, 1CEBh; char *
0x180069c51  lea     rcx, aStatusPropagat; "Status propagated"
0x180069c58  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069c5d  mov     ecx, edi; this
0x180069c5f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180069c64  jmp     short loc_180069CD7
0x180069c66  lea     rdx, [rsi+20h]
0x180069c6a  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069c71  cmp     qword ptr [rdx], 0
0x180069c75  mov     [rbp+var_20], r12
0x180069c79  jz      short loc_180069C94
0x180069c7b  mov     [rbp+var_18], 8Eh
0x180069c82  lea     rdx, [rbp+var_20]
0x180069c86  lea     rcx, [rbp+var_20]
0x180069c8a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069c8f  mov     ebx, dword ptr [rbp+var_10]
0x180069c92  jmp     short loc_180069CA3
0x180069c94  mov     rcx, rbx
0x180069c97  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_ULONG_TABLE,Windows::Cdf::Rtl::_CDF_ULONG_TABLE &)
0x180069c9c  xor     ebx, ebx
0x180069c9e  test    eax, eax
0x180069ca0  cmovs   ebx, eax
0x180069ca3  test    ebx, ebx
0x180069ca5  jns     short loc_180069CD5
0x180069ca7  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180069cad  jnz     short loc_180069CB5
0x180069caf  call    cs:__imp_DebugBreak
0x180069cb5  mov     r9d, ebx; int
0x180069cb8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069cbf  mov     r8d, 1CECh; char *
0x180069cc5  lea     rcx, aStatusPropagat; "Status propagated"
0x180069ccc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069cd1  mov     ecx, ebx
0x180069cd3  jmp     short loc_180069C5F
0x180069cd5  xor     eax, eax
0x180069cd7  add     rsp, 40h
0x180069cdb  pop     r12
0x180069cdd  pop     rdi
0x180069cde  pop     rsi
0x180069cdf  pop     rbx
0x180069ce0  pop     rbp
0x180069ce1  retn
```
