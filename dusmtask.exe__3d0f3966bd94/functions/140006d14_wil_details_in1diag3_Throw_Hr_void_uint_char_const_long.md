# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x140006d14`
- end: `0x140006d2d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006304`
- `0x140007018`

## callees

- `0x140002758`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x140006d14  sub     rsp, 48h
0x140006d18  mov     rax, [rsp+48h]
0x140006d1d  mov     [rsp+48h+var_18], r9d
0x140006d22  mov     [rsp+48h+var_20], rax
0x140006d27  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
