# CEnumCOMRedirectionSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_GUID_TABLE)

- ea: `0x1800685b0`
- end: `0x180068699`
- name: `?Initialize@CEnumCOMRedirectionSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009f190`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x1800685b0`
- `0x1800d537c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006861c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068661`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006861c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068661`

## string_xrefs

- `0x1800685d6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180068625`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006866a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCOMRedirectionSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x531A,
      v6,
      (unsigned int)v13);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  v11 = CdfEnumerateGuidTable(a3, a1 + 24);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x531B,
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
0x1800685b0  mov     r11, rsp
0x1800685b3  mov     [r11+8], rbx
0x1800685b7  mov     [r11+10h], rsi
0x1800685bb  push    rdi
0x1800685bc  sub     rsp, 40h
0x1800685c0  mov     rax, rdx
0x1800685c3  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x1800685cb  lea     rdx, [rcx+10h]
0x1800685cf  mov     rsi, rcx
0x1800685d2  cmp     qword ptr [rdx], 0
0x1800685d6  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800685dd  mov     [r11-28h], rcx
0x1800685e1  mov     rbx, r8
0x1800685e4  jz      short loc_180068601
0x1800685e6  mov     [rsp+48h+var_20], 8Eh
0x1800685ee  lea     rdx, [r11-28h]
0x1800685f2  lea     rcx, [r11-28h]
0x1800685f6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800685fb  mov     edi, dword ptr [rsp+48h+var_18]
0x1800685ff  jmp     short loc_180068610
0x180068601  mov     rcx, rax
0x180068604  call    CdfDuplicateHandle
0x180068609  xor     edi, edi
0x18006860b  test    eax, eax
0x18006860d  cmovs   edi, eax
0x180068610  test    edi, edi
0x180068612  jns     short loc_180068647
0x180068614  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006861a  jnz     short loc_180068622
0x18006861c  call    cs:__imp_DebugBreak
0x180068622  mov     r9d, edi; int
0x180068625  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006862c  mov     r8d, 531Ah; char *
0x180068632  lea     rcx, aStatusPropagat; "Status propagated"
0x180068639  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006863e  mov     ecx, edi; this
0x180068640  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180068645  jmp     short loc_180068689
0x180068647  lea     rdx, [rsi+18h]
0x18006864b  mov     rcx, rbx
0x18006864e  call    CdfEnumerateGuidTable
0x180068653  mov     ebx, eax
0x180068655  test    eax, eax
0x180068657  jns     short loc_180068687
0x180068659  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18006865f  jnz     short loc_180068667
0x180068661  call    cs:__imp_DebugBreak
0x180068667  mov     r9d, ebx; int
0x18006866a  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068671  mov     r8d, 531Bh; char *
0x180068677  lea     rcx, aStatusPropagat; "Status propagated"
0x18006867e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068683  mov     ecx, ebx
0x180068685  jmp     short loc_180068640
0x180068687  xor     eax, eax
0x180068689  mov     rbx, [rsp+48h+arg_0]
0x18006868e  mov     rsi, [rsp+48h+arg_8]
0x180068693  add     rsp, 40h
0x180068697  pop     rdi
0x180068698  retn
```
