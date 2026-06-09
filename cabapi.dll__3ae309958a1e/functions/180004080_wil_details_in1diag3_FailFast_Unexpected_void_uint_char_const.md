# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180004080`
- end: `0x1800040a9`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a68`
- `0x18000536c`

## callees

- `0x180002748`

## string_xrefs

- `0x180004097`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004080  sub     rsp, 58h
0x180004084  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000408d  mov     rax, [rsp+58h]
0x180004092  mov     [rsp+58h+var_30], rax
0x180004097  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000409e  mov     edx, 0E01h
0x1800040a3  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
