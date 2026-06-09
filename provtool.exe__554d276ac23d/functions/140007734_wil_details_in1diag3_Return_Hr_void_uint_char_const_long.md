# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140007734`
- end: `0x140007752`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140003de0`
- `0x1400045f0`
- `0x140004d58`
- `0x140005854`
- `0x1400059ac`
- `0x140006b04`
- `0x140007844`
- `0x14000820c`
- `0x140009590`
- `0x140009918`

## callees

- `0x140002638`

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
0x140007734  sub     rsp, 48h
0x140007738  mov     rax, [rsp+48h]
0x14000773d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140007742  mov     [rsp+48h+var_20], rax; __int64
0x140007747  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000774c  nop
0x14000774d  add     rsp, 48h
0x140007751  retn
```
