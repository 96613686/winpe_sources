# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180015668`
- end: `0x180015699`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007944`
- `0x18000a6d4`
- `0x180010ac4`
- `0x1800143d0`
- `0x18001488c`
- `0x180015010`

## callees

- `0x180005324`

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
    (__int64)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180015668  sub     rsp, 48h
0x18001566c  mov     rax, [rsp+48h]
0x180015671  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180015676  mov     [rsp+48h+var_20], rax; __int64
0x18001567b  mov     [rsp+48h+var_28], 0; __int64
0x180015684  xor     r9d, r9d; int
0x180015687  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18001568e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015693  nop
0x180015694  add     rsp, 48h
0x180015698  retn
```
