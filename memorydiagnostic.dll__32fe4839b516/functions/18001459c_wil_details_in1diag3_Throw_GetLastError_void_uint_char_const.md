# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x18001459c`
- end: `0x1800145bc`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007074`

## callees

- `0x180004c7c`

## string_xrefs

- `0x1800145a5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<0>(
    (_DWORD)this,
    7274,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001459c  sub     rsp, 38h
0x1800145a0  mov     rax, [rsp+38h]
0x1800145a5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800145ac  mov     edx, 1C6Ah
0x1800145b1  mov     [rsp+38h+var_10], rax
0x1800145b6  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
