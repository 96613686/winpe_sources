# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003690`
- end: `0x1400036dc`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039d4`
- `0x14000e060`
- `0x140010da8`
- `0x140011688`

## callees

- `0x140004404`

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
0x140003690  mov     r11, rsp
0x140003693  sub     rsp, 58h
0x140003697  mov     eax, [rsp+58h+arg_48]
0x14000369e  mov     [rsp+58h+var_10], eax
0x1400036a2  mov     rax, [rsp+58h+arg_38]
0x1400036aa  mov     [r11-20h], rax
0x1400036ae  mov     rax, [rsp+58h+arg_30]
0x1400036b6  mov     [r11-28h], rax
0x1400036ba  mov     rax, [rsp+58h+arg_28]
0x1400036c2  mov     [r11-30h], rax
0x1400036c6  mov     rax, [rsp+58h+arg_20]
0x1400036ce  mov     [r11-38h], rax
0x1400036d2  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400036d7  add     rsp, 58h
0x1400036db  retn
```
