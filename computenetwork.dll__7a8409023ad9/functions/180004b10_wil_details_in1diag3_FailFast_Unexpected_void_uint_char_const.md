# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180004b10`
- end: `0x180004b38`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044f8`
- `0x1800066dc`

## callees

- `0x180003428`

## string_xrefs

- `0x180004b26`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180004b10  sub     rsp, 48h
0x180004b14  mov     rax, [rsp+48h]
0x180004b19  mov     [rsp+48h+var_18], 8000FFFFh
0x180004b21  mov     [rsp+48h+var_20], rax
0x180004b26  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004b2d  mov     edx, 0E01h
0x180004b32  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
