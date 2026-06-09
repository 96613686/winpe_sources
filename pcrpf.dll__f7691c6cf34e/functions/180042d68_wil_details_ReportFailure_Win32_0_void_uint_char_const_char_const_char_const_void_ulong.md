# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180042d68`
- end: `0x180042dd3`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `107`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004dd98`

## callees

- `0x180006b34`
- `0x18002a218`
- `0x180042d68`

## string_xrefs

- `0x180042d96`: `onecore\base\ngscb\pcrpf\txfjson\ppftxfjson.cpp`

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
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::ResultStatus::FromResult(v9, v7);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    224,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
    v8);
}

```

## disassembly

```asm
0x180042d68  sub     rsp, 78h
0x180042d6c  mov     edx, [rsp+78h+arg_30]
0x180042d73  mov     r9, rcx
0x180042d76  test    edx, edx
0x180042d78  jle     short loc_180042D83
0x180042d7a  movzx   edx, dx
0x180042d7d  or      edx, 80070000h
0x180042d83  lea     rcx, [rsp+78h+var_18]
0x180042d88  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180042d8d  mov     [rsp+78h+var_40], 0
0x180042d96  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\pcrpf\\txfjson\\p"...
0x180042d9d  mov     edx, 0E0h
0x180042da2  mov     rcx, r9
0x180042da5  movsd   xmm0, qword ptr [rax]
0x180042da9  mov     eax, [rax+8]
0x180042dac  mov     [rsp+78h+var_20], eax
0x180042db0  lea     rax, [rsp+78h+var_28]
0x180042db5  mov     [rsp+78h+var_48], rax
0x180042dba  mov     rax, [rsp+78h+arg_28]
0x180042dc2  mov     [rsp+78h+var_50], rax
0x180042dc7  movsd   [rsp+78h+var_28], xmm0
0x180042dcd  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
