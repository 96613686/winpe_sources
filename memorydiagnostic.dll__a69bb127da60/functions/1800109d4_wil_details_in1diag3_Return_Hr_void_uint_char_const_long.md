# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800109d4`
- end: `0x1800109f2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180008cc8`
- `0x180009098`
- `0x1800094d4`
- `0x180009fc0`
- `0x18000a294`
- `0x18000a6d4`
- `0x18000b238`
- `0x18000d448`
- `0x18000dcdc`
- `0x180011760`
- `0x1800139d0`
- `0x180014030`
- `0x1800143d0`
- `0x180014570`
- `0x18001f6ec`

## callees

- `0x1800052cc`

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
0x1800109d4  sub     rsp, 48h
0x1800109d8  mov     rax, [rsp+48h]
0x1800109dd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800109e2  mov     [rsp+48h+var_20], rax; __int64
0x1800109e7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800109ec  nop
0x1800109ed  add     rsp, 48h
0x1800109f1  retn
```
