# initialize_msvcrt_compatibility

- ea: `0x10012780`
- end: `0x1001279f`
- name: `initialize_msvcrt_compatibility`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x10012765`
- `0x10012771`

## pseudocode

```c
int initialize_msvcrt_compatibility()
{
  unsigned __int64 *v0; // eax
  int v1; // ecx
  unsigned __int64 *v2; // eax
  int v3; // ecx

  v0 = __local_stdio_printf_options();
  v1 = *((_DWORD *)v0 + 1);
  *(_DWORD *)v0 |= 0x18u;
  *((_DWORD *)v0 + 1) = v1;
  v2 = __local_stdio_scanf_options();
  v3 = *((_DWORD *)v2 + 1);
  *(_DWORD *)v2 |= 4u;
  *((_DWORD *)v2 + 1) = v3;
  return 0;
}

```

## disassembly

```asm
0x10012780  call    ___local_stdio_printf_options
0x10012785  mov     ecx, [eax+4]
0x10012788  or      dword ptr [eax], 18h
0x1001278b  mov     [eax+4], ecx
0x1001278e  call    ___local_stdio_scanf_options
0x10012793  mov     ecx, [eax+4]
0x10012796  or      dword ptr [eax], 4
0x10012799  mov     [eax+4], ecx
0x1001279c  xor     eax, eax
0x1001279e  retn
```
