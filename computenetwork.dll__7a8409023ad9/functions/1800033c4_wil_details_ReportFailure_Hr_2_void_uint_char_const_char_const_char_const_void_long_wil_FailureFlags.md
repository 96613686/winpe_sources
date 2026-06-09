# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800033c4`
- end: `0x18000341f`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032bc`
- `0x180005100`
- `0x180005168`
- `0x1800060f0`
- `0x18000a384`

## callees

- `0x180003020`
- `0x180005f2c`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x1800033c4  sub     rsp, 68h
0x1800033c8  mov     r10, rcx
0x1800033cb  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1800033d2  mov     [rsp+68h+var_18], ecx
0x1800033d6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800033db  mov     [rsp+68h+var_14], eax
0x1800033df  mov     rcx, r10
0x1800033e2  xor     eax, eax
0x1800033e4  mov     [rsp+68h+var_20], eax
0x1800033e8  mov     [rsp+68h+var_30], rax
0x1800033ed  mov     [rsp+68h+var_10], eax
0x1800033f1  lea     rax, [rsp+68h+var_18]
0x1800033f6  mov     [rsp+68h+var_38], rax
0x1800033fb  mov     rax, [rsp+68h+arg_28]
0x180003403  mov     [rsp+68h+var_40], rax
0x180003408  mov     rax, [rsp+68h+arg_20]
0x180003410  mov     [rsp+68h+var_48], rax
0x180003415  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000341a  add     rsp, 68h
0x18000341e  retn
```
