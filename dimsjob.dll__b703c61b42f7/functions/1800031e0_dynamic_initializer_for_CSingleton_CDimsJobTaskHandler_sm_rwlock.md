# _dynamic_initializer_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__

- ea: `0x1800031e0`
- end: `0x180003201`
- name: `_dynamic_initializer_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__`
- size: `33`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004980`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x1800031eb`
- `ntdll!RtlInitializeSRWLock` at `0x1800031eb`

## pseudocode

```c
int dynamic_initializer_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__()
{
  RtlInitializeSRWLock(&qword_180011050);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CSingleton_CDimsJobTaskHandler_::sm_rwlock__);
}

```

## disassembly

```asm
0x1800031e0  sub     rsp, 28h
0x1800031e4  lea     rcx, qword_180011050
0x1800031eb  call    cs:__imp_RtlInitializeSRWLock
0x1800031f1  lea     rcx, _dynamic_atexit_destructor_for__CSingleton_CDimsJobTaskHandler___sm_rwlock__
0x1800031f8  add     rsp, 28h
0x1800031fc  jmp     atexit
```
