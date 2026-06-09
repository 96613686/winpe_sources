# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___

- ea: `0x180011540`
- end: `0x18001154c`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800042dc`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___()
{
  return Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::~StaticStorage<Windows::Internal::ServiceModule,1,int>((__int64)&Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_);
}

```

## disassembly

```asm
0x180011540  lea     rcx, ?instance_@?$StaticStorage@VServiceModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::instance_
0x180011547  jmp     ??1?$StaticStorage@VServiceModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::StaticStorage<Windows::Internal::ServiceModule,1,int>::~StaticStorage<Windows::Internal::ServiceModule,1,int>(void)
```
