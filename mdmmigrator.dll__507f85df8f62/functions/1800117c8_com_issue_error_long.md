# _com_issue_error(long)

- ea: `0x1800117c8`
- end: `0x1800117d4`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aa2c`
- `0x18000ac08`
- `0x180012ed4`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001b094`
- `0x18001e79c`

## callees

- `0x1800118f8`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x1800117c8  sub     rsp, 28h
0x1800117cc  xor     edx, edx; struct IErrorInfo *
0x1800117ce  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
