# __unlock

- ea: `0x10034fde`
- end: `0x10034ff3`
- name: `__unlock`
- size: `21`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x1002e746`
- `0x1002eac8`
- `0x1002eb6e`
- `0x1002ef30`
- `0x1002f122`
- `0x10032330`
- `0x10033cee`
- `0x10033cf7`
- `0x100344f8`
- `0x10034efc`
- `0x100372f3`
- `0x1003732d`
- `0x1003a31c`
- `0x1003b9aa`
- `0x1003bafa`
- `0x1003bbde`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10034feb`
- `KERNEL32!LeaveCriticalSection` at `0x10034feb`

## pseudocode

```c
void __cdecl _unlock(int a1)
{
  LeaveCriticalSection(*(&lpCriticalSection + 2 * a1));
}

```

## disassembly

```asm
0x10034fde  push    ebp
0x10034fdf  mov     ebp, esp
0x10034fe1  mov     eax, [ebp+arg_0]
0x10034fe4  push    lpCriticalSection[eax*8]; lpCriticalSection
0x10034feb  call    ds:__imp__LeaveCriticalSection@4
0x10034ff1  pop     ebp
0x10034ff2  retn
```
