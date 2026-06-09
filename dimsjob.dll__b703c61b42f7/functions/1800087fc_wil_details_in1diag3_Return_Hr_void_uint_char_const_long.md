# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800087fc`
- end: `0x18000881a`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ca8`
- `0x180005e10`
- `0x180005fd8`
- `0x180006d40`
- `0x1800075a8`
- `0x1800076cc`
- `0x180009300`
- `0x180009374`

## callees

- `0x1800051c4`

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
0x1800087fc  sub     rsp, 48h
0x180008800  mov     rax, [rsp+48h]
0x180008805  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000880a  mov     [rsp+48h+var_20], rax; __int64
0x18000880f  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008814  nop
0x180008815  add     rsp, 48h
0x180008819  retn
```
