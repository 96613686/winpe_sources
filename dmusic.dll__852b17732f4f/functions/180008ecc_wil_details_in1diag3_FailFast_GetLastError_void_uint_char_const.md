# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180008ecc`
- end: `0x180008ee0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003104`
- `0x1800031d0`
- `0x180003ac8`
- `0x180003e98`
- `0x180004290`
- `0x1800044e0`
- `0x18000739c`
- `0x1800074b0`
- `0x1800085ec`

## callees

- `0x180002634`

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
0x180008ecc  sub     rsp, 38h
0x180008ed0  mov     rax, [rsp+38h]
0x180008ed5  mov     [rsp+38h+var_10], rax
0x180008eda  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
