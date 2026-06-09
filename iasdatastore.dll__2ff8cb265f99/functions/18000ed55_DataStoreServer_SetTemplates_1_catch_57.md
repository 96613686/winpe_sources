# _DataStoreServer::SetTemplates_::_1_::catch$57

- ea: `0x18000ed55`
- end: `0x18000eda0`
- name: `_DataStoreServer::SetTemplates_::_1_::catch$57`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800020a5`
- `0x180007840`
- `0x18000be0c`
- `0x18000d94c`
- `0x180010010`

## pseudocode

```c
void __noreturn DataStoreServer::SetTemplates_::_1_::catch_57()
{
  IASTraceExcept();
}

```

## disassembly

```asm
0x18000ed55  mov     [rsp+arg_8], rdx
0x18000ed5a  push    rbx
0x18000ed5b  push    rbp
0x18000ed5c  sub     rsp, 38h
0x18000ed60  mov     rbp, rdx
0x18000ed63  call    IASTraceExcept
0x18000ed68  mov     rbx, [rbp+0D0h]
0x18000ed6f  lea     rcx, [rbx+880h]
0x18000ed76  call    ??C?$auto_xxx@PEAUIIASVssWriter@@P6AXPEAU1@@Z$1??$_delete@UIIASVssWriter@@@nap@@YAX0@Z$0A@Vno_copy@2@@nap@@QEBAPEAUIIASVssWriter@@XZ; nap::auto_xxx<IIASVssWriter *,void (*)(IIASVssWriter *),&nap::_delete<IIASVssWriter>(IIASVssWriter *),0,nap::no_copy>::operator->(void)
0x18000ed7b  mov     rdx, rax
0x18000ed7e  mov     rcx, [rax]
0x18000ed81  mov     rax, [rcx+18h]
0x18000ed85  mov     rcx, rdx
0x18000ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed8d  lea     rcx, [rbx+8]; lpCriticalSection
0x18000ed91  call    ?Unlock@Guardable@@QEBAXXZ; Guardable::Unlock(void)
0x18000ed96  xor     edx, edx; pThrowInfo
0x18000ed98  xor     ecx, ecx; pExceptionObject
0x18000ed9a  call    _CxxThrowException_0
```
