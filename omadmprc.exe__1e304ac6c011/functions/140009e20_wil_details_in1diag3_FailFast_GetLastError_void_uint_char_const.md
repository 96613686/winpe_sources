# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x140009e20`
- end: `0x140009e34`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f50`
- `0x1400042a4`
- `0x140004680`
- `0x140004bf4`
- `0x140007dc4`
- `0x140007f30`
- `0x14000942c`
- `0x14000a120`
- `0x14000f250`

## callees

- `0x140002e54`

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
0x140009e20  sub     rsp, 38h
0x140009e24  mov     rax, [rsp+38h]
0x140009e29  mov     [rsp+38h+var_10], rax
0x140009e2e  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
