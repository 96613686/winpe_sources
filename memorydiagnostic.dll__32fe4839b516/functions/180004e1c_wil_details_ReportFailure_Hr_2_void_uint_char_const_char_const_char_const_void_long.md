# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180004e1c`
- end: `0x180004e7a`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z`
- size: `94`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b14`
- `0x180004cf8`
- `0x180005870`
- `0x18000d73c`
- `0x18000d7a8`
- `0x18000eb14`
- `0x18001634c`
- `0x18001fa5c`

## callees

- `0x1800047d0`
- `0x18000dd50`

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
  int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[2] = 0;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  return wil::details::ReportFailure_Base<2,0>(v10, v9, v7, v8, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x180004e1c  sub     rsp, 68h
0x180004e20  mov     r11, rcx
0x180004e23  mov     r10d, edx
0x180004e26  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180004e2d  mov     [rsp+68h+var_18], ecx
0x180004e31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004e36  and     [rsp+68h+var_30], 0
0x180004e3c  mov     edx, r10d
0x180004e3f  and     [rsp+68h+var_10], 0
0x180004e44  mov     rcx, r11
0x180004e47  mov     [rsp+68h+var_14], eax
0x180004e4b  lea     rax, [rsp+68h+var_18]
0x180004e50  mov     [rsp+68h+var_38], rax
0x180004e55  mov     rax, [rsp+68h+arg_28]
0x180004e5d  mov     [rsp+68h+var_40], rax
0x180004e62  mov     rax, [rsp+68h+arg_20]
0x180004e6a  mov     [rsp+68h+var_48], rax
0x180004e6f  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
0x180004e74  add     rsp, 68h
0x180004e78  retn
```
