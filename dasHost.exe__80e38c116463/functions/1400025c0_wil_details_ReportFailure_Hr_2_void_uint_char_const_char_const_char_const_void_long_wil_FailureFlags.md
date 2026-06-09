# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1400025c0`
- end: `0x14000261f`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400024b8`
- `0x140002bb8`
- `0x140004ed0`
- `0x140004f38`
- `0x14001450c`

## callees

- `0x1400023a4`
- `0x1400053bc`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        int a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0, 0, 0);
}

```

## disassembly

```asm
0x1400025c0  sub     rsp, 68h
0x1400025c4  mov     r10, rcx
0x1400025c7  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1400025ce  mov     [rsp+68h+var_18], ecx
0x1400025d2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400025d7  mov     [rsp+68h+var_14], eax
0x1400025db  mov     rcx, r10
0x1400025de  xor     eax, eax
0x1400025e0  mov     [rsp+68h+var_20], eax
0x1400025e4  mov     [rsp+68h+var_28], eax
0x1400025e8  mov     [rsp+68h+var_30], rax
0x1400025ed  mov     [rsp+68h+var_10], eax
0x1400025f1  lea     rax, [rsp+68h+var_18]
0x1400025f6  mov     [rsp+68h+var_38], rax
0x1400025fb  mov     rax, [rsp+68h+arg_28]
0x140002603  mov     [rsp+68h+var_40], rax
0x140002608  mov     rax, [rsp+68h+arg_20]
0x140002610  mov     [rsp+68h+var_48], rax
0x140002615  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000261a  add     rsp, 68h
0x14000261e  retn
```
