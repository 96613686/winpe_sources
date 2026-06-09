# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180013728`
- end: `0x18001379e`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `118`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002225c`

## callees

- `0x180003d80`
- `0x180005d80`
- `0x180013728`

## string_xrefs

- `0x18001375a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

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
    263,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    0,
    v8,
    a6,
    (__int64)v11,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180013728  push    rbx
0x18001372a  sub     rsp, 60h
0x18001372e  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180013735  xor     edx, edx; int
0x180013737  mov     r10, rcx
0x18001373a  test    ebx, ebx
0x18001373c  jle     short loc_180013747
0x18001373e  movzx   ebx, bx
0x180013741  or      ebx, 80070000h
0x180013747  mov     ecx, ebx; this
0x180013749  mov     [rsp+68h+var_18], ebx
0x18001374d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013752  mov     rcx, [rsp+68h+arg_28]
0x18001375a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180013761  mov     [rsp+68h+var_20], edx
0x180013765  xor     r9d, r9d
0x180013768  mov     [rsp+68h+var_30], rdx
0x18001376d  mov     [rsp+68h+var_14], eax
0x180013771  lea     rax, [rsp+68h+var_18]
0x180013776  mov     [rsp+68h+var_38], rax
0x18001377b  mov     [rsp+68h+var_40], rcx
0x180013780  mov     rcx, r10
0x180013783  mov     [rsp+68h+var_48], rdx
0x180013788  mov     [rsp+68h+var_10], edx
0x18001378c  mov     edx, 107h
0x180013791  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180013796  mov     eax, ebx
0x180013798  add     rsp, 60h
0x18001379c  pop     rbx
0x18001379d  retn
```
