# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18000b92c`
- end: `0x18000b988`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b83c`
- `0x18000d4b0`
- `0x18000d518`
- `0x18000e034`

## callees

- `0x18000b748`
- `0x18000ddd0`

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
0x18000b92c  sub     rsp, 68h
0x18000b930  mov     r10, rcx
0x18000b933  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x18000b93a  mov     [rsp+68h+var_18], ecx
0x18000b93e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b943  mov     [rsp+68h+var_14], eax
0x18000b947  mov     rcx, r10
0x18000b94a  mov     [rsp+68h+var_20], 0
0x18000b952  lea     rax, [rsp+68h+var_18]
0x18000b957  mov     [rsp+68h+var_38], rax
0x18000b95c  mov     rax, [rsp+68h+arg_28]
0x18000b964  mov     [rsp+68h+var_40], rax
0x18000b969  mov     rax, [rsp+68h+arg_20]
0x18000b971  mov     [rsp+68h+var_48], rax
0x18000b976  mov     [rsp+68h+var_10], 0
0x18000b97e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b983  add     rsp, 68h
0x18000b987  retn
```
