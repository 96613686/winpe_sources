# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x1800123bc`
- end: `0x1800123d5`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e90`
- `0x180011f90`
- `0x1800120e4`
- `0x1800121f0`

## callees

- `0x180011b10`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<0>((__int64)this, a2, a3, (__int64)a4, v5, retaddr, (unsigned int)a4);
}

```

## disassembly

```asm
0x1800123bc  sub     rsp, 48h
0x1800123c0  mov     rax, [rsp+48h]
0x1800123c5  mov     [rsp+48h+var_18], r9d
0x1800123ca  mov     [rsp+48h+var_20], rax
0x1800123cf  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
