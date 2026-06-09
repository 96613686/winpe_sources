# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1400027fc`
- end: `0x140002851`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400032b4`
- `0x1400057cc`

## callees

- `0x14000262c`
- `0x140003368`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x1400027fc  sub     rsp, 78h
0x140002800  mov     r11, rcx
0x140002803  mov     r10d, edx
0x140002806  mov     edx, [rsp+78h+arg_30]
0x14000280d  lea     rcx, [rsp+78h+var_18]
0x140002812  mov     r9, r8
0x140002815  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000281a  mov     r8, r9
0x14000281d  mov     edx, r10d
0x140002820  mov     rcx, r11
0x140002823  movsd   xmm0, qword ptr [rax]
0x140002827  mov     eax, [rax+8]
0x14000282a  mov     [rsp+78h+var_20], eax
0x14000282e  lea     rax, [rsp+78h+var_28]
0x140002833  mov     [rsp+78h+var_48], rax
0x140002838  mov     rax, [rsp+78h+arg_28]
0x140002840  mov     [rsp+78h+var_50], rax
0x140002845  movsd   [rsp+78h+var_28], xmm0
0x14000284b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
