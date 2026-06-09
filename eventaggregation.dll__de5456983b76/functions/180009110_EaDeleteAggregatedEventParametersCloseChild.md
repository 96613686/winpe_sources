# EaDeleteAggregatedEventParametersCloseChild

- ea: `0x180009110`
- end: `0x180009125`
- name: `EaDeleteAggregatedEventParametersCloseChild`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009110`

## import_xrefs

- `ntdll!ZwClose` at `0x18000911e`

## pseudocode

```c
NTSTATUS __fastcall EaDeleteAggregatedEventParametersCloseChild(__int64 a1, void *a2)
{
  if ( a2 )
    return ZwClose(a2);
  else
    return -1073741811;
}

```

## disassembly

```asm
0x180009110  test    rdx, rdx
0x180009113  jnz     short loc_18000911B
0x180009115  mov     eax, 0C000000Dh
0x18000911a  retn
0x18000911b  mov     rcx, rdx
0x18000911e  jmp     cs:__imp_ZwClose
```
