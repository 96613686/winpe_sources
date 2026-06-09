# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800091f4`
- end: `0x18000925f`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `107`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005560`
- `0x180005a4c`
- `0x180006324`

## callees

- `0x180005610`
- `0x180009178`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        int a1,
        __int64 a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(a1, v10, v9, v8, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x1800091f4  push    rbx
0x1800091f6  sub     rsp, 60h
0x1800091fa  mov     rbx, rcx
0x1800091fd  mov     r10, r8
0x180009200  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180009207  mov     r11d, edx
0x18000920a  mov     [rsp+68h+var_18], ecx
0x18000920e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009213  mov     [rsp+68h+var_14], eax
0x180009217  mov     r8, r10
0x18000921a  mov     [rsp+68h+var_20], 0
0x180009222  lea     rax, [rsp+68h+var_18]
0x180009227  mov     [rsp+68h+var_38], rax
0x18000922c  mov     edx, r11d
0x18000922f  mov     rax, [rsp+68h+arg_28]
0x180009237  mov     rcx, rbx
0x18000923a  mov     [rsp+68h+var_40], rax
0x18000923f  mov     rax, [rsp+68h+arg_20]
0x180009247  mov     [rsp+68h+var_48], rax
0x18000924c  mov     [rsp+68h+var_10], 0
0x180009254  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180009259  add     rsp, 60h
0x18000925d  pop     rbx
0x18000925e  retn
```
