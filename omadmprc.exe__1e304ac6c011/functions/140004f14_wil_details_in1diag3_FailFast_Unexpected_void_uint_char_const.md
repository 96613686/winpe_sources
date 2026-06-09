# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x140004f14`
- end: `0x140004f3c`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400042a4`
- `0x140004680`
- `0x140007dc4`
- `0x140007f30`

## callees

- `0x140003034`

## string_xrefs

- `0x140004f2a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140004f14  sub     rsp, 48h
0x140004f18  mov     rax, [rsp+48h]
0x140004f1d  mov     [rsp+48h+var_18], 8000FFFFh
0x140004f25  mov     [rsp+48h+var_20], rax
0x140004f2a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004f31  mov     edx, 0E01h
0x140004f36  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
