# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180006450`
- end: `0x1800064a5`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007670`
- `0x180007800`
- `0x180007820`

## callees

- `0x1800038a8`
- `0x1800062e0`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  int v9; // r11d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v10, a7);
  wil::details::ReportFailure_Base<0,0>(v9, v8, v7, v7);
}

```

## disassembly

```asm
0x180006450  sub     rsp, 78h
0x180006454  mov     r11, rcx
0x180006457  mov     r10d, edx
0x18000645a  mov     edx, [rsp+78h+arg_30]
0x180006461  lea     rcx, [rsp+78h+var_18]
0x180006466  mov     r9, r8
0x180006469  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000646e  mov     r8, r9
0x180006471  mov     edx, r10d
0x180006474  mov     rcx, r11
0x180006477  movsd   xmm0, qword ptr [rax]
0x18000647b  mov     eax, [rax+8]
0x18000647e  mov     [rsp+78h+var_20], eax
0x180006482  lea     rax, [rsp+78h+var_28]
0x180006487  mov     [rsp+78h+var_48], rax
0x18000648c  mov     rax, [rsp+78h+arg_28]
0x180006494  mov     [rsp+78h+var_50], rax
0x180006499  movsd   [rsp+78h+var_28], xmm0
0x18000649f  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
