# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000fb48`
- end: `0x14000fb66`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400026a0`
- `0x1400029e0`
- `0x140002ea0`
- `0x14000de20`
- `0x14000e354`
- `0x140011a6c`
- `0x140012700`
- `0x140013cec`
- `0x140016968`

## callees

- `0x14000fb6c`

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
0x14000fb48  sub     rsp, 48h
0x14000fb4c  mov     rax, [rsp+48h]
0x14000fb51  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000fb56  mov     [rsp+48h+var_20], rax; __int64
0x14000fb5b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000fb60  nop
0x14000fb61  add     rsp, 48h
0x14000fb65  retn
```
