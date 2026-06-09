# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x1800120dc`
- end: `0x1800120fc`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800126d0`

## callees

- `0x18000eac0`

## string_xrefs

- `0x1800120e5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    7368,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x1800120dc  sub     rsp, 38h
0x1800120e0  mov     rax, [rsp+38h]
0x1800120e5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800120ec  mov     edx, 1CC8h; int
0x1800120f1  mov     [rsp+38h+var_10], rax; char *
0x1800120f6  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
