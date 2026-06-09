# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x18001399c`
- end: `0x1800139bc`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006fd8`

## callees

- `0x1800051ac`

## string_xrefs

- `0x1800139a5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
    7368,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001399c  sub     rsp, 38h
0x1800139a0  mov     rax, [rsp+38h]
0x1800139a5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800139ac  mov     edx, 1CC8h
0x1800139b1  mov     [rsp+38h+var_10], rax
0x1800139b6  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
