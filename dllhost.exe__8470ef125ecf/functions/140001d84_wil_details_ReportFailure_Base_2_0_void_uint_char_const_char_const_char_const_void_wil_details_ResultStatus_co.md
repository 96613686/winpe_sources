# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140001d84`
- end: `0x140001dcc`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e74`

## callees

- `0x140002174`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Base<2,0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int *a7,
        __int64 a8,
        __int64 a9,
        int a10)
{
  int v10; // [rsp+40h] [rbp-18h]

  wil::details::ReportFailure_Return<2>(a1, a2, a3, a4, a5, a6, a7, 0, v10, a10);
}

```

## disassembly

```asm
0x140001d84  mov     r11, rsp
0x140001d87  sub     rsp, 58h
0x140001d8b  mov     eax, [rsp+58h+arg_48]
0x140001d92  mov     [rsp+58h+var_10], eax
0x140001d96  mov     rax, [rsp+58h+arg_30]
0x140001d9e  mov     qword ptr [r11-20h], 0
0x140001da6  mov     [r11-28h], rax
0x140001daa  mov     rax, [rsp+58h+arg_28]
0x140001db2  mov     [r11-30h], rax
0x140001db6  mov     rax, [rsp+58h+arg_20]
0x140001dbe  mov     [r11-38h], rax
0x140001dc2  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140001dc7  add     rsp, 58h
0x140001dcb  retn
```
