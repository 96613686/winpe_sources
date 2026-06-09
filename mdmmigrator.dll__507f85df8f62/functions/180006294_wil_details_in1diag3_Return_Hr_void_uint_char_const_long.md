# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006294`
- end: `0x1800062b2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046a8`
- `0x180004a78`
- `0x1800056f4`
- `0x180006d7c`
- `0x180012254`
- `0x180017558`
- `0x1800194bc`
- `0x18001b094`
- `0x18001c054`
- `0x18001c61c`

## callees

- `0x180003ab0`

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
0x180006294  sub     rsp, 48h
0x180006298  mov     rax, [rsp+48h]
0x18000629d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800062a2  mov     [rsp+48h+var_20], rax; __int64
0x1800062a7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800062ac  nop
0x1800062ad  add     rsp, 48h
0x1800062b1  retn
```
