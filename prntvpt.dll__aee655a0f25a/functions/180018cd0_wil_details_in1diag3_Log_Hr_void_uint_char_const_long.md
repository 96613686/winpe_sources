# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180018cd0`
- end: `0x180018d00`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `48`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800189c8`
- `0x180018f10`

## callees

- `0x1800109e8`

## string_xrefs

- `0x180018cd9`: `printscan\print\spooler\spoolss\ptservice\server\ptapi.cxx`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"printscan\\print\\spooler\\spoolss\\ptservice\\server\\ptapi.cxx",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180018cd0  sub     rsp, 48h
0x180018cd4  mov     rax, [rsp+48h]
0x180018cd9  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\spoolss\\pts"...
0x180018ce0  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180018ce5  xor     r9d, r9d; int
0x180018ce8  mov     [rsp+48h+var_20], rax; __int64
0x180018ced  mov     [rsp+48h+var_28], 0; __int64
0x180018cf6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180018cfb  add     rsp, 48h
0x180018cff  retn
```
