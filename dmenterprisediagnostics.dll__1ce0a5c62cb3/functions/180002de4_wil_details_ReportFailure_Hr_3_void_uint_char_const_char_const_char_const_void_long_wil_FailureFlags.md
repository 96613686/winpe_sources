# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180002de4`
- end: `0x180002e40`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004300`

## callees

- `0x180002a60`
- `0x1800043a8`

## string_xrefs

- `0x180002e03`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  _BYTE v7[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v7, 2147549183LL, a3, a1);
  wil::details::ReportFailure_Base<3,0>(
    v6,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x180002de4  sub     rsp, 78h
0x180002de8  mov     r9, rcx
0x180002deb  mov     edx, 8000FFFFh
0x180002df0  lea     rcx, [rsp+78h+var_18]
0x180002df5  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002dfa  mov     [rsp+78h+var_40], 0
0x180002e03  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002e0a  mov     edx, 0E01h
0x180002e0f  mov     rcx, r9
0x180002e12  movsd   xmm0, qword ptr [rax]
0x180002e16  mov     eax, [rax+8]
0x180002e19  mov     [rsp+78h+var_20], eax
0x180002e1d  lea     rax, [rsp+78h+var_28]
0x180002e22  mov     [rsp+78h+var_48], rax
0x180002e27  mov     rax, [rsp+78h+arg_28]
0x180002e2f  mov     [rsp+78h+var_50], rax
0x180002e34  movsd   [rsp+78h+var_28], xmm0
0x180002e3a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
