# CCOMRedirectionSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_GUID_TABLE)

- ea: `0x180066e98`
- end: `0x180066f81`
- name: `?Initialize@CCOMRedirectionSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x18008d5b0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005c2a8`
- `0x180066e98`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066f04`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066f49`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066f04`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180066f49`

## string_xrefs

- `0x180066ebe`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x180066f0d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180066f52`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCOMRedirectionSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x15C5,
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
      (const char *)0x15C6,
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
0x180066e98  mov     r11, rsp
0x180066e9b  mov     [r11+8], rbx
0x180066e9f  mov     [r11+10h], rsi
0x180066ea3  push    rdi
0x180066ea4  sub     rsp, 40h
0x180066ea8  mov     rax, rdx
0x180066eab  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x180066eb3  lea     rdx, [rcx+18h]
0x180066eb7  mov     rsi, rcx
0x180066eba  cmp     qword ptr [rdx], 0
0x180066ebe  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066ec5  mov     [r11-28h], rcx
0x180066ec9  mov     rbx, r8
0x180066ecc  jz      short loc_180066EE9
0x180066ece  mov     [rsp+48h+var_20], 8Eh
0x180066ed6  lea     rdx, [r11-28h]
0x180066eda  lea     rcx, [r11-28h]
0x180066ede  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180066ee3  mov     edi, dword ptr [rsp+48h+var_18]
0x180066ee7  jmp     short loc_180066EF8
0x180066ee9  mov     rcx, rax
0x180066eec  call    CdfDuplicateHandle
0x180066ef1  xor     edi, edi
0x180066ef3  test    eax, eax
0x180066ef5  cmovs   edi, eax
0x180066ef8  test    edi, edi
0x180066efa  jns     short loc_180066F2F
0x180066efc  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x180066f02  jnz     short loc_180066F0A
0x180066f04  call    cs:__imp_DebugBreak
0x180066f0a  mov     r9d, edi; int
0x180066f0d  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066f14  mov     r8d, 15C5h; char *
0x180066f1a  lea     rcx, aStatusPropagat; "Status propagated"
0x180066f21  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066f26  mov     ecx, edi; this
0x180066f28  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180066f2d  jmp     short loc_180066F71
0x180066f2f  lea     rcx, [rsi+20h]
0x180066f33  mov     rdx, rbx
0x180066f36  call    ?Assign@?$CTSHANDLE@V?$CCdfTableTraitsToTableTSHandleTraits@V?$CTableTraits@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE_ENUMERATOR@234@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@@Rtl@Cdf@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAJU_CDF_GUID_TABLE@2Cdf@4@@Z; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCdfTableTraitsToTableTSHandleTraits<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM>>>::Assign(Windows::Cdf::Rtl::_CDF_GUID_TABLE)
0x180066f3b  mov     ebx, eax
0x180066f3d  test    eax, eax
0x180066f3f  jns     short loc_180066F6F
0x180066f41  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180066f47  jnz     short loc_180066F4F
0x180066f49  call    cs:__imp_DebugBreak
0x180066f4f  mov     r9d, ebx; int
0x180066f52  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180066f59  mov     r8d, 15C6h; char *
0x180066f5f  lea     rcx, aStatusPropagat; "Status propagated"
0x180066f66  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180066f6b  mov     ecx, ebx
0x180066f6d  jmp     short loc_180066F28
0x180066f6f  xor     eax, eax
0x180066f71  mov     rbx, [rsp+48h+arg_0]
0x180066f76  mov     rsi, [rsp+48h+arg_8]
0x180066f7b  add     rsp, 40h
0x180066f7f  pop     rdi
0x180066f80  retn
```
