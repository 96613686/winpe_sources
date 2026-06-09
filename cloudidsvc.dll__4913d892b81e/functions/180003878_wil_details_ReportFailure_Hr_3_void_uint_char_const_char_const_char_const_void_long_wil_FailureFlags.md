# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003878`
- end: `0x1800038d5`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005244`
- `0x18000fd34`

## callees

- `0x18000335c`
- `0x1800052f8`

## string_xrefs

- `0x18000389a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  int v7; // r10d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, 2147549183LL, a3, a2);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x180003878  sub     rsp, 78h
0x18000387c  mov     r10, rcx
0x18000387f  mov     r9d, edx
0x180003882  mov     edx, 8000FFFFh
0x180003887  lea     rcx, [rsp+78h+var_18]
0x18000388c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180003891  mov     [rsp+78h+var_40], 0
0x18000389a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800038a1  mov     edx, r9d
0x1800038a4  mov     rcx, r10
0x1800038a7  movsd   xmm0, qword ptr [rax]
0x1800038ab  mov     eax, [rax+8]
0x1800038ae  mov     [rsp+78h+var_20], eax
0x1800038b2  lea     rax, [rsp+78h+var_28]
0x1800038b7  mov     [rsp+78h+var_48], rax
0x1800038bc  mov     rax, [rsp+78h+arg_28]
0x1800038c4  mov     [rsp+78h+var_50], rax
0x1800038c9  movsd   [rsp+78h+var_28], xmm0
0x1800038cf  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
