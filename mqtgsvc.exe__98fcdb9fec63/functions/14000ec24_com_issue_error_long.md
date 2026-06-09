# _com_issue_error(long)

- ea: `0x14000ec24`
- end: `0x14000ec30`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `12`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003058`
- `0x1400030ac`
- `0x140003104`
- `0x140003148`
- `0x1400031a0`
- `0x1400035a0`
- `0x140003dc8`
- `0x1400078d4`
- `0x140007dbc`
- `0x140007f4c`
- `0x1400080f0`
- `0x1400096ac`
- `0x140009994`
- `0x14000d110`
- `0x14000d4a8`
- `0x14000d648`
- `0x14000e6d4`

## callees

- `0x14000ecd0`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x14000ec24  sub     rsp, 28h
0x14000ec28  xor     edx, edx; struct IErrorInfo *
0x14000ec2a  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
