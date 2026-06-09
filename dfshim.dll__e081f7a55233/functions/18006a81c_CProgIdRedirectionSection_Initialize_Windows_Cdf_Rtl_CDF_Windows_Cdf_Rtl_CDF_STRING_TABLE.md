# CProgIdRedirectionSection::Initialize(Windows::Cdf::Rtl::_CDF,Windows::Cdf::Rtl::_CDF_STRING_TABLE)

- ea: `0x18006a81c`
- end: `0x18006a92a`
- name: `?Initialize@CProgIdRedirectionSection@@QEAAJU_CDF@Rtl@Cdf@Windows@@U_CDF_STRING_TABLE@345@@Z`
- size: `270`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065590`
- `0x180074680`
- `0x180099ad0`

## callees

- `0x180012950`
- `0x1800187f0`
- `0x180018940`
- `0x18002f5b4`
- `0x18005dd28`
- `0x18006a81c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a883`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a8f7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a883`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006a8f7`

## string_xrefs

- `0x18006a83f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x18006a88c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`
- `0x18006a900`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CProgIdRedirectionSection::Initialize(__int64 a1, __int64 a2, __int64 a3)
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
      (const char *)0x165B,
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
      (const char *)0x165C,
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
0x18006a81c  push    rbp
0x18006a81e  push    rbx
0x18006a81f  push    rsi
0x18006a820  push    rdi
0x18006a821  push    r12
0x18006a823  mov     rbp, rsp
0x18006a826  sub     rsp, 40h
0x18006a82a  mov     rax, rdx
0x18006a82d  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a834  lea     rdx, [rcx+18h]
0x18006a838  mov     rbx, r8
0x18006a83b  cmp     qword ptr [rdx], 0
0x18006a83f  lea     r12, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a846  mov     rsi, rcx
0x18006a849  mov     [rbp+var_20], r12
0x18006a84d  jz      short loc_18006A868
0x18006a84f  mov     [rbp+var_18], 8Eh
0x18006a856  lea     rdx, [rbp+var_20]
0x18006a85a  lea     rcx, [rbp+var_20]
0x18006a85e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a863  mov     edi, dword ptr [rbp+var_10]
0x18006a866  jmp     short loc_18006A877
0x18006a868  mov     rcx, rax
0x18006a86b  call    CdfDuplicateHandle
0x18006a870  xor     edi, edi
0x18006a872  test    eax, eax
0x18006a874  cmovs   edi, eax
0x18006a877  test    edi, edi
0x18006a879  jns     short loc_18006A8AE
0x18006a87b  cmp     edi, cs:g_NTSTATUS_to_break_on_propagate
0x18006a881  jnz     short loc_18006A889
0x18006a883  call    cs:__imp_DebugBreak
0x18006a889  mov     r9d, edi; int
0x18006a88c  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a893  mov     r8d, 165Bh; char *
0x18006a899  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a8a0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a8a5  mov     ecx, edi; this
0x18006a8a7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18006a8ac  jmp     short loc_18006A91F
0x18006a8ae  lea     rdx, [rsi+20h]
0x18006a8b2  mov     dword ptr [rbp+var_10], 0C00000E5h
0x18006a8b9  cmp     qword ptr [rdx], 0
0x18006a8bd  mov     [rbp+var_20], r12
0x18006a8c1  jz      short loc_18006A8DC
0x18006a8c3  mov     [rbp+var_18], 8Eh
0x18006a8ca  lea     rdx, [rbp+var_20]
0x18006a8ce  lea     rcx, [rbp+var_20]
0x18006a8d2  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18006a8d7  mov     ebx, dword ptr [rbp+var_10]
0x18006a8da  jmp     short loc_18006A8EB
0x18006a8dc  mov     rcx, rbx
0x18006a8df  call    ?Duplicate@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE@123@AEAU4123@@Z; Windows::Cdf::Rtl::Duplicate(Windows::Cdf::Rtl::_CDF_STRING_TABLE,Windows::Cdf::Rtl::_CDF_STRING_TABLE &)
0x18006a8e4  xor     ebx, ebx
0x18006a8e6  test    eax, eax
0x18006a8e8  cmovs   ebx, eax
0x18006a8eb  test    ebx, ebx
0x18006a8ed  jns     short loc_18006A91D
0x18006a8ef  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18006a8f5  jnz     short loc_18006A8FD
0x18006a8f7  call    cs:__imp_DebugBreak
0x18006a8fd  mov     r9d, ebx; int
0x18006a900  lea     rdx, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18006a907  mov     r8d, 165Ch; char *
0x18006a90d  lea     rcx, aStatusPropagat; "Status propagated"
0x18006a914  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18006a919  mov     ecx, ebx
0x18006a91b  jmp     short loc_18006A8A7
0x18006a91d  xor     eax, eax
0x18006a91f  add     rsp, 40h
0x18006a923  pop     r12
0x18006a925  pop     rdi
0x18006a926  pop     rsi
0x18006a927  pop     rbx
0x18006a928  pop     rbp
0x18006a929  retn
```
