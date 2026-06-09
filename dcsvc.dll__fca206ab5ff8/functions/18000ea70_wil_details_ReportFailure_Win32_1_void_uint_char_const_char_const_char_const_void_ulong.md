# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000ea70`
- end: `0x18000ead2`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000ef00`

## callees

- `0x180002efc`
- `0x180005eec`
- `0x18000ea70`

## string_xrefs

- `0x18000eaa0`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`

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
  __int64 v8; // rdx
  __int64 v9; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    "onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp");
  return v7;
}

```

## disassembly

```asm
0x18000ea70  push    rbx
0x18000ea72  sub     rsp, 60h
0x18000ea76  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000ea7d  mov     r9, rcx
0x18000ea80  test    ebx, ebx
0x18000ea82  jle     short loc_18000EA8D
0x18000ea84  movzx   ebx, bx
0x18000ea87  or      ebx, 80070000h
0x18000ea8d  mov     ecx, ebx; this
0x18000ea8f  mov     [rsp+68h+var_18], ebx
0x18000ea93  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ea98  mov     rcx, [rsp+68h+arg_28]
0x18000eaa0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x18000eaa7  mov     [rsp+68h+var_14], eax
0x18000eaab  lea     rax, [rsp+68h+var_18]
0x18000eab0  mov     [rsp+68h+var_38], rax
0x18000eab5  mov     [rsp+68h+var_40], rcx
0x18000eaba  mov     rcx, r9
0x18000eabd  mov     [rsp+68h+var_10], 0
0x18000eac5  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000eaca  mov     eax, ebx
0x18000eacc  add     rsp, 60h
0x18000ead0  pop     rbx
0x18000ead1  retn
```
