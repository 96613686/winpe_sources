# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x14000a448`
- end: `0x14000a4c1`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `121`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000c6e4`

## callees

- `0x140002e54`
- `0x14000c334`

## string_xrefs

- `0x14000a470`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // [rsp+50h] [rbp-18h]

  v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(a1, 82, "onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h");
  return v9;
}

```

## disassembly

```asm
0x14000a448  mov     [rsp+arg_0], rbx
0x14000a44d  mov     [rsp+arg_8], rsi
0x14000a452  push    rdi
0x14000a453  sub     rsp, 60h
0x14000a457  mov     ebx, dword ptr [rsp+68h+arg_30]
0x14000a45e  mov     rsi, rcx
0x14000a461  mov     ecx, ebx; this
0x14000a463  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000a468  mov     rdx, [rsp+68h+arg_28]
0x14000a470  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000a477  mov     edi, eax
0x14000a479  mov     [rsp+68h+var_18], eax
0x14000a47d  lea     rax, [rsp+68h+var_18]
0x14000a482  mov     [rsp+68h+var_30], 0
0x14000a48b  mov     [rsp+68h+var_38], rax
0x14000a490  mov     rcx, rsi
0x14000a493  mov     [rsp+68h+var_40], rdx
0x14000a498  mov     edx, 52h ; 'R'
0x14000a49d  mov     [rsp+68h+var_14], ebx
0x14000a4a1  mov     [rsp+68h+var_10], 1
0x14000a4a9  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000a4ae  mov     rbx, [rsp+68h+arg_0]
0x14000a4b3  mov     eax, edi
0x14000a4b5  mov     rsi, [rsp+68h+arg_8]
0x14000a4ba  add     rsp, 60h
0x14000a4be  pop     rdi
0x14000a4bf  retn
```
