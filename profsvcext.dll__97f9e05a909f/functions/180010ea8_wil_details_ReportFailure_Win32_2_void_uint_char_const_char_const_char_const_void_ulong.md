# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180010ea8`
- end: `0x180010f14`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016ed8`

## callees

- `0x180004e68`
- `0x18000bcc4`

## string_xrefs

- `0x180010efe`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(__int64 a1, int a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  int v6; // r10d
  _DWORD v8[6]; // [rsp+50h] [rbp-18h] BYREF

  v8[0] = -2147024770;
  v8[1] = wil::details::HrToNtStatus((wil::details *)0x8007007ELL, a2);
  v8[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    2125,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    0,
    0,
    a6,
    (__int64)v8,
    0);
  return 2147942526LL;
}

```

## disassembly

```asm
0x180010ea8  sub     rsp, 68h
0x180010eac  mov     r10, rcx
0x180010eaf  mov     [rsp+68h+var_18], 8007007Eh
0x180010eb7  mov     ecx, 8007007Eh; this
0x180010ebc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010ec1  mov     rdx, [rsp+68h+arg_28]
0x180010ec9  lea     rcx, [rsp+68h+var_18]
0x180010ece  xor     r8d, r8d
0x180010ed1  mov     [rsp+68h+var_14], eax
0x180010ed5  mov     [rsp+68h+var_20], r8d
0x180010eda  xor     r9d, r9d
0x180010edd  mov     [rsp+68h+var_30], r8
0x180010ee2  mov     [rsp+68h+var_38], rcx
0x180010ee7  mov     rcx, r10
0x180010eea  mov     [rsp+68h+var_40], rdx
0x180010eef  mov     edx, 84Dh
0x180010ef4  mov     [rsp+68h+var_48], r8
0x180010ef9  mov     [rsp+68h+var_10], r8d
0x180010efe  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180010f05  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180010f0a  mov     eax, 8007007Eh
0x180010f0f  add     rsp, 68h
0x180010f13  retn
```
