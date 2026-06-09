# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800039a0`
- end: `0x1800039fc`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003898`
- `0x180006680`
- `0x1800066e8`
- `0x180006e10`

## callees

- `0x180003788`
- `0x180006b64`

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
0x1800039a0  sub     rsp, 68h
0x1800039a4  mov     r10, rcx
0x1800039a7  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1800039ae  mov     [rsp+68h+var_18], ecx
0x1800039b2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800039b7  mov     [rsp+68h+var_14], eax
0x1800039bb  mov     rcx, r10
0x1800039be  mov     [rsp+68h+var_20], 0
0x1800039c6  lea     rax, [rsp+68h+var_18]
0x1800039cb  mov     [rsp+68h+var_38], rax
0x1800039d0  mov     rax, [rsp+68h+arg_28]
0x1800039d8  mov     [rsp+68h+var_40], rax
0x1800039dd  mov     rax, [rsp+68h+arg_20]
0x1800039e5  mov     [rsp+68h+var_48], rax
0x1800039ea  mov     [rsp+68h+var_10], 0
0x1800039f2  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800039f7  add     rsp, 68h
0x1800039fb  retn
```
