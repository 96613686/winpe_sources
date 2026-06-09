# DecMemFreeFn

- ea: `0x180001b10`
- end: `0x180001b21`
- name: `DecMemFreeFn`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030d0`
- `0x1800051a0`
- `0x180009c10`

## callees

- `0x180001b10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b19`

## pseudocode

```c
HLOCAL __fastcall DecMemFreeFn(__int64 a1, void *a2)
{
  HLOCAL result; // rax

  if ( !*(_DWORD *)(a1 + 76) )
    return LocalFree(a2);
  return result;
}

```

## disassembly

```asm
0x180001b10  cmp     dword ptr [rcx+4Ch], 0
0x180001b14  jnz     short locret_180001B20
0x180001b16  mov     rcx, rdx
0x180001b19  jmp     cs:__imp_LocalFree
0x180001b20  retn
```
