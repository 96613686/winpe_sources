# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x1800083d4`
- end: `0x1800083fc`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075bc`

## callees

- `0x1800071d0`

## string_xrefs

- `0x1800083dd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<0>(
    (__int64)this,
    4088,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (__int64)a4,
    v4,
    retaddr,
    0x8007000E);
}

```

## disassembly

```asm
0x1800083d4  sub     rsp, 48h
0x1800083d8  mov     rax, [rsp+48h]
0x1800083dd  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800083e4  mov     [rsp+48h+var_18], 8007000Eh
0x1800083ec  mov     edx, 0FF8h
0x1800083f1  mov     [rsp+48h+var_20], rax
0x1800083f6  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
