# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18000603c`
- end: `0x180006050`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000315c`
- `0x1800034b8`
- `0x180003888`
- `0x180004eec`
- `0x180005c6c`

## callees

- `0x1800026e0`

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
0x18000603c  sub     rsp, 38h
0x180006040  mov     rax, [rsp+38h]
0x180006045  mov     [rsp+38h+var_10], rax
0x18000604a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
