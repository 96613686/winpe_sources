# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003070`
- end: `0x1800030c5`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d50`
- `0x180007f00`
- `0x1800084c8`

## callees

- `0x180002e9c`
- `0x180003e08`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
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

  wil::details::ResultStatus::FromResult(v10, a7, a3, a3);
  wil::details::ReportFailure_Base<3,0>(v9, v8, v7, v7);
}

```

## disassembly

```asm
0x180003070  sub     rsp, 78h
0x180003074  mov     r11, rcx
0x180003077  mov     r10d, edx
0x18000307a  mov     edx, [rsp+78h+arg_30]
0x180003081  lea     rcx, [rsp+78h+var_18]
0x180003086  mov     r9, r8
0x180003089  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000308e  mov     r8, r9
0x180003091  mov     edx, r10d
0x180003094  mov     rcx, r11
0x180003097  movsd   xmm0, qword ptr [rax]
0x18000309b  mov     eax, [rax+8]
0x18000309e  mov     [rsp+78h+var_20], eax
0x1800030a2  lea     rax, [rsp+78h+var_28]
0x1800030a7  mov     [rsp+78h+var_48], rax
0x1800030ac  mov     rax, [rsp+78h+arg_28]
0x1800030b4  mov     [rsp+78h+var_50], rax
0x1800030b9  movsd   [rsp+78h+var_28], xmm0
0x1800030bf  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
