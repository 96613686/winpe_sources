# initialize_msvcrt_compatibility

- ea: `0x180004520`
- end: `0x18000453d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800044f4`
- `0x180004504`

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
0x180004520  sub     rsp, 28h
0x180004524  call    __local_stdio_printf_options
0x180004529  or      qword ptr [rax], 18h
0x18000452d  call    __local_stdio_scanf_options
0x180004532  or      qword ptr [rax], 4
0x180004536  xor     eax, eax
0x180004538  add     rsp, 28h
0x18000453c  retn
```
