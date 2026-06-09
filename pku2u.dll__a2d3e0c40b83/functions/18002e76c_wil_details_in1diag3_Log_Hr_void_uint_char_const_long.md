# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18002e76c`
- end: `0x18002e79d`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002dbdc`
- `0x18002e0ac`

## callees

- `0x180024dd8`

## string_xrefs

- `0x18002e78b`: `onecore\ds\security\protocols\pku2u\credapi.cxx`

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
    (int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18002e76c  sub     rsp, 48h
0x18002e770  mov     rax, [rsp+48h]
0x18002e775  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18002e77a  mov     [rsp+48h+var_20], rax; __int64
0x18002e77f  mov     [rsp+48h+var_28], 0; __int64
0x18002e788  xor     r9d, r9d; int
0x18002e78b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e792  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002e797  nop
0x18002e798  add     rsp, 48h
0x18002e79c  retn
```
