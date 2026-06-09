# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800066e4`
- end: `0x180006702`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `147`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021dc`
- `0x180002244`
- `0x18000230c`
- `0x18000237c`
- `0x1800023f0`
- `0x1800024a8`
- `0x180002524`
- `0x1800025a0`
- `0x180002608`
- `0x180002670`
- `0x1800026e0`
- `0x180002748`
- `0x180002814`
- `0x180002884`
- `0x1800028f4`
- `0x180002970`
- `0x180002a18`
- `0x180002a98`
- `0x180002b20`
- `0x180002be8`
- `0x180002c50`
- `0x180002cb8`
- `0x180002d20`
- `0x180002d88`
- `0x180002e04`
- `0x180002e8c`
- `0x180002efc`
- `0x180003fd0`
- `0x1800044b0`
- `0x180004650`
- `0x180005224`
- `0x180005540`
- `0x180005788`
- `0x18000639c`
- `0x180006b70`
- `0x180007090`
- `0x180007100`
- `0x1800071d0`
- `0x1800072b0`
- `0x180007350`
- `0x180007400`
- `0x180007490`
- `0x180007610`
- `0x1800079d0`
- `0x180007d00`
- `0x180007ed0`
- `0x180007f20`
- `0x180008060`
- `0x180008150`
- `0x1800081c0`

## callees

- `0x180003104`

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
0x1800066e4  sub     rsp, 48h
0x1800066e8  mov     rax, [rsp+48h]
0x1800066ed  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800066f2  mov     [rsp+48h+var_20], rax; __int64
0x1800066f7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800066fc  nop
0x1800066fd  add     rsp, 48h
0x180006701  retn
```
