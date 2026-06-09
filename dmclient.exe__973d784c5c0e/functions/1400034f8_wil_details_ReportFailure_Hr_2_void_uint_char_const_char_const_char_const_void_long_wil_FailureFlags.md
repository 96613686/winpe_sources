# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1400034f8`
- end: `0x140003555`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033f8`
- `0x140007050`
- `0x1400070c0`
- `0x140007c9c`

## callees

- `0x1400032d0`
- `0x14000764c`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x1400034f8  sub     rsp, 68h
0x1400034fc  mov     r10, rcx
0x1400034ff  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x140003506  mov     [rsp+68h+var_18], ecx
0x14000350a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000350f  mov     [rsp+68h+var_14], eax
0x140003513  mov     rcx, r10
0x140003516  mov     [rsp+68h+var_20], 0
0x14000351e  lea     rax, [rsp+68h+var_18]
0x140003523  mov     [rsp+68h+var_38], rax
0x140003528  mov     rax, [rsp+68h+arg_28]
0x140003530  mov     [rsp+68h+var_40], rax
0x140003535  mov     rax, [rsp+68h+arg_20]
0x14000353d  mov     [rsp+68h+var_48], rax
0x140003542  mov     [rsp+68h+var_10], 0
0x14000354a  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000354f  add     rsp, 68h
0x140003553  retn
```
