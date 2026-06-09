# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18000fcd8`
- end: `0x18000fd42`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010470`

## callees

- `0x18000554c`
- `0x180010330`

## string_xrefs

- `0x18000fd1f`: `clientcore\ds\security\gina\profile\roaming\network.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v10; // [rsp+50h] [rbp-38h]

  v10 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(a1, a2, "clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp");
  return v10;
}

```

## disassembly

```asm
0x18000fcd8  push    rbx
0x18000fcda  push    rbp
0x18000fcdb  push    rsi
0x18000fcdc  push    rdi
0x18000fcdd  sub     rsp, 68h
0x18000fce1  mov     ebx, dword ptr [rsp+88h+arg_30]
0x18000fce8  mov     rbp, rcx
0x18000fceb  mov     ecx, ebx; this
0x18000fced  mov     esi, edx
0x18000fcef  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fcf4  mov     r8, [rsp+88h+arg_28]
0x18000fcfc  mov     edi, eax
0x18000fcfe  mov     [rsp+88h+var_38], eax
0x18000fd02  mov     edx, esi
0x18000fd04  lea     rax, [rsp+88h+var_38]
0x18000fd09  mov     [rsp+88h+var_50], 0
0x18000fd12  mov     [rsp+88h+var_58], rax
0x18000fd17  mov     rcx, rbp
0x18000fd1a  mov     [rsp+88h+var_60], r8
0x18000fd1f  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x18000fd26  mov     [rsp+88h+var_34], ebx
0x18000fd2a  mov     [rsp+88h+var_30], 1
0x18000fd32  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fd37  mov     eax, edi
0x18000fd39  add     rsp, 68h
0x18000fd3d  pop     rdi
0x18000fd3e  pop     rsi
0x18000fd3f  pop     rbp
0x18000fd40  pop     rbx
0x18000fd41  retn
```
