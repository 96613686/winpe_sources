# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x14000e060`
- end: `0x14000e0d4`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `116`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f0cc`

## callees

- `0x140003690`
- `0x140007908`
- `0x14000e060`

## string_xrefs

- `0x14000e0c0`: `onecoreuap\printscan\print\edu\printprov\registrystore.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  int v9; // edx
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v10,
    v9,
    (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\registrystore.cpp",
    0,
    v8,
    a6,
    (__int64)v12,
    v8);
  return v7;
}

```

## disassembly

```asm
0x14000e060  push    rbx
0x14000e062  sub     rsp, 60h
0x14000e066  mov     ebx, dword ptr [rsp+68h+arg_30]
0x14000e06d  xor     r8d, r8d
0x14000e070  mov     r10, rcx
0x14000e073  test    ebx, ebx
0x14000e075  jle     short loc_14000E080
0x14000e077  movzx   ebx, bx
0x14000e07a  or      ebx, 80070000h
0x14000e080  mov     ecx, ebx; this
0x14000e082  mov     [rsp+68h+var_18], ebx
0x14000e086  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000e08b  mov     rcx, [rsp+68h+arg_28]
0x14000e093  xor     r9d, r9d
0x14000e096  mov     [rsp+68h+var_20], r8d
0x14000e09b  mov     [rsp+68h+var_30], r8
0x14000e0a0  mov     [rsp+68h+var_14], eax
0x14000e0a4  lea     rax, [rsp+68h+var_18]
0x14000e0a9  mov     [rsp+68h+var_38], rax
0x14000e0ae  mov     [rsp+68h+var_40], rcx
0x14000e0b3  mov     rcx, r10
0x14000e0b6  mov     [rsp+68h+var_48], r8
0x14000e0bb  mov     [rsp+68h+var_10], r8d
0x14000e0c0  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000e0c7  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000e0cc  mov     eax, ebx
0x14000e0ce  add     rsp, 60h
0x14000e0d2  pop     rbx
0x14000e0d3  retn
```
