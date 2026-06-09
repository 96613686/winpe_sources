# terminate_0

- ea: `0x18000516a`
- end: `0x180005170`
- name: `terminate_0`
- size: `6`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002890`
- `0x180002978`
- `0x1800029e4`
- `0x1800033d8`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18000516a`

## pseudocode

```c
// attributes: thunk
void __noreturn terminate_0()
{
  terminate();
}

```

## disassembly

```asm
0x18000516a  jmp     cs:__imp_terminate
```
