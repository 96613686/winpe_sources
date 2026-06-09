# _dynamic_initializer_for__sPwrshCommon__

- ea: `0x180001070`
- end: `0x180001090`
- name: `_dynamic_initializer_for__sPwrshCommon__`
- size: `32`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800019f8`
- `0x180007428`

## pseudocode

```c
int dynamic_initializer_for__sPwrshCommon__()
{
  NativeMsh::PwrshCommon::PwrshCommon((NativeMsh::PwrshCommon *)qword_180014CA8);
  return atexit(dynamic_atexit_destructor_for__sPwrshCommon__);
}

```

## disassembly

```asm
0x180001070  sub     rsp, 28h
0x180001074  lea     rcx, qword_180014CA8; this
0x18000107b  call    ??0PwrshCommon@NativeMsh@@QEAA@XZ; NativeMsh::PwrshCommon::PwrshCommon(void)
0x180001080  lea     rcx, _dynamic_atexit_destructor_for__sPwrshCommon__
0x180001087  add     rsp, 28h
0x18000108b  jmp     atexit
```
