# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180015468`
- end: `0x18001548d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001296c`
- `0x18001de88`

## callees

- `0x180004514`

## string_xrefs

- `0x18001547b`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    271,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180015468  sub     rsp, 48h
0x18001546c  mov     rax, [rsp+48h]
0x180015471  mov     [rsp+48h+var_18], r9d
0x180015476  mov     [rsp+48h+var_20], rax
0x18001547b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015482  mov     edx, 10Fh
0x180015487  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
