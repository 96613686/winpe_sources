# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___

- ea: `0x1800169e0`
- end: `0x180016a11`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800169e0`
- `0x180017010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_HgServiceModule_1_int_::instance___()
{
  __int64 result; // rax

  if ( byte_1800205E8 )
  {
    result = ((__int64 (__fastcall *)(void *, _QWORD))*Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_)(
               &Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_,
               0);
    byte_1800205E8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800169e0  sub     rsp, 28h
0x1800169e4  cmp     cs:byte_1800205E8, 0
0x1800169eb  jz      short loc_180016A0C
0x1800169ed  mov     rax, cs:?instance_@?$StaticStorage@VHgServiceModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_
0x1800169f4  lea     rcx, ?instance_@?$StaticStorage@VHgServiceModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int> Microsoft::WRL::Details::StaticStorage<HgServiceModule,1,int>::instance_
0x1800169fb  xor     edx, edx
0x1800169fd  mov     rax, [rax]
0x180016a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a05  mov     cs:byte_1800205E8, 0
0x180016a0c  add     rsp, 28h
0x180016a10  retn
```
