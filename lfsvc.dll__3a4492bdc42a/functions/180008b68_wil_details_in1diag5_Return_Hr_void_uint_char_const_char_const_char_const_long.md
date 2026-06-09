# wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)

- ea: `0x180008b68`
- end: `0x180008b93`
- name: `?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z`
- size: `43`
- prototype: `void __fastcall(wil::details::in1diag5 *this, void *, __int64, const char *, const char *, wil::details *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180006308`
- `0x180006498`
- `0x180006698`
- `0x180007374`
- `0x180007c9c`
- `0x180007df0`
- `0x180009758`
- `0x1800097f4`

## callees

- `0x18000503c`

## pseudocode

```c
void __fastcall wil::details::in1diag5::Return_Hr(
        wil::details::in1diag5 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        wil::details *a6)
{
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a6;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, retaddr, (int)a4, (__int64)a5, retaddr, v6);
}

```

## disassembly

```asm
0x180008b68  sub     rsp, 48h
0x180008b6c  mov     r8, [rsp+48h]; int
0x180008b71  mov     eax, dword ptr [rsp+48h+arg_28]
0x180008b75  mov     dword ptr [rsp+48h+var_18], eax; wil::details *
0x180008b79  mov     [rsp+48h+var_20], r8; __int64
0x180008b7e  mov     rax, [rsp+48h+arg_20]
0x180008b83  mov     [rsp+48h+var_28], rax; __int64
0x180008b88  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008b8d  nop
0x180008b8e  add     rsp, 48h
0x180008b92  retn
```
