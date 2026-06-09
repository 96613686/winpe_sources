# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800071d0`
- end: `0x18000722e`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `94`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800083d4`
- `0x1800096c4`
- `0x180009a84`

## callees

- `0x1800034f8`
- `0x180007048`

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
0x1800071d0  sub     rsp, 78h
0x1800071d4  mov     r11, rcx
0x1800071d7  mov     r10d, edx
0x1800071da  mov     edx, [rsp+78h+arg_30]
0x1800071e1  lea     rcx, [rsp+78h+var_18]
0x1800071e6  mov     r9, r8
0x1800071e9  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800071ee  mov     [rsp+78h+var_40], 0
0x1800071f7  mov     r8, r9
0x1800071fa  mov     edx, r10d
0x1800071fd  mov     rcx, r11
0x180007200  movsd   xmm0, qword ptr [rax]
0x180007204  mov     eax, [rax+8]
0x180007207  mov     [rsp+78h+var_20], eax
0x18000720b  lea     rax, [rsp+78h+var_28]
0x180007210  mov     [rsp+78h+var_48], rax
0x180007215  mov     rax, [rsp+78h+arg_28]
0x18000721d  mov     [rsp+78h+var_50], rax
0x180007222  movsd   [rsp+78h+var_28], xmm0
0x180007228  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
