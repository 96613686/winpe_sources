# CFileAssociationSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180069f5c`
- end: `0x18006a06a`
- name: `?Initialize@CFileAssociationSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180095400`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x180069f5c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069fc3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a037`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069fc3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a037`

## string_xrefs

- `0x180069f7f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180069fcc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006a040`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CFileAssociationSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1368,
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
      (const char *)0x1369,
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
0x180069f5c  push    rbp
0x180069f5e  push    rbx
0x180069f5f  push    rsi
0x180069f60  push    rdi
0x180069f61  push    r12
0x180069f63  mov     rbp, rsp
0x180069f66  sub     rsp, 40h
0x180069f6a  mov     rax, rdx
0x180069f6d  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069f74  lea     rdx, [rcx+18h]
0x180069f78  mov     rbx, r8
0x180069f7b  cmp     qword ptr [rdx], 0
0x180069f7f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069f86  mov     rsi, rcx
0x180069f89  mov     [rbp+var_20], r12
0x180069f8d  jz      short loc_180069FA8
0x180069f8f  mov     [rbp+var_18], 8Eh
0x180069f96  lea     rdx, [rbp+var_20]
0x180069f9a  lea     rcx, [rbp+var_20]
0x180069f9e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180069fa3  mov     edi, dword ptr [rbp+var_10]
0x180069fa6  jmp     short loc_180069FB7
0x180069fa8  mov     rcx, rax
0x180069fab  call    CdfDuplicateHandle
0x180069fb0  xor     edi, edi
0x180069fb2  test    eax, eax
0x180069fb4  cmovs   edi, eax
0x180069fb7  test    edi, edi
0x180069fb9  jns     short loc_180069FEE
0x180069fbb  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180069fc1  jnz     short loc_180069FC9
0x180069fc3  call    cs:__imp_DebugBreak
0x180069fc9  mov     r9d, edi; int
0x180069fcc  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069fd3  mov     r8d, 1368h; char *
0x180069fd9  lea     rcx, aStatusPropagat; "Status propagated"
0x180069fe0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069fe5  mov     ecx, edi; this
0x180069fe7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180069fec  jmp     short loc_18006A05F
0x180069fee  lea     rdx, [rsi+20h]
0x180069ff2  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180069ff9  cmp     qword ptr [rdx], 0
0x180069ffd  mov     [rbp+var_20], r12
0x18006a001  jz      short loc_18006A01C
0x18006a003  mov     [rbp+var_18], 8Eh
0x18006a00a  lea     rdx, [rbp+var_20]
0x18006a00e  lea     rcx, [rbp+var_20]
0x18006a012  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a017  mov     ebx, dword ptr [rbp+var_10]
0x18006a01a  jmp     short loc_18006A02B
0x18006a01c  mov     rcx, rbx
0x18006a01f  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006a024  xor     ebx, ebx
0x18006a026  test    eax, eax
0x18006a028  cmovs   ebx, eax
0x18006a02b  test    ebx, ebx
0x18006a02d  jns     short loc_18006A05D
0x18006a02f  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006a035  jnz     short loc_18006A03D
0x18006a037  call    cs:__imp_DebugBreak
0x18006a03d  mov     r9d, ebx; int
0x18006a040  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a047  mov     r8d, 1369h; char *
0x18006a04d  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a054  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a059  mov     ecx, ebx
0x18006a05b  jmp     short loc_180069FE7
0x18006a05d  xor     eax, eax
0x18006a05f  add     rsp, 40h
0x18006a063  pop     r12
0x18006a065  pop     rdi
0x18006a066  pop     rsi
0x18006a067  pop     rbx
0x18006a068  pop     rbp
0x18006a069  retn
```
