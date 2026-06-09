# CMemoryTable::`scalar deleting destructor'(uint)

- ea: `0x180001fe8`
- end: `0x180002008`
- name: `??_GCMemoryTable@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CMemoryTable *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800024b0`
- `0x180010e30`

## callees

- `0x18000e2a0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001ff9`
- `ole32!CoTaskMemFree` at `0x180001ff9`

## pseudocode

```c
CMemoryTable *__fastcall CMemoryTable::`scalar deleting destructor'(CMemoryTable *this)
{
  CMemoryTable::~CMemoryTable(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180001fe8  push    rbx
0x180001fea  sub     rsp, 20h
0x180001fee  mov     rbx, rcx
0x180001ff1  call    ??1CMemoryTable@@QEAA@XZ; CMemoryTable::~CMemoryTable(void)
0x180001ff6  mov     rcx, rbx; pv
0x180001ff9  call    cs:__imp_CoTaskMemFree
0x180001fff  mov     rax, rbx
0x180002002  add     rsp, 20h
0x180002006  pop     rbx
0x180002007  retn
```
