# _com_issue_error(long)

- ea: `0x180014920`
- end: `0x18001492a`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005290`
- `0x180005358`
- `0x1800053ac`
- `0x18000544c`
- `0x1800054a4`
- `0x1800056c8`
- `0x1800057c8`
- `0x180005d74`
- `0x180014930`
- `0x18001f159`

## callees

- `0x180014a98`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1, struct IErrorInfo *a2)
{
  _com_raise_error(a1, a2);
}

```

## disassembly

```asm
0x180014920  sub     rsp, 28h
0x180014924  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
