# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800162e8`
- end: `0x1800162fc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a38`
- `0x180007abc`
- `0x1800084d8`
- `0x180008cc4`
- `0x1800090b8`
- `0x180010788`
- `0x180010918`
- `0x180013df0`
- `0x1800145d0`
- `0x180014cd0`
- `0x1800150d0`
- `0x1800152b8`
- `0x1800188bc`
- `0x180023780`

## callees

- `0x180004bf8`

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
0x1800162e8  sub     rsp, 38h
0x1800162ec  mov     rax, [rsp+38h]
0x1800162f1  mov     [rsp+38h+var_10], rax
0x1800162f6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
