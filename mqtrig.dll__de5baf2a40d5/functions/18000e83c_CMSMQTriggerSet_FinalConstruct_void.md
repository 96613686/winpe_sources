# CMSMQTriggerSet::FinalConstruct(void)

- ea: `0x18000e83c`
- end: `0x18000e867`
- name: `?FinalConstruct@CMSMQTriggerSet@@QEAAJXZ`
- size: `43`
- prototype: `HRESULT __fastcall(CMSMQTriggerSet *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e0e4`
- `0x18000e488`

## callees

- `0x180022010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e860`

## pseudocode

```c
HRESULT __fastcall CMSMQTriggerSet::FinalConstruct(CMSMQTriggerSet *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 1184);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQTriggerSet *))(*(_QWORD *)this + 32LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e83c  push    rbx
0x18000e83e  sub     rsp, 20h
0x18000e842  mov     rax, [rcx]
0x18000e845  lea     rbx, [rcx+4A0h]
0x18000e84c  mov     rax, [rax+20h]
0x18000e850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e855  mov     rcx, rax
0x18000e858  mov     rdx, rbx
0x18000e85b  add     rsp, 20h
0x18000e85f  pop     rbx
0x18000e860  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
