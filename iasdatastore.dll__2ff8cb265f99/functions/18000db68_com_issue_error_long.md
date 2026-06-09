# _com_issue_error(long)

- ea: `0x18000db68`
- end: `0x18000db74`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007370`
- `0x180007460`
- `0x18000750c`
- `0x180007628`
- `0x18000774c`
- `0x180007770`
- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`
- `0x180008ce4`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x18000dc14`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x18000db68  sub     rsp, 28h
0x18000db6c  xor     edx, edx; struct IErrorInfo *
0x18000db6e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
