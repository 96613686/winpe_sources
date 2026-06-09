# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x14000bc2c`
- end: `0x14000bc40`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1400046b8`
- `0x140004ae0`
- `0x140004bd0`
- `0x140005600`
- `0x140005a60`
- `0x1400076b0`
- `0x14000ab9c`
- `0x14000b69c`
- `0x14000bef0`
- `0x140012dc0`
- `0x140013330`
- `0x14001594c`

## callees

- `0x140003338`

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
0x14000bc2c  sub     rsp, 38h
0x14000bc30  mov     rax, [rsp+38h]
0x14000bc35  mov     [rsp+38h+var_10], rax
0x14000bc3a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
