# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18000ba8c`
- end: `0x18000bab1`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c420`

## callees

- `0x1800031bc`

## string_xrefs

- `0x18000ba9f`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    501,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000ba8c  sub     rsp, 48h
0x18000ba90  mov     rax, [rsp+48h]
0x18000ba95  mov     [rsp+48h+var_18], r9d
0x18000ba9a  mov     [rsp+48h+var_20], rax
0x18000ba9f  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000baa6  mov     edx, 1F5h
0x18000baab  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
