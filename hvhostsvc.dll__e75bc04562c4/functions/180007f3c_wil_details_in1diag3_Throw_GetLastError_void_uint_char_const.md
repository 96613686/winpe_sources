# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x180007f3c`
- end: `0x180007f50`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ebc`
- `0x180007594`
- `0x180007b7c`
- `0x1800084f4`

## callees

- `0x180006608`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>((int)this, (int)a2, a3, (int)a4, v4, retaddr);
}

```

## disassembly

```asm
0x180007f3c  sub     rsp, 38h
0x180007f40  mov     rax, [rsp+38h]
0x180007f45  mov     [rsp+38h+var_10], rax; char *
0x180007f4a  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
