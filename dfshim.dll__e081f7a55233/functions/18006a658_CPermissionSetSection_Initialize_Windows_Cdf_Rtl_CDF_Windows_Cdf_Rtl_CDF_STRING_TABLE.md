# CPermissionSetSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006a658`
- end: `0x18006a766`
- name: `?Initialize@CPermissionSetSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180099490`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006a658`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a6bf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a733`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a6bf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a733`

## string_xrefs

- `0x18006a67b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006a6c8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006a73c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CPermissionSetSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1A8B,
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
      (const char *)0x1A8C,
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
0x18006a658  push    rbp
0x18006a65a  push    rbx
0x18006a65b  push    rsi
0x18006a65c  push    rdi
0x18006a65d  push    r12
0x18006a65f  mov     rbp, rsp
0x18006a662  sub     rsp, 40h
0x18006a666  mov     rax, rdx
0x18006a669  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a670  lea     rdx, [rcx+18h]
0x18006a674  mov     rbx, r8
0x18006a677  cmp     qword ptr [rdx], 0
0x18006a67b  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a682  mov     rsi, rcx
0x18006a685  mov     [rbp+var_20], r12
0x18006a689  jz      short loc_18006A6A4
0x18006a68b  mov     [rbp+var_18], 8Eh
0x18006a692  lea     rdx, [rbp+var_20]
0x18006a696  lea     rcx, [rbp+var_20]
0x18006a69a  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a69f  mov     edi, dword ptr [rbp+var_10]
0x18006a6a2  jmp     short loc_18006A6B3
0x18006a6a4  mov     rcx, rax
0x18006a6a7  call    CdfDuplicateHandle
0x18006a6ac  xor     edi, edi
0x18006a6ae  test    eax, eax
0x18006a6b0  cmovs   edi, eax
0x18006a6b3  test    edi, edi
0x18006a6b5  jns     short loc_18006A6EA
0x18006a6b7  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006a6bd  jnz     short loc_18006A6C5
0x18006a6bf  call    cs:__imp_DebugBreak
0x18006a6c5  mov     r9d, edi; int
0x18006a6c8  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a6cf  mov     r8d, 1A8Bh; char *
0x18006a6d5  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a6dc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a6e1  mov     ecx, edi; this
0x18006a6e3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006a6e8  jmp     short loc_18006A75B
0x18006a6ea  lea     rdx, [rsi+20h]
0x18006a6ee  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a6f5  cmp     qword ptr [rdx], 0
0x18006a6f9  mov     [rbp+var_20], r12
0x18006a6fd  jz      short loc_18006A718
0x18006a6ff  mov     [rbp+var_18], 8Eh
0x18006a706  lea     rdx, [rbp+var_20]
0x18006a70a  lea     rcx, [rbp+var_20]
0x18006a70e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a713  mov     ebx, dword ptr [rbp+var_10]
0x18006a716  jmp     short loc_18006A727
0x18006a718  mov     rcx, rbx
0x18006a71b  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006a720  xor     ebx, ebx
0x18006a722  test    eax, eax
0x18006a724  cmovs   ebx, eax
0x18006a727  test    ebx, ebx
0x18006a729  jns     short loc_18006A759
0x18006a72b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006a731  jnz     short loc_18006A739
0x18006a733  call    cs:__imp_DebugBreak
0x18006a739  mov     r9d, ebx; int
0x18006a73c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a743  mov     r8d, 1A8Ch; char *
0x18006a749  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a750  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a755  mov     ecx, ebx
0x18006a757  jmp     short loc_18006A6E3
0x18006a759  xor     eax, eax
0x18006a75b  add     rsp, 40h
0x18006a75f  pop     r12
0x18006a761  pop     rdi
0x18006a762  pop     rsi
0x18006a763  pop     rbx
0x18006a764  pop     rbp
0x18006a765  retn
```
