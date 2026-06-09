# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180004a84`
- end: `0x180004aa2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003068`
- `0x180003438`
- `0x180003ff4`
- `0x18000555c`
- `0x18001176c`
- `0x180012444`

## callees

- `0x1800024c4`

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
0x180004a84  sub     rsp, 48h
0x180004a88  mov     rax, [rsp+48h]
0x180004a8d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180004a92  mov     [rsp+48h+var_20], rax; __int64
0x180004a97  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004a9c  nop
0x180004a9d  add     rsp, 48h
0x180004aa1  retn
```
