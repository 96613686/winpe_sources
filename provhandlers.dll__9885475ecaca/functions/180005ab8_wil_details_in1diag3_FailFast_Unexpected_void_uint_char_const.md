# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180005ab8`
- end: `0x180005ae0`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d50`
- `0x18000724c`
- `0x180016630`
- `0x180023af0`

## callees

- `0x180003a70`

## string_xrefs

- `0x180005ace`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005ab8  sub     rsp, 48h
0x180005abc  mov     rax, [rsp+48h]
0x180005ac1  mov     [rsp+48h+var_18], 8000FFFFh
0x180005ac9  mov     [rsp+48h+var_20], rax
0x180005ace  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005ad5  mov     edx, 0E01h
0x180005ada  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
