# WmiClass::`scalar deleting destructor'(uint)

- ea: `0x180009de8`
- end: `0x180009e07`
- name: `??_GWmiClass@@QEAAPEAXI@Z`
- size: `31`
- prototype: `WmiClass *__fastcall(WmiClass *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009d44`
- `0x180009e10`
- `0x18000a030`

## callees

- `0x180009c68`
- `0x180009cc0`

## pseudocode

```c
WmiClass *__fastcall WmiClass::`scalar deleting destructor'(WmiClass *this)
{
  WmiClass::~WmiClass(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009de8  push    rbx
0x180009dea  sub     rsp, 20h
0x180009dee  mov     rbx, rcx
0x180009df1  call    ??1WmiClass@@QEAA@XZ; WmiClass::~WmiClass(void)
0x180009df6  mov     rcx, rbx; void *
0x180009df9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009dfe  mov     rax, rbx
0x180009e01  add     rsp, 20h
0x180009e05  pop     rbx
0x180009e06  retn
```
