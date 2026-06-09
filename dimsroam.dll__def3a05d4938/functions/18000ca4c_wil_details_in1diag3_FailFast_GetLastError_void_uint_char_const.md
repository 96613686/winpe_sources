# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000ca4c`
- end: `0x18000ca60`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080c4`
- `0x180008190`
- `0x18000870c`
- `0x180008ab0`
- `0x180008e80`
- `0x1800090b0`
- `0x18000b7bc`
- `0x18000b8d0`
- `0x18000c268`

## callees

- `0x1800077a0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x18000ca4c  sub     rsp, 38h
0x18000ca50  mov     rax, [rsp+38h]
0x18000ca55  mov     [rsp+38h+var_10], rax
0x18000ca5a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
