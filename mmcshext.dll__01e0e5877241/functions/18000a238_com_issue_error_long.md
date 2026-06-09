# _com_issue_error(long)

- ea: `0x18000a238`
- end: `0x18000a242`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007fc0`
- `0x1800083b8`
- `0x1800097e8`
- `0x180009878`
- `0x180009908`

## callees

- `0x18000a360`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x18000a238  sub     rsp, 28h
0x18000a23c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
