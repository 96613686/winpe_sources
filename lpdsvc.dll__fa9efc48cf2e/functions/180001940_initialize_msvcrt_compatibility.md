# initialize_msvcrt_compatibility

- ea: `0x180001940`
- end: `0x18000195d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001914`
- `0x180001924`

## pseudocode

```c
__int64 initialize_msvcrt_compatibility()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *v1; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x18u;
  v1 = _local_stdio_scanf_options();
  *v1 |= 4u;
  return 0;
}

```

## disassembly

```asm
0x180001940  sub     rsp, 28h
0x180001944  call    __local_stdio_printf_options
0x180001949  or      qword ptr [rax], 18h
0x18000194d  call    __local_stdio_scanf_options
0x180001952  or      qword ptr [rax], 4
0x180001956  xor     eax, eax
0x180001958  add     rsp, 28h
0x18000195c  retn
```
