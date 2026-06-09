# CMSMQPropertyBag::FinalConstruct(void)

- ea: `0x18000e7dc`
- end: `0x18000e804`
- name: `?FinalConstruct@CMSMQPropertyBag@@QEAAJXZ`
- size: `40`
- prototype: `HRESULT __fastcall(CMSMQPropertyBag *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df28`
- `0x18000e1cc`

## callees

- `0x180022010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e7fd`

## pseudocode

```c
HRESULT __fastcall CMSMQPropertyBag::FinalConstruct(CMSMQPropertyBag *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 24);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQPropertyBag *))(*(_QWORD *)this + 32LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e7dc  push    rbx
0x18000e7de  sub     rsp, 20h
0x18000e7e2  mov     rax, [rcx]
0x18000e7e5  lea     rbx, [rcx+18h]
0x18000e7e9  mov     rax, [rax+20h]
0x18000e7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f2  mov     rcx, rax
0x18000e7f5  mov     rdx, rbx
0x18000e7f8  add     rsp, 20h
0x18000e7fc  pop     rbx
0x18000e7fd  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
