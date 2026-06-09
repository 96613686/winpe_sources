# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000b084`
- end: `0x14000b0a3`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `31`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f18`
- `0x140004198`
- `0x140004ce4`
- `0x140005740`
- `0x1400074c4`
- `0x14000b9ec`
- `0x140015fb4`

## callees

- `0x1400034a8`

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
0x14000b084  sub     rsp, 48h
0x14000b088  mov     rax, [rsp+48h]
0x14000b08d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000b092  mov     [rsp+48h+var_20], rax; __int64
0x14000b097  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000b09c  nop
0x14000b09d  add     rsp, 48h
0x14000b0a1  retn
```
