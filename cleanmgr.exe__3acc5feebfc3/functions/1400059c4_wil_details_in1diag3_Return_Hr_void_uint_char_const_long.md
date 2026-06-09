# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1400059c4`
- end: `0x1400059e2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140004238`
- `0x1400043e4`
- `0x140004e64`
- `0x1400054dc`
- `0x14000612c`
- `0x1400061a0`
- `0x140007260`
- `0x140007dd0`

## callees

- `0x1400036a8`

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
0x1400059c4  sub     rsp, 48h
0x1400059c8  mov     rax, [rsp+48h]
0x1400059cd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1400059d2  mov     [rsp+48h+var_20], rax; __int64
0x1400059d7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400059dc  nop
0x1400059dd  add     rsp, 48h
0x1400059e1  retn
```
