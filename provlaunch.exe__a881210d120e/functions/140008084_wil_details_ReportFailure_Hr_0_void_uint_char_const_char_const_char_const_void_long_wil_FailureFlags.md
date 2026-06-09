# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140008084`
- end: `0x1400080d9`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009490`

## callees

- `0x14000240c`
- `0x140004128`

## string_xrefs

- `0x14000809c`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

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
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, a7);
  wil::details::ReportFailure_Base<0,0>(
    v7,
    67,
    (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
    v7);
}

```

## disassembly

```asm
0x140008084  sub     rsp, 78h
0x140008088  mov     edx, [rsp+78h+arg_30]
0x14000808f  mov     r9, rcx
0x140008092  lea     rcx, [rsp+78h+var_18]
0x140008097  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000809c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1400080a3  mov     edx, 43h ; 'C'
0x1400080a8  mov     rcx, r9
0x1400080ab  movsd   xmm0, qword ptr [rax]
0x1400080af  mov     eax, [rax+8]
0x1400080b2  mov     [rsp+78h+var_20], eax
0x1400080b6  lea     rax, [rsp+78h+var_28]
0x1400080bb  mov     [rsp+78h+var_48], rax
0x1400080c0  mov     rax, [rsp+78h+arg_28]
0x1400080c8  mov     [rsp+78h+var_50], rax
0x1400080cd  movsd   [rsp+78h+var_28], xmm0
0x1400080d3  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
