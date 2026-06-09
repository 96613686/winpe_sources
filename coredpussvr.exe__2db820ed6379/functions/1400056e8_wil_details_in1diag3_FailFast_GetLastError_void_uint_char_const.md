# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1400056e8`
- end: `0x1400056fc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e88`
- `0x14000308c`
- `0x1400047e4`
- `0x1400052dc`
- `0x140005704`

## callees

- `0x1400022dc`

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
0x1400056e8  sub     rsp, 38h
0x1400056ec  mov     rax, [rsp+38h]
0x1400056f1  mov     [rsp+38h+var_10], rax
0x1400056f6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
