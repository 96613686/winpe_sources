# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140002fd0`
- end: `0x14000302d`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ed4`
- `0x1400058d0`
- `0x140005940`
- `0x140006158`

## callees

- `0x140002dd8`
- `0x140005e1c`

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
0x140002fd0  sub     rsp, 68h
0x140002fd4  mov     r10, rcx
0x140002fd7  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x140002fde  mov     [rsp+68h+var_18], ecx
0x140002fe2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002fe7  mov     [rsp+68h+var_14], eax
0x140002feb  mov     rcx, r10
0x140002fee  mov     [rsp+68h+var_20], 0
0x140002ff6  lea     rax, [rsp+68h+var_18]
0x140002ffb  mov     [rsp+68h+var_38], rax
0x140003000  mov     rax, [rsp+68h+arg_28]
0x140003008  mov     [rsp+68h+var_40], rax
0x14000300d  mov     rax, [rsp+68h+arg_20]
0x140003015  mov     [rsp+68h+var_48], rax
0x14000301a  mov     [rsp+68h+var_10], 0
0x140003022  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140003027  add     rsp, 68h
0x14000302b  retn
```
