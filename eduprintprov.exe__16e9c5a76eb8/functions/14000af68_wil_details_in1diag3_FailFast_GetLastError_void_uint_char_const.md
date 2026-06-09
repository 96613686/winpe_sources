# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x14000af68`
- end: `0x14000af7c`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140004cdc`
- `0x140004da8`
- `0x140005738`
- `0x140005b08`
- `0x140006434`
- `0x140006680`
- `0x14000943c`
- `0x140009550`
- `0x14000a6cc`

## callees

- `0x140003748`

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
0x14000af68  sub     rsp, 38h
0x14000af6c  mov     rax, [rsp+38h]
0x14000af71  mov     [rsp+38h+var_10], rax
0x14000af76  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
