# CEnumCMS::Initialize(Windows::Cdf::Rtl::_CDF)

- ea: `0x18006843c`
- end: `0x1800685a9`
- name: `?Initialize@CEnumCMS@@QEAAJU_CDF@Rtl@Cdf@Windows@@@Z`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18009efe0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18002ff64`
- `0x180048d00`
- `0x180048d70`
- `0x18006843c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800684ad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800684f8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068553`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800684ad`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800684f8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180068553`

## string_xrefs

- `0x180068467`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800684b6`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180068501`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006855c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCMS::Initialize(__int64 a1, __int64 a2)
{
  bool v3; // zf
  int v5; // edi
  int v6; // eax
  int v7; // edx
  unsigned int v8; // edi
  int TOC; // eax
  unsigned int v10; // ebx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  int v17; // edx
  const char *v19; // [rsp+20h] [rbp-28h] BYREF
  int v20; // [rsp+28h] [rbp-20h]
  Windows::ErrorHandling::COM *v21; // [rsp+30h] [rbp-18h]
  __int64 v22; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(v21) = -1073741595;
  v22 = 0;
  v3 = *(_QWORD *)(a1 + 16) == 0;
  v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
  if ( v3 )
  {
    v6 = CdfDuplicateHandle(a2);
    v5 = 0;
    if ( v6 < 0 )
      v5 = v6;
  }
  else
  {
    v20 = 142;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v19,
      &v19);
    v5 = (int)v21;
  }
  if ( v5 < 0 )
  {
    if ( v5 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5C4F,
      v5,
      (unsigned int)v19);
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                           (Windows::ErrorHandling::COM *)(unsigned int)v5,
                           v7);
  }
  TOC = CdfGetTOC(a2, &v22);
  v10 = TOC;
  if ( TOC >= 0 )
  {
    v14 = v22;
    v15 = CdfEnumerateUlongTable(v22, a1 + 24);
    v16 = v15;
    if ( v15 >= 0 )
    {
      if ( v14 )
        CdfCloseUlongTableHandle(v14);
      return 0;
    }
    else
    {
      if ( v15 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x5C51,
        v16,
        (unsigned int)v19);
      v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v16, v17);
      if ( v14 )
      {
        v13 = v14;
LABEL_13:
        CdfCloseUlongTableHandle(v13);
      }
    }
  }
  else
  {
    if ( TOC == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x5C50,
      v10,
      (unsigned int)v19);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v11);
    v13 = v22;
    v8 = v12;
    if ( v22 )
      goto LABEL_13;
  }
  return v8;
}

```

## disassembly

```asm
0x18006843c  mov     r11, rsp
0x18006843f  mov     [r11+10h], rbx
0x180068443  mov     [r11+18h], rsi
0x180068447  push    rdi
0x180068448  sub     rsp, 40h
0x18006844c  mov     rbx, rdx
0x18006844f  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x180068457  lea     rdx, [rcx+10h]
0x18006845b  mov     qword ptr [r11+8], 0
0x180068463  cmp     qword ptr [rdx], 0
0x180068467  lea     rax, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006846e  mov     rsi, rcx
0x180068471  mov     [r11-28h], rax
0x180068475  jz      short loc_180068492
0x180068477  mov     [rsp+48h+var_20], 8Eh
0x18006847f  lea     rdx, [r11-28h]
0x180068483  lea     rcx, [r11-28h]
0x180068487  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006848c  mov     edi, dword ptr [rsp+48h+var_18]
0x180068490  jmp     short loc_1800684A1
0x180068492  mov     rcx, rbx
0x180068495  call    CdfDuplicateHandle
0x18006849a  xor     edi, edi
0x18006849c  test    eax, eax
0x18006849e  cmovs   edi, eax
0x1800684a1  test    edi, edi
0x1800684a3  jns     short loc_1800684DD
0x1800684a5  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x1800684ab  jnz     short loc_1800684B3
0x1800684ad  call    cs:__imp_DebugBreak
0x1800684b3  mov     r9d, edi; int
0x1800684b6  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800684bd  mov     r8d, 5C4Fh; char *
0x1800684c3  lea     rcx, aStatusPropagat; "Status propagated"
0x1800684ca  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800684cf  mov     ecx, edi; this
0x1800684d1  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800684d6  mov     edi, eax
0x1800684d8  jmp     loc_180068597
0x1800684dd  lea     rdx, [rsp+48h+arg_0]
0x1800684e2  mov     rcx, rbx
0x1800684e5  call    CdfGetTOC
0x1800684ea  mov     ebx, eax
0x1800684ec  test    eax, eax
0x1800684ee  jns     short loc_180068534
0x1800684f0  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800684f6  jnz     short loc_1800684FE
0x1800684f8  call    cs:__imp_DebugBreak
0x1800684fe  mov     r9d, ebx; int
0x180068501  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068508  mov     r8d, 5C50h; char *
0x18006850e  lea     rcx, aStatusPropagat; "Status propagated"
0x180068515  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006851a  mov     ecx, ebx; this
0x18006851c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180068521  mov     rcx, [rsp+48h+arg_0]
0x180068526  mov     edi, eax
0x180068528  test    rcx, rcx
0x18006852b  jz      short loc_180068597
0x18006852d  call    CdfCloseUlongTableHandle
0x180068532  jmp     short loc_180068597
0x180068534  mov     rbx, [rsp+48h+arg_0]
0x180068539  lea     rdx, [rsi+18h]
0x18006853d  mov     rcx, rbx
0x180068540  call    CdfEnumerateUlongTable
0x180068545  mov     edi, eax
0x180068547  test    eax, eax
0x180068549  jns     short loc_180068588
0x18006854b  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180068551  jnz     short loc_180068559
0x180068553  call    cs:__imp_DebugBreak
0x180068559  mov     r9d, edi; int
0x18006855c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180068563  mov     r8d, 5C51h; char *
0x180068569  lea     rcx, aStatusPropagat; "Status propagated"
0x180068570  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180068575  mov     ecx, edi; this
0x180068577  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006857c  mov     edi, eax
0x18006857e  test    rbx, rbx
0x180068581  jz      short loc_180068597
0x180068583  mov     rcx, rbx
0x180068586  jmp     short loc_18006852D
0x180068588  test    rbx, rbx
0x18006858b  jz      short loc_180068595
0x18006858d  mov     rcx, rbx
0x180068590  call    CdfCloseUlongTableHandle
0x180068595  xor     edi, edi
0x180068597  mov     rbx, [rsp+48h+arg_8]
0x18006859c  mov     eax, edi
0x18006859e  mov     rsi, [rsp+48h+arg_10]
0x1800685a3  add     rsp, 40h
0x1800685a7  pop     rdi
0x1800685a8  retn
```
