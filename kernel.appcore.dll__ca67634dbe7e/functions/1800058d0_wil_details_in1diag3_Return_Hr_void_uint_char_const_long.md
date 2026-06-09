# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800058d0`
- end: `0x1800058ed`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001610`
- `0x180001af0`
- `0x180001ef0`
- `0x1800020d0`
- `0x1800029c0`
- `0x180002b70`
- `0x180009a9c`

## callees

- `0x1800058f4`

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
0x1800058d0  sub     rsp, 48h
0x1800058d4  mov     rax, [rsp+48h]
0x1800058d9  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800058de  mov     [rsp+48h+var_20], rax; __int64
0x1800058e3  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800058e8  add     rsp, 48h
0x1800058ec  retn
```
