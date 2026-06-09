# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x18000c518`
- end: `0x18000c540`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2ac`

## callees

- `0x180009cb0`

## string_xrefs

- `0x18000c521`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    4088,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000c518  sub     rsp, 48h
0x18000c51c  mov     rax, [rsp+48h]
0x18000c521  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c528  mov     [rsp+48h+var_18], 8007000Eh
0x18000c530  mov     edx, 0FF8h
0x18000c535  mov     [rsp+48h+var_20], rax
0x18000c53a  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
