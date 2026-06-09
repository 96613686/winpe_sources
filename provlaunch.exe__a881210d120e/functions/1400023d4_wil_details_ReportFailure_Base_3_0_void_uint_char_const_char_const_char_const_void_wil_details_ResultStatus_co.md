# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400023d4`
- end: `0x140002405`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002438`
- `0x14000257c`
- `0x140002778`

## callees

- `0x1400027dc`

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
0x1400023d4  sub     rsp, 58h
0x1400023d8  mov     rax, [rsp+58h+arg_38]
0x1400023e0  mov     [rsp+58h+var_20], rax
0x1400023e5  mov     rax, [rsp+58h+arg_30]
0x1400023ed  mov     [rsp+58h+var_28], rax
0x1400023f2  mov     rax, [rsp+58h+arg_28]
0x1400023fa  mov     [rsp+58h+var_30], rax
0x1400023ff  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
