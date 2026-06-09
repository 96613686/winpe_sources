# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180005b10`
- end: `0x180005b24`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e90`
- `0x180003140`
- `0x180003524`
- `0x180004a5c`
- `0x18000564c`

## callees

- `0x180002340`

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
0x180005b10  sub     rsp, 38h
0x180005b14  mov     rax, [rsp+38h]
0x180005b19  mov     [rsp+38h+var_10], rax
0x180005b1e  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
