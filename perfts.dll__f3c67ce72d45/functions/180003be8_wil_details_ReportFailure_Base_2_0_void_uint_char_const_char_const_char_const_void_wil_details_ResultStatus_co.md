# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003be8`
- end: `0x180003c34`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c74`
- `0x180003dd8`

## callees

- `0x1800040c4`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Base<2,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  return wil::details::ReportFailure_Return<2>(a1, a2, a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x180003be8  mov     r11, rsp
0x180003beb  sub     rsp, 58h
0x180003bef  mov     eax, [rsp+58h+arg_48]
0x180003bf6  mov     [rsp+58h+var_10], eax
0x180003bfa  mov     rax, [rsp+58h+arg_38]
0x180003c02  mov     [r11-20h], rax
0x180003c06  mov     rax, [rsp+58h+arg_30]
0x180003c0e  mov     [r11-28h], rax
0x180003c12  mov     rax, [rsp+58h+arg_28]
0x180003c1a  mov     [r11-30h], rax
0x180003c1e  mov     rax, [rsp+58h+arg_20]
0x180003c26  mov     [r11-38h], rax
0x180003c2a  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003c2f  add     rsp, 58h
0x180003c33  retn
```
