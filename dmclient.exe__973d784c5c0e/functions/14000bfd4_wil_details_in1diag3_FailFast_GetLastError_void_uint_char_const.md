# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x14000bfd4`
- end: `0x14000bfe8`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a04`
- `0x140004be0`
- `0x140004ce4`
- `0x140005ae4`
- `0x140007810`
- `0x14000ae34`
- `0x14000b9ec`
- `0x14000c2a4`
- `0x14000c340`
- `0x140015fb4`
- `0x140017c4c`

## callees

- `0x140003378`

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
0x14000bfd4  sub     rsp, 38h
0x14000bfd8  mov     rax, [rsp+38h]
0x14000bfdd  mov     [rsp+38h+var_10], rax
0x14000bfe2  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
