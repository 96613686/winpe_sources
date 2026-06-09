# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18001d2d4`
- end: `0x18001d2f4`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c684`
- `0x18001ca7c`
- `0x180024834`
- `0x1800249c4`

## callees

- `0x18001b7a4`

## string_xrefs

- `0x18001d2dd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    3127,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001d2d4  sub     rsp, 48h
0x18001d2d8  mov     rax, [rsp+48h]
0x18001d2dd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d2e4  mov     edx, 0C37h
0x18001d2e9  mov     [rsp+48h+var_20], rax
0x18001d2ee  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)
```
