# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180008e58`
- end: `0x180008e76`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008010`
- `0x1800083b4`
- `0x180008ac0`
- `0x18000914c`

## callees

- `0x180007bd4`

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
0x180008e58  sub     rsp, 48h
0x180008e5c  mov     rax, [rsp+48h]
0x180008e61  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180008e66  mov     [rsp+48h+var_20], rax; __int64
0x180008e6b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008e70  nop
0x180008e71  add     rsp, 48h
0x180008e75  retn
```
