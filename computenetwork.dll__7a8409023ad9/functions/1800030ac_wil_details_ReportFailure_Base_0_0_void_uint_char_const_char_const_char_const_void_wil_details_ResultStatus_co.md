# wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800030ac`
- end: `0x1800030dd`
- name: `??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000348c`
- `0x180009dd0`
- `0x180009fa0`
- `0x18000bb44`

## callees

- `0x180003770`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<0,0>(
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

  wil::details::ReportFailure_NoReturn<0>(a1, a2, a3, a4, v8, a6, a7, a8);
}

```

## disassembly

```asm
0x1800030ac  sub     rsp, 58h
0x1800030b0  mov     rax, [rsp+58h+arg_38]
0x1800030b8  mov     [rsp+58h+var_20], rax
0x1800030bd  mov     rax, [rsp+58h+arg_30]
0x1800030c5  mov     [rsp+58h+var_28], rax
0x1800030ca  mov     rax, [rsp+58h+arg_28]
0x1800030d2  mov     [rsp+58h+var_30], rax
0x1800030d7  call    ??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
