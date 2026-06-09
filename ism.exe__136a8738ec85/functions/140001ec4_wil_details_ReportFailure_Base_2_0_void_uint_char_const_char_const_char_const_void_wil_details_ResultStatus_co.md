# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140001ec4`
- end: `0x140001f10`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020a4`
- `0x140002164`

## callees

- `0x140002804`

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
0x140001ec4  mov     r11, rsp
0x140001ec7  sub     rsp, 58h
0x140001ecb  mov     eax, [rsp+58h+arg_48]
0x140001ed2  mov     [rsp+58h+var_10], eax
0x140001ed6  mov     rax, [rsp+58h+arg_38]
0x140001ede  mov     [r11-20h], rax
0x140001ee2  mov     rax, [rsp+58h+arg_30]
0x140001eea  mov     [r11-28h], rax
0x140001eee  mov     rax, [rsp+58h+arg_28]
0x140001ef6  mov     [r11-30h], rax
0x140001efa  mov     rax, [rsp+58h+arg_20]
0x140001f02  mov     [r11-38h], rax
0x140001f06  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140001f0b  add     rsp, 58h
0x140001f0f  retn
```
