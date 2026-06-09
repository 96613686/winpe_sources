# _dynamic_atexit_destructor_for__g_ohThread__

- ea: `0x140009a40`
- end: `0x140009a4c`
- name: `_dynamic_atexit_destructor_for__g_ohThread__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003be0`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ohThread__()
{
  CHandle::~CHandle((CHandle *)&g_ohThread);
}

```

## disassembly

```asm
0x140009a40  lea     rcx, ?g_ohThread@@3VCHandle@@A; this
0x140009a47  jmp     ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
```
