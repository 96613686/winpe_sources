# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180007eec`
- end: `0x180007f00`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fe8`
- `0x1800030b4`
- `0x1800037a8`
- `0x180003b4c`
- `0x180003f1c`
- `0x180004140`
- `0x1800067b0`
- `0x1800068c4`
- `0x18000770c`

## callees

- `0x1800024e0`

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
0x180007eec  sub     rsp, 38h
0x180007ef0  mov     rax, [rsp+38h]
0x180007ef5  mov     [rsp+38h+var_10], rax
0x180007efa  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
