# CMSMQQuery::FinalConstruct(void)

- ea: `0x18000e748`
- end: `0x18000e770`
- name: `?FinalConstruct@CMSMQQuery@@QEAAJXZ`
- size: `40`
- prototype: `__int64 __fastcall(CMSMQQuery *__hidden this)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cce4`
- `0x18000cdcc`
- `0x18000d1bc`
- `0x18000d2a4`
- `0x18000d38c`
- `0x18000d474`
- `0x18000d55c`
- `0x18000d644`
- `0x18000d72c`
- `0x18000d814`
- `0x18000d8e4`
- `0x18000dc4c`
- `0x18000dd00`
- `0x18000ddd0`
- `0x18000de84`
- `0x18000df38`
- `0x18000dfec`
- `0x18000e0a0`
- `0x1800140bc`
- `0x18001aa00`
- `0x18001ccdc`
- `0x18001f53c`
- `0x180020a54`

## callees

- `0x180029010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e769`

## pseudocode

```c
HRESULT __fastcall CMSMQQuery::FinalConstruct(CMSMQQuery *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 72);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQQuery *))(*(_QWORD *)this + 32LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e748  push    rbx
0x18000e74a  sub     rsp, 20h
0x18000e74e  mov     rax, [rcx]
0x18000e751  lea     rbx, [rcx+48h]
0x18000e755  mov     rax, [rax+20h]
0x18000e759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e75e  mov     rcx, rax
0x18000e761  mov     rdx, rbx
0x18000e764  add     rsp, 20h
0x18000e768  pop     rbx
0x18000e769  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
