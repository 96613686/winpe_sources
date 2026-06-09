# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000af78`
- end: `0x18000af96`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ee0`
- `0x18000804c`
- `0x180008218`
- `0x1800087c0`
- `0x180008c6c`
- `0x180008f44`
- `0x1800097dc`
- `0x18000990c`
- `0x18000a094`
- `0x18000b384`
- `0x18000b990`
- `0x18000bab4`
- `0x18000bb38`

## callees

- `0x180006af8`

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
0x18000af78  sub     rsp, 48h
0x18000af7c  mov     rax, [rsp+48h]
0x18000af81  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000af86  mov     [rsp+48h+var_20], rax; __int64
0x18000af8b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000af90  nop
0x18000af91  add     rsp, 48h
0x18000af95  retn
```
