# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180005044`
- end: `0x180005067`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043ec`
- `0x1800047e4`
- `0x180007ab8`
- `0x180007c50`
- `0x1800112b8`
- `0x180014464`

## callees

- `0x180002fe4`

## string_xrefs

- `0x18000505a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
    (_DWORD)a2,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180005044  sub     rsp, 48h
0x180005048  mov     rax, [rsp+48h]
0x18000504d  mov     [rsp+48h+var_18], 8000FFFFh
0x180005055  mov     [rsp+48h+var_20], rax
0x18000505a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005061  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)
```
