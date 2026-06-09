# _dynamic_atexit_destructor_for__TagEntries__

- ea: `0x180024c70`
- end: `0x180024c8c`
- name: `_dynamic_atexit_destructor_for__TagEntries__`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800145b0`

## pseudocode

```c
void dynamic_atexit_destructor_for__TagEntries__()
{
  `eh vector destructor iterator'(&TagEntries, 0xB8u, 0x5Au, (void (*)(void *))CTagEntry::~CTagEntry);
}

```

## disassembly

```asm
0x180024c70  mov     edx, 0B8h; unsigned __int64
0x180024c75  lea     r9, ??1CTagEntry@@QEAA@XZ; void (*)(void *)
0x180024c7c  lea     rcx, ?TagEntries@@3PAVCTagEntry@@A; void *
0x180024c83  lea     r8d, [rdx-5Eh]; unsigned __int64
0x180024c87  jmp     ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
```
