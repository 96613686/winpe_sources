# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000ac1c`
- end: `0x18000ac8b`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `111`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c68c`

## callees

- `0x18000bcd4`
- `0x18000bd80`

## string_xrefs

- `0x18000ac44`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // [rsp+50h] [rbp-18h]

  v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(a1, 454, "clientcore\\windows\\dwm\\dwmapi\\composition.cpp");
  return v9;
}

```

## disassembly

```asm
0x18000ac1c  mov     [rsp+arg_0], rbx
0x18000ac21  mov     [rsp+arg_8], rsi
0x18000ac26  push    rdi
0x18000ac27  sub     rsp, 60h
0x18000ac2b  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000ac32  mov     rsi, rcx
0x18000ac35  mov     ecx, ebx; this
0x18000ac37  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000ac3c  mov     rdx, [rsp+68h+arg_28]
0x18000ac44  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18000ac4b  mov     edi, eax
0x18000ac4d  mov     [rsp+68h+var_18], eax
0x18000ac51  lea     rax, [rsp+68h+var_18]
0x18000ac56  mov     [rsp+68h+var_14], ebx
0x18000ac5a  mov     [rsp+68h+var_38], rax
0x18000ac5f  mov     rcx, rsi
0x18000ac62  mov     [rsp+68h+var_40], rdx
0x18000ac67  mov     edx, 1C6h
0x18000ac6c  mov     [rsp+68h+var_10], 1
0x18000ac74  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000ac79  mov     rbx, [rsp+68h+arg_0]
0x18000ac7e  mov     eax, edi
0x18000ac80  mov     rsi, [rsp+68h+arg_8]
0x18000ac85  add     rsp, 60h
0x18000ac89  pop     rdi
0x18000ac8a  retn
```
