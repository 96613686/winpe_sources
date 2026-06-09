# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180003290`
- end: `0x1800032ae`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a70`
- `0x180001c20`
- `0x180002ad0`
- `0x180002f50`
- `0x180003030`
- `0x180006858`
- `0x180006a34`
- `0x18000738c`
- `0x180007534`
- `0x180008138`
- `0x18000a540`

## callees

- `0x180003360`

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
0x180003290  sub     rsp, 48h
0x180003294  mov     rax, [rsp+48h]
0x180003299  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000329e  mov     [rsp+48h+var_20], rax; __int64
0x1800032a3  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800032a8  nop
0x1800032a9  add     rsp, 48h
0x1800032ad  retn
```
