# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800022ac`
- end: `0x180002307`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021a4`
- `0x180003a40`
- `0x180003aa8`
- `0x1800040e8`

## callees

- `0x180002090`
- `0x180003f24`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x1800022ac  sub     rsp, 68h
0x1800022b0  mov     r10, rcx
0x1800022b3  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1800022ba  mov     [rsp+68h+var_18], ecx
0x1800022be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800022c3  mov     [rsp+68h+var_14], eax
0x1800022c7  mov     rcx, r10
0x1800022ca  xor     eax, eax
0x1800022cc  mov     [rsp+68h+var_20], eax
0x1800022d0  mov     [rsp+68h+var_30], rax
0x1800022d5  mov     [rsp+68h+var_10], eax
0x1800022d9  lea     rax, [rsp+68h+var_18]
0x1800022de  mov     [rsp+68h+var_38], rax
0x1800022e3  mov     rax, [rsp+68h+arg_28]
0x1800022eb  mov     [rsp+68h+var_40], rax
0x1800022f0  mov     rax, [rsp+68h+arg_20]
0x1800022f8  mov     [rsp+68h+var_48], rax
0x1800022fd  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180002302  add     rsp, 68h
0x180002306  retn
```
