# _com_issue_error(long)

- ea: `0x14002c070`
- end: `0x14002c07c`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018d0c`
- `0x1400196f4`
- `0x140019a5c`
- `0x140019af4`
- `0x14001a28c`
- `0x14001b3f0`
- `0x14001b9fc`
- `0x140027410`
- `0x140027534`
- `0x14002774c`
- `0x140027d80`
- `0x140027f04`
- `0x140028040`
- `0x14002ac64`
- `0x14002ad94`
- `0x14002ae28`
- `0x14002aebc`

## callees

- `0x14002c238`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x14002c070  sub     rsp, 28h
0x14002c074  xor     edx, edx; struct IErrorInfo *
0x14002c076  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
