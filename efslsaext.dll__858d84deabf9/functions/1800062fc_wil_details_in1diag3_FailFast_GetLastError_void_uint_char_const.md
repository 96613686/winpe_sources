# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800062fc`
- end: `0x180006310`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003900`
- `0x180003bf8`
- `0x180003f9c`
- `0x1800041c8`
- `0x180005648`
- `0x180005f2c`
- `0x18000ca30`
- `0x18000cf30`
- `0x180010bb0`

## callees

- `0x1800030a4`

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
0x1800062fc  sub     rsp, 38h
0x180006300  mov     rax, [rsp+38h]
0x180006305  mov     [rsp+38h+var_10], rax
0x18000630a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
