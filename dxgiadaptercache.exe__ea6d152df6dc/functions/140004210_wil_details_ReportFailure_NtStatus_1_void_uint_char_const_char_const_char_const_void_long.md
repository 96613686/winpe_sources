# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x140004210`
- end: `0x140004288`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `120`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c8f8`

## callees

- `0x1400036b8`
- `0x14000a7b4`

## string_xrefs

- `0x140004238`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v8 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v12[0] = v8;
  v12[1] = (_DWORD)a7;
  v12[2] = 1;
  wil::details::ReportFailure_Base<1,0>(
    a1,
    512,
    (int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
    v9,
    v11,
    a6,
    (int)v12,
    0);
  return v8;
}

```

## disassembly

```asm
0x140004210  mov     [rsp+arg_0], rbx
0x140004215  mov     [rsp+arg_8], rsi
0x14000421a  push    rdi
0x14000421b  sub     rsp, 60h
0x14000421f  mov     ebx, dword ptr [rsp+68h+arg_30]
0x140004226  mov     rsi, rcx
0x140004229  mov     ecx, ebx; this
0x14000422b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140004230  mov     rdx, [rsp+68h+arg_28]
0x140004238  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000423f  mov     edi, eax
0x140004241  mov     [rsp+68h+var_18], eax
0x140004245  lea     rax, [rsp+68h+var_18]
0x14000424a  mov     [rsp+68h+var_30], 0
0x140004253  mov     [rsp+68h+var_38], rax
0x140004258  mov     rcx, rsi
0x14000425b  mov     [rsp+68h+var_40], rdx
0x140004260  mov     edx, 200h
0x140004265  mov     [rsp+68h+var_14], ebx
0x140004269  mov     [rsp+68h+var_10], 1
0x140004271  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140004276  mov     rbx, [rsp+68h+arg_0]
0x14000427b  mov     eax, edi
0x14000427d  mov     rsi, [rsp+68h+arg_8]
0x140004282  add     rsp, 60h
0x140004286  pop     rdi
0x140004287  retn
```
