# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1400083bc`
- end: `0x1400083d0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000312c`
- `0x1400031f8`
- `0x1400039d8`
- `0x140003da8`
- `0x1400041a0`
- `0x1400043e0`
- `0x1400068ac`
- `0x1400069c0`
- `0x140007bac`
- `0x140010820`

## callees

- `0x140002430`

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
0x1400083bc  sub     rsp, 38h
0x1400083c0  mov     rax, [rsp+38h]
0x1400083c5  mov     [rsp+38h+var_10], rax
0x1400083ca  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
