# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18001634c`
- end: `0x18001637b`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `47`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007944`
- `0x18000a7e4`
- `0x1800114d0`
- `0x1800150d0`
- `0x1800156b4`
- `0x180015cd0`

## callees

- `0x180004e1c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, __int64 a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    a2,
    (__int64)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18001634c  sub     rsp, 48h
0x180016350  mov     rax, [rsp+48h]
0x180016355  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18001635a  mov     [rsp+48h+var_20], rax; __int64
0x18001635f  and     [rsp+48h+var_28], 0
0x180016365  xor     r9d, r9d; int
0x180016368  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18001636f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180016374  nop
0x180016375  add     rsp, 48h
0x180016379  retn
```
