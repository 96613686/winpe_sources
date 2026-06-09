# CMSMQRuleHandler::FinalConstruct(void)

- ea: `0x18000e80c`
- end: `0x18000e834`
- name: `?FinalConstruct@CMSMQRuleHandler@@QEAAJXZ`
- size: `40`
- prototype: `HRESULT __fastcall(CMSMQRuleHandler *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000dffc`
- `0x18000e2a0`

## callees

- `0x180022010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e82d`

## pseudocode

```c
HRESULT __fastcall CMSMQRuleHandler::FinalConstruct(CMSMQRuleHandler *this)
{
  LPUNKNOWN *v1; // rbx
  IUnknown *v2; // rax

  v1 = (LPUNKNOWN *)((char *)this + 72);
  v2 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQRuleHandler *))(*(_QWORD *)this + 32LL))(this);
  return CoCreateFreeThreadedMarshaler(v2, v1);
}

```

## disassembly

```asm
0x18000e80c  push    rbx
0x18000e80e  sub     rsp, 20h
0x18000e812  mov     rax, [rcx]
0x18000e815  lea     rbx, [rcx+48h]
0x18000e819  mov     rax, [rax+20h]
0x18000e81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e822  mov     rcx, rax
0x18000e825  mov     rdx, rbx
0x18000e828  add     rsp, 20h
0x18000e82c  pop     rbx
0x18000e82d  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
