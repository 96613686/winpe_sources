# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1400046c0`
- end: `0x14000472b`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c91c`

## callees

- `0x1400036b8`
- `0x1400046c0`
- `0x140009b94`

## string_xrefs

- `0x1400046f0`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    (int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v7;
}

```

## disassembly

```asm
0x1400046c0  push    rbx
0x1400046c2  sub     rsp, 60h
0x1400046c6  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1400046cd  mov     r9, rcx
0x1400046d0  test    ebx, ebx
0x1400046d2  jle     short loc_1400046DD
0x1400046d4  movzx   ebx, bx
0x1400046d7  or      ebx, 80070000h
0x1400046dd  mov     ecx, ebx; this
0x1400046df  mov     [rsp+68h+var_18], ebx
0x1400046e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400046e8  mov     rcx, [rsp+68h+arg_28]
0x1400046f0  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1400046f7  mov     [rsp+68h+var_14], eax
0x1400046fb  lea     rax, [rsp+68h+var_18]
0x140004700  mov     [rsp+68h+var_30], 0
0x140004709  mov     [rsp+68h+var_38], rax
0x14000470e  mov     [rsp+68h+var_40], rcx
0x140004713  mov     rcx, r9
0x140004716  mov     [rsp+68h+var_10], 0
0x14000471e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140004723  mov     eax, ebx
0x140004725  add     rsp, 60h
0x140004729  pop     rbx
0x14000472a  retn
```
