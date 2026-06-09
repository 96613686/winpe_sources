# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1400032b4`
- end: `0x1400032d0`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005328`
- `0x1400057f8`

## callees

- `0x1400027fc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>((__int64)this, a2, a3, (__int64)a4, v4, retaddr, 0x8000FFFF);
}

```

## disassembly

```asm
0x1400032b4  sub     rsp, 48h
0x1400032b8  mov     rax, [rsp+48h]
0x1400032bd  mov     [rsp+48h+var_18], 8000FFFFh
0x1400032c5  mov     [rsp+48h+var_20], rax
0x1400032ca  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
