# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000262c`
- end: `0x140002650`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002658`
- `0x1400027fc`

## callees

- `0x140002858`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(int a1, int a2, int a3, int a4)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000262c  sub     rsp, 58h
0x140002630  mov     rax, [rsp+58h+arg_30]
0x140002638  mov     [rsp+58h+var_28], rax
0x14000263d  mov     rax, [rsp+58h+arg_28]
0x140002645  mov     [rsp+58h+var_30], rax
0x14000264a  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
