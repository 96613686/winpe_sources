# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___

- ea: `0x1800169a0`
- end: `0x1800169d1`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800169a0`
- `0x180017010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_HgServiceModule_::GenericReleaseNotifier__lambda_0f77b13830ba1ec030a3cf008c830582____2_HgServiceModule_::instance___()
{
  __int64 result; // rax

  if ( byte_180020608 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))qword_1800205F0)(&qword_1800205F0, 0);
    byte_180020608 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800169a0  sub     rsp, 28h
0x1800169a4  cmp     cs:byte_180020608, 0
0x1800169ab  jz      short loc_1800169CC
0x1800169ad  mov     rax, cs:qword_1800205F0
0x1800169b4  lea     rcx, qword_1800205F0
0x1800169bb  xor     edx, edx
0x1800169bd  mov     rax, [rax]
0x1800169c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169c5  mov     cs:byte_180020608, 0
0x1800169cc  add     rsp, 28h
0x1800169d0  retn
```
