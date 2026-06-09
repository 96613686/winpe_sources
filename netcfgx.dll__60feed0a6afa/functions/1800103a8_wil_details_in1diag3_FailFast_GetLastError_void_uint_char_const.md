# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800103a8`
- end: `0x1800103bc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c2fc`
- `0x18000c3c8`
- `0x18000c8ec`
- `0x18000cc94`
- `0x18000ea9c`
- `0x18000ff0c`

## callees

- `0x18000b7c4`

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
0x1800103a8  sub     rsp, 38h
0x1800103ac  mov     rax, [rsp+38h]
0x1800103b1  mov     [rsp+38h+var_10], rax
0x1800103b6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
