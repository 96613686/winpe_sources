# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180007efc`
- end: `0x180007f2d`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e18`
- `0x180007e68`

## callees

- `0x180002428`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    (int)a2,
    (__int64)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180007efc  sub     rsp, 48h
0x180007f00  mov     rax, [rsp+48h]
0x180007f05  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007f0a  mov     [rsp+48h+var_20], rax; __int64
0x180007f0f  mov     [rsp+48h+var_28], 0; __int64
0x180007f18  xor     r9d, r9d; int
0x180007f1b  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180007f22  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007f27  nop
0x180007f28  add     rsp, 48h
0x180007f2c  retn
```
