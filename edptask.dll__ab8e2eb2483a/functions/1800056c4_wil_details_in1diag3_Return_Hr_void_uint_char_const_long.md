# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800056c4`
- end: `0x1800056e2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d40`
- `0x180004110`
- `0x180004cb4`
- `0x1800061ac`
- `0x180007e80`
- `0x180008920`
- `0x1800089b0`
- `0x1800089e0`
- `0x180008a70`
- `0x180009f20`
- `0x18000a0b0`
- `0x18000a140`
- `0x18000a1d0`
- `0x18000a260`
- `0x18000a2f0`
- `0x18000a380`
- `0x18000a410`
- `0x18000a4a0`
- `0x18000a530`
- `0x18000a5c0`
- `0x18000a650`
- `0x18000a6e0`
- `0x18000a770`
- `0x18000a800`
- `0x18000a890`
- `0x18000ac1c`
- `0x180010720`
- `0x1800108e0`
- `0x180010aa0`
- `0x180010cb0`
- `0x1800138ef`

## callees

- `0x180003178`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x1800056c4  sub     rsp, 48h
0x1800056c8  mov     rax, [rsp+48h]
0x1800056cd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800056d2  mov     [rsp+48h+var_20], rax; __int64
0x1800056d7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800056dc  nop
0x1800056dd  add     rsp, 48h
0x1800056e1  retn
```
