# wil::details::ReportFailure_CaughtExceptionCommon<0>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000b5f0`
- end: `0x18000b619`
- name: `??$ReportFailure_CaughtExceptionCommon@$0A@@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(__int64, int, int, int, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b5a0`

## callees

- `0x18000b620`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommon<0>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  char v8; // [rsp+50h] [rbp-18h] BYREF

  wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>((unsigned int)&v8, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b5f0  sub     rsp, 68h
0x18000b5f4  mov     rax, [rsp+68h+arg_38]
0x18000b5fc  lea     rcx, [rsp+68h+var_18]
0x18000b601  mov     [rsp+68h+var_30], rax
0x18000b606  mov     rax, [rsp+68h+arg_30]
0x18000b60e  mov     [rsp+68h+var_38], rax
0x18000b613  call    ??$ReportFailure_CaughtExceptionCommonNoReturnBase@$0A@@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)
```
