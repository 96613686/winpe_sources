# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800113a4`
- end: `0x1800113c3`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `31`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180008cc4`
- `0x1800090b8`
- `0x180009504`
- `0x18000a1a8`
- `0x18000a490`
- `0x18000a7e4`
- `0x18000b3e0`
- `0x18000dbc8`
- `0x18000e790`
- `0x1800121a0`
- `0x1800145d0`
- `0x180014cd0`
- `0x1800150d0`
- `0x1800152b8`
- `0x180020c20`

## callees

- `0x180004dc4`

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
0x1800113a4  sub     rsp, 48h
0x1800113a8  mov     rax, [rsp+48h]
0x1800113ad  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800113b2  mov     [rsp+48h+var_20], rax; __int64
0x1800113b7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long)
0x1800113bc  nop
0x1800113bd  add     rsp, 48h
0x1800113c1  retn
```
