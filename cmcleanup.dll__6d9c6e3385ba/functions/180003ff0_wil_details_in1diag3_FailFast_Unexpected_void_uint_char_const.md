# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180003ff0`
- end: `0x180004004`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003518`
- `0x1800055d8`

## callees

- `0x18000248c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180003ff0  sub     rsp, 48h
0x180003ff4  mov     rax, [rsp+48h]
0x180003ff9  mov     [rsp+48h+var_20], rax
0x180003ffe  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
