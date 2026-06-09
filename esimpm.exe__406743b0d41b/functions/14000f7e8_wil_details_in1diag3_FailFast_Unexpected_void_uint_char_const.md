# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x14000f7e8`
- end: `0x14000f808`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000eb58`
- `0x14000eefc`
- `0x14001211c`
- `0x140012230`

## callees

- `0x14000d638`

## string_xrefs

- `0x14000f7f6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x14000f7e8  sub     rsp, 48h
0x14000f7ec  mov     rax, [rsp+48h]
0x14000f7f1  mov     [rsp+48h+var_20], rax
0x14000f7f6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000f7fd  mov     edx, 0E01h
0x14000f802  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
