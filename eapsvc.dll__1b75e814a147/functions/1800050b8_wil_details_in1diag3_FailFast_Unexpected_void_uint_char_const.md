# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800050b8`
- end: `0x1800050e0`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004428`
- `0x1800047cc`
- `0x180007b6c`
- `0x180007c80`

## callees

- `0x180002fc8`

## string_xrefs

- `0x1800050ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800050b8  sub     rsp, 48h
0x1800050bc  mov     rax, [rsp+48h]
0x1800050c1  mov     [rsp+48h+var_18], 8000FFFFh
0x1800050c9  mov     [rsp+48h+var_20], rax
0x1800050ce  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800050d5  mov     edx, 0E01h
0x1800050da  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
