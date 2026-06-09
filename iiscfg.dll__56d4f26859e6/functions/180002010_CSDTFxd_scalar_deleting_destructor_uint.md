# CSDTFxd::`scalar deleting destructor'(uint)

- ea: `0x180002010`
- end: `0x180002030`
- name: `??_GCSDTFxd@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CSDTFxd *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800023d8`
- `0x1800291b0`

## callees

- `0x180025b68`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002021`
- `ole32!CoTaskMemFree` at `0x180002021`

## pseudocode

```c
CSDTFxd *__fastcall CSDTFxd::`scalar deleting destructor'(CSDTFxd *this)
{
  CSDTFxd::~CSDTFxd(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180002010  push    rbx
0x180002012  sub     rsp, 20h
0x180002016  mov     rbx, rcx
0x180002019  call    ??1CSDTFxd@@QEAA@XZ; CSDTFxd::~CSDTFxd(void)
0x18000201e  mov     rcx, rbx; pv
0x180002021  call    cs:__imp_CoTaskMemFree
0x180002027  mov     rax, rbx
0x18000202a  add     rsp, 20h
0x18000202e  pop     rbx
0x18000202f  retn
```
