# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180002310`
- end: `0x18000236d`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003460`
- `0x1800083b8`

## callees

- `0x1800020e4`
- `0x1800034f8`

## string_xrefs

- `0x180002332`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // xmm0_8
  int v8; // r9d
  int v9; // r10d
  int v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+50h] [rbp-28h] BYREF
  int v12; // [rsp+58h] [rbp-20h]
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v13, 2147549183LL);
  v7 = *(_QWORD *)v6;
  v12 = *(_DWORD *)(v6 + 8);
  v11 = v7;
  wil::details::ReportFailure_Base<3,0>(
    v9,
    v8,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v8,
    v10,
    a6,
    (__int64)&v11,
    0);
}

```

## disassembly

```asm
0x180002310  sub     rsp, 78h
0x180002314  mov     r10, rcx
0x180002317  mov     r9d, edx
0x18000231a  mov     edx, 8000FFFFh
0x18000231f  lea     rcx, [rsp+78h+var_18]
0x180002324  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002329  mov     [rsp+78h+var_40], 0
0x180002332  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002339  mov     edx, r9d
0x18000233c  mov     rcx, r10
0x18000233f  movsd   xmm0, qword ptr [rax]
0x180002343  mov     eax, [rax+8]
0x180002346  mov     [rsp+78h+var_20], eax
0x18000234a  lea     rax, [rsp+78h+var_28]
0x18000234f  mov     [rsp+78h+var_48], rax
0x180002354  mov     rax, [rsp+78h+arg_28]
0x18000235c  mov     [rsp+78h+var_50], rax
0x180002361  movsd   [rsp+78h+var_28], xmm0
0x180002367  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
