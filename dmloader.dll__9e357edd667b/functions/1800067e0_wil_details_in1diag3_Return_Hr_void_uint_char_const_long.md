# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800067e0`
- end: `0x1800067fd`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003114`
- `0x1800034b8`
- `0x1800038a4`
- `0x180004b10`
- `0x180007048`

## callees

- `0x180002280`

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
0x1800067e0  sub     rsp, 48h
0x1800067e4  mov     rax, [rsp+48h]
0x1800067e9  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800067ee  mov     [rsp+48h+var_20], rax; __int64
0x1800067f3  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800067f8  add     rsp, 48h
0x1800067fc  retn
```
