# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005964`
- end: `0x180005982`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180003db8`
- `0x180004188`
- `0x180004d44`
- `0x1800063cc`
- `0x180006af8`
- `0x18000ad80`
- `0x18000ae80`
- `0x18000b640`
- `0x18000b6c0`
- `0x18000b830`
- `0x18000c4f0`
- `0x18000c6b0`
- `0x18000c950`
- `0x18000cc90`
- `0x18000ce20`
- `0x18000cf60`
- `0x18000d0d0`
- `0x18000d3e0`

## callees

- `0x1800031c8`

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
0x180005964  sub     rsp, 48h
0x180005968  mov     rax, [rsp+48h]
0x18000596d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005972  mov     [rsp+48h+var_20], rax; __int64
0x180005977  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000597c  nop
0x18000597d  add     rsp, 48h
0x180005981  retn
```
