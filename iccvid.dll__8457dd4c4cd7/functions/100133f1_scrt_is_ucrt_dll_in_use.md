# ___scrt_is_ucrt_dll_in_use

- ea: `0x100133f1`
- end: `0x100133fd`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x10012c9b`
- `0x10012cd5`
- `0x10012d4d`
- `0x10012d89`
- `0x10012e06`
- `0x10012f32`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return __scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x100133f1  xor     eax, eax
0x100133f3  cmp     ___scrt_ucrt_dll_is_in_use, eax
0x100133f9  setnz   al
0x100133fc  retn
```
