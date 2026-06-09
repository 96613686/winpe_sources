# _dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___

- ea: `0x1800012c0`
- end: `0x1800012cc`
- name: `_dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001b88`

## pseudocode

```c
int dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___);
}

```

## disassembly

```asm
0x1800012c0  lea     rcx, _dynamic_atexit_destructor_for__Microsoft__WRL__Details__StaticStorage_Microsoft__WRL__Details__OutOfProcModuleBase_HgServiceModule___GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule___instance___
0x1800012c7  jmp     atexit
```
