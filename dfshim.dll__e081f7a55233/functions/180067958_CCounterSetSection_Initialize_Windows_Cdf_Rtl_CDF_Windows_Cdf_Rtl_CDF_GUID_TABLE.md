# CCounterSetSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_GUID_TABLE)

- ea: `0x180067958`
- end: `0x180067a41`
- name: `?Initialize@CCounterSetSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE@345@@Z`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180092cb0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005c2a8`
- `0x180067958`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800679c4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067a09`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800679c4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180067a09`

## string_xrefs

- `0x18006797e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800679cd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x180067a12`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCounterSetSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x2084,
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
      (const char *)0x2085,
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
0x180067958  mov     r11, rsp
0x18006795b  mov     [r11+8], rbx
0x18006795f  mov     [r11+10h], rsi
0x180067963  push    rdi
0x180067964  sub     rsp, 40h
0x180067968  mov     rax, rdx
0x18006796b  mov     dword ptr [rsp+48h+var_18], 0C00000E5h
0x180067973  lea     rdx, [rcx+18h]
0x180067977  mov     rsi, rcx
0x18006797a  cmp     qword ptr [rdx], 0
0x18006797e  lea     rcx, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067985  mov     [r11-28h], rcx
0x180067989  mov     rbx, r8
0x18006798c  jz      short loc_1800679A9
0x18006798e  mov     [rsp+48h+var_20], 8Eh
0x180067996  lea     rdx, [r11-28h]
0x18006799a  lea     rcx, [r11-28h]
0x18006799e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800679a3  mov     edi, dword ptr [rsp+48h+var_18]
0x1800679a7  jmp     short loc_1800679B8
0x1800679a9  mov     rcx, rax
0x1800679ac  call    CdfDuplicateHandle
0x1800679b1  xor     edi, edi
0x1800679b3  test    eax, eax
0x1800679b5  cmovs   edi, eax
0x1800679b8  test    edi, edi
0x1800679ba  jns     short loc_1800679EF
0x1800679bc  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x1800679c2  jnz     short loc_1800679CA
0x1800679c4  call    cs:__imp_DebugBreak
0x1800679ca  mov     r9d, edi; int
0x1800679cd  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800679d4  mov     r8d, 2084h; char *
0x1800679da  lea     rcx, aStatusPropagat; "Status propagated"
0x1800679e1  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800679e6  mov     ecx, edi; this
0x1800679e8  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800679ed  jmp     short loc_180067A31
0x1800679ef  lea     rcx, [rsi+20h]
0x1800679f3  mov     rdx, rbx
0x1800679f6  call    ?Assign@?$CTSHANDLE@V?$CCdfTableTraitsToTableTSHandleTraits@V?$CTableTraits@U_CDF_GUID_TABLE@Rtl@Cdf@Windows@@U_CDF_GUID_TABLE_ENUMERATOR@234@U_CDF_GUID_TABLE_ENUMERATOR_ITEM@234@@Rtl@Cdf@Windows@@@Rtl@Cdf@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAJU_CDF_GUID_TABLE@2Cdf@4@@Z; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Cdf::Rtl::CCdfTableTraitsToTableTSHandleTraits<Windows::Cdf::Rtl::CTableTraits<Windows::Cdf::Rtl::_CDF_GUID_TABLE,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_GUID_TABLE_ENUMERATOR_ITEM>>>::Assign(Windows::Cdf::Rtl::_CDF_GUID_TABLE)
0x1800679fb  mov     ebx, eax
0x1800679fd  test    eax, eax
0x1800679ff  jns     short loc_180067A2F
0x180067a01  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180067a07  jnz     short loc_180067A0F
0x180067a09  call    cs:__imp_DebugBreak
0x180067a0f  mov     r9d, ebx; int
0x180067a12  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180067a19  mov     r8d, 2085h; char *
0x180067a1f  lea     rcx, aStatusPropagat; "Status propagated"
0x180067a26  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180067a2b  mov     ecx, ebx
0x180067a2d  jmp     short loc_1800679E8
0x180067a2f  xor     eax, eax
0x180067a31  mov     rbx, [rsp+48h+arg_0]
0x180067a36  mov     rsi, [rsp+48h+arg_8]
0x180067a3b  add     rsp, 40h
0x180067a3f  pop     rdi
0x180067a40  retn
```
