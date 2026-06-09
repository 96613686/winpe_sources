# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18002229c`
- end: `0x1800222bc`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012910`
- `0x180012b38`
- `0x180016c70`
- `0x180016e28`

## callees

- `0x180007ed8`

## string_xrefs

- `0x1800222a5`: `onecore\ds\security\cfl\api\lib\CflApiJson.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJson.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18002229c  sub     rsp, 48h
0x1800222a0  mov     rax, [rsp+48h]
0x1800222a5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x1800222ac  mov     [rsp+48h+var_18], r9d
0x1800222b1  mov     [rsp+48h+var_20], rax
0x1800222b6  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
