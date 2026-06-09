# _com_issue_error(long)

- ea: `0x1800137b0`
- end: `0x1800137ba`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002280`
- `0x180002428`
- `0x180016bac`
- `0x180016cd0`
- `0x180016d70`

## callees

- `0x1800137c0`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x1800137b0  sub     rsp, 28h
0x1800137b4  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
