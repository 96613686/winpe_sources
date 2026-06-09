# CSTShell::`scalar deleting destructor'(uint)

- ea: `0x180004700`
- end: `0x180004720`
- name: `??_GCSTShell@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CSTShell *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800047f0`
- `0x1800053a0`

## callees

- `0x180004658`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004711`
- `ole32!CoTaskMemFree` at `0x180004711`

## pseudocode

```c
CSTShell *__fastcall CSTShell::`scalar deleting destructor'(CSTShell *this)
{
  CSTShell::~CSTShell(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180004700  push    rbx
0x180004702  sub     rsp, 20h
0x180004706  mov     rbx, rcx
0x180004709  call    ??1CSTShell@@QEAA@XZ; CSTShell::~CSTShell(void)
0x18000470e  mov     rcx, rbx; pv
0x180004711  call    cs:__imp_CoTaskMemFree
0x180004717  mov     rax, rbx
0x18000471a  add     rsp, 20h
0x18000471e  pop     rbx
0x18000471f  retn
```
