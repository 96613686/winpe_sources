# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180006740`
- end: `0x18000675d`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `29`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000357c`
- `0x180003a68`
- `0x180003e38`
- `0x18000536c`
- `0x18000615c`

## callees

- `0x180002564`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  char *retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x180006740  sub     rsp, 48h
0x180006744  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000674d  mov     rax, [rsp+48h]
0x180006752  mov     [rsp+48h+var_20], rax
0x180006757  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
