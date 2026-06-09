# __scrt_initialize_default_local_stdio_options

- ea: `0x14000172c`
- end: `0x140001747`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001190`

## callees

- `0x140001084`
- `0x140001094`

## pseudocode

```c
unsigned __int64 *_scrt_initialize_default_local_stdio_options()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *result; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x24u;
  result = _local_stdio_scanf_options();
  *result |= 2u;
  return result;
}

```

## disassembly

```asm
0x14000172c  sub     rsp, 28h
0x140001730  call    __local_stdio_printf_options
0x140001735  or      qword ptr [rax], 24h
0x140001739  call    __local_stdio_scanf_options
0x14000173e  or      qword ptr [rax], 2
0x140001742  add     rsp, 28h
0x140001746  retn
```
