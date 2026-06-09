# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000c960`
- end: `0x18000c980`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008cc4`
- `0x1800090b8`
- `0x180010788`
- `0x180010918`

## callees

- `0x180004e80`

## string_xrefs

- `0x18000c96e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000c960  sub     rsp, 48h
0x18000c964  mov     rax, [rsp+48h]
0x18000c969  mov     [rsp+48h+var_20], rax
0x18000c96e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c975  mov     edx, 0C37h
0x18000c97a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)
```
