# initialize_msvcrt_compatibility

- ea: `0x1800036f0`
- end: `0x18000370d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800036c4`
- `0x1800036d4`

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
0x1800036f0  sub     rsp, 28h
0x1800036f4  call    __local_stdio_printf_options
0x1800036f9  or      qword ptr [rax], 18h
0x1800036fd  call    __local_stdio_scanf_options
0x180003702  or      qword ptr [rax], 4
0x180003706  xor     eax, eax
0x180003708  add     rsp, 28h
0x18000370c  retn
```
