# initialize_msvcrt_compatibility

- ea: `0x180009c10`
- end: `0x180009c2d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009be4`
- `0x180009bf4`

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
0x180009c10  sub     rsp, 28h
0x180009c14  call    __local_stdio_printf_options
0x180009c19  or      qword ptr [rax], 18h
0x180009c1d  call    __local_stdio_scanf_options
0x180009c22  or      qword ptr [rax], 4
0x180009c26  xor     eax, eax
0x180009c28  add     rsp, 28h
0x180009c2c  retn
```
