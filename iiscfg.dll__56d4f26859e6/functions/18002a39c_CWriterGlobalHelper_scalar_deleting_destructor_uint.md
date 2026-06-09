# CWriterGlobalHelper::`scalar deleting destructor'(uint)

- ea: `0x18002a39c`
- end: `0x18002a3bc`
- name: `??_GCWriterGlobalHelper@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CWriterGlobalHelper *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002a2fc`
- `0x18002a6f0`

## callees

- `0x18002bf8c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a3ad`
- `ole32!CoTaskMemFree` at `0x18002a3ad`

## pseudocode

```c
CWriterGlobalHelper *__fastcall CWriterGlobalHelper::`scalar deleting destructor'(CWriterGlobalHelper *this)
{
  CWriterGlobalHelper::~CWriterGlobalHelper(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18002a39c  push    rbx
0x18002a39e  sub     rsp, 20h
0x18002a3a2  mov     rbx, rcx
0x18002a3a5  call    ??1CWriterGlobalHelper@@QEAA@XZ; CWriterGlobalHelper::~CWriterGlobalHelper(void)
0x18002a3aa  mov     rcx, rbx; pv
0x18002a3ad  call    cs:__imp_CoTaskMemFree
0x18002a3b3  mov     rax, rbx
0x18002a3b6  add     rsp, 20h
0x18002a3ba  pop     rbx
0x18002a3bb  retn
```
