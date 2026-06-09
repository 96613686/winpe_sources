# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800099b8`
- end: `0x1800099cc`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005338`
- `0x180005a88`
- `0x180005e80`
- `0x180007e4c`
- `0x18000952c`

## callees

- `0x180004584`

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
0x1800099b8  sub     rsp, 38h
0x1800099bc  mov     rax, [rsp+38h]
0x1800099c1  mov     [rsp+38h+var_10], rax
0x1800099c6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
