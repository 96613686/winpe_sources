# abort

- ea: `0x1800fbfce`
- end: `0x1800fbfd4`
- name: `abort`
- size: `6`
- prototype: `void __cdecl __noreturn()`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1800cce18`
- `0x1800cd4fc`
- `0x1800cd960`
- `0x1800cdda8`
- `0x1800cdff4`
- `0x1800ce130`
- `0x1800ce300`
- `0x1800ce4d0`
- `0x1800ce590`
- `0x1800ce818`
- `0x1800cecd4`
- `0x1800cf1f0`
- `0x1800cf430`
- `0x1800cf964`
- `0x1800cfb78`
- `0x1800d02b0`
- `0x1800d0770`
- `0x1800d0914`
- `0x1800d0cc0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800fbfce`

## pseudocode

```c
// attributes: thunk
void __cdecl __noreturn abort()
{
  __imp_abort();
}

```

## disassembly

```asm
0x1800fbfce  jmp     cs:__imp_abort
```
