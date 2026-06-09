# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000bf64`
- end: `0x18000bf8c`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a8a4`
- `0x18000ac80`
- `0x180011538`
- `0x1800116a4`

## callees

- `0x1800090bc`

## string_xrefs

- `0x18000bf7a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x18000bf64  sub     rsp, 48h
0x18000bf68  mov     rax, [rsp+48h]
0x18000bf6d  mov     [rsp+48h+var_18], 8000FFFFh
0x18000bf75  mov     [rsp+48h+var_20], rax
0x18000bf7a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bf81  mov     edx, 0E01h
0x18000bf86  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
