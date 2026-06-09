# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x1800215ec`
- end: `0x180021614`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013784`

## callees

- `0x18001659c`

## string_xrefs

- `0x1800215f5`: `onecore\internal\sdk\inc\wil\opensource\wil\wrl.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    63,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\wrl.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800215ec  sub     rsp, 48h
0x1800215f0  mov     rax, [rsp+48h]
0x1800215f5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800215fc  mov     [rsp+48h+var_18], 8007000Eh
0x180021604  mov     edx, 3Fh ; '?'
0x180021609  mov     [rsp+48h+var_20], rax
0x18002160e  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
