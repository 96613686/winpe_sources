# wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000fd48`
- end: `0x18000fdbc`
- name: `??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `116`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010744`

## callees

- `0x18000bcc4`
- `0x180010330`

## string_xrefs

- `0x18000fd6c`: `clientcore\ds\security\gina\profile\roaming\network.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // edi
  _DWORD v11[14]; // [rsp+50h] [rbp-38h] BYREF

  v11[0] = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v9 = v11[0];
  v11[1] = (_DWORD)a7;
  v11[2] = 1;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
    0,
    0,
    a6,
    (__int64)v11,
    0);
  return v9;
}

```

## disassembly

```asm
0x18000fd48  push    rbx
0x18000fd4a  push    rbp
0x18000fd4b  push    rsi
0x18000fd4c  push    rdi
0x18000fd4d  sub     rsp, 68h
0x18000fd51  mov     ebx, dword ptr [rsp+88h+arg_30]
0x18000fd58  mov     rbp, rcx
0x18000fd5b  mov     ecx, ebx; this
0x18000fd5d  mov     esi, edx
0x18000fd5f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fd64  mov     rdx, [rsp+88h+arg_28]
0x18000fd6c  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x18000fd73  xor     ecx, ecx
0x18000fd75  mov     [rsp+88h+var_38], eax
0x18000fd79  mov     [rsp+88h+var_40], ecx
0x18000fd7d  mov     edi, eax
0x18000fd7f  mov     [rsp+88h+var_50], rcx
0x18000fd84  lea     rax, [rsp+88h+var_38]
0x18000fd89  mov     [rsp+88h+var_58], rax
0x18000fd8e  xor     r9d, r9d
0x18000fd91  mov     [rsp+88h+var_60], rdx
0x18000fd96  mov     edx, esi
0x18000fd98  mov     [rsp+88h+var_68], rcx
0x18000fd9d  mov     rcx, rbp
0x18000fda0  mov     [rsp+88h+var_34], ebx
0x18000fda4  mov     [rsp+88h+var_30], 1
0x18000fdac  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fdb1  mov     eax, edi
0x18000fdb3  add     rsp, 68h
0x18000fdb7  pop     rdi
0x18000fdb8  pop     rsi
0x18000fdb9  pop     rbp
0x18000fdba  pop     rbx
0x18000fdbb  retn
```
