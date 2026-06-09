# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18004dd70`
- end: `0x18004dd90`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004b710`

## callees

- `0x18002a250`

## string_xrefs

- `0x18004dd79`: `onecore\base\ngscb\pcrpf\txfjson\ppftxfjson.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18004dd70  sub     rsp, 48h
0x18004dd74  mov     rax, [rsp+48h]
0x18004dd79  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\pcrpf\\txfjson\\p"...
0x18004dd80  mov     [rsp+48h+var_18], r9d
0x18004dd85  mov     [rsp+48h+var_20], rax
0x18004dd8a  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
