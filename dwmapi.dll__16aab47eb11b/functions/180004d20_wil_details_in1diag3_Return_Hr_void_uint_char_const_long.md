# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180004d20`
- end: `0x180004d3d`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `43`
- callee_count: `1`
- tags: ``

## callers

- `0x18000387c`
- `0x180004610`
- `0x180004a40`
- `0x180004d44`
- `0x180004e30`
- `0x180005788`
- `0x180005980`
- `0x180005bc0`
- `0x180005d14`
- `0x18000601c`
- `0x180006670`
- `0x180006aa0`
- `0x180006b30`
- `0x18000a650`
- `0x18000bacc`
- `0x18000c35c`
- `0x18000c48c`
- `0x18000e8f0`
- `0x1800114e0`
- `0x180011800`
- `0x1800124d0`
- `0x180012550`
- `0x1800125d0`
- `0x180012650`
- `0x1800126d0`
- `0x180012750`
- `0x180012870`
- `0x180012930`
- `0x1800129b0`
- `0x180012b20`
- `0x180012bd0`
- `0x180012c80`
- `0x180012d30`
- `0x180012de0`
- `0x180012e60`
- `0x180012ee0`
- `0x180013010`
- `0x1800130c0`
- `0x180013140`
- `0x1800131c0`
- `0x180013aa0`
- `0x180014ce0`
- `0x180015224`

## callees

- `0x18000bd30`

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
0x180004d20  sub     rsp, 48h
0x180004d24  mov     rax, [rsp+48h]
0x180004d29  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180004d2e  mov     [rsp+48h+var_20], rax; __int64
0x180004d33  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004d38  add     rsp, 48h
0x180004d3c  retn
```
