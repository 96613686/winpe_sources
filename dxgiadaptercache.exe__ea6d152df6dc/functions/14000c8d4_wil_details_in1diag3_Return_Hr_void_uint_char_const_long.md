# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000c8d4`
- end: `0x14000c8f2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140007368`
- `0x140007738`
- `0x140007f28`
- `0x1400090c4`
- `0x140009a44`
- `0x14000adf0`
- `0x14000bebc`
- `0x14000de70`

## callees

- `0x140003b5c`

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
0x14000c8d4  sub     rsp, 48h
0x14000c8d8  mov     rax, [rsp+48h]
0x14000c8dd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000c8e2  mov     [rsp+48h+var_20], rax; __int64
0x14000c8e7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000c8ec  nop
0x14000c8ed  add     rsp, 48h
0x14000c8f1  retn
```
