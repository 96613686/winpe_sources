# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180008714`
- end: `0x18000873f`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `43`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000752c`
- `0x180007e0c`
- `0x180009980`
- `0x1800103b4`
- `0x180011f44`
- `0x180015880`
- `0x180016c14`
- `0x180017368`
- `0x1800178fc`
- `0x1800188c0`

## callees

- `0x18000333c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x180008714  sub     rsp, 48h
0x180008718  mov     rax, [rsp+48h]
0x18000871d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180008722  mov     [rsp+48h+var_20], rax; __int64
0x180008727  mov     [rsp+48h+var_28], 0; __int64
0x180008730  xor     r9d, r9d; int
0x180008733  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008738  nop
0x180008739  add     rsp, 48h
0x18000873d  retn
```
