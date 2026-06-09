# _com_issue_error(long)

- ea: `0x180017020`
- end: `0x18001702a`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004784`

## callees

- `0x180017150`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(__int64 a1, struct IErrorInfo *a2, struct IErrorInfo *a3, bool a4)
{
  _com_raise_error(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180017020  sub     rsp, 28h
0x180017024  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
