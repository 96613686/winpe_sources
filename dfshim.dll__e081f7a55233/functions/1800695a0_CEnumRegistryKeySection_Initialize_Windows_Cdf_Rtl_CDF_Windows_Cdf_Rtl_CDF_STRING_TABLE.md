# CEnumRegistryKeySection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x1800695a0`
- end: `0x180069689`
- name: `?Initialize@CEnumRegistryKeySection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a1170`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x1800695a0`
- `0x1800d8368`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006960c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069651`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006960c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180069651`

## string_xrefs

- `0x1800695c6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180069615`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006965a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumRegistryKeySection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x5A1D,
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
      (const char *)0x5A1E,
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
0x1800695a0  mov     r11, rsp
0x1800695a3  mov     [r11+8], rbx
0x1800695a7  mov     [r11+10h], rsi
0x1800695ab  push    rdi
0x1800695ac  sub     rsp, 40h
0x1800695b0  mov     rax, rdx
0x1800695b3  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x1800695bb  lea     rdx, [rcx+10h]
0x1800695bf  mov     rsi, rcx
0x1800695c2  cmp     qword ptr [rdx], 0
0x1800695c6  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800695cd  mov     [r11-28h], rcx
0x1800695d1  mov     rbx, r8
0x1800695d4  jz      short loc_1800695F1
0x1800695d6  mov     [rsp+48h+var_20], 8Eh
0x1800695de  lea     rdx, [r11-28h]
0x1800695e2  lea     rcx, [r11-28h]
0x1800695e6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800695eb  mov     edi, dword ptr [rsp+48h+var_18]
0x1800695ef  jmp     short loc_180069600
0x1800695f1  mov     rcx, rax
0x1800695f4  call    CdfDuplicateHandle
0x1800695f9  xor     edi, edi
0x1800695fb  test    eax, eax
0x1800695fd  cmovs   edi, eax
0x180069600  test    edi, edi
0x180069602  jns     short loc_180069637
0x180069604  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006960a  jnz     short loc_180069612
0x18006960c  call    cs:__imp_DebugBreak
0x180069612  mov     r9d, edi; int
0x180069615  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006961c  mov     r8d, 5A1Dh; char *
0x180069622  lea     rcx, aStatusPropagat; "Status propagated"
0x180069629  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006962e  mov     ecx, edi; this
0x180069630  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180069635  jmp     short loc_180069679
0x180069637  lea     rdx, [rsi+18h]
0x18006963b  mov     rcx, rbx
0x18006963e  call    CdfEnumerateStringTable
0x180069643  mov     ebx, eax
0x180069645  test    eax, eax
0x180069647  jns     short loc_180069677
0x180069649  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18006964f  jnz     short loc_180069657
0x180069651  call    cs:__imp_DebugBreak
0x180069657  mov     r9d, ebx; int
0x18006965a  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180069661  mov     r8d, 5A1Eh; char *
0x180069667  lea     rcx, aStatusPropagat; "Status propagated"
0x18006966e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180069673  mov     ecx, ebx
0x180069675  jmp     short loc_180069630
0x180069677  xor     eax, eax
0x180069679  mov     rbx, [rsp+48h+arg_0]
0x18006967e  mov     rsi, [rsp+48h+arg_8]
0x180069683  add     rsp, 40h
0x180069687  pop     rdi
0x180069688  retn
```
