# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007b84`
- end: `0x180007b9d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007888`
- `0x18000a5f4`
- `0x18000ad90`
- `0x18000b064`

## callees

- `0x180006750`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  __int64 v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<0>((__int64)this, a2, a3, (__int64)a4, v5, retaddr, (unsigned int)a4);
}

```

## disassembly

```asm
0x180007b84  sub     rsp, 48h
0x180007b88  mov     rax, [rsp+48h]
0x180007b8d  mov     [rsp+48h+var_18], r9d
0x180007b92  mov     [rsp+48h+var_20], rax
0x180007b97  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
