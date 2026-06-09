# CCategoryMembershipDataSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_ULONG_TABLE)

- ea: `0x1800670ec`
- end: `0x1800671fa`
- name: `?Initialize@CCategoryMembershipDataSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_ULONG_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005dae4`
- `0x180062b80`
- `0x18008d7d0`

## callees

- `0x180012950`
- `0x180014588`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x1800670ec`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067153`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800671c7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067153`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800671c7`

## string_xrefs

- `0x18006710f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006715c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x1800671d0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCategoryMembershipDataSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x1533,
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
      (const char *)0x1534,
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
0x1800670ec  push    rbp
0x1800670ee  push    rbx
0x1800670ef  push    rsi
0x1800670f0  push    rdi
0x1800670f1  push    r12
0x1800670f3  mov     rbp, rsp
0x1800670f6  sub     rsp, 40h
0x1800670fa  mov     rax, rdx
0x1800670fd  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067104  lea     rdx, [rcx+18h]
0x180067108  mov     rbx, r8
0x18006710b  cmp     qword ptr [rdx], 0
0x18006710f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067116  mov     rsi, rcx
0x180067119  mov     [rbp+var_20], r12
0x18006711d  jz      short loc_180067138
0x18006711f  mov     [rbp+var_18], 8Eh
0x180067126  lea     rdx, [rbp+var_20]
0x18006712a  lea     rcx, [rbp+var_20]
0x18006712e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180067133  mov     edi, dword ptr [rbp+var_10]
0x180067136  jmp     short loc_180067147
0x180067138  mov     rcx, rax
0x18006713b  call    CdfDuplicateHandle
0x180067140  xor     edi, edi
0x180067142  test    eax, eax
0x180067144  cmovs   edi, eax
0x180067147  test    edi, edi
0x180067149  jns     short loc_18006717E
0x18006714b  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180067151  jnz     short loc_180067159
0x180067153  call    cs:__imp_DebugBreak
0x180067159  mov     r9d, edi; int
0x18006715c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067163  mov     r8d, 1533h; char *
0x180067169  lea     rcx, aStatusPropagat; "Status propagated"
0x180067170  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067175  mov     ecx, edi; this
0x180067177  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006717c  jmp     short loc_1800671EF
0x18006717e  lea     rdx, [rsi+20h]
0x180067182  mov     dword ptr [rbp+var_10], 0C00000E5h
0x180067189  cmp     qword ptr [rdx], 0
0x18006718d  mov     [rbp+var_20], r12
0x180067191  jz      short loc_1800671AC
0x180067193  mov     [rbp+var_18], 8Eh
0x18006719a  lea     rdx, [rbp+var_20]
0x18006719e  lea     rcx, [rbp+var_20]
0x1800671a2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800671a7  mov     ebx, dword ptr [rbp+var_10]
0x1800671aa  jmp     short loc_1800671BB
0x1800671ac  mov     rcx, rbx
0x1800671af  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_ULONG_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_ULONG_TABLE,Windows::Cdf::Rtl::_CDF_ULONG_TABLE &)
0x1800671b4  xor     ebx, ebx
0x1800671b6  test    eax, eax
0x1800671b8  cmovs   ebx, eax
0x1800671bb  test    ebx, ebx
0x1800671bd  jns     short loc_1800671ED
0x1800671bf  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800671c5  jnz     short loc_1800671CD
0x1800671c7  call    cs:__imp_DebugBreak
0x1800671cd  mov     r9d, ebx; int
0x1800671d0  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800671d7  mov     r8d, 1534h; char *
0x1800671dd  lea     rcx, aStatusPropagat; "Status propagated"
0x1800671e4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800671e9  mov     ecx, ebx
0x1800671eb  jmp     short loc_180067177
0x1800671ed  xor     eax, eax
0x1800671ef  add     rsp, 40h
0x1800671f3  pop     r12
0x1800671f5  pop     rdi
0x1800671f6  pop     rsi
0x1800671f7  pop     rbx
0x1800671f8  pop     rbp
0x1800671f9  retn
```
