# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000214c`
- end: `0x180002170`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002178`
- `0x18000234c`

## callees

- `0x1800023a0`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v7; // [rsp+20h] [rbp-38h]

  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4, v7, a6, a7);
}

```

## disassembly

```asm
0x18000214c  sub     rsp, 58h
0x180002150  mov     rax, [rsp+58h+arg_30]
0x180002158  mov     [rsp+58h+var_28], rax
0x18000215d  mov     rax, [rsp+58h+arg_28]
0x180002165  mov     [rsp+58h+var_30], rax
0x18000216a  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
