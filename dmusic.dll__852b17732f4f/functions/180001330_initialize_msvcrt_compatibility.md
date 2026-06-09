# initialize_msvcrt_compatibility

- ea: `0x180001330`
- end: `0x18000134d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001304`
- `0x180001314`

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
0x180001330  sub     rsp, 28h
0x180001334  call    __local_stdio_printf_options
0x180001339  or      qword ptr [rax], 18h
0x18000133d  call    __local_stdio_scanf_options
0x180001342  or      qword ptr [rax], 4
0x180001346  xor     eax, eax
0x180001348  add     rsp, 28h
0x18000134c  retn
```
