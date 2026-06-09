# CEnumCompatibleFrameworksSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_ULONG_TABLE)

- ea: `0x180068880`
- end: `0x180068969`
- name: `?Initialize@CEnumCompatibleFrameworksSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_ULONG_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009f730`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x180048d70`
- `0x180068880`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800688ec`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068931`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800688ec`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068931`

## string_xrefs

- `0x1800688a6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800688f5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006893a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCompatibleFrameworksSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x5BDD,
      v6,
      (unsigned int)v13);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  v11 = CdfEnumerateUlongTable(a3, a1 + 24);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5BDE,
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
0x180068880  mov     r11, rsp
0x180068883  mov     [r11+8], rbx
0x180068887  mov     [r11+10h], rsi
0x18006888b  push    rdi
0x18006888c  sub     rsp, 40h
0x180068890  mov     rax, rdx
0x180068893  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x18006889b  lea     rdx, [rcx+10h]
0x18006889f  mov     rsi, rcx
0x1800688a2  cmp     qword ptr [rdx], 0
0x1800688a6  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800688ad  mov     [r11-28h], rcx
0x1800688b1  mov     rbx, r8
0x1800688b4  jz      short loc_1800688D1
0x1800688b6  mov     [rsp+48h+var_20], 8Eh
0x1800688be  lea     rdx, [r11-28h]
0x1800688c2  lea     rcx, [r11-28h]
0x1800688c6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800688cb  mov     edi, dword ptr [rsp+48h+var_18]
0x1800688cf  jmp     short loc_1800688E0
0x1800688d1  mov     rcx, rax
0x1800688d4  call    CdfDuplicateHandle
0x1800688d9  xor     edi, edi
0x1800688db  test    eax, eax
0x1800688dd  cmovs   edi, eax
0x1800688e0  test    edi, edi
0x1800688e2  jns     short loc_180068917
0x1800688e4  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x1800688ea  jnz     short loc_1800688F2
0x1800688ec  call    cs:__imp_DebugBreak
0x1800688f2  mov     r9d, edi; int
0x1800688f5  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800688fc  mov     r8d, 5BDDh; char *
0x180068902  lea     rcx, aStatusPropagat; "Status propagated"
0x180068909  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006890e  mov     ecx, edi; this
0x180068910  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180068915  jmp     short loc_180068959
0x180068917  lea     rdx, [rsi+18h]
0x18006891b  mov     rcx, rbx
0x18006891e  call    CdfEnumerateUlongTable
0x180068923  mov     ebx, eax
0x180068925  test    eax, eax
0x180068927  jns     short loc_180068957
0x180068929  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18006892f  jnz     short loc_180068937
0x180068931  call    cs:__imp_DebugBreak
0x180068937  mov     r9d, ebx; int
0x18006893a  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068941  mov     r8d, 5BDEh; char *
0x180068947  lea     rcx, aStatusPropagat; "Status propagated"
0x18006894e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068953  mov     ecx, ebx
0x180068955  jmp     short loc_180068910
0x180068957  xor     eax, eax
0x180068959  mov     rbx, [rsp+48h+arg_0]
0x18006895e  mov     rsi, [rsp+48h+arg_8]
0x180068963  add     rsp, 40h
0x180068967  pop     rdi
0x180068968  retn
```
