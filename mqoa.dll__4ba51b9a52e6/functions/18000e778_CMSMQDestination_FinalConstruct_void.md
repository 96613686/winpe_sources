# CMSMQDestination::FinalConstruct(void)

- ea: `0x18000e778`
- end: `0x18000e7a0`
- name: `?FinalConstruct@CMSMQDestination@@QEAAJXZ`
- size: `40`
- prototype: `__int64 __fastcall(CMSMQDestination *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ceb4`
- `0x18000d9b4`
- `0x18001401c`

## callees

- `0x180029010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e799`

## pseudocode

```c
HRESULT __fastcall CMSMQDestination::FinalConstruct(CMSMQDestination *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 80);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQDestination *))(*(_QWORD *)this + 32LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e778  push    rbx
0x18000e77a  sub     rsp, 20h
0x18000e77e  mov     rax, [rcx]
0x18000e781  lea     rbx, [rcx+50h]
0x18000e785  mov     rax, [rax+20h]
0x18000e789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e78e  mov     rcx, rax
0x18000e791  mov     rdx, rbx
0x18000e794  add     rsp, 20h
0x18000e798  pop     rbx
0x18000e799  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
