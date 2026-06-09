# _com_issue_error(long)

- ea: `0x140012ebc`
- end: `0x140012ecd`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `17`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010098`
- `0x140010384`

## callees

- `0x140012ff8`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error()
{
  _com_raise_error(-2147024882, 0);
}

```

## disassembly

```asm
0x140012ebc  sub     rsp, 28h
0x140012ec0  xor     edx, edx; struct IErrorInfo *
0x140012ec2  mov     ecx, 8007000Eh; int
0x140012ec7  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
