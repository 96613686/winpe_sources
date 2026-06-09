# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180006108`
- end: `0x180006173`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `107`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002780`
- `0x1800032b4`
- `0x180004150`
- `0x180004208`

## callees

- `0x180002b90`
- `0x18000601c`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(a1, v10, v9, v8, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x180006108  push    rbx
0x18000610a  sub     rsp, 60h
0x18000610e  mov     rbx, rcx
0x180006111  mov     r10, r8
0x180006114  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x18000611b  mov     r11d, edx
0x18000611e  mov     [rsp+68h+var_18], ecx
0x180006122  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006127  mov     [rsp+68h+var_14], eax
0x18000612b  mov     r8, r10
0x18000612e  mov     [rsp+68h+var_20], 0
0x180006136  lea     rax, [rsp+68h+var_18]
0x18000613b  mov     [rsp+68h+var_38], rax
0x180006140  mov     edx, r11d
0x180006143  mov     rax, [rsp+68h+arg_28]
0x18000614b  mov     rcx, rbx
0x18000614e  mov     [rsp+68h+var_40], rax
0x180006153  mov     rax, [rsp+68h+arg_20]
0x18000615b  mov     [rsp+68h+var_48], rax
0x180006160  mov     [rsp+68h+var_10], 0
0x180006168  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000616d  add     rsp, 60h
0x180006171  pop     rbx
0x180006172  retn
```
