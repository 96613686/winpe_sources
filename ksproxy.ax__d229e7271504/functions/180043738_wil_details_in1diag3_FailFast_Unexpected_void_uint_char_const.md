# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180043738`
- end: `0x180043760`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800119f0`

## callees

- `0x18002031c`

## string_xrefs

- `0x180043741`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    241,
    (__int64)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
    (__int64)a4,
    v4,
    retaddr,
    0x8000FFFF);
}

```

## disassembly

```asm
0x180043738  sub     rsp, 48h
0x18004373c  mov     rax, [rsp+48h]
0x180043741  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180043748  mov     [rsp+48h+var_18], 8000FFFFh
0x180043750  mov     edx, 0F1h
0x180043755  mov     [rsp+48h+var_20], rax
0x18004375a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
