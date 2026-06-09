# CMSMQManagement::FinalConstruct(void)

- ea: `0x18000e7a8`
- end: `0x18000e7d0`
- name: `?FinalConstruct@CMSMQManagement@@QEAAJXZ`
- size: `40`
- prototype: `__int64 __fastcall(CMSMQManagement *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d0c0`
- `0x18000db68`

## callees

- `0x180029010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e7c9`

## pseudocode

```c
HRESULT __fastcall CMSMQManagement::FinalConstruct(CMSMQManagement *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 88);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQManagement *))(*(_QWORD *)this + 40LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e7a8  push    rbx
0x18000e7aa  sub     rsp, 20h
0x18000e7ae  mov     rax, [rcx]
0x18000e7b1  lea     rbx, [rcx+58h]
0x18000e7b5  mov     rax, [rax+28h]
0x18000e7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7be  mov     rcx, rax
0x18000e7c1  mov     rdx, rbx
0x18000e7c4  add     rsp, 20h
0x18000e7c8  pop     rbx
0x18000e7c9  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
