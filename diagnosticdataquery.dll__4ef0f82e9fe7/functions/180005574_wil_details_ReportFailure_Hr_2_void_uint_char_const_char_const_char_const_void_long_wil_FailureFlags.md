# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180005574`
- end: `0x1800055d0`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000547c`
- `0x180006cc0`
- `0x180006d28`
- `0x180007368`

## callees

- `0x180005388`
- `0x1800071a4`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x180005574  sub     rsp, 68h
0x180005578  mov     r10, rcx
0x18000557b  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180005582  mov     [rsp+68h+var_18], ecx
0x180005586  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000558b  mov     [rsp+68h+var_14], eax
0x18000558f  mov     rcx, r10
0x180005592  mov     [rsp+68h+var_20], 0
0x18000559a  lea     rax, [rsp+68h+var_18]
0x18000559f  mov     [rsp+68h+var_38], rax
0x1800055a4  mov     rax, [rsp+68h+arg_28]
0x1800055ac  mov     [rsp+68h+var_40], rax
0x1800055b1  mov     rax, [rsp+68h+arg_20]
0x1800055b9  mov     [rsp+68h+var_48], rax
0x1800055be  mov     [rsp+68h+var_10], 0
0x1800055c6  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800055cb  add     rsp, 68h
0x1800055cf  retn
```
