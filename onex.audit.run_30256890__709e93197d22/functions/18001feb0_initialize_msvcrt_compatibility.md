# initialize_msvcrt_compatibility

- ea: `0x18001feb0`
- end: `0x18001fecd`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001fe84`
- `0x18001fe94`

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
0x18001feb0  sub     rsp, 28h
0x18001feb4  call    __local_stdio_printf_options
0x18001feb9  or      qword ptr [rax], 18h
0x18001febd  call    __local_stdio_scanf_options
0x18001fec2  or      qword ptr [rax], 4
0x18001fec6  xor     eax, eax
0x18001fec8  add     rsp, 28h
0x18001fecc  retn
```
