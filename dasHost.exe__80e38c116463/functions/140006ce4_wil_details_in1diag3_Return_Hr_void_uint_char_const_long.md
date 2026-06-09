# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140006ce4`
- end: `0x140006d02`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039d8`
- `0x140003da8`
- `0x1400041a0`
- `0x140005264`
- `0x140007bac`
- `0x140011cc8`
- `0x140011ea4`
- `0x14001211c`
- `0x1400124d0`
- `0x140012748`
- `0x1400128a0`
- `0x140012c08`
- `0x1400138ac`
- `0x140014fd8`
- `0x14001af6a`

## callees

- `0x140002568`

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
0x140006ce4  sub     rsp, 48h
0x140006ce8  mov     rax, [rsp+48h]
0x140006ced  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140006cf2  mov     [rsp+48h+var_20], rax; __int64
0x140006cf7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006cfc  nop
0x140006cfd  add     rsp, 48h
0x140006d01  retn
```
