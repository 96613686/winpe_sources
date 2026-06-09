# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180010cb4`
- end: `0x180010cd8`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `36`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800104d4`

## callees

- `0x180002748`

## string_xrefs

- `0x180010ccb`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180010cb4  sub     rsp, 58h
0x180010cb8  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180010cc1  mov     rax, [rsp+58h]
0x180010cc6  mov     [rsp+58h+var_30], rax
0x180010ccb  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x180010cd2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
