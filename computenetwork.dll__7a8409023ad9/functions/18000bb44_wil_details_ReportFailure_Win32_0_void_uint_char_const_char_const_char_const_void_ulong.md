# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000bb44`
- end: `0x18000bbb0`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c0bc`

## callees

- `0x1800030ac`
- `0x180004bb8`
- `0x18000bb44`

## string_xrefs

- `0x18000bb75`: `onecore\vm\dv\net\hns\service\common\rpc\client\rpcclient.cpp`

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
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\rpc\\client\\rpcclient.cpp",
    v8);
}

```

## disassembly

```asm
0x18000bb44  sub     rsp, 78h
0x18000bb48  mov     r9d, edx
0x18000bb4b  mov     r10, rcx
0x18000bb4e  mov     edx, [rsp+78h+arg_30]
0x18000bb55  test    edx, edx
0x18000bb57  jle     short loc_18000BB62
0x18000bb59  movzx   edx, dx
0x18000bb5c  or      edx, 80070000h
0x18000bb62  lea     rcx, [rsp+78h+var_18]
0x18000bb67  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000bb6c  mov     [rsp+78h+var_40], 0
0x18000bb75  lea     r8, aOnecoreVmDvNet_2; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18000bb7c  mov     edx, r9d
0x18000bb7f  mov     rcx, r10
0x18000bb82  movsd   xmm0, qword ptr [rax]
0x18000bb86  mov     eax, [rax+8]
0x18000bb89  mov     [rsp+78h+var_20], eax
0x18000bb8d  lea     rax, [rsp+78h+var_28]
0x18000bb92  mov     [rsp+78h+var_48], rax
0x18000bb97  mov     rax, [rsp+78h+arg_28]
0x18000bb9f  mov     [rsp+78h+var_50], rax
0x18000bba4  movsd   [rsp+78h+var_28], xmm0
0x18000bbaa  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
