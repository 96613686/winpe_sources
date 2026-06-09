# CEntryPointSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180068058`
- end: `0x180068166`
- name: `?Initialize@CEntryPointSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180094730`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180068058`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800680bf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068133`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800680bf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068133`

## string_xrefs

- `0x18006807b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800680c8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006813c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEntryPointSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x19F0,
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
      (const char *)0x19F1,
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
0x180068058  push    rbp
0x18006805a  push    rbx
0x18006805b  push    rsi
0x18006805c  push    rdi
0x18006805d  push    r12
0x18006805f  mov     rbp, rsp
0x180068062  sub     rsp, 40h
0x180068066  mov     rax, rdx
0x180068069  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180068070  lea     rdx, [rcx+18h]
0x180068074  mov     rbx, r8
0x180068077  cmp     qword ptr [rdx], 0
0x18006807b  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068082  mov     rsi, rcx
0x180068085  mov     [rbp+var_20], r12
0x180068089  jz      short loc_1800680A4
0x18006808b  mov     [rbp+var_18], 8Eh
0x180068092  lea     rdx, [rbp+var_20]
0x180068096  lea     rcx, [rbp+var_20]
0x18006809a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006809f  mov     edi, dword ptr [rbp+var_10]
0x1800680a2  jmp     short loc_1800680B3
0x1800680a4  mov     rcx, rax
0x1800680a7  call    CdfDuplicateHandle
0x1800680ac  xor     edi, edi
0x1800680ae  test    eax, eax
0x1800680b0  cmovs   edi, eax
0x1800680b3  test    edi, edi
0x1800680b5  jns     short loc_1800680EA
0x1800680b7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x1800680bd  jnz     short loc_1800680C5
0x1800680bf  call    cs:__imp_DebugBreak
0x1800680c5  mov     r9d, edi; int
0x1800680c8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800680cf  mov     r8d, 19F0h; char *
0x1800680d5  lea     rcx, aStatusPropagat; "Status propagated"
0x1800680dc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800680e1  mov     ecx, edi; this
0x1800680e3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800680e8  jmp     short loc_18006815B
0x1800680ea  lea     rdx, [rsi+20h]
0x1800680ee  mov     dword ptr [rbp+var_10], 0C00000E5h
0x1800680f5  cmp     qword ptr [rdx], 0
0x1800680f9  mov     [rbp+var_20], r12
0x1800680fd  jz      short loc_180068118
0x1800680ff  mov     [rbp+var_18], 8Eh
0x180068106  lea     rdx, [rbp+var_20]
0x18006810a  lea     rcx, [rbp+var_20]
0x18006810e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180068113  mov     ebx, dword ptr [rbp+var_10]
0x180068116  jmp     short loc_180068127
0x180068118  mov     rcx, rbx
0x18006811b  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x180068120  xor     ebx, ebx
0x180068122  test    eax, eax
0x180068124  cmovs   ebx, eax
0x180068127  test    ebx, ebx
0x180068129  jns     short loc_180068159
0x18006812b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180068131  jnz     short loc_180068139
0x180068133  call    cs:__imp_DebugBreak
0x180068139  mov     r9d, ebx; int
0x18006813c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068143  mov     r8d, 19F1h; char *
0x180068149  lea     rcx, aStatusPropagat; "Status propagated"
0x180068150  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068155  mov     ecx, ebx
0x180068157  jmp     short loc_1800680E3
0x180068159  xor     eax, eax
0x18006815b  add     rsp, 40h
0x18006815f  pop     r12
0x180068161  pop     rdi
0x180068162  pop     rsi
0x180068163  pop     rbx
0x180068164  pop     rbp
0x180068165  retn
```
