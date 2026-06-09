# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180008ebc`
- end: `0x180008ed0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003208`
- `0x1800032d4`
- `0x1800039e4`
- `0x180003d88`
- `0x180004158`
- `0x1800044c0`
- `0x180007690`
- `0x1800077a4`
- `0x1800085f8`

## callees

- `0x1800028e4`

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
0x180008ebc  sub     rsp, 38h
0x180008ec0  mov     rax, [rsp+38h]
0x180008ec5  mov     [rsp+38h+var_10], rax
0x180008eca  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
