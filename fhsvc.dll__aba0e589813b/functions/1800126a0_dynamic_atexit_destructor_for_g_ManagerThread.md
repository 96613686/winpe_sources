# _dynamic_atexit_destructor_for__g_ManagerThread__

- ea: `0x1800126a0`
- end: `0x1800126ac`
- name: `_dynamic_atexit_destructor_for__g_ManagerThread__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007cb0`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ManagerThread__()
{
  CManagerThread::~CManagerThread((CManagerThread *)&g_ManagerThread);
}

```

## disassembly

```asm
0x1800126a0  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; this
0x1800126a7  jmp     ??1CManagerThread@@QEAA@XZ; CManagerThread::~CManagerThread(void)
```
