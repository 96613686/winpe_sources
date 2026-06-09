# _dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__

- ea: `0x1800014c0`
- end: `0x1800014d5`
- name: `_dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__`
- size: `21`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004f8c`

## pseudocode

```c
__int64 *dynamic_initializer_for__Microsoft::WRL::Module_1_Windows::Internal::ServiceModule_::isInitialized__()
{
  __int64 *result; // rax

  result = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create();
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x1800014c0  sub     rsp, 28h
0x1800014c4  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x1800014c9  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 1; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x1800014d0  add     rsp, 28h
0x1800014d4  retn
```
