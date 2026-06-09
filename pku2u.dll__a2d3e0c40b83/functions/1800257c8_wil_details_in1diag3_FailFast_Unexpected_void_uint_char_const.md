# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800257c8`
- end: `0x1800257e8`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026e6c`

## callees

- `0x180024e3c`

## string_xrefs

- `0x1800257d6`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800257c8  sub     rsp, 48h
0x1800257cc  mov     rax, [rsp+48h]
0x1800257d1  mov     [rsp+48h+var_20], rax
0x1800257d6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800257dd  mov     edx, 0E01h
0x1800257e2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
