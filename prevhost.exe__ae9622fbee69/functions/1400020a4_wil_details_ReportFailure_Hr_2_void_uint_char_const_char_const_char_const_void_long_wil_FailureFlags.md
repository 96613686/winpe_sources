# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1400020a4`
- end: `0x140002100`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001fb4`
- `0x140003960`
- `0x1400039c8`
- `0x1400040dc`

## callees

- `0x140001ec0`
- `0x140003e3c`

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
0x1400020a4  sub     rsp, 68h
0x1400020a8  mov     r10, rcx
0x1400020ab  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1400020b2  mov     [rsp+68h+var_18], ecx
0x1400020b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400020bb  mov     [rsp+68h+var_14], eax
0x1400020bf  mov     rcx, r10
0x1400020c2  mov     [rsp+68h+var_20], 0
0x1400020ca  lea     rax, [rsp+68h+var_18]
0x1400020cf  mov     [rsp+68h+var_38], rax
0x1400020d4  mov     rax, [rsp+68h+arg_28]
0x1400020dc  mov     [rsp+68h+var_40], rax
0x1400020e1  mov     rax, [rsp+68h+arg_20]
0x1400020e9  mov     [rsp+68h+var_48], rax
0x1400020ee  mov     [rsp+68h+var_10], 0
0x1400020f6  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400020fb  add     rsp, 68h
0x1400020ff  retn
```
