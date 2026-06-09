# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800099f8`
- end: `0x180009a15`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003828`
- `0x180003bf8`
- `0x180004bb4`
- `0x180006350`
- `0x18000a47c`
- `0x180013ef8`
- `0x180014b78`

## callees

- `0x18000250c`

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
0x1800099f8  sub     rsp, 48h
0x1800099fc  mov     rax, [rsp+48h]
0x180009a01  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180009a06  mov     [rsp+48h+var_20], rax; __int64
0x180009a0b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009a10  add     rsp, 48h
0x180009a14  retn
```
