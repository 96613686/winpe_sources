# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x18001cf4c`
- end: `0x18001cfbb`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d600`

## callees

- `0x18000775c`
- `0x180018f88`

## string_xrefs

- `0x18001cf74`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

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
  wil::details::ReportFailure_Base<1,0>(a1, 396, "onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp");
  return v9;
}

```

## disassembly

```asm
0x18001cf4c  mov     [rsp+arg_0], rbx
0x18001cf51  mov     [rsp+arg_8], rsi
0x18001cf56  push    rdi
0x18001cf57  sub     rsp, 60h
0x18001cf5b  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18001cf62  mov     rsi, rcx
0x18001cf65  mov     ecx, ebx; this
0x18001cf67  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001cf6c  mov     rdx, [rsp+68h+arg_28]
0x18001cf74  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cf7b  mov     edi, eax
0x18001cf7d  mov     [rsp+68h+var_18], eax
0x18001cf81  lea     rax, [rsp+68h+var_18]
0x18001cf86  mov     [rsp+68h+var_14], ebx
0x18001cf8a  mov     [rsp+68h+var_38], rax
0x18001cf8f  mov     rcx, rsi
0x18001cf92  mov     [rsp+68h+var_40], rdx
0x18001cf97  mov     edx, 18Ch
0x18001cf9c  mov     [rsp+68h+var_10], 1
0x18001cfa4  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001cfa9  mov     rbx, [rsp+68h+arg_0]
0x18001cfae  mov     eax, edi
0x18001cfb0  mov     rsi, [rsp+68h+arg_8]
0x18001cfb5  add     rsp, 60h
0x18001cfb9  pop     rdi
0x18001cfba  retn
```
