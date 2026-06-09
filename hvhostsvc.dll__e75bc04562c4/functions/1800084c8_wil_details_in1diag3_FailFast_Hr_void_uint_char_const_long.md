# wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)

- ea: `0x1800084c8`
- end: `0x1800084ed`
- name: `?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008a50`

## callees

- `0x180003070`

## string_xrefs

- `0x1800084db`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    3249,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x1800084c8  sub     rsp, 48h
0x1800084cc  mov     rax, [rsp+48h]
0x1800084d1  mov     [rsp+48h+var_18], r9d
0x1800084d6  mov     [rsp+48h+var_20], rax
0x1800084db  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800084e2  mov     edx, 0CB1h
0x1800084e7  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
