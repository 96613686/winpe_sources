# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180021b7c`
- end: `0x180021b9a`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f3d8`
- `0x18001f540`
- `0x18001f904`
- `0x1800205e4`
- `0x180020d6c`
- `0x180020e98`
- `0x180022588`
- `0x1800225fc`

## callees

- `0x18001e830`

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
0x180021b7c  sub     rsp, 48h
0x180021b80  mov     rax, [rsp+48h]
0x180021b85  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180021b8a  mov     [rsp+48h+var_20], rax; __int64
0x180021b8f  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180021b94  nop
0x180021b95  add     rsp, 48h
0x180021b99  retn
```
