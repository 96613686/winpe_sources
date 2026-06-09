# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x14000e0dc`
- end: `0x14000e148`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f2e4`

## callees

- `0x140003710`
- `0x140006e38`
- `0x14000e0dc`

## string_xrefs

- `0x14000e10d`: `onecoreuap\printscan\print\edu\printprov\registrystore.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Win32<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  __int64 v7; // rdx
  int v8; // r9d
  int v9; // r10d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::ResultStatus::FromResult(v10, v7);
  wil::details::ReportFailure_Base<0,0>(
    v9,
    v8,
    (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\registrystore.cpp",
    v8);
}

```

## disassembly

```asm
0x14000e0dc  sub     rsp, 78h
0x14000e0e0  mov     r9d, edx
0x14000e0e3  mov     r10, rcx
0x14000e0e6  mov     edx, [rsp+78h+arg_30]
0x14000e0ed  test    edx, edx
0x14000e0ef  jle     short loc_14000E0FA
0x14000e0f1  movzx   edx, dx
0x14000e0f4  or      edx, 80070000h
0x14000e0fa  lea     rcx, [rsp+78h+var_18]
0x14000e0ff  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000e104  mov     [rsp+78h+var_40], 0
0x14000e10d  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000e114  mov     edx, r9d
0x14000e117  mov     rcx, r10
0x14000e11a  movsd   xmm0, qword ptr [rax]
0x14000e11e  mov     eax, [rax+8]
0x14000e121  mov     [rsp+78h+var_20], eax
0x14000e125  lea     rax, [rsp+78h+var_28]
0x14000e12a  mov     [rsp+78h+var_48], rax
0x14000e12f  mov     rax, [rsp+78h+arg_28]
0x14000e137  mov     [rsp+78h+var_50], rax
0x14000e13c  movsd   [rsp+78h+var_28], xmm0
0x14000e142  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
