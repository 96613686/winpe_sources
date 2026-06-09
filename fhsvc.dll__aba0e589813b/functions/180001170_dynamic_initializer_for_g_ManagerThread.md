# _dynamic_initializer_for__g_ManagerThread__

- ea: `0x180001170`
- end: `0x180001189`
- name: `_dynamic_initializer_for__g_ManagerThread__`
- size: `25`
- prototype: `int __fastcall(CManagerThread *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009990`
- `0x18000d1e8`

## pseudocode

```c
int __fastcall dynamic_initializer_for__g_ManagerThread__(CManagerThread *a1)
{
  CManagerThread::CManagerThread(a1);
  return atexit(dynamic_atexit_destructor_for__g_ManagerThread__);
}

```

## disassembly

```asm
0x180001170  sub     rsp, 28h
0x180001174  call    ??0CManagerThread@@QEAA@XZ; CManagerThread::CManagerThread(void)
0x180001179  lea     rcx, _dynamic_atexit_destructor_for__g_ManagerThread__
0x180001180  add     rsp, 28h
0x180001184  jmp     atexit
```
