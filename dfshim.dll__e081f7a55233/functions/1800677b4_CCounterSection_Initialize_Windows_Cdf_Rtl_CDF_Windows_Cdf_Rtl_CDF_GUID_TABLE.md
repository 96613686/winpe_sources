# CCounterSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_GUID_TABLE)

- ea: `0x1800677b4`
- end: `0x18006789d`
- name: `?Initialize@CCounterSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180092930`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005c2a8`
- `0x1800677b4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067820`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067865`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067820`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067865`

## string_xrefs

- `0x1800677da`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180067829`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006786e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCounterSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x211A,
      v6,
      (unsigned int)v13);
    v9 = (unsigned int)v6;
    return Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
  }
  v11 = Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCdfTableTraitsToTableTSHandleTraits<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM>>>::Assign(
          a1 + 32,
          a3);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
      (const char *)0x211B,
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
0x1800677b4  mov     r11, rsp
0x1800677b7  mov     [r11+8], rbx
0x1800677bb  mov     [r11+10h], rsi
0x1800677bf  push    rdi
0x1800677c0  sub     rsp, 40h
0x1800677c4  mov     rax, rdx
0x1800677c7  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x1800677cf  lea     rdx, [rcx+18h]
0x1800677d3  mov     rsi, rcx
0x1800677d6  cmp     qword ptr [rdx], 0
0x1800677da  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800677e1  mov     [r11-28h], rcx
0x1800677e5  mov     rbx, r8
0x1800677e8  jz      short loc_180067805
0x1800677ea  mov     [rsp+48h+var_20], 8Eh
0x1800677f2  lea     rdx, [r11-28h]
0x1800677f6  lea     rcx, [r11-28h]
0x1800677fa  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800677ff  mov     edi, dword ptr [rsp+48h+var_18]
0x180067803  jmp     short loc_180067814
0x180067805  mov     rcx, rax
0x180067808  call    CdfDuplicateHandle
0x18006780d  xor     edi, edi
0x18006780f  test    eax, eax
0x180067811  cmovs   edi, eax
0x180067814  test    edi, edi
0x180067816  jns     short loc_18006784B
0x180067818  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006781e  jnz     short loc_180067826
0x180067820  call    cs:__imp_DebugBreak
0x180067826  mov     r9d, edi; int
0x180067829  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067830  mov     r8d, 211Ah; char *
0x180067836  lea     rcx, aStatusPropagat; "Status propagated"
0x18006783d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067842  mov     ecx, edi; this
0x180067844  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180067849  jmp     short loc_18006788D
0x18006784b  lea     rcx, [rsi+20h]
0x18006784f  mov     rdx, rbx
0x180067852  call    ?Assign@?$CTSHANDLE@V?$CCdfTableTraitsToTableTSHandleTraits@V?$CTableTraits@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE_ENUMERATOR@234@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@@Rtl@Cdf@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAJU_CDF_GUID_TABLE@2Cdf@4@@Z; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCdfTableTraitsToTableTSHandleTraits<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM>>>::Assign(Windows::Cdf::Rtl::_CDF_GUID_TABLE)
0x180067857  mov     ebx, eax
0x180067859  test    eax, eax
0x18006785b  jns     short loc_18006788B
0x18006785d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180067863  jnz     short loc_18006786B
0x180067865  call    cs:__imp_DebugBreak
0x18006786b  mov     r9d, ebx; int
0x18006786e  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067875  mov     r8d, 211Bh; char *
0x18006787b  lea     rcx, aStatusPropagat; "Status propagated"
0x180067882  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067887  mov     ecx, ebx
0x180067889  jmp     short loc_180067844
0x18006788b  xor     eax, eax
0x18006788d  mov     rbx, [rsp+48h+arg_0]
0x180067892  mov     rsi, [rsp+48h+arg_8]
0x180067897  add     rsp, 40h
0x18006789b  pop     rdi
0x18006789c  retn
```
