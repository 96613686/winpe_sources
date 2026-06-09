# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18004370c`
- end: `0x180043731`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800119f0`

## callees

- `0x18002031c`

## string_xrefs

- `0x180043715`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
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
    5324,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x18004370c  sub     rsp, 48h
0x180043710  mov     rax, [rsp+48h]
0x180043715  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004371c  mov     [rsp+48h+var_18], r9d
0x180043721  mov     edx, 14CCh
0x180043726  mov     [rsp+48h+var_20], rax
0x18004372b  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
