# CEnumDirectorySection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x180068c40`
- end: `0x180068d29`
- name: `?Initialize@CEnumDirectorySection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009feb0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x180068c40`
- `0x1800d8368`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068cac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068cf1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068cac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068cf1`

## string_xrefs

- `0x180068c66`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180068cb5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180068cfa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumDirectorySection::Initialize(__int64 a1, __int64 a2, __int64 a3)
{
  bool v4; // zf
  int v6; // edi
  int v7; // eax
  int v8; // edx
  unsigned __int64 v9; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  const char *v13; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+28h] [rbp-20h]
  Windows::ErrorHandling::COM *v15; // [rsp+30h] [rbp-18h]

  LODWORD(v15) = -1073741595;
  v4 = *(_QWORD *)(a1 + 16) == 0;
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
      (const char *)0x5A8D,
      v6,
      (unsigned int)v13);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  v11 = CdfEnumerateStringTable(a3, a1 + 24);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5A8E,
      v12,
      (unsigned int)v13);
    v9 = v12;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180068c40  mov     r11, rsp
0x180068c43  mov     [r11+8], rbx
0x180068c47  mov     [r11+10h], rsi
0x180068c4b  push    rdi
0x180068c4c  sub     rsp, 40h
0x180068c50  mov     rax, rdx
0x180068c53  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x180068c5b  lea     rdx, [rcx+10h]
0x180068c5f  mov     rsi, rcx
0x180068c62  cmp     qword ptr [rdx], 0
0x180068c66  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068c6d  mov     [r11-28h], rcx
0x180068c71  mov     rbx, r8
0x180068c74  jz      short loc_180068C91
0x180068c76  mov     [rsp+48h+var_20], 8Eh
0x180068c7e  lea     rdx, [r11-28h]
0x180068c82  lea     rcx, [r11-28h]
0x180068c86  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180068c8b  mov     edi, dword ptr [rsp+48h+var_18]
0x180068c8f  jmp     short loc_180068CA0
0x180068c91  mov     rcx, rax
0x180068c94  call    CdfDuplicateHandle
0x180068c99  xor     edi, edi
0x180068c9b  test    eax, eax
0x180068c9d  cmovs   edi, eax
0x180068ca0  test    edi, edi
0x180068ca2  jns     short loc_180068CD7
0x180068ca4  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180068caa  jnz     short loc_180068CB2
0x180068cac  call    cs:__imp_DebugBreak
0x180068cb2  mov     r9d, edi; int
0x180068cb5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068cbc  mov     r8d, 5A8Dh; char *
0x180068cc2  lea     rcx, aStatusPropagat; "Status propagated"
0x180068cc9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068cce  mov     ecx, edi; this
0x180068cd0  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180068cd5  jmp     short loc_180068D19
0x180068cd7  lea     rdx, [rsi+18h]
0x180068cdb  mov     rcx, rbx
0x180068cde  call    CdfEnumerateStringTable
0x180068ce3  mov     ebx, eax
0x180068ce5  test    eax, eax
0x180068ce7  jns     short loc_180068D17
0x180068ce9  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180068cef  jnz     short loc_180068CF7
0x180068cf1  call    cs:__imp_DebugBreak
0x180068cf7  mov     r9d, ebx; int
0x180068cfa  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068d01  mov     r8d, 5A8Eh; char *
0x180068d07  lea     rcx, aStatusPropagat; "Status propagated"
0x180068d0e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068d13  mov     ecx, ebx
0x180068d15  jmp     short loc_180068CD0
0x180068d17  xor     eax, eax
0x180068d19  mov     rbx, [rsp+48h+arg_0]
0x180068d1e  mov     rsi, [rsp+48h+arg_8]
0x180068d23  add     rsp, 40h
0x180068d27  pop     rdi
0x180068d28  retn
```
