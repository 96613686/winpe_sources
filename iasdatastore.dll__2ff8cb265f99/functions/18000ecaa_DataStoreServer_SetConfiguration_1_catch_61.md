# _DataStoreServer::SetConfiguration_::_1_::catch$61

- ea: `0x18000ecaa`
- end: `0x18000ecf5`
- name: `_DataStoreServer::SetConfiguration_::_1_::catch$61`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800020a5`
- `0x180007840`
- `0x18000be0c`
- `0x18000d94c`
- `0x180010010`

## pseudocode

```c
void __noreturn DataStoreServer::SetConfiguration_::_1_::catch_61()
{
  IASTraceExcept();
}

```

## disassembly

```asm
0x18000ecaa  mov     [rsp+arg_8], rdx
0x18000ecaf  push    rbx
0x18000ecb0  push    rbp
0x18000ecb1  sub     rsp, 38h
0x18000ecb5  mov     rbp, rdx
0x18000ecb8  call    IASTraceExcept
0x18000ecbd  mov     rbx, [rbp+0F0h]
0x18000ecc4  lea     rcx, [rbx+880h]
0x18000eccb  call    ??C?$auto_xxx@PEAUIIASVssWriter@@P6AXPEAU1@@Z$1??$_delete@UIIASVssWriter@@@nap@@YAX0@Z$0A@Vno_copy@2@@nap@@QEBAPEAUIIASVssWriter@@XZ; nap::auto_xxx<IIASVssWriter *,void (*)(IIASVssWriter *),&nap::_delete<IIASVssWriter>(IIASVssWriter *),0,nap::no_copy>::operator->(void)
0x18000ecd0  mov     rdx, rax
0x18000ecd3  mov     rcx, [rax]
0x18000ecd6  mov     rax, [rcx+18h]
0x18000ecda  mov     rcx, rdx
0x18000ecdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece2  lea     rcx, [rbx+8]; lpCriticalSection
0x18000ece6  call    ?Unlock@Guardable@@QEBAXXZ; Guardable::Unlock(void)
0x18000eceb  xor     edx, edx; pThrowInfo
0x18000eced  xor     ecx, ecx; pExceptionObject
0x18000ecef  call    _CxxThrowException_0
```
