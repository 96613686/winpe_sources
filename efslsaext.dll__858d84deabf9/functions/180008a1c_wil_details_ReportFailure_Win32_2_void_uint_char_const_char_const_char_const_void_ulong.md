# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180008a1c`
- end: `0x180008a8d`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `113`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800090c8`

## callees

- `0x180003028`
- `0x180004c24`
- `0x180008a1c`

## string_xrefs

- `0x180008a4e`: `onecoreuap\ds\security\efs\lib\efsraw.cxx`

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
    1727,
    (unsigned int)"onecoreuap\\ds\\security\\efs\\lib\\efsraw.cxx",
    0,
    v8,
    a6,
    (__int64)v11);
  return v7;
}

```

## disassembly

```asm
0x180008a1c  push    rbx
0x180008a1e  sub     rsp, 60h
0x180008a22  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180008a29  xor     edx, edx; int
0x180008a2b  mov     r10, rcx
0x180008a2e  test    ebx, ebx
0x180008a30  jle     short loc_180008A3B
0x180008a32  movzx   ebx, bx
0x180008a35  or      ebx, 80070000h
0x180008a3b  mov     ecx, ebx; this
0x180008a3d  mov     [rsp+68h+var_18], ebx
0x180008a41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008a46  mov     rcx, [rsp+68h+arg_28]
0x180008a4e  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\efs\\lib\\efs"...
0x180008a55  mov     [rsp+68h+var_20], edx
0x180008a59  xor     r9d, r9d
0x180008a5c  mov     [rsp+68h+var_14], eax
0x180008a60  lea     rax, [rsp+68h+var_18]
0x180008a65  mov     [rsp+68h+var_38], rax
0x180008a6a  mov     [rsp+68h+var_40], rcx
0x180008a6f  mov     rcx, r10
0x180008a72  mov     [rsp+68h+var_48], rdx
0x180008a77  mov     [rsp+68h+var_10], edx
0x180008a7b  mov     edx, 6BFh
0x180008a80  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180008a85  mov     eax, ebx
0x180008a87  add     rsp, 60h
0x180008a8b  pop     rbx
0x180008a8c  retn
```
