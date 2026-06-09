# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x14000b470`
- end: `0x14000b49a`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b968`
- `0x14000c500`
- `0x14000c88c`
- `0x140010384`
- `0x1400111bc`
- `0x140011bb0`

## callees

- `0x1400039d4`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, __int64 a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((__int64)this, a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x14000b470  sub     rsp, 48h
0x14000b474  mov     rax, [rsp+48h]
0x14000b479  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000b47e  mov     [rsp+48h+var_20], rax; __int64
0x14000b483  mov     [rsp+48h+var_28], 0; __int64
0x14000b48c  xor     r9d, r9d; int
0x14000b48f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000b494  nop
0x14000b495  add     rsp, 48h
0x14000b499  retn
```
