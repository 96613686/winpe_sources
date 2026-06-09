# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x1800074bc`
- end: `0x1800074dc`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800023e8`
- `0x18000244c`
- `0x1800024c4`
- `0x180002544`
- `0x1800025d8`
- `0x180002648`
- `0x1800026b8`
- `0x180002728`
- `0x1800027a8`
- `0x180002820`
- `0x18000d0c8`
- `0x18000d13d`
- `0x18000d1b5`

## callees

- `0x18000348c`

## string_xrefs

- `0x1800074c5`: `onecore\vm\dv\net\hns\service\common\rpc\client\RpcClient.h`

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
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\rpc\\client\\RpcClient.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800074bc  sub     rsp, 48h
0x1800074c0  mov     rax, [rsp+48h]
0x1800074c5  lea     r8, aOnecoreVmDvNet_3; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1800074cc  mov     [rsp+48h+var_18], r9d
0x1800074d1  mov     [rsp+48h+var_20], rax
0x1800074d6  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
