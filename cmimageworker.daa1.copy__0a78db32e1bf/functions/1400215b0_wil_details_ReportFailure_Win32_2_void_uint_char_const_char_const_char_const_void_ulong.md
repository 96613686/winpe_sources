# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1400215b0`
- end: `0x140021621`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `113`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140022e68`

## callees

- `0x140002e60`
- `0x1400052b8`
- `0x1400215b0`

## string_xrefs

- `0x1400215e2`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r10d
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, 0);
  v11[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v9,
    67,
    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
    0,
    v8,
    a6,
    (__int64)v11);
  return v7;
}

```

## disassembly

```asm
0x1400215b0  push    rbx
0x1400215b2  sub     rsp, 60h
0x1400215b6  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1400215bd  xor     edx, edx; int
0x1400215bf  mov     r10, rcx
0x1400215c2  test    ebx, ebx
0x1400215c4  jle     short loc_1400215CF
0x1400215c6  movzx   ebx, bx
0x1400215c9  or      ebx, 80070000h
0x1400215cf  mov     ecx, ebx; this
0x1400215d1  mov     [rsp+68h+var_18], ebx
0x1400215d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400215da  mov     rcx, [rsp+68h+arg_28]
0x1400215e2  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1400215e9  mov     [rsp+68h+var_20], edx
0x1400215ed  xor     r9d, r9d
0x1400215f0  mov     [rsp+68h+var_14], eax
0x1400215f4  lea     rax, [rsp+68h+var_18]
0x1400215f9  mov     [rsp+68h+var_38], rax
0x1400215fe  mov     [rsp+68h+var_40], rcx
0x140021603  mov     rcx, r10
0x140021606  mov     [rsp+68h+var_48], rdx
0x14002160b  mov     [rsp+68h+var_10], edx
0x14002160f  lea     edx, [r9+43h]
0x140021613  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140021618  mov     eax, ebx
0x14002161a  add     rsp, 60h
0x14002161e  pop     rbx
0x14002161f  retn
```
