# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002554`
- end: `0x180002585`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000258c`
- `0x1800026e0`
- `0x1800028d4`

## callees

- `0x180002938`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v8; // [rsp+20h] [rbp-38h]

  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4, v8, a6, a7, a8);
}

```

## disassembly

```asm
0x180002554  sub     rsp, 58h
0x180002558  mov     rax, [rsp+58h+arg_38]
0x180002560  mov     [rsp+58h+var_20], rax
0x180002565  mov     rax, [rsp+58h+arg_30]
0x18000256d  mov     [rsp+58h+var_28], rax
0x180002572  mov     rax, [rsp+58h+arg_28]
0x18000257a  mov     [rsp+58h+var_30], rax
0x18000257f  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
