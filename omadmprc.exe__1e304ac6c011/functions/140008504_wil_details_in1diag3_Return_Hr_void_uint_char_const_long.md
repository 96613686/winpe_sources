# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140008504`
- end: `0x140008523`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `31`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1400042a4`
- `0x140004680`
- `0x140004a88`
- `0x140005c90`
- `0x140006970`
- `0x14000942c`
- `0x14000debc`
- `0x14000e3e4`
- `0x14000e710`
- `0x14000f2b8`
- `0x14000f76c`
- `0x14000fe64`
- `0x1400107ec`
- `0x140010d08`
- `0x140011468`
- `0x140011ac8`
- `0x1400127c4`
- `0x140013350`
- `0x1400147f0`

## callees

- `0x140002f80`

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
0x140008504  sub     rsp, 48h
0x140008508  mov     rax, [rsp+48h]
0x14000850d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140008512  mov     [rsp+48h+var_20], rax; __int64
0x140008517  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000851c  nop
0x14000851d  add     rsp, 48h
0x140008521  retn
```
