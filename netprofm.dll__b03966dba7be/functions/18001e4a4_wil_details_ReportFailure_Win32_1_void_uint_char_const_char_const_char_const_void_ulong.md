# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18001e4a4`
- end: `0x18001e514`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001e51c`

## callees

- `0x180008bf8`
- `0x180014238`
- `0x18001e4a4`

## string_xrefs

- `0x18001e4d4`: `onecore\net\netprofiles\service\src\public\dll\netshhelper.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v8, 58, "onecore\\net\\netprofiles\\service\\src\\public\\dll\\netshhelper.cpp");
  return v7;
}

```

## disassembly

```asm
0x18001e4a4  push    rbx
0x18001e4a6  sub     rsp, 60h
0x18001e4aa  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18001e4b1  mov     r9, rcx
0x18001e4b4  test    ebx, ebx
0x18001e4b6  jle     short loc_18001E4C1
0x18001e4b8  movzx   ebx, bx
0x18001e4bb  or      ebx, 80070000h
0x18001e4c1  mov     ecx, ebx; this
0x18001e4c3  mov     [rsp+68h+var_18], ebx
0x18001e4c7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001e4cc  mov     rcx, [rsp+68h+arg_28]
0x18001e4d4  lea     r8, aOnecoreNetNetp_12; "onecore\\net\\netprofiles\\service\\src"...
0x18001e4db  mov     [rsp+68h+var_14], eax
0x18001e4df  mov     edx, 3Ah ; ':'
0x18001e4e4  lea     rax, [rsp+68h+var_18]
0x18001e4e9  mov     [rsp+68h+var_30], 0
0x18001e4f2  mov     [rsp+68h+var_38], rax
0x18001e4f7  mov     [rsp+68h+var_40], rcx
0x18001e4fc  mov     rcx, r9
0x18001e4ff  mov     [rsp+68h+var_10], 0
0x18001e507  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001e50c  mov     eax, ebx
0x18001e50e  add     rsp, 60h
0x18001e512  pop     rbx
0x18001e513  retn
```
