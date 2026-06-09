# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800182cc`
- end: `0x18001831f`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `83`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a3d8`

## callees

- `0x180005b28`
- `0x18001809c`

## string_xrefs

- `0x1800182e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  _BYTE v7[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v7, 2147942414LL, a3, a1);
  wil::details::ReportFailure_Base<0,0>(
    v6,
    4088,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x1800182cc  sub     rsp, 78h
0x1800182d0  mov     r9, rcx
0x1800182d3  mov     edx, 8007000Eh
0x1800182d8  lea     rcx, [rsp+78h+var_18]
0x1800182dd  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800182e2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800182e9  mov     edx, 0FF8h
0x1800182ee  mov     rcx, r9
0x1800182f1  movsd   xmm0, qword ptr [rax]
0x1800182f5  mov     eax, [rax+8]
0x1800182f8  mov     [rsp+78h+var_20], eax
0x1800182fc  lea     rax, [rsp+78h+var_28]
0x180018301  mov     [rsp+78h+var_48], rax
0x180018306  mov     rax, [rsp+78h+arg_28]
0x18001830e  mov     [rsp+78h+var_50], rax
0x180018313  movsd   [rsp+78h+var_28], xmm0
0x180018319  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
