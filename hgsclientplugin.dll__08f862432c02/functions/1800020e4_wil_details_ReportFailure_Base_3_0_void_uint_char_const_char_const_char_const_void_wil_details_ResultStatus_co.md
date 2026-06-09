# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800020e4`
- end: `0x180002115`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000211c`
- `0x180002310`
- `0x180007080`
- `0x180009aa4`

## callees

- `0x180002374`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800020e4  sub     rsp, 58h
0x1800020e8  mov     rax, [rsp+58h+arg_38]
0x1800020f0  mov     [rsp+58h+var_20], rax
0x1800020f5  mov     rax, [rsp+58h+arg_30]
0x1800020fd  mov     [rsp+58h+var_28], rax
0x180002102  mov     rax, [rsp+58h+arg_28]
0x18000210a  mov     [rsp+58h+var_30], rax
0x18000210f  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)
```
