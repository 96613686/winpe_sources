# _dynamic_atexit_destructor_for__sPwrshCommon__

- ea: `0x18000a150`
- end: `0x18000a15c`
- name: `_dynamic_atexit_destructor_for__sPwrshCommon__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007730`

## pseudocode

```c
void dynamic_atexit_destructor_for__sPwrshCommon__()
{
  NativeMsh::PwrshCommon::~PwrshCommon((NativeMsh::PwrshCommon *)qword_180014CA8);
}

```

## disassembly

```asm
0x18000a150  lea     rcx, qword_180014CA8; this
0x18000a157  jmp     ??1PwrshCommon@NativeMsh@@QEAA@XZ; NativeMsh::PwrshCommon::~PwrshCommon(void)
```
