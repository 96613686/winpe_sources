# initialize_msvcrt_compatibility

- ea: `0x10035140`
- end: `0x1003515f`
- name: `initialize_msvcrt_compatibility`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x10035125`
- `0x10035131`

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
0x10035140  call    ___local_stdio_printf_options
0x10035145  mov     ecx, [eax+4]
0x10035148  or      dword ptr [eax], 18h
0x1003514b  mov     [eax+4], ecx
0x1003514e  call    ___local_stdio_scanf_options
0x10035153  mov     ecx, [eax+4]
0x10035156  or      dword ptr [eax], 4
0x10035159  mov     [eax+4], ecx
0x1003515c  xor     eax, eax
0x1003515e  retn
```
