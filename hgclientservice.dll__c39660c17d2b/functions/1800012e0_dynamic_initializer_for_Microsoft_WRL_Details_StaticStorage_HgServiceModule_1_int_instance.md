# _dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___

- ea: `0x1800012e0`
- end: `0x1800012ec`
- name: `_dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001b88`

## pseudocode

```c
int dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___);
}

```

## disassembly

```asm
0x1800012e0  lea     rcx, _dynamic_atexit_destructor_for__Microsoft__WRL__Details__StaticStorage_HgServiceModule_1_int___instance___
0x1800012e7  jmp     atexit
```
