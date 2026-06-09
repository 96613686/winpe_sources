# CIISGlobalModule::Terminate(void)

- ea: `0x1800031e0`
- end: `0x1800031fb`
- name: `?Terminate@CIISGlobalModule@@UEAAXXZ`
- size: `27`
- prototype: `void __fastcall(CIISGlobalModule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001048`
- `0x180003204`

## pseudocode

```c
void __fastcall CIISGlobalModule::Terminate(CIISGlobalModule *this)
{
  ETW_TRACE_HANDLER::Terminate();
  operator delete(this);
}

```

## disassembly

```asm
0x1800031e0  push    rbx
0x1800031e2  sub     rsp, 20h
0x1800031e6  mov     rbx, rcx
0x1800031e9  call    ?Terminate@ETW_TRACE_HANDLER@@SAXXZ
0x1800031ee  mov     rcx, rbx; Block
0x1800031f1  add     rsp, 20h
0x1800031f5  pop     rbx
0x1800031f6  jmp     ??3@YAXPEAX@Z
```
