# wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18004234c`
- end: `0x1800423cc`
- name: `??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `128`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800431b4`

## callees

- `0x180009ec4`
- `0x180010ac4`

## string_xrefs

- `0x180042374`: `onecore\net\netprofiles\service\src\l2manager\clientlib\pluginclient.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  _DWORD v10[6]; // [rsp+50h] [rbp-18h] BYREF

  v10[0] = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v8 = v10[0];
  v10[1] = (_DWORD)a7;
  v10[2] = 1;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    27,
    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\pluginclient.cpp",
    0,
    0,
    a6,
    (__int64)v10,
    0);
  return v8;
}

```

## disassembly

```asm
0x18004234c  mov     [rsp+arg_0], rbx
0x180042351  mov     [rsp+arg_8], rsi
0x180042356  push    rdi
0x180042357  sub     rsp, 60h
0x18004235b  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180042362  mov     rsi, rcx
0x180042365  mov     ecx, ebx; this
0x180042367  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18004236c  mov     rdx, [rsp+68h+arg_28]
0x180042374  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18004237b  xor     ecx, ecx
0x18004237d  mov     [rsp+68h+var_18], eax
0x180042381  mov     [rsp+68h+var_20], ecx
0x180042385  mov     edi, eax
0x180042387  mov     [rsp+68h+var_30], rcx
0x18004238c  lea     rax, [rsp+68h+var_18]
0x180042391  mov     [rsp+68h+var_38], rax
0x180042396  xor     r9d, r9d
0x180042399  mov     [rsp+68h+var_40], rdx
0x18004239e  lea     edx, [rcx+1Bh]
0x1800423a1  mov     [rsp+68h+var_48], rcx
0x1800423a6  mov     rcx, rsi
0x1800423a9  mov     [rsp+68h+var_14], ebx
0x1800423ad  mov     [rsp+68h+var_10], 1
0x1800423b5  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800423ba  mov     rbx, [rsp+68h+arg_0]
0x1800423bf  mov     eax, edi
0x1800423c1  mov     rsi, [rsp+68h+arg_8]
0x1800423c6  add     rsp, 60h
0x1800423ca  pop     rdi
0x1800423cb  retn
```
